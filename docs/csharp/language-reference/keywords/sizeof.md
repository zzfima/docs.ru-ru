---
title: "sizeof (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0148ae8381804ca9286315251582c8ab40778369
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="sizeof-c-reference"></a><span data-ttu-id="091eb-102">sizeof (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="091eb-102">sizeof (C# Reference)</span></span>
<span data-ttu-id="091eb-103">Позволяет получить размер в байтах для неуправляемого типа.</span><span class="sxs-lookup"><span data-stu-id="091eb-103">Used to obtain the size in bytes for an unmanaged type.</span></span> <span data-ttu-id="091eb-104">К неуправляемым типам относятся встроенные типы, перечисленные в представленной ниже таблице, а также следующие типы:</span><span class="sxs-lookup"><span data-stu-id="091eb-104">Unmanaged types include the built-in types that are listed in the table that follows, and also the following:</span></span>  
  
-   <span data-ttu-id="091eb-105">типы перечисления;</span><span class="sxs-lookup"><span data-stu-id="091eb-105">Enum types</span></span>  
  
-   <span data-ttu-id="091eb-106">типы указателей;</span><span class="sxs-lookup"><span data-stu-id="091eb-106">Pointer types</span></span>  
  
-   <span data-ttu-id="091eb-107">определяемые пользователем структуры, не содержащие полей или свойств, принадлежащих ссылочным типам.</span><span class="sxs-lookup"><span data-stu-id="091eb-107">User-defined structs that do not contain any fields or properties that are reference types</span></span>  
  
 <span data-ttu-id="091eb-108">В приведенном ниже примере показано, как извлекать размер переменной типа `int`.</span><span class="sxs-lookup"><span data-stu-id="091eb-108">The following example shows how to retrieve the size of an `int`:</span></span>  
  
```csharp  
// Constant value 4:  
int intSize = sizeof(int);   
```  
  
## <a name="remarks"></a><span data-ttu-id="091eb-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="091eb-109">Remarks</span></span>  
 <span data-ttu-id="091eb-110">Начиная с версии 2.0 языка C# при применении оператора `sizeof` к встроенным типам больше не требуется использовать [небезопасный](../../../csharp/language-reference/keywords/unsafe.md) режим.</span><span class="sxs-lookup"><span data-stu-id="091eb-110">Starting with version 2.0 of C#, applying `sizeof` to built-in types no longer requires that [unsafe](../../../csharp/language-reference/keywords/unsafe.md) mode be used.</span></span>  
  
 <span data-ttu-id="091eb-111">Оператор `sizeof` перегрузить нельзя.</span><span class="sxs-lookup"><span data-stu-id="091eb-111">The `sizeof` operator cannot be overloaded.</span></span> <span data-ttu-id="091eb-112">Возвращаемые оператором `sizeof` значения принадлежат типу `int`.</span><span class="sxs-lookup"><span data-stu-id="091eb-112">The values returned by the `sizeof` operator are of type `int`.</span></span> <span data-ttu-id="091eb-113">В приведенной ниже таблице показаны константы, которые заменяются выражениями `sizeof`, содержащими некоторые операнды встроенных типов.</span><span class="sxs-lookup"><span data-stu-id="091eb-113">The following table shows the constant values that are substituted for `sizeof` expressions that have certain built-in types as operands.</span></span>  
  
|<span data-ttu-id="091eb-114">Выражение</span><span class="sxs-lookup"><span data-stu-id="091eb-114">Expression</span></span>|<span data-ttu-id="091eb-115">Константа</span><span class="sxs-lookup"><span data-stu-id="091eb-115">Constant value</span></span>|  
|----------------|--------------------|  
|`sizeof(sbyte)`|<span data-ttu-id="091eb-116">1</span><span class="sxs-lookup"><span data-stu-id="091eb-116">1</span></span>|  
|`sizeof(byte)`|<span data-ttu-id="091eb-117">1</span><span class="sxs-lookup"><span data-stu-id="091eb-117">1</span></span>|  
|`sizeof(short)`|<span data-ttu-id="091eb-118">2</span><span class="sxs-lookup"><span data-stu-id="091eb-118">2</span></span>|  
|`sizeof(ushort)`|<span data-ttu-id="091eb-119">2</span><span class="sxs-lookup"><span data-stu-id="091eb-119">2</span></span>|  
|`sizeof(int)`|<span data-ttu-id="091eb-120">4</span><span class="sxs-lookup"><span data-stu-id="091eb-120">4</span></span>|  
|`sizeof(uint)`|<span data-ttu-id="091eb-121">4</span><span class="sxs-lookup"><span data-stu-id="091eb-121">4</span></span>|  
|`sizeof(long)`|<span data-ttu-id="091eb-122">8</span><span class="sxs-lookup"><span data-stu-id="091eb-122">8</span></span>|  
|`sizeof(ulong)`|<span data-ttu-id="091eb-123">8</span><span class="sxs-lookup"><span data-stu-id="091eb-123">8</span></span>|  
|`sizeof(char)`|<span data-ttu-id="091eb-124">2 (Юникод)</span><span class="sxs-lookup"><span data-stu-id="091eb-124">2 (Unicode)</span></span>|  
|`sizeof(float)`|<span data-ttu-id="091eb-125">4</span><span class="sxs-lookup"><span data-stu-id="091eb-125">4</span></span>|  
|`sizeof(double)`|<span data-ttu-id="091eb-126">8</span><span class="sxs-lookup"><span data-stu-id="091eb-126">8</span></span>|  
|`sizeof(decimal)`|<span data-ttu-id="091eb-127">16</span><span class="sxs-lookup"><span data-stu-id="091eb-127">16</span></span>|  
|`sizeof(bool)`|<span data-ttu-id="091eb-128">1</span><span class="sxs-lookup"><span data-stu-id="091eb-128">1</span></span>|  
  
 <span data-ttu-id="091eb-129">Для всех остальных типов, в том числе для структур, оператор `sizeof` можно использовать только в блоках небезопасного кода.</span><span class="sxs-lookup"><span data-stu-id="091eb-129">For all other types, including structs, the `sizeof` operator can be used only in unsafe code blocks.</span></span> <span data-ttu-id="091eb-130">Несмотря на то, что вы можете использовать метод <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType>, возвращаемое им значение не всегда совпадает со значением, которое возвращает метод `sizeof`.</span><span class="sxs-lookup"><span data-stu-id="091eb-130">Although you can use the <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> method, the value returned by this method is not always the same as the value returned by `sizeof`.</span></span> <span data-ttu-id="091eb-131">Метод <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> возвращает размер после маршалинга типа, тогда как оператор `sizeof` возвращает размер сразу после выделения памяти средой CLR, включая заполнения.</span><span class="sxs-lookup"><span data-stu-id="091eb-131"><xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> returns the size after the type has been marshaled, whereas `sizeof` returns the size as it has been allocated by the common language runtime, including any padding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="091eb-132">Пример</span><span class="sxs-lookup"><span data-stu-id="091eb-132">Example</span></span>  
 [!code-csharp[csrefKeywordsOperator#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/sizeof_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="091eb-133">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="091eb-133">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="091eb-134">См. также</span><span class="sxs-lookup"><span data-stu-id="091eb-134">See Also</span></span>  
 [<span data-ttu-id="091eb-135">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="091eb-135">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="091eb-136">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="091eb-136">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="091eb-137">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="091eb-137">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="091eb-138">Ключевые слова операторов</span><span class="sxs-lookup"><span data-stu-id="091eb-138">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [<span data-ttu-id="091eb-139">enum</span><span class="sxs-lookup"><span data-stu-id="091eb-139">enum</span></span>](../../../csharp/language-reference/keywords/enum.md)  
 [<span data-ttu-id="091eb-140">Небезопасный код и указатели</span><span class="sxs-lookup"><span data-stu-id="091eb-140">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [<span data-ttu-id="091eb-141">Структуры</span><span class="sxs-lookup"><span data-stu-id="091eb-141">Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/structs.md)  
 [<span data-ttu-id="091eb-142">Константы</span><span class="sxs-lookup"><span data-stu-id="091eb-142">Constants</span></span>](../../../csharp/programming-guide/classes-and-structs/constants.md)
