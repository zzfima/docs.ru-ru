---
title: Циклы. Выражение for...to
description: См. раздел F# о... выражение to используется для прохода по циклу над диапазоном значений переменной цикла.
ms.date: 05/16/2016
ms.openlocfilehash: 882b6e48dd09efcb57f7ef2f419e68a6c43393a5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283906"
---
# <a name="loops-forto-expression"></a>Циклы. Выражение for...to

Выражение `for...to` используется для прохода по циклу над диапазоном значений переменной цикла.

## <a name="syntax"></a>Синтаксис

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a>Заметки

Тип идентификатора выводится из типа выражений *начала* и *окончания* . Типы для этих выражений должны быть 32-разрядными целыми числами.

Хотя технически это выражение, `for...to` более похоже на традиционный оператор в императивном языке программирования. Тип возвращаемого значения для *выражения тела* должен быть `unit`. В следующих примерах показаны различные варианты использования выражения `for...to`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

Результат выполнения приведенного кода будет следующим.

```console
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a>См. также

- [Справочник по языку F#](index.md)
- [Циклы: выражение `for...in`](loops-for-in-expression.md)
- [Циклы: выражение `while...do`](loops-while-do-expression.md)
