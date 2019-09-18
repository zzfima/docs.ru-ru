---
title: Расчет метрики для оценки качества модели машинного обучения
description: Сведения о том, как рассчитать метрики для оценки и проверки качества модели машинного обучения с помощью ML.NET
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 529003913b166c966e131b006800f944096605b7
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855561"
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
