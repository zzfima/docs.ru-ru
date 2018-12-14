---
title: Использование обобщенных аддитивных моделей и функций форм для объясняемости модели в ML.NET
description: Использование обобщенных аддитивных моделей и функций форм для объясняемости модели в ML.NET
ms.date: 12/04/2018
ms.custom: mvc,how-to
ms.openlocfilehash: 489aee34d0404293bc080b934636c01bdab92fe9
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53156632"
---
# <a name="use-generalized-additive-models-and-shape-functions-for-model-explainability-in-mlnet"></a>Использование обобщенных аддитивных моделей и функций форм для объясняемости модели в ML.NET

При создании моделей машинного обучения зачастую недостаточно просто делать прогнозы. Часто разработчики машинного обучения, руководители, принимающие решения, и те, на чью работу влияют модели, должны понимать, как модели машинного обучения принимают решения и какие признаки влияют на их эффективность. **Обобщенные аддитивные модели (GAM)** используются внутри корпорации Майкрософт для объяснения моделей, чтобы помочь разработчикам машинного обучения создавать высокоэффективные модели, которые могут быть легко интерпретированы другими.

GAM — это класс **интерпретируемых моделей**. Это линейные модели, в которых условия являются нелинейными функциями, называемыми "функциями форм" одной переменной. Как линейные модели, их легко интерпретировать, но так как модели изучают функции признаков вместо одного весового коэффициента, они могут моделировать более сложные отношения, чем простая линейная модель. Результирующее прогнозирование GAM имеет свободный член, который представляет среднее прогнозирование по набору для обучения, и функции форм, которые представляют отклонение от среднего прогнозирования. Функции форм можно проверить на глаз, чтобы увидеть ответ модели на различные значения признака, и визуализировать, как на следующем графике, созданном в конце примера кода. Механизм обучения GAM в ML.NET реализован с помощью неполных деревьев с градиентным бустингом (например, пней) для изучения непараметрических функций форм. Он основан на методе, описанном в публикации [Intelligible Models for Classification and Regression](https://www.cs.cornell.edu/~yinlou/papers/lou-kdd12.pdf) (Понятные модели для классификации и регрессии), написанной Лу, Каруана и Герке.

```csharp
// Train the Generalized Additive Model
var gamTrainer = mlContext.Regression.Trainers.GeneralizedAdditiveModels()
var gamModel = gamTrainer.Fit(data);
 
// The intercept for Generalize Additive Models represent the average prediction for the training data
var intercept = gamModel.Intercept;
 
// Get the feature names from the training set
var featureNames = data.Schema.GetColumns()
                .Select(tuple => tuple.column.Name) // Get the column names
                .Where(name => name != labelName) // Drop the Label
                .ToArray();
 
// Get the index of a variable from the training data
var myFeatureIndex = featureNames.ToList().FindIndex(str => str.Equals("MyFeature"));
 
// The shape functions represent the deviation from the average prediction as a function of the feature value
// It is represented by a discrete set of bins
// First, get the array of bin upper bounds from the model for this feature
var myFeatureBins = gamModel.GetFeatureBinUpperBounds(myFeatureIndex);
// Then get the array of bin weights; these are the effect size for each bin
var myFeatureWeights = gamModel.GetFeatureWeights(myFeatureIndex);
 
// Write out the shape function for the feature (see the following figure for what this looks like)
for (int i = 0; i < myFeatureBins.Length; i++)
  Console.WriteLine($"x < {myFeatureBins[i]:0.00} => {myFeatureWeights[i]:0.000}");
```

![График функции формы обобщенных аддитивных моделей](./media/use-gams-for-model-explainability/gam-shape-function-graph.png)

Пример обучения модели GAM, а также проверки и интерпретации результатов см. в [репозитории GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/blob/master/docs/samples/Microsoft.ML.Samples/Dynamic/GeneralizedAdditiveModels.cs).