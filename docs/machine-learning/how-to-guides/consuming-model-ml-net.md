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
# <a name="operationalize-a-trained-machine-learning-model-in-apps---mlnet"></a>Реализация обученной модели машинного обучения в приложениях — ML.NET

> [!NOTE]
> В этом разделе описано, как использовать платформу ML.NET, которая сейчас доступна в режиме предварительной версии. Этот материал может быть изменен. Дополнительные сведения см. в [обзоре ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

Сейчас в этих инструкциях и примере используется **ML.NET версии 0.10**. Дополнительные сведения см. в заметках о выпуске в [репозитории GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).

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
