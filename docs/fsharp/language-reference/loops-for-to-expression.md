---
title: Циклы. Выражение for...to (F#)
description: См. в разделе как F# for... выражение используется для итерации в цикле по диапазону значений переменной цикла.
ms.date: 05/16/2016
ms.openlocfilehash: 8160fd30c4f3afe8bb6b58f468802ef1c0ef32ee
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2018
ms.locfileid: "43800473"
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
- [Циклы: выражение `for...in`](loops-for-in-expression.md)
- [Циклы: выражение `while...do`](loops-while-do-expression.md)
