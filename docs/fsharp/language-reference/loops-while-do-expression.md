---
title: "Циклы: выражение while...do (F#)"
description: "В разделе как while... выполните выражение используется для выполнения итерации (в цикле), пока заданное проверяемое условие имеет значение true."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 0416ffca-7ed9-4aff-9493-e001fdba8c9b
ms.openlocfilehash: 5f10fda84a5e748856eb7b2c63ad46cc1fba44bb
ms.sourcegitcommit: 8ed4ebc15b5ef89d06a7507dc9d5e306e30accf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2017
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
