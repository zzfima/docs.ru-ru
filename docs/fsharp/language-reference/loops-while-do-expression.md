---
title: 'Циклы: выражение while...do'
description: См. в разделе как while... сделать выражение используется для выполнения итерации (в цикле), пока заданное условие теста истинно.
ms.date: 05/16/2016
ms.openlocfilehash: d2a77e0bfefe3b6b026012e6b2938ba670326bcf
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2018
ms.locfileid: "53613015"
---
# <a name="loops-whiledo-expression"></a>Циклы: выражение while...do

`while...do` Выражение используется для выполнения итерации (в цикле), пока заданное условие теста истинно.

## <a name="syntax"></a>Синтаксис

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a>Примечания

*Тестовое выражение* вычисляется; Если это `true`, *телом выражения* выполняется и снова вычисляется выражение. *Телом выражения* должен иметь тип `unit`. Если выражение является `false`, завершения итерации.

Следующий пример иллюстрирует использование `while...do` выражение.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

Результат выполнения предыдущего кода — это поток случайных чисел от 1 до 20, последнее из которых — 10.

```
13 19 8 18 16 2 10
Found a 10!
```

> [!NOTE]
> Можно использовать `while...do` в выражениях последовательности и другие вычисления выражения, в этом случае настроенную версию `while...do` используется выражение. Дополнительные сведения см. в разделе [последовательностей](sequences.md), [асинхронные рабочие потоки](asynchronous-workflows.md), и [выражения вычисления](computation-expressions.md).

## <a name="see-also"></a>См. также

- [Справочник по языку F#](index.md)
- [Циклы. `for...in` Выражение](loops-for-in-expression.md)
- [Циклы. `for...to` Выражение](loops-for-to-expression.md)