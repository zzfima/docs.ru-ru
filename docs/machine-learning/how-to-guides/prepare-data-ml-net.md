---
title: Подготовка данных для построения модели
description: Узнайте, как использовать преобразования в ML.NET для обработки и подготовки данных для дополнительной обработки или построения модели.
author: luisquintanilla
ms.author: luquinta
ms.date: 01/29/2020
ms.custom: mvc, how-to, title-hack-0625
ms.openlocfilehash: 12f933253af9ea519d711c20227fe075fed003de
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452991"
---
# <a name="prepare-data-for-building-a-model"></a><span data-ttu-id="71786-103">Подготовка данных для построения модели</span><span class="sxs-lookup"><span data-stu-id="71786-103">Prepare data for building a model</span></span>

<span data-ttu-id="71786-104">Сведения об использовании ML.NET для подготовки данных к дополнительной обработке или построению модели.</span><span class="sxs-lookup"><span data-stu-id="71786-104">Learn how to use ML.NET to prepare data for additional processing or building a model.</span></span>

<span data-ttu-id="71786-105">Данные часто являются грязными и разреженными.</span><span class="sxs-lookup"><span data-stu-id="71786-105">Data is often unclean and sparse.</span></span> <span data-ttu-id="71786-106">Алгоритмы машинного обучения ML.NET ожидают входные данные или признаки в одном числовом векторе.</span><span class="sxs-lookup"><span data-stu-id="71786-106">ML.NET machine learning algorithms expect input or features to be in a single numerical vector.</span></span> <span data-ttu-id="71786-107">Аналогичным образом, значение для прогнозирования (метка), особенно если это категориальные данные, должно быть закодировано.</span><span class="sxs-lookup"><span data-stu-id="71786-107">Similarly, the value to predict (label), especially when it's categorical data, has to be encoded.</span></span> <span data-ttu-id="71786-108">Поэтому одна из целей подготовки данных — преобразовать данные в формат, ожидаемый алгоритмами ML.NET.</span><span class="sxs-lookup"><span data-stu-id="71786-108">Therefore one of the goals of data preparation is to get the data into the format expected by ML.NET algorithms.</span></span>

## <a name="filter-data"></a><span data-ttu-id="71786-109">Фильтрация данных</span><span class="sxs-lookup"><span data-stu-id="71786-109">Filter data</span></span>

<span data-ttu-id="71786-110">В некоторых случаях не все данные в наборе данных важны для анализа.</span><span class="sxs-lookup"><span data-stu-id="71786-110">Sometimes, not all data in a dataset is relevant for analysis.</span></span> <span data-ttu-id="71786-111">Один из подходов для удаления ненужных данных — фильтрация.</span><span class="sxs-lookup"><span data-stu-id="71786-111">An approach to remove irrelevant data is filtering.</span></span> <span data-ttu-id="71786-112">[`DataOperationsCatalog`](xref:Microsoft.ML.DataOperationsCatalog) содержит набор операций фильтров, которые принимают [`IDataView`](xref:Microsoft.ML.IDataView), содержащий все данные, и возвращают [IDataView](xref:Microsoft.ML.IDataView), содержащий только релевантные точки данных.</span><span class="sxs-lookup"><span data-stu-id="71786-112">The [`DataOperationsCatalog`](xref:Microsoft.ML.DataOperationsCatalog) contains a set of filter operations that take in an [`IDataView`](xref:Microsoft.ML.IDataView) containing all of the data and return an [IDataView](xref:Microsoft.ML.IDataView) containing only the data points of interest.</span></span> <span data-ttu-id="71786-113">Важно отметить следующее: так как операции фильтрации не являются [`IEstimator`](xref:Microsoft.ML.IEstimator%601) или [`ITransformer`](xref:Microsoft.ML.ITransformer), как типы [`TransformsCatalog`](xref:Microsoft.ML.TransformsCatalog), они не могут рассматриваться как часть конвейера подготовки данных [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) или [`TransformerChain`](xref:Microsoft.ML.Data.TransformerChain%601).</span><span class="sxs-lookup"><span data-stu-id="71786-113">It's important to note that because filter operations are not an [`IEstimator`](xref:Microsoft.ML.IEstimator%601) or [`ITransformer`](xref:Microsoft.ML.ITransformer) like those in the [`TransformsCatalog`](xref:Microsoft.ML.TransformsCatalog), they cannot be included as part of an [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) or [`TransformerChain`](xref:Microsoft.ML.Data.TransformerChain%601) data preparation pipeline.</span></span>

<span data-ttu-id="71786-114">Загрузите следующие входные данные в [`IDataView`](xref:Microsoft.ML.IDataView) с именем `data`:</span><span class="sxs-lookup"><span data-stu-id="71786-114">Take the following input data and load it into an [`IDataView`](xref:Microsoft.ML.IDataView) called `data`:</span></span>

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

<span data-ttu-id="71786-115">Чтобы отфильтровать данные на основе значения столбца, используйте метод [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn%2A).</span><span class="sxs-lookup"><span data-stu-id="71786-115">To filter data based on the value of a column, use the [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn%2A) method.</span></span>

```csharp
// Apply filter
IDataView filteredData = mlContext.Data.FilterRowsByColumn(data, "Price", lowerBound: 200000, upperBound: 1000000);
```

<span data-ttu-id="71786-116">В приведенном выше примере задействуются строки в наборе данных с ценой между 200 000 и 1 000 000.</span><span class="sxs-lookup"><span data-stu-id="71786-116">The sample above takes rows in the dataset with a price between 200000 and 1000000.</span></span> <span data-ttu-id="71786-117">Результат применения этого фильтра будет возвращать только последние две строки в данных и исключать первую строку, так как цена в ней — 100 000, что не входит в пределы указанного диапазона.</span><span class="sxs-lookup"><span data-stu-id="71786-117">The result of applying this filter would return only the last two rows in the data and exclude the first row because its price is 100000 and not between the specified range.</span></span>

## <a name="replace-missing-values"></a><span data-ttu-id="71786-118">Замените отсутствующие значения</span><span class="sxs-lookup"><span data-stu-id="71786-118">Replace missing values</span></span>

<span data-ttu-id="71786-119">Отсутствующие значения — это обычное дело в наборах данных.</span><span class="sxs-lookup"><span data-stu-id="71786-119">Missing values are a common occurrence in datasets.</span></span> <span data-ttu-id="71786-120">Один из подходов к отсутствующим значениям состоит в том, чтобы заменить их значением по умолчанию для заданного типа или любым другим осмысленным значением, например средним значением в данных.</span><span class="sxs-lookup"><span data-stu-id="71786-120">One approach to dealing with missing values is to replace them with the default value for the given type if any or another meaningful value such as the mean value in the data.</span></span>

<span data-ttu-id="71786-121">Загрузите следующие входные данные в [`IDataView`](xref:Microsoft.ML.IDataView) с именем `data`:</span><span class="sxs-lookup"><span data-stu-id="71786-121">Take the following input data and load it into an [`IDataView`](xref:Microsoft.ML.IDataView) called `data`:</span></span>

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

<span data-ttu-id="71786-122">Обратите внимание, что в последнем элементе в нашем списке отсутствует значение для `Price`.</span><span class="sxs-lookup"><span data-stu-id="71786-122">Notice that the last element in our list has a missing value for `Price`.</span></span> <span data-ttu-id="71786-123">Чтобы заменить недостающие значения в столбце `Price`, используйте метод [`ReplaceMissingValues`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues%2A) для заполнения этого отсутствующего значения.</span><span class="sxs-lookup"><span data-stu-id="71786-123">To replace the missing values in the `Price` column, use the [`ReplaceMissingValues`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues%2A) method to fill in that missing value.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71786-124">[`ReplaceMissingValue`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues%2A) работает только с числовыми данными.</span><span class="sxs-lookup"><span data-stu-id="71786-124">[`ReplaceMissingValue`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues%2A) only works with numerical data.</span></span>

```csharp
// Define replacement estimator
var replacementEstimator = mlContext.Transforms.ReplaceMissingValues("Price", replacementMode: MissingValueReplacingEstimator.ReplacementMode.Mean);

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer replacementTransformer = replacementEstimator.Fit(data);

// Transform data
IDataView transformedData = replacementTransformer.Transform(data);
```

<span data-ttu-id="71786-125">ML.NET поддерживает различные [режимы замены](xref:Microsoft.ML.Transforms.MissingValueReplacingEstimator.ReplacementMode).</span><span class="sxs-lookup"><span data-stu-id="71786-125">ML.NET supports various [replacement modes](xref:Microsoft.ML.Transforms.MissingValueReplacingEstimator.ReplacementMode).</span></span> <span data-ttu-id="71786-126">В примере выше используется режим замены `Mean`, который заполняет отсутствующее значение средним значением этого столбца.</span><span class="sxs-lookup"><span data-stu-id="71786-126">The sample above uses the `Mean` replacement mode, which fills in the missing value with that column's average value.</span></span> <span data-ttu-id="71786-127">Замена заполняет свойство `Price` для последнего элемента в наших данные значением 200 000, так как это среднее значение между 100 000 и 300 000.</span><span class="sxs-lookup"><span data-stu-id="71786-127">The replacement 's result fills in the `Price` property for the last element in our data with 200,000 since it's the average of 100,000 and 300,000.</span></span>

## <a name="use-normalizers"></a><span data-ttu-id="71786-128">Используйте нормализаторы</span><span class="sxs-lookup"><span data-stu-id="71786-128">Use normalizers</span></span>

<span data-ttu-id="71786-129">[Нормализация](https://en.wikipedia.org/wiki/Feature_scaling) — это метод предварительной обработки данных, используемый для масштабирования функций в одном диапазоне (обычно от 0 до 1), чтобы их можно было более точно обрабатывать с помощью алгоритма машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="71786-129">[Normalization](https://en.wikipedia.org/wiki/Feature_scaling) is a data pre-processing technique used to scale features to be in the same range, usually between 0 and 1, so that they can be more accurately processed by a machine learning algorithm.</span></span> <span data-ttu-id="71786-130">Например, диапазоны возраста и дохода, могут существенно различаться: возраст, как правило, задается в диапазоне от 0 до 100, а доход, как правило, в диапазоне от нуля до нескольких тысяч.</span><span class="sxs-lookup"><span data-stu-id="71786-130">For example, the ranges for age and income vary significantly with age generally being in the range of 0-100 and income generally being in the range of zero to thousands.</span></span> <span data-ttu-id="71786-131">См. на [странице преобразований](../resources/transforms.md) более подробный список и описание преобразований нормализации.</span><span class="sxs-lookup"><span data-stu-id="71786-131">Visit the [transforms page](../resources/transforms.md) for a more detailed list and description of normalization transforms.</span></span>

### <a name="min-max-normalization"></a><span data-ttu-id="71786-132">Минимакс</span><span class="sxs-lookup"><span data-stu-id="71786-132">Min-Max normalization</span></span>

<span data-ttu-id="71786-133">Загрузите следующие входные данные в [`IDataView`](xref:Microsoft.ML.IDataView) с именем `data`:</span><span class="sxs-lookup"><span data-stu-id="71786-133">Take the following input data and load it into an [`IDataView`](xref:Microsoft.ML.IDataView) called `data`:</span></span>

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

<span data-ttu-id="71786-134">Нормализация может применяться к столбцам с одинарными числовыми значениями, а также к векторам.</span><span class="sxs-lookup"><span data-stu-id="71786-134">Normalization can be applied to columns with single numerical values as well as vectors.</span></span> <span data-ttu-id="71786-135">Нормализуйте данные в столбце `Price` методом минимакса, используя метод [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax%2A).</span><span class="sxs-lookup"><span data-stu-id="71786-135">Normalize the data in the `Price` column using min-max normalization with the [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax%2A) method.</span></span>

```csharp
// Define min-max estimator
var minMaxEstimator = mlContext.Transforms.NormalizeMinMax("Price");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer minMaxTransformer = minMaxEstimator.Fit(data);

// Transform data
IDataView transformedData = minMaxTransformer.Transform(data);
```

<span data-ttu-id="71786-136">Исходные значения цены `[200000,100000]` преобразуются в `[ 1, 0.5 ]` с помощью формулы нормализации `MinMax`, которая создает выходные значения в диапазоне от 0 до 1.</span><span class="sxs-lookup"><span data-stu-id="71786-136">The original price values `[200000,100000]` are converted to `[ 1, 0.5 ]` using the `MinMax` normalization formula that generates output values in the range of 0-1.</span></span>

### <a name="binning"></a><span data-ttu-id="71786-137">Группирование</span><span class="sxs-lookup"><span data-stu-id="71786-137">Binning</span></span>

<span data-ttu-id="71786-138">[Группирование](https://en.wikipedia.org/wiki/Data_binning) преобразует непрерывные значения в дискретное представление входных данных.</span><span class="sxs-lookup"><span data-stu-id="71786-138">[Binning](https://en.wikipedia.org/wiki/Data_binning) converts continuous values into a discrete representation of the input.</span></span> <span data-ttu-id="71786-139">Например предположим, что один из признаков — возраст.</span><span class="sxs-lookup"><span data-stu-id="71786-139">For example, suppose one of your features is age.</span></span> <span data-ttu-id="71786-140">Вместо использования фактического возраста создаются диапазоны для этого значения путем группирования данных.</span><span class="sxs-lookup"><span data-stu-id="71786-140">Instead of using the actual age value,  binning creates ranges for that value.</span></span> <span data-ttu-id="71786-141">Диапазон 0–18 может быть первой ячейкой, другой может быть 19–35 и т.д.</span><span class="sxs-lookup"><span data-stu-id="71786-141">0-18 could be one bin, another could be 19-35 and so on.</span></span>

<span data-ttu-id="71786-142">Загрузите следующие входные данные в [`IDataView`](xref:Microsoft.ML.IDataView) с именем `data`:</span><span class="sxs-lookup"><span data-stu-id="71786-142">Take the following input data and load it into an [`IDataView`](xref:Microsoft.ML.IDataView) called `data`:</span></span>

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

<span data-ttu-id="71786-143">Нормализуйте данные в интервалах группирования с помощью метода [`NormalizeBinning`](xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning%2A).</span><span class="sxs-lookup"><span data-stu-id="71786-143">Normalize the data into bins using the [`NormalizeBinning`](xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning%2A) method.</span></span> <span data-ttu-id="71786-144">Параметр `maximumBinCount` позволяет указать количество ячеек, нужное для классификации данных.</span><span class="sxs-lookup"><span data-stu-id="71786-144">The `maximumBinCount` parameter enables you to specify the number of bins needed to classify your data.</span></span> <span data-ttu-id="71786-145">В этом примере данные будут помещены в две ячейки.</span><span class="sxs-lookup"><span data-stu-id="71786-145">In this example, data will be put into two bins.</span></span>

```csharp
// Define binning estimator
var binningEstimator = mlContext.Transforms.NormalizeBinning("Price", maximumBinCount: 2);

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
var binningTransformer = binningEstimator.Fit(data);

// Transform Data
IDataView transformedData = binningTransformer.Transform(data);
```

<span data-ttu-id="71786-146">В результате разделения на корзины создаются границы ячейки `[0,200000,Infinity]`.</span><span class="sxs-lookup"><span data-stu-id="71786-146">The result of binning creates bin bounds of `[0,200000,Infinity]`.</span></span> <span data-ttu-id="71786-147">Поэтому полученные корзины — это `[0,1,1]`, так как первое наблюдение находится в диапазоне от 0 до 200 000, а другое больше 200 000, но меньше бесконечности.</span><span class="sxs-lookup"><span data-stu-id="71786-147">Therefore the resulting bins are `[0,1,1]` because the first observation is between 0-200000 and the others are greater than 200000 but less than infinity.</span></span>

## <a name="work-with-categorical-data"></a><span data-ttu-id="71786-148">Работа с категориальными данными</span><span class="sxs-lookup"><span data-stu-id="71786-148">Work with categorical data</span></span>

<span data-ttu-id="71786-149">Один из наиболее распространенных типов данных — это категорийные данные.</span><span class="sxs-lookup"><span data-stu-id="71786-149">One of the most common types of data is categorical data.</span></span> <span data-ttu-id="71786-150">У категорийных данных есть конечное количество категорий.</span><span class="sxs-lookup"><span data-stu-id="71786-150">Categorical data has a finite number of categories.</span></span> <span data-ttu-id="71786-151">Например, штаты США, или список видов животных, найденных в наборе изображений.</span><span class="sxs-lookup"><span data-stu-id="71786-151">For example, the states of the USA, or a list of the types of animals found in a set of pictures.</span></span> <span data-ttu-id="71786-152">Независимо от того, являются ли категорийные данные функциями или метками, их следует сопоставить с числовым значением, чтобы использовать для создания модели машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="71786-152">Whether the categorical data are features or labels, they must be mapped onto a numerical value so they can be used to generate a machine learning model.</span></span> <span data-ttu-id="71786-153">Существует несколько способов работы с категорийными данными в ML.NET, которые зависят от решаемой задачи.</span><span class="sxs-lookup"><span data-stu-id="71786-153">There are a number of ways of working with categorical data in ML.NET, depending on the problem you are solving.</span></span>

### <a name="key-value-mapping"></a><span data-ttu-id="71786-154">Сопоставление значений ключа</span><span class="sxs-lookup"><span data-stu-id="71786-154">Key value mapping</span></span>

<span data-ttu-id="71786-155">Ключ в ML.NET — это целочисленное значение, представляющее категорию.</span><span class="sxs-lookup"><span data-stu-id="71786-155">In ML.NET, a key is an integer value that represents a category.</span></span> <span data-ttu-id="71786-156">Сопоставление значений ключа чаще всего используется для преобразования строковых меток с уникальными целочисленными значениями для обучения, а затем их возвращения в строковые значения, если модель используется для создания прогноза.</span><span class="sxs-lookup"><span data-stu-id="71786-156">Key value mapping is most often used to map string labels into unique integer values for training, then back to their string values when the model is used to make a prediction.</span></span>

<span data-ttu-id="71786-157">Преобразования, используемые для сопоставления значений ключей — это [MapValueToKey](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) и [MapKeyToValue](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapKeyToValue%2A).</span><span class="sxs-lookup"><span data-stu-id="71786-157">The transforms used to perform key value mapping are [MapValueToKey](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) and [MapKeyToValue](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapKeyToValue%2A).</span></span>

<span data-ttu-id="71786-158">`MapValueToKey` добавляет словарь сопоставлений в модель, чтобы `MapKeyToValue` мог выполнить обратное преобразование при выполнении прогноза.</span><span class="sxs-lookup"><span data-stu-id="71786-158">`MapValueToKey` adds a dictionary of mappings in the model, so that `MapKeyToValue` can perform the reverse transform when making a prediction.</span></span>

### <a name="one-hot-encoding"></a><span data-ttu-id="71786-159">Прямое унитарное кодирование</span><span class="sxs-lookup"><span data-stu-id="71786-159">One hot encoding</span></span>

<span data-ttu-id="71786-160">Прямое унитарное кодирование принимает конечный набор значений и сопоставляет их с целыми числами, двоичное представление которых содержит одно значение `1` в уникальных позициях в строке.</span><span class="sxs-lookup"><span data-stu-id="71786-160">One hot encoding takes a finite set of values and maps them onto integers whose binary representation has a single `1` value in unique positions in the string.</span></span> <span data-ttu-id="71786-161">Прямое унитарное кодирование может быть лучшим выбором, если нет неявного упорядочения категорийных данных.</span><span class="sxs-lookup"><span data-stu-id="71786-161">One hot encoding can be the best choice if there is no implicit ordering of the categorical data.</span></span> <span data-ttu-id="71786-162">В следующей таблице приведен пример с почтовыми индексами в виде необработанных значений.</span><span class="sxs-lookup"><span data-stu-id="71786-162">The following table shows an example with zip codes as raw values.</span></span>

|<span data-ttu-id="71786-163">Необработанное значение</span><span class="sxs-lookup"><span data-stu-id="71786-163">Raw value</span></span>|<span data-ttu-id="71786-164">Закодированное значение с одним активным состоянием</span><span class="sxs-lookup"><span data-stu-id="71786-164">One hot encoded value</span></span>|
|---------|---------------------|
|<span data-ttu-id="71786-165">98052</span><span class="sxs-lookup"><span data-stu-id="71786-165">98052</span></span>|<span data-ttu-id="71786-166">00...01</span><span class="sxs-lookup"><span data-stu-id="71786-166">00...01</span></span>|
|<span data-ttu-id="71786-167">98100</span><span class="sxs-lookup"><span data-stu-id="71786-167">98100</span></span>|<span data-ttu-id="71786-168">00...10</span><span class="sxs-lookup"><span data-stu-id="71786-168">00...10</span></span>|
|<span data-ttu-id="71786-169">...</span><span class="sxs-lookup"><span data-stu-id="71786-169">...</span></span>|<span data-ttu-id="71786-170">...</span><span class="sxs-lookup"><span data-stu-id="71786-170">...</span></span>|
|<span data-ttu-id="71786-171">98109</span><span class="sxs-lookup"><span data-stu-id="71786-171">98109</span></span>|<span data-ttu-id="71786-172">10...00</span><span class="sxs-lookup"><span data-stu-id="71786-172">10...00</span></span>|

<span data-ttu-id="71786-173">Преобразованием для конвертирования категорийных данных в числа с одним активным состоянием является [`OneHotEncoding`](xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding%2A).</span><span class="sxs-lookup"><span data-stu-id="71786-173">The transform to convert categorical data to one-hot encoded numbers is [`OneHotEncoding`](xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding%2A).</span></span>

### <a name="hashing"></a><span data-ttu-id="71786-174">Хэширование</span><span class="sxs-lookup"><span data-stu-id="71786-174">Hashing</span></span>

<span data-ttu-id="71786-175">Хэширование — это еще один способ преобразования категорийных данных в числа.</span><span class="sxs-lookup"><span data-stu-id="71786-175">Hashing is another way to convert categorical data to numbers.</span></span> <span data-ttu-id="71786-176">Функция хэширования сопоставляет данные случайного размера (например, текстовую строку) в номер с фиксированным диапазоном.</span><span class="sxs-lookup"><span data-stu-id="71786-176">A hash function maps data of an arbitrary size (a string of text for example) onto a number with a fixed range.</span></span> <span data-ttu-id="71786-177">Хэширование может быть быстрым и экономным способом векторизации функций.</span><span class="sxs-lookup"><span data-stu-id="71786-177">Hashing can be a fast and space-efficient way of vectorizing features.</span></span> <span data-ttu-id="71786-178">Важным примером хэширования в машинном обучении является фильтрация нежелательной почты на электронной почте, где вместо поддержки словаря известных слов, каждое слово в сообщении хэшируется и добавляется в большой вектор функций.</span><span class="sxs-lookup"><span data-stu-id="71786-178">One notable example of hashing in machine learning is email spam filtering where, instead of maintaining a dictionary of known words, every word in the email is hashed and added to a large feature vector.</span></span> <span data-ttu-id="71786-179">Использование хэширования позволяет избежать проблем с обходом фильтрации вредоносной нежелательной почты, используя слова, которых нет в словаре.</span><span class="sxs-lookup"><span data-stu-id="71786-179">Using hashing in this way avoids the problem of malicious spam filtering circumvention by the use of words that are not in the dictionary.</span></span>

<span data-ttu-id="71786-180">ML.NET обеспечивает преобразование [хэша](xref:Microsoft.ML.ConversionsExtensionsCatalog.Hash%2A) для выполнения хэширования текста, дат и числовых данных.</span><span class="sxs-lookup"><span data-stu-id="71786-180">ML.NET provides [Hash](xref:Microsoft.ML.ConversionsExtensionsCatalog.Hash%2A) transform to perform hashing on text, dates, and numerical data.</span></span> <span data-ttu-id="71786-181">Как и сопоставление ключей значений, выходные данные преобразования хэша являются типами ключей.</span><span class="sxs-lookup"><span data-stu-id="71786-181">Like value key mapping, the outputs of the hash transform are key types.</span></span>

## <a name="work-with-text-data"></a><span data-ttu-id="71786-182">Работа с текстовыми данными</span><span class="sxs-lookup"><span data-stu-id="71786-182">Work with text data</span></span>

<span data-ttu-id="71786-183">Также, как и категорийные, текстовые данные необходимо преобразовывать в числовые функции, прежде чем использовать их для формирования модели машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="71786-183">Like categorical data, text data needs to be transformed into numerical features before using it to build a machine learning model.</span></span> <span data-ttu-id="71786-184">См. на [странице преобразований](../resources/transforms.md) более подробный список и описание преобразований текста.</span><span class="sxs-lookup"><span data-stu-id="71786-184">Visit the [transforms page](../resources/transforms.md) for a more detailed list and description of text transforms.</span></span>

<span data-ttu-id="71786-185">Используем такие данные, как загруженные ниже в [`IDataView`](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="71786-185">Using data like the data below that has been loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

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

<span data-ttu-id="71786-186">ML.NET предоставляет преобразование [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText%2A), которое принимает строковое значение текста и создает набор компонентов из текста, применяя ряд отдельных преобразований.</span><span class="sxs-lookup"><span data-stu-id="71786-186">ML.NET provides the [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText%2A) transform that takes a text's string value and creates a set of features from the text, by applying a series of individual transforms.</span></span>

```csharp
// Define text transform estimator
var textEstimator  = mlContext.Transforms.Text.FeaturizeText("Description");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer textTransformer = textEstimator.Fit(data);

// Transform data
IDataView transformedData = textTransformer.Transform(data);
```

<span data-ttu-id="71786-187">Результирующее преобразование превращает текстовые значения в столбце `Description` в числовой вектор, который будет выглядеть, как в выходных данных ниже.</span><span class="sxs-lookup"><span data-stu-id="71786-187">The resulting transform converts the text values in the `Description` column to a numerical vector that looks similar to the output below:</span></span>

```text
[ 0.2041241, 0.2041241, 0.2041241, 0.4082483, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0, 0, 0, 0, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0 ]
```

<span data-ttu-id="71786-188">Преобразования, составляющие `FeaturizeText`, можно также применять отдельно для более детального управления созданием компонентов.</span><span class="sxs-lookup"><span data-stu-id="71786-188">The transforms that make up `FeaturizeText` can also be applied individually for finer grain control over feature generation.</span></span>

```csharp
// Define text transform estimator
var textEstimator = mlContext.Transforms.Text.NormalizeText("Description")
    .Append(mlContext.Transforms.Text.TokenizeIntoWords("Description"))
    .Append(mlContext.Transforms.Text.RemoveDefaultStopWords("Description"))
    .Append(mlContext.Transforms.Conversion.MapValueToKey("Description"))
    .Append(mlContext.Transforms.Text.ProduceNgrams("Description"))
    .Append(mlContext.Transforms.NormalizeLpNorm("Description"));
```

<span data-ttu-id="71786-189">`textEstimator` содержит подмножество операций, выполняемых методом [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText%2A).</span><span class="sxs-lookup"><span data-stu-id="71786-189">`textEstimator` contains a subset of operations performed by the [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText%2A) method.</span></span> <span data-ttu-id="71786-190">Преимущество более сложного конвейера — контроль и мониторинг преобразований, примененных к данным.</span><span class="sxs-lookup"><span data-stu-id="71786-190">The benefit of a more complex pipeline is control and visibility over the transformations applied to the data.</span></span>

<span data-ttu-id="71786-191">На основании первой записи в качестве примера ниже приведено подробное описание результатов преобразования, определенного в `textEstimator`.</span><span class="sxs-lookup"><span data-stu-id="71786-191">Using the first entry as an example, the following is a detailed description of the results produced by the transformation steps defined by `textEstimator`:</span></span>

<span data-ttu-id="71786-192">**Исходный текст: This is a good product**</span><span class="sxs-lookup"><span data-stu-id="71786-192">**Original Text: This is a good product**</span></span>

|<span data-ttu-id="71786-193">Transform</span><span class="sxs-lookup"><span data-stu-id="71786-193">Transform</span></span> | <span data-ttu-id="71786-194">Описание</span><span class="sxs-lookup"><span data-stu-id="71786-194">Description</span></span> | <span data-ttu-id="71786-195">Результат</span><span class="sxs-lookup"><span data-stu-id="71786-195">Result</span></span>
|--|--|--|
|<span data-ttu-id="71786-196">1. NormalizeText</span><span class="sxs-lookup"><span data-stu-id="71786-196">1. NormalizeText</span></span> | <span data-ttu-id="71786-197">Преобразует все буквы в строчные по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="71786-197">Converts all letters to lowercase by default</span></span> | <span data-ttu-id="71786-198">this is a good product</span><span class="sxs-lookup"><span data-stu-id="71786-198">this is a good product</span></span>
|<span data-ttu-id="71786-199">2. TokenizeWords</span><span class="sxs-lookup"><span data-stu-id="71786-199">2. TokenizeWords</span></span> | <span data-ttu-id="71786-200">Разделяет строку на отдельные слова.</span><span class="sxs-lookup"><span data-stu-id="71786-200">Splits string into individual words</span></span> | <span data-ttu-id="71786-201">["this","is","a","good","product"]</span><span class="sxs-lookup"><span data-stu-id="71786-201">["this","is","a","good","product"]</span></span>
|<span data-ttu-id="71786-202">3. RemoveDefaultStopWords</span><span class="sxs-lookup"><span data-stu-id="71786-202">3. RemoveDefaultStopWords</span></span> | <span data-ttu-id="71786-203">Удаляет стоп-слова, такие как *is* и *a*.</span><span class="sxs-lookup"><span data-stu-id="71786-203">Removes stopwords like *is* and *a*.</span></span> | <span data-ttu-id="71786-204">["good","product"]</span><span class="sxs-lookup"><span data-stu-id="71786-204">["good","product"]</span></span>
|<span data-ttu-id="71786-205">4. MapValueToKey</span><span class="sxs-lookup"><span data-stu-id="71786-205">4. MapValueToKey</span></span> | <span data-ttu-id="71786-206">Сопоставляет значения ключей (категории) на основе входных данных.</span><span class="sxs-lookup"><span data-stu-id="71786-206">Maps the values to keys (categories) based on the input data</span></span> |  <span data-ttu-id="71786-207">[1,2]</span><span class="sxs-lookup"><span data-stu-id="71786-207">[1,2]</span></span>
|<span data-ttu-id="71786-208">5. ProduceNGrams</span><span class="sxs-lookup"><span data-stu-id="71786-208">5. ProduceNGrams</span></span> | <span data-ttu-id="71786-209">Преобразует текст в последовательность слов.</span><span class="sxs-lookup"><span data-stu-id="71786-209">Transforms text into sequence of consecutive words</span></span> | <span data-ttu-id="71786-210">[1,1,1,0,0]</span><span class="sxs-lookup"><span data-stu-id="71786-210">[1,1,1,0,0]</span></span>
|<span data-ttu-id="71786-211">6.  NormalizeLpNorm</span><span class="sxs-lookup"><span data-stu-id="71786-211">6. NormalizeLpNorm</span></span> | <span data-ttu-id="71786-212">Масштабирует входы по их lp-норме.</span><span class="sxs-lookup"><span data-stu-id="71786-212">Scale inputs by their lp-norm</span></span> | <span data-ttu-id="71786-213">[ 0.577350529, 0.577350529, 0.577350529, 0, 0 ]</span><span class="sxs-lookup"><span data-stu-id="71786-213">[ 0.577350529, 0.577350529, 0.577350529, 0, 0 ]</span></span>
