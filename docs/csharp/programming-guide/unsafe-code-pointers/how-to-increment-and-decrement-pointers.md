---
title: "Практическое руководство. Увеличение и уменьшение указателей (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- pointers [C#], increment and decrement
- pointer expressions [C#], increment and decrement
ms.assetid: 1b8b9281-44ee-485a-9045-3db38a4b4b89
caps.latest.revision: 20
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
ms.openlocfilehash: b474249ed9f7778e44981b292d51f29f46bc420d
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-increment-and-decrement-pointers-c-programming-guide"></a><span data-ttu-id="2b9d2-102">Практическое руководство. Увеличение и уменьшение указателей (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="2b9d2-102">How to: Increment and Decrement Pointers (C# Programming Guide)</span></span>
<span data-ttu-id="2b9d2-103">С помощью операторов инкремента и декремента (`++` и `--`) можно изменить расположение указателя на тип на величину [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`)*.</span><span class="sxs-lookup"><span data-stu-id="2b9d2-103">Use the increment and the decrement operators, `++` and `--`, to change the pointer location by [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) for a pointer of type pointer-type*.</span></span> <span data-ttu-id="2b9d2-104">Выражения инкремента или декремента имеют следующий вид:</span><span class="sxs-lookup"><span data-stu-id="2b9d2-104">The increment and decrement expressions take the following form:</span></span>  
  
```  
++p;  
p++;  
--p;  
p--;  
```  
  
 <span data-ttu-id="2b9d2-105">Операторы инкремента и декремента можно применять к указателям любого типа, за исключением типа `void*`.</span><span class="sxs-lookup"><span data-stu-id="2b9d2-105">The increment and decrement operators can be applied to pointers of any type except the type `void*`.</span></span>  
  
 <span data-ttu-id="2b9d2-106">В результате применения оператора инкремента к указателю типа `pointer-type` добавляется [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) к адресу, который содержится в переменной указателя.</span><span class="sxs-lookup"><span data-stu-id="2b9d2-106">The effect of applying the increment operator to a pointer of the type `pointer-type` is to add [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) to the address that is contained in the pointer variable.</span></span>  
  
 <span data-ttu-id="2b9d2-107">В результате применения оператора декремента к указателю типа `pointer-type` вычитается `sizeof` (`pointer-type`) из адреса, который содержится в переменной указателя.</span><span class="sxs-lookup"><span data-stu-id="2b9d2-107">The effect of applying the decrement operator to a pointer of the type `pointer-type` is to subtract `sizeof` (`pointer-type`) from the address that is contained in the pointer variable.</span></span>  
  
 <span data-ttu-id="2b9d2-108">Исключения не создаются, если операция переполняет домен указателя, а результат зависит от реализации.</span><span class="sxs-lookup"><span data-stu-id="2b9d2-108">No exceptions are generated when the operation overflows the domain of the pointer, and the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b9d2-109">Пример</span><span class="sxs-lookup"><span data-stu-id="2b9d2-109">Example</span></span>  
 <span data-ttu-id="2b9d2-110">В этом примере реализуется пошаговая обработка массива путем увеличения указателя на размер `int`.</span><span class="sxs-lookup"><span data-stu-id="2b9d2-110">In this example, you step through an array by incrementing the pointer by the size of `int`.</span></span> <span data-ttu-id="2b9d2-111">После выполнения каждого шага отображаются адрес и содержимое элемента массива.</span><span class="sxs-lookup"><span data-stu-id="2b9d2-111">With each step, you display the address and the content of the array element.</span></span>  
  
 <span data-ttu-id="2b9d2-112">[!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="2b9d2-112">[!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_1.cs)]</span></span>  
  
 <span data-ttu-id="2b9d2-113">[!code-cs[csProgGuidePointers#13](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="2b9d2-113">[!code-cs[csProgGuidePointers#13](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_2.cs)]</span></span>  
  
 <span data-ttu-id="2b9d2-114">**Значение:0 по адресу:12860272**</span><span class="sxs-lookup"><span data-stu-id="2b9d2-114">**Value:0 @ Address:12860272**</span></span>  
<span data-ttu-id="2b9d2-115">**Значение:1 по адресу:12860276**</span><span class="sxs-lookup"><span data-stu-id="2b9d2-115">**Value:1 @ Address:12860276**</span></span>  
<span data-ttu-id="2b9d2-116">**Значение:2 по адресу:12860280**</span><span class="sxs-lookup"><span data-stu-id="2b9d2-116">**Value:2 @ Address:12860280**</span></span>  
<span data-ttu-id="2b9d2-117">**Значение:3 по адресу:12860284**</span><span class="sxs-lookup"><span data-stu-id="2b9d2-117">**Value:3 @ Address:12860284**</span></span>  
<span data-ttu-id="2b9d2-118">**Значение:4 по адресу:12860288**</span><span class="sxs-lookup"><span data-stu-id="2b9d2-118">**Value:4 @ Address:12860288**</span></span>   
## <a name="see-also"></a><span data-ttu-id="2b9d2-119">См. также</span><span class="sxs-lookup"><span data-stu-id="2b9d2-119">See Also</span></span>  
 <span data-ttu-id="2b9d2-120">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="2b9d2-120">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="2b9d2-121">[Выражения указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="2b9d2-121">[Pointer Expressions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span></span>  
 <span data-ttu-id="2b9d2-122">[Операторы в C#](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="2b9d2-122">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 <span data-ttu-id="2b9d2-123">[Обработка указателей](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md) </span><span class="sxs-lookup"><span data-stu-id="2b9d2-123">[Manipulating Pointers](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md) </span></span>  
 <span data-ttu-id="2b9d2-124">[Типы указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span><span class="sxs-lookup"><span data-stu-id="2b9d2-124">[Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span></span>  
 <span data-ttu-id="2b9d2-125">[Типы](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="2b9d2-125">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 <span data-ttu-id="2b9d2-126">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="2b9d2-126">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 <span data-ttu-id="2b9d2-127">[Оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md) </span><span class="sxs-lookup"><span data-stu-id="2b9d2-127">[fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) </span></span>  
 [<span data-ttu-id="2b9d2-128">stackalloc</span><span class="sxs-lookup"><span data-stu-id="2b9d2-128">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)

