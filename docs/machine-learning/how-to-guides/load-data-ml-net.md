---
title: Загрузка данных из файлов и других источников
description: В этой инструкции показано, как загружать данные для обработки и обучения в ML.NET. Изначально данные хранились в файлах или других источниках данных, таких как базы данных, JSON, XML или коллекции в памяти.
ms.date: 09/11/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to, title-hack-0625
ms.openlocfilehash: 4008f38bf4a20113a3f5c865e38222e5b82f2acc
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991366"
---
# <a name="load-data-from-files-and-other-sources"></a>Загрузка данных из файлов и других источников

В этой инструкции показано, как загружать данные для обработки и обучения в ML.NET. Изначально данные хранились в файлах или других источниках данных, таких как базы данных, JSON, XML или коллекции в памяти.

## <a name="create-the-data-model"></a>Создание модели данных

ML.NET позволяет определять модели данных с помощью классов. Допустим, у нас есть следующие входные данные:

```text
Size (Sq. ft.), HistoricalPrice1 ($), HistoricalPrice2 ($), HistoricalPrice3 ($), Current Price ($)
700, 100000, 3000000, 250000, 500000
1000, 600000, 400000, 650000, 700000
```

Создадим модель данных как в следующем фрагменте кода:

```csharp
public class HousingData
{
    [LoadColumn(0)]
    public float Size { get; set; }

    [LoadColumn(1, 3)]
    [VectorType(3)]
    public float[] HistoricalPrices { get; set; }

    [LoadColumn(4)]
    [ColumnName("Label")]
    public float CurrentPrice { get; set; }
}
```

### <a name="annotating-the-data-model-with-column-attributes"></a>Создание примечаний к модели данных с помощью атрибутов столбцов

Атрибуты предоставляют ML.NET дополнительные сведения о модели и источнике данных.

Атрибут [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) определяет индексы столбцов свойств.

> [!IMPORTANT]
> [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) требуется только при загрузке данных из файла.

Загрузите столбцы как:

- Отдельные столбцы, например `Size` и `CurrentPrices` в классе `HousingData`.
- Несколько столбцов за раз в виде вектора, например `HistoricalPrices` в классе `HousingData`.

Если у вас есть свойство вектора, примените атрибут [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) к этому свойству в модели данных. Следует отметить, что все элементы в векторе должны быть одного типа. Хранение разделенных столбцов позволяет упростить и облегчить проектирование признаков, но в случае большого количества столбцов работа с отдельными столбцами отрицательно влияет на скорость обучения.

ML.NET работает с именами столбцов. Если вы хотите изменить имя столбца, чтобы оно отличалось от имени свойства, используйте атрибут [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute). При создании объектов в памяти тоже можно создавать объекты, используя имя свойства. Однако для обработки данных и создания моделей машинного обучения ML.NET переопределяет свойство со значением, указанным в атрибуте [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) и ссылается на него.

## <a name="load-data-from-a-single-file"></a>Загрузка данных из отдельного файла

Для загрузки данных из файла используйте метод [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) с моделью данных для загружаемых данных. Поскольку параметр `separatorChar` по умолчанию разделяется знаками табуляции, измените его, если нужно для файла данных. Если в файле есть заголовок, присвойте параметру `hasHeader` значение `true`, чтобы игнорировать первую строку в файле и начать загрузку данных со второй строки.

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("my-data-file.csv", separatorChar: ',', hasHeader: true);
```

## <a name="load-data-from-multiple-files"></a>Загрузка данных из нескольких файлов

Если ваши данные хранятся в нескольких файлах с одинаковой схемой данных, в ML.NET можно загрузить данные из нескольких файлов, которые находятся в одном или нескольких каталогах.

### <a name="load-from-files-in-a-single-directory"></a>Загрузка данных из файлов в одном каталоге

Если все файлы данных находятся в одном и том же каталоге, используйте в методе [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) подстановочные знаки.

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data File
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("Data/*", separatorChar: ',', hasHeader: true);
```

### <a name="load-from-files-in-multiple-directories"></a>Загрузка из файлов в нескольких каталогах

Чтобы загрузить данные из нескольких каталогов, с помощью метода [`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*) создайте [`TextLoader`](xref:Microsoft.ML.Data.TextLoader). Затем с помощью метода [`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*) укажите пути к отдельным файлам (подстановочные знаки использовать нельзя).

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

// Create TextLoader
TextLoader textLoader = mlContext.Data.CreateTextLoader<HousingData>(separatorChar: ',', hasHeader: true);

// Load Data
IDataView data = textLoader.Load("DataFolder/SubFolder1/1.txt", "DataFolder/SubFolder2/1.txt");
```

## <a name="load-data-from-a-relational-database"></a>Загрузка данных из реляционной базы данных

> [!NOTE]
> Сейчас DatabaseLoader находится на этапе предварительной версии. Его можно использовать, указав ссылки на пакеты NuGet [Microsoft.ML.Experimental](https://www.nuget.org/packages/Microsoft.ML.Experimental/0.16.0-preview) и [System.Data.SqlClient](https://www.nuget.org/packages/System.Data.SqlClient/4.6.1).

ML.NET поддерживает загрузку данных из различных реляционных баз данных , поддерживаемых [`System.Data`](xref:System.Data), включая SQL Server, базу данных SQL Azure, Oracle, SQLite, PostgreSQL, Progress, IBM DB2 и многие другие.

Имеется база данных с таблицей `House` и следующей схемой:

```SQL
CREATE TABLE [House] (
    [HouseId] int NOT NULL IDENTITY,
    [Size] real NOT NULL,
    [Price] real NOT NULL
    CONSTRAINT [PK_House] PRIMARY KEY ([HouseId])
);
```

Можно моделировать данные с помощью класса, например `HouseData`.

```csharp
public class HouseData
{
    public float Size { get; set; }

    public float Price { get; set; }
}
```

Затем в приложении создайте `DatabaseLoader`.

```csharp
MLContext mlContext = new MLContext();

DatabaseLoader loader = mlContext.Data.CreateDatabaseLoader<HouseData>();
```

Определите строку подключения, а также команду SQL для выполнения в базе данных и создайте экземпляр `DatabaseSource`. В этом примере используется база данных LocalDB SQL Server с путем к файлу. Однако DatabaseLoader поддерживает любые другие допустимые строки подключения для баз данных в локальной среде и в облаке.

```csharp
string connectionString = @"Data Source=(LocalDB)\MSSQLLocalDB;AttachDbFilename=<YOUR-DB-FILEPATH>;Database=<YOUR-DB-NAME>;Integrated Security=True;Connect Timeout=30";

string sqlCommand = "SELECT Size,Price FROM House";

DatabaseSource dbSource = new DatabaseSource(SqlClientFactory.Instance,connectionString,sqlCommand);
```

Наконец, используйте метод `Load` для загрузки данных в [`IDataView`](xref:Microsoft.ML.IDataView).

```csharp
IDataView data = loader.Load(dbSource);
```

## <a name="load-data-from-other-sources"></a>Загрузка данных из других источников

Помимо загрузки данных, хранящихся в файлах, ML.NET позволяет загружать данные из таких источников, как, помимо прочего:

- Коллекции оперативной памяти
- располагаться в коде JSON или XML;

Обратите внимание на то, что при работе с источниками потоковой передачи данных ML.NET ожидает получить данные в виде коллекции в памяти. Это значит, что при работе с такими источниками, как JSON/XML, данные должны быть переведены в формат коллекции в памяти.

Допустим, у нас есть следующая коллекция в памяти:

```csharp
HousingData[] inMemoryCollection = new HousingData[]
{
    new HousingData
    {
        Size =700f,
        HistoricalPrices = new float[]
        {
            100000f, 3000000f, 250000f
        },
        CurrentPrice = 500000f
    },
    new HousingData
    {
        Size =1000f,
        HistoricalPrices = new float[]
        {
            600000f, 400000f, 650000f
        },
        CurrentPrice=700000f
    }
};
```

Загрузите эту коллекцию в памяти в [`IDataView`](xref:Microsoft.ML.IDataView) с помощью метода [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*):

> [!IMPORTANT]
> [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) предполагает, что [`IEnumerable`](xref:System.Collections.IEnumerable), откуда он загружается, является потокобезопасным.

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromEnumerable<HousingData>(inMemoryCollection);
```
