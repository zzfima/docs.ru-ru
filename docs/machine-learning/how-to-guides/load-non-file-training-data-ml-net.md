---
title: Обучение модели машинного обучения, данные для которой находятся не в текстовом файле — ML.NET
description: Сведения об использовании ML.NET для загрузки обучающих данных, находящихся не в файле, для обучения модели машинного обучения в рамках конвейера прогнозирования.
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 27b327a63cb55b7fce0f4ff7facd3ee7c4a1c85c
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/08/2019
ms.locfileid: "57678631"
---
# <a name="train-a-machine-learning-model-with-data-thats-not-in-a-text-file---mlnet"></a><span data-ttu-id="cb92b-103">Обучение модели машинного обучения, данные для которой находятся не в текстовом файле — ML.NET</span><span class="sxs-lookup"><span data-stu-id="cb92b-103">Train a machine learning model with data that's not in a text file - ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="cb92b-104">В этом разделе описано, как использовать платформу ML.NET, которая сейчас доступна в режиме предварительной версии. Этот материал может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="cb92b-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="cb92b-105">Дополнительные сведения см. в [обзоре ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="cb92b-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="cb92b-106">Сейчас в этих инструкциях и примере используется **ML.NET версии 0.10**.</span><span class="sxs-lookup"><span data-stu-id="cb92b-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="cb92b-107">Дополнительные сведения см. в заметках о выпуске в [репозитории GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="cb92b-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="cb92b-108">Как правило, при работе с ML.NET используется вариант с чтением данных для обучения из файла с помощью `TextLoader`.</span><span class="sxs-lookup"><span data-stu-id="cb92b-108">The commonly demonstrated use case for ML.NET is use the `TextLoader` to read the training data from a file.</span></span>
<span data-ttu-id="cb92b-109">Тем не менее, в сценариях обучения в реальном времени возможны и другие варианты размещения данных. Данные могут:</span><span class="sxs-lookup"><span data-stu-id="cb92b-109">However, in real-time training scenarios the data can be elsewhere, such as:</span></span>

* <span data-ttu-id="cb92b-110">располагаться в таблицах SQL;</span><span class="sxs-lookup"><span data-stu-id="cb92b-110">in SQL tables</span></span>
* <span data-ttu-id="cb92b-111">извлекаться из файлов журналов;</span><span class="sxs-lookup"><span data-stu-id="cb92b-111">extracted from log files</span></span>
* <span data-ttu-id="cb92b-112">генерироваться "на лету".</span><span class="sxs-lookup"><span data-stu-id="cb92b-112">generated on the fly</span></span>

<span data-ttu-id="cb92b-113">Используйте [понимание схемы](https://github.com/dotnet/machinelearning/tree/master/docs/code/SchemaComprehension.md), чтобы перенести существующий интерфейс `IEnumerable` C# в ML.NET как `DataView`.</span><span class="sxs-lookup"><span data-stu-id="cb92b-113">Use [schema comprehension](https://github.com/dotnet/machinelearning/tree/master/docs/code/SchemaComprehension.md) to bring an existing C# `IEnumerable` into ML.NET as a `DataView`.</span></span>

<span data-ttu-id="cb92b-114">В этом примере вам предстоит создать модель прогнозирования оттока клиентов, а также извлечь следующие функции из производственной системы:</span><span class="sxs-lookup"><span data-stu-id="cb92b-114">For this example, you'll build the customer churn prediction model, and extract the following features from your production system:</span></span>

* <span data-ttu-id="cb92b-115">идентификатор клиента (игнорируется моделью);</span><span class="sxs-lookup"><span data-stu-id="cb92b-115">Customer ID (ignored by the model)</span></span>
* <span data-ttu-id="cb92b-116">прекратил ли клиент сотрудничество (целевая "метка");</span><span class="sxs-lookup"><span data-stu-id="cb92b-116">Whether the customer has churned (the target 'label')</span></span>
* <span data-ttu-id="cb92b-117">"демографическая категория" (одна строка, например "молодой взрослый" и т. д.);</span><span class="sxs-lookup"><span data-stu-id="cb92b-117">The 'demographic category' (one string, like 'young adult' etc.)</span></span>
* <span data-ttu-id="cb92b-118">число посещений за последние 5 дней.</span><span class="sxs-lookup"><span data-stu-id="cb92b-118">The number of visits from the last 5 days.</span></span>

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

<span data-ttu-id="cb92b-119">Загрузите эти данные в `DataView` и обучите модель, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="cb92b-119">Load this data into the `DataView` and train the model, using the following code:</span></span>

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
var trainData = mlContext.Data.ReadFromEnumerable(churnData);

// Build the learning pipeline.
// In our case, we will one-hot encode the demographic category, and concatenate that with the number of visits.
// We apply our FastTree binary classifier to predict the 'HasChurned' label.

var pipeline = mlContext.Transforms.Categorical.OneHotEncoding("DemographicCategory")
    .Append(mlContext.Transforms.Concatenate("Features", "DemographicCategory", "LastVisits"))
    .Append(mlContext.BinaryClassification.Trainers.FastTree("HasChurned", "Features", numTrees: 20));

var model = pipeline.Fit(trainData);
```
