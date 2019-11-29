---
title: Загрузка данных из файлов и других источников
description: Узнайте, как загружать данные для обработки и обучения в ML.NET с помощью интерфейса API. Данные хранятся в файлах, базах данных, JSON, XML или коллекциях в памяти.
ms.date: 11/07/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to, title-hack-0625
ms.openlocfilehash: 83aaae2d2e75b3076841750bf5d505390a538bc0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344759"
---
# <a name="load-data-from-files-and-other-sources"></a><span data-ttu-id="d69c3-104">Загрузка данных из файлов и других источников</span><span class="sxs-lookup"><span data-stu-id="d69c3-104">Load data from files and other sources</span></span>

<span data-ttu-id="d69c3-105">Узнайте, как загружать данные для обработки и обучения в ML.NET с помощью интерфейса API.</span><span class="sxs-lookup"><span data-stu-id="d69c3-105">Learn how to load data for processing and training into ML.NET using the API.</span></span> <span data-ttu-id="d69c3-106">Изначально данные хранились в файлах или других источниках данных, таких как базы данных, JSON, XML или коллекции в памяти.</span><span class="sxs-lookup"><span data-stu-id="d69c3-106">The data is originally stored in files or other data sources such as databases, JSON, XML or in-memory collections.</span></span>

<span data-ttu-id="d69c3-107">Если вы используете построитель моделей, см. руководство по [загрузке обучающих данных в построитель моделей](load-data-model-builder.md).</span><span class="sxs-lookup"><span data-stu-id="d69c3-107">If you're using Model Builder, see [Load training data into Model Builder](load-data-model-builder.md).</span></span>

## <a name="create-the-data-model"></a><span data-ttu-id="d69c3-108">Создание модели данных</span><span class="sxs-lookup"><span data-stu-id="d69c3-108">Create the data model</span></span>

<span data-ttu-id="d69c3-109">ML.NET позволяет определять модели данных с помощью классов.</span><span class="sxs-lookup"><span data-stu-id="d69c3-109">ML.NET enables you to define data models via classes.</span></span> <span data-ttu-id="d69c3-110">Допустим, у нас есть следующие входные данные:</span><span class="sxs-lookup"><span data-stu-id="d69c3-110">For example, given the following input data:</span></span>

```text
Size (Sq. ft.), HistoricalPrice1 ($), HistoricalPrice2 ($), HistoricalPrice3 ($), Current Price ($)
700, 100000, 3000000, 250000, 500000
1000, 600000, 400000, 650000, 700000
```

<span data-ttu-id="d69c3-111">Создадим модель данных как в следующем фрагменте кода:</span><span class="sxs-lookup"><span data-stu-id="d69c3-111">Create a data model that represents the snippet below:</span></span>

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

### <a name="annotating-the-data-model-with-column-attributes"></a><span data-ttu-id="d69c3-112">Создание примечаний к модели данных с помощью атрибутов столбцов</span><span class="sxs-lookup"><span data-stu-id="d69c3-112">Annotating the data model with column attributes</span></span>

<span data-ttu-id="d69c3-113">Атрибуты предоставляют ML.NET дополнительные сведения о модели и источнике данных.</span><span class="sxs-lookup"><span data-stu-id="d69c3-113">Attributes give ML.NET more information about the data model and the data source.</span></span>

<span data-ttu-id="d69c3-114">Атрибут [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) определяет индексы столбцов свойств.</span><span class="sxs-lookup"><span data-stu-id="d69c3-114">The [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) attribute specifies your properties' column indices.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d69c3-115">[`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) требуется только при загрузке данных из файла.</span><span class="sxs-lookup"><span data-stu-id="d69c3-115">[`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) is only required when loading data from a file.</span></span>

<span data-ttu-id="d69c3-116">Загрузите столбцы как:</span><span class="sxs-lookup"><span data-stu-id="d69c3-116">Load columns as:</span></span>

- <span data-ttu-id="d69c3-117">Отдельные столбцы, например `Size` и `CurrentPrices` в классе `HousingData`.</span><span class="sxs-lookup"><span data-stu-id="d69c3-117">Individual columns like `Size` and `CurrentPrices` in the `HousingData` class.</span></span>
- <span data-ttu-id="d69c3-118">Несколько столбцов за раз в виде вектора, например `HistoricalPrices` в классе `HousingData`.</span><span class="sxs-lookup"><span data-stu-id="d69c3-118">Multiple columns at a time in the form of a vector like `HistoricalPrices` in the `HousingData` class.</span></span>

<span data-ttu-id="d69c3-119">Если у вас есть свойство вектора, примените атрибут [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) к этому свойству в модели данных.</span><span class="sxs-lookup"><span data-stu-id="d69c3-119">If you have a vector property, apply the [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) attribute to the property in your data model.</span></span> <span data-ttu-id="d69c3-120">Следует отметить, что все элементы в векторе должны быть одного типа.</span><span class="sxs-lookup"><span data-stu-id="d69c3-120">It's important to note that all of the elements in the vector need to be the same type.</span></span> <span data-ttu-id="d69c3-121">Хранение разделенных столбцов позволяет упростить и облегчить проектирование признаков, но в случае большого количества столбцов работа с отдельными столбцами отрицательно влияет на скорость обучения.</span><span class="sxs-lookup"><span data-stu-id="d69c3-121">Keeping the columns separated allows for ease and flexibility of feature engineering, but for a very large number of columns, operating on the individual columns causes an impact on training speed.</span></span>

<span data-ttu-id="d69c3-122">ML.NET работает с именами столбцов.</span><span class="sxs-lookup"><span data-stu-id="d69c3-122">ML.NET Operates through column names.</span></span> <span data-ttu-id="d69c3-123">Если вы хотите изменить имя столбца, чтобы оно отличалось от имени свойства, используйте атрибут [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute).</span><span class="sxs-lookup"><span data-stu-id="d69c3-123">If you want to change the name of a column to something other than the property name, use the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute.</span></span> <span data-ttu-id="d69c3-124">При создании объектов в памяти тоже можно создавать объекты, используя имя свойства.</span><span class="sxs-lookup"><span data-stu-id="d69c3-124">When creating in-memory objects, you still create objects using the property name.</span></span> <span data-ttu-id="d69c3-125">Однако для обработки данных и создания моделей машинного обучения ML.NET переопределяет свойство со значением, указанным в атрибуте [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) и ссылается на него.</span><span class="sxs-lookup"><span data-stu-id="d69c3-125">However, for data processing and building machine learning models, ML.NET overrides and references the property with the value provided in the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute.</span></span>

## <a name="load-data-from-a-single-file"></a><span data-ttu-id="d69c3-126">Загрузка данных из отдельного файла</span><span class="sxs-lookup"><span data-stu-id="d69c3-126">Load data from a single file</span></span>

<span data-ttu-id="d69c3-127">Для загрузки данных из файла используйте метод [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) с моделью данных для загружаемых данных.</span><span class="sxs-lookup"><span data-stu-id="d69c3-127">To load data from a file use the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) method along with the data model for the data to be loaded.</span></span> <span data-ttu-id="d69c3-128">Поскольку параметр `separatorChar` по умолчанию разделяется знаками табуляции, измените его, если нужно для файла данных.</span><span class="sxs-lookup"><span data-stu-id="d69c3-128">Since `separatorChar` parameter is tab-delimited by default, change it for your data file as needed.</span></span> <span data-ttu-id="d69c3-129">Если в файле есть заголовок, присвойте параметру `hasHeader` значение `true`, чтобы игнорировать первую строку в файле и начать загрузку данных со второй строки.</span><span class="sxs-lookup"><span data-stu-id="d69c3-129">If your file has a header, set the `hasHeader` parameter to `true` to ignore the first line in the file and begin to load data from the second line.</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("my-data-file.csv", separatorChar: ',', hasHeader: true);
```

## <a name="load-data-from-multiple-files"></a><span data-ttu-id="d69c3-130">Загрузка данных из нескольких файлов</span><span class="sxs-lookup"><span data-stu-id="d69c3-130">Load data from multiple files</span></span>

<span data-ttu-id="d69c3-131">Если ваши данные хранятся в нескольких файлах с одинаковой схемой данных, в ML.NET можно загрузить данные из нескольких файлов, которые находятся в одном или нескольких каталогах.</span><span class="sxs-lookup"><span data-stu-id="d69c3-131">In the event that your data is stored in multiple files, as long as the data schema is the same, ML.NET allows you to load data from multiple files that are either in the same directory or multiple directories.</span></span>

### <a name="load-from-files-in-a-single-directory"></a><span data-ttu-id="d69c3-132">Загрузка данных из файлов в одном каталоге</span><span class="sxs-lookup"><span data-stu-id="d69c3-132">Load from files in a single directory</span></span>

<span data-ttu-id="d69c3-133">Если все файлы данных находятся в одном и том же каталоге, используйте в методе [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="d69c3-133">When all of your data files are in the same directory, use wildcards in the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) method.</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data File
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("Data/*", separatorChar: ',', hasHeader: true);
```

### <a name="load-from-files-in-multiple-directories"></a><span data-ttu-id="d69c3-134">Загрузка из файлов в нескольких каталогах</span><span class="sxs-lookup"><span data-stu-id="d69c3-134">Load from files in multiple directories</span></span>

<span data-ttu-id="d69c3-135">Чтобы загрузить данные из нескольких каталогов, с помощью метода [`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*) создайте [`TextLoader`](xref:Microsoft.ML.Data.TextLoader).</span><span class="sxs-lookup"><span data-stu-id="d69c3-135">To load data from multiple directories, use the [`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*) method to create a [`TextLoader`](xref:Microsoft.ML.Data.TextLoader).</span></span> <span data-ttu-id="d69c3-136">Затем с помощью метода [`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*) укажите пути к отдельным файлам (подстановочные знаки использовать нельзя).</span><span class="sxs-lookup"><span data-stu-id="d69c3-136">Then, use the [`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*) method and specify the individual file paths (wildcards can't be used).</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

// Create TextLoader
TextLoader textLoader = mlContext.Data.CreateTextLoader<HousingData>(separatorChar: ',', hasHeader: true);

// Load Data
IDataView data = textLoader.Load("DataFolder/SubFolder1/1.txt", "DataFolder/SubFolder2/1.txt");
```

## <a name="load-data-from-a-relational-database"></a><span data-ttu-id="d69c3-137">Загрузка данных из реляционной базы данных</span><span class="sxs-lookup"><span data-stu-id="d69c3-137">Load data from a relational database</span></span>

<span data-ttu-id="d69c3-138">ML.NET поддерживает загрузку данных из различных реляционных баз данных , поддерживаемых [`System.Data`](xref:System.Data), включая SQL Server, базу данных SQL Azure, Oracle, SQLite, PostgreSQL, Progress, IBM DB2 и многие другие.</span><span class="sxs-lookup"><span data-stu-id="d69c3-138">ML.NET supports loading data from a variety of relational databases supported by [`System.Data`](xref:System.Data) that include SQL Server, Azure SQL Database, Oracle, SQLite, PostgreSQL, Progress, IBM DB2, and many more.</span></span>

> [!NOTE]
> <span data-ttu-id="d69c3-139">Чтобы использовать `DatabaseLoader`, необходимо сослаться на пакет NuGet [System.Data.SqlClient](https://www.nuget.org/packages/System.Data.SqlClient).</span><span class="sxs-lookup"><span data-stu-id="d69c3-139">To use `DatabaseLoader`, reference the [System.Data.SqlClient](https://www.nuget.org/packages/System.Data.SqlClient) NuGet package.</span></span>

<span data-ttu-id="d69c3-140">Имеется база данных с таблицей `House` и следующей схемой:</span><span class="sxs-lookup"><span data-stu-id="d69c3-140">Given a database with a table named `House` and the following schema:</span></span>

```SQL
CREATE TABLE [House] (
    [HouseId] INT NOT NULL IDENTITY,
    [Size] INT NOT NULL,
    [NumBed] INT NOT NULL,
    [Price] REAL NOT NULL
    CONSTRAINT [PK_House] PRIMARY KEY ([HouseId])
);
```

<span data-ttu-id="d69c3-141">Можно моделировать данные с помощью класса, например `HouseData`.</span><span class="sxs-lookup"><span data-stu-id="d69c3-141">The data can be modeled by a class like `HouseData`.</span></span>

```csharp
public class HouseData
{
    public float Size { get; set; }

    public float NumBed { get; set; }

    public float Price { get; set; }
}
```

<span data-ttu-id="d69c3-142">Затем в приложении создайте `DatabaseLoader`.</span><span class="sxs-lookup"><span data-stu-id="d69c3-142">Then, inside of your application, create a `DatabaseLoader`.</span></span>

```csharp
MLContext mlContext = new MLContext();

DatabaseLoader loader = mlContext.Data.CreateDatabaseLoader<HouseData>();
```

<span data-ttu-id="d69c3-143">Определите строку подключения, а также команду SQL для выполнения в базе данных и создайте экземпляр `DatabaseSource`.</span><span class="sxs-lookup"><span data-stu-id="d69c3-143">Define your connection string as well as the SQL command to be executed on the database and create a `DatabaseSource` instance.</span></span> <span data-ttu-id="d69c3-144">В этом примере используется база данных LocalDB SQL Server с путем к файлу.</span><span class="sxs-lookup"><span data-stu-id="d69c3-144">This sample uses a LocalDB SQL Server database with a file path.</span></span> <span data-ttu-id="d69c3-145">Однако DatabaseLoader поддерживает любые другие допустимые строки подключения для баз данных в локальной среде и в облаке.</span><span class="sxs-lookup"><span data-stu-id="d69c3-145">However, DatabaseLoader supports any other valid connection string for databases on-premises and in the cloud.</span></span>

```csharp
string connectionString = @"Data Source=(LocalDB)\MSSQLLocalDB;AttachDbFilename=<YOUR-DB-FILEPATH>;Database=<YOUR-DB-NAME>;Integrated Security=True;Connect Timeout=30";

string sqlCommand = "SELECT Size, CAST(NumBed as REAL) as NumBed, Price FROM House";

DatabaseSource dbSource = new DatabaseSource(SqlClientFactory.Instance, connectionString, sqlCommand);
```

<span data-ttu-id="d69c3-146">Числовые данные, не являющиеся типами [`Real`](xref:System.Data.SqlDbType), необходимо преобразовать в [`Real`](xref:System.Data.SqlDbType).</span><span class="sxs-lookup"><span data-stu-id="d69c3-146">Numerical data that is not of type [`Real`](xref:System.Data.SqlDbType) has to be converted to [`Real`](xref:System.Data.SqlDbType).</span></span> <span data-ttu-id="d69c3-147">Тип [`Real`](xref:System.Data.SqlDbType) представлен значением с плавающей запятой одиночной точности или [`Single`](xref:System.Single) (тип входных данных, ожидаемый алгоритмами ML.NET).</span><span class="sxs-lookup"><span data-stu-id="d69c3-147">The [`Real`](xref:System.Data.SqlDbType) type is represented as a single-precision floating-point value or [`Single`](xref:System.Single), the input type expected by ML.NET algorithms.</span></span> <span data-ttu-id="d69c3-148">В этом примере столбец `NumBed` является целым числом в базе данных.</span><span class="sxs-lookup"><span data-stu-id="d69c3-148">In this sample, the `NumBed` column is an integer in the database.</span></span> <span data-ttu-id="d69c3-149">С помощью встроенной функции `CAST` выполняется преобразование в [`Real`](xref:System.Data.SqlDbType).</span><span class="sxs-lookup"><span data-stu-id="d69c3-149">Using the `CAST` built-in function, it's converted to [`Real`](xref:System.Data.SqlDbType).</span></span> <span data-ttu-id="d69c3-150">Так как свойство `Price` уже имеет тип [`Real`](xref:System.Data.SqlDbType), оно загружается как есть.</span><span class="sxs-lookup"><span data-stu-id="d69c3-150">Because the `Price` property is already of type [`Real`](xref:System.Data.SqlDbType) it is loaded as is.</span></span>

<span data-ttu-id="d69c3-151">Используйте метод `Load` для загрузки данных в [`IDataView`](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="d69c3-151">Use the `Load` method to load the data into an [`IDataView`](xref:Microsoft.ML.IDataView).</span></span>

```csharp
IDataView data = loader.Load(dbSource);
```

## <a name="load-data-from-other-sources"></a><span data-ttu-id="d69c3-152">Загрузка данных из других источников</span><span class="sxs-lookup"><span data-stu-id="d69c3-152">Load data from other sources</span></span>

<span data-ttu-id="d69c3-153">Помимо загрузки данных, хранящихся в файлах, ML.NET позволяет загружать данные из таких источников, как, помимо прочего:</span><span class="sxs-lookup"><span data-stu-id="d69c3-153">In addition to loading data stored in files, ML.NET supports loading data from sources that include but are not limited to:</span></span>

- <span data-ttu-id="d69c3-154">Коллекции оперативной памяти</span><span class="sxs-lookup"><span data-stu-id="d69c3-154">In-memory collections</span></span>
- <span data-ttu-id="d69c3-155">располагаться в коде JSON или XML;</span><span class="sxs-lookup"><span data-stu-id="d69c3-155">JSON/XML</span></span>

<span data-ttu-id="d69c3-156">Обратите внимание на то, что при работе с источниками потоковой передачи данных ML.NET ожидает получить данные в виде коллекции в памяти.</span><span class="sxs-lookup"><span data-stu-id="d69c3-156">Note that when working with streaming sources, ML.NET expects input to be in the form of an in-memory collection.</span></span> <span data-ttu-id="d69c3-157">Это значит, что при работе с такими источниками, как JSON/XML, данные должны быть переведены в формат коллекции в памяти.</span><span class="sxs-lookup"><span data-stu-id="d69c3-157">Therefore, when working with sources like JSON/XML, make sure to format the data into an in-memory collection.</span></span>

<span data-ttu-id="d69c3-158">Допустим, у нас есть следующая коллекция в памяти:</span><span class="sxs-lookup"><span data-stu-id="d69c3-158">Given the following in-memory collection:</span></span>

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

<span data-ttu-id="d69c3-159">Загрузите эту коллекцию в памяти в [`IDataView`](xref:Microsoft.ML.IDataView) с помощью метода [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*):</span><span class="sxs-lookup"><span data-stu-id="d69c3-159">Load the in-memory collection into an [`IDataView`](xref:Microsoft.ML.IDataView) with the [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) method:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d69c3-160">[`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) предполагает, что [`IEnumerable`](xref:System.Collections.IEnumerable), откуда он загружается, является потокобезопасным.</span><span class="sxs-lookup"><span data-stu-id="d69c3-160">[`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) assumes that the [`IEnumerable`](xref:System.Collections.IEnumerable) it loads from is thread-safe.</span></span>

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromEnumerable<HousingData>(inMemoryCollection);
```

## <a name="next-steps"></a><span data-ttu-id="d69c3-161">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="d69c3-161">Next steps</span></span>

- <span data-ttu-id="d69c3-162">Сведения об очистке или иной обработке данных см. в статье [Подготовка данных для построения модели](prepare-data-ml-net.md).</span><span class="sxs-lookup"><span data-stu-id="d69c3-162">To clean or otherwise process data, see [Prepare data for building a model](prepare-data-ml-net.md).</span></span>
- <span data-ttu-id="d69c3-163">Когда вы будете готовы к созданию модели, обратитесь к статье [Обучение и оценка модели](train-machine-learning-model-ml-net.md).</span><span class="sxs-lookup"><span data-stu-id="d69c3-163">When you're ready to build a model, see [Train and evaluate a model](train-machine-learning-model-ml-net.md).</span></span>
