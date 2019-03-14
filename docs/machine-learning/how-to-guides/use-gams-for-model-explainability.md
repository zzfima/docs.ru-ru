---
title: Использование обобщенных аддитивных моделей и функций форм для объясняемости модели в ML.NET
description: Использование обобщенных аддитивных моделей и функций форм для объясняемости модели в ML.NET
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: f7b8b9a3daabb16f59c901911a1f6950ce864fff
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/08/2019
ms.locfileid: "57675593"
---
# <a name="use-generalized-additive-models-and-shape-functions-for-model-explainability-in-mlnet"></a>Использование обобщенных аддитивных моделей и функций форм для объясняемости модели в ML.NET

> [!NOTE]
> В этом разделе описано, как использовать платформу ML.NET, которая сейчас доступна в режиме предварительной версии. Этот материал может быть изменен. Дополнительные сведения см. в [обзоре ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

Сейчас в этих инструкциях и примере используется **ML.NET версии 0.10**. Дополнительные сведения см. в заметках о выпуске в [репозитории GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).

При создании моделей машинного обучения зачастую недостаточно просто делать прогнозы. Часто разработчики машинного обучения, руководители, принимающие решения, и те, на чью работу влияют модели, должны понимать, как модели машинного обучения принимают решения и какие признаки влияют на их эффективность. **Обобщенные аддитивные модели (GAM)** используются внутри корпорации Майкрософт для объяснения моделей, чтобы помочь разработчикам машинного обучения создавать высокоэффективные модели, которые могут быть легко интерпретированы другими.

GAM — это класс **интерпретируемых моделей**. Это линейные модели, в которых условия являются нелинейными функциями, называемыми "функциями форм" одной переменной. Как линейные модели, их легко интерпретировать, но так как модели изучают функции признаков вместо одного весового коэффициента, они могут моделировать более сложные отношения, чем простая линейная модель. Результирующее прогнозирование GAM имеет свободный член, который представляет среднее прогнозирование по набору для обучения, и функции форм, которые представляют отклонение от среднего прогнозирования. Функции форм можно проверить на глаз, чтобы увидеть ответ модели на различные значения признака, и визуализировать, как на следующем графике, созданном в конце примера кода. Механизм обучения GAM в ML.NET реализован с помощью неполных деревьев с градиентным бустингом (например, пней) для изучения непараметрических функций форм. Он основан на методе, описанном в публикации [Intelligible Models for Classification and Regression](https://www.cs.cornell.edu/~yinlou/papers/lou-kdd12.pdf) (Понятные модели для классификации и регрессии), написанной Лу, Каруана и Герке.

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

Пример обучения модели GAM, а также проверки и интерпретации результатов см. в [репозитории GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/blob/master/docs/samples/Microsoft.ML.Samples/Dynamic/GeneralizedAdditiveModels.cs).
