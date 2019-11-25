---
title: Прогнозирование с помощью обученной модели
description: Сведения о прогнозировании с помощью обученной модели
ms.date: 09/18/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 182350cc5143155133385c6fd77986b271f6db91
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73977047"
---
# <a name="make-predictions-with-a-trained-model"></a><span data-ttu-id="24a6a-103">Прогнозирование с помощью обученной модели</span><span class="sxs-lookup"><span data-stu-id="24a6a-103">Make predictions with a trained model</span></span>

<span data-ttu-id="24a6a-104">Сведения об использовании обученной модели для прогнозирования</span><span class="sxs-lookup"><span data-stu-id="24a6a-104">Learn how to use a trained model to make predictions</span></span>

## <a name="create-data-models"></a><span data-ttu-id="24a6a-105">Создание моделей данных</span><span class="sxs-lookup"><span data-stu-id="24a6a-105">Create data models</span></span>

### <a name="input-data"></a><span data-ttu-id="24a6a-106">Входные данные</span><span class="sxs-lookup"><span data-stu-id="24a6a-106">Input data</span></span>

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

### <a name="output-data"></a><span data-ttu-id="24a6a-107">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="24a6a-107">Output data</span></span>

<span data-ttu-id="24a6a-108">Как в случае с именами входных столбцов `Features` и `Label`, ML.NET использует имена по умолчанию для столбцов прогнозируемых значений, создаваемых моделью.</span><span class="sxs-lookup"><span data-stu-id="24a6a-108">Like the `Features` and `Label` input column names, ML.NET has default names for the predicted value columns produced by a model.</span></span> <span data-ttu-id="24a6a-109">Имя может отличаться в зависимости от задачи.</span><span class="sxs-lookup"><span data-stu-id="24a6a-109">Depending on the task the name may differ.</span></span>

<span data-ttu-id="24a6a-110">Так как в этом примере используется алгоритм линейной регрессии, имя по умолчанию выходного столбца имеет значение `Score`, которое определяется атрибутом [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) в свойстве `PredictedPrice`.</span><span class="sxs-lookup"><span data-stu-id="24a6a-110">Because the algorithm used in this sample is a linear regression algorithm, the default name of the output column is `Score` which is defined by the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute on the `PredictedPrice` property.</span></span>

```csharp
class HousingPrediction
{
    [ColumnName("Score")]
    public float PredictedPrice { get; set; }
}
```

## <a name="set-up-a-prediction-pipeline"></a><span data-ttu-id="24a6a-111">Настройка конвейера прогнозирования</span><span class="sxs-lookup"><span data-stu-id="24a6a-111">Set up a prediction pipeline</span></span>

<span data-ttu-id="24a6a-112">Выполняется ли отдельный или пакетный прогноз, конвейер прогнозирования нужно загрузить в приложение.</span><span class="sxs-lookup"><span data-stu-id="24a6a-112">Whether making a single or batch prediction, the prediction pipeline needs to be loaded into the application.</span></span> <span data-ttu-id="24a6a-113">Этот конвейер содержит как преобразования для предварительной обработки данных, так и обученную модель.</span><span class="sxs-lookup"><span data-stu-id="24a6a-113">This pipeline contains both the data pre-processing transformations as well as the trained model.</span></span> <span data-ttu-id="24a6a-114">Приведенный ниже фрагмент кода загружает конвейер прогнозирования из файла с именем `model.zip`.</span><span class="sxs-lookup"><span data-stu-id="24a6a-114">The code snippet below loads the prediction pipeline from a file named `model.zip`.</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

// Load Trained Model
DataViewSchema predictionPipelineSchema;
ITransformer predictionPipeline = mlContext.Model.Load("model.zip", out predictionPipelineSchema);
```

## <a name="single-prediction"></a><span data-ttu-id="24a6a-115">Отдельный прогноз</span><span class="sxs-lookup"><span data-stu-id="24a6a-115">Single prediction</span></span>

<span data-ttu-id="24a6a-116">Чтобы создать отдельный прогноз, создайте [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) с помощью загруженного конвейера прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="24a6a-116">To make a single prediction, create a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) using the loaded prediction pipeline.</span></span>

```csharp
// Create PredictionEngines
PredictionEngine<HousingData, HousingPrediction> predictionEngine = mlContext.Model.CreatePredictionEngine<HousingData, HousingPrediction>(predictionPipeline);
```

<span data-ttu-id="24a6a-117">Затем с помощью метода [`Predict`](xref:Microsoft.ML.PredictionEngineBase%602.Predict*) передайте входные данные как параметр.</span><span class="sxs-lookup"><span data-stu-id="24a6a-117">Then, use the [`Predict`](xref:Microsoft.ML.PredictionEngineBase%602.Predict*) method and pass in your input data as a parameter.</span></span> <span data-ttu-id="24a6a-118">Обратите внимание, что для использования метода [`Predict`](xref:Microsoft.ML.PredictionEngineBase%602.Predict*) не нужно, чтобы входные данные были [`IDataView`](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="24a6a-118">Notice that using the [`Predict`](xref:Microsoft.ML.PredictionEngineBase%602.Predict*) method does not require the input to be an [`IDataView`](xref:Microsoft.ML.IDataView)).</span></span> <span data-ttu-id="24a6a-119">Это обусловлено тем, что он беспрепятственно осуществляет внутреннюю обработку типов входных данных, чтобы вы могли передать объект типа входных данных.</span><span class="sxs-lookup"><span data-stu-id="24a6a-119">This is because it conveniently internalizes the input data type manipulation so you can pass in an object of the input data type.</span></span> <span data-ttu-id="24a6a-120">Кроме того, так как `CurrentPrice` является целью или меткой, которую вы пытаетесь спрогнозировать с помощью новых данных, предполагается, что на данный момент значения для него нет.</span><span class="sxs-lookup"><span data-stu-id="24a6a-120">Additionally, since `CurrentPrice` is the target or label you're trying to predict using new data, it's assumed there is no value for it at the moment.</span></span>

```csharp
// Input Data
HousingData inputData = new HousingData
{
    Size = 900f,
    HistoricalPrices = new float[] { 155000f, 190000f, 220000f }
};

// Get Prediction
HousingPrediction prediction = predictionEngine.Predict(inputData);
```

<span data-ttu-id="24a6a-121">При обращении к свойству `Score` объекта `prediction` вы должны получить значение, аналогичное `150079`.</span><span class="sxs-lookup"><span data-stu-id="24a6a-121">If you access the `Score` property of the `prediction` object, you should get a value similar to `150079`.</span></span>

## <a name="multiple-predictions"></a><span data-ttu-id="24a6a-122">Множественное прогнозирование</span><span class="sxs-lookup"><span data-stu-id="24a6a-122">Multiple predictions</span></span>

<span data-ttu-id="24a6a-123">Получив следующие данные, загрузите их в [`IDataView`](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="24a6a-123">Given the following data, load it into an [`IDataView`](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="24a6a-124">В этом случае имя [`IDataView`](xref:Microsoft.ML.IDataView) — `inputData`.</span><span class="sxs-lookup"><span data-stu-id="24a6a-124">In this case, the name of the [`IDataView`](xref:Microsoft.ML.IDataView) is `inputData`.</span></span> <span data-ttu-id="24a6a-125">Так как `CurrentPrice` является целью или меткой, которую вы пытаетесь спрогнозировать с помощью новых данных, предполагается, что на данный момент значения для него нет.</span><span class="sxs-lookup"><span data-stu-id="24a6a-125">Because `CurrentPrice` is the target or label you're trying to predict using new data, it's assumed there is no value for it at the moment.</span></span>

```csharp
// Actual data
HousingData[] housingData = new HousingData[]
{
    new HousingData
    {
        Size = 850f,
        HistoricalPrices = new float[] { 150000f, 175000f, 210000f }
    },
    new HousingData
    {
        Size = 900f,
        HistoricalPrices = new float[] { 155000f, 190000f, 220000f }
    },
    new HousingData
    {
        Size = 550f,
        HistoricalPrices = new float[] { 99000f, 98000f, 130000f }
    }
};
```

<span data-ttu-id="24a6a-126">Затем воспользуйтесь методом [`Transform`](xref:Microsoft.ML.ITransformer.Transform*), чтобы применить преобразования данных и сформировать прогнозы.</span><span class="sxs-lookup"><span data-stu-id="24a6a-126">Then, use the [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) method to apply the data transformations and generate predictions.</span></span>

```csharp
// Predicted Data
IDataView predictions = predictionPipeline.Transform(inputData);
```

<span data-ttu-id="24a6a-127">Проверьте прогнозируемые значения с помощью метода [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*).</span><span class="sxs-lookup"><span data-stu-id="24a6a-127">Inspect the predicted values by using the [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*) method.</span></span>

```csharp
// Get Predictions
float[] scoreColumn = predictions.GetColumn<float>("Score").ToArray();
```

<span data-ttu-id="24a6a-128">Прогнозируемые значения в столбце оценки должны выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="24a6a-128">The predicted values in the score column should look like the following:</span></span>

| <span data-ttu-id="24a6a-129">Наблюдение</span><span class="sxs-lookup"><span data-stu-id="24a6a-129">Observation</span></span> | <span data-ttu-id="24a6a-130">Прогноз</span><span class="sxs-lookup"><span data-stu-id="24a6a-130">Prediction</span></span> |
|---|---|
| <span data-ttu-id="24a6a-131">1</span><span class="sxs-lookup"><span data-stu-id="24a6a-131">1</span></span> | <span data-ttu-id="24a6a-132">144 638,2</span><span class="sxs-lookup"><span data-stu-id="24a6a-132">144638.2</span></span> |
| <span data-ttu-id="24a6a-133">2</span><span class="sxs-lookup"><span data-stu-id="24a6a-133">2</span></span> | <span data-ttu-id="24a6a-134">150 079,4</span><span class="sxs-lookup"><span data-stu-id="24a6a-134">150079.4</span></span> |
| <span data-ttu-id="24a6a-135">3</span><span class="sxs-lookup"><span data-stu-id="24a6a-135">3</span></span> | <span data-ttu-id="24a6a-136">107 789,8</span><span class="sxs-lookup"><span data-stu-id="24a6a-136">107789.8</span></span> |
