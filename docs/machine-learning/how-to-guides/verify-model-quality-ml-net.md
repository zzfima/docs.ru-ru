---
title: Расчет метрик для оценки качества модели машинного обучения — ML.NET
description: Сведения о том, как рассчитать метрики для оценки и проверки качества модели машинного обучения с помощью ML.NET
ms.date: 11/07/2018
ms.custom: mvc,how-to
ms.openlocfilehash: 6fd4dfab6104b4398918e42ed70584b04169a8c1
ms.sourcegitcommit: 35316b768394e56087483cde93f854ba607b63bc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2018
ms.locfileid: "52297571"
---
# <a name="calculate-metrics-to-evaluate-machine-learning-model-quality---mlnet"></a>Расчет метрик для оценки качества модели машинного обучения — ML.NET

Как можно оценить качество после обучения модели? Каждая задача машинного обучения предоставляет метрики для оценки качества.

Для оценки модели вы можете использовать соответствующий "контекст" задачи, как показано в следующем примере:

```csharp
// Read the test dataset.
var testData = reader.Read(testDataPath);
// Calculate metrics of the model on the test data.
var metrics = mlContext.Regression.Evaluate(model.Transform(testData), label: "Target");
```