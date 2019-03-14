---
title: Использование PredictionEngine для поочередного прогнозирования в ML.NET
description: Узнайте, как использовать PredictionEngine для поочередного прогнозирования в ML.NET
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 68837888c53409b4249bbece481888fb4167a5ca
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/08/2019
ms.locfileid: "57673812"
---
# <a name="use-the-predictionengine-to-make-one-prediction-at-a-time---mlnet"></a><span data-ttu-id="271c5-103">Использование PredictionEngine для поочередного прогнозирования в ML.NET</span><span class="sxs-lookup"><span data-stu-id="271c5-103">Use the PredictionEngine to make one prediction at a time - ML.NET</span></span> 

> [!NOTE]
> <span data-ttu-id="271c5-104">В этом разделе описано, как использовать платформу ML.NET, которая сейчас доступна в режиме предварительной версии. Этот материал может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="271c5-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="271c5-105">Дополнительные сведения см. в [обзоре ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="271c5-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="271c5-106">Сейчас в этих инструкциях и примере используется **ML.NET версии 0.10**.</span><span class="sxs-lookup"><span data-stu-id="271c5-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="271c5-107">Дополнительные сведения см. в заметках о выпуске в [репозитории GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="271c5-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="271c5-108">Так как любая модель ML.NET является преобразователем, используйте `model.Transform` для применения модели к `DataView` для создания прогнозов.</span><span class="sxs-lookup"><span data-stu-id="271c5-108">Since any ML.NET model is a transformer, you use `model.Transform` to apply the model to the `DataView` to make predictions.</span></span> 

<span data-ttu-id="271c5-109">Но чаще бывает так, что набор данных для прогнозирования отсутствует, и вместо этого вы получаете один пример за раз.</span><span class="sxs-lookup"><span data-stu-id="271c5-109">A more typical case, though, is when there is no 'dataset' that you want to predict on, but instead you receive one example at a time.</span></span> <span data-ttu-id="271c5-110">Например, вы можете запустить модель как часть веб-сайта ASP.NET и создать прогноз для входящего запроса HTTP.</span><span class="sxs-lookup"><span data-stu-id="271c5-110">For instance, you run the model as part of your ASP.NET website, and need to make a prediction for an incoming HTTP request.</span></span>

<span data-ttu-id="271c5-111">`PredictionEngine` выполняет один пример за раз с использованием конвейера прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="271c5-111">The `PredictionEngine` runs one example at a time through the prediction pipeline.</span></span>

<span data-ttu-id="271c5-112">Ниже приведен полный пример использования готовой модели прогнозирования на основе набора данных Iris:</span><span class="sxs-lookup"><span data-stu-id="271c5-112">Here is the full example using a prebuilt Iris prediction dataset model:</span></span>

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Step one: read the data as an IDataView.
// First, we define the reader: specify the data columns and where to find them in the text file.
var reader = mlContext.Data.CreateTextLoader(
    columns: new TextLoader.Column[]
    {
        // The four features of the Iris dataset will be grouped together as one Features column.
        new TextLoader.Column("SepalLength",DataKind.R4,0),
        new TextLoader.Column("SepalWidth",DataKind.R4,1),
        new TextLoader.Column("PetalLength",DataKind.R4,2),
        new TextLoader.Column("PetalWidth",DataKind.R4,3),
        // Label: kind of iris.
        new TextLoader.Column("Label",DataKind.TX,4)
    },
    separatorChar: ',',
    hasHeader: true
);

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
    .Append(mlContext.Transforms.Conversion.MapKeyToValue(("Data", "PredictedLabel")));

// Train the model.
var model = pipeline.Fit(trainData);
```

<span data-ttu-id="271c5-113">Чтобы применить [понимание схемы](https://github.com/dotnet/machinelearning/blob/master/docs/code/SchemaComprehension.md) для прогнозирования, определите пару классов следующим образом:</span><span class="sxs-lookup"><span data-stu-id="271c5-113">To use [schema comprehension](https://github.com/dotnet/machinelearning/blob/master/docs/code/SchemaComprehension.md) for prediction, define a pair of classes like the following:</span></span>

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

<span data-ttu-id="271c5-114">Код прогнозирования теперь выглядит так:</span><span class="sxs-lookup"><span data-stu-id="271c5-114">The prediction code now looks as follows:</span></span>

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
