---
title: "Передача параметров ссылочного типа (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- method parameters [C#], reference types
- parameters [C#], reference
ms.assetid: 9e6eb65c-942e-48ab-920a-b7ba9df4ea20
caps.latest.revision: 14
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
ms.openlocfilehash: 3f57dc9f0de6fae6da3ec8e6e6cfdc3a21baeaea
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="passing-reference-type-parameters-c-programming-guide"></a><span data-ttu-id="8be49-102">Передача параметров ссылочного типа (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="8be49-102">Passing Reference-Type Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="8be49-103">Переменная [ссылочного типа](../../../csharp/language-reference/keywords/reference-types.md) содержит не сами данные, а ссылку на них.</span><span class="sxs-lookup"><span data-stu-id="8be49-103">A variable of a [reference type](../../../csharp/language-reference/keywords/reference-types.md) does not contain its data directly; it contains a reference to its data.</span></span> <span data-ttu-id="8be49-104">При передаче параметра ссылочного типа по значению можно изменять данные, на которые указывает ссылка, например значение элемента класса.</span><span class="sxs-lookup"><span data-stu-id="8be49-104">When you pass a reference-type parameter by value, it is possible to change the data pointed to by the reference, such as the value of a class member.</span></span> <span data-ttu-id="8be49-105">Тем не менее изменить значение самой ссылки нельзя. Это значит, что вы не можете использовать одну и ту же ссылку для выделения памяти для нового класса и его создания вне этого блока.</span><span class="sxs-lookup"><span data-stu-id="8be49-105">However, you cannot change the value of the reference itself; that is, you cannot use the same reference to allocate memory for a new class and have it persist outside the block.</span></span> <span data-ttu-id="8be49-106">Для этого необходимо передать параметр с использованием ключевого слова [ref](../../../csharp/language-reference/keywords/ref.md) или [out](../../../csharp/language-reference/keywords/out.md).</span><span class="sxs-lookup"><span data-stu-id="8be49-106">To do that, pass the parameter using the [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out.md) keyword.</span></span> <span data-ttu-id="8be49-107">В следующих примерах мы для простоты используем `ref`.</span><span class="sxs-lookup"><span data-stu-id="8be49-107">For simplicity, the following examples use `ref`.</span></span>  
  
## <a name="passing-reference-types-by-value"></a><span data-ttu-id="8be49-108">Передача ссылочных типов по значению</span><span class="sxs-lookup"><span data-stu-id="8be49-108">Passing Reference Types by Value</span></span>  
 <span data-ttu-id="8be49-109">В следующем примере демонстрируется передача параметра ссылочного типа `arr` по значению в метод `Change`.</span><span class="sxs-lookup"><span data-stu-id="8be49-109">The following example demonstrates passing a reference-type parameter, `arr`, by value, to a method, `Change`.</span></span> <span data-ttu-id="8be49-110">Поскольку этот параметр является ссылкой на `arr`, можно изменять элементы массива.</span><span class="sxs-lookup"><span data-stu-id="8be49-110">Because the parameter is a reference to `arr`, it is possible to change the values of the array elements.</span></span> <span data-ttu-id="8be49-111">Тем не менее переназначение параметра другому блоку памяти возможно только внутри самого метода и не влияет на исходную переменную `arr`.</span><span class="sxs-lookup"><span data-stu-id="8be49-111">However, the attempt to reassign the parameter to a different memory location only works inside the method and does not affect the original variable, `arr`.</span></span>  
  
 <span data-ttu-id="8be49-112">[!code-cs[csProgGuideParameters#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="8be49-112">[!code-cs[csProgGuideParameters#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_1.cs)]</span></span>  
  
 <span data-ttu-id="8be49-113">В предыдущем примере массив `arr` имеет ссылочный тип и передается в метод без параметра `ref`.</span><span class="sxs-lookup"><span data-stu-id="8be49-113">In the preceding example, the array, `arr`, which is a reference type, is passed to the method without the `ref` parameter.</span></span> <span data-ttu-id="8be49-114">В таком случае в метод будет передана копия ссылки, которая указывает на `arr`.</span><span class="sxs-lookup"><span data-stu-id="8be49-114">In such a case, a copy of the reference, which points to `arr`, is passed to the method.</span></span> <span data-ttu-id="8be49-115">Как видно из выходных данных, метод может изменять содержимое элемента массива (в данном случае с `1` на `888`).</span><span class="sxs-lookup"><span data-stu-id="8be49-115">The output shows that it is possible for the method to change the contents of an array element, in this case from `1` to `888`.</span></span> <span data-ttu-id="8be49-116">Тем не менее при выделении нового блока памяти с помощью оператора [new](../../../csharp/language-reference/keywords/new.md) внутри метода `Change` переменная `pArray` будет ссылаться на новый массив.</span><span class="sxs-lookup"><span data-stu-id="8be49-116">However, allocating a new portion of memory by using the [new](../../../csharp/language-reference/keywords/new.md) operator inside the `Change` method makes the variable `pArray` reference a new array.</span></span> <span data-ttu-id="8be49-117">Таким образом, любые выполненные после этого изменения не будут отражаться в исходном массиве `arr`, который был создан внутри `Main`.</span><span class="sxs-lookup"><span data-stu-id="8be49-117">Thus, any changes after that will not affect the original array, `arr`, which is created inside `Main`.</span></span> <span data-ttu-id="8be49-118">Фактически, в этом примере создается два массива: один внутри `Main`, а другой — в методе `Change`.</span><span class="sxs-lookup"><span data-stu-id="8be49-118">In fact, two arrays are created in this example, one inside `Main` and one inside the `Change` method.</span></span>  
  
## <a name="passing-reference-types-by-reference"></a><span data-ttu-id="8be49-119">Передача ссылочных типов по ссылке</span><span class="sxs-lookup"><span data-stu-id="8be49-119">Passing Reference Types by Reference</span></span>  
 <span data-ttu-id="8be49-120">Следующий пример аналогичен предыдущему, однако в нем в заголовок и вызов метода добавляется ключевое слово `ref`.</span><span class="sxs-lookup"><span data-stu-id="8be49-120">The following example is the same as the previous example, except that the `ref` keyword is added to the method header and call.</span></span> <span data-ttu-id="8be49-121">Любые изменения, выполняемые в методе, влияют на исходную переменную в вызывающей программе.</span><span class="sxs-lookup"><span data-stu-id="8be49-121">Any changes that take place in the method affect the original variable in the calling program.</span></span>  
  
 <span data-ttu-id="8be49-122">[!code-cs[csProgGuideParameters#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="8be49-122">[!code-cs[csProgGuideParameters#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_2.cs)]</span></span>  
  
 <span data-ttu-id="8be49-123">Все изменения, выполняемые внутри метода, влияют на исходный массив в `Main`.</span><span class="sxs-lookup"><span data-stu-id="8be49-123">All of the changes that take place inside the method affect the original array in `Main`.</span></span> <span data-ttu-id="8be49-124">Фактически, происходит перемещение исходного массива с помощью оператора `new`.</span><span class="sxs-lookup"><span data-stu-id="8be49-124">In fact, the original array is reallocated using the `new` operator.</span></span> <span data-ttu-id="8be49-125">Таким образом, после вызова метода `Change` любые ссылки на `arr` будут указывать на массив из пяти элементов, который создается в методе `Change`.</span><span class="sxs-lookup"><span data-stu-id="8be49-125">Thus, after calling the `Change` method, any reference to `arr` points to the five-element array, which is created in the `Change` method.</span></span>  
  
## <a name="swapping-two-strings"></a><span data-ttu-id="8be49-126">Перестановка двух строк</span><span class="sxs-lookup"><span data-stu-id="8be49-126">Swapping Two Strings</span></span>  
 <span data-ttu-id="8be49-127">Перестановка строк представляет собой наглядный пример передачи параметров ссылочного типа по ссылке.</span><span class="sxs-lookup"><span data-stu-id="8be49-127">Swapping strings is a good example of passing reference-type parameters by reference.</span></span> <span data-ttu-id="8be49-128">В этом примере две строки (`str1` и `str2`) инициализируются в `Main`, а затем передаются в метод `SwapStrings` в качестве параметров, измененных по ключевому слову `ref`.</span><span class="sxs-lookup"><span data-stu-id="8be49-128">In the example, two strings, `str1` and `str2`, are initialized in `Main` and passed to the `SwapStrings` method as parameters modified by the `ref` keyword.</span></span> <span data-ttu-id="8be49-129">Перестановка двух строк выполняется как в этом методе, так и в `Main`.</span><span class="sxs-lookup"><span data-stu-id="8be49-129">The two strings are swapped inside the method and inside `Main` as well.</span></span>  
  
 <span data-ttu-id="8be49-130">[!code-cs[csProgGuideParameters#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="8be49-130">[!code-cs[csProgGuideParameters#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_3.cs)]</span></span>  
  
 <span data-ttu-id="8be49-131">В этом примере параметры должны передаваться по ссылке, чтобы обеспечить изменение переменных в вызывающей программе.</span><span class="sxs-lookup"><span data-stu-id="8be49-131">In this example, the parameters need to be passed by reference to affect the variables in the calling program.</span></span> <span data-ttu-id="8be49-132">Если удалить ключевое слово `ref` из заголовка и вызова метода, в вызывающей программе не будут выполнены никакие изменения.</span><span class="sxs-lookup"><span data-stu-id="8be49-132">If you remove the `ref` keyword from both the method header and the method call, no changes will take place in the calling program.</span></span>  
  
 <span data-ttu-id="8be49-133">Дополнительные сведения о строках см. в [этом разделе](../../../csharp/language-reference/keywords/string.md).</span><span class="sxs-lookup"><span data-stu-id="8be49-133">For more information about strings, see [string](../../../csharp/language-reference/keywords/string.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8be49-134">См. также</span><span class="sxs-lookup"><span data-stu-id="8be49-134">See Also</span></span>  
 <span data-ttu-id="8be49-135">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="8be49-135">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="8be49-136">[Передача параметров](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="8be49-136">[Passing Parameters](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md) </span></span>  
 <span data-ttu-id="8be49-137">[Передача массивов при помощи параметров ref и out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md) </span><span class="sxs-lookup"><span data-stu-id="8be49-137">[Passing Arrays Using ref and out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md) </span></span>  
 <span data-ttu-id="8be49-138">[ref](../../../csharp/language-reference/keywords/ref.md) </span><span class="sxs-lookup"><span data-stu-id="8be49-138">[ref](../../../csharp/language-reference/keywords/ref.md) </span></span>  
 [<span data-ttu-id="8be49-139">Ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="8be49-139">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)

