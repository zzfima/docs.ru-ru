---
title: Предобработка данных для обучения с помощью методов нормализации для использования в обработке данных — ML.NET
description: Сведения об использовании методов нормализации для предобработки данных для обучения для использования при создании, обучении и оценке модели машинного обучения с помощью ML.NET
ms.date: 11/07/2018
ms.custom: mvc,how-to
ms.openlocfilehash: c8b959904705e996c97bdcd8b3444e754d14d046
ms.sourcegitcommit: 35316b768394e56087483cde93f854ba607b63bc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2018
ms.locfileid: "52297621"
---
# <a name="preprocess-training-data-with-normalizers-to-use-in-data-processing---mlnet"></a><span data-ttu-id="5e028-103">Предобработка данных для обучения с помощью методов нормализации для использования в обработке данных — ML.NET</span><span class="sxs-lookup"><span data-stu-id="5e028-103">Preprocess training data with normalizers to use in data processing - ML.NET</span></span>

<span data-ttu-id="5e028-104">ML.NET предоставляет ряд [параметрических и непараметрических алгоритмов](https://machinelearningmastery.com/parametric-and-nonparametric-machine-learning-algorithms/).</span><span class="sxs-lookup"><span data-stu-id="5e028-104">ML.NET exposes a number of [parametric and non-parametric algorithms](https://machinelearningmastery.com/parametric-and-nonparametric-machine-learning-algorithms/).</span></span>

<span data-ttu-id="5e028-105">**Не** столь важно, какой метод нормализации вы выберете, важно **использовать** его при обучении линейных или других параметрических моделей.</span><span class="sxs-lookup"><span data-stu-id="5e028-105">It's **not** as important which normalizer you choose as it is to **use** a normalizer when training linear or other parametric models.</span></span>

<span data-ttu-id="5e028-106">Всегда включайте метод нормализации непосредственно в конвейер обучения ML.NET, чтобы он:</span><span class="sxs-lookup"><span data-stu-id="5e028-106">Always include the normalizer directly in the ML.NET learning pipeline, so it:</span></span>

- <span data-ttu-id="5e028-107">обучался только на данных для обучения, а не на тестовых данных;</span><span class="sxs-lookup"><span data-stu-id="5e028-107">is only trained on the training data, and not on your test data,</span></span>
- <span data-ttu-id="5e028-108">правильно применялся для всех новых входящих данных без необходимости дополнительной предобработки во время прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="5e028-108">is correctly applied to all the new incoming data, without the need for extra pre-processing at prediction time.</span></span>

<span data-ttu-id="5e028-109">Ниже приведен фрагмент кода, демонстрирующий нормализацию в конвейерах обучения.</span><span class="sxs-lookup"><span data-stu-id="5e028-109">Here's a snippet of code that demonstrates normalization in learning pipelines.</span></span> <span data-ttu-id="5e028-110">В нем предполагается использование набора данных по ирисам:</span><span class="sxs-lookup"><span data-stu-id="5e028-110">It assumes the Iris dataset:</span></span>

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Define the reader: specify the data columns and where to find them in the text file.
var reader = mlContext.Data.TextReader(new TextLoader.Arguments
{
    Column = new[] {
        // The four features of the Iris dataset will be grouped together as one Features column.
        new TextLoader.Column("Features", DataKind.R4, 0, 3),
        // Label: kind of iris.
        new TextLoader.Column("Label", DataKind.TX, 4),
    },
    // Default separator is tab, but the dataset has comma.
    Separator = ","
});

// Read the training data.
var trainData = reader.Read(dataPath);

// Apply all kinds of standard ML.NET normalization to the raw features.
var pipeline =
    mlContext.Transforms.Normalize(
        new NormalizingEstimator.MinMaxColumn("Features", "MinMaxNormalized", fixZero: true),
        new NormalizingEstimator.MeanVarColumn("Features", "MeanVarNormalized", fixZero: true),
        new NormalizingEstimator.BinningColumn("Features", "BinNormalized", numBins: 256));

// Let's train our pipeline of normalizers, and then apply it to the same data.
var normalizedData = pipeline.Fit(trainData).Transform(trainData);

// Inspect one column of the resulting dataset.
var meanVarValues = normalizedData.GetColumn<float[]>(mlContext, "MeanVarNormalized").ToArray();
```
