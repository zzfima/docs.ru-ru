---
title: Встраиваемые функции
description: Узнайте, как использовать F# встроенные функции, интегрированные непосредственно в вызывающий код.
ms.date: 05/16/2016
ms.openlocfilehash: 2830d1ada5b3005c3fcae975a44e85a7c84554f7
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630679"
---
# <a name="inline-functions"></a><span data-ttu-id="4bbe7-103">Встраиваемые функции</span><span class="sxs-lookup"><span data-stu-id="4bbe7-103">Inline Functions</span></span>

<span data-ttu-id="4bbe7-104">*Встроенные функции* — это функции, интегрированные непосредственно в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="4bbe7-104">*Inline functions* are functions that are integrated directly into the calling code.</span></span>

## <a name="using-inline-functions"></a><span data-ttu-id="4bbe7-105">Использование встроенных функций</span><span class="sxs-lookup"><span data-stu-id="4bbe7-105">Using Inline Functions</span></span>

<span data-ttu-id="4bbe7-106">При использовании статических параметров типа все функции, параметризованные параметрами типа, должны быть встроенными.</span><span class="sxs-lookup"><span data-stu-id="4bbe7-106">When you use static type parameters, any functions that are parameterized by type parameters must be inline.</span></span> <span data-ttu-id="4bbe7-107">Это гарантирует, что компилятор может разрешить эти параметры типа.</span><span class="sxs-lookup"><span data-stu-id="4bbe7-107">This guarantees that the compiler can resolve these type parameters.</span></span> <span data-ttu-id="4bbe7-108">При использовании обычных параметров универсального типа такое ограничение отсутствует.</span><span class="sxs-lookup"><span data-stu-id="4bbe7-108">When you use ordinary generic type parameters, there is no such restriction.</span></span>

<span data-ttu-id="4bbe7-109">Кроме включения использования ограничений элементов, встроенные функции могут быть полезны при оптимизации кода.</span><span class="sxs-lookup"><span data-stu-id="4bbe7-109">Other than enabling the use of member constraints, inline functions can be helpful in optimizing code.</span></span> <span data-ttu-id="4bbe7-110">Однако чрезмерное использование встроенных функций может привести к тому, что ваш код будет менее устойчив к изменениям в оптимизации компилятора и реализации библиотечных функций.</span><span class="sxs-lookup"><span data-stu-id="4bbe7-110">However, overuse of inline functions can cause your code to be less resistant to changes in compiler optimizations and the implementation of library functions.</span></span> <span data-ttu-id="4bbe7-111">По этой причине следует избегать использования встроенных функций для оптимизации, если не были предприняты другие методы оптимизации.</span><span class="sxs-lookup"><span data-stu-id="4bbe7-111">For this reason, you should avoid using inline functions for optimization unless you have tried all other optimization techniques.</span></span> <span data-ttu-id="4bbe7-112">Создание встроенной функции или метода иногда может повысить производительность, но это не всегда так.</span><span class="sxs-lookup"><span data-stu-id="4bbe7-112">Making a function or method inline can sometimes improve performance, but that is not always the case.</span></span> <span data-ttu-id="4bbe7-113">Поэтому следует также использовать измерения производительности, чтобы убедиться в том, что выполнение любой заданной функции имеет положительный результат.</span><span class="sxs-lookup"><span data-stu-id="4bbe7-113">Therefore, you should also use performance measurements to verify that making any given function inline does in fact have a positive effect.</span></span>

<span data-ttu-id="4bbe7-114">`inline` Модификатор можно применять к функциям на верхнем уровне, на уровне модуля или на уровне метода в классе.</span><span class="sxs-lookup"><span data-stu-id="4bbe7-114">The `inline` modifier can be applied to functions at the top level, at the module level, or at the method level in a class.</span></span>

<span data-ttu-id="4bbe7-115">В следующем примере кода показана встроенная функция на верхнем уровне, встроенный метод экземпляра и встроенный статический метод.</span><span class="sxs-lookup"><span data-stu-id="4bbe7-115">The following code example illustrates an inline function at the top level, an inline instance method, and an inline static method.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet201.fs)]

## <a name="inline-functions-and-type-inference"></a><span data-ttu-id="4bbe7-116">Встроенные функции и вывод типов</span><span class="sxs-lookup"><span data-stu-id="4bbe7-116">Inline Functions and Type Inference</span></span>

<span data-ttu-id="4bbe7-117">Наличие `inline` влияет на вывод типа.</span><span class="sxs-lookup"><span data-stu-id="4bbe7-117">The presence of `inline` affects type inference.</span></span> <span data-ttu-id="4bbe7-118">Это обусловлено тем, что встроенные функции могут иметь статически разрешаемые параметры типа, тогда как невстроенные функции не могут.</span><span class="sxs-lookup"><span data-stu-id="4bbe7-118">This is because inline functions can have statically resolved type parameters, whereas non-inline functions cannot.</span></span> <span data-ttu-id="4bbe7-119">В следующем примере кода показан случай, когда `inline` используется функция с статически разрешаемым параметром типа `float` , оператором преобразования.</span><span class="sxs-lookup"><span data-stu-id="4bbe7-119">The following code example shows a case where `inline` is helpful because you are using a function that has a statically resolved type parameter, the `float` conversion operator.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet202.fs)]

<span data-ttu-id="4bbe7-120">Без модификатора вывод типа заставляет функцию принять конкретный тип, в данном случае `int`. `inline`</span><span class="sxs-lookup"><span data-stu-id="4bbe7-120">Without the `inline` modifier, type inference forces the function to take a specific type, in this case `int`.</span></span> <span data-ttu-id="4bbe7-121">Но с помощью `inline` модификатора функция также выводится для статического разрешаемого параметра типа.</span><span class="sxs-lookup"><span data-stu-id="4bbe7-121">But with the `inline` modifier, the function is also inferred to have a statically resolved type parameter.</span></span> <span data-ttu-id="4bbe7-122">При использовании `inline` модификатора тип выводится следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4bbe7-122">With the `inline` modifier, the type is inferred to be the following:</span></span>

```fsharp
^a -> unit when ^a : (static member op_Explicit : ^a -> float)
```

<span data-ttu-id="4bbe7-123">Это означает, что функция принимает любой тип, поддерживающий преобразование в **float**.</span><span class="sxs-lookup"><span data-stu-id="4bbe7-123">This means that the function accepts any type that supports a conversion to **float**.</span></span>

## <a name="see-also"></a><span data-ttu-id="4bbe7-124">См. также</span><span class="sxs-lookup"><span data-stu-id="4bbe7-124">See also</span></span>

- [<span data-ttu-id="4bbe7-125">Функции</span><span class="sxs-lookup"><span data-stu-id="4bbe7-125">Functions</span></span>](index.md)
- [<span data-ttu-id="4bbe7-126">Ограничения</span><span class="sxs-lookup"><span data-stu-id="4bbe7-126">Constraints</span></span>](../generics/constraints.md)
- [<span data-ttu-id="4bbe7-127">Статически разрешаемые параметры типов</span><span class="sxs-lookup"><span data-stu-id="4bbe7-127">Statically Resolved Type Parameters</span></span>](../generics/statically-resolved-type-parameters.md)
