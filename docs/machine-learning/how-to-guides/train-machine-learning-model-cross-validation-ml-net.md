---
title: Обучение модели машинного обучения с помощью перекрестной проверки
description: Узнайте, как использовать кросс-валидацию для создания более надежных моделей машинного обучения в ML.NET. Кросс-валидация — это методика обучения и оценки модели, которая разбивает данные на несколько секций и обучает несколько алгоритмов на этих секциях.
ms.date: 06/25/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to,title-hack-0625
ms.openlocfilehash: c68c2b61054f59f03b4743ec30a694e94086ebab
ms.sourcegitcommit: bab17fd81bab7886449217356084bf4881d6e7c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2019
ms.locfileid: "67397649"
---
# <a name="train-a-machine-learning-model-using-cross-validation"></a><span data-ttu-id="72335-104">Обучение модели машинного обучения с помощью перекрестной проверки</span><span class="sxs-lookup"><span data-stu-id="72335-104">Train a machine learning model using cross validation</span></span>

<span data-ttu-id="72335-105">Узнайте, как использовать перекрестную проверку для обучения более надежных моделей машинного обучения в ML.NET.</span><span class="sxs-lookup"><span data-stu-id="72335-105">Learn how to use cross validation to train more robust machine learning models in ML.NET.</span></span> 

<span data-ttu-id="72335-106">Кросс-валидация — это методика обучения и оценки модели, которая разбивает данные на несколько секций и обучает несколько алгоритмов на этих секциях.</span><span class="sxs-lookup"><span data-stu-id="72335-106">Cross-validation is a training and model evaluation technique that splits the data into several partitions and trains multiple algorithms on these partitions.</span></span> <span data-ttu-id="72335-107">Этот метод повышает надежность модели, удерживая данные вне процесса обучения.</span><span class="sxs-lookup"><span data-stu-id="72335-107">This technique improves the robustness of the model by holding out data from the training process.</span></span> <span data-ttu-id="72335-108">Кроме повышения производительности на многих неучитываемых наблюдениях, в средах с ограниченными данными он может быть эффективным инструментом для обучения моделей с меньшим набором данных.</span><span class="sxs-lookup"><span data-stu-id="72335-108">In addition to improving performance on unseen observations, in data-constrained environments it can be an effective tool for training models with a smaller dataset.</span></span>

## <a name="the-data-and-data-model"></a><span data-ttu-id="72335-109">Данные и модель данных</span><span class="sxs-lookup"><span data-stu-id="72335-109">The data and data model</span></span>

<span data-ttu-id="72335-110">Используя данные из файла, который имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="72335-110">Given data from a file that has the following format:</span></span>

```text
Size (Sq. ft.), HistoricalPrice1 ($), HistoricalPrice2 ($), HistoricalPrice3 ($), Current Price ($)
620.00, 148330.32, 140913.81, 136686.39, 146105.37
550.00, 557033.46, 529181.78, 513306.33, 548677.95
1127.00, 479320.99, 455354.94, 441694.30, 472131.18
1120.00, 47504.98, 45129.73, 43775.84, 46792.41
```

<span data-ttu-id="72335-111">Можно моделировать данные с помощью класса, например `HousingData`:</span><span class="sxs-lookup"><span data-stu-id="72335-111">The data can be modeled by a class like `HousingData`:</span></span>

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

<span data-ttu-id="72335-112">Загрузка данных в [`IDataView`](xref:Microsoft.ML.IDataView):</span><span class="sxs-lookup"><span data-stu-id="72335-112">Load the data in into an [`IDataView`](xref:Microsoft.ML.IDataView).</span></span>

## <a name="prepare-the-data"></a><span data-ttu-id="72335-113">Подготовка данных</span><span class="sxs-lookup"><span data-stu-id="72335-113">Prepare the data</span></span>

<span data-ttu-id="72335-114">Следует предварительно обработать данные перед их использованием для создания модели машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="72335-114">Pre-process the data before using it to build the machine learning model.</span></span> <span data-ttu-id="72335-115">В этом примере столбцы `Size` и `HistoricalPrices` объединяются в один вектор признака, который выводится в новый столбец с именем `Features` с помощью метода [`Concatenate`](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate*).</span><span class="sxs-lookup"><span data-stu-id="72335-115">In this sample, the `Size` and `HistoricalPrices` columns are combined into a single feature vector,  which is output to a new column called `Features` using the [`Concatenate`](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate*) method.</span></span> <span data-ttu-id="72335-116">Кроме получения данных в формате, ожидаемом алгоритмами ML.NET, сцепка столбцов оптимизирует последующие операции в конвейере, применяя операцию один раз для объединенного столбца, а не обрабатывая каждый отдельный столбец.</span><span class="sxs-lookup"><span data-stu-id="72335-116">In addition to getting the data into the format expected by ML.NET algorithms, concatenating columns optimizes subsequent operations in the pipeline by applying the operation once for the concatenated column instead of each of the separate columns.</span></span> 

<span data-ttu-id="72335-117">Как только столбцы объединяются в один вектор, [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax*) применяется к столбцу `Features`, чтобы получить `Size` и `HistoricalPrices` в одном и том же диапазоне 0–1.</span><span class="sxs-lookup"><span data-stu-id="72335-117">Once the columns are combined into a single vector, [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax*) is applied to the `Features` column to get `Size` and `HistoricalPrices` in the same range between 0-1.</span></span> 

```csharp
// Define data prep estimator
IEstimator<ITransformer> dataPrepEstimator = 
    mlContext.Transforms.Concatenate("Features", new string[] { "Size", "HistoricalPrices" })
        .Append(mlContext.Transforms.NormalizeMinMax("Features"));

// Create data prep transformer
ITransformer dataPrepTransformer = dataPrepEstimator.Fit(data);

// Transform data
IDataView transformedData = dataPrepTransformer.Transform(data);
```

## <a name="train-model-with-cross-validation"></a><span data-ttu-id="72335-118">Обучение модели с помощью кросс-валидации</span><span class="sxs-lookup"><span data-stu-id="72335-118">Train model with cross validation</span></span>

<span data-ttu-id="72335-119">Когда данные предварительно обработаны, пришло время для обучения модели.</span><span class="sxs-lookup"><span data-stu-id="72335-119">Once the data has been pre-processed, it's time to train the model.</span></span> <span data-ttu-id="72335-120">Во-первых, выберите алгоритм, который наиболее точно соответствует задаче машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="72335-120">First, select the algorithm that most closely aligns with the machine learning task to be performed.</span></span> <span data-ttu-id="72335-121">Поскольку прогнозируемое значение является числовым и непрерывным, задача — регрессия.</span><span class="sxs-lookup"><span data-stu-id="72335-121">Because the predicted value is a numerically continuous value, the task is regression.</span></span> <span data-ttu-id="72335-122">Один из алгоритмов регрессии, реализуемый ML.NET, – алгоритм [`StochasticDualCoordinateAscentCoordinator`](xref:Microsoft.ML.Trainers.SdcaRegressionTrainer).</span><span class="sxs-lookup"><span data-stu-id="72335-122">One of the regression algorithms implemented by ML.NET is the [`StochasticDualCoordinateAscentCoordinator`](xref:Microsoft.ML.Trainers.SdcaRegressionTrainer) algorithm.</span></span> <span data-ttu-id="72335-123">Для обучения модели с использованием кросс-валидации используется метод [`CrossValidate`](xref:Microsoft.ML.RegressionCatalog.CrossValidate*).</span><span class="sxs-lookup"><span data-stu-id="72335-123">To train the model with cross-validation use the [`CrossValidate`](xref:Microsoft.ML.RegressionCatalog.CrossValidate*) method.</span></span> 

> [!NOTE]
> <span data-ttu-id="72335-124">Несмотря на то что в этом примере используется модель линейной регрессии, CrossValidate применяется для всех других задач машинного обучения в ML.NET, за исключением обнаружения аномалий.</span><span class="sxs-lookup"><span data-stu-id="72335-124">Although this sample uses a linear regression model, CrossValidate is applicable to all other machine learning tasks in ML.NET except Anomaly Detection.</span></span>

```csharp
// Define StochasticDualCoordinateAscent algorithm estimator
IEstimator<ITransformer> sdcaEstimator = mlContext.Regression.Trainers.Sdca();

// Apply 5-fold cross validation
var cvResults = mlContext.Regression.CrossValidate(transformedData, sdcaEstimator, numberOfFolds: 5);
```

<span data-ttu-id="72335-125">[`CrossValidate`](xref:Microsoft.ML.RegressionCatalog.CrossValidate*) выполняет следующие действия.</span><span class="sxs-lookup"><span data-stu-id="72335-125">[`CrossValidate`](xref:Microsoft.ML.RegressionCatalog.CrossValidate*) performs the following operations:</span></span>

1. <span data-ttu-id="72335-126">Разбивает данные на несколько секций по значению, указанному в параметре `numberOfFolds`.</span><span class="sxs-lookup"><span data-stu-id="72335-126">Partitions the data into a number of partitions equal to the value specified in the `numberOfFolds` parameter.</span></span> <span data-ttu-id="72335-127">В результате каждая секция превратится в объект [`TrainTestData`](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData).</span><span class="sxs-lookup"><span data-stu-id="72335-127">The result of each partition is a [`TrainTestData`](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData) object.</span></span>
1. <span data-ttu-id="72335-128">Модель обучается на каждой из секций с помощью указанного алгоритма оценки машинного обучения в наборе данных для обучения.</span><span class="sxs-lookup"><span data-stu-id="72335-128">A model is trained on each of the partitions using the specified machine learning algorithm estimator on the training data set.</span></span>
1. <span data-ttu-id="72335-129">Эффективность каждой модели оценивается с помощью метода [`Evaluate`](xref:Microsoft.ML.RegressionCatalog.Evaluate*) на тестовом наборе данных.</span><span class="sxs-lookup"><span data-stu-id="72335-129">Each model's performance is evaluated using the [`Evaluate`](xref:Microsoft.ML.RegressionCatalog.Evaluate*) method on the test data set.</span></span> 
1. <span data-ttu-id="72335-130">Для всех моделей возвращается сама модель, а также ее метрики.</span><span class="sxs-lookup"><span data-stu-id="72335-130">The model along with its metrics are returned for each of the models.</span></span>

<span data-ttu-id="72335-131">Результат в `cvResults` сохраняется в коллекции объектов [`CrossValidationResult`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601).</span><span class="sxs-lookup"><span data-stu-id="72335-131">The result stored in `cvResults` is a collection of [`CrossValidationResult`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601) objects.</span></span> <span data-ttu-id="72335-132">Этот объект включает обученную модель, а также метрики, доступные через свойства [`Model`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601.Model) и [`Metrics`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601.Metrics) соответственно.</span><span class="sxs-lookup"><span data-stu-id="72335-132">This object includes the trained model as well as metrics which are both accessible form the [`Model`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601.Model) and [`Metrics`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601.Metrics) properties respectively.</span></span> <span data-ttu-id="72335-133">В этом примере свойство `Model` имеет тип [`ITransformer`](xref:Microsoft.ML.ITransformer), а свойство `Metrics` имеет тип [`RegressionMetrics`](xref:Microsoft.ML.Data.RegressionMetrics).</span><span class="sxs-lookup"><span data-stu-id="72335-133">In this sample, the `Model` property is of type [`ITransformer`](xref:Microsoft.ML.ITransformer) and the `Metrics` property is of type [`RegressionMetrics`](xref:Microsoft.ML.Data.RegressionMetrics).</span></span> 

## <a name="evaluate-the-model"></a><span data-ttu-id="72335-134">Оценка модели</span><span class="sxs-lookup"><span data-stu-id="72335-134">Evaluate the model</span></span>

<span data-ttu-id="72335-135">Метрики для разных обученных моделей доступны через свойства `Metrics` отдельного объекта [`CrossValidationResult`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601).</span><span class="sxs-lookup"><span data-stu-id="72335-135">Metrics for the different trained models can be accessed through the `Metrics` property of the individual [`CrossValidationResult`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601) object.</span></span> <span data-ttu-id="72335-136">В этом случае [метрика R-квадрат](https://en.wikipedia.org/wiki/Coefficient_of_determination) извлекается и сохраняется в переменной `rSquared`.</span><span class="sxs-lookup"><span data-stu-id="72335-136">In this case, the [R-Squared metric](https://en.wikipedia.org/wiki/Coefficient_of_determination) is accessed and stored in the variable `rSquared`.</span></span> 

```csharp
IEnumerable<double> rSquared = 
    cvResults
        .Select(fold => fold.Metrics.RSquared);
```

<span data-ttu-id="72335-137">Если проверить содержимое переменной `rSquared`, в выходных данных должно быть пять значений в диапазоне от 0 до 1, где близость к 1 означает, что эта модель лучше.</span><span class="sxs-lookup"><span data-stu-id="72335-137">If you inspect the contents of the `rSquared` variable, the output should be five values ranging from 0-1 where closer to 1 means best.</span></span> <span data-ttu-id="72335-138">С помощью таких метрик, как R-квадрат, отранжируйте модели от лучших к наихудшим.</span><span class="sxs-lookup"><span data-stu-id="72335-138">Using metrics like R-Squared, select the models from best to worst performing.</span></span> <span data-ttu-id="72335-139">Затем выберите лучшую модель для прогнозов или дополнительных операций.</span><span class="sxs-lookup"><span data-stu-id="72335-139">Then, select the top model to make predictions or perform additional operations with.</span></span>

```csharp
// Select all models
ITransformer[] models =
    cvResults
        .OrderByDescending(fold => fold.Metrics.RSquared)
        .Select(fold => fold.Model)
        .ToArray();

// Get Top Model
ITransformer topModel = models[0];
```
