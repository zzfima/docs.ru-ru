---
title: Исключения. Функция failwith (F#)
description: 'Узнайте, как функция «failwith» приводит к возникновению исключения F #.'
ms.date: 05/16/2016
ms.openlocfilehash: 59f7129faf38668dd7390790e22d25f37c129750
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563332"
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
