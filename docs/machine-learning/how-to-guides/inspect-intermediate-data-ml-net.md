---
title: Проверка значений промежуточных данных при конвейерной обработке ML.NET
description: Сведения о проверке значений промежуточных данных при конвейерной обработке машинного обучения ML.NET
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 3d20f153be7b502fb5a542a942245546412efde2
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/08/2019
ms.locfileid: "57678648"
---
# <a name="inspect-intermediate-data-values-during-mlnet-pipeline-processing"></a><span data-ttu-id="81a70-103">Проверка значений промежуточных данных при конвейерной обработке ML.NET</span><span class="sxs-lookup"><span data-stu-id="81a70-103">Inspect intermediate data values during ML.NET pipeline processing</span></span>

> [!NOTE]
> <span data-ttu-id="81a70-104">В этом разделе описано, как использовать платформу ML.NET, которая сейчас доступна в режиме предварительной версии. Этот материал может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="81a70-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="81a70-105">Дополнительные сведения см. в [обзоре ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="81a70-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="81a70-106">Сейчас в этих инструкциях и примере используется **ML.NET версии 0.10**.</span><span class="sxs-lookup"><span data-stu-id="81a70-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="81a70-107">Дополнительные сведения см. в заметках о выпуске в [репозитории GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="81a70-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="81a70-108">Во время эксперимента вам может потребоваться просмотреть и проверить результаты обработки данных в заданной точке.</span><span class="sxs-lookup"><span data-stu-id="81a70-108">During the experiment, you may want to observe and validate the data processing results at a given point.</span></span> <span data-ttu-id="81a70-109">Это не просто сделать, так как операции ML.NET медлительны и создают объекты, представляющие собой "обещания" данных.</span><span class="sxs-lookup"><span data-stu-id="81a70-109">This isn't easy since ML.NET operations are lazy, constructing objects that are 'promises' of data.</span></span>

<span data-ttu-id="81a70-110">Метод расширения `GetColumn<T>` позволяет проверить промежуточные данные.</span><span class="sxs-lookup"><span data-stu-id="81a70-110">The `GetColumn<T>` extension method lets you inspect the intermediate data.</span></span> <span data-ttu-id="81a70-111">Он возвращает содержимое столбца данных в виде `IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="81a70-111">It returns the contents of one data column as an `IEnumerable`.</span></span>

<span data-ttu-id="81a70-112">В следующем примере показано, как использовать метод расширения `GetColumn<T>`:</span><span class="sxs-lookup"><span data-stu-id="81a70-112">The following example shows how to use the `GetColumn<T>` extension method:</span></span>

<span data-ttu-id="81a70-113">[Пример файла](https://github.com/dotnet/machinelearning/tree/master/test/data/adult.tiny.with-schema.txt):</span><span class="sxs-lookup"><span data-stu-id="81a70-113">[Example file](https://github.com/dotnet/machinelearning/tree/master/test/data/adult.tiny.with-schema.txt):</span></span>
```
Label   Workclass   education   marital-status
0   Private 11th    Never-married
0   Private HS-grad Married-civ-spouse
1   Local-gov   Assoc-acdm  Married-civ-spouse
1   Private Some-college    Married-civ-spouse

```

<span data-ttu-id="81a70-114">Наш класс определен следующим образом:</span><span class="sxs-lookup"><span data-stu-id="81a70-114">Our class is defined as follows:</span></span>

```csharp
public class InspectedRow
{
    [LoadColumn(0)]
    public bool IsOver50K { get; set; }
    [LoadColumn(1)]
    public string WorkClass { get; set; }
    [LoadColumn(2)]
    public string Education { get; set; }
    [LoadColumn(3)]
    public string MaritalStatus { get; set; }
}
```

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Read the data into a data view.
var data = mlContext.Data.ReadFromTextFile<InspectedRow>(dataPath, hasHeader: true);

// Start creating our processing pipeline. For now, let's just concatenate all the text columns
// together into one.
var pipeline = mlContext.Transforms.Concatenate("AllFeatures", "WorkClass", "Education", "MaritalStatus");

// Fit our data pipeline and transform data with it.
var transformedData = pipeline.Fit(data).Transform(data);

// Extract the 'AllFeatures' column.
// This will give the entire dataset: make sure to only take several row
// in case the dataset is huge. The is similar to the static API, except
// you have to specify the column name and type.
var featureColumns =
    transformedData
        .GetColumn<string[]>(mlContext, "AllFeatures")
        .Take(20)
        .ToArray();
```
