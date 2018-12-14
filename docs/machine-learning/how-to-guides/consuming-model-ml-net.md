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
# <a name="operationalize-a-trained-machine-learning-model-in-apps---mlnet"></a><span data-ttu-id="21525-103">Реализация обученной модели машинного обучения в приложениях — ML.NET</span><span class="sxs-lookup"><span data-stu-id="21525-103">Operationalize a trained machine learning model in apps - ML.NET</span></span>

<span data-ttu-id="21525-104">Получив требуемые метрики модели, можно приступать к реализации модели.</span><span class="sxs-lookup"><span data-stu-id="21525-104">When the model metrics look good to you, it's time to 'operationalize' the model.</span></span> <span data-ttu-id="21525-105">Созданный объект `model` можно использовать, хранить и повторно использовать в разных средах, применяя изученные во время обучения действия.</span><span class="sxs-lookup"><span data-stu-id="21525-105">The `model` object you built can be consumed, persisted, and reused in different environments, applying the same steps that it 'learned' during training.</span></span>

<span data-ttu-id="21525-106">Чтобы сохранить модель в файле и перезагрузить ее (возможно, в другом контексте), используйте следующий пример:</span><span class="sxs-lookup"><span data-stu-id="21525-106">To save the model to a file, and reload it (potentially in a different context), use the following example:</span></span>

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
