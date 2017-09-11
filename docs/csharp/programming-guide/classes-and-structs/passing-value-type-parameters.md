---
title: "Передача параметров типа значения (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- method parameters [C#], value types
- parameters [C#], value
ms.assetid: 193ab86f-5f9b-4359-ac29-7cdf8afad3a6
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a3377630fc4294831f6b9d66a69377aa42d973f1
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="passing-value-type-parameters-c-programming-guide"></a><span data-ttu-id="fb67f-102">Передача параметров типа значения (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="fb67f-102">Passing Value-Type Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="fb67f-103">Переменная [типа значения](../../../csharp/language-reference/keywords/value-types.md) напрямую содержит данные, в отличие от переменной [ссылочного типа](../../../csharp/language-reference/keywords/reference-types.md), которая содержит только ссылку на данные.</span><span class="sxs-lookup"><span data-stu-id="fb67f-103">A [value-type](../../../csharp/language-reference/keywords/value-types.md) variable contains its data directly as opposed to a [reference-type](../../../csharp/language-reference/keywords/reference-types.md) variable, which contains a reference to its data.</span></span> <span data-ttu-id="fb67f-104">Передавая в метод переменную типа значения, вы передаете ему копию этой переменной.</span><span class="sxs-lookup"><span data-stu-id="fb67f-104">Passing a value-type variable to a method by value means passing a copy of the variable to the method.</span></span> <span data-ttu-id="fb67f-105">Любые изменения параметра, которые происходят внутри метода, не влияют на исходные данные, хранимые в переменной.</span><span class="sxs-lookup"><span data-stu-id="fb67f-105">Any changes to the parameter that take place inside the method have no affect on the original data stored in the argument variable.</span></span> <span data-ttu-id="fb67f-106">Если вы хотите, чтобы вызываемый метод изменял значение параметра, его необходимо передавать по ссылке с помощью ключевых слов [ref](../../../csharp/language-reference/keywords/ref.md) или [out](../../../csharp/language-reference/keywords/out.md).</span><span class="sxs-lookup"><span data-stu-id="fb67f-106">If you want the called method to change the value of the parameter, you must pass it by reference, using the [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out.md) keyword.</span></span> <span data-ttu-id="fb67f-107">В следующих примерах мы для простоты используем `ref`.</span><span class="sxs-lookup"><span data-stu-id="fb67f-107">For simplicity, the following examples use `ref`.</span></span>  
  
## <a name="passing-value-types-by-value"></a><span data-ttu-id="fb67f-108">Передача переменных типы значения по значению</span><span class="sxs-lookup"><span data-stu-id="fb67f-108">Passing Value Types by Value</span></span>  
 <span data-ttu-id="fb67f-109">Следующий пример демонстрирует передачу параметров типа значения по значению.</span><span class="sxs-lookup"><span data-stu-id="fb67f-109">The following example demonstrates passing value-type parameters by value.</span></span> <span data-ttu-id="fb67f-110">Переменная `n` передается по значению в метод `SquareIt`.</span><span class="sxs-lookup"><span data-stu-id="fb67f-110">The variable `n` is passed by value to the method `SquareIt`.</span></span> <span data-ttu-id="fb67f-111">Любые изменения, выполненные внутри метода, не влияют на исходное значение переменной.</span><span class="sxs-lookup"><span data-stu-id="fb67f-111">Any changes that take place inside the method have no affect on the original value of the variable.</span></span>  
  
 <span data-ttu-id="fb67f-112">[!code-cs[csProgGuideParameters#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="fb67f-112">[!code-cs[csProgGuideParameters#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_1.cs)]</span></span>  
  
 <span data-ttu-id="fb67f-113">Переменная `n` имеет тип значения.</span><span class="sxs-lookup"><span data-stu-id="fb67f-113">The variable `n` is a value type.</span></span> <span data-ttu-id="fb67f-114">Она содержит данные, в нашем примере это значение `5`.</span><span class="sxs-lookup"><span data-stu-id="fb67f-114">It contains its data, the value `5`.</span></span> <span data-ttu-id="fb67f-115">Когда вызывается `SquareIt`, содержимое `n` копируется в параметр `x`, который используется исключительно внутри метода.</span><span class="sxs-lookup"><span data-stu-id="fb67f-115">When `SquareIt` is invoked, the contents of `n` are copied into the parameter `x`, which is squared inside the method.</span></span> <span data-ttu-id="fb67f-116">Но в `Main` значение `n` всегда останется прежним после выполнения метода `SquareIt`.</span><span class="sxs-lookup"><span data-stu-id="fb67f-116">In `Main`, however, the value of `n` is the same after calling the `SquareIt` method as it was before.</span></span> <span data-ttu-id="fb67f-117">Изменения, выполненные внутри метода, влияют только на локальную переменную `x`.</span><span class="sxs-lookup"><span data-stu-id="fb67f-117">The change that takes place inside the method only affects the local variable `x`.</span></span>  
  
## <a name="passing-value-types-by-reference"></a><span data-ttu-id="fb67f-118">Передача переменных типы значения по ссылке</span><span class="sxs-lookup"><span data-stu-id="fb67f-118">Passing Value Types by Reference</span></span>  
 <span data-ttu-id="fb67f-119">Следующий пример полностью совпадает с предыдущим, но теперь аргумент передается как параметр `ref`.</span><span class="sxs-lookup"><span data-stu-id="fb67f-119">The following example is the same as the previous example, except that the argument is passed as a `ref` parameter.</span></span> <span data-ttu-id="fb67f-120">Значение базового аргумента `n` будет изменяться, когда метод изменяет значение `x`.</span><span class="sxs-lookup"><span data-stu-id="fb67f-120">The value of the underlying argument, `n`, is changed when `x` is changed in the method.</span></span>  
  
 <span data-ttu-id="fb67f-121">[!code-cs[csProgGuideParameters#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="fb67f-121">[!code-cs[csProgGuideParameters#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_2.cs)]</span></span>  
  
 <span data-ttu-id="fb67f-122">В этом примере передается не значение `n`, а ссылка на `n`.</span><span class="sxs-lookup"><span data-stu-id="fb67f-122">In this example, it is not the value of `n` that is passed; rather, a reference to `n` is passed.</span></span> <span data-ttu-id="fb67f-123">Теперь параметр `x` будет не значением типа [int](../../../csharp/language-reference/keywords/int.md), а ссылкой на `int`. В нашем примере это ссылка на `n`.</span><span class="sxs-lookup"><span data-stu-id="fb67f-123">The parameter `x` is not an [int](../../../csharp/language-reference/keywords/int.md); it is a reference to an `int`, in this case, a reference to `n`.</span></span> <span data-ttu-id="fb67f-124">Таким образом, при передаче `x` в метод передается только информация о том, что `x` ссылается на `n`.</span><span class="sxs-lookup"><span data-stu-id="fb67f-124">Therefore, when `x` is squared inside the method, what actually is squared is what `x` refers to, `n`.</span></span>  
  
## <a name="swapping-value-types"></a><span data-ttu-id="fb67f-125">Изменение типов значений</span><span class="sxs-lookup"><span data-stu-id="fb67f-125">Swapping Value Types</span></span>  
 <span data-ttu-id="fb67f-126">Распространенным примером изменения значений аргументов является метод замены, при котором в метод передаются две переменные, а метод меняет местами их содержимое.</span><span class="sxs-lookup"><span data-stu-id="fb67f-126">A common example of changing the values of arguments is a swap method, where you pass two variables to the method, and the method swaps their contents.</span></span> <span data-ttu-id="fb67f-127">Для метода замены аргументы необходимо передавать по ссылке.</span><span class="sxs-lookup"><span data-stu-id="fb67f-127">You must pass the arguments to the swap method by reference.</span></span> <span data-ttu-id="fb67f-128">В противном случае замена затронет лишь локальные копии параметров в этом методе, но в вызывающем методе не произойдет никаких изменений.</span><span class="sxs-lookup"><span data-stu-id="fb67f-128">Otherwise, you swap local copies of the parameters inside the method, and no change occurs in the calling method.</span></span> <span data-ttu-id="fb67f-129">В следующем примере меняются местами целочисленные значения.</span><span class="sxs-lookup"><span data-stu-id="fb67f-129">The following example swaps integer values.</span></span>  
  
 <span data-ttu-id="fb67f-130">[!code-cs[csProgGuideParameters#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="fb67f-130">[!code-cs[csProgGuideParameters#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_3.cs)]</span></span>  
  
 <span data-ttu-id="fb67f-131">При вызове метода `SwapByRef` используйте ключевое слово `ref`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="fb67f-131">When you call the `SwapByRef` method, use the `ref` keyword in the call, as shown in the following example.</span></span>  
  
 <span data-ttu-id="fb67f-132">[!code-cs[csProgGuideParameters#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="fb67f-132">[!code-cs[csProgGuideParameters#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_4.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb67f-133">См. также</span><span class="sxs-lookup"><span data-stu-id="fb67f-133">See Also</span></span>  
 <span data-ttu-id="fb67f-134">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="fb67f-134">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="fb67f-135">[Передача параметров](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="fb67f-135">[Passing Parameters](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md) </span></span>  
 [<span data-ttu-id="fb67f-136">Передача параметров ссылочного типа</span><span class="sxs-lookup"><span data-stu-id="fb67f-136">Passing Reference-Type Parameters</span></span>](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)

