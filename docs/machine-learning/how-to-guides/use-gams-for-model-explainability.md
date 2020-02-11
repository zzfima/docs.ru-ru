---
title: Интерпретация моделей ML.NET с помощью обобщенных аддитивных моделей
description: Использование обобщенных аддитивных моделей и функций форм для интерпретируемости модели в ML.NET
ms.date: 01/30/2020
ms.custom: mvc,how-to
ms.openlocfilehash: 6df19eff4fec98c5815a9f8f4d8e4e9a80cba6ed
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2020
ms.locfileid: "77092477"
---
# <a name="use-generalized-additive-models-and-shape-functions-for-model-interpretability-in-mlnet"></a><span data-ttu-id="874ea-103">Использование обобщенных аддитивных моделей и функций форм для интерпретируемости модели в ML.NET</span><span class="sxs-lookup"><span data-stu-id="874ea-103">Use Generalized Additive Models and shape functions for model interpretability in ML.NET</span></span>

<span data-ttu-id="874ea-104">При создании моделей машинного обучения зачастую недостаточно просто делать прогнозы.</span><span class="sxs-lookup"><span data-stu-id="874ea-104">When creating machine learning models, it is often not enough to simply make predictions.</span></span> <span data-ttu-id="874ea-105">Часто разработчики машинного обучения, руководители, принимающие решения, и те, на чью работу влияют модели, должны понимать, как модели машинного обучения принимают решения и какие признаки влияют на их эффективность.</span><span class="sxs-lookup"><span data-stu-id="874ea-105">Often, machine learning developers, decision makers, and those affected by the models need to understand how machine learning models make decisions and which features contribute to their performance.</span></span> <span data-ttu-id="874ea-106">**Обобщенные аддитивные модели (GAM)** используются внутри корпорации Майкрософт для интерпретируемости моделей, чтобы помочь разработчикам машинного обучения создавать высокоэффективные модели, которые могут быть легко интерпретированы другими.</span><span class="sxs-lookup"><span data-stu-id="874ea-106">**Generalized Additive Models (GAMs)** are used internally at Microsoft for model interpretability to help machine learning developers create high-capacity models that can be easily interpreted by others.</span></span>

<span data-ttu-id="874ea-107">GAM — это класс **интерпретируемых моделей**. Это линейные модели, в которых условия являются нелинейными функциями, называемыми "функциями форм" одной переменной.</span><span class="sxs-lookup"><span data-stu-id="874ea-107">GAMs are a class of **interpretable models** that are linear models where the terms are nonlinear functions, called "shape functions" of a single variable.</span></span> <span data-ttu-id="874ea-108">Как линейные модели, их легко интерпретировать, но так как модели изучают функции признаков вместо одного весового коэффициента, они могут моделировать более сложные отношения, чем простая линейная модель.</span><span class="sxs-lookup"><span data-stu-id="874ea-108">As linear models, they are easily interpreted but because the models learn functions of features instead of a single weight, they can model more complex relationships than a simple linear model.</span></span> <span data-ttu-id="874ea-109">Результирующее прогнозирование GAM имеет свободный член, который представляет среднее прогнозирование по набору для обучения, и функции форм, которые представляют отклонение от среднего прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="874ea-109">The resulting GAM predictor has an intercept term that represents the average prediction over the training set, and shape functions that represent the deviation from the average prediction.</span></span> <span data-ttu-id="874ea-110">Функции форм можно проверить на глаз, чтобы увидеть ответ модели на различные значения признака, и визуализировать, как на следующем графике, созданном в конце примера кода.</span><span class="sxs-lookup"><span data-stu-id="874ea-110">The shape functions can be inspected by eye to see the response of the model to different values of a feature, and visualized like the following graph that is created at the end of the code example.</span></span> <span data-ttu-id="874ea-111">Механизм обучения GAM в ML.NET реализован с помощью неполных деревьев с градиентным бустингом (например, пней) для изучения непараметрических функций форм. Он основан на методе, описанном в публикации [Intelligible Models for Classification and Regression](https://www.cs.cornell.edu/~yinlou/papers/lou-kdd12.pdf) (Понятные модели для классификации и регрессии), написанной Лу, Каруана и Герке.</span><span class="sxs-lookup"><span data-stu-id="874ea-111">The GAM trainer in ML.NET is implemented using shallow gradient boosted trees (for example tree stumps) to learn nonparametric shape functions, and is based on the method described in [Intelligible Models for Classification and Regression](https://www.cs.cornell.edu/~yinlou/papers/lou-kdd12.pdf) by Lou, Caruana, and Gehrke.</span></span>

```csharp
// Train the Generalized Additive Model
var fitPipeline = pipeline.Fit(data);
var gamModel = fitPipeline.LastTransformer.Model;

// The intercept for Generalize Additive Models represent the average prediction for the training data
var intercept = gamModel.Intercept;
Console.WriteLine($"Average predicted cost: {intercept:0.00}");

// Get the column names from the training set
var columnNames = data.Schema.AsEnumerable()
    .Select(column => column.Name) // Get the column names
    .Where(name => name != "MedianHomeValue") // Drop the Label
    .ToArray();

// Get the index of a variable from the training data
var myFeatureIndex = columnNames.ToList().FindIndex(str => str.Equals("MyFeature"));

// The shape functions represent the deviation from the average prediction as a function of the feature value
// It is represented by a discrete set of bins
// First, get the array of bin upper bounds from the model for this feature
var myFeatureBins = gamModel.GetBinUpperBounds(myFeatureIndex);
// Then get the array of bin weights; these are the effect size for each bin
var myFeatureWeights = gamModel.GetBinEffects(myFeatureIndex);

// Write out the shape function for the feature (see the following figure for what this looks like)
for (int i = 0; i < myFeatureBins.Length; i++)
{
    Console.WriteLine($"x < {myFeatureBins[i]:0.00} => {myFeatureWeights[i]:0.000}");
}
```

![График функции формы обобщенных аддитивных моделей](./media/use-gams-for-model-explainability/gam-shape-function-graph.png)

<span data-ttu-id="874ea-113">Пример обучения модели GAM, а также проверки и интерпретации результатов см. в [репозитории GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/blob/master/docs/samples/Microsoft.ML.Samples/Dynamic/GeneralizedAdditiveModels.cs).</span><span class="sxs-lookup"><span data-stu-id="874ea-113">For a sample of how to train a GAM model and inspect and interpret the results, see [the dotnet/machinelearning GitHub repository](https://github.com/dotnet/machinelearning/blob/master/docs/samples/Microsoft.ML.Samples/Dynamic/GeneralizedAdditiveModels.cs).</span></span>
