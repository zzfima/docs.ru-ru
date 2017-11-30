---
title: "Встраиваемые функции (F#)"
description: "Узнайте, как использовать встроенные функции на языке F #, интегрированные напрямую в вызывающий код."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 3fa31178-08f8-463d-9d41-d29220a90027
ms.openlocfilehash: 0489d411e2754eaab6a10ff0feb4405491b3b511
ms.sourcegitcommit: 425524461530f020f9747492b42f8cd72b011ae7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/25/2017
---
# <a name="inline-functions"></a><span data-ttu-id="976c3-104">Встраиваемые функции</span><span class="sxs-lookup"><span data-stu-id="976c3-104">Inline Functions</span></span>

<span data-ttu-id="976c3-105">*Встроенные функции* — это функции, интегрированные напрямую в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="976c3-105">*Inline functions* are functions that are integrated directly into the calling code.</span></span>


## <a name="using-inline-functions"></a><span data-ttu-id="976c3-106">С помощью встроенных функций</span><span class="sxs-lookup"><span data-stu-id="976c3-106">Using Inline Functions</span></span>
<span data-ttu-id="976c3-107">При использовании параметров статического типа все функции, которые параметризуются параметрами типа должны быть встроенными.</span><span class="sxs-lookup"><span data-stu-id="976c3-107">When you use static type parameters, any functions that are parameterized by type parameters must be inline.</span></span> <span data-ttu-id="976c3-108">Это гарантирует, что компилятор может разрешить эти параметры типа.</span><span class="sxs-lookup"><span data-stu-id="976c3-108">This guarantees that the compiler can resolve these type parameters.</span></span> <span data-ttu-id="976c3-109">При использовании обычных параметров универсального типа, не существует такого ограничения.</span><span class="sxs-lookup"><span data-stu-id="976c3-109">When you use ordinary generic type parameters, there is no such restriction.</span></span>

<span data-ttu-id="976c3-110">Кроме включения использование ограничений членов, встроенные функции могут быть полезны при оптимизации кода.</span><span class="sxs-lookup"><span data-stu-id="976c3-110">Other than enabling the use of member constraints, inline functions can be helpful in optimizing code.</span></span> <span data-ttu-id="976c3-111">Тем не менее избыточное использование встроенных функций может привести к код, чтобы быть менее устойчивы к изменениям оптимизации компилятора и реализации функций библиотек.</span><span class="sxs-lookup"><span data-stu-id="976c3-111">However, overuse of inline functions can cause your code to be less resistant to changes in compiler optimizations and the implementation of library functions.</span></span> <span data-ttu-id="976c3-112">По этой причине следует избегать использования встроенных функций для оптимизации, если вы попытались использовать другие способы оптимизации.</span><span class="sxs-lookup"><span data-stu-id="976c3-112">For this reason, you should avoid using inline functions for optimization unless you have tried all other optimization techniques.</span></span> <span data-ttu-id="976c3-113">Создание встроенной функции или метода иногда могут увеличить производительность, но которая не.</span><span class="sxs-lookup"><span data-stu-id="976c3-113">Making a function or method inline can sometimes improve performance, but that is not always the case.</span></span> <span data-ttu-id="976c3-114">Таким образом измерения производительности также следует использовать для проверки, что внесения любого встроенного заданной функции на самом деле положительного воздействия изменения.</span><span class="sxs-lookup"><span data-stu-id="976c3-114">Therefore, you should also use performance measurements to verify that making any given function inline does in fact have a positive effect.</span></span>

<span data-ttu-id="976c3-115">`inline` Модификатор может применяться к функциям на верхнем уровне, на уровне модуля или на уровне метода в классе.</span><span class="sxs-lookup"><span data-stu-id="976c3-115">The `inline` modifier can be applied to functions at the top level, at the module level, or at the method level in a class.</span></span>

<span data-ttu-id="976c3-116">В следующем примере кода показаны встроенная функция на верхнем уровне, встроенный метод экземпляра и встроенный статический метод.</span><span class="sxs-lookup"><span data-stu-id="976c3-116">The following code example illustrates an inline function at the top level, an inline instance method, and an inline static method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet201.fs)]
    
## <a name="inline-functions-and-type-inference"></a><span data-ttu-id="976c3-117">Встроенные функции и определение типов</span><span class="sxs-lookup"><span data-stu-id="976c3-117">Inline Functions and Type Inference</span></span>
<span data-ttu-id="976c3-118">Наличие `inline` влияет на определение типа.</span><span class="sxs-lookup"><span data-stu-id="976c3-118">The presence of `inline` affects type inference.</span></span> <span data-ttu-id="976c3-119">Это потому, что встроенные функции могут иметь статически разрешаемые параметры типа, а не в отличных от встроенных функций.</span><span class="sxs-lookup"><span data-stu-id="976c3-119">This is because inline functions can have statically resolved type parameters, whereas non-inline functions cannot.</span></span> <span data-ttu-id="976c3-120">В следующем примере кода показан случай где `inline` полезен, так как вы используете функцию, которая имеет параметр типа статически разрешаемые, `float` оператор преобразования.</span><span class="sxs-lookup"><span data-stu-id="976c3-120">The following code example shows a case where `inline` is helpful because you are using a function that has a statically resolved type parameter, the `float` conversion operator.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet202.fs)]

<span data-ttu-id="976c3-121">Без `inline` модификатор, определения типа принудительно назначает функции определенный тип, в этом случае `int`.</span><span class="sxs-lookup"><span data-stu-id="976c3-121">Without the `inline` modifier, type inference forces the function to take a specific type, in this case `int`.</span></span> <span data-ttu-id="976c3-122">Но с `inline` модификатор, функция также определяется, имеет статически разрешаемые типа параметра.</span><span class="sxs-lookup"><span data-stu-id="976c3-122">But with the `inline` modifier, the function is also inferred to have a statically resolved type parameter.</span></span> <span data-ttu-id="976c3-123">С `inline` модификатор типа выводится на следующий:</span><span class="sxs-lookup"><span data-stu-id="976c3-123">With the `inline` modifier, the type is inferred to be the following:</span></span>

```fsharp
^a -> unit when ^a : (static member op_Explicit : ^a -> float)
```

<span data-ttu-id="976c3-124">Это означает, что функция принимает любой тип, поддерживающий преобразование в **float**.</span><span class="sxs-lookup"><span data-stu-id="976c3-124">This means that the function accepts any type that supports a conversion to **float**.</span></span>


## <a name="see-also"></a><span data-ttu-id="976c3-125">См. также</span><span class="sxs-lookup"><span data-stu-id="976c3-125">See Also</span></span>
[<span data-ttu-id="976c3-126">Функции</span><span class="sxs-lookup"><span data-stu-id="976c3-126">Functions</span></span>](index.md)

[<span data-ttu-id="976c3-127">Ограничения</span><span class="sxs-lookup"><span data-stu-id="976c3-127">Constraints</span></span>](../generics/constraints.md)

[<span data-ttu-id="976c3-128">Статически разрешаемые параметры типов</span><span class="sxs-lookup"><span data-stu-id="976c3-128">Statically Resolved Type Parameters</span></span>](../generics/statically-resolved-type-parameters.md)
