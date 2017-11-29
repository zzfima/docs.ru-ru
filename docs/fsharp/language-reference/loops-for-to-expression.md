---
title: "Циклы. Выражение for...to (F#)"
description: ". В разделе как F # оператор for... выражение используется для перебора в цикле диапазона значений переменной цикла."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: e14c38d9-b1ef-4b7f-be9a-fb6ef6708e02
ms.openlocfilehash: 1a1d71d30b5e87e4691a78acd5032de9419399db
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
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
