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
# <a name="determine-the-feature-importance-of-models-with-permutation-feature-importance-in-mlnet"></a><span data-ttu-id="1b413-103">Определение важности признаков моделей с помощью средства Permutation Feature Importance в ML.NET</span><span class="sxs-lookup"><span data-stu-id="1b413-103">Determine the feature importance of models with Permutation Feature Importance in ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="1b413-104">В этом разделе описано, как использовать платформу ML.NET, которая сейчас доступна в режиме предварительной версии. Этот материал может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="1b413-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="1b413-105">Дополнительные сведения см. в [обзоре ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="1b413-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="1b413-106">Сейчас в этих инструкциях и примере используется **ML.NET версии 0.10**.</span><span class="sxs-lookup"><span data-stu-id="1b413-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="1b413-107">Дополнительные сведения см. в заметках о выпуске в [репозитории GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="1b413-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="1b413-108">При создании моделей машинного обучения зачастую недостаточно просто делать прогнозы.</span><span class="sxs-lookup"><span data-stu-id="1b413-108">When creating machine learning models, it is often not enough to simply make predictions.</span></span> <span data-ttu-id="1b413-109">Часто разработчики машинного обучения, руководители, принимающие решения, и те, на чью работу влияют модели, должны понимать, как модели машинного обучения принимают решения и какие признаки влияют на их эффективность.</span><span class="sxs-lookup"><span data-stu-id="1b413-109">Often, machine learning developers, decision makers, and those affected by the models need to understand how machine learning models make decisions and which features contribute to their performance.</span></span> <span data-ttu-id="1b413-110">`Permutation Feature Importance` (PFI) — это инструмент объяснения модели, который корпорация Майкрософт использует, чтобы помочь внутренним разработчикам машинного обучения понять важность признаков моделей.</span><span class="sxs-lookup"><span data-stu-id="1b413-110">`Permutation Feature Importance` (PFI) is a model explainability tool that is used internally at Microsoft to help machine learning developers better understand the feature importance of models.</span></span>

<span data-ttu-id="1b413-111">PFI — это метод определения **глобальной важности признака** в обученной модели машинного обучения, описанный Брейманом в статье о [случайных лесах, раздел 10](https://www.stat.berkeley.edu/~breiman/randomforest2001.pdf).</span><span class="sxs-lookup"><span data-stu-id="1b413-111">PFI is a technique to determine **global feature importance** in a trained machine learning model, motivated by Breiman in the ["Random Forests" paper, section 10](https://www.stat.berkeley.edu/~breiman/randomforest2001.pdf).</span></span> <span data-ttu-id="1b413-112">PFI определяет важность признака, задавая следующий вопрос: "Если для признака будут установлены случайные\* значение, как это отразится на модели?".</span><span class="sxs-lookup"><span data-stu-id="1b413-112">PFI measures feature importance by asking the question, "What would the effect on the model be if the values for a feature were set to a random\* value?".</span></span> <span data-ttu-id="1b413-113">Преимущество метода PFI состоит в том, что он не зависит от модели. Он применим к любой модели, которую можно оценить. Кроме того, для определения важности признака он может использовать любой набор данных, не ограничиваясь набором для обучения.</span><span class="sxs-lookup"><span data-stu-id="1b413-113">The advantage of the PFI method is that it is model agnostic — it works with any model that can be evaluated — and it can use any dataset, not just the training set, to compute feature importance.</span></span> <span data-ttu-id="1b413-114">С помощью PFI можно получить значения важности признаков, аналогичные представленным на следующем графике:</span><span class="sxs-lookup"><span data-stu-id="1b413-114">You can use PFI like so to produce feature importances like this graph:</span></span>

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

<span data-ttu-id="1b413-116">Пример анализа важности признака модели с помощью PFI приведен на [сайте GitHub в репозитории dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/samples/Microsoft.ML.Samples/Dynamic/PermutationFeatureImportance).</span><span class="sxs-lookup"><span data-stu-id="1b413-116">For a sample using PFI to analyze the feature importance of a model, see [the dotnet/machinelearning GitHub repository](https://github.com/dotnet/machinelearning/tree/master/docs/samples/Microsoft.ML.Samples/Dynamic/PermutationFeatureImportance).</span></span>

<span data-ttu-id="1b413-117">/\* Необязательно случайные, это могут быть переставленные значения в наборе примеров.</span><span class="sxs-lookup"><span data-stu-id="1b413-117">/\* Well, not random exactly, but permuted across the set of examples.</span></span>
