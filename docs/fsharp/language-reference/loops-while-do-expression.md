---
title: 'Циклы: выражение while...do (F#)'
description: В разделе как while... выполните выражение используется для выполнения итерации (в цикле), пока заданное проверяемое условие имеет значение true.
ms.date: 05/16/2016
ms.openlocfilehash: e3198246e44bbb11b226f04da6795f3da22626e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562236"
---
# <a name="loops-whiledo-expression"></a>Циклы: выражение while...do

`while...do` Выражение используется для выполнения итерации (в цикле), пока заданное проверяемое условие имеет значение true.


## <a name="syntax"></a>Синтаксис

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a>Примечания
*Тестовое выражение* вычисляется; Если это `true`, *выражение тела* выполняется и снова вычисляется выражение. *Выражение тела* должен иметь тип `unit`. Если выражение является `false`, окончания итерации.

Следующий пример иллюстрирует использование `while...do` выражение.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

Результат выполнения предыдущего кода является поток случайных чисел от 1 до 20, последнее из которых — 10.

```
13 19 8 18 16 2 10
Found a 10!
```

>[!NOTE] 
Можно использовать `while...do` в выражениях последовательности и других вычислительных выражениях, при этом настроенную версию `while...do` используется выражение. Дополнительные сведения см. в разделе [последовательности](sequences.md), [асинхронные рабочие потоки](asynchronous-workflows.md), и [вычислительных выражениях](computation-expressions.md).


## <a name="see-also"></a>См. также
[Справочник по языку F#](index.md)

[Циклы: выражение `for...in`](loops-for-in-expression.md)

[Циклы: выражение `for...to`](loops-for-to-expression.md)
