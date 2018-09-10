---
title: Арифметические операции над указателями (Руководство по программированию в C#)
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], arithmetic operations
ms.assetid: d4f0b623-827e-45ce-8649-cfcebc8692aa
ms.openlocfilehash: 3694699466f7a200eecd5eef85f60fa19f9584a8
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43862307"
---
# <a name="arithmetic-operations-on-pointers-c-programming-guide"></a><span data-ttu-id="2e682-102">Арифметические операции над указателями (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="2e682-102">Arithmetic Operations on Pointers (C# Programming Guide)</span></span>
<span data-ttu-id="2e682-103">В этом разделе рассматривается использование арифметических операторов `+` и **-** для управления указателями.</span><span class="sxs-lookup"><span data-stu-id="2e682-103">This topic discusses using the arithmetic operators `+` and **-** to manipulate pointers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2e682-104">Выполнение арифметических операций с указателями void невозможно.</span><span class="sxs-lookup"><span data-stu-id="2e682-104">You cannot perform any arithmetic operations on void pointers.</span></span>  
  
## <a name="adding-and-subtracting-numeric-values-to-or-from-pointers"></a><span data-ttu-id="2e682-105">Добавление числовых значений в указатели и вычитание из них</span><span class="sxs-lookup"><span data-stu-id="2e682-105">Adding and Subtracting Numeric Values to or From Pointers</span></span>  
 <span data-ttu-id="2e682-106">Можно добавить значение `n` типа [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) или [ulong](../../../csharp/language-reference/keywords/ulong.md) в указатель, `p`, любого типа, за исключением `void*`.</span><span class="sxs-lookup"><span data-stu-id="2e682-106">You can add a value `n` of type [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), or [ulong](../../../csharp/language-reference/keywords/ulong.md) to a pointer, `p`,of any type except `void*`.</span></span> <span data-ttu-id="2e682-107">Результат `p+n` — это указатель, полученный при добавлении `n * sizeof(p) to the address of p`.</span><span class="sxs-lookup"><span data-stu-id="2e682-107">The result `p+n` is the pointer resulting from adding `n * sizeof(p) to the address of p`.</span></span> <span data-ttu-id="2e682-108">Аналогичным образом, `p-n` является указателем, полученным в результате вычитания `n * sizeof(p)` из адреса `p`.</span><span class="sxs-lookup"><span data-stu-id="2e682-108">Similarly, `p-n` is the pointer resulting from subtracting `n * sizeof(p)` from the address of `p`.</span></span>  
  
## <a name="subtracting-pointers"></a><span data-ttu-id="2e682-109">Вычитание указателей</span><span class="sxs-lookup"><span data-stu-id="2e682-109">Subtracting Pointers</span></span>  
 <span data-ttu-id="2e682-110">Также можно вычитать указатели одного типа.</span><span class="sxs-lookup"><span data-stu-id="2e682-110">You can also subtract pointers of the same type.</span></span> <span data-ttu-id="2e682-111">Результат всегда имеет тип `long`.</span><span class="sxs-lookup"><span data-stu-id="2e682-111">The result is always of the type `long`.</span></span> <span data-ttu-id="2e682-112">Например, если `p1` и `p2` являются указателями типа `pointer-type*`, то результатом выражения `p1-p2` будет:</span><span class="sxs-lookup"><span data-stu-id="2e682-112">For example, if `p1` and `p2` are pointers of the type `pointer-type*`, then the expression `p1-p2` results in:</span></span>  
  
 `((long)p1 - (long)p2)/sizeof(pointer_type)`  
  
 <span data-ttu-id="2e682-113">Исключения не создаются, если арифметическая операция переполняет домен указателя, а результат зависит от реализации.</span><span class="sxs-lookup"><span data-stu-id="2e682-113">No exceptions are generated when the arithmetic operation overflows the domain of the pointer, and the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e682-114">Пример</span><span class="sxs-lookup"><span data-stu-id="2e682-114">Example</span></span>  
 [!code-csharp[csProgGuidePointers#14](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#15](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="2e682-115">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="2e682-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2e682-116">См. также</span><span class="sxs-lookup"><span data-stu-id="2e682-116">See Also</span></span>

- [<span data-ttu-id="2e682-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="2e682-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="2e682-118">Небезопасный код и указатели</span><span class="sxs-lookup"><span data-stu-id="2e682-118">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
- [<span data-ttu-id="2e682-119">Выражения указателей</span><span class="sxs-lookup"><span data-stu-id="2e682-119">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
- [<span data-ttu-id="2e682-120">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="2e682-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="2e682-121">Обработка указателей</span><span class="sxs-lookup"><span data-stu-id="2e682-121">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
- [<span data-ttu-id="2e682-122">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="2e682-122">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
- [<span data-ttu-id="2e682-123">Типы</span><span class="sxs-lookup"><span data-stu-id="2e682-123">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
- [<span data-ttu-id="2e682-124">unsafe</span><span class="sxs-lookup"><span data-stu-id="2e682-124">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
- [<span data-ttu-id="2e682-125">Оператор fixed</span><span class="sxs-lookup"><span data-stu-id="2e682-125">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
- [<span data-ttu-id="2e682-126">stackalloc</span><span class="sxs-lookup"><span data-stu-id="2e682-126">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
