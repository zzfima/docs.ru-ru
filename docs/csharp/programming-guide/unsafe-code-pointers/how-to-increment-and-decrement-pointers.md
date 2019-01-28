---
title: Руководство по программированию на C#. Увеличение и уменьшение указателей
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], increment and decrement
- pointer expressions [C#], increment and decrement
ms.assetid: 1b8b9281-44ee-485a-9045-3db38a4b4b89
ms.openlocfilehash: ead179c3711a5e63bbdc2ec2b5644d5991b82ee7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54573274"
---
# <a name="how-to-increment-and-decrement-pointers-c-programming-guide"></a><span data-ttu-id="60fd7-102">Практическое руководство. Увеличение и уменьшение указателей (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="60fd7-102">How to: increment and decrement pointers (C# Programming Guide)</span></span>

<span data-ttu-id="60fd7-103">С помощью операторов инкремента и декремента (`++` и `--`) можно изменить расположение указателя типа `pointer-type*` на `sizeof(pointer-type)`.</span><span class="sxs-lookup"><span data-stu-id="60fd7-103">Use the increment and the decrement operators, `++` and `--`, to change the pointer location by `sizeof(pointer-type)` for a pointer of the type `pointer-type*`.</span></span> <span data-ttu-id="60fd7-104">Выражения инкремента или декремента имеют следующий вид:</span><span class="sxs-lookup"><span data-stu-id="60fd7-104">The increment and decrement expressions take the following form:</span></span>  
  
```csharp
++p;  
p++;  
--p;  
p--;  
```  
  
 <span data-ttu-id="60fd7-105">Операторы инкремента и декремента можно применять к указателям любого типа, за исключением типа `void*`.</span><span class="sxs-lookup"><span data-stu-id="60fd7-105">The increment and decrement operators can be applied to pointers of any type except the type `void*`.</span></span>  
  
 <span data-ttu-id="60fd7-106">В результате применения оператора инкремента к указателю типа `pointer-type*` к адресу, который содержится в переменной указателя, добавляется `sizeof(pointer-type)`.</span><span class="sxs-lookup"><span data-stu-id="60fd7-106">The effect of applying the increment operator to a pointer of the type `pointer-type*` is to add `sizeof(pointer-type)` to the address that is contained in the pointer variable.</span></span>  
  
 <span data-ttu-id="60fd7-107">В результате применения оператора декремента к указателю типа `pointer-type*` из адреса, который содержится в переменной указателя, вычитается `sizeof(pointer-type)`.</span><span class="sxs-lookup"><span data-stu-id="60fd7-107">The effect of applying the decrement operator to a pointer of the type `pointer-type*` is to subtract `sizeof(pointer-type)` from the address that is contained in the pointer variable.</span></span>  
  
 <span data-ttu-id="60fd7-108">Исключения не создаются, если операция переполняет домен указателя, а результат зависит от реализации.</span><span class="sxs-lookup"><span data-stu-id="60fd7-108">No exceptions are generated when the operation overflows the domain of the pointer, and the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60fd7-109">Пример</span><span class="sxs-lookup"><span data-stu-id="60fd7-109">Example</span></span>  
 <span data-ttu-id="60fd7-110">В этом примере реализуется пошаговая обработка массива путем увеличения указателя на размер `int`.</span><span class="sxs-lookup"><span data-stu-id="60fd7-110">In this example, you step through an array by incrementing the pointer by the size of `int`.</span></span> <span data-ttu-id="60fd7-111">После выполнения каждого шага отображаются адрес и содержимое элемента массива.</span><span class="sxs-lookup"><span data-stu-id="60fd7-111">With each step, you display the address and the content of the array element.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#13](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_2.cs)]  
  
<span data-ttu-id="60fd7-112">**Значение:0 @ Адрес:12860272**
**Значение:1 @ Адрес:12860276**
**Значение:2 @ Адрес:12860280**
**Значение:3 @ Адрес:12860284**
**Значение:4 @ Адрес:12860288**</span><span class="sxs-lookup"><span data-stu-id="60fd7-112">**Value:0 @ Address:12860272**
**Value:1 @ Address:12860276**
**Value:2 @ Address:12860280**
**Value:3 @ Address:12860284**
**Value:4 @ Address:12860288**</span></span>

## <a name="see-also"></a><span data-ttu-id="60fd7-113">См. также</span><span class="sxs-lookup"><span data-stu-id="60fd7-113">See also</span></span>

- [<span data-ttu-id="60fd7-114">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="60fd7-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="60fd7-115">Выражения указателей</span><span class="sxs-lookup"><span data-stu-id="60fd7-115">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [<span data-ttu-id="60fd7-116">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="60fd7-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
- [<span data-ttu-id="60fd7-117">Обработка указателей</span><span class="sxs-lookup"><span data-stu-id="60fd7-117">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)
- [<span data-ttu-id="60fd7-118">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="60fd7-118">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="60fd7-119">Типы</span><span class="sxs-lookup"><span data-stu-id="60fd7-119">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="60fd7-120">unsafe</span><span class="sxs-lookup"><span data-stu-id="60fd7-120">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="60fd7-121">Оператор fixed</span><span class="sxs-lookup"><span data-stu-id="60fd7-121">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="60fd7-122">stackalloc</span><span class="sxs-lookup"><span data-stu-id="60fd7-122">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
- [<span data-ttu-id="60fd7-123">sizeof</span><span class="sxs-lookup"><span data-stu-id="60fd7-123">sizeof</span></span>](../../../csharp/language-reference/keywords/sizeof.md)
