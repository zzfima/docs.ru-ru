---
title: Загрузка данных из файлов и других источников
description: В этой инструкции показано, как загружать данные для обработки и обучения в ML.NET. Изначально данные хранились в файлах или других источниках данных, таких как базы данных, JSON, XML или коллекции в памяти.
ms.date: 08/01/2019
ms.custom: mvc,how-to, title-hack-0625
ms.openlocfilehash: d5f3aab14a60a8c9860dc67f1cc98f3b1b3188ed
ms.sourcegitcommit: 8c6426a3d2adff5fbcbe1fed0f28eda718c15351
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2019
ms.locfileid: "68733375"
---
# <a name="load-data-from-files-and-other-sources"></a><span data-ttu-id="a46bf-104">Загрузка данных из файлов и других источников</span><span class="sxs-lookup"><span data-stu-id="a46bf-104">Load data from files and other sources</span></span>

<span data-ttu-id="a46bf-105">В этой инструкции показано, как загружать данные для обработки и обучения в ML.NET.</span><span class="sxs-lookup"><span data-stu-id="a46bf-105">This how-to shows you how to load data for processing and training into ML.NET.</span></span> <span data-ttu-id="a46bf-106">Изначально данные хранились в файлах или других источниках данных, таких как базы данных, JSON, XML или коллекции в памяти.</span><span class="sxs-lookup"><span data-stu-id="a46bf-106">The data is originally stored in files or other data sources such as databases, JSON, XML or in-memory collections.</span></span>

## <a name="create-the-data-model"></a><span data-ttu-id="a46bf-107">Создание модели данных</span><span class="sxs-lookup"><span data-stu-id="a46bf-107">Create the data model</span></span>

<span data-ttu-id="a46bf-108">ML.NET позволяет определять модели данных с помощью классов.</span><span class="sxs-lookup"><span data-stu-id="a46bf-108">ML.NET enables you to define data models via classes.</span></span> <span data-ttu-id="a46bf-109">Допустим, у нас есть следующие входные данные:</span><span class="sxs-lookup"><span data-stu-id="a46bf-109">For example, given the following input data:</span></span>

```text
Size (Sq. ft.), HistoricalPrice1 ($), HistoricalPrice2 ($), HistoricalPrice3 ($), Current Price ($)
700, 100000, 3000000, 250000, 500000
1000, 600000, 400000, 650000, 700000
```

<span data-ttu-id="a46bf-110">Создадим модель данных как в следующем фрагменте кода:</span><span class="sxs-lookup"><span data-stu-id="a46bf-110">Create a data model that represents the snippet below:</span></span>

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

### <a name="annotating-the-data-model-with-column-attributes"></a><span data-ttu-id="a46bf-111">Создание примечаний к модели данных с помощью атрибутов столбцов</span><span class="sxs-lookup"><span data-stu-id="a46bf-111">Annotating the data model with column attributes</span></span>

<span data-ttu-id="a46bf-112">Атрибуты предоставляют ML.NET дополнительные сведения о модели и источнике данных.</span><span class="sxs-lookup"><span data-stu-id="a46bf-112">Attributes give ML.NET more information about the data model and the data source.</span></span>

<span data-ttu-id="a46bf-113">Атрибут [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) определяет индексы столбцов свойств.</span><span class="sxs-lookup"><span data-stu-id="a46bf-113">The [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) attribute specifies your properties' column indices.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a46bf-114">[`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) требуется только при загрузке данных из файла.</span><span class="sxs-lookup"><span data-stu-id="a46bf-114">[`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) is only required when loading data from a file.</span></span>

<span data-ttu-id="a46bf-115">Загрузите столбцы как:</span><span class="sxs-lookup"><span data-stu-id="a46bf-115">Load columns as:</span></span> 
- <span data-ttu-id="a46bf-116">Отдельные столбцы, например `Size` и `CurrentPrices` в классе `HousingData`.</span><span class="sxs-lookup"><span data-stu-id="a46bf-116">Individual columns like `Size` and `CurrentPrices` in the `HousingData` class.</span></span>
- <span data-ttu-id="a46bf-117">Несколько столбцов за раз в виде вектора, например `HistoricalPrices` в классе `HousingData`.</span><span class="sxs-lookup"><span data-stu-id="a46bf-117">Multiple columns at a time in the form of a vector like `HistoricalPrices` in the `HousingData` class.</span></span>

<span data-ttu-id="a46bf-118">Если у вас есть свойство вектора, примените атрибут [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) к этому свойству в модели данных.</span><span class="sxs-lookup"><span data-stu-id="a46bf-118">If you have a vector property, apply the [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) attribute to the property in your data model.</span></span> <span data-ttu-id="a46bf-119">Следует отметить, что все элементы в векторе должны быть одного типа.</span><span class="sxs-lookup"><span data-stu-id="a46bf-119">It's important to note that all of the elements in the vector need to be the same type.</span></span> <span data-ttu-id="a46bf-120">Хранение разделенных столбцов позволяет упростить и облегчить проектирование признаков, но в случае большого количества столбцов работа с отдельными столбцами отрицательно влияет на скорость обучения.</span><span class="sxs-lookup"><span data-stu-id="a46bf-120">Keeping the columns separated allows for ease and flexibility of feature engineering, but for a very large number of columns, operating on the individual columns causes an impact on training speed.</span></span>

<span data-ttu-id="a46bf-121">ML.NET работает с именами столбцов.</span><span class="sxs-lookup"><span data-stu-id="a46bf-121">ML.NET Operates through column names.</span></span> <span data-ttu-id="a46bf-122">Если вы хотите изменить имя столбца, чтобы оно отличалось от имени свойства, используйте атрибут [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute).</span><span class="sxs-lookup"><span data-stu-id="a46bf-122">If you want to change the name of a column to something other than the property name, use the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute.</span></span> <span data-ttu-id="a46bf-123">При создании объектов в памяти тоже можно создавать объекты, используя имя свойства.</span><span class="sxs-lookup"><span data-stu-id="a46bf-123">When creating in-memory objects, you still create objects using the property name.</span></span> <span data-ttu-id="a46bf-124">Однако для обработки данных и создания моделей машинного обучения ML.NET переопределяет свойство со значением, указанным в атрибуте [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) и ссылается на него.</span><span class="sxs-lookup"><span data-stu-id="a46bf-124">However, for data processing and building machine learning models, ML.NET overrides and references the property with the value provided in the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute.</span></span>

## <a name="load-data-from-a-single-file"></a><span data-ttu-id="a46bf-125">Загрузка данных из отдельного файла</span><span class="sxs-lookup"><span data-stu-id="a46bf-125">Load data from a single file</span></span>

<span data-ttu-id="a46bf-126">Для загрузки данных из файла используйте метод [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) с моделью данных для загружаемых данных.</span><span class="sxs-lookup"><span data-stu-id="a46bf-126">To load data from a file use the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) method along with the data model for the data to be loaded.</span></span> <span data-ttu-id="a46bf-127">Поскольку параметр `separatorChar` по умолчанию разделяется знаками табуляции, измените его, если нужно для файла данных.</span><span class="sxs-lookup"><span data-stu-id="a46bf-127">Since `separatorChar` parameter is tab-delimited by default, change it for your data file as needed.</span></span> <span data-ttu-id="a46bf-128">Если в файле есть заголовок, присвойте параметру `hasHeader` значение `true`, чтобы игнорировать первую строку в файле и начать загрузку данных со второй строки.</span><span class="sxs-lookup"><span data-stu-id="a46bf-128">If your file has a header, set the `hasHeader` parameter to `true` to ignore the first line in the file and begin to load data from the second line.</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("my-data-file.csv", separatorChar: ',', hasHeader: true);
```

## <a name="load-data-from-multiple-files"></a><span data-ttu-id="a46bf-129">Загрузка данных из нескольких файлов</span><span class="sxs-lookup"><span data-stu-id="a46bf-129">Load data from multiple files</span></span>

<span data-ttu-id="a46bf-130">Если ваши данные хранятся в нескольких файлах с одинаковой схемой данных, в ML.NET можно загрузить данные из нескольких файлов, которые находятся в одном или нескольких каталогах.</span><span class="sxs-lookup"><span data-stu-id="a46bf-130">In the event that your data is stored in multiple files, as long as the data schema is the same, ML.NET allows you to load data from multiple files that are either in the same directory or multiple directories.</span></span>

### <a name="load-from-files-in-a-single-directory"></a><span data-ttu-id="a46bf-131">Загрузка данных из файлов в одном каталоге</span><span class="sxs-lookup"><span data-stu-id="a46bf-131">Load from files in a single directory</span></span>

<span data-ttu-id="a46bf-132">Если все файлы данных находятся в одном и том же каталоге, используйте в методе [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="a46bf-132">When all of your data files are in the same directory, use wildcards in the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) method.</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data File
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("Data/*", separatorChar: ',', hasHeader: true);
```

### <a name="load-from-files-in-multiple-directories"></a><span data-ttu-id="a46bf-133">Загрузка из файлов в нескольких каталогах</span><span class="sxs-lookup"><span data-stu-id="a46bf-133">Load from files in multiple directories</span></span>

<span data-ttu-id="a46bf-134">Чтобы загрузить данные из нескольких каталогов, с помощью метода [`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*) создайте [`TextLoader`](xref:Microsoft.ML.Data.TextLoader).</span><span class="sxs-lookup"><span data-stu-id="a46bf-134">To load data from multiple directories, use the [`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*) method to create a [`TextLoader`](xref:Microsoft.ML.Data.TextLoader).</span></span> <span data-ttu-id="a46bf-135">Затем с помощью метода [`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*) укажите пути к отдельным файлам (подстановочные знаки использовать нельзя).</span><span class="sxs-lookup"><span data-stu-id="a46bf-135">Then, use the [`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*) method and specify the individual file paths (wildcards can't be used).</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

// Create TextLoader
TextLoader textLoader = mlContext.Data.CreateTextLoader<HousingData>(separatorChar: ',', hasHeader: true);

// Load Data
IDataView data = textLoader.Load("DataFolder/SubFolder1/1.txt", "DataFolder/SubFolder2/1.txt");
```

## <a name="load-data-from-other-sources"></a><span data-ttu-id="a46bf-136">Загрузка данных из других источников</span><span class="sxs-lookup"><span data-stu-id="a46bf-136">Load data from other sources</span></span>

<span data-ttu-id="a46bf-137">Помимо загрузки данных, хранящихся в файлах, ML.NET позволяет загружать данные из таких источников, как, помимо прочего:</span><span class="sxs-lookup"><span data-stu-id="a46bf-137">In addition to loading data stored in files, ML.NET supports loading data from sources that include but are not limited to:</span></span>

- <span data-ttu-id="a46bf-138">Коллекции оперативной памяти</span><span class="sxs-lookup"><span data-stu-id="a46bf-138">In-memory collections</span></span>
- <span data-ttu-id="a46bf-139">располагаться в коде JSON или XML;</span><span class="sxs-lookup"><span data-stu-id="a46bf-139">JSON/XML</span></span>
- <span data-ttu-id="a46bf-140">Базы данных</span><span class="sxs-lookup"><span data-stu-id="a46bf-140">Databases</span></span>

<span data-ttu-id="a46bf-141">Обратите внимание на то, что при работе с источниками потоковой передачи данных ML.NET ожидает получить данные в виде коллекции в памяти.</span><span class="sxs-lookup"><span data-stu-id="a46bf-141">Note that when working with streaming sources, ML.NET expects input to be in the form of an in-memory collection.</span></span> <span data-ttu-id="a46bf-142">Это значит, что при работе с такими источниками, как JSON/XML, данные должны быть переведены в формат коллекции в памяти.</span><span class="sxs-lookup"><span data-stu-id="a46bf-142">Therefore, when working with sources like JSON/XML, make sure to format the data into an in-memory collection.</span></span>

<span data-ttu-id="a46bf-143">Допустим, у нас есть следующая коллекция в памяти:</span><span class="sxs-lookup"><span data-stu-id="a46bf-143">Given the following in-memory collection:</span></span>

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

<span data-ttu-id="a46bf-144">Загрузите эту коллекцию в памяти в [`IDataView`](xref:Microsoft.ML.IDataView) с помощью метода [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*):</span><span class="sxs-lookup"><span data-stu-id="a46bf-144">Load the in-memory collection into an [`IDataView`](xref:Microsoft.ML.IDataView) with the [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) method:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a46bf-145">[`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) предполагает, что [`IEnumerable`](xref:System.Collections.IEnumerable), откуда он загружается, является потокобезопасным.</span><span class="sxs-lookup"><span data-stu-id="a46bf-145">[`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) assumes that the [`IEnumerable`](xref:System.Collections.IEnumerable) it loads from is thread-safe.</span></span> 

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromEnumerable<HousingData>(inMemoryCollection);
```
