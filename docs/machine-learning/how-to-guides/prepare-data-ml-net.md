---
title: Подготовка данных для построения модели
description: Узнайте, как использовать преобразования в ML.NET для обработки и подготовки данных для дополнительной обработки или построения модели.
author: luisquintanilla
ms.author: luquinta
ms.date: 09/11/2019
ms.custom: mvc, how-to, title-hack-0625
ms.openlocfilehash: e9bfad4724b353b0f3bfc615a40f1d72b80a2cd4
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976982"
---
# <a name="prepare-data-for-building-a-model"></a>Подготовка данных для построения модели

Сведения об использовании ML.NET для подготовки данных к дополнительной обработке или построению модели.

Данные часто являются грязными и разреженными. Алгоритмы машинного обучения ML.NET ожидают входные данные или признаки в одном числовом векторе. Аналогичным образом, значение для прогнозирования (метка), особенно если это категориальные данные, должно быть закодировано. Поэтому одна из целей подготовки данных — преобразовать данные в формат, ожидаемый алгоритмами ML.NET.

## <a name="filter-data"></a>Фильтрация данных

В некоторых случаях не все данные в наборе данных важны для анализа. Один из подходов для удаления ненужных данных — фильтрация. [`DataOperationsCatalog`](xref:Microsoft.ML.DataOperationsCatalog) содержит набор операций фильтров, которые принимают [`IDataView`](xref:Microsoft.ML.IDataView), содержащий все данные, и возвращают [IDataView](xref:Microsoft.ML.IDataView), содержащий только релевантные точки данных. Важно отметить следующее: так как операции фильтрации не являются [`IEstimator`](xref:Microsoft.ML.IEstimator%601) или [`ITransformer`](xref:Microsoft.ML.ITransformer), как типы [`TransformsCatalog`](xref:Microsoft.ML.TransformsCatalog), они не могут рассматриваться как часть конвейера подготовки данных [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) или [`TransformerChain`](xref:Microsoft.ML.Data.TransformerChain%601).

Используйте следующие входные данные, которые загружаются в [`IDataView`](xref:Microsoft.ML.IDataView):

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

Чтобы отфильтровать данные на основе значения столбца, используйте метод [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn*).

```csharp
// Apply filter
IDataView filteredData = mlContext.Data.FilterRowsByColumn(data, "Price", lowerBound: 200000, upperBound: 1000000);
```

В приведенном выше примере задействуются строки в наборе данных с ценой между 200 000 и 1 000 000. Результат применения этого фильтра будет возвращать только последние две строки в данных и исключать первую строку, так как цена в ней — 100 000, что не входит в пределы указанного диапазона.

## <a name="replace-missing-values"></a>Замените отсутствующие значения

Отсутствующие значения — это обычное дело в наборах данных. Один из подходов к отсутствующим значениям состоит в том, чтобы заменить их значением по умолчанию для заданного типа или любым другим осмысленным значением, например средним значением в данных.

Используйте следующие входные данные, которые загружаются в [`IDataView`](xref:Microsoft.ML.IDataView):

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

Обратите внимание, что в последнем элементе в нашем списке отсутствует значение для `Price`. Чтобы заменить недостающие значения в столбце `Price`, используйте метод [`ReplaceMissingValues`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*) для заполнения этого отсутствующего значения.

> [!IMPORTANT]
> [`ReplaceMissingValue`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*) работает только с числовыми данными.

```csharp
// Define replacement estimator
var replacementEstimator = mlContext.Transforms.ReplaceMissingValues("Price", replacementMode: MissingValueReplacingEstimator.ReplacementMode.Mean);

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer replacementTransformer = replacementEstimator.Fit(data);

// Transform data
IDataView transformedData = replacementTransformer.Transform(data);
```

ML.NET поддерживает различные [режимы замены](xref:Microsoft.ML.Transforms.MissingValueReplacingEstimator.ReplacementMode). В примере выше используется режим замены `Mean`, который будет заполнять отсутствующее значение средним значением этого столбца. Замена заполняет свойство `Price` для последнего элемента в наших данные значением 200 000, так как это среднее значение между 100 000 и 300 000.

## <a name="use-normalizers"></a>Используйте нормализаторы

[Нормализация](https://en.wikipedia.org/wiki/Feature_scaling) — это прием предварительной обработки данных, используемый для стандартизации признаков, которые не находятся на одной шкале, что помогает ускорить сходимость алгоритмов. Например диапазоны таких значений, как возраст и доход, могут существенно различаться: возраст, как правило, задается в диапазоне от 0 до 100, а доход, как правило, в диапазоне от нуля до нескольких тысяч. См. на [странице преобразований](../resources/transforms.md) более подробный список и описание преобразований нормализации.

### <a name="min-max-normalization"></a>Минимакс

Используйте следующие входные данные, которые загружаются в [`IDataView`](xref:Microsoft.ML.IDataView):

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

Нормализация может применяться к столбцам с одинарными числовыми значениями, а также к векторам. Нормализуйте данные в столбце `Price` методом минимакса, используя метод [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax*).

```csharp
// Define min-max estimator
var minMaxEstimator = mlContext.Transforms.NormalizeMinMax("Price");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer minMaxTransformer = minMaxEstimator.Fit(data);

// Transform data
IDataView transformedData = minMaxTransformer.Transform(data);
```

Исходные значения цены `[200000,100000]` преобразуются в `[ 1, 0.5 ]` с помощью формулы нормализации `MinMax`, которая создает выходные значения в диапазоне от 0 до 1.

### <a name="binning"></a>Группирование

[Группирование](https://en.wikipedia.org/wiki/Data_binning) преобразует непрерывные значения в дискретное представление входных данных. Например предположим, что один из признаков — возраст. Вместо использования фактического возраста создаются диапазоны для этого значения путем группирования данных. Диапазон 0–18 может быть первой ячейкой, другой может быть 19–35 и т.д.

Используйте следующие входные данные, которые загружаются в [`IDataView`](xref:Microsoft.ML.IDataView):

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

Нормализуйте данные в интервалах группирования с помощью метода [`NormalizeBinning`](xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning*). Параметр `maximumBinCount` позволяет указать количество ячеек, нужное для классификации данных. В этом примере данные будут помещены в две ячейки.

```csharp
// Define binning estimator
var binningEstimator = mlContext.Transforms.NormalizeBinning("Price", maximumBinCount: 2);

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
var binningTransformer = binningEstimator.Fit(data);

// Transform Data
IDataView transformedData = binningTransformer.Transform(data);
```

В результате разделения на корзины создаются границы ячейки `[0,200000,Infinity]`. Поэтому полученные корзины — это `[0,1,1]`, так как первое наблюдение находится в диапазоне от 0 до 200 000, а другое больше 200 000, но меньше бесконечности.

## <a name="work-with-categorical-data"></a>Работа с категориальными данными

Нечисловые категориальные данные необходимо преобразовать в числа перед их использованием для создания модели машинного обучения.

Используйте следующие входные данные, которые загружаются в [`IDataView`](xref:Microsoft.ML.IDataView):

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

Категориальное свойство `VehicleType` может быть преобразовано в число с помощью метода [`OneHotEncoding`](xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding*).

```csharp
// Define categorical transform estimator
var categoricalEstimator = mlContext.Transforms.Categorical.OneHotEncoding("VehicleType");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer categoricalTransformer = categoricalEstimator.Fit(data);

// Transform Data
IDataView transformedData = categoricalTransformer.Transform(data);
```

Результирующее преобразование преобразует текстовое значение `VehicleType` в число. Записи в столбце `VehicleType` становятся следующими при применении преобразования:

```text
[
    1, // SUV
    2, // Sedan
    1 // SUV
]
```

## <a name="work-with-text-data"></a>Работа с текстовыми данными

Текстовые данные необходимо преобразовывать в числа, прежде чем использовать их для формирования модели машинного обучения. См. на [странице преобразований](../resources/transforms.md) более подробный список и описание преобразований текста.

Используем такие данные, как загруженные ниже в [`IDataView`](xref:Microsoft.ML.IDataView).

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

Минимальный шаг, позволяющий преобразовать текст в представление в виде числового вектора, заключается в использовании метода [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*). С помощью преобразования [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*) к столбцу входного текста применяется серия преобразований, которая приводит его к числовому вектору, представляющему lp-нормализованные слова и символьные n-граммы.

```csharp
// Define text transform estimator
var textEstimator  = mlContext.Transforms.Text.FeaturizeText("Description");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer textTransformer = textEstimator.Fit(data);

// Transform data
IDataView transformedData = textTransformer.Transform(data);
```

Результирующее преобразование превратит текстовые значения в столбце `Description` в числовой вектор, который будет выглядеть, как в выходных данных ниже.

```text
[ 0.2041241, 0.2041241, 0.2041241, 0.4082483, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0, 0, 0, 0, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0 ]
```

Сочетайте сложную обработку текста в [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) для удаления шума и уменьшения объема необходимых вычислительных ресурсов.

```csharp
// Define text transform estimator
var textEstimator = mlContext.Transforms.Text.NormalizeText("Description")
    .Append(mlContext.Transforms.Text.TokenizeIntoWords("Description"))
    .Append(mlContext.Transforms.Text.RemoveDefaultStopWords("Description"))
    .Append(mlContext.Transforms.Conversion.MapValueToKey("Description"))
    .Append(mlContext.Transforms.Text.ProduceNgrams("Description"))
    .Append(mlContext.Transforms.NormalizeLpNorm("Description"));
```

`textEstimator` содержит подмножество операций, выполняемых методом [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*). Преимущество более сложного конвейера — контроль и мониторинг преобразований, примененных к данным.

На основании первой записи в качестве примера ниже приведено подробное описание результатов преобразования, определенного в `textEstimator`.

**Исходный текст: This is a good product**

|Transform | ОПИСАНИЕ | Результат
|--|--|--|
|1. NormalizeText | Преобразует все буквы в строчные по умолчанию. | this is a good product
|2. TokenizeWords | Разделяет строку на отдельные слова. | ["this","is","a","good","product"]
|3. RemoveDefaultStopWords | Удаляет стоп-слова, такие как *is* и *a*. | ["good","product"]
|4. MapValueToKey | Сопоставляет значения ключей (категории) на основе входных данных. |  [1,2]
|5. ProduceNGrams | Преобразует текст в последовательность слов. | [1,1,1,0,0]
|6.  NormalizeLpNorm | Масштабирует входы по их lp-норме. | [ 0.577350529, 0.577350529, 0.577350529, 0, 0 ]
