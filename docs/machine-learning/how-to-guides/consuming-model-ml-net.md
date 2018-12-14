---
title: Реализация обученной модели машинного обучения в приложениях — ML.NET
description: Узнайте, как применять модель для использования обученной и вычисленной модели машинного обучения в приложениях с помощью ML.NET
ms.date: 11/07/2018
ms.custom: mvc,how-to
ms.openlocfilehash: ff3f0a8856382d020129693bcf722f572fd87606
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53131648"
---
# <a name="operationalize-a-trained-machine-learning-model-in-apps---mlnet"></a>Реализация обученной модели машинного обучения в приложениях — ML.NET

Получив требуемые метрики модели, можно приступать к реализации модели. Созданный объект `model` можно использовать, хранить и повторно использовать в разных средах, применяя изученные во время обучения действия.

Чтобы сохранить модель в файле и перезагрузить ее (возможно, в другом контексте), используйте следующий пример:

```csharp
using (var stream = File.Create(modelPath))
{
    // Saving and loading happens to 'dynamic' models.
    mlContext.Model.Save(model, stream);
}

// Potentially, the lines below can be in a different process altogether.

// When you load the model, it's a transformer.
ITransformer loadedModel;
using (var stream = File.OpenRead(modelPath))
    loadedModel = mlContext.Model.Load(stream);
```
