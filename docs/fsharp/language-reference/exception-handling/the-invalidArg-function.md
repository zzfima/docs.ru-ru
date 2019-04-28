---
title: 'Исключения: Функция invalidArg'
description: Узнайте, как F# «invalidArg» функция создает исключение аргумента.
ms.date: 05/16/2016
ms.openlocfilehash: 7fd8d48b80970dbbafc0c23a478b4ccf3490f3ee
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61996889"
---
# <a name="exceptions-the-invalidarg-function"></a>Исключения: Функция invalidArg

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
- [Исключения. `try...with` Выражение](the-try-with-expression.md)
- [Исключения. `try...finally` Выражение](the-try-finally-expression.md)
- [Исключения: функция `raise`](the-raise-function.md)
- [Исключения. `failwith` Функции](the-failwith-function.md)