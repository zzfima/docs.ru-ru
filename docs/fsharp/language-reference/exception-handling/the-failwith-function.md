---
title: "Исключения. Функция failwith (F#)"
description: "Узнайте, как функция «failwith» приводит к возникновению исключения F #."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 2e0c1f28-cc6c-4ecd-bb93-3816c4dd7cd3
ms.openlocfilehash: 295a4d754e0df015ba67daa9cf80d7df5b40199c
ms.sourcegitcommit: ffb9aa26cd5211dc6d96ebb42968d8357048880e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2017
---
# <a name="exceptions-the-failwith-function"></a>Исключения. Функция failwith

`failwith` Функция создает исключение F #.


## <a name="syntax"></a>Синтаксис

```fsharp
failwith error-message-string
```

## <a name="remarks"></a>Примечания
*Строка сообщения об* в предыдущем синтаксисе является строковым литералом или значением типа `string`. Оно становится `Message` свойства исключения.

Исключение, создаваемое `failwith` — `System.Exception` исключение, которое является ссылкой с именем `Failure` в коде F #. Следующий код иллюстрирует использование `failwith` создаст исключение.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6001.fs)]
    
## <a name="see-also"></a>См. также
[Обработка исключений](index.md)

[Типы исключения](exception-types.md)

[Исключения: выражение `try...with`](the-try-with-expression.md)

[Исключения: выражение `try...finally`](the-try-finally-expression.md)

[Исключения: функция `raise`](the-raise-function.md)
