---
title: Интерпретация моделей ML.NET с помощью функции PFI
description: Сведения об определении важности признаков моделей с помощью средства Permutation Feature Importance в ML.NET
ms.date: 01/30/2020
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to
ms.openlocfilehash: c1163a41cd2feb0e8785ae9d4c6a71dfbedf3f12
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2020
ms.locfileid: "77092620"
---
# <a name="interpret-model-predictions-using-permutation-feature-importance"></a>Интерпретация прогнозов модели с помощью функции PFI

Использование функции PFI для интерпретации прогнозов модели машинного обучения ML.NET. PFI оценивает относительный вклад каждого признака в прогнозе.

Модели машинного обучения часто представляются черными ящиками, которые принимают входные данные и создают выходные данные. Промежуточные этапы или взаимодействие между компонентами, которые влияют на выходные данные, распознаются редко. Машинное обучение проникает во все аспекты нашей повседневной жизни, такие как здравоохранение, а значит, очень важно понимать, почему модель машинного обучения принимает именно те решения, которые она принимает. Например, если диагностика осуществляется на основе модели машинного обучения, у медицинских работников должен быть способ изучить факторы, которые на нее повлияли. Правильная диагностика намного повышает шансы пациента на быстрое выздоровление. Таким образом, чем объяснение модели лучше, тем увереннее медицинские работники будут принимать или отклонять принятые моделью решения.

Для объяснения моделей применяются различные приемы, одной из которых является PFI. PFI — это прием, который используется для объяснения моделей классификации и регрессии и основан на работе [Бреймана *Random Forests* (Случайные леса)](https://www.stat.berkeley.edu/~breiman/randomforest2001.pdf) (см. раздел 10). В общем смысле он случайным образом тасует весь набор данных по одному компоненту за раз и рассчитывает, на сколько снижается метрика эффективности, отражающая интерес. Чем больше изменение, тем важнее компонент.

Выделив самые важные компоненты, сборщики модели могут сосредоточиться на работе с подмножеством более значимых компонентов и таким образом уменьшить шум и время обучения.

## <a name="load-the-data"></a>Загрузка данных

Компоненты набора данных, которые используются в этом примере, перечислены в столбцах 1–12. Цель — спрогнозировать `Price`.

| Столбец | Функция | Описание
| --- | --- | --- |
| 1 | CrimeRate | Уровень преступности на душу населения
| 2 | ResidentialZones | Жилые районы в городе
| 3 | CommercialZones | Нежилые районы в городе
| 4 | NearWater | Близость к водоему
| 5 | ToxicWasteLevels | Уровень токсичности (PPM)
| 6 | AverageRoomNumber | Среднее количество комнат в доме
| 7 | HomeAge | Возраст дома
| 8 | BusinessCenterDistance | Расстояние до ближайшего делового района
| 9 | HighwayAccess | Близость к автомагистралям
| 10 | TaxRate | Ставка налога на имущество
| 11 | StudentTeacherRatio | Соотношение учащихся и учителей
| 12 | PercentPopulationBelowPoverty | Процент населения, живущего за чертой бедности
| 13 | Price | Цена на дом

Пример набора данных:

```text
1,24,13,1,0.59,3,96,11,23,608,14,13,32
4,80,18,1,0.37,5,14,7,4,346,19,13,41
2,98,16,1,0.25,10,5,1,8,689,13,36,12
```

Данные в этом примере можно моделировать с помощью класса, например, `HousingPriceData`, и загружать в [`IDataView`](xref:Microsoft.ML.IDataView).

```csharp
class HousingPriceData
{
    [LoadColumn(0)]
    public float CrimeRate { get; set; }

    [LoadColumn(1)]
    public float ResidentialZones { get; set; }

    [LoadColumn(2)]
    public float CommercialZones { get; set; }

    [LoadColumn(3)]
    public float NearWater { get; set; }

    [LoadColumn(4)]
    public float ToxicWasteLevels { get; set; }

    [LoadColumn(5)]
    public float AverageRoomNumber { get; set; }

    [LoadColumn(6)]
    public float HomeAge { get; set; }

    [LoadColumn(7)]
    public float BusinessCenterDistance { get; set; }

    [LoadColumn(8)]
    public float HighwayAccess { get; set; }

    [LoadColumn(9)]
    public float TaxRate { get; set; }

    [LoadColumn(10)]
    public float StudentTeacherRatio { get; set; }

    [LoadColumn(11)]
    public float PercentPopulationBelowPoverty { get; set; }

    [LoadColumn(12)]
    [ColumnName("Label")]
    public float Price { get; set; }
}
```

## <a name="train-the-model"></a>Обучение модели

Код в приведенном ниже примере иллюстрирует процесс обучения модели линейной регрессии для прогнозирования цен на дома.

```csharp
// 1. Get the column name of input features.
string[] featureColumnNames =
    data.Schema
        .Select(column => column.Name)
        .Where(columnName => columnName != "Label").ToArray();

// 2. Define estimator with data pre-processing steps
IEstimator<ITransformer> dataPrepEstimator =
    mlContext.Transforms.Concatenate("Features", featureColumnNames)
        .Append(mlContext.Transforms.NormalizeMinMax("Features"));

// 3. Create transformer using the data pre-processing estimator
ITransformer dataPrepTransformer = dataPrepEstimator.Fit(data);

// 4. Pre-process the training data
IDataView preprocessedTrainData = dataPrepTransformer.Transform(data);

// 5. Define Stochastic Dual Coordinate Ascent machine learning estimator
var sdcaEstimator = mlContext.Regression.Trainers.Sdca();

// 6. Train machine learning model
var sdcaModel = sdcaEstimator.Fit(preprocessedTrainData);
```

## <a name="explain-the-model-with-permutation-feature-importance-pfi"></a>Объяснение модели с помощью функции PFI

В ML.NET используйте метод [`PermutationFeatureImportance`](xref:Microsoft.ML.PermutationFeatureImportanceExtensions) для решения соответствующей задачи.

```csharp
ImmutableArray<RegressionMetricsStatistics> permutationFeatureImportance =
    mlContext
        .Regression
        .PermutationFeatureImportance(sdcaModel, preprocessedTrainData, permutationCount:3);
```

В результате применения метода [`PermutationFeatureImportance`](xref:Microsoft.ML.PermutationFeatureImportanceExtensions) в проверочном наборе данных создается [`ImmutableArray`](xref:System.Collections.Immutable.ImmutableArray) из объектов [`RegressionMetricsStatistics`](xref:Microsoft.ML.Data.RegressionMetricsStatistics). [`RegressionMetricsStatistics`](xref:Microsoft.ML.Data.RegressionMetricsStatistics) предоставляет сводные статистические данные, такие как среднее и стандартное отклонение, для нескольких значений параметра [`RegressionMetrics`](xref:Microsoft.ML.Data.RegressionMetrics), количество которых равно числу перестановок, которое определяет параметр `permutationCount`.

Важность, или в данном случае среднее абсолютное снижение метрики R-квадрат, рассчитанное методом [`PermutationFeatureImportance`](xref:Microsoft.ML.PermutationFeatureImportanceExtensions), можно отсортировать по убыванию.

```csharp
// Order features by importance
var featureImportanceMetrics =
    permutationFeatureImportance
        .Select((metric, index) => new { index, metric.RSquared })
        .OrderByDescending(myFeatures => Math.Abs(myFeatures.RSquared.Mean));

Console.WriteLine("Feature\tPFI");

foreach (var feature in featureImportanceMetrics)
{
    Console.WriteLine($"{featureColumnNames[feature.index],-20}|\t{feature.RSquared.Mean:F6}");
}
```

При печати значений для каждого параметра в `featureImportanceMetrics` выдается результат представленного ниже вида. У вас результаты будут другими, поскольку эти значения зависят от предоставленных данных.

| Функция | Изменение в R-квадрат |
|:--|:--:|
HighwayAccess       |   –0,042731
StudentTeacherRatio |   –0,012730
BusinessCenterDistance| –0,010491
TaxRate             |   –0,008545
AverageRoomNumber   |   –0,003949
CrimeRate           |   –0,003665
CommercialZones     |   0,002749
HomeAge             |   –0,002426
ResidentialZones    |   –0,002319
NearWater           |   0,000203
PercentPopulationLivingBelowPoverty|    0,000031
ToxicWasteLevels    |   –0,000019

Рассмотрим пять самых важных компонентов для этого набора данных. Цена на дом, спрогнозированная этой моделью, зависит от его близости к автомагистралям, соотношения учащихся и учителей в окрестных школах, близости к основным центрам трудоустройства, ставки налога на имущество и среднего количества комнат.
