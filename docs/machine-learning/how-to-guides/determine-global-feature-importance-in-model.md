---
title: Определение важности признаков моделей с помощью средства Permutation Feature Importance в ML.NET
description: Сведения об определении важности признаков моделей с помощью средства Permutation Feature Importance в ML.NET
ms.date: 12/04/2018
ms.custom: mvc,how-to
ms.openlocfilehash: ebad89aaee1155d7c116b8536307756227dced31
ms.sourcegitcommit: 75567a3cb437009db55949c6092f4e77ed1a9da4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2019
ms.locfileid: "54307114"
---
# <a name="determine-the-feature-importance-of-models-with-permutation-feature-importance-in-mlnet"></a>Определение важности признаков моделей с помощью средства Permutation Feature Importance в ML.NET

При создании моделей машинного обучения зачастую недостаточно просто делать прогнозы. Часто разработчики машинного обучения, руководители, принимающие решения, и те, на чью работу влияют модели, должны понимать, как модели машинного обучения принимают решения и какие признаки влияют на их эффективность. `Permutation Feature Importance` (PFI) — это инструмент объяснения модели, который корпорация Майкрософт использует, чтобы помочь внутренним разработчикам машинного обучения понять важность признаков моделей.

PFI — это метод определения **глобальной важности признака** в обученной модели машинного обучения, описанный Брейманом в статье о [случайных лесах, раздел 10](https://www.stat.berkeley.edu/~breiman/randomforest2001.pdf). PFI определяет важность признака, задавая следующий вопрос: "Если для признака будут установлены случайные* значение, как это отразится на модели?". Преимущество метода PFI состоит в том, что он не зависит от модели. Он применим к любой модели, которую можно оценить. Кроме того, для определения важности признака он может использовать любой набор данных, не ограничиваясь набором для обучения. С помощью PFI можно получить значения важности признаков, аналогичные представленным на следующем графике:

![График Permutation Feature Importance](./media/determine-global-feature-importance-in-model/pfi-graph.png)

```csharp
// Compute the feature importance using PFI
var permutationMetrics = mlContext.Regression.PermutationFeatureImportance(model, data);
 
// Get the feature names from the training set
var featureNames = data.Schema.GetColumns()
                .Select(tuple => tuple.column.Name) // Get the column names
                .Where(name => name != labelName) // Drop the Label
                .ToArray();
 
// Write out the feature names and their importance to the model's R-squared value
for (int i = 0; i < featureNames.Length; i++)
  Console.WriteLine($"{featureNames[i]}\t{permutationMetrics[i].rSquared:G4}");
```

Пример анализа важности признака модели с помощью PFI приведен на [сайте GitHub в репозитории dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/samples/Microsoft.ML.Samples/Dynamic/PermutationFeatureImportance).

/* Необязательно случайные, это могут быть переставленные значения в наборе примеров.
