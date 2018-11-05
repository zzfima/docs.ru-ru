---
title: 'Исключения: функция invalidArg (F#)'
description: Узнайте, как функция «invalidArg» F# создает исключение аргумента.
ms.date: 05/16/2016
ms.openlocfilehash: 8bf65fae9392a88205e3cdec8b7d7a3ff42f8416
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2018
ms.locfileid: "44180323"
---
# <a name="exceptions-the-invalidarg-function"></a>Исключения: функция invalidArg

`invalidArg` Функция создает исключение аргумента.

## <a name="syntax"></a>Синтаксис

```fsharp
invalidArg parameter-name error-message-string
```

## <a name="remarks"></a>Примечания

Имя параметра в предыдущем синтаксисе является строка с именем параметра, аргумент которого был недопустимым. *Строку сообщения об* является строковым литералом или значением типа `string`. Он становится `Message` свойства объекта исключения.

Исключение, вызванное `invalidArg` является `System.ArgumentException` исключение. Следующий код иллюстрирует использование `invalidArg` для создания исключения.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6101.fs)]

Вывод будет следующий, следуют трассировки стека (не показано).

```
December
January
System.ArgumentException: Month parameter out of range.
```

## <a name="see-also"></a>См. также

- [Обработка исключений](index.md)
- [Типы исключения](exception-types.md)
- [Исключения: выражение `try...with`](the-try-with-expression.md)
- [Исключения: выражение `try...finally`](the-try-finally-expression.md)
- [Исключения: функция `raise`](the-raise-function.md)
- [Исключения: функция `failwith`](the-failwith-function.md)
