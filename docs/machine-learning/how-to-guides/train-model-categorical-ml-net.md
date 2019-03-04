---
title: Конструирование признаков для обучения модели по текстовым данным — ML.NET
description: Узнайте о том, как конструировать признаки для обучения модели машинного обучения по категориальным данным с помощью ML.NET
ms.date: 02/06/2019
ms.custom: mvc,how-to
ms.openlocfilehash: eedbe0499784e7a99b0101c42892652daef3a114
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56968417"
---
# <a name="apply-feature-engineering-for-model-training-on-categorical-data---mlnet"></a><span data-ttu-id="b03a9-103">Конструирование признаков для обучения модели по текстовым данным — ML.NET</span><span class="sxs-lookup"><span data-stu-id="b03a9-103">Apply feature engineering for model training on categorical data - ML.NET</span></span>

<span data-ttu-id="b03a9-104">Вам нужно преобразовать все данные, не связанные с числами с плавающей запятой, в типы данных `float`, так как все `learners` ML.NET ожидают признаки в виде `float vector`.</span><span class="sxs-lookup"><span data-stu-id="b03a9-104">You need to convert any non float data to `float` data types since all ML.NET `learners` expect features as a `float vector`.</span></span>

<span data-ttu-id="b03a9-105">Если набор данных содержит данные `categorical` (например, enum), в ML.NET их можно преобразовать в признаки несколькими способами:</span><span class="sxs-lookup"><span data-stu-id="b03a9-105">If the dataset contains `categorical` data (for example, 'enum'), ML.NET offers several ways of converting it to features:</span></span>

- <span data-ttu-id="b03a9-106">прямое кодирование;</span><span class="sxs-lookup"><span data-stu-id="b03a9-106">One-hot encoding</span></span>
- <span data-ttu-id="b03a9-107">прямое кодирование на основе хэша;</span><span class="sxs-lookup"><span data-stu-id="b03a9-107">Hash-based one-hot encoding</span></span>
- <span data-ttu-id="b03a9-108">двоичное кодирование (с преобразованием индекса категории в двоичную последовательность и использованием битов как признаков).</span><span class="sxs-lookup"><span data-stu-id="b03a9-108">Binary encoding (convert category index into a bit sequence and use bits as features)</span></span>

<span data-ttu-id="b03a9-109">Объект `one-hot encoding` может быть избыточным, если некоторые категории имеют большую кратность (часто встречается множество разных значений с небольшими наборами).</span><span class="sxs-lookup"><span data-stu-id="b03a9-109">A `one-hot encoding` can be wasteful if some categories are very high-cardinality (lots of different values, with a small set commonly occurring.</span></span> <span data-ttu-id="b03a9-110">В таком случае нужно сократить число слотов для кодирования, выбирая признаки на основе количества.</span><span class="sxs-lookup"><span data-stu-id="b03a9-110">In that case, reduce the number of slots to encode with count-based feature selection.</span></span>

<span data-ttu-id="b03a9-111">Включите добавление категориальных признаков непосредственно в конвейере обучения ML.NET, чтобы убедиться, что категориальное преобразование:</span><span class="sxs-lookup"><span data-stu-id="b03a9-111">Include categorical featurization directly in the ML.NET learning pipeline to ensure that the categorical transformation:</span></span>

- <span data-ttu-id="b03a9-112">обучалось только на данных для обучения, а не на тестовых данных;</span><span class="sxs-lookup"><span data-stu-id="b03a9-112">is only 'trained' on the training data, and not on your test data,</span></span>
- <span data-ttu-id="b03a9-113">правильно применялось для новых входящих данных без дополнительной предобработки во время прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="b03a9-113">is correctly applied to new incoming data, without extra pre-processing at prediction time.</span></span>

<span data-ttu-id="b03a9-114">В следующем примере демонстрируется категориальная обработка для [набора данных учета численности взрослого населения](https://github.com/dotnet/machinelearning/blob/master/test/data/adult.tiny.with-schema.txt):</span><span class="sxs-lookup"><span data-stu-id="b03a9-114">The following example illustrates categorical handling for the [adult census dataset](https://github.com/dotnet/machinelearning/blob/master/test/data/adult.tiny.with-schema.txt):</span></span>

```console
Label   Workclass   education   marital-status  occupation  relationship    ethnicity   sex native-country-region   age fnlwgt  education-num   capital-gain    capital-loss    hours-per-week
0   Private 11th    Never-married   Machine-op-inspct   Own-child   Black   Male    United-States   25  226802  7   0   0   40
0   Private HS-grad Married-civ-spouse  Farming-fishing Husband White   Male    United-States   38  89814   9   0   0   50
1   Local-gov   Assoc-acdm  Married-civ-spouse  Protective-serv Husband White   Male    United-States   28  336951  12  0   0   40
1   Private Some-college    Married-civ-spouse  Machine-op-inspct   Husband Black   Male    United-States   44  160323  10  7688    0   40
```

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Define the reader: specify the data columns and where to find them in the text file.
var reader = mlContext.Data.CreateTextLoader(new[] 
    {
        new TextLoader.Column("Label", DataKind.BL, 0),
        // We will load all the categorical features into one vector column of size 8.
        new TextLoader.Column("CategoricalFeatures", DataKind.TX, 1, 8),
        // Similarly, load all numerical features into one vector of size 6.
        new TextLoader.Column("NumericalFeatures", DataKind.R4, 9, 14),
        // Let's also separately load the 'Workclass' column.
        new TextLoader.Column("Workclass", DataKind.TX, 1),
    },
    hasHeader: true
);

// Read the data.
var data = reader.Read(dataPath);

// Inspect the first 10 records of the categorical columns to check that they are correctly read.
var catColumns = data.GetColumn<string[]>(mlContext, "CategoricalFeatures").Take(10).ToArray();

// Build several alternative featurization pipelines.
var pipeline =
    // Convert each categorical feature into one-hot encoding independently.
    mlContext.Transforms.Categorical.OneHotEncoding("CategoricalFeatures", "CategoricalOneHot")
        // Convert all categorical features into indices, and build a 'word bag' of these.
        .Append(mlContext.Transforms.Categorical.OneHotEncoding("CategoricalFeatures", "CategoricalBag",OneHotEncodingTransformer.OutputKind.Bag))
        // One-hot encode the workclass column, then drop all the categories that have fewer than 10 instances in the train set.
        .Append(mlContext.Transforms.Categorical.OneHotEncoding("Workclass", "WorkclassOneHot"))
        .Append(mlContext.Transforms.FeatureSelection.SelectFeaturesBasedOnCount("WorkclassOneHot", "WorkclassOneHotTrimmed", count: 10));

// Let's train our pipeline, and then apply it to the same data.
var transformedData = pipeline.Fit(data).Transform(data);

// Inspect some columns of the resulting dataset.
var categoricalBags = transformedData.GetColumn<float[]>(mlContext, "CategoricalBag").Take(10).ToArray();
var workclasses = transformedData.GetColumn<float[]>(mlContext, "WorkclassOneHotTrimmed").Take(10).ToArray();

// Of course, if we want to train the model, we will need to compose a single float vector of all the features.
// Here's how we could do this:

var fullLearningPipeline = pipeline
    // Concatenate two of the 3 categorical pipelines, and the numeric features.
    .Append(mlContext.Transforms.Concatenate("Features", "NumericalFeatures", "CategoricalBag", "WorkclassOneHotTrimmed"))
    // Cache data in memory so that the following trainer will be able to access training examples without
    // reading them from disk multiple times.
    .AppendCacheCheckpoint(mlContext)
    // Now we're ready to train. We chose our FastTree trainer for this classification task.
    .Append(mlContext.BinaryClassification.Trainers.FastTree(numTrees: 50));

// Train the model.
var model = fullLearningPipeline.Fit(data);
```
