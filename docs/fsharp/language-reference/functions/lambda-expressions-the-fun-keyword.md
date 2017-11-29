---
title: "Лямбда-выражения: ключевое слово fun (F#)"
description: "Сведения об использовании ключевого слова «fun» F # для определения лямбда-выражения, который является анонимной функцией."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: e5d3565c-d7cc-433f-a619-886ed92523a7
ms.openlocfilehash: 09f1c1787bbb4b86ec40f9e973e08104919631aa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
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
