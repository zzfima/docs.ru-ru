---
title: Обучение модели машинного обучения, данные для которой находятся не в текстовом файле — ML.NET
description: Сведения об использовании ML.NET для загрузки обучающих данных, находящихся не в файле, для обучения модели машинного обучения в рамках конвейера прогнозирования.
ms.date: 03/18/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 32de37e45b9e19669ea06d74c7f252ec885fe004
ms.sourcegitcommit: 462dc41a13942e467984e48f4018d1f79ae67346
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2019
ms.locfileid: "58186095"
---
# <a name="train-a-machine-learning-model-with-data-thats-not-in-a-text-file---mlnet"></a>Обучение модели машинного обучения, данные для которой находятся не в текстовом файле — ML.NET

> [!NOTE]
> В этом разделе описано, как использовать платформу ML.NET, которая сейчас доступна в режиме предварительной версии. Этот материал может быть изменен. Дополнительные сведения см. в [обзоре ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

Сейчас в этих инструкциях и примере используется **ML.NET версии 0.11**. Дополнительные сведения см. в заметках о выпуске в [репозитории GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).

Как правило, при работе с ML.NET используется вариант с чтением данных для обучения из файла с помощью `TextLoader`.
Тем не менее, в сценариях обучения в реальном времени возможны и другие варианты размещения данных. Данные могут:

* располагаться в таблицах SQL;
* располагаться в коде JSON или XML;
* извлекаться из файлов журналов;
* генерироваться "на лету".

Используйте [понимание схемы](https://github.com/dotnet/machinelearning/tree/master/docs/code/SchemaComprehension.md), чтобы перенести существующий интерфейс `IEnumerable` C# в ML.NET как `DataView`.

В этом примере вам предстоит создать модель прогнозирования оттока клиентов, а также извлечь следующие функции из производственной системы:

* идентификатор клиента (игнорируется моделью);
* прекратил ли клиент сотрудничество (целевая "метка");
* "демографическая категория" (одна строка, например "молодой взрослый" и т. д.);
* число посещений за последние 5 дней.

```csharp
private class CustomerChurnInfo
{
    public string CustomerID { get; set; }
    public bool HasChurned { get; set; }
    public string DemographicCategory { get; set; }
    // Visits during last 5 days, latest to newest.
    [VectorType(5)]
    public float[] LastVisits { get; set; }
}
```

Загрузите эти данные в `DataView` и обучите модель, используя следующий код:

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging,
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Step one: read the data as an IDataView.
// Let's assume that 'GetChurnData()' fetches and returns the training data from somewhere.
IEnumerable<CustomerChurnInfo> churnData = GetChurnInfo();

// Turn the data into the ML.NET data view.
// We can use CreateDataView or CreateStreamingDataView, depending on whether 'churnData' is an IList,
// or merely an IEnumerable.
var trainData = mlContext.Data.LoadFromEnumerable(churnData);

// Build the learning pipeline.
// In our case, we will one-hot encode the demographic category, and concatenate that with the number of visits.
// We apply our FastTree binary classifier to predict the 'HasChurned' label.

var pipeline = mlContext.Transforms.Categorical.OneHotEncoding("DemographicCategory")
    .Append(mlContext.Transforms.Concatenate("Features", "DemographicCategory", "LastVisits"))
    .Append(mlContext.BinaryClassification.Trainers.FastTree("HasChurned", "Features", numTrees: 20));

var model = pipeline.Fit(trainData);
```
