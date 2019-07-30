---
title: Циклы. Выражение for...to
description: См. раздел F# о... выражение to используется для прохода по циклу над диапазоном значений переменной цикла.
ms.date: 05/16/2016
ms.openlocfilehash: 910c04aa4ea6b2c637dcad147347c1c317b5e0c0
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68626623"
---
# <a name="loops-forto-expression"></a>Циклы. Выражение for...to

`for...to` Выражение используется для прохода по циклу над диапазоном значений переменной цикла.

## <a name="syntax"></a>Синтаксис

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a>Примечания

Тип идентификатора выводится из типа выражений *начала* и *окончания* . Типы для этих выражений должны быть 32-разрядными целыми числами.

Хотя технически это выражение, `for...to` более похоже на традиционный оператор в императивном языке программирования. Тип возвращаемого значения для *выражения тела* должен быть `unit`. В следующих примерах показаны различные варианты использования `for...to` выражения.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

Результат выполнения приведенного кода будет следующим.

```
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a>См. также

- [Справочник по языку F#](index.md)
- [Бираются `for...in`Выражение](loops-for-in-expression.md)
- [Бираются `while...do`Выражение](loops-while-do-expression.md)
