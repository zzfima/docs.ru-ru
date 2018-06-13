---
title: Циклы. Выражение for...to (F#)
description: '. В разделе как F # оператор for... выражение используется для перебора в цикле диапазона значений переменной цикла.'
ms.date: 05/16/2016
ms.openlocfilehash: 841c7d557abc11e0253cb87ab8081cc77671b44b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563406"
---
# <a name="loops-forto-expression"></a>Циклы. Выражение for...to

`for...to` Выражение используется для перебора в цикле диапазона значений переменной цикла.


## <a name="syntax"></a>Синтаксис

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a>Примечания
Тип идентификатора выводится из типа *запустить* и *Готово* выражения. Типы для этих выражений должны быть 32-разрядных целых чисел.

Несмотря на то что технически выражения, `for...to` — это больше похоже на традиционный оператор в императивном языке программирования. Тип возвращаемого значения для *выражение тела* должен быть `unit`. В следующих примерах показано различные способы использования `for...to` выражение.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

Результат выполнения приведенного кода будет следующим.

```
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a>См. также
[Справочник по языку F#](index.md)

[Циклы: выражение `for...in`](loops-for-in-expression.md)

[Циклы: выражение `while...do`](loops-while-do-expression.md)
