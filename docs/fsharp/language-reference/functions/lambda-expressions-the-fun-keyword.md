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
# <a name="lambda-expressions-the-fun-keyword-f"></a><span data-ttu-id="f0456-103">Лямбда-выражения: ключевое слово fun (F#)</span><span class="sxs-lookup"><span data-stu-id="f0456-103">Lambda Expressions: The fun Keyword (F#)</span></span>

<span data-ttu-id="f0456-104">`fun` Ключевое слово используется для определения лямбда-выражение, то есть анонимную функцию.</span><span class="sxs-lookup"><span data-stu-id="f0456-104">The `fun` keyword is used to define a lambda expression, that is, an anonymous function.</span></span>


## <a name="syntax"></a><span data-ttu-id="f0456-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f0456-105">Syntax</span></span>

```fsharp
fun parameter-list -> expression
```

## <a name="remarks"></a><span data-ttu-id="f0456-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="f0456-106">Remarks</span></span>
<span data-ttu-id="f0456-107">*Список параметров* обычно состоит из имен и, возможно, типы параметров.</span><span class="sxs-lookup"><span data-stu-id="f0456-107">The *parameter-list* typically consists of names and, optionally, types of parameters.</span></span> <span data-ttu-id="f0456-108">Как правило *список параметров* может состоять из любых шаблонов F #.</span><span class="sxs-lookup"><span data-stu-id="f0456-108">More generally, the *parameter-list* can be composed of any F# patterns.</span></span> <span data-ttu-id="f0456-109">Полный список возможных шаблонов см. в разделе [соответствие шаблону](../pattern-matching.md).</span><span class="sxs-lookup"><span data-stu-id="f0456-109">For a full list of possible patterns, see [Pattern Matching](../pattern-matching.md).</span></span> <span data-ttu-id="f0456-110">Примеры списков допустимых параметров.</span><span class="sxs-lookup"><span data-stu-id="f0456-110">Lists of valid parameters include the following examples.</span></span>

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

<span data-ttu-id="f0456-111">*Выражение* является тело функции, последнее выражение которого формирует возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="f0456-111">The *expression* is the body of the function, the last expression of which generates a return value.</span></span> <span data-ttu-id="f0456-112">Примеры допустимых лямбда-выражений:</span><span class="sxs-lookup"><span data-stu-id="f0456-112">Examples of valid lambda expressions include the following:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet301.fs)]
    
## <a name="using-lambda-expressions"></a><span data-ttu-id="f0456-113">Использование лямбда-выражений</span><span class="sxs-lookup"><span data-stu-id="f0456-113">Using Lambda Expressions</span></span>
<span data-ttu-id="f0456-114">Лямбда-выражения особенно полезны, когда требуется выполнять операции над списком или других коллекций и требуется избежать лишней работы — определения функции.</span><span class="sxs-lookup"><span data-stu-id="f0456-114">Lambda expressions are especially useful when you want to perform operations on a list or other collection and want to avoid the extra work of defining a function.</span></span> <span data-ttu-id="f0456-115">Многие функции библиотеки F # принимают значения функций в качестве аргументов и может быть особенно удобно использовать в тех случаях, лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="f0456-115">Many F# library functions take function values as arguments, and it can be especially convenient to use a lambda expression in those cases.</span></span> <span data-ttu-id="f0456-116">Следующий код лямбда-выражение применяется к элементам списка.</span><span class="sxs-lookup"><span data-stu-id="f0456-116">The following code applies a lambda expression to elements of a list.</span></span> <span data-ttu-id="f0456-117">В этом случае анонимная функция добавляет 1 к каждому элементу списка.</span><span class="sxs-lookup"><span data-stu-id="f0456-117">In this case, the anonymous function adds 1 to every element of a list.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet302.fs)]
    
## <a name="see-also"></a><span data-ttu-id="f0456-118">См. также</span><span class="sxs-lookup"><span data-stu-id="f0456-118">See Also</span></span>
[<span data-ttu-id="f0456-119">Функции</span><span class="sxs-lookup"><span data-stu-id="f0456-119">Functions</span></span>](index.md)
