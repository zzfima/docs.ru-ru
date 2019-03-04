---
title: Руководство по программированию на C#. Арифметические операции с указателями
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], arithmetic operations
ms.assetid: d4f0b623-827e-45ce-8649-cfcebc8692aa
ms.openlocfilehash: bfa81bc926b4fe81455cecb88bc55f4dcd69268e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977842"
---
# <a name="arithmetic-operations-on-pointers-c-programming-guide"></a><span data-ttu-id="45d48-102">Арифметические операции с указателями (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="45d48-102">Arithmetic operations on pointers (C# Programming Guide)</span></span>
<span data-ttu-id="45d48-103">В этом разделе рассматривается использование арифметических операторов `+` и `-` для управления указателями.</span><span class="sxs-lookup"><span data-stu-id="45d48-103">This topic discusses using the arithmetic operators `+` and `-` to manipulate pointers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="45d48-104">Выполнение арифметических операций с указателями void невозможно.</span><span class="sxs-lookup"><span data-stu-id="45d48-104">You cannot perform any arithmetic operations on void pointers.</span></span>  
  
## <a name="adding-and-subtracting-numeric-values-to-or-from-pointers"></a><span data-ttu-id="45d48-105">Добавление числовых значений в указатели и вычитание из них</span><span class="sxs-lookup"><span data-stu-id="45d48-105">Adding and subtracting numeric values to or from pointers</span></span>  
 <span data-ttu-id="45d48-106">Можно добавить значение `n` типа [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) или [ulong](../../../csharp/language-reference/keywords/ulong.md) в указатель.</span><span class="sxs-lookup"><span data-stu-id="45d48-106">You can add a value `n` of type [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), or [ulong](../../../csharp/language-reference/keywords/ulong.md) to a pointer.</span></span> <span data-ttu-id="45d48-107">Если `p` — это указатель типа `pointer-type*`, результат `p+n` будет указателем, полученным при добавлении `n * sizeof(pointer-type)` к адресу `p`.</span><span class="sxs-lookup"><span data-stu-id="45d48-107">If `p` is a pointer of the type `pointer-type*`, the result `p+n` is the pointer resulting from adding `n * sizeof(pointer-type)` to the address of `p`.</span></span> <span data-ttu-id="45d48-108">Аналогичным образом, `p-n` является указателем, полученным в результате вычитания `n * sizeof(pointer-type)` из адреса `p`.</span><span class="sxs-lookup"><span data-stu-id="45d48-108">Similarly, `p-n` is the pointer resulting from subtracting `n * sizeof(pointer-type)` from the address of `p`.</span></span>  
  
## <a name="subtracting-pointers"></a><span data-ttu-id="45d48-109">Вычитание указателей</span><span class="sxs-lookup"><span data-stu-id="45d48-109">Subtracting pointers</span></span>  
 <span data-ttu-id="45d48-110">Также можно вычитать указатели одного типа.</span><span class="sxs-lookup"><span data-stu-id="45d48-110">You can also subtract pointers of the same type.</span></span> <span data-ttu-id="45d48-111">Результат всегда имеет тип `long`.</span><span class="sxs-lookup"><span data-stu-id="45d48-111">The result is always of the type `long`.</span></span> <span data-ttu-id="45d48-112">Например, если `p1` и `p2` являются указателями типа `pointer-type*`, то результатом выражения `p1-p2` будет:</span><span class="sxs-lookup"><span data-stu-id="45d48-112">For example, if `p1` and `p2` are pointers of the type `pointer-type*`, then the expression `p1-p2` results in:</span></span>  
  
 `((long)p1 - (long)p2)/sizeof(pointer-type)`  
  
 <span data-ttu-id="45d48-113">Исключения не создаются, если арифметическая операция переполняет домен указателя, а результат зависит от реализации.</span><span class="sxs-lookup"><span data-stu-id="45d48-113">No exceptions are generated when the arithmetic operation overflows the domain of the pointer, and the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="45d48-114">Пример</span><span class="sxs-lookup"><span data-stu-id="45d48-114">Example</span></span>  
 [!code-csharp[csProgGuidePointers#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#14)]  
  
 [!code-csharp[csProgGuidePointers#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#15)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="45d48-115">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="45d48-115">C# language specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="45d48-116">См. также</span><span class="sxs-lookup"><span data-stu-id="45d48-116">See also</span></span>

- [<span data-ttu-id="45d48-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="45d48-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="45d48-118">Небезопасный код и указатели</span><span class="sxs-lookup"><span data-stu-id="45d48-118">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
- [<span data-ttu-id="45d48-119">Выражения указателей</span><span class="sxs-lookup"><span data-stu-id="45d48-119">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [<span data-ttu-id="45d48-120">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="45d48-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
- [<span data-ttu-id="45d48-121">Обработка указателей</span><span class="sxs-lookup"><span data-stu-id="45d48-121">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)
- [<span data-ttu-id="45d48-122">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="45d48-122">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="45d48-123">Типы</span><span class="sxs-lookup"><span data-stu-id="45d48-123">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="45d48-124">unsafe</span><span class="sxs-lookup"><span data-stu-id="45d48-124">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="45d48-125">Оператор fixed</span><span class="sxs-lookup"><span data-stu-id="45d48-125">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="45d48-126">stackalloc</span><span class="sxs-lookup"><span data-stu-id="45d48-126">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
