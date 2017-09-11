---
title: "Арифметические операции над указателями (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- pointers [C#], arithmetic operations
ms.assetid: d4f0b623-827e-45ce-8649-cfcebc8692aa
caps.latest.revision: 18
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
ms.openlocfilehash: d40d44f8be590a909ff059b0fa84efb598fcf263
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="arithmetic-operations-on-pointers-c-programming-guide"></a><span data-ttu-id="5d331-102">Арифметические операции над указателями (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="5d331-102">Arithmetic Operations on Pointers (C# Programming Guide)</span></span>
<span data-ttu-id="5d331-103">В этом разделе рассматривается использование арифметических операторов `+` и **-** для управления указателями.</span><span class="sxs-lookup"><span data-stu-id="5d331-103">This topic discusses using the arithmetic operators `+` and **-** to manipulate pointers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5d331-104">Выполнение арифметических операций с указателями void невозможно.</span><span class="sxs-lookup"><span data-stu-id="5d331-104">You cannot perform any arithmetic operations on void pointers.</span></span>  
  
## <a name="adding-and-subtracting-numeric-values-to-or-from-pointers"></a><span data-ttu-id="5d331-105">Добавление числовых значений в указатели и вычитание из них</span><span class="sxs-lookup"><span data-stu-id="5d331-105">Adding and Subtracting Numeric Values to or From Pointers</span></span>  
 <span data-ttu-id="5d331-106">Можно добавить значение `n` типа [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) или [ulong](../../../csharp/language-reference/keywords/ulong.md) в указатель, `p`, любого типа, за исключением `void*`.</span><span class="sxs-lookup"><span data-stu-id="5d331-106">You can add a value `n` of type [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), or [ulong](../../../csharp/language-reference/keywords/ulong.md) to a pointer, `p`,of any type except `void*`.</span></span> <span data-ttu-id="5d331-107">Результат `p+n` — это указатель, полученный при добавлении `n * sizeof(p) to the address of p`.</span><span class="sxs-lookup"><span data-stu-id="5d331-107">The result `p+n` is the pointer resulting from adding `n * sizeof(p) to the address of p`.</span></span> <span data-ttu-id="5d331-108">Аналогичным образом, `p-n` является указателем, полученным в результате вычитания `n * sizeof(p)` из адреса `p`.</span><span class="sxs-lookup"><span data-stu-id="5d331-108">Similarly, `p-n` is the pointer resulting from subtracting `n * sizeof(p)` from the address of `p`.</span></span>  
  
## <a name="subtracting-pointers"></a><span data-ttu-id="5d331-109">Вычитание указателей</span><span class="sxs-lookup"><span data-stu-id="5d331-109">Subtracting Pointers</span></span>  
 <span data-ttu-id="5d331-110">Также можно вычитать указатели одного типа.</span><span class="sxs-lookup"><span data-stu-id="5d331-110">You can also subtract pointers of the same type.</span></span> <span data-ttu-id="5d331-111">Результат всегда имеет тип `long`.</span><span class="sxs-lookup"><span data-stu-id="5d331-111">The result is always of the type `long`.</span></span> <span data-ttu-id="5d331-112">Например, если `p1` и `p2` являются указателями типа `pointer-type*`, то результатом выражения `p1-p2` будет:</span><span class="sxs-lookup"><span data-stu-id="5d331-112">For example, if `p1` and `p2` are pointers of the type `pointer-type*`, then the expression `p1-p2` results in:</span></span>  
  
 `((long)p1 - (long)p2)/sizeof(pointer_type)`  
  
 <span data-ttu-id="5d331-113">Исключения не создаются, если арифметическая операция переполняет домен указателя, а результат зависит от реализации.</span><span class="sxs-lookup"><span data-stu-id="5d331-113">No exceptions are generated when the arithmetic operation overflows the domain of the pointer, and the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d331-114">Пример</span><span class="sxs-lookup"><span data-stu-id="5d331-114">Example</span></span>  
 <span data-ttu-id="5d331-115">[!code-cs[csProgGuidePointers#14](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="5d331-115">[!code-cs[csProgGuidePointers#14](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_1.cs)]</span></span>  
  
 <span data-ttu-id="5d331-116">[!code-cs[csProgGuidePointers#15](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="5d331-116">[!code-cs[csProgGuidePointers#15](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="5d331-117">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="5d331-117">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5d331-118">См. также</span><span class="sxs-lookup"><span data-stu-id="5d331-118">See Also</span></span>  
 <span data-ttu-id="5d331-119">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="5d331-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="5d331-120">[Небезопасный код и указатели](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span><span class="sxs-lookup"><span data-stu-id="5d331-120">[Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span></span>  
 <span data-ttu-id="5d331-121">[Выражения указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="5d331-121">[Pointer Expressions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span></span>  
 <span data-ttu-id="5d331-122">[Операторы в C#](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="5d331-122">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 <span data-ttu-id="5d331-123">[Обработка указателей](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md) </span><span class="sxs-lookup"><span data-stu-id="5d331-123">[Manipulating Pointers](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md) </span></span>  
 <span data-ttu-id="5d331-124">[Типы указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span><span class="sxs-lookup"><span data-stu-id="5d331-124">[Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span></span>  
 <span data-ttu-id="5d331-125">[Типы](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="5d331-125">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 <span data-ttu-id="5d331-126">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="5d331-126">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 <span data-ttu-id="5d331-127">[Оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md) </span><span class="sxs-lookup"><span data-stu-id="5d331-127">[fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) </span></span>  
 [<span data-ttu-id="5d331-128">stackalloc</span><span class="sxs-lookup"><span data-stu-id="5d331-128">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)

