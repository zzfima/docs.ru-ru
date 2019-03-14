---
title: Определение важности признаков моделей с помощью средства Permutation Feature Importance в ML.NET
description: Сведения об определении важности признаков моделей с помощью средства Permutation Feature Importance в ML.NET
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: b0457bc07168579403e5a00383864c5612e1d17f
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/08/2019
ms.locfileid: "57675554"
---
# <a name="determine-the-feature-importance-of-models-with-permutation-feature-importance-in-mlnet"></a>Определение важности признаков моделей с помощью средства Permutation Feature Importance в ML.NET

> [!NOTE]
> В этом разделе описано, как использовать платформу ML.NET, которая сейчас доступна в режиме предварительной версии. Этот материал может быть изменен. Дополнительные сведения см. в [обзоре ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

Сейчас в этих инструкциях и примере используется **ML.NET версии 0.10**. Дополнительные сведения см. в заметках о выпуске в [репозитории GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).

При создании моделей машинного обучения зачастую недостаточно просто делать прогнозы. Часто разработчики машинного обучения, руководители, принимающие решения, и те, на чью работу влияют модели, должны понимать, как модели машинного обучения принимают решения и какие признаки влияют на их эффективность. `Permutation Feature Importance` (PFI) — это инструмент объяснения модели, который корпорация Майкрософт использует, чтобы помочь внутренним разработчикам машинного обучения понять важность признаков моделей.

PFI — это метод определения **глобальной важности признака** в обученной модели машинного обучения, описанный Брейманом в статье о [случайных лесах, раздел 10](https://www.stat.berkeley.edu/~breiman/randomforest2001.pdf). PFI определяет важность признака, задавая следующий вопрос: "Если для признака будут установлены случайные* значение, как это отразится на модели?". Преимущество метода PFI состоит в том, что он не зависит от модели. Он применим к любой модели, которую можно оценить. Кроме того, для определения важности признака он может использовать любой набор данных, не ограничиваясь набором для обучения. С помощью PFI можно получить значения важности признаков, аналогичные представленным на следующем графике:

![График Permutation Feature Importance](./media/determine-global-feature-importance-in-model/pfi-graph.png)

```csharp
// Compute the feature importance using PFI
var permutationMetrics = mlContext.Regression.PermutationFeatureImportance(model.LastTransformer, model.Transform(data), "MedianHomeValue");

// Get the feature names from the training set
var featureNames =
    data.Schema.AsEnumerable()
    .Select(column => column.Name) // Get the column names
    .Where(name => name != "MedianHomeValue") // Drop the Label
    .ToArray();

// Write out the feature names and their importance to the model's Mean R-squared value
for (int i = 0; i < featureNames.Length;i++)
{
    Console.WriteLine($"{featureNames[i]}\t{permutationMetrics[i].RSquared.Mean:G4}");
}
```

Пример анализа важности признака модели с помощью PFI приведен на [сайте GitHub в репозитории dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/samples/Microsoft.ML.Samples/Dynamic/PermutationFeatureImportance).

/* Необязательно случайные, это могут быть переставленные значения в наборе примеров.
