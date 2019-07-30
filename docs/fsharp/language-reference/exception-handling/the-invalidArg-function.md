---
title: Исключения. Функция invalidArg
description: Узнайте, F# как функция "invalidArg" создает исключение аргумента.
ms.date: 05/16/2016
ms.openlocfilehash: 010dbfe313f539093b4ee7a19984ef54500b072d
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630304"
---
# <a name="exceptions-the-invalidarg-function"></a>Исключения. Функция invalidArg

`invalidArg` Функция создает исключение аргумента.

## <a name="syntax"></a>Синтаксис

```fsharp
invalidArg parameter-name error-message-string
```

## <a name="remarks"></a>Примечания

Параметр-Name в предыдущем синтаксисе представляет собой строку с именем параметра, аргумент которого был недопустимым. *Строка сообщения Error-Message-* представляет собой литеральную строку или значение типа `string`. Он станет `Message` свойством объекта исключения.

Исключение, созданное `invalidArg` , `System.ArgumentException` является исключением. Следующий код иллюстрирует использование `invalidArg` для создания исключения.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6101.fs)]

Ниже приведены выходные данные, за которыми следует трассировка стека (не показана).

```
December
January
System.ArgumentException: Month parameter out of range.
```

## <a name="see-also"></a>См. также

- [Обработка исключений](index.md)
- [Типы исключения](exception-types.md)
- [Исключения. `try...with` Выражение](the-try-with-expression.md)
- [Исключения. `try...finally` Выражение](the-try-finally-expression.md)
- [Исключения: функция `raise`](the-raise-function.md)
- [Исключения. `failwith` Функция](the-failwith-function.md)
