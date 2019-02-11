---
title: Предобработка данных для обучения с помощью методов нормализации для использования в обработке данных — ML.NET
description: Сведения об использовании методов нормализации для предобработки данных для обучения для использования при создании, обучении и оценке модели машинного обучения с помощью ML.NET
ms.date: 02/01/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 4311307f5410a96bb4a30fcedd88bc43afd25c12
ms.sourcegitcommit: facefcacd7ae2e5645e463bc841df213c505ffd4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2019
ms.locfileid: "55738582"
---
# <a name="preprocess-training-data-with-normalizers-to-use-in-data-processing---mlnet"></a>Предобработка данных для обучения с помощью методов нормализации для использования в обработке данных — ML.NET

ML.NET предоставляет ряд [параметрических и непараметрических алгоритмов](https://machinelearningmastery.com/parametric-and-nonparametric-machine-learning-algorithms/).

**Не** столь важно, какой метод нормализации вы выберете, важно **использовать** его при обучении линейных или других параметрических моделей.

Всегда включайте метод нормализации непосредственно в конвейер обучения ML.NET, чтобы он:

- обучался только на данных для обучения, а не на тестовых данных;
- правильно применялся для всех новых входящих данных без необходимости дополнительной предобработки во время прогнозирования.

Ниже приведен фрагмент кода, демонстрирующий нормализацию в конвейерах обучения. В нем предполагается использование набора данных по ирисам:

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Define the reader: specify the data columns and where to find them in the text file.
var reader = mlContext.Data.CreateTextReader(
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
        new NormalizingEstimator.MinMaxColumn("Features", "MinMaxNormalized", fixZero: true),
        new NormalizingEstimator.MeanVarColumn("Features", "MeanVarNormalized", fixZero: true),
        new NormalizingEstimator.BinningColumn("Features", "BinNormalized", numBins: 256));

// Let's train our pipeline of normalizers, and then apply it to the same data.
var normalizedData = pipeline.Fit(trainData).Transform(trainData);

// Inspect one column of the resulting dataset.
var meanVarValues = normalizedData.GetColumn<float[]>(mlContext, "MeanVarNormalized").ToArray();
```
