---
title: Встраиваемые функции
description: Сведения об использовании F# встроенные функции, интегрированные непосредственно в вызывающем коде.
ms.date: 05/16/2016
ms.openlocfilehash: 12c175e3e46e12d978fe02d3e1fe83142e71a25d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61966599"
---
# <a name="inline-functions"></a><span data-ttu-id="c3d3e-103">Встраиваемые функции</span><span class="sxs-lookup"><span data-stu-id="c3d3e-103">Inline Functions</span></span>

<span data-ttu-id="c3d3e-104">*Встроенные функции* — это функции, интегрированные непосредственно в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="c3d3e-104">*Inline functions* are functions that are integrated directly into the calling code.</span></span>

## <a name="using-inline-functions"></a><span data-ttu-id="c3d3e-105">С помощью встроенных функций</span><span class="sxs-lookup"><span data-stu-id="c3d3e-105">Using Inline Functions</span></span>

<span data-ttu-id="c3d3e-106">При использовании статических типов параметров, любые функции, которые параметризуются языком параметров типа должны быть встроенными.</span><span class="sxs-lookup"><span data-stu-id="c3d3e-106">When you use static type parameters, any functions that are parameterized by type parameters must be inline.</span></span> <span data-ttu-id="c3d3e-107">Это гарантирует, что компилятор может разрешить эти параметры типа.</span><span class="sxs-lookup"><span data-stu-id="c3d3e-107">This guarantees that the compiler can resolve these type parameters.</span></span> <span data-ttu-id="c3d3e-108">При использовании обычных параметров универсального типа, не существует такого ограничения.</span><span class="sxs-lookup"><span data-stu-id="c3d3e-108">When you use ordinary generic type parameters, there is no such restriction.</span></span>

<span data-ttu-id="c3d3e-109">Кроме применение ограничений членов, встроенные функции могут быть полезны при оптимизации кода.</span><span class="sxs-lookup"><span data-stu-id="c3d3e-109">Other than enabling the use of member constraints, inline functions can be helpful in optimizing code.</span></span> <span data-ttu-id="c3d3e-110">Тем не менее избыточное использование встроенных функций может привести к ваш код будет менее устойчивы к изменениям в оптимизации компилятора и реализации функций библиотек.</span><span class="sxs-lookup"><span data-stu-id="c3d3e-110">However, overuse of inline functions can cause your code to be less resistant to changes in compiler optimizations and the implementation of library functions.</span></span> <span data-ttu-id="c3d3e-111">По этой причине следует избегать использования встроенных функций для оптимизации, если вы попытались использовать другие методы оптимизации.</span><span class="sxs-lookup"><span data-stu-id="c3d3e-111">For this reason, you should avoid using inline functions for optimization unless you have tried all other optimization techniques.</span></span> <span data-ttu-id="c3d3e-112">Создание встроенной функции или метода может иногда повысить производительность, но это не всегда так.</span><span class="sxs-lookup"><span data-stu-id="c3d3e-112">Making a function or method inline can sometimes improve performance, but that is not always the case.</span></span> <span data-ttu-id="c3d3e-113">Таким образом чтобы убедиться, что сделать все встроенные заданная функция на самом деле оказывает положительное влияние также следует использовать измерения производительности.</span><span class="sxs-lookup"><span data-stu-id="c3d3e-113">Therefore, you should also use performance measurements to verify that making any given function inline does in fact have a positive effect.</span></span>

<span data-ttu-id="c3d3e-114">`inline` Модификатор может применяться к функциям на верхнем уровне, на уровне модуля или на уровне метода в классе.</span><span class="sxs-lookup"><span data-stu-id="c3d3e-114">The `inline` modifier can be applied to functions at the top level, at the module level, or at the method level in a class.</span></span>

<span data-ttu-id="c3d3e-115">В следующем примере кода показана встроенная функция на верхнем уровне, встроенный метод экземпляра и встроенный статический метод.</span><span class="sxs-lookup"><span data-stu-id="c3d3e-115">The following code example illustrates an inline function at the top level, an inline instance method, and an inline static method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet201.fs)]

## <a name="inline-functions-and-type-inference"></a><span data-ttu-id="c3d3e-116">Встроенные функции и вывод типов</span><span class="sxs-lookup"><span data-stu-id="c3d3e-116">Inline Functions and Type Inference</span></span>

<span data-ttu-id="c3d3e-117">Наличие `inline` влияет на определение типа.</span><span class="sxs-lookup"><span data-stu-id="c3d3e-117">The presence of `inline` affects type inference.</span></span> <span data-ttu-id="c3d3e-118">Это так, как встроенные функции могут иметь статически разрешаемые параметры типа, а не встроенные функции нельзя.</span><span class="sxs-lookup"><span data-stu-id="c3d3e-118">This is because inline functions can have statically resolved type parameters, whereas non-inline functions cannot.</span></span> <span data-ttu-id="c3d3e-119">В следующем примере кода показан случай где `inline` полезно потому, что при использовании функции, которая имеет статически разрешаемым параметром типа, `float` оператор преобразования.</span><span class="sxs-lookup"><span data-stu-id="c3d3e-119">The following code example shows a case where `inline` is helpful because you are using a function that has a statically resolved type parameter, the `float` conversion operator.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet202.fs)]

<span data-ttu-id="c3d3e-120">Без `inline` модификатор, вывод типа заставляет функции определенного типа, в данном случае `int`.</span><span class="sxs-lookup"><span data-stu-id="c3d3e-120">Without the `inline` modifier, type inference forces the function to take a specific type, in this case `int`.</span></span> <span data-ttu-id="c3d3e-121">Но с `inline` модификатор, функция также логически распознается статически разрешаемым параметром типа.</span><span class="sxs-lookup"><span data-stu-id="c3d3e-121">But with the `inline` modifier, the function is also inferred to have a statically resolved type parameter.</span></span> <span data-ttu-id="c3d3e-122">С помощью `inline` модификатор, тип определяется следующим:</span><span class="sxs-lookup"><span data-stu-id="c3d3e-122">With the `inline` modifier, the type is inferred to be the following:</span></span>

```fsharp
^a -> unit when ^a : (static member op_Explicit : ^a -> float)
```

<span data-ttu-id="c3d3e-123">Это означает, что функция принимает любой тип, поддерживающий преобразование в **float**.</span><span class="sxs-lookup"><span data-stu-id="c3d3e-123">This means that the function accepts any type that supports a conversion to **float**.</span></span>

## <a name="see-also"></a><span data-ttu-id="c3d3e-124">См. также</span><span class="sxs-lookup"><span data-stu-id="c3d3e-124">See also</span></span>

- [<span data-ttu-id="c3d3e-125">Функции</span><span class="sxs-lookup"><span data-stu-id="c3d3e-125">Functions</span></span>](index.md)
- [<span data-ttu-id="c3d3e-126">Ограничения</span><span class="sxs-lookup"><span data-stu-id="c3d3e-126">Constraints</span></span>](../generics/constraints.md)
- [<span data-ttu-id="c3d3e-127">Статически разрешаемые параметры типов</span><span class="sxs-lookup"><span data-stu-id="c3d3e-127">Statically Resolved Type Parameters</span></span>](../generics/statically-resolved-type-parameters.md)