---
title: "Практическое руководство. Увеличение и уменьшение указателей (Руководство по программированию в C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- pointers [C#], increment and decrement
- pointer expressions [C#], increment and decrement
ms.assetid: 1b8b9281-44ee-485a-9045-3db38a4b4b89
caps.latest.revision: "20"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2c8efc6d0844d867ad6eebccf3bb22c03e6d5020
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-increment-and-decrement-pointers-c-programming-guide"></a><span data-ttu-id="a0174-102">Практическое руководство. Увеличение и уменьшение указателей (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="a0174-102">How to: Increment and Decrement Pointers (C# Programming Guide)</span></span>
<span data-ttu-id="a0174-103">С помощью операторов инкремента и декремента (`++` и `--`) можно изменить расположение указателя на тип на величину [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`)*.</span><span class="sxs-lookup"><span data-stu-id="a0174-103">Use the increment and the decrement operators, `++` and `--`, to change the pointer location by [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) for a pointer of type pointer-type*.</span></span> <span data-ttu-id="a0174-104">Выражения инкремента или декремента имеют следующий вид:</span><span class="sxs-lookup"><span data-stu-id="a0174-104">The increment and decrement expressions take the following form:</span></span>  
  
```  
++p;  
p++;  
--p;  
p--;  
```  
  
 <span data-ttu-id="a0174-105">Операторы инкремента и декремента можно применять к указателям любого типа, за исключением типа `void*`.</span><span class="sxs-lookup"><span data-stu-id="a0174-105">The increment and decrement operators can be applied to pointers of any type except the type `void*`.</span></span>  
  
 <span data-ttu-id="a0174-106">В результате применения оператора инкремента к указателю типа `pointer-type` добавляется [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) к адресу, который содержится в переменной указателя.</span><span class="sxs-lookup"><span data-stu-id="a0174-106">The effect of applying the increment operator to a pointer of the type `pointer-type` is to add [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) to the address that is contained in the pointer variable.</span></span>  
  
 <span data-ttu-id="a0174-107">В результате применения оператора декремента к указателю типа `pointer-type` вычитается `sizeof` (`pointer-type`) из адреса, который содержится в переменной указателя.</span><span class="sxs-lookup"><span data-stu-id="a0174-107">The effect of applying the decrement operator to a pointer of the type `pointer-type` is to subtract `sizeof` (`pointer-type`) from the address that is contained in the pointer variable.</span></span>  
  
 <span data-ttu-id="a0174-108">Исключения не создаются, если операция переполняет домен указателя, а результат зависит от реализации.</span><span class="sxs-lookup"><span data-stu-id="a0174-108">No exceptions are generated when the operation overflows the domain of the pointer, and the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0174-109">Пример</span><span class="sxs-lookup"><span data-stu-id="a0174-109">Example</span></span>  
 <span data-ttu-id="a0174-110">В этом примере реализуется пошаговая обработка массива путем увеличения указателя на размер `int`.</span><span class="sxs-lookup"><span data-stu-id="a0174-110">In this example, you step through an array by incrementing the pointer by the size of `int`.</span></span> <span data-ttu-id="a0174-111">После выполнения каждого шага отображаются адрес и содержимое элемента массива.</span><span class="sxs-lookup"><span data-stu-id="a0174-111">With each step, you display the address and the content of the array element.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#13](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_2.cs)]  
  
 <span data-ttu-id="a0174-112">**Значение:0 по адресу:12860272**</span><span class="sxs-lookup"><span data-stu-id="a0174-112">**Value:0 @ Address:12860272**</span></span>  
<span data-ttu-id="a0174-113">**Значение:1 по адресу:12860276**</span><span class="sxs-lookup"><span data-stu-id="a0174-113">**Value:1 @ Address:12860276**</span></span>  
<span data-ttu-id="a0174-114">**Значение:2 по адресу:12860280**</span><span class="sxs-lookup"><span data-stu-id="a0174-114">**Value:2 @ Address:12860280**</span></span>  
<span data-ttu-id="a0174-115">**Значение:3 по адресу:12860284**</span><span class="sxs-lookup"><span data-stu-id="a0174-115">**Value:3 @ Address:12860284**</span></span>  
<span data-ttu-id="a0174-116">**Значение:4 по адресу:12860288**</span><span class="sxs-lookup"><span data-stu-id="a0174-116">**Value:4 @ Address:12860288**</span></span>   
## <a name="see-also"></a><span data-ttu-id="a0174-117">См. также</span><span class="sxs-lookup"><span data-stu-id="a0174-117">See Also</span></span>  
 [<span data-ttu-id="a0174-118">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a0174-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="a0174-119">Выражения указателей</span><span class="sxs-lookup"><span data-stu-id="a0174-119">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [<span data-ttu-id="a0174-120">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="a0174-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="a0174-121">Обработка указателей</span><span class="sxs-lookup"><span data-stu-id="a0174-121">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
 [<span data-ttu-id="a0174-122">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="a0174-122">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [<span data-ttu-id="a0174-123">Типы</span><span class="sxs-lookup"><span data-stu-id="a0174-123">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="a0174-124">unsafe</span><span class="sxs-lookup"><span data-stu-id="a0174-124">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="a0174-125">Оператор fixed</span><span class="sxs-lookup"><span data-stu-id="a0174-125">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="a0174-126">stackalloc</span><span class="sxs-lookup"><span data-stu-id="a0174-126">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
