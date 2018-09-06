---
title: Условные выражения. if... then...else (F#)
description: 'Вы можете научиться писать условных выражений в F # для выполнения различных ветвей кода.'
ms.date: 05/16/2016
ms.openlocfilehash: 10e4224bef772f00520cf5a0fff2f2920147c2fc
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43890873"
---
# <a name="conditional-expressions-ifthenelse"></a>Условные выражения. `if...then...else`

`if...then...else` Выражение выполняет различные ветви кода и имеет другое значение в зависимости от заданного логического выражения.

## <a name="syntax"></a>Синтаксис

```fsharp
if boolean-expression then expression1 [ else expression2 ]
```

## <a name="remarks"></a>Примечания

В приведенном выше синтаксисе *expression1* выполняется, когда логическое выражение, результатом которого является `true`; в противном случае *expression2* выполняется.

В отличие от других языков, `if...then...else` конструкция представляет собой выражение, а не оператором. Это означает, что она формирует значение, которое является значением последнего выражения в ветвь, которая выполняет. Типы значений, получаемых в каждой ветви должны совпадать. Если имеется без явного указания `else` ветви, его тип — `unit`. Таким образом Если тип `then` ветвь — это любой тип, отличное от `unit`, должна существовать `else` ветви с тем же типом возвращаемого значения. При объединении в `if...then...else` выражений, можно использовать ключевое слово `elif` вместо `else if`; они равны.

## <a name="example"></a>Пример

В следующем примере показано, как использовать `if...then...else` выражение.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4501.fs)]

```
10 is less than 20
What is your name? John
How old are you? 9
You are only 9 years old and already learning F#? Wow!
```

## <a name="see-also"></a>См. также

- [Справочник по языку F#](index.md)
