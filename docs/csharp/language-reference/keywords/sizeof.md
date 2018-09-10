---
title: sizeof (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
ms.openlocfilehash: f2507dd8528e2e66016524873ada890227a74ed8
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43487199"
---
# <a name="sizeof-c-reference"></a><span data-ttu-id="7660f-102">sizeof (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="7660f-102">sizeof (C# Reference)</span></span>
<span data-ttu-id="7660f-103">Позволяет получить размер в байтах для неуправляемого типа.</span><span class="sxs-lookup"><span data-stu-id="7660f-103">Used to obtain the size in bytes for an unmanaged type.</span></span>

<span data-ttu-id="7660f-104">К неуправляемым типам относятся:</span><span class="sxs-lookup"><span data-stu-id="7660f-104">Unmanaged types include:</span></span>

-   <span data-ttu-id="7660f-105">Простые типы, которые перечислены в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="7660f-105">The simple types that are listed in the following table:</span></span>
  
   |<span data-ttu-id="7660f-106">Выражение</span><span class="sxs-lookup"><span data-stu-id="7660f-106">Expression</span></span>|<span data-ttu-id="7660f-107">Константа</span><span class="sxs-lookup"><span data-stu-id="7660f-107">Constant value</span></span>|  
   |----------------|--------------------|  
   |`sizeof(sbyte)`|<span data-ttu-id="7660f-108">1</span><span class="sxs-lookup"><span data-stu-id="7660f-108">1</span></span>|  
   |`sizeof(byte)`|<span data-ttu-id="7660f-109">1</span><span class="sxs-lookup"><span data-stu-id="7660f-109">1</span></span>|  
   |`sizeof(short)`|<span data-ttu-id="7660f-110">2</span><span class="sxs-lookup"><span data-stu-id="7660f-110">2</span></span>|  
   |`sizeof(ushort)`|<span data-ttu-id="7660f-111">2</span><span class="sxs-lookup"><span data-stu-id="7660f-111">2</span></span>|  
   |`sizeof(int)`|<span data-ttu-id="7660f-112">4</span><span class="sxs-lookup"><span data-stu-id="7660f-112">4</span></span>|  
   |`sizeof(uint)`|<span data-ttu-id="7660f-113">4</span><span class="sxs-lookup"><span data-stu-id="7660f-113">4</span></span>|  
   |`sizeof(long)`|<span data-ttu-id="7660f-114">8</span><span class="sxs-lookup"><span data-stu-id="7660f-114">8</span></span>|  
   |`sizeof(ulong)`|<span data-ttu-id="7660f-115">8</span><span class="sxs-lookup"><span data-stu-id="7660f-115">8</span></span>|  
   |`sizeof(char)`|<span data-ttu-id="7660f-116">2 (Юникод)</span><span class="sxs-lookup"><span data-stu-id="7660f-116">2 (Unicode)</span></span>|  
   |`sizeof(float)`|<span data-ttu-id="7660f-117">4</span><span class="sxs-lookup"><span data-stu-id="7660f-117">4</span></span>|  
   |`sizeof(double)`|<span data-ttu-id="7660f-118">8</span><span class="sxs-lookup"><span data-stu-id="7660f-118">8</span></span>|  
   |`sizeof(decimal)`|<span data-ttu-id="7660f-119">16</span><span class="sxs-lookup"><span data-stu-id="7660f-119">16</span></span>|  
   |`sizeof(bool)`|<span data-ttu-id="7660f-120">1</span><span class="sxs-lookup"><span data-stu-id="7660f-120">1</span></span>| 
  
-   <span data-ttu-id="7660f-121">Типы перечисления.</span><span class="sxs-lookup"><span data-stu-id="7660f-121">Enum types.</span></span>
  
-   <span data-ttu-id="7660f-122">Типы указателей.</span><span class="sxs-lookup"><span data-stu-id="7660f-122">Pointer types.</span></span>
  
-   <span data-ttu-id="7660f-123">Определяемые пользователем структуры, которые не содержат полей экземпляров или автоматически реализуемых свойств, являющихся ссылочными или сконструированными типами.</span><span class="sxs-lookup"><span data-stu-id="7660f-123">User-defined structs that do not contain any instance fields or auto-implemented instance properties that are reference types or constructed types.</span></span>
  
 <span data-ttu-id="7660f-124">В приведенном ниже примере показано, как извлекать размер переменной типа `int`.</span><span class="sxs-lookup"><span data-stu-id="7660f-124">The following example shows how to retrieve the size of an `int`:</span></span>  
  
```csharp  
// Constant value 4:  
int intSize = sizeof(int);   
```  
  
## <a name="remarks"></a><span data-ttu-id="7660f-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="7660f-125">Remarks</span></span>  
 <span data-ttu-id="7660f-126">Начиная с версии 2.0 языка C# применение `sizeof` к простым типам или типам перечисления больше не требует компиляции кода в [небезопасном](unsafe.md) контексте.</span><span class="sxs-lookup"><span data-stu-id="7660f-126">Starting with version 2.0 of C#, applying `sizeof` to simple or enum types no longer requires that code be compiled in an [unsafe](unsafe.md) context.</span></span>
  
 <span data-ttu-id="7660f-127">Оператор `sizeof` перегрузить нельзя.</span><span class="sxs-lookup"><span data-stu-id="7660f-127">The `sizeof` operator cannot be overloaded.</span></span> <span data-ttu-id="7660f-128">Возвращаемые оператором `sizeof` значения принадлежат типу `int`.</span><span class="sxs-lookup"><span data-stu-id="7660f-128">The values returned by the `sizeof` operator are of type `int`.</span></span> <span data-ttu-id="7660f-129">В предыдущей таблице показаны константы, которые заменяются выражениями `sizeof`, содержащими некоторые операнды простых типов.</span><span class="sxs-lookup"><span data-stu-id="7660f-129">The previous table shows the constant values that are substituted for `sizeof` expressions that have certain simple types as operands.</span></span>  
    
 <span data-ttu-id="7660f-130">Для всех остальных типов, в том числе для структур, оператор `sizeof` можно использовать только в блоках небезопасного кода.</span><span class="sxs-lookup"><span data-stu-id="7660f-130">For all other types, including structs, the `sizeof` operator can be used only in unsafe code blocks.</span></span> <span data-ttu-id="7660f-131">Несмотря на то, что вы можете использовать метод <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType>, возвращаемое им значение не всегда совпадает со значением, которое возвращает метод `sizeof`.</span><span class="sxs-lookup"><span data-stu-id="7660f-131">Although you can use the <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> method, the value returned by this method is not always the same as the value returned by `sizeof`.</span></span> <span data-ttu-id="7660f-132">Метод <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> возвращает размер после маршалинга типа, тогда как оператор `sizeof` возвращает размер сразу после выделения памяти средой CLR, включая заполнения.</span><span class="sxs-lookup"><span data-stu-id="7660f-132"><xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> returns the size after the type has been marshaled, whereas `sizeof` returns the size as it has been allocated by the common language runtime, including any padding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7660f-133">Пример</span><span class="sxs-lookup"><span data-stu-id="7660f-133">Example</span></span>  
 [!code-csharp[csrefKeywordsOperator#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/sizeof_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="7660f-134">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="7660f-134">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7660f-135">См. также</span><span class="sxs-lookup"><span data-stu-id="7660f-135">See Also</span></span>

- [<span data-ttu-id="7660f-136">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="7660f-136">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="7660f-137">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="7660f-137">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="7660f-138">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="7660f-138">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="7660f-139">Ключевые слова операторов</span><span class="sxs-lookup"><span data-stu-id="7660f-139">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)  
- [<span data-ttu-id="7660f-140">enum</span><span class="sxs-lookup"><span data-stu-id="7660f-140">enum</span></span>](../../../csharp/language-reference/keywords/enum.md)  
- [<span data-ttu-id="7660f-141">Небезопасный код и указатели</span><span class="sxs-lookup"><span data-stu-id="7660f-141">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
- [<span data-ttu-id="7660f-142">Структуры</span><span class="sxs-lookup"><span data-stu-id="7660f-142">Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/structs.md)  
- [<span data-ttu-id="7660f-143">Константы</span><span class="sxs-lookup"><span data-stu-id="7660f-143">Constants</span></span>](../../../csharp/programming-guide/classes-and-structs/constants.md)
