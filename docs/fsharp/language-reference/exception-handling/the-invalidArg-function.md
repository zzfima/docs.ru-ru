---
title: 'Исключения: функция invalidArg (F#)'
description: 'Узнайте, как функция «invalidArg» F # создает исключение аргумента.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.assetid: d375b704-6b27-493e-bd1d-ee217a53c4b5
ms.openlocfilehash: fc7b1d25adf71bc1704a3f2db4359006f0ba1670
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
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
