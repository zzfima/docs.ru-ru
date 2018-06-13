---
title: 'Лямбда-выражения: ключевое слово fun (F#)'
description: 'Сведения об использовании ключевого слова «fun» F # для определения лямбда-выражения, который является анонимной функцией.'
ms.date: 05/16/2016
ms.openlocfilehash: 433451fb9bf89bfabdcd8e71560105317771d251
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563854"
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
