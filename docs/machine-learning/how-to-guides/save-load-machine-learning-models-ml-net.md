---
title: Сохранение и загрузка обученных моделей
description: Узнайте, как сохранять и загружать обученные модели
ms.date: 05/03/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: e3cebe979b5c279ce8cb90db5510f8758c24c2b4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73976999"
---
# <a name="save-and-load-trained-models"></a>Сохранение и загрузка обученных моделей

Узнайте, как сохранять и загружать в приложение обученные модели.

В процессе создания модель находится в памяти и доступна на протяжении всего жизненного цикла приложения. Однако, если приложение прекращает работу, а модель не сохранена ни на локальном компьютере, ни на удаленном ресурсе, она станет недоступна. Обычно модели используются после обучения в других приложениях для вывода либо для переобучения. В связи с этим модель необходимо сохранять. Сохраняйте и загружайте модели, выполняя действия, описанные в последующих разделах этого документа, при использовании конвейеров подготовки данных и обучения модели, подобных описанному ниже. Несмотря на то что в этом примере используется модель линейной регрессии, такая же процедура подходит и для других алгоритмов ML.NET.

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

Поскольку большинство моделей и конвейеров подготовки наследуется из одного и того же набора классов, подписи методов сохранения и загрузки для этих компонентов будут одинаковы. В зависимости от варианта использования можно либо объединить конвейер подготовки данных и модель в единый объект [`EstimatorChain`](xref:Microsoft.ML.Data.TransformerChain%601), который выдаст один [`ITransformer`](xref:Microsoft.ML.ITransformer), или разделить их и создать таким образом для каждого отдельный [`ITransformer`](xref:Microsoft.ML.ITransformer).

## <a name="save-a-model-locally"></a>Сохранение модели на локальном компьютере

При сохранении модели нужны две вещи:

1. [`ITransformer`](xref:Microsoft.ML.ITransformer) модели;
2. [`DataViewSchema`](xref:Microsoft.ML.DataViewSchema) ожидаемых входных данных [`ITransformer`](xref:Microsoft.ML.ITransformer).

После обучения модели вызовите метод [`Save`](xref:Microsoft.ML.ModelOperationsCatalog.Save*), чтобы сохранить обученную модель в файл с именем `model.zip`, используя `DataViewSchema` входных данных.

```csharp
// Save Trained Model
mlContext.Model.Save(trainedModel, data.Schema, "model.zip");
```

## <a name="load-a-model-stored-locally"></a>Загрузка модели, сохраненной на локальном компьютере

Модели, сохраненные на локальном компьютере, можно использовать в других процессах или приложениях, таких как `ASP.NET Core` и `Serverless Web Applications`. Дополнительные сведения см. в статьях [Использование ML.NET в веб-API](./serve-model-web-api-ml-net.md) и [Развертывание бессерверного веб-приложения ML.NET](./serve-model-serverless-azure-functions-ml-net.md).

В отдельном приложении или процессе вызовите метод [`Load`](xref:Microsoft.ML.ModelOperationsCatalog.Load*) с указанием пути к файлу, чтобы загрузить в приложение обученную модель.

```csharp
//Define DataViewSchema for data preparation pipeline and trained model
DataViewSchema modelSchema;

// Load trained model
ITransformer trainedModel = mlContext.Model.Load("model.zip", out modelSchema);
```

## <a name="load-a-model-stored-remotely"></a>Загрузка модели, сохраненной на удаленном ресурсе

Чтобы загрузить в приложение конвейеры подготовки данных и модели, сохраненные на удаленном ресурсе, вместо пути к файлу укажите [`Stream`](xref:System.IO.Stream) в методе [`Load`](xref:Microsoft.ML.ModelOperationsCatalog.Load*).

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

## <a name="working-with-separate-data-preparation-and-model-pipelines"></a>Работа с отдельными конвейерами подготовки данных и модели

> [!NOTE]
> Работать с отдельными конвейерами подготовки данных и обучения модели необязательно. Отделение конвейеров упрощает проверку параметров обученной модели. Для создания прогнозов проще сохранять и загружать единый конвейер, который включает операции подготовки данных и обучения модели.

При работе с отдельными конвейерами подготовки данных и моделей применяется тот же порядок действий, что и при работе с единым конвейером за тем исключением, что оба конвейера должны сохраняться и загружаться одновременно.

Допустим, у нас есть отдельные конвейеры подготовки данных и обучения модели:

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

### <a name="save-data-preparation-pipeline-and-trained-model"></a>Сохранение конвейера подготовки данных и обученной модели

Чтобы сохранить и конвейер подготовки данных, и обученную модель, используйте следующие команды:

```csharp
// Save Data Prep transformer
mlContext.Model.Save(dataPrepTransformer, data.Schema, "data_preparation_pipeline.zip");

// Save Trained Model
mlContext.Model.Save(trainedModel, transformedData.Schema, "model.zip");
```

### <a name="load-data-preparation-pipeline-and-trained-model"></a>Загрузка конвейера подготовки данных и обученной модели

Для одновременной загрузки конвейера подготовки данных и обученной модели в отдельный процесс или приложение используйте следующие команды:

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

// Define data preparation and trained model schemas
DataViewSchema dataPrepPipelineSchema, modelSchema;

// Load data preparation pipeline and trained model
ITransformer dataPrepPipeline = mlContext.Model.Load("data_preparation_pipeline.zip",out dataPrepPipelineSchema);
ITransformer trainedModel = mlContext.Model.Load("model.zip", out modelSchema);
```
