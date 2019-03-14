---
title: Предобработка данных для обучения с помощью методов нормализации для использования в обработке данных — ML.NET
description: Сведения об использовании методов нормализации для предобработки данных для обучения для использования при создании, обучении и оценке модели машинного обучения с помощью ML.NET
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 2d18f7c19a51fd929ac6efb7f600cb1ac2733de8
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/08/2019
ms.locfileid: "57676607"
---
# <a name="preprocess-training-data-with-normalizers-to-use-in-data-processing---mlnet"></a><span data-ttu-id="6adba-103">Предобработка данных для обучения с помощью методов нормализации для использования в обработке данных — ML.NET</span><span class="sxs-lookup"><span data-stu-id="6adba-103">Preprocess training data with normalizers to use in data processing - ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="6adba-104">В этом разделе описано, как использовать платформу ML.NET, которая сейчас доступна в режиме предварительной версии. Этот материал может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="6adba-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="6adba-105">Дополнительные сведения см. в [обзоре ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="6adba-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="6adba-106">Сейчас в этих инструкциях и примере используется **ML.NET версии 0.10**.</span><span class="sxs-lookup"><span data-stu-id="6adba-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="6adba-107">Дополнительные сведения см. в заметках о выпуске в [репозитории GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="6adba-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="6adba-108">ML.NET предоставляет ряд [параметрических и непараметрических алгоритмов](https://machinelearningmastery.com/parametric-and-nonparametric-machine-learning-algorithms/).</span><span class="sxs-lookup"><span data-stu-id="6adba-108">ML.NET exposes a number of [parametric and non-parametric algorithms](https://machinelearningmastery.com/parametric-and-nonparametric-machine-learning-algorithms/).</span></span>

<span data-ttu-id="6adba-109">**Не** столь важно, какой метод нормализации вы выберете, важно **использовать** его при обучении линейных или других параметрических моделей.</span><span class="sxs-lookup"><span data-stu-id="6adba-109">It's **not** as important which normalizer you choose as it is to **use** a normalizer when training linear or other parametric models.</span></span>

<span data-ttu-id="6adba-110">Всегда включайте метод нормализации непосредственно в конвейер обучения ML.NET, чтобы он:</span><span class="sxs-lookup"><span data-stu-id="6adba-110">Always include the normalizer directly in the ML.NET learning pipeline, so it:</span></span>

- <span data-ttu-id="6adba-111">обучался только на данных для обучения, а не на тестовых данных;</span><span class="sxs-lookup"><span data-stu-id="6adba-111">is only trained on the training data, and not on your test data,</span></span>
- <span data-ttu-id="6adba-112">правильно применялся для всех новых входящих данных без необходимости дополнительной предобработки во время прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="6adba-112">is correctly applied to all the new incoming data, without the need for extra pre-processing at prediction time.</span></span>

<span data-ttu-id="6adba-113">Ниже приведен фрагмент кода, демонстрирующий нормализацию в конвейерах обучения.</span><span class="sxs-lookup"><span data-stu-id="6adba-113">Here's a snippet of code that demonstrates normalization in learning pipelines.</span></span> <span data-ttu-id="6adba-114">В нем предполагается использование набора данных по ирисам:</span><span class="sxs-lookup"><span data-stu-id="6adba-114">It assumes the Iris dataset:</span></span>

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Define the reader: specify the data columns and where to find them in the text file.
var reader = mlContext.Data.CreateTextLoader(
    columns: new TextLoader.Column[]
    {
        // The four features of the Iris dataset will be grouped together as one Features column.
        new TextLoader.Column("Features",DataKind.R4,0,3),
        // Label: kind of iris.
        new TextLoader.Column("Label",DataKind.TX,4)
    },
    // Default separator is tab, but the dataset has comma.
    separatorChar: ',',
    // First line of the file is a header, not a data row.
    hasHeader: true
);

// Read the training data.
var trainData = reader.Read(dataPath);

// Apply all kinds of standard ML.NET normalization to the raw features.
var pipeline =
    mlContext.Transforms.Normalize(
            new NormalizingEstimator.MinMaxColumn(inputColumnName:"Features", outputColumnName:"MinMaxNormalized", fixZero: true),
            new NormalizingEstimator.MeanVarColumn(inputColumnName: "Features", outputColumnName: "MeanVarNormalized", fixZero: true),
            new NormalizingEstimator.BinningColumn(inputColumnName: "Features", outputColumnName: "BinNormalized", numBins: 256));

// Let's train our pipeline of normalizers, and then apply it to the same data.
var normalizedData = pipeline.Fit(trainData).Transform(trainData);

// Inspect one column of the resulting dataset.
var meanVarValues = normalizedData.GetColumn<float[]>(mlContext, "MeanVarNormalized").ToArray();
```
