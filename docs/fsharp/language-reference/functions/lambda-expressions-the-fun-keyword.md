---
title: 'Лямбда-выражения: ключевое слово fun (F#)'
description: 'Сведения об использовании ключевого слова «fun» F # для определения лямбда-выражения, который является анонимной функцией.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: f2f15a1b482ce3971d0b3d5ffc4f6dcc9ccf1569
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="lambda-expressions-the-fun-keyword-f"></a>Лямбда-выражения: ключевое слово fun (F#)

`fun` Ключевое слово используется для определения лямбда-выражение, то есть анонимную функцию.


## <a name="syntax"></a>Синтаксис

```fsharp
fun parameter-list -> expression
```

## <a name="remarks"></a>Примечания
*Список параметров* обычно состоит из имен и, возможно, типы параметров. Как правило *список параметров* может состоять из любых шаблонов F #. Полный список возможных шаблонов см. в разделе [соответствие шаблону](../pattern-matching.md). Примеры списков допустимых параметров.

```fsharp
// Lambda expressions with parameter lists.
fun a b c -> ...
fun (a: int) b c -> ...
fun (a : int) (b : string) (c:float) -> ...

// A lambda expression with a tuple pattern.
fun (a, b) -> …

// A lambda expression with a list pattern.
fun head :: tail -> …
```

*Выражение* является тело функции, последнее выражение которого формирует возвращаемое значение. Примеры допустимых лямбда-выражений:

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet301.fs)]
    
## <a name="using-lambda-expressions"></a>Использование лямбда-выражений
Лямбда-выражения особенно полезны, когда требуется выполнять операции над списком или других коллекций и требуется избежать лишней работы — определения функции. Многие функции библиотеки F # принимают значения функций в качестве аргументов и может быть особенно удобно использовать в тех случаях, лямбда-выражения. Следующий код лямбда-выражение применяется к элементам списка. В этом случае анонимная функция добавляет 1 к каждому элементу списка.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet302.fs)]
    
## <a name="see-also"></a>См. также
[Функции](index.md)
