---
title: Условные выражения. if... then...else (F#)
description: 'Дополнительные сведения о записи условные выражения на языке F # для выполнения различных ветвей кода.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: bfb985f09be91034894e1d3eba88cebef6bb3fd4
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="conditional-expressions-ifthenelse"></a>Условные выражения. `if...then...else`

`if...then...else` Выражение выполняет различные ветви кода и имеет разные значения в зависимости от заданного логического выражения.


## <a name="syntax"></a>Синтаксис

```fsharp
if boolean-expression then expression1 [ else expression2 ]
```

## <a name="remarks"></a>Примечания
В предыдущем синтаксисе *expression1* выполняется, когда логическое выражение, результатом которого является `true`; в противном случае *expression2* запускает.

В отличие от других языков, `if...then...else` конструктор является выражением, а не оператором. Это означает, что она создает значение, которое является значением последнего выражения в ветвь, для которой выполняется. Типы значений, получаемых в каждой ветви должны совпадать. При наличии без явного указания `else` ветви, но его тип — `unit`. Таким образом Если тип `then` ветвь — любой тип, отличный от `unit`, должно быть `else` с тем же типом возврата ветви. При объединении `if...then...else` выражений, можно использовать ключевое слово `elif` вместо `else if`; они равны.

## <a name="example"></a>Пример
Следующий пример показывает, как использовать `if...then...else` выражение.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4501.fs)]

```
10 is less than 20
What is your name? John
How old are you? 9
You are only 9 years old and already learning F#? Wow!
```

## <a name="see-also"></a>См. также
[Справочник по языку F#](index.md)

