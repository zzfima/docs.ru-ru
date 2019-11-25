---
title: Обучение и оценка модели
description: Из этой статьи вы узнаете, как создавать модели машинного обучения, собирать метрики и измерять производительность с помощью ML.NET. Модель машинного обучения выполняет обнаружение шаблонов в данных обучения для создания прогнозов на основе новых данных.
ms.date: 08/29/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to, title-hack-0625
ms.openlocfilehash: 0e0f43225b9bf243c31b3095817bdcbdb3123012
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976759"
---
# <a name="train-and-evaluate-a-model"></a>Обучение и оценка модели

Из этой статьи вы узнаете, как создавать модели машинного обучения, собирать метрики и измерять производительность с помощью ML.NET. Несмотря на то что код в этом примере обучает модель регрессии, те же принципы действуют и в большинстве других алгоритмов.

## <a name="split-data-for-training-and-testing"></a>Разделение данных на обучающий и проверочный наборы

Цель модели машинного обучения — обнаружить закономерности в обучающих данных. Эти закономерности используются для создания прогнозов на основе новых данных.

Можно моделировать данные с помощью класса, например `HousingData`.

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

Используйте следующие данные, которые загружаются в [`IDataView`](xref:Microsoft.ML.IDataView).

```csharp
HousingData[] housingData = new HousingData[]
{
    new HousingData
    {
        Size = 600f,
        HistoricalPrices = new float[] { 100000f ,125000f ,122000f },
        CurrentPrice = 170000f
    },
    new HousingData
    {
        Size = 1000f,
        HistoricalPrices = new float[] { 200000f, 250000f, 230000f },
        CurrentPrice = 225000f
    },
    new HousingData
    {
        Size = 1000f,
        HistoricalPrices = new float[] { 126000f, 130000f, 200000f },
        CurrentPrice = 195000f
    },
    new HousingData
    {
        Size = 850f,
        HistoricalPrices = new float[] { 150000f,175000f,210000f },
        CurrentPrice = 205000f
    },
    new HousingData
    {
        Size = 900f,
        HistoricalPrices = new float[] { 155000f, 190000f, 220000f },
        CurrentPrice = 210000f
    },
    new HousingData
    {
        Size = 550f,
        HistoricalPrices = new float[] { 99000f, 98000f, 130000f },
        CurrentPrice = 180000f
    }
};
```

Разделите данные на обучающий и проверочный наборы с помощью метода [`TrainTestSplit`](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit*). В результате появится объект [`TrainTestData`](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData), содержащий два члена [`IDataView`](xref:Microsoft.ML.IDataView) — один для обучающего набора данных, другой для проверочного. Распределение данных определяется параметром `testFraction`. В приведенном ниже фрагменте кода для проверочного набора удерживаются 20 процентов исходных данных.

```csharp
DataOperationsCatalog.TrainTestData dataSplit = mlContext.Data.TrainTestSplit(data, testFraction: 0.2);
IDataView trainData = dataSplit.TrainSet;
IDataView testData = dataSplit.TestSet;
```

## <a name="prepare-the-data"></a>Подготовка данных

Перед обучением модели машинного обучения данные необходимо подвергнуть предварительной обработке. Дополнительные сведения о подготовке данных см. в [инструкции по подготовке данных](prepare-data-ml-net.md), а также в [`transforms page`](../resources/transforms.md).

Алгоритмы ML.NET имеют ограничения на типы входных столбцов. Кроме того, если значения не указаны, в качестве имен входных и выходных столбцов используются значения по умолчанию.

### <a name="working-with-expected-column-types"></a>Работа с ожидаемыми типами столбцов

Алгоритмы машинного обучения в ML.NET в качестве входных данных ожидают вектор с плавающей запятой известного размера. Если все данные уже переведены в числовой формат и предназначены для одновременной обработки (пиксели изображения), примените к модели данных атрибут [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute).

Если не все данные являются числовыми, а вы хотите к каждому столбцу применить отдельное преобразование данных, используйте метод [`Concatenate`](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate*) после обработки каждого столбца — в результате все отдельные столбцы будут объединены в единый вектор компонентов, который будет выходными данными нового столбца.

В следующем фрагменте кода столбцы `Size` и `HistoricalPrices` объединены в один вектор компонентов, который служит выходными данными для нового столбца с именем `Features`. Поскольку нет разницы в масштабах, [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax*) применяется к столбцу `Features` для нормализации данных.

```csharp
// Define Data Prep Estimator
// 1. Concatenate Size and Historical into a single feature vector output to a new column called Features
// 2. Normalize Features vector
IEstimator<ITransformer> dataPrepEstimator =
    mlContext.Transforms.Concatenate("Features", "Size", "HistoricalPrices")
        .Append(mlContext.Transforms.NormalizeMinMax("Features"));

// Create data prep transformer
ITransformer dataPrepTransformer = dataPrepEstimator.Fit(trainData);

// Apply transforms to training data
IDataView transformedTrainingData = dataPrepTransformer.Transform(trainData);
```

### <a name="working-with-default-column-names"></a>Работа с именами столбцов по умолчанию

Если имена столбцов не указаны, алгоритмы ML.NET используют имена по умолчанию. Все инструкторы имеют параметр с именем `featureColumnName` для входных данных, алгоритма, а там, где это применимо, еще и параметр с именем `labelColumnName` для ожидаемого значения. По умолчанию используются значения `Features` и `Label` соответственно.

Если во время предварительной обработки используется метод [`Concatenate`](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate*), который создает столбец с именем `Features`, имя столбца компонентов в параметрах алгоритма указывать необязательно, поскольку он уже существует в предварительно обработанных данных `IDataView`. Столбец меток — `CurrentPrice`, но в связи с тем, что атрибут [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) используется в модели данных, ML.NET переименовывает столбец `CurrentPrice` в `Label` и таким образом устраняет необходимость предоставлять параметр `labelColumnName` для средства оценки алгоритма машинного обучения.

Если вы не хотите использовать имена столбцов по умолчанию, передайте имена столбцов компонентов и меток в виде параметров при определении средства оценки алгоритма машинного обучения, как показано в следующем фрагменте кода:

```csharp
var UserDefinedColumnSdcaEstimator = mlContext.Regression.Trainers.Sdca(labelColumnName: "MyLabelColumnName", featureColumnName: "MyFeatureColumnName");
```

## <a name="train-the-machine-learning-model"></a>Обучение модели машинного обучения

Когда данные пройдут предварительную обработку, используйте метод [`Fit`](xref:Microsoft.ML.Trainers.TrainerEstimatorBase`2.Fit*) для обучения модели машинного обучения с алгоритмом регрессии [`StochasticDualCoordinateAscent`](xref:Microsoft.ML.Trainers.SdcaRegressionTrainer).

```csharp
// Define StochasticDualCoordinateAscent regression algorithm estimator
var sdcaEstimator = mlContext.Regression.Trainers.Sdca();

// Build machine learning model
var trainedModel = sdcaEstimator.Fit(transformedTrainingData);
```

## <a name="extract-model-parameters"></a>Извлечение параметров модели

После обучения модели извлеките полученные [`ModelParameters`](xref:Microsoft.ML.Trainers.ModelParametersBase%601) для проверки или повторного обучения. [`LinearRegressionModelParameters`](xref:Microsoft.ML.Trainers.LinearRegressionModelParameters) предоставляют смещение и полученные коэффициенты или вес обученной модели.

```csharp
var trainedModelParameters = trainedModel.Model as LinearRegressionModelParameters;
```

> [!NOTE]
> Другие модели включают параметры, характерные для их задач. Например, [алгоритм K-средних](xref:Microsoft.ML.Trainers.KMeansTrainer) помещает данные в кластер на основе центроидов, а [`KMeansModelParameters`](xref:Microsoft.ML.Trainers.KMeansModelParameters) содержит свойство, в котором хранятся полученные центроиды. Чтобы узнать больше, изучите [`Microsoft.ML.Trainers`документацию по API](xref:Microsoft.ML.Trainers) и выполните поиск классов, в именах которых есть `ModelParameters`.

## <a name="evaluate-model-quality"></a>Оценка качества модели

Чтобы выбрать наиболее эффективную модель, необходимо оценить ее производительность на основе проверочных данных. Для измерения различных метрик обученной модели используйте метод [`Evaluate`](xref:Microsoft.ML.RegressionCatalog.Evaluate*).

> [!NOTE]
> Метод `Evaluate` создает различные метрики в зависимости от того, на каком компьютере выполнялась задача машинного обучения. Чтобы узнать больше, изучите [`Microsoft.ML.Data`документацию по API](xref:Microsoft.ML.Data) и выполните поиск классов, в именах которых есть `Metrics`.

```csharp
// Measure trained model performance
// Apply data prep transformer to test data
IDataView transformedTestData = dataPrepTransformer.Transform(testData);

// Use trained model to make inferences on test data
IDataView testDataPredictions = trainedModel.Transform(transformedTestData);

// Extract model metrics and get RSquared
RegressionMetrics trainedModelMetrics = mlContext.Regression.Evaluate(testDataPredictions);
double rSquared = trainedModelMetrics.RSquared;
```

В приведенном выше фрагменте кода:

1. Проверочный набор данных подвергается предварительной обработке с использованием предварительно заданных преобразований для подготовки данных.
2. В обученной модели машинного обучения формируются прогнозы на основе проверочных данных.
3. В методе `Evaluate` значения в столбцу `CurrentPrice` проверочного набора данных сравниваются со столбцом `Score`, куда сохраняются новые полученные прогнозы, и рассчитываются метрики модели регрессии, одна из которых, R-квадрат, хранится в переменной `rSquared`.

> [!NOTE]
> В этом небольшом примере из-за ограниченного объема данных значение R-квадрат не попадает в диапазон от 0 до 1. В реальной ситуации его значение должно быть в диапазоне от 0 до 1.
