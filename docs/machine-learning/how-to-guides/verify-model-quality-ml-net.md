---
title: Расчет метрики для оценки качества модели машинного обучения
description: Сведения о том, как рассчитать метрики для оценки и проверки качества модели машинного обучения с помощью ML.NET
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 2c7749205b862a42f42b857972057c441ab84364
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641097"
---
# <a name="calculate-metrics-to-evaluate-machine-learning-model-quality"></a><span data-ttu-id="a589d-103">Расчет метрики для оценки качества модели машинного обучения</span><span class="sxs-lookup"><span data-stu-id="a589d-103">Calculate metrics to evaluate machine learning model quality</span></span> 

> [!NOTE]
> <span data-ttu-id="a589d-104">В этом разделе описано, как использовать платформу ML.NET, которая сейчас доступна в режиме предварительной версии. Этот материал может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="a589d-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="a589d-105">Дополнительные сведения см. в [обзоре ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="a589d-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="a589d-106">Сейчас в этих инструкциях и примере используется **ML.NET версии 0.10**.</span><span class="sxs-lookup"><span data-stu-id="a589d-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="a589d-107">Дополнительные сведения см. в заметках о выпуске в [репозитории GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="a589d-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="a589d-108">Как можно оценить качество после обучения модели?</span><span class="sxs-lookup"><span data-stu-id="a589d-108">How do you evaluate quality after you train the model?</span></span> <span data-ttu-id="a589d-109">Каждая задача машинного обучения предоставляет метрики для оценки качества.</span><span class="sxs-lookup"><span data-stu-id="a589d-109">Each machine learning task exposes metrics for quality evaluation.</span></span>

<span data-ttu-id="a589d-110">Для оценки модели вы можете использовать соответствующий "контекст" задачи, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="a589d-110">You can use the corresponding 'context' of the task to evaluate the model, as in the following example:</span></span>

```csharp
// Read the test dataset.
var testData = reader.Read(testDataPath);
// Calculate metrics of the model on the test data.
var metrics = mlContext.Regression.Evaluate(model.Transform(testData), label: "Target");
```
