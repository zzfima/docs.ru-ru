---
title: Исключения. Функция failwith (F#)
description: 'Узнайте, как функция «failwith» создает исключение F #.'
ms.date: 05/16/2016
ms.openlocfilehash: 69a2eb69e0157d3bde8cb8884cb0ae960634dddc
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863433"
---
# <a name="exceptions-the-failwith-function"></a>Исключения. Функция failwith

`failwith` Функция создает исключение F #.

## <a name="syntax"></a>Синтаксис

```fsharp
failwith error-message-string
```

## <a name="remarks"></a>Примечания

*Строку сообщения об* в предыдущем синтаксисе является строковым литералом или значением типа `string`. Он становится `Message` свойство исключения.

Исключение, создаваемое `failwith` — `System.Exception` исключение, которое представляет собой ссылку с именем `Failure` в коде F #. Следующий код иллюстрирует использование `failwith` для создания исключения.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6001.fs)]

## <a name="see-also"></a>См. также

- [Обработка исключений](index.md)
- [Типы исключения](exception-types.md)
- [Исключения: выражение `try...with`](the-try-with-expression.md)
- [Исключения: выражение `try...finally`](the-try-finally-expression.md)
- [Исключения: функция `raise`](the-raise-function.md)
