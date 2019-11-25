---
title: Сохранение и загрузка обученных моделей
description: Узнайте, как сохранять и загружать обученные модели
ms.date: 05/03/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: e3cebe979b5c279ce8cb90db5510f8758c24c2b4
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976999"
---
# <a name="save-and-load-trained-models"></a><span data-ttu-id="114b7-103">Сохранение и загрузка обученных моделей</span><span class="sxs-lookup"><span data-stu-id="114b7-103">Save and load trained models</span></span>

<span data-ttu-id="114b7-104">Узнайте, как сохранять и загружать в приложение обученные модели.</span><span class="sxs-lookup"><span data-stu-id="114b7-104">Learn how to save and load trained models in your application.</span></span>

<span data-ttu-id="114b7-105">В процессе создания модель находится в памяти и доступна на протяжении всего жизненного цикла приложения.</span><span class="sxs-lookup"><span data-stu-id="114b7-105">Throughout the model building process, a model lives in memory and is accessible throughout the application's lifecycle.</span></span> <span data-ttu-id="114b7-106">Однако, если приложение прекращает работу, а модель не сохранена ни на локальном компьютере, ни на удаленном ресурсе, она станет недоступна.</span><span class="sxs-lookup"><span data-stu-id="114b7-106">However, once the application stops running, if the model is not saved somewhere locally or remotely, it's no longer accessible.</span></span> <span data-ttu-id="114b7-107">Обычно модели используются после обучения в других приложениях для вывода либо для переобучения.</span><span class="sxs-lookup"><span data-stu-id="114b7-107">Typically models are used at some point after training in other applications either for inference or re-training.</span></span> <span data-ttu-id="114b7-108">В связи с этим модель необходимо сохранять.</span><span class="sxs-lookup"><span data-stu-id="114b7-108">Therefore, it's important to store the model.</span></span> <span data-ttu-id="114b7-109">Сохраняйте и загружайте модели, выполняя действия, описанные в последующих разделах этого документа, при использовании конвейеров подготовки данных и обучения модели, подобных описанному ниже.</span><span class="sxs-lookup"><span data-stu-id="114b7-109">Save and load models using the steps described in subsequent sections of this document when using data preparation and model training pipelines like the one detailed below.</span></span> <span data-ttu-id="114b7-110">Несмотря на то что в этом примере используется модель линейной регрессии, такая же процедура подходит и для других алгоритмов ML.NET.</span><span class="sxs-lookup"><span data-stu-id="114b7-110">Although this sample uses a linear regression model, the same process applies to other ML.NET algorithms.</span></span>

```csharp
HousingData[] housingData = new HousingData[]
{
    new HousingData
    {
        Size = 600f,
        HistoricalPrices = new float[] { 100000f, 125000f, 122000f },
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
    }
};

// Create MLContext
MLContext mlContext = new MLContext();

// Load Data
IDataView data = mlContext.Data.LoadFromEnumerable<HousingData>(housingData);

// Define data preparation estimator
EstimatorChain<RegressionPredictionTransformer<LinearRegressionModelParameters>> pipelineEstimator =
    mlContext.Transforms.Concatenate("Features", new string[] { "Size", "HistoricalPrices" })
        .Append(mlContext.Transforms.NormalizeMinMax("Features"))
        .Append(mlContext.Regression.Trainers.Sdca());

// Train model
ITransformer trainedModel = pipelineEstimator.Fit(data);

// Save model
mlContext.Model.Save(trainedModel, data.Schema, "model.zip");
```

<span data-ttu-id="114b7-111">Поскольку большинство моделей и конвейеров подготовки наследуется из одного и того же набора классов, подписи методов сохранения и загрузки для этих компонентов будут одинаковы.</span><span class="sxs-lookup"><span data-stu-id="114b7-111">Because most models and data preparation pipelines inherit from the same set of classes, the save and load method signatures for these components is the same.</span></span> <span data-ttu-id="114b7-112">В зависимости от варианта использования можно либо объединить конвейер подготовки данных и модель в единый объект [`EstimatorChain`](xref:Microsoft.ML.Data.TransformerChain%601), который выдаст один [`ITransformer`](xref:Microsoft.ML.ITransformer), или разделить их и создать таким образом для каждого отдельный [`ITransformer`](xref:Microsoft.ML.ITransformer).</span><span class="sxs-lookup"><span data-stu-id="114b7-112">Depending on your use case, you can either combine the data preparation pipeline and model into a single [`EstimatorChain`](xref:Microsoft.ML.Data.TransformerChain%601) which would output a single [`ITransformer`](xref:Microsoft.ML.ITransformer) or separate them thus creating a separate [`ITransformer`](xref:Microsoft.ML.ITransformer) for each.</span></span>

## <a name="save-a-model-locally"></a><span data-ttu-id="114b7-113">Сохранение модели на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="114b7-113">Save a model locally</span></span>

<span data-ttu-id="114b7-114">При сохранении модели нужны две вещи:</span><span class="sxs-lookup"><span data-stu-id="114b7-114">When saving a model you need two things:</span></span>

1. <span data-ttu-id="114b7-115">[`ITransformer`](xref:Microsoft.ML.ITransformer) модели;</span><span class="sxs-lookup"><span data-stu-id="114b7-115">The [`ITransformer`](xref:Microsoft.ML.ITransformer) of the model.</span></span>
2. <span data-ttu-id="114b7-116">[`DataViewSchema`](xref:Microsoft.ML.DataViewSchema) ожидаемых входных данных [`ITransformer`](xref:Microsoft.ML.ITransformer).</span><span class="sxs-lookup"><span data-stu-id="114b7-116">The [`DataViewSchema`](xref:Microsoft.ML.DataViewSchema) of the [`ITransformer`](xref:Microsoft.ML.ITransformer)'s expected input.</span></span>

<span data-ttu-id="114b7-117">После обучения модели вызовите метод [`Save`](xref:Microsoft.ML.ModelOperationsCatalog.Save*), чтобы сохранить обученную модель в файл с именем `model.zip`, используя `DataViewSchema` входных данных.</span><span class="sxs-lookup"><span data-stu-id="114b7-117">After training the model, use the [`Save`](xref:Microsoft.ML.ModelOperationsCatalog.Save*) method to save the trained model to a file called `model.zip` using the `DataViewSchema` of the input data.</span></span>

```csharp
// Save Trained Model
mlContext.Model.Save(trainedModel, data.Schema, "model.zip");
```

## <a name="load-a-model-stored-locally"></a><span data-ttu-id="114b7-118">Загрузка модели, сохраненной на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="114b7-118">Load a model stored locally</span></span>

<span data-ttu-id="114b7-119">Модели, сохраненные на локальном компьютере, можно использовать в других процессах или приложениях, таких как `ASP.NET Core` и `Serverless Web Applications`.</span><span class="sxs-lookup"><span data-stu-id="114b7-119">Models stored locally can be used in other processes or applications like `ASP.NET Core` and `Serverless Web Applications`.</span></span> <span data-ttu-id="114b7-120">Дополнительные сведения см. в статьях [Использование ML.NET в веб-API](./serve-model-web-api-ml-net.md) и [Развертывание бессерверного веб-приложения ML.NET](./serve-model-serverless-azure-functions-ml-net.md).</span><span class="sxs-lookup"><span data-stu-id="114b7-120">See [Use ML.NET in Web API](./serve-model-web-api-ml-net.md) and [Deploy ML.NET Serverless Web App](./serve-model-serverless-azure-functions-ml-net.md) how-to articles to learn more.</span></span>

<span data-ttu-id="114b7-121">В отдельном приложении или процессе вызовите метод [`Load`](xref:Microsoft.ML.ModelOperationsCatalog.Load*) с указанием пути к файлу, чтобы загрузить в приложение обученную модель.</span><span class="sxs-lookup"><span data-stu-id="114b7-121">In a separate application or process, use the [`Load`](xref:Microsoft.ML.ModelOperationsCatalog.Load*) method along with the file path to get the trained model into your application.</span></span>

```csharp
//Define DataViewSchema for data preparation pipeline and trained model
DataViewSchema modelSchema;

// Load trained model
ITransformer trainedModel = mlContext.Model.Load("model.zip", out modelSchema);
```

## <a name="load-a-model-stored-remotely"></a><span data-ttu-id="114b7-122">Загрузка модели, сохраненной на удаленном ресурсе</span><span class="sxs-lookup"><span data-stu-id="114b7-122">Load a model stored remotely</span></span>

<span data-ttu-id="114b7-123">Чтобы загрузить в приложение конвейеры подготовки данных и модели, сохраненные на удаленном ресурсе, вместо пути к файлу укажите [`Stream`](xref:System.IO.Stream) в методе [`Load`](xref:Microsoft.ML.ModelOperationsCatalog.Load*).</span><span class="sxs-lookup"><span data-stu-id="114b7-123">To load data preparation pipelines and models stored in a remote location into your application, use a [`Stream`](xref:System.IO.Stream) instead of a file path in the [`Load`](xref:Microsoft.ML.ModelOperationsCatalog.Load*) method.</span></span>

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

// Define DataViewSchema and ITransformers
DataViewSchema modelSchema;
ITransformer trainedModel;

// Load data prep pipeline and trained model
using (HttpClient client = new HttpClient())
{
    Stream modelFile = await client.GetStreamAsync("<YOUR-REMOTE-FILE-LOCATION>");

    trainedModel = mlContext.Model.Load(modelFile, out modelSchema);
}
```

## <a name="working-with-separate-data-preparation-and-model-pipelines"></a><span data-ttu-id="114b7-124">Работа с отдельными конвейерами подготовки данных и модели</span><span class="sxs-lookup"><span data-stu-id="114b7-124">Working with separate data preparation and model pipelines</span></span>

> [!NOTE]
> <span data-ttu-id="114b7-125">Работать с отдельными конвейерами подготовки данных и обучения модели необязательно.</span><span class="sxs-lookup"><span data-stu-id="114b7-125">Working with separate data preparation and model training pipelines is optional.</span></span> <span data-ttu-id="114b7-126">Отделение конвейеров упрощает проверку параметров обученной модели.</span><span class="sxs-lookup"><span data-stu-id="114b7-126">Separation of pipelines makes it easier to inspect the learned model parameters.</span></span> <span data-ttu-id="114b7-127">Для создания прогнозов проще сохранять и загружать единый конвейер, который включает операции подготовки данных и обучения модели.</span><span class="sxs-lookup"><span data-stu-id="114b7-127">For predictions, it's easier to save and load a single pipeline that includes the data preparation and model training operations.</span></span>

<span data-ttu-id="114b7-128">При работе с отдельными конвейерами подготовки данных и моделей применяется тот же порядок действий, что и при работе с единым конвейером за тем исключением, что оба конвейера должны сохраняться и загружаться одновременно.</span><span class="sxs-lookup"><span data-stu-id="114b7-128">When working with separate data preparation pipelines and models, the same process as single pipelines applies; except now both pipelines need to be saved and loaded simultaneously.</span></span>

<span data-ttu-id="114b7-129">Допустим, у нас есть отдельные конвейеры подготовки данных и обучения модели:</span><span class="sxs-lookup"><span data-stu-id="114b7-129">Given separate data preparation and model training pipelines:</span></span>

```csharp
// Define data preparation estimator
IEstimator<ITransformer> dataPrepEstimator =
    mlContext.Transforms.Concatenate("Features", new string[] { "Size", "HistoricalPrices" })
        .Append(mlContext.Transforms.NormalizeMinMax("Features"));

// Create data preparation transformer
ITransformer dataPrepTransformer = dataPrepEstimator.Fit(data);

// Define StochasticDualCoordinateAscent regression algorithm estimator
var sdcaEstimator = mlContext.Regression.Trainers.Sdca();

// Pre-process data using data prep operations
IDataView transformedData = dataPrepTransformer.Transform(data);

// Train regression model
RegressionPredictionTransformer<LinearRegressionModelParameters> trainedModel = sdcaEstimator.Fit(transformedData);
```

### <a name="save-data-preparation-pipeline-and-trained-model"></a><span data-ttu-id="114b7-130">Сохранение конвейера подготовки данных и обученной модели</span><span class="sxs-lookup"><span data-stu-id="114b7-130">Save data preparation pipeline and trained model</span></span>

<span data-ttu-id="114b7-131">Чтобы сохранить и конвейер подготовки данных, и обученную модель, используйте следующие команды:</span><span class="sxs-lookup"><span data-stu-id="114b7-131">To save both the data preparation pipeline and trained model, use the following commands:</span></span>

```csharp
// Save Data Prep transformer
mlContext.Model.Save(dataPrepTransformer, data.Schema, "data_preparation_pipeline.zip");

// Save Trained Model
mlContext.Model.Save(trainedModel, transformedData.Schema, "model.zip");
```

### <a name="load-data-preparation-pipeline-and-trained-model"></a><span data-ttu-id="114b7-132">Загрузка конвейера подготовки данных и обученной модели</span><span class="sxs-lookup"><span data-stu-id="114b7-132">Load data preparation pipeline and trained model</span></span>

<span data-ttu-id="114b7-133">Для одновременной загрузки конвейера подготовки данных и обученной модели в отдельный процесс или приложение используйте следующие команды:</span><span class="sxs-lookup"><span data-stu-id="114b7-133">In a separate process or application, load the data preparation pipeline and trained model simultaneously as follows:</span></span>

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

// Define data preparation and trained model schemas
DataViewSchema dataPrepPipelineSchema, modelSchema;

// Load data preparation pipeline and trained model
ITransformer dataPrepPipeline = mlContext.Model.Load("data_preparation_pipeline.zip",out dataPrepPipelineSchema);
ITransformer trainedModel = mlContext.Model.Load("model.zip", out modelSchema);
```
