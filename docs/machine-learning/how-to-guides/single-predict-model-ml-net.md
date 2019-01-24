---
title: Использование PredictionEngine для поочередного прогнозирования в ML.NET
description: Узнайте, как использовать PredictionEngine для поочередного прогнозирования в ML.NET
ms.date: 01/15/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 0b3f60038fe7f49ffbff3c63fd2862ba67adb506
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333646"
---
# <a name="use-the-predictionengine-to-make-one-prediction-at-a-time---mlnet"></a><span data-ttu-id="c8224-103">Использование PredictionEngine для поочередного прогнозирования в ML.NET</span><span class="sxs-lookup"><span data-stu-id="c8224-103">Use the PredictionEngine to make one prediction at a time - ML.NET</span></span> 

<span data-ttu-id="c8224-104">Так как любая модель ML.NET является преобразователем, используйте `model.Transform` для применения модели к `DataView` для создания прогнозов.</span><span class="sxs-lookup"><span data-stu-id="c8224-104">Since any ML.NET model is a transformer, you use `model.Transform` to apply the model to the `DataView` to make predictions.</span></span> 

<span data-ttu-id="c8224-105">Но чаще бывает так, что набор данных для прогнозирования отсутствует, и вместо этого вы получаете один пример за раз.</span><span class="sxs-lookup"><span data-stu-id="c8224-105">A more typical case, though, is when there is no 'dataset' that you want to predict on, but instead you receive one example at a time.</span></span> <span data-ttu-id="c8224-106">Например, вы можете запустить модель как часть веб-сайта ASP.NET и создать прогноз для входящего запроса HTTP.</span><span class="sxs-lookup"><span data-stu-id="c8224-106">For instance, you run the model as part of your ASP.NET website, and need to make a prediction for an incoming HTTP request.</span></span>

<span data-ttu-id="c8224-107">`PredictionEngine` выполняет один пример за раз с использованием конвейера прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="c8224-107">The `PredictionEngine` runs one example at a time through the prediction pipeline.</span></span>

<span data-ttu-id="c8224-108">Ниже приведен полный пример использования готовой модели прогнозирования на основе набора данных Iris:</span><span class="sxs-lookup"><span data-stu-id="c8224-108">Here is the full example using a prebuilt Iris prediction dataset model:</span></span>

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Step one: read the data as an IDataView.
// First, we define the reader: specify the data columns and where to find them in the text file.
var reader = mlContext.Data.CreateTextReader(new TextLoader.Arguments
{
    Column = new[] {
        new TextLoader.Column("SepalLength", DataKind.R4, 0),
        new TextLoader.Column("SepalWidth", DataKind.R4, 1),
        new TextLoader.Column("PetalLength", DataKind.R4, 2),
        new TextLoader.Column("PetalWidth", DataKind.R4, 3),
        // Label: kind of iris.
        new TextLoader.Column("Label", DataKind.TX, 4),
    },
    // Default separator is tab, but the dataset has comma.
    Separator = ","
});

// Retrieve the training data.
var trainData = reader.Read(irisDataPath);

// Build the training pipeline.
var pipeline =
    // Concatenate all the features together into one column 'Features'.
    mlContext.Transforms.Concatenate("Features", "SepalLength", "SepalWidth", "PetalLength", "PetalWidth")
    // Note that the label is text, so it needs to be converted to key.
    .Append(mlContext.Transforms.Categorical.MapValueToKey("Label"), TransformerScope.TrainTest)
    // Use the multi-class SDCA model to predict the label using features.
    .Append(mlContext.MulticlassClassification.Trainers.StochasticDualCoordinateAscent())
    // Apply the inverse conversion from 'PredictedLabel' column back to string value.
    .Append(mlContext.Transforms.Conversion.MapKeyToValue(("PredictedLabel", "Data")));

// Train the model.
var model = pipeline.Fit(trainData);
```

<span data-ttu-id="c8224-109">Чтобы применить [понимание схемы](https://github.com/dotnet/machinelearning/blob/master/docs/code/SchemaComprehension.md) для прогнозирования, определите пару классов следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c8224-109">To use [schema comprehension](https://github.com/dotnet/machinelearning/blob/master/docs/code/SchemaComprehension.md) for prediction, define a pair of classes like the following:</span></span>

```csharp
private class IrisInput
{
    // Unfortunately, we still need the dummy 'Label' column to be present.
    [ColumnName("Label")]
    public string IgnoredLabel { get; set; }
    public float SepalLength { get; set; }
    public float SepalWidth { get; set; }
    public float PetalLength { get; set; }
    public float PetalWidth { get; set; }
}

private class IrisPrediction
{
    [ColumnName("Data")]
    public string PredictedClass { get; set; }
}
```

<span data-ttu-id="c8224-110">Код прогнозирования теперь выглядит так:</span><span class="sxs-lookup"><span data-stu-id="c8224-110">The prediction code now looks as follows:</span></span>

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Use the model for one-time prediction.
// Make the prediction function object. Note that, on average, this call takes around 200x longer
// than one prediction, so you might want to cache and reuse the prediction engine, instead of
// creating one per prediction.
var predictionEngine = model.CreatePredictionEngine<IrisInput, IrisPrediction>(mlContext);

// Obtain the prediction. Remember that 'Predict' is not reentrant. If you want to use multiple threads
// for simultaneous prediction, make sure each thread is using its own PredictionEngine.
var prediction = predictionEngine.Predict(new IrisInput
{
    SepalLength = 4.1f,
    SepalWidth = 0.1f,
    PetalLength = 3.2f,
    PetalWidth = 1.4f
});
```
