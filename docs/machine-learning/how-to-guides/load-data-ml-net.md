---
title: Загрузка данных
description: Загрузка файла данных и потоковая передача данных в ML.NET
ms.date: 05/03/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 6edcc92b610e2e1f5e21c371b9f0aefd0b216d31
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063647"
---
# <a name="load-data-from-file-and-in-memory-sources"></a><span data-ttu-id="67c0d-103">Загрузка данных из файлов и источников в памяти</span><span class="sxs-lookup"><span data-stu-id="67c0d-103">Load data from file and in-memory sources</span></span>

<span data-ttu-id="67c0d-104">В этой инструкции показано, как загружать данные для обработки и обучения в ML.NET.</span><span class="sxs-lookup"><span data-stu-id="67c0d-104">This how-to shows you how to load data for processing and training into ML.NET.</span></span> <span data-ttu-id="67c0d-105">Изначально данные хранились в файлах или в источниках данных в режиме реального времени/потоковой передачи.</span><span class="sxs-lookup"><span data-stu-id="67c0d-105">The data is originally stored in files or real-time / streaming data sources.</span></span>

## <a name="create-the-data-model"></a><span data-ttu-id="67c0d-106">Создание модели данных</span><span class="sxs-lookup"><span data-stu-id="67c0d-106">Create the data model</span></span>

<span data-ttu-id="67c0d-107">ML.NET позволяет определять модели данных с помощью классов.</span><span class="sxs-lookup"><span data-stu-id="67c0d-107">ML.NET enables you to define data models via classes.</span></span> <span data-ttu-id="67c0d-108">Допустим, у нас есть следующие входные данные:</span><span class="sxs-lookup"><span data-stu-id="67c0d-108">For example, given the following input data:</span></span>

```text
Size (Sq. ft.), HistoricalPrice1 ($), HistoricalPrice2 ($), HistoricalPrice3 ($), Current Price ($)
700, 100000, 3000000, 250000, 500000
1000, 600000, 400000, 650000, 700000
```

<span data-ttu-id="67c0d-109">Создадим модель данных как в следующем фрагменте кода:</span><span class="sxs-lookup"><span data-stu-id="67c0d-109">Create a data model that represents the snippet below:</span></span>

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

### <a name="annotating-the-data-model-with-column-attributes"></a><span data-ttu-id="67c0d-110">Создание примечаний к модели данных с помощью атрибутов столбцов</span><span class="sxs-lookup"><span data-stu-id="67c0d-110">Annotating the data model with column attributes</span></span>

<span data-ttu-id="67c0d-111">Атрибуты предоставляют ML.NET дополнительные сведения о модели и источнике данных.</span><span class="sxs-lookup"><span data-stu-id="67c0d-111">Attributes give ML.NET more information about the data model and the data source.</span></span>

<span data-ttu-id="67c0d-112">Атрибут [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) определяет индексы столбцов свойств.</span><span class="sxs-lookup"><span data-stu-id="67c0d-112">The [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) attribute specifies your properties' column indices.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67c0d-113">[`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) требуется только при загрузке данных из файла.</span><span class="sxs-lookup"><span data-stu-id="67c0d-113">[`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) is only required when loading data from a file.</span></span>

<span data-ttu-id="67c0d-114">Загрузите столбцы как:</span><span class="sxs-lookup"><span data-stu-id="67c0d-114">Load columns as:</span></span> 
- <span data-ttu-id="67c0d-115">Отдельные столбцы, например `Size` и `CurrentPrices` в классе `HousingData`.</span><span class="sxs-lookup"><span data-stu-id="67c0d-115">Individual columns like `Size` and `CurrentPrices` in the `HousingData` class.</span></span>
- <span data-ttu-id="67c0d-116">Несколько столбцов за раз в виде вектора, например `HistoricalPrices` в классе `HousingData`.</span><span class="sxs-lookup"><span data-stu-id="67c0d-116">Multiple columns at a time in the form of a vector like `HistoricalPrices` in the `HousingData` class.</span></span>

<span data-ttu-id="67c0d-117">Если у вас есть свойство вектора, примените атрибут [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) к этому свойству в модели данных.</span><span class="sxs-lookup"><span data-stu-id="67c0d-117">If you have a vector property, apply the [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) attribute to the property in your data model.</span></span> <span data-ttu-id="67c0d-118">Следует отметить, что все элементы в векторе должны быть одного типа.</span><span class="sxs-lookup"><span data-stu-id="67c0d-118">It's important to note that all of the elements in the vector need to be the same type.</span></span>

<span data-ttu-id="67c0d-119">ML.NET работает с именами столбцов.</span><span class="sxs-lookup"><span data-stu-id="67c0d-119">ML.NET Operates through column names.</span></span> <span data-ttu-id="67c0d-120">Если вы хотите изменить имя столбца, чтобы оно отличалось от имени свойства, используйте атрибут [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute).</span><span class="sxs-lookup"><span data-stu-id="67c0d-120">If you want to change the name of a column to something other than the property name, use the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute.</span></span> <span data-ttu-id="67c0d-121">При создании объектов в памяти тоже можно создавать объекты, используя имя свойства.</span><span class="sxs-lookup"><span data-stu-id="67c0d-121">When creating in-memory objects, you still create objects using the property name.</span></span> <span data-ttu-id="67c0d-122">Однако для обработки данных и создания моделей машинного обучения ML.NET переопределяет свойство со значением, указанным в атрибуте [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) и ссылается на него.</span><span class="sxs-lookup"><span data-stu-id="67c0d-122">However, for data processing and building machine learning models, ML.NET overrides and references the property with the value provided in the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute.</span></span>

## <a name="load-data-from-a-single-file"></a><span data-ttu-id="67c0d-123">Загрузка данных из отдельного файла</span><span class="sxs-lookup"><span data-stu-id="67c0d-123">Load data from a single file</span></span>

<span data-ttu-id="67c0d-124">Для загрузки данных из файла используйте метод [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) с моделью данных для загружаемых данных.</span><span class="sxs-lookup"><span data-stu-id="67c0d-124">To load data from a file use the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) method along with the data model for the data to be loaded.</span></span> <span data-ttu-id="67c0d-125">Поскольку параметр `separatorChar` по умолчанию разделяется знаками табуляции, измените его, если нужно для файла данных.</span><span class="sxs-lookup"><span data-stu-id="67c0d-125">Since `separatorChar` parameter is tab-delimited by default, change it for your data file as needed.</span></span> <span data-ttu-id="67c0d-126">Если в файле есть заголовок, присвойте параметру `hasHeader` значение `true`, чтобы игнорировать первую строку в файле и начать загрузку данных со второй строки.</span><span class="sxs-lookup"><span data-stu-id="67c0d-126">If your file has a header, set the `hasHeader` parameter to `true` to ignore the first line in the file and begin to load data from the second line.</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("my-data-file.csv", separatorChar: ',', hasHeader: true);
```

## <a name="load-data-from-multiple-files"></a><span data-ttu-id="67c0d-127">Загрузка данных из нескольких файлов</span><span class="sxs-lookup"><span data-stu-id="67c0d-127">Load data from multiple files</span></span>

<span data-ttu-id="67c0d-128">Если ваши данные хранятся в нескольких файлах с одинаковой схемой данных, в ML.NET можно загрузить данные из нескольких файлов, которые находятся в одном или нескольких каталогах.</span><span class="sxs-lookup"><span data-stu-id="67c0d-128">In the event that your data is stored in multiple files, as long as the data schema is the same, ML.NET allows you to load data from multiple files that are either in the same directory or multiple directories.</span></span>

### <a name="load-from-files-in-a-single-directory"></a><span data-ttu-id="67c0d-129">Загрузка данных из файлов в одном каталоге</span><span class="sxs-lookup"><span data-stu-id="67c0d-129">Load from files in a single directory</span></span>

<span data-ttu-id="67c0d-130">Если все файлы данных находятся в одном и том же каталоге, используйте в методе [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="67c0d-130">When all of your data files are in the same directory, use wildcards in the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) method.</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data File
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("Data/*", separatorChar: ',', hasHeader: true);
```

### <a name="load-from-files-in-multiple-directories"></a><span data-ttu-id="67c0d-131">Загрузка из файлов в нескольких каталогах</span><span class="sxs-lookup"><span data-stu-id="67c0d-131">Load from files in multiple directories</span></span>

<span data-ttu-id="67c0d-132">Чтобы загрузить данные из нескольких каталогов, с помощью метода [`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*) создайте [`TextLoader`](xref:Microsoft.ML.Data.TextLoader).</span><span class="sxs-lookup"><span data-stu-id="67c0d-132">To load data from multiple directories, use the [`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*) method to create a [`TextLoader`](xref:Microsoft.ML.Data.TextLoader).</span></span> <span data-ttu-id="67c0d-133">Затем с помощью метода [`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*) укажите пути к отдельным файлам (подстановочные знаки использовать нельзя).</span><span class="sxs-lookup"><span data-stu-id="67c0d-133">Then, use the [`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*) method and specify the individual file paths (wildcards can't be used).</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

// Create TextLoader
TextLoader textLoader = mlContext.Data.CreateTextLoader<HousingData>(separatorChar: ',', hasHeader: true);

// Load Data
IDataView data = textLoader.Load("DataFolder/SubFolder1/1.txt", "DataFolder/SubFolder2/1.txt");
```

## <a name="load-data-from-a-streaming-source"></a><span data-ttu-id="67c0d-134">Загрузка из источника потоковой передачи данных</span><span class="sxs-lookup"><span data-stu-id="67c0d-134">Load data from a streaming source</span></span>

<span data-ttu-id="67c0d-135">Помимо загрузки данных, хранящихся на диске, ML.NET позволяет загружать данные из различных источников потоковой передачи, в число которых входят:</span><span class="sxs-lookup"><span data-stu-id="67c0d-135">In addition to loading data stored on disk, ML.NET supports loading data from various streaming sources that include but are not limited to:</span></span>

- <span data-ttu-id="67c0d-136">Коллекции оперативной памяти</span><span class="sxs-lookup"><span data-stu-id="67c0d-136">In-memory collections</span></span>
- <span data-ttu-id="67c0d-137">располагаться в коде JSON или XML;</span><span class="sxs-lookup"><span data-stu-id="67c0d-137">JSON/XML</span></span>
- <span data-ttu-id="67c0d-138">Базы данных</span><span class="sxs-lookup"><span data-stu-id="67c0d-138">Databases</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67c0d-139">Обратите внимание на то, что при работе с источниками потоковой передачи данных ML.NET ожидает получить данные в виде коллекции в памяти.</span><span class="sxs-lookup"><span data-stu-id="67c0d-139">Note that when working with streaming sources, ML.NET expects input to be in the form of an in-memory collection.</span></span> <span data-ttu-id="67c0d-140">Это значит, что при работе с такими источниками, как JSON/XML, данные должны быть переведены в формат коллекции в памяти.</span><span class="sxs-lookup"><span data-stu-id="67c0d-140">Therefore, when working with sources like JSON/XML, make sure to format the data into an in-memory collection.</span></span>

<span data-ttu-id="67c0d-141">Допустим, у нас есть следующая коллекция в памяти:</span><span class="sxs-lookup"><span data-stu-id="67c0d-141">Given the following in-memory collection:</span></span>

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

<span data-ttu-id="67c0d-142">Загрузите эту коллекцию в памяти в [`IDataView`](xref:Microsoft.ML.IDataView) с помощью метода [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*):</span><span class="sxs-lookup"><span data-stu-id="67c0d-142">Load the in-memory collection into an [`IDataView`](xref:Microsoft.ML.IDataView) with the [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) method:</span></span>

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromEnumerable<HousingData>(inMemoryCollection);
```
