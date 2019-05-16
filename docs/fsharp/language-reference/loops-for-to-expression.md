---
title: Циклы. Выражение for...to
description: См. в разделе как F# for... выражение используется для итерации в цикле по диапазону значений переменной цикла.
ms.date: 05/16/2016
ms.openlocfilehash: 5b7bb9bac659ddf1d457be1ce17e90a2593666de
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645237"
---
# <a name="loops-forto-expression"></a>Циклы. Выражение for...to

`for...to` Выражение используется для циклической итерации по диапазону значений переменной цикла.

## <a name="syntax"></a>Синтаксис

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a>Примечания

Тип идентификатора выводится из типа *запустить* и *Готово* выражения. Типы для этих выражений должны быть 32-разрядных целых чисел.

Несмотря на то что технически выражения, `for...to` больше напоминает традиционный оператор в процедурном языке программирования. Тип возвращаемого значения для *телом выражения* должно быть `unit`. Ниже приведены примеры различных вариантов использования `for...to` выражение.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

Результат выполнения приведенного кода будет следующим.

```
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a>См. также

- [Справочник по языку F#](index.md)
- [Циклы. `for...in` Выражение](loops-for-in-expression.md)
- [Циклы. `while...do` Выражение](loops-while-do-expression.md)
