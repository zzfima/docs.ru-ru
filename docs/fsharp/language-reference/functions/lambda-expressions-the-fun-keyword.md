---
title: 'Лямбда-выражения: Ключевое слово fun'
description: Сведения об использовании F# ключевое слово «интересные» для определения лямбда-выражения, который представляет собой анонимную функцию.
ms.date: 05/16/2016
ms.openlocfilehash: c59d32bd4226384213453f1a9d362209e68a6fb5
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645392"
---
# <a name="lambda-expressions-the-fun-keyword-f"></a><span data-ttu-id="5d28c-103">Лямбда-выражения: Ключевое слово fun (F#)</span><span class="sxs-lookup"><span data-stu-id="5d28c-103">Lambda Expressions: The fun Keyword (F#)</span></span>

<span data-ttu-id="5d28c-104">`fun` Ключевое слово используется для определения лямбда-выражения, то есть анонимную функцию.</span><span class="sxs-lookup"><span data-stu-id="5d28c-104">The `fun` keyword is used to define a lambda expression, that is, an anonymous function.</span></span>

## <a name="syntax"></a><span data-ttu-id="5d28c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5d28c-105">Syntax</span></span>

```fsharp
fun parameter-list -> expression
```

## <a name="remarks"></a><span data-ttu-id="5d28c-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="5d28c-106">Remarks</span></span>

<span data-ttu-id="5d28c-107">*Список параметров* обычно состоит из имен и, возможно, типы параметров.</span><span class="sxs-lookup"><span data-stu-id="5d28c-107">The *parameter-list* typically consists of names and, optionally, types of parameters.</span></span> <span data-ttu-id="5d28c-108">Как правило *список параметров* может состоять из любой F# шаблонов.</span><span class="sxs-lookup"><span data-stu-id="5d28c-108">More generally, the *parameter-list* can be composed of any F# patterns.</span></span> <span data-ttu-id="5d28c-109">Полный список шаблонов, см. в разделе [сопоставление шаблонов](../pattern-matching.md).</span><span class="sxs-lookup"><span data-stu-id="5d28c-109">For a full list of possible patterns, see [Pattern Matching](../pattern-matching.md).</span></span> <span data-ttu-id="5d28c-110">Списки допустимых параметров включает следующие варианты.</span><span class="sxs-lookup"><span data-stu-id="5d28c-110">Lists of valid parameters include the following examples.</span></span>

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

<span data-ttu-id="5d28c-111">*Выражение* представляет собой тело функции, последнее выражение которого формирует возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="5d28c-111">The *expression* is the body of the function, the last expression of which generates a return value.</span></span> <span data-ttu-id="5d28c-112">Следующие примеры допустимых лямбда-выражений.</span><span class="sxs-lookup"><span data-stu-id="5d28c-112">Examples of valid lambda expressions include the following:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet301.fs)]

## <a name="using-lambda-expressions"></a><span data-ttu-id="5d28c-113">Использование лямбда-выражений</span><span class="sxs-lookup"><span data-stu-id="5d28c-113">Using Lambda Expressions</span></span>

<span data-ttu-id="5d28c-114">Лямбда-выражения особенно полезны при необходимости для выполнения операций со списками или другой коллекции и хотите избежать дополнительной работы определения функции.</span><span class="sxs-lookup"><span data-stu-id="5d28c-114">Lambda expressions are especially useful when you want to perform operations on a list or other collection and want to avoid the extra work of defining a function.</span></span> <span data-ttu-id="5d28c-115">Многие F# библиотеки функции принимают значения функции в качестве аргументов, и может быть особенно удобно использовать лямбда-выражение в таких случаях.</span><span class="sxs-lookup"><span data-stu-id="5d28c-115">Many F# library functions take function values as arguments, and it can be especially convenient to use a lambda expression in those cases.</span></span> <span data-ttu-id="5d28c-116">Следующий код применяет лямбда-выражение к элементам списка.</span><span class="sxs-lookup"><span data-stu-id="5d28c-116">The following code applies a lambda expression to elements of a list.</span></span> <span data-ttu-id="5d28c-117">В этом случае анонимная функция добавляет 1 к каждому элементу списка.</span><span class="sxs-lookup"><span data-stu-id="5d28c-117">In this case, the anonymous function adds 1 to every element of a list.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet302.fs)]

## <a name="see-also"></a><span data-ttu-id="5d28c-118">См. также</span><span class="sxs-lookup"><span data-stu-id="5d28c-118">See also</span></span>

- [<span data-ttu-id="5d28c-119">Функции</span><span class="sxs-lookup"><span data-stu-id="5d28c-119">Functions</span></span>](index.md)
