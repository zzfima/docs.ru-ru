---
title: Руководство по программированию на C#. Арифметические операции с указателями
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], arithmetic operations
ms.assetid: d4f0b623-827e-45ce-8649-cfcebc8692aa
ms.openlocfilehash: b08f9dbf8137e483bd38a4f396732191598532cf
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65635224"
---
# <a name="arithmetic-operations-on-pointers-c-programming-guide"></a><span data-ttu-id="0a14c-102">Арифметические операции с указателями (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="0a14c-102">Arithmetic operations on pointers (C# Programming Guide)</span></span>
<span data-ttu-id="0a14c-103">В этом разделе рассматривается использование арифметических операторов `+` и `-` для управления указателями.</span><span class="sxs-lookup"><span data-stu-id="0a14c-103">This topic discusses using the arithmetic operators `+` and `-` to manipulate pointers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a14c-104">Выполнение арифметических операций с указателями void невозможно.</span><span class="sxs-lookup"><span data-stu-id="0a14c-104">You cannot perform any arithmetic operations on void pointers.</span></span>  
  
## <a name="adding-and-subtracting-numeric-values-to-or-from-pointers"></a><span data-ttu-id="0a14c-105">Добавление числовых значений в указатели и вычитание из них</span><span class="sxs-lookup"><span data-stu-id="0a14c-105">Adding and subtracting numeric values to or from pointers</span></span>  
 <span data-ttu-id="0a14c-106">Можно добавить значение `n` типа [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) или [ulong](../../../csharp/language-reference/keywords/ulong.md) в указатель.</span><span class="sxs-lookup"><span data-stu-id="0a14c-106">You can add a value `n` of type [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), or [ulong](../../../csharp/language-reference/keywords/ulong.md) to a pointer.</span></span> <span data-ttu-id="0a14c-107">Если `p` — это указатель типа `pointer-type*`, результат `p+n` будет указателем, полученным при добавлении `n * sizeof(pointer-type)` к адресу `p`.</span><span class="sxs-lookup"><span data-stu-id="0a14c-107">If `p` is a pointer of the type `pointer-type*`, the result `p+n` is the pointer resulting from adding `n * sizeof(pointer-type)` to the address of `p`.</span></span> <span data-ttu-id="0a14c-108">Аналогичным образом, `p-n` является указателем, полученным в результате вычитания `n * sizeof(pointer-type)` из адреса `p`.</span><span class="sxs-lookup"><span data-stu-id="0a14c-108">Similarly, `p-n` is the pointer resulting from subtracting `n * sizeof(pointer-type)` from the address of `p`.</span></span>  
  
## <a name="subtracting-pointers"></a><span data-ttu-id="0a14c-109">Вычитание указателей</span><span class="sxs-lookup"><span data-stu-id="0a14c-109">Subtracting pointers</span></span>  
 <span data-ttu-id="0a14c-110">Также можно вычитать указатели одного типа.</span><span class="sxs-lookup"><span data-stu-id="0a14c-110">You can also subtract pointers of the same type.</span></span> <span data-ttu-id="0a14c-111">Результат всегда имеет тип `long`.</span><span class="sxs-lookup"><span data-stu-id="0a14c-111">The result is always of the type `long`.</span></span> <span data-ttu-id="0a14c-112">Например, если `p1` и `p2` являются указателями типа `pointer-type*`, то результатом выражения `p1-p2` будет:</span><span class="sxs-lookup"><span data-stu-id="0a14c-112">For example, if `p1` and `p2` are pointers of the type `pointer-type*`, then the expression `p1-p2` results in:</span></span>  
  
 `((long)p1 - (long)p2)/sizeof(pointer-type)`  
  
 <span data-ttu-id="0a14c-113">Исключения не создаются, если арифметическая операция переполняет домен указателя, а результат зависит от реализации.</span><span class="sxs-lookup"><span data-stu-id="0a14c-113">No exceptions are generated when the arithmetic operation overflows the domain of the pointer, and the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a14c-114">Пример</span><span class="sxs-lookup"><span data-stu-id="0a14c-114">Example</span></span>  
 [!code-csharp[csProgGuidePointers#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#14)]  
  
 [!code-csharp[csProgGuidePointers#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#15)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="0a14c-115">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="0a14c-115">C# language specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0a14c-116">См. также</span><span class="sxs-lookup"><span data-stu-id="0a14c-116">See also</span></span>

- [<span data-ttu-id="0a14c-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="0a14c-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="0a14c-118">Небезопасный код и указатели</span><span class="sxs-lookup"><span data-stu-id="0a14c-118">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
- [<span data-ttu-id="0a14c-119">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="0a14c-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
- [<span data-ttu-id="0a14c-120">Обработка указателей</span><span class="sxs-lookup"><span data-stu-id="0a14c-120">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/how-to-increment-and-decrement-pointers.md)
- [<span data-ttu-id="0a14c-121">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="0a14c-121">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="0a14c-122">Типы</span><span class="sxs-lookup"><span data-stu-id="0a14c-122">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="0a14c-123">unsafe</span><span class="sxs-lookup"><span data-stu-id="0a14c-123">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="0a14c-124">Оператор fixed</span><span class="sxs-lookup"><span data-stu-id="0a14c-124">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="0a14c-125">stackalloc</span><span class="sxs-lookup"><span data-stu-id="0a14c-125">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
