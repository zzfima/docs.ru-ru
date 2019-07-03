---
title: Подготовка данных
description: Узнайте, как использовать преобразования в ML.NET для обработки и подготовки данных для дополнительной обработки или построения модели.
author: luisquintanilla
ms.author: luquinta
ms.date: 05/03/2019
ms.custom: mvc, how-to
ms.openlocfilehash: abf43260a438c9b1febffc77cf39e7328e0377ee
ms.sourcegitcommit: 4c41ec195caf03d98b7900007c3c8e24eba20d34
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/20/2019
ms.locfileid: "67268248"
---
# <a name="prepare-data"></a><span data-ttu-id="841a6-103">Подготовка данных</span><span class="sxs-lookup"><span data-stu-id="841a6-103">Prepare Data</span></span>

<span data-ttu-id="841a6-104">Сведения об использовании ML.NET для подготовки данных к дополнительной обработке или построению модели.</span><span class="sxs-lookup"><span data-stu-id="841a6-104">Learn how to use ML.NET to prepare data for additional processing or building a model.</span></span>

<span data-ttu-id="841a6-105">Данные часто являются грязными и разреженными.</span><span class="sxs-lookup"><span data-stu-id="841a6-105">Data is often unclean and sparse.</span></span> <span data-ttu-id="841a6-106">Кроме того, алгоритмы машинного обучения ML.NET ожидают входные данные или признаки в одном числовом векторе.</span><span class="sxs-lookup"><span data-stu-id="841a6-106">Additionally, ML.NET machine learning algorithms expect input or features to be in a single numerical vector.</span></span> <span data-ttu-id="841a6-107">Поэтому одна из целей подготовки данных — преобразовать данные в формат, ожидаемый алгоритмами ML.NET.</span><span class="sxs-lookup"><span data-stu-id="841a6-107">Therefore one of the goals of data preparation is to get the data into the format expected by ML.NET algorithms.</span></span> 

## <a name="filter-data"></a><span data-ttu-id="841a6-108">Фильтрация данных</span><span class="sxs-lookup"><span data-stu-id="841a6-108">Filter data</span></span>

<span data-ttu-id="841a6-109">В некоторых случаях не все данные в наборе данных важны для анализа.</span><span class="sxs-lookup"><span data-stu-id="841a6-109">Sometimes, not all data in a dataset is relevant for analysis.</span></span> <span data-ttu-id="841a6-110">Один из подходов для удаления ненужных данных — фильтрация.</span><span class="sxs-lookup"><span data-stu-id="841a6-110">An approach to remove irrelevant data is filtering.</span></span> <span data-ttu-id="841a6-111">[`DataOperationsCatalog`](xref:Microsoft.ML.DataOperationsCatalog) содержит набор операций фильтров, которые принимают [`IDataView`](xref:Microsoft.ML.IDataView), содержащий все данные, и возвращают [IDataView](xref:Microsoft.ML.IDataView), содержащий только релевантные точки данных.</span><span class="sxs-lookup"><span data-stu-id="841a6-111">The [`DataOperationsCatalog`](xref:Microsoft.ML.DataOperationsCatalog) contains a set of filter operations that take in an [`IDataView`](xref:Microsoft.ML.IDataView) containing all of the data and return an [IDataView](xref:Microsoft.ML.IDataView) containing only the data points of interest.</span></span> <span data-ttu-id="841a6-112">Важно отметить следующее: так как операции фильтрации не являются [`IEstimator`](xref:Microsoft.ML.IEstimator%601) или [`ITransformer`](xref:Microsoft.ML.ITransformer), как типы [`TransformsCatalog`](xref:Microsoft.ML.TransformsCatalog), они не могут рассматриваться как часть конвейера подготовки данных [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) или [`TransformerChain`](xref:Microsoft.ML.Data.TransformerChain%601).</span><span class="sxs-lookup"><span data-stu-id="841a6-112">It's important to note that because filter operations are not an [`IEstimator`](xref:Microsoft.ML.IEstimator%601) or [`ITransformer`](xref:Microsoft.ML.ITransformer) like those in the [`TransformsCatalog`](xref:Microsoft.ML.TransformsCatalog), they cannot be included as part of an [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) or [`TransformerChain`](xref:Microsoft.ML.Data.TransformerChain%601) data preparation pipeline.</span></span> 

<span data-ttu-id="841a6-113">Используйте следующие входные данные, которые загружаются в [`IDataView`](xref:Microsoft.ML.IDataView):</span><span class="sxs-lookup"><span data-stu-id="841a6-113">Using the following input data which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

```csharp
HomeData[] homeDataList = new HomeData[]
{
    new HomeData
    {
        NumberOfBedrooms=1f,
        Price=100000f
    },
    new HomeData
    {
        NumberOfBedrooms=2f,
        Price=300000f
    },
    new HomeData
    {
        NumberOfBedrooms=6f,
        Price=600000f
    }
};
```

<span data-ttu-id="841a6-114">Чтобы отфильтровать данные на основе значения столбца, используйте метод [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn*).</span><span class="sxs-lookup"><span data-stu-id="841a6-114">To filter data based on the value of a column, use the [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn*) method.</span></span>

```csharp
// Apply filter
IDataView filteredData = mlContext.Data.FilterRowsByColumn(data, "Price", lowerBound: 200000, upperBound: 1000000);
```

<span data-ttu-id="841a6-115">В приведенном выше примере задействуются строки в наборе данных с ценой между 200 000 и 1 000 000.</span><span class="sxs-lookup"><span data-stu-id="841a6-115">The sample above takes rows in the dataset with a price between 200000 and 1000000.</span></span> <span data-ttu-id="841a6-116">Результат применения этого фильтра будет возвращать только последние две строки в данных и исключать первую строку, так как цена в ней — 100 000, что не входит в пределы указанного диапазона.</span><span class="sxs-lookup"><span data-stu-id="841a6-116">The result of applying this filter would return only the last two rows in the data and exclude the first row because its price is 100000 and not between the specified range.</span></span>

## <a name="replace-missing-values"></a><span data-ttu-id="841a6-117">Замените отсутствующие значения</span><span class="sxs-lookup"><span data-stu-id="841a6-117">Replace missing values</span></span>

<span data-ttu-id="841a6-118">Отсутствующие значения — это обычное дело в наборах данных.</span><span class="sxs-lookup"><span data-stu-id="841a6-118">Missing values are a common occurrence in datasets.</span></span> <span data-ttu-id="841a6-119">Один из подходов к отсутствующим значениям состоит в том, чтобы заменить их значением по умолчанию для заданного типа или любым другим осмысленным значением, например средним значением в данных.</span><span class="sxs-lookup"><span data-stu-id="841a6-119">One approach to dealing with missing values is to replace them with the default value for the given type if any or another meaningful value such as the mean value in the data.</span></span> 

<span data-ttu-id="841a6-120">Используйте следующие входные данные, которые загружаются в [`IDataView`](xref:Microsoft.ML.IDataView):</span><span class="sxs-lookup"><span data-stu-id="841a6-120">Using the following input data which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

```csharp
HomeData[] homeDataList = new HomeData[]
{
    new HomeData
    {
        NumberOfBedrooms=1f,
        Price=100000f
    },
    new HomeData
    {
        NumberOfBedrooms=2f,
        Price=300000f
    },
    new HomeData
    {
        NumberOfBedrooms=6f,
        Price=float.NaN
    }
};
```

<span data-ttu-id="841a6-121">Обратите внимание, что в последнем элементе в нашем списке отсутствует значение для `Price`.</span><span class="sxs-lookup"><span data-stu-id="841a6-121">Notice that the last element in our list has a missing value for `Price`.</span></span> <span data-ttu-id="841a6-122">Чтобы заменить недостающие значения в столбце `Price`, используйте метод [`ReplaceMissingValues`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*) для заполнения этого отсутствующего значения.</span><span class="sxs-lookup"><span data-stu-id="841a6-122">To replace the missing values in the `Price` column, use the [`ReplaceMissingValues`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*) method to fill in that missing value.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="841a6-123">[`ReplaceMissingValue`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*) работает только с числовыми данными.</span><span class="sxs-lookup"><span data-stu-id="841a6-123">[`ReplaceMissingValue`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*) only works with numerical data.</span></span>

```csharp
// Define replacement estimator
var replacementEstimator = mlContext.Transforms.ReplaceMissingValues("Price", replacementMode: MissingValueReplacingEstimator.ReplacementMode.Mean);

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer replacementTransformer = replacementEstimator.Fit(data);

// Transform data
IDataView transformedData = replacementTransformer.Transform(data);
```

<span data-ttu-id="841a6-124">ML.NET поддерживает различные [режимы замены](xref:Microsoft.ML.Transforms.MissingValueReplacingEstimator.ReplacementMode).</span><span class="sxs-lookup"><span data-stu-id="841a6-124">ML.NET supports various [replacement modes](xref:Microsoft.ML.Transforms.MissingValueReplacingEstimator.ReplacementMode).</span></span> <span data-ttu-id="841a6-125">В примере выше используется режим замены `Mean`, который будет заполнять отсутствующее значение средним значением этого столбца.</span><span class="sxs-lookup"><span data-stu-id="841a6-125">The sample above uses the `Mean` replacement mode which will fill in the missing value with that column's average value.</span></span> <span data-ttu-id="841a6-126">Замена заполняет свойство `Price` для последнего элемента в наших данные значением 200 000, так как это среднее значение между 100 000 и 300 000.</span><span class="sxs-lookup"><span data-stu-id="841a6-126">The replacement 's result fills in the `Price` property for the last element in our data with 200,000 since it's the average of 100,000 and 300,000.</span></span> 

## <a name="use-normalizers"></a><span data-ttu-id="841a6-127">Используйте нормализаторы</span><span class="sxs-lookup"><span data-stu-id="841a6-127">Use normalizers</span></span>

<span data-ttu-id="841a6-128">[Нормализация](https://en.wikipedia.org/wiki/Feature_scaling) — это прием предварительной обработки данных, используемый для стандартизации признаков, которые не находятся на одной шкале, что помогает ускорить сходимость алгоритмов.</span><span class="sxs-lookup"><span data-stu-id="841a6-128">[Normalization](https://en.wikipedia.org/wiki/Feature_scaling) is a data pre-processing technique used to standardize features that are not on the same scale which helps algorithms converge faster.</span></span> <span data-ttu-id="841a6-129">Например диапазоны таких значений, как возраст и доход, могут существенно различаться: возраст, как правило, задается в диапазоне от 0 до 100, а доход, как правило, в диапазоне от нуля до нескольких тысяч.</span><span class="sxs-lookup"><span data-stu-id="841a6-129">For example, the ranges for values like age and income vary significantly with age generally being in the range of 0-100 and income generally being in the range of zero to thousands.</span></span> <span data-ttu-id="841a6-130">См. на [странице преобразований](../resources/transforms.md) более подробный список и описание преобразований нормализации.</span><span class="sxs-lookup"><span data-stu-id="841a6-130">Visit the [transforms page](../resources/transforms.md) for a more detailed list and description of normalization transforms.</span></span> 

### <a name="min-max-normalization"></a><span data-ttu-id="841a6-131">Минимакс</span><span class="sxs-lookup"><span data-stu-id="841a6-131">Min-Max normalization</span></span>

<span data-ttu-id="841a6-132">Используйте следующие входные данные, которые загружаются в [`IDataView`](xref:Microsoft.ML.IDataView):</span><span class="sxs-lookup"><span data-stu-id="841a6-132">Using the following input data which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

```csharp
HomeData[] homeDataList = new HomeData[]
{
    new HomeData
    {
        NumberOfBedrooms = 2f,
        Price = 200000f
    },
    new HomeData
    {
        NumberOfBedrooms = 1f,
        Price = 100000f
    }
};
```

<span data-ttu-id="841a6-133">Нормализация может применяться к столбцам с одинарными числовыми значениями, а также к векторам.</span><span class="sxs-lookup"><span data-stu-id="841a6-133">Normalization can be applied to columns with single numerical values as well as vectors.</span></span> <span data-ttu-id="841a6-134">Нормализуйте данные в столбце `Price` методом минимакса, используя метод [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax*).</span><span class="sxs-lookup"><span data-stu-id="841a6-134">Normalize the data in the `Price` column using min-max normalization with the [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax*) method.</span></span>

```csharp
// Define min-max estimator
var minMaxEstimator = mlContext.Transforms.NormalizeMinMax("Price");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer minMaxTransformer = minMaxEstimator.Fit(data);

// Transform data
IDataView transformedData = minMaxTransformer.Transform(data);
```

<span data-ttu-id="841a6-135">Исходные значения цены `[200000,100000]` преобразуются в `[ 1, 0.5 ]` с помощью формулы нормализации `MinMax`, которая создает выходные значения в диапазоне от 0 до 1.</span><span class="sxs-lookup"><span data-stu-id="841a6-135">The original price values `[200000,100000]` are converted to `[ 1, 0.5 ]` using the `MinMax` normalization formula which generates output values in the range of 0-1.</span></span>

### <a name="binning"></a><span data-ttu-id="841a6-136">Группирование</span><span class="sxs-lookup"><span data-stu-id="841a6-136">Binning</span></span>

<span data-ttu-id="841a6-137">[Группирование](https://en.wikipedia.org/wiki/Data_binning) преобразует непрерывные значения в дискретное представление входных данных.</span><span class="sxs-lookup"><span data-stu-id="841a6-137">[Binning](https://en.wikipedia.org/wiki/Data_binning) converts continuous values into a discrete representation of the input.</span></span> <span data-ttu-id="841a6-138">Например предположим, что один из признаков — возраст.</span><span class="sxs-lookup"><span data-stu-id="841a6-138">For example, suppose one of your features is age.</span></span> <span data-ttu-id="841a6-139">Вместо использования фактического возраста создаются диапазоны для этого значения путем группирования данных.</span><span class="sxs-lookup"><span data-stu-id="841a6-139">Instead of using the actual age value,  binning creates ranges for that value.</span></span> <span data-ttu-id="841a6-140">Диапазон 0–18 может быть первой ячейкой, другой может быть 19–35 и т.д.</span><span class="sxs-lookup"><span data-stu-id="841a6-140">0-18 could be one bin, another could be 19-35 and so on.</span></span> 

<span data-ttu-id="841a6-141">Используйте следующие входные данные, которые загружаются в [`IDataView`](xref:Microsoft.ML.IDataView):</span><span class="sxs-lookup"><span data-stu-id="841a6-141">Using the following input data which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

```csharp
HomeData[] homeDataList = new HomeData[]
{
    new HomeData
    {
        NumberOfBedrooms=1f,
        Price=100000f
    },
    new HomeData
    {
        NumberOfBedrooms=2f,
        Price=300000f
    },
    new HomeData
    {
        NumberOfBedrooms=6f,
        Price=600000f
    }
};
```

<span data-ttu-id="841a6-142">Нормализуйте данные в интервалах группирования с помощью метода [`NormalizeBinning`](xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning*).</span><span class="sxs-lookup"><span data-stu-id="841a6-142">Normalize the data into bins using the [`NormalizeBinning`](xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning*) method.</span></span> <span data-ttu-id="841a6-143">Параметр `maximumBinCount` позволяет указать количество ячеек, нужное для классификации данных.</span><span class="sxs-lookup"><span data-stu-id="841a6-143">The `maximumBinCount` parameter enables you to specify the number of bins needed to classify your data.</span></span> <span data-ttu-id="841a6-144">В этом примере данные будут помещены в две ячейки.</span><span class="sxs-lookup"><span data-stu-id="841a6-144">In this example, data will be put into two bins.</span></span>  

```csharp
// Define binning estimator
var binningEstimator = mlContext.Transforms.NormalizeBinning("Price", maximumBinCount: 2);

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
var binningTransformer = binningEstimator.Fit(data);

// Transform Data
IDataView transformedData = binningTransformer.Transform(data);
```

<span data-ttu-id="841a6-145">В результате разделения на корзины создаются границы ячейки `[0,200000,Infinity]`.</span><span class="sxs-lookup"><span data-stu-id="841a6-145">The result of binning creates bin bounds of `[0,200000,Infinity]`.</span></span> <span data-ttu-id="841a6-146">Поэтому полученные корзины — это `[0,1,1]`, так как первое наблюдение находится в диапазоне от 0 до 200 000, а другое больше 200 000, но меньше бесконечности.</span><span class="sxs-lookup"><span data-stu-id="841a6-146">Therefore the resulting bins are `[0,1,1]` because the first observation is between 0-200000 and the others are greater than 200000 but less than infinity.</span></span>

## <a name="work-with-categorical-data"></a><span data-ttu-id="841a6-147">Работа с категориальными данными</span><span class="sxs-lookup"><span data-stu-id="841a6-147">Work with categorical data</span></span>

<span data-ttu-id="841a6-148">Нечисловые категориальные данные необходимо преобразовать в числа перед их использованием для создания модели машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="841a6-148">Non-numeric categorical data needs to be converted to a number before being used to build a machine learning model.</span></span> 

<span data-ttu-id="841a6-149">Используйте следующие входные данные, которые загружаются в [`IDataView`](xref:Microsoft.ML.IDataView):</span><span class="sxs-lookup"><span data-stu-id="841a6-149">Using the following input data which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

```csharp
CarData[] cars = new CarData[] 
{
    new CarData
    {
        Color="Red",
        VehicleType="SUV"
    },
    new CarData
    {
        Color="Blue",
        VehicleType="Sedan"
    },
    new CarData
    {
        Color="Black",
        VehicleType="SUV"
    }
};
```

<span data-ttu-id="841a6-150">Категориальное свойство `VehicleType` может быть преобразовано в число с помощью метода [`OneHotEncoding`](xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding*).</span><span class="sxs-lookup"><span data-stu-id="841a6-150">The categorical `VehicleType` property can be converted into a number using the [`OneHotEncoding`](xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding*) method.</span></span> 

```csharp
// Define categorical transform estimator
var categoricalEstimator = mlContext.Transforms.Categorical.OneHotEncoding("VehicleType");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer categoricalTransformer = categoricalEstimator.Fit(data);

// Transform Data
IDataView transformedData = categoricalTransformer.Transform(data);
```

<span data-ttu-id="841a6-151">Результирующее преобразование преобразует текстовое значение `VehicleType` в число.</span><span class="sxs-lookup"><span data-stu-id="841a6-151">The resulting transform converts the text value of `VehicleType` to a number.</span></span> <span data-ttu-id="841a6-152">Записи в столбце `VehicleType` становятся следующими при применении преобразования:</span><span class="sxs-lookup"><span data-stu-id="841a6-152">The entries in the `VehicleType` column become the following when the transform is applied:</span></span> 

```text
[
    1, // SUV
    2, // Sedan
    1 // SUV
]
```

## <a name="work-with-text-data"></a><span data-ttu-id="841a6-153">Работа с текстовыми данными</span><span class="sxs-lookup"><span data-stu-id="841a6-153">Work with text data</span></span>

<span data-ttu-id="841a6-154">Текстовые данные необходимо преобразовывать в числа, прежде чем использовать их для формирования модели машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="841a6-154">Text data needs to be transformed into numbers before using it to build a machine learning model.</span></span> <span data-ttu-id="841a6-155">См. на [странице преобразований](../resources/transforms.md) более подробный список и описание преобразований текста.</span><span class="sxs-lookup"><span data-stu-id="841a6-155">Visit the [transforms page](../resources/transforms.md) for a more detailed list and description of text transforms.</span></span>

<span data-ttu-id="841a6-156">Используем такие данные, как загруженные ниже в [`IDataView`](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="841a6-156">Using data like the data below that has been loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

```csharp
ReviewData[] reviews = new ReviewData[]
{
    new ReviewData
    {
        Description="This is a good product",
        Rating=4.7f
    },
    new ReviewData
    {
        Description="This is a bad product",
        Rating=2.3f
    }
};
```

<span data-ttu-id="841a6-157">Минимальный шаг, позволяющий преобразовать текст в представление в виде числового вектора, заключается в использовании метода [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*).</span><span class="sxs-lookup"><span data-stu-id="841a6-157">The minimum step to convert text to a numerical vector representation is to use the [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*) method.</span></span> <span data-ttu-id="841a6-158">С помощью преобразования [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*) к столбцу входного текста применяется серия преобразований, которая приводит его к числовому вектору, представляющему lp-нормализованные слова и символьные n-граммы.</span><span class="sxs-lookup"><span data-stu-id="841a6-158">By using the [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*) transform, a series of transformations is applied to the input text column resulting in a numerical vector representing the lp-normalized word and character ngrams.</span></span> 

```csharp
// Define text transform estimator
var textEstimator  = mlContext.Transforms.Text.FeaturizeText("Description");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer textTransformer = textEstimator.Fit(data);

// Transform data
IDataView transformedData = textTransformer.Transform(data);
```

<span data-ttu-id="841a6-159">Результирующее преобразование превратит текстовые значения в столбце `Description` в числовой вектор, который будет выглядеть, как в выходных данных ниже.</span><span class="sxs-lookup"><span data-stu-id="841a6-159">The resulting transform would convert the text values in the `Description` column to a numerical vector that looks similar to the output below:</span></span>

```text
[ 0.2041241, 0.2041241, 0.2041241, 0.4082483, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0, 0, 0, 0, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0 ]
```

<span data-ttu-id="841a6-160">Сочетайте сложную обработку текста в [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) для удаления шума и уменьшения объема необходимых вычислительных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="841a6-160">Combine complex text processing steps into an [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) to remove noise and potentially reduce the amount of required processing resources as needed.</span></span>

```csharp
// Define text transform estimator
var textEstimator = mlContext.Transforms.Text.NormalizeText("Description")
    .Append(mlContext.Transforms.Text.TokenizeIntoWords("Description"))
    .Append(mlContext.Transforms.Text.RemoveDefaultStopWords("Description"))
    .Append(mlContext.Transforms.Conversion.MapValueToKey("Description"))
    .Append(mlContext.Transforms.Text.ProduceNgrams("Description"))
    .Append(mlContext.Transforms.NormalizeLpNorm("Description"));
```

<span data-ttu-id="841a6-161">`textEstimator` содержит подмножество операций, выполняемых методом [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*).</span><span class="sxs-lookup"><span data-stu-id="841a6-161">`textEstimator` contains a subset of operations performed by the [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*) method.</span></span> <span data-ttu-id="841a6-162">Преимущество более сложного конвейера — контроль и мониторинг преобразований, примененных к данным.</span><span class="sxs-lookup"><span data-stu-id="841a6-162">The benefit of a more complex pipeline is control and visibility over the transformations applied to the data.</span></span> 

<span data-ttu-id="841a6-163">На основании первой записи в качестве примера ниже приведено подробное описание результатов преобразования, определенного в `textEstimator`.</span><span class="sxs-lookup"><span data-stu-id="841a6-163">Using the first entry as an example, the following is a detailed description of the results produced by the transformation steps defined by `textEstimator`:</span></span>

<span data-ttu-id="841a6-164">**Исходный текст: This is a good product**</span><span class="sxs-lookup"><span data-stu-id="841a6-164">**Original Text: This is a good product**</span></span>

|<span data-ttu-id="841a6-165">Transform</span><span class="sxs-lookup"><span data-stu-id="841a6-165">Transform</span></span> | <span data-ttu-id="841a6-166">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="841a6-166">Description</span></span> | <span data-ttu-id="841a6-167">Результат</span><span class="sxs-lookup"><span data-stu-id="841a6-167">Result</span></span>
|--|--|--|
|<span data-ttu-id="841a6-168">1. NormalizeText</span><span class="sxs-lookup"><span data-stu-id="841a6-168">1. NormalizeText</span></span> | <span data-ttu-id="841a6-169">Преобразует все буквы в строчные по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="841a6-169">Converts all letters to lowercase by default</span></span> | <span data-ttu-id="841a6-170">this is a good product</span><span class="sxs-lookup"><span data-stu-id="841a6-170">this is a good product</span></span>
|<span data-ttu-id="841a6-171">2. TokenizeWords</span><span class="sxs-lookup"><span data-stu-id="841a6-171">2. TokenizeWords</span></span> | <span data-ttu-id="841a6-172">Разделяет строку на отдельные слова.</span><span class="sxs-lookup"><span data-stu-id="841a6-172">Splits string into individual words</span></span> | <span data-ttu-id="841a6-173">["this","is","a","good","product"]</span><span class="sxs-lookup"><span data-stu-id="841a6-173">["this","is","a","good","product"]</span></span>
|<span data-ttu-id="841a6-174">3. RemoveDefaultStopWords</span><span class="sxs-lookup"><span data-stu-id="841a6-174">3. RemoveDefaultStopWords</span></span> | <span data-ttu-id="841a6-175">Удаляет стоп-слова, такие как *is* и *a*.</span><span class="sxs-lookup"><span data-stu-id="841a6-175">Removes stopwords like *is* and *a*.</span></span> | <span data-ttu-id="841a6-176">["good","product"]</span><span class="sxs-lookup"><span data-stu-id="841a6-176">["good","product"]</span></span>
|<span data-ttu-id="841a6-177">4. MapValueToKey</span><span class="sxs-lookup"><span data-stu-id="841a6-177">4. MapValueToKey</span></span> | <span data-ttu-id="841a6-178">Сопоставляет значения ключей (категории) на основе входных данных.</span><span class="sxs-lookup"><span data-stu-id="841a6-178">Maps the values to keys (categories) based on the input data</span></span> |  <span data-ttu-id="841a6-179">[1,2]</span><span class="sxs-lookup"><span data-stu-id="841a6-179">[1,2]</span></span>
|<span data-ttu-id="841a6-180">5. ProduceNGrams</span><span class="sxs-lookup"><span data-stu-id="841a6-180">5. ProduceNGrams</span></span> | <span data-ttu-id="841a6-181">Преобразует текст в последовательность слов.</span><span class="sxs-lookup"><span data-stu-id="841a6-181">Transforms text into sequence of consecutive words</span></span> | <span data-ttu-id="841a6-182">[1,1,1,0,0]</span><span class="sxs-lookup"><span data-stu-id="841a6-182">[1,1,1,0,0]</span></span>
|<span data-ttu-id="841a6-183">6.  NormalizeLpNorm</span><span class="sxs-lookup"><span data-stu-id="841a6-183">6. NormalizeLpNorm</span></span> | <span data-ttu-id="841a6-184">Масштабирует входы по их lp-норме.</span><span class="sxs-lookup"><span data-stu-id="841a6-184">Scale inputs by their lp-norm</span></span> | <span data-ttu-id="841a6-185">[ 0.577350529, 0.577350529, 0.577350529, 0, 0 ]</span><span class="sxs-lookup"><span data-stu-id="841a6-185">[ 0.577350529, 0.577350529, 0.577350529, 0, 0 ]</span></span>
