---
title: 'Условные выражения: if... затем... Кроме'
description: Сведения о написании условных выражений F# в для выполнения различных ветвей кода.
ms.date: 05/16/2016
ms.openlocfilehash: d9763f37cd9170c42e968282b54a3ce925e92591
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2019
ms.locfileid: "71083022"
---
# <a name="conditional-expressions-ifthenelse"></a>Условные выражения:`if...then...else`

`if...then...else` Выражение выполняет различные ветви кода, а также вычисляет различные значения в зависимости от заданного логического выражения.

## <a name="syntax"></a>Синтаксис

```fsharp
if boolean-expression then expression1 [ else expression2 ]
```

## <a name="remarks"></a>Примечания

В предыдущем синтаксисе *expression1* выполняется, когда логическое выражение принимает `true`значение; в противном случае — *Expression2* .

В отличие от других языков, `if...then...else` конструкция является выражением, а не оператором. Это означает, что он создает значение, которое является значением последнего выражения в ветви, в которой выполняется. Типы значений, создаваемых в каждой ветви, должны совпадать. Если явная `else` ветвь отсутствует, ее тип — `unit`. Поэтому, если тип `then` ветви отличается от `unit`типа `else` , необходимо наличие ветви с таким же типом возвращаемого значения. При совместном `if...then...else` связывании выражений можно использовать ключевое слово `elif` , а `else if`не. они эквивалентны.

## <a name="example"></a>Пример

В следующем примере показано, `if...then...else` как использовать выражение.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4501.fs)]

```console
10 is less than 20
What is your name? John
How old are you? 9
You are only 9 years old and already learning F#? Wow!
```

## <a name="see-also"></a>См. также

- [Справочник по языку F#](index.md)
