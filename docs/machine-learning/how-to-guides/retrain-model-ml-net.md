---
title: Повторное обучение модели
description: Узнайте, как переобучать модель в ML.NET
ms.date: 05/03/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 2f8f8c035166612aabede8a512485bdf296c5655
ms.sourcegitcommit: 682c64df0322c7bda016f8bfea8954e9b31f1990
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2019
ms.locfileid: "65557908"
---
# <a name="re-train-a-model"></a><span data-ttu-id="a77e4-103">Повторное обучение модели</span><span class="sxs-lookup"><span data-stu-id="a77e4-103">Re-train a model</span></span>

<span data-ttu-id="a77e4-104">Узнайте, как переобучать модель машинного обучения в ML.NET.</span><span class="sxs-lookup"><span data-stu-id="a77e4-104">Learn how to retrain a machine learning model in ML.NET.</span></span>

<span data-ttu-id="a77e4-105">Мир и данные вокруг него меняются с постоянной скоростью.</span><span class="sxs-lookup"><span data-stu-id="a77e4-105">The world and the data around it change at a constant pace.</span></span> <span data-ttu-id="a77e4-106">Это значит, что вместе с ними должны меняться и обновляться модели машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="a77e4-106">As such, models need to change and update as well.</span></span> <span data-ttu-id="a77e4-107">ML.NET предоставляет функциональные возможности для переобучения моделей с использованием параметров обученной модели, которые служат отправной точкой для постоянного развития и позволяют не начинать каждый раз заново.</span><span class="sxs-lookup"><span data-stu-id="a77e4-107">ML.NET provides functionality for re-training models using learned model parameters as a starting point to continually build on previous experience rather than starting from scratch every time.</span></span>  

<span data-ttu-id="a77e4-108">В ML.NET можно переобучать следующие алгоритмы:</span><span class="sxs-lookup"><span data-stu-id="a77e4-108">The following algorithms are re-trainable in ML.NET:</span></span>

- <span data-ttu-id="a77e4-109">[AveragedPerceptronTrainer](xref:Microsoft.ML.Trainers.AveragedPerceptronTrainer);</span><span class="sxs-lookup"><span data-stu-id="a77e4-109">[AveragedPerceptronTrainer](xref:Microsoft.ML.Trainers.AveragedPerceptronTrainer)</span></span>
- <span data-ttu-id="a77e4-110">[FieldAwareFactorizationMachineTrainer](xref:Microsoft.ML.Trainers.FieldAwareFactorizationMachineTrainer);</span><span class="sxs-lookup"><span data-stu-id="a77e4-110">[FieldAwareFactorizationMachineTrainer](xref:Microsoft.ML.Trainers.FieldAwareFactorizationMachineTrainer)</span></span>
- [<span data-ttu-id="a77e4-111">LbfgsLogisticRegressionBinaryTrainer</span><span class="sxs-lookup"><span data-stu-id="a77e4-111">LbfgsLogisticRegressionBinaryTrainer</span></span>](xref:Microsoft.ML.Trainers.LbfgsLogisticRegressionBinaryTrainer)
- [<span data-ttu-id="a77e4-112">LbfgsMaximumEntropyMulticlassTrainer</span><span class="sxs-lookup"><span data-stu-id="a77e4-112">LbfgsMaximumEntropyMulticlassTrainer</span></span>](xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer)
- [<span data-ttu-id="a77e4-113">LbfgsPoissonRegressionTrainer</span><span class="sxs-lookup"><span data-stu-id="a77e4-113">LbfgsPoissonRegressionTrainer</span></span>](xref:Microsoft.ML.Trainers.LbfgsPoissonRegressionTrainer)
- [<span data-ttu-id="a77e4-114">LinearSvmTrainer</span><span class="sxs-lookup"><span data-stu-id="a77e4-114">LinearSvmTrainer</span></span>](xref:Microsoft.ML.Trainers.LinearSvmTrainer)
- <span data-ttu-id="a77e4-115">[OnlineGradientDescentTrainer](xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer);</span><span class="sxs-lookup"><span data-stu-id="a77e4-115">[OnlineGradientDescentTrainer](xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer)</span></span>
- [<span data-ttu-id="a77e4-116">SgdCalibratedTrainer</span><span class="sxs-lookup"><span data-stu-id="a77e4-116">SgdCalibratedTrainer</span></span>](xref:Microsoft.ML.Trainers.SgdCalibratedTrainer)
- [<span data-ttu-id="a77e4-117">SgdNonCalibratedTrainer</span><span class="sxs-lookup"><span data-stu-id="a77e4-117">SgdNonCalibratedTrainer</span></span>](xref:Microsoft.ML.Trainers.SgdNonCalibratedTrainer)
- [<span data-ttu-id="a77e4-118">SymbolicSgdLogisticRegressionBinaryTrainer</span><span class="sxs-lookup"><span data-stu-id="a77e4-118">SymbolicSgdLogisticRegressionBinaryTrainer</span></span>](xref:Microsoft.ML.Trainers.SymbolicSgdLogisticRegressionBinaryTrainer)

## <a name="load-pre-trained-model"></a><span data-ttu-id="a77e4-119">Загрузка предварительно обученной модели</span><span class="sxs-lookup"><span data-stu-id="a77e4-119">Load pre-trained model</span></span>

<span data-ttu-id="a77e4-120">Для начала загрузите обученную ранее модель в свое приложение.</span><span class="sxs-lookup"><span data-stu-id="a77e4-120">First, load the pre-trained model into your application.</span></span> <span data-ttu-id="a77e4-121">Дополнительные сведения о загрузке конвейеров и моделей обучения см. в соответствующей [инструкции](./consuming-model-ml-net.md).</span><span class="sxs-lookup"><span data-stu-id="a77e4-121">To learn more about loading training pipelines and models, see the related [how-to article](./consuming-model-ml-net.md).</span></span>

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

// Define DataViewSchema of data prep pipeline and trained model
DataViewSchema dataPrepPipelineSchema, modelSchema;

// Load data prepration pipeline
ITransformer dataPrepPipeline = mlContext.Model.Load("data_preparation_pipeline.zip", out dataPrepPipelineSchema);

// Load trained model
ITransformer trainedModel = mlContext.Model.Load("ogd_model.zip", out modelSchema);
```

## <a name="extract-pre-trained-model-parameters"></a><span data-ttu-id="a77e4-122">Извлечение параметров обученной ранее модели</span><span class="sxs-lookup"><span data-stu-id="a77e4-122">Extract pre-trained model parameters</span></span>

<span data-ttu-id="a77e4-123">Загрузив модель, извлеките параметры модели через свойство [`Model`](xref:Microsoft.ML.Data.PredictionTransformerBase`1.Model*) обученной ранее модели.</span><span class="sxs-lookup"><span data-stu-id="a77e4-123">Once the model is loaded, extract the learned model parameters by accessing the [`Model`](xref:Microsoft.ML.Data.PredictionTransformerBase`1.Model*) property of the pre-trained model.</span></span> <span data-ttu-id="a77e4-124">Обученная ранее модель была обучена с использованием модели линейной регрессии [`OnlineGradientDescentTrainer`](xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer), которая создает [`RegressionPredictionTransformer`](xref:Microsoft.ML.Data.RegressionPredictionTransformer%601), а тот, в свою очередь, выводит [`LinearRegressionModelParameters`](xref:Microsoft.ML.Trainers.LinearRegressionModelParameters).</span><span class="sxs-lookup"><span data-stu-id="a77e4-124">The pre-trained model was trained using the linear regression model [`OnlineGradientDescentTrainer`](xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer) which creates a[`RegressionPredictionTransformer`](xref:Microsoft.ML.Data.RegressionPredictionTransformer%601) that outputs [`LinearRegressionModelParameters`](xref:Microsoft.ML.Trainers.LinearRegressionModelParameters).</span></span> <span data-ttu-id="a77e4-125">Эти параметры модели линейной регрессии содержат смещение и вес или коэффициенты обученной модели.</span><span class="sxs-lookup"><span data-stu-id="a77e4-125">These linear regression model parameters contain the learned bias and weights or coefficients of the model.</span></span> <span data-ttu-id="a77e4-126">Данные значения станут отправной точкой для переобученной модели.</span><span class="sxs-lookup"><span data-stu-id="a77e4-126">These values will be used as a starting point for the new re-trained model.</span></span>

```csharp
// Extract trained model parameters
LinearRegressionModelParameters originalModelParameters = 
    ((ISingleFeaturePredictionTransformer<object>)trainedModel).Model as LinearRegressionModelParameters;
```

## <a name="re-train-model"></a><span data-ttu-id="a77e4-127">Переобучение модели</span><span class="sxs-lookup"><span data-stu-id="a77e4-127">Re-train model</span></span>

<span data-ttu-id="a77e4-128">Переобучение осуществляется точно так же, как обучение модели.</span><span class="sxs-lookup"><span data-stu-id="a77e4-128">The process for retraining a model is no different than that of training a model.</span></span> <span data-ttu-id="a77e4-129">Единственное отличие заключается в том, что метод [`Fit`](xref:Microsoft.ML.Trainers.OnlineLinearTrainer`2.Fit*), помимо данных, принимает в качестве входных данных параметры обученной модели и использует их как отправную точку в процессе переобучения.</span><span class="sxs-lookup"><span data-stu-id="a77e4-129">The only difference is, the [`Fit`](xref:Microsoft.ML.Trainers.OnlineLinearTrainer`2.Fit*) method in addition to the data also takes as input the original learned model parameters and uses them as a starting point in the re-training process.</span></span>  

```csharp
// New Data
HousingData[] housingData = new HousingData[]
{
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

//Load New Data
IDataView newData = mlContext.Data.LoadFromEnumerable<HousingData>(housingData);

// Preprocess Data
IDataView transformedNewData = dataPrepPipeline.Transform(newData);

// Retrain model
RegressionPredictionTransformer<LinearRegressionModelParameters> retrainedModel = 
    mlContext.Regression.Trainers.OnlineGradientDescent()
        .Fit(transformedNewData, originalModelParameters);
```

## <a name="compare-model-parameters"></a><span data-ttu-id="a77e4-130">Сравнение параметров модели</span><span class="sxs-lookup"><span data-stu-id="a77e4-130">Compare model parameters</span></span>

<span data-ttu-id="a77e4-131">Как узнать, произошло ли переобучение?</span><span class="sxs-lookup"><span data-stu-id="a77e4-131">How do you know if re-training actually happened?</span></span> <span data-ttu-id="a77e4-132">Один из способов — это сравнить параметры переобученной и исходной модели.</span><span class="sxs-lookup"><span data-stu-id="a77e4-132">One way would be to compare whether the re-trained model's parameters are different than those of the original model.</span></span> <span data-ttu-id="a77e4-133">В представленном ниже примере как сравниваются значения веса в исходной и переобученной модели, а результаты выводятся на консоль.</span><span class="sxs-lookup"><span data-stu-id="a77e4-133">The code sample below compares the original against the re-trained model weights and outputs them to the console.</span></span>

```csharp
// Extract Model Parameters of re-trained model
LinearRegressionModelParameters retrainedModelParameters = retrainedModel.Model as LinearRegressionModelParameters;

// Inspect Change in Weights
var weightDiffs = 
    originalModelParameters.Weights.Zip(
        retrainedModelParameters.Weights, (original, retrained) => original - retrained).ToArray();

Console.WriteLine("Original | Retrained | Difference");
for(int i=0;i < weightDiffs.Count();i++)
{
    Console.WriteLine($"{originalModelParameters.Weights[i]} | {retrainedModelParameters.Weights[i]} | {weightDiffs[i]}");
}
```

<span data-ttu-id="a77e4-134">В следующей таблице показано, как могут выглядеть выходные данные.</span><span class="sxs-lookup"><span data-stu-id="a77e4-134">The table below shows what the output might look like.</span></span> 

|<span data-ttu-id="a77e4-135">До преобразования</span><span class="sxs-lookup"><span data-stu-id="a77e4-135">Original</span></span> | <span data-ttu-id="a77e4-136">Переобученная модель</span><span class="sxs-lookup"><span data-stu-id="a77e4-136">Retrained</span></span> | <span data-ttu-id="a77e4-137">Различие</span><span class="sxs-lookup"><span data-stu-id="a77e4-137">Difference</span></span> |
|---|---|---|
| <span data-ttu-id="a77e4-138">33 039,86</span><span class="sxs-lookup"><span data-stu-id="a77e4-138">33039.86</span></span> | <span data-ttu-id="a77e4-139">56 293,76</span><span class="sxs-lookup"><span data-stu-id="a77e4-139">56293.76</span></span> | <span data-ttu-id="a77e4-140">–23 253,9</span><span class="sxs-lookup"><span data-stu-id="a77e4-140">-23253.9</span></span> |
| <span data-ttu-id="a77e4-141">29 099,14</span><span class="sxs-lookup"><span data-stu-id="a77e4-141">29099.14</span></span> | <span data-ttu-id="a77e4-142">49 586,03</span><span class="sxs-lookup"><span data-stu-id="a77e4-142">49586.03</span></span> | <span data-ttu-id="a77e4-143">–20 486,89</span><span class="sxs-lookup"><span data-stu-id="a77e4-143">-20486.89</span></span> |
| <span data-ttu-id="a77e4-144">28 938,38</span><span class="sxs-lookup"><span data-stu-id="a77e4-144">28938.38</span></span> | <span data-ttu-id="a77e4-145">48 609,23</span><span class="sxs-lookup"><span data-stu-id="a77e4-145">48609.23</span></span> | <span data-ttu-id="a77e4-146">–19 670,85</span><span class="sxs-lookup"><span data-stu-id="a77e4-146">-19670.85</span></span> |
| <span data-ttu-id="a77e4-147">30 484,02</span><span class="sxs-lookup"><span data-stu-id="a77e4-147">30484.02</span></span> | <span data-ttu-id="a77e4-148">53 745,43</span><span class="sxs-lookup"><span data-stu-id="a77e4-148">53745.43</span></span> | <span data-ttu-id="a77e4-149">–23 261,41</span><span class="sxs-lookup"><span data-stu-id="a77e4-149">-23261.41</span></span> |
