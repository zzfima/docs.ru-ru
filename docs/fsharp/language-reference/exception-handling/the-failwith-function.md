---
title: Исключения. Функция failwith
description: Узнайте, как функция "FailWith" создает F# исключение.
ms.date: 05/16/2016
ms.openlocfilehash: f2c86362d5bdde7bab55751f019965a5f4ca6236
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630327"
---
# <a name="exceptions-the-failwith-function"></a>Исключения. Функция failwith

`failwith` Функция создает F# исключение.

## <a name="syntax"></a>Синтаксис

```fsharp
failwith error-message-string
```

## <a name="remarks"></a>Примечания

*Строка Error-Message-* в предыдущем синтаксисе представляет собой литеральную строку или значение типа `string`. Он станет `Message` свойством исключения.

Исключение, формируемое `failwith` , `System.Exception` — это исключение, которое представляет собой ссылку с именем `Failure` в F# коде. Следующий код иллюстрирует использование `failwith` для создания исключения.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6001.fs)]

## <a name="see-also"></a>См. также

- [Обработка исключений](index.md)
- [Типы исключения](exception-types.md)
- [Исключения. `try...with` Выражение](the-try-with-expression.md)
- [Исключения. `try...finally` Выражение](the-try-finally-expression.md)
- [Исключения: функция `raise`](the-raise-function.md)
