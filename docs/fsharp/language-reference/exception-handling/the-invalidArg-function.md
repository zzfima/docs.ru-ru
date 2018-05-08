---
title: 'Исключения: функция invalidArg (F#)'
description: 'Узнайте, как функция «invalidArg» F # создает исключение аргумента.'
ms.date: 05/16/2016
ms.openlocfilehash: 43e1b6f3f36774ac50aeff147f75f133d6e3e5dc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="exceptions-the-invalidarg-function"></a>Исключения: функция invalidArg

`invalidArg` Функция создает исключение аргумента.


## <a name="syntax"></a>Синтаксис

```fsharp
invalidArg parameter-name error-message-string
```

## <a name="remarks"></a>Примечания
Имя параметра в предыдущем синтаксисе — это строка с именем параметра, аргумент которого был недопустимым. *Строка сообщения об* является строковым литералом или значением типа `string`. Оно становится `Message` свойства объекта исключения.

Исключение, вызванное `invalidArg` — `System.ArgumentException` исключение. Следующий код иллюстрирует использование `invalidArg` создаст исключение.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6101.fs)]

Выходные данные выглядят следующим образом, следуют трассировки стека (не показано).

```
December
January
System.ArgumentException: Month parameter out of range.
```

## <a name="see-also"></a>См. также
[Обработка исключений](index.md)

[Типы исключения](exception-types.md)

[Исключения: выражение `try...with`](the-try-with-expression.md)

[Исключения: выражение `try...finally`](the-try-finally-expression.md)

[Исключения: функция `raise`](the-raise-function.md)

[Исключения: функция `failwith`](the-failwith-function.md)
