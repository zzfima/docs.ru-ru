---
title: 'Исключения: Функция failwith'
description: Узнайте, как функция «failwith» создает F# исключение.
ms.date: 05/16/2016
ms.openlocfilehash: 05d385ddfc98a910779a6f59949a7187c38f0812
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2018
ms.locfileid: "53610116"
---
# <a name="exceptions-the-failwith-function"></a>Исключения: Функция failwith

`failwith` Функция создает F# исключение.

## <a name="syntax"></a>Синтаксис

```fsharp
failwith error-message-string
```

## <a name="remarks"></a>Примечания

*Строку сообщения об* в предыдущем синтаксисе является строковым литералом или значением типа `string`. Он становится `Message` свойство исключения.

Исключение, создаваемое `failwith` — `System.Exception` исключение, которое представляет собой ссылку с именем `Failure` в F# кода. Следующий код иллюстрирует использование `failwith` для создания исключения.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6001.fs)]

## <a name="see-also"></a>См. также

- [Обработка исключений](index.md)
- [Типы исключения](exception-types.md)
- [Исключения. `try...with` Выражение](the-try-with-expression.md)
- [Исключения. `try...finally` Выражение](the-try-finally-expression.md)
- [Исключения: функция `raise`](the-raise-function.md)