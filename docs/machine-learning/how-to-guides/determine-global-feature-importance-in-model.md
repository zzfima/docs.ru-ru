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
# <a name="determine-the-feature-importance-of-models-with-permutation-feature-importance-in-mlnet"></a><span data-ttu-id="5b2ec-103">Определение важности признаков моделей с помощью средства Permutation Feature Importance в ML.NET</span><span class="sxs-lookup"><span data-stu-id="5b2ec-103">Determine the feature importance of models with Permutation Feature Importance in ML.NET</span></span>

<span data-ttu-id="5b2ec-104">При создании моделей машинного обучения зачастую недостаточно просто делать прогнозы.</span><span class="sxs-lookup"><span data-stu-id="5b2ec-104">When creating machine learning models, it is often not enough to simply make predictions.</span></span> <span data-ttu-id="5b2ec-105">Часто разработчики машинного обучения, руководители, принимающие решения, и те, на чью работу влияют модели, должны понимать, как модели машинного обучения принимают решения и какие признаки влияют на их эффективность.</span><span class="sxs-lookup"><span data-stu-id="5b2ec-105">Often, machine learning developers, decision makers, and those affected by the models need to understand how machine learning models make decisions and which features contribute to their performance.</span></span> <span data-ttu-id="5b2ec-106">`Permutation Feature Importance` (PFI) — это инструмент объяснения модели, который корпорация Майкрософт использует, чтобы помочь внутренним разработчикам машинного обучения понять важность признаков моделей.</span><span class="sxs-lookup"><span data-stu-id="5b2ec-106">`Permutation Feature Importance` (PFI) is a model explainability tool that is used internally at Microsoft to help machine learning developers better understand the feature importance of models.</span></span>

<span data-ttu-id="5b2ec-107">PFI — это метод определения **глобальной важности признака** в обученной модели машинного обучения, описанный Брейманом в статье о [случайных лесах, раздел 10](https://www.stat.berkeley.edu/~breiman/randomforest2001.pdf).</span><span class="sxs-lookup"><span data-stu-id="5b2ec-107">PFI is a technique to determine **global feature importance** in a trained machine learning model, motivated by Breiman in the ["Random Forests" paper, section 10](https://www.stat.berkeley.edu/~breiman/randomforest2001.pdf).</span></span> <span data-ttu-id="5b2ec-108">PFI определяет важность признака, задавая следующий вопрос: "Если для признака будут установлены случайные\* значение, как это отразится на модели?".</span><span class="sxs-lookup"><span data-stu-id="5b2ec-108">PFI measures feature importance by asking the question, "What would the effect on the model be if the values for a feature were set to a random\* value?".</span></span> <span data-ttu-id="5b2ec-109">Преимущество метода PFI состоит в том, что он не зависит от модели. Он применим к любой модели, которую можно оценить. Кроме того, для определения важности признака он может использовать любой набор данных, не ограничиваясь набором для обучения.</span><span class="sxs-lookup"><span data-stu-id="5b2ec-109">The advantage of the PFI method is that it is model agnostic — it works with any model that can be evaluated — and it can use any dataset, not just the training set, to compute feature importance.</span></span> <span data-ttu-id="5b2ec-110">С помощью PFI можно получить значения важности признаков, аналогичные представленным на следующем графике:</span><span class="sxs-lookup"><span data-stu-id="5b2ec-110">You can use PFI like so to produce feature importances like this graph:</span></span>

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

<span data-ttu-id="5b2ec-112">Пример анализа важности признака модели с помощью PFI приведен на [сайте GitHub в репозитории dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/samples/Microsoft.ML.Samples/Dynamic/PermutationFeatureImportance).</span><span class="sxs-lookup"><span data-stu-id="5b2ec-112">For a sample using PFI to analyze the feature importance of a model, see [the dotnet/machinelearning GitHub repository](https://github.com/dotnet/machinelearning/tree/master/docs/samples/Microsoft.ML.Samples/Dynamic/PermutationFeatureImportance).</span></span>

<span data-ttu-id="5b2ec-113">/\* Необязательно случайные, это могут быть переставленные значения в наборе примеров.</span><span class="sxs-lookup"><span data-stu-id="5b2ec-113">/\* Well, not random exactly, but permuted across the set of examples.</span></span>
