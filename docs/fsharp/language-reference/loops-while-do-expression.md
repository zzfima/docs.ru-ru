---
title: 'Циклы: выражение while...do (F#)'
description: См. в разделе как while... сделать выражение используется для выполнения итерации (в цикле), пока заданное условие теста истинно.
ms.date: 05/16/2016
ms.openlocfilehash: 5cf4461669221f91cb50e238c25494f03a10bbc2
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/13/2018
ms.locfileid: "45517465"
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

>[!NOTE]
Можно использовать `while...do` в выражениях последовательности и другие вычисления выражения, в этом случае настроенную версию `while...do` используется выражение. Дополнительные сведения см. в разделе [последовательностей](sequences.md), [асинхронные рабочие потоки](asynchronous-workflows.md), и [выражения вычисления](computation-expressions.md).

## <a name="see-also"></a>См. также

- [Справочник по языку F#](index.md)
- [Циклы: выражение `for...in`](loops-for-in-expression.md)
- [Циклы: выражение `for...to`](loops-for-to-expression.md)
