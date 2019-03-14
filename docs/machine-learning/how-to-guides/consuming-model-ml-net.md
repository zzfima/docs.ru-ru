---
title: Реализация обученной модели машинного обучения в приложениях — ML.NET
description: Узнайте, как применять модель для использования обученной и вычисленной модели машинного обучения в приложениях с помощью ML.NET
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: be6906c939b82d00067babaeebe809dae3de413a
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/08/2019
ms.locfileid: "57675138"
---
# <a name="operationalize-a-trained-machine-learning-model-in-apps---mlnet"></a><span data-ttu-id="b12e5-103">Реализация обученной модели машинного обучения в приложениях — ML.NET</span><span class="sxs-lookup"><span data-stu-id="b12e5-103">Operationalize a trained machine learning model in apps - ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="b12e5-104">В этом разделе описано, как использовать платформу ML.NET, которая сейчас доступна в режиме предварительной версии. Этот материал может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="b12e5-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="b12e5-105">Дополнительные сведения см. в [обзоре ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="b12e5-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="b12e5-106">Сейчас в этих инструкциях и примере используется **ML.NET версии 0.10**.</span><span class="sxs-lookup"><span data-stu-id="b12e5-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="b12e5-107">Дополнительные сведения см. в заметках о выпуске в [репозитории GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="b12e5-107">For more information, see the release notes at the [dotnet/machinelearning github repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)</span></span>

<span data-ttu-id="b12e5-108">Получив требуемые метрики модели, можно приступать к реализации модели.</span><span class="sxs-lookup"><span data-stu-id="b12e5-108">When the model metrics look good to you, it's time to 'operationalize' the model.</span></span> <span data-ttu-id="b12e5-109">Созданный объект `model` можно использовать, хранить и повторно использовать в разных средах, применяя изученные во время обучения действия.</span><span class="sxs-lookup"><span data-stu-id="b12e5-109">The `model` object you built can be consumed, persisted, and reused in different environments, applying the same steps that it 'learned' during training.</span></span>

<span data-ttu-id="b12e5-110">Чтобы сохранить модель в файле и перезагрузить ее (возможно, в другом контексте), используйте следующий пример:</span><span class="sxs-lookup"><span data-stu-id="b12e5-110">To save the model to a file, and reload it (potentially in a different context), use the following example:</span></span>

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
