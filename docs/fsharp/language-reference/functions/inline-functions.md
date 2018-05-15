---
title: Встраиваемые функции (F#)
description: 'Узнайте, как использовать встроенные функции на языке F #, интегрированные напрямую в вызывающий код.'
ms.date: 05/16/2016
ms.openlocfilehash: d265f9b4e828946c510bd8e84b14d5236ab511fa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="inline-functions"></a><span data-ttu-id="61445-103">Встраиваемые функции</span><span class="sxs-lookup"><span data-stu-id="61445-103">Inline Functions</span></span>

<span data-ttu-id="61445-104">*Встроенные функции* — это функции, интегрированные напрямую в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="61445-104">*Inline functions* are functions that are integrated directly into the calling code.</span></span>


## <a name="using-inline-functions"></a><span data-ttu-id="61445-105">С помощью встроенных функций</span><span class="sxs-lookup"><span data-stu-id="61445-105">Using Inline Functions</span></span>
<span data-ttu-id="61445-106">При использовании параметров статического типа все функции, которые параметризуются параметрами типа должны быть встроенными.</span><span class="sxs-lookup"><span data-stu-id="61445-106">When you use static type parameters, any functions that are parameterized by type parameters must be inline.</span></span> <span data-ttu-id="61445-107">Это гарантирует, что компилятор может разрешить эти параметры типа.</span><span class="sxs-lookup"><span data-stu-id="61445-107">This guarantees that the compiler can resolve these type parameters.</span></span> <span data-ttu-id="61445-108">При использовании обычных параметров универсального типа, не существует такого ограничения.</span><span class="sxs-lookup"><span data-stu-id="61445-108">When you use ordinary generic type parameters, there is no such restriction.</span></span>

<span data-ttu-id="61445-109">Кроме включения использование ограничений членов, встроенные функции могут быть полезны при оптимизации кода.</span><span class="sxs-lookup"><span data-stu-id="61445-109">Other than enabling the use of member constraints, inline functions can be helpful in optimizing code.</span></span> <span data-ttu-id="61445-110">Тем не менее избыточное использование встроенных функций может привести к код, чтобы быть менее устойчивы к изменениям оптимизации компилятора и реализации функций библиотек.</span><span class="sxs-lookup"><span data-stu-id="61445-110">However, overuse of inline functions can cause your code to be less resistant to changes in compiler optimizations and the implementation of library functions.</span></span> <span data-ttu-id="61445-111">По этой причине следует избегать использования встроенных функций для оптимизации, если вы попытались использовать другие способы оптимизации.</span><span class="sxs-lookup"><span data-stu-id="61445-111">For this reason, you should avoid using inline functions for optimization unless you have tried all other optimization techniques.</span></span> <span data-ttu-id="61445-112">Создание встроенной функции или метода иногда могут увеличить производительность, но которая не.</span><span class="sxs-lookup"><span data-stu-id="61445-112">Making a function or method inline can sometimes improve performance, but that is not always the case.</span></span> <span data-ttu-id="61445-113">Таким образом измерения производительности также следует использовать для проверки, что внесения любого встроенного заданной функции на самом деле положительного воздействия изменения.</span><span class="sxs-lookup"><span data-stu-id="61445-113">Therefore, you should also use performance measurements to verify that making any given function inline does in fact have a positive effect.</span></span>

<span data-ttu-id="61445-114">`inline` Модификатор может применяться к функциям на верхнем уровне, на уровне модуля или на уровне метода в классе.</span><span class="sxs-lookup"><span data-stu-id="61445-114">The `inline` modifier can be applied to functions at the top level, at the module level, or at the method level in a class.</span></span>

<span data-ttu-id="61445-115">В следующем примере кода показаны встроенная функция на верхнем уровне, встроенный метод экземпляра и встроенный статический метод.</span><span class="sxs-lookup"><span data-stu-id="61445-115">The following code example illustrates an inline function at the top level, an inline instance method, and an inline static method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet201.fs)]
    
## <a name="inline-functions-and-type-inference"></a><span data-ttu-id="61445-116">Встроенные функции и определение типов</span><span class="sxs-lookup"><span data-stu-id="61445-116">Inline Functions and Type Inference</span></span>
<span data-ttu-id="61445-117">Наличие `inline` влияет на определение типа.</span><span class="sxs-lookup"><span data-stu-id="61445-117">The presence of `inline` affects type inference.</span></span> <span data-ttu-id="61445-118">Это потому, что встроенные функции могут иметь статически разрешаемые параметры типа, а не в отличных от встроенных функций.</span><span class="sxs-lookup"><span data-stu-id="61445-118">This is because inline functions can have statically resolved type parameters, whereas non-inline functions cannot.</span></span> <span data-ttu-id="61445-119">В следующем примере кода показан случай где `inline` полезен, так как вы используете функцию, которая имеет параметр типа статически разрешаемые, `float` оператор преобразования.</span><span class="sxs-lookup"><span data-stu-id="61445-119">The following code example shows a case where `inline` is helpful because you are using a function that has a statically resolved type parameter, the `float` conversion operator.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet202.fs)]

<span data-ttu-id="61445-120">Без `inline` модификатор, определения типа принудительно назначает функции определенный тип, в этом случае `int`.</span><span class="sxs-lookup"><span data-stu-id="61445-120">Without the `inline` modifier, type inference forces the function to take a specific type, in this case `int`.</span></span> <span data-ttu-id="61445-121">Но с `inline` модификатор, функция также определяется, имеет статически разрешаемые типа параметра.</span><span class="sxs-lookup"><span data-stu-id="61445-121">But with the `inline` modifier, the function is also inferred to have a statically resolved type parameter.</span></span> <span data-ttu-id="61445-122">С `inline` модификатор типа выводится на следующий:</span><span class="sxs-lookup"><span data-stu-id="61445-122">With the `inline` modifier, the type is inferred to be the following:</span></span>

```fsharp
^a -> unit when ^a : (static member op_Explicit : ^a -> float)
```

<span data-ttu-id="61445-123">Это означает, что функция принимает любой тип, поддерживающий преобразование в **float**.</span><span class="sxs-lookup"><span data-stu-id="61445-123">This means that the function accepts any type that supports a conversion to **float**.</span></span>


## <a name="see-also"></a><span data-ttu-id="61445-124">См. также</span><span class="sxs-lookup"><span data-stu-id="61445-124">See Also</span></span>
[<span data-ttu-id="61445-125">Функции</span><span class="sxs-lookup"><span data-stu-id="61445-125">Functions</span></span>](index.md)

[<span data-ttu-id="61445-126">Ограничения</span><span class="sxs-lookup"><span data-stu-id="61445-126">Constraints</span></span>](../generics/constraints.md)

[<span data-ttu-id="61445-127">Статически разрешаемые параметры типов</span><span class="sxs-lookup"><span data-stu-id="61445-127">Statically Resolved Type Parameters</span></span>](../generics/statically-resolved-type-parameters.md)
