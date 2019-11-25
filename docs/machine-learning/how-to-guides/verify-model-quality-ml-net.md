---
title: Расчет метрики для оценки качества модели машинного обучения
description: Сведения о том, как рассчитать метрики для оценки и проверки качества модели машинного обучения с помощью ML.NET
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: d6409307cd283ae67d7546c4dc6e19e6089a0766
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975843"
---
# <a name="calculate-metrics-to-evaluate-machine-learning-model-quality"></a>Расчет метрики для оценки качества модели машинного обучения

> [!NOTE]
> В этом разделе описано, как использовать платформу ML.NET, которая сейчас доступна в режиме предварительной версии. Этот материал может быть изменен. Дополнительные сведения см. на странице [ML.NET](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet).

Сейчас в этих инструкциях и примере используется **ML.NET версии 0.10**. Дополнительные сведения см. в заметках о выпуске в [репозитории GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).

Как можно оценить качество после обучения модели? Каждая задача машинного обучения предоставляет метрики для оценки качества.

Для оценки модели вы можете использовать соответствующий "контекст" задачи, как показано в следующем примере:

```csharp
// Read the test dataset.
var testData = reader.Read(testDataPath);
// Calculate metrics of the model on the test data.
var metrics = mlContext.Regression.Evaluate(model.Transform(testData), label: "Target");
```
