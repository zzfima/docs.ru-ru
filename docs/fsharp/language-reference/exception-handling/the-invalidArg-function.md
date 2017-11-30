---
title: "Исключения: функция invalidArg (F#)"
description: "Узнайте, как функция «invalidArg» F # создает исключение аргумента."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: d375b704-6b27-493e-bd1d-ee217a53c4b5
ms.openlocfilehash: 107bef361a6bd034e3d6a2227e18cf64b1b04576
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
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
