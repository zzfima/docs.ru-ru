---
title: "sizeof (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
dev_langs:
- CSharp
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
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
ms.openlocfilehash: 15d11071c369fad398d40cfef301e462c006d5e4
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="sizeof-c-reference"></a><span data-ttu-id="dd328-102">sizeof (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="dd328-102">sizeof (C# Reference)</span></span>
<span data-ttu-id="dd328-103">Позволяет получить размер в байтах для неуправляемого типа.</span><span class="sxs-lookup"><span data-stu-id="dd328-103">Used to obtain the size in bytes for an unmanaged type.</span></span> <span data-ttu-id="dd328-104">К неуправляемым типам относятся встроенные типы, перечисленные в представленной ниже таблице, а также следующие типы:</span><span class="sxs-lookup"><span data-stu-id="dd328-104">Unmanaged types include the built-in types that are listed in the table that follows, and also the following:</span></span>  
  
-   <span data-ttu-id="dd328-105">типы перечисления;</span><span class="sxs-lookup"><span data-stu-id="dd328-105">Enum types</span></span>  
  
-   <span data-ttu-id="dd328-106">типы указателей;</span><span class="sxs-lookup"><span data-stu-id="dd328-106">Pointer types</span></span>  
  
-   <span data-ttu-id="dd328-107">определяемые пользователем структуры, не содержащие полей или свойств, принадлежащих ссылочным типам.</span><span class="sxs-lookup"><span data-stu-id="dd328-107">User-defined structs that do not contain any fields or properties that are reference types</span></span>  
  
 <span data-ttu-id="dd328-108">В приведенном ниже примере показано, как извлекать размер переменной типа `int`.</span><span class="sxs-lookup"><span data-stu-id="dd328-108">The following example shows how to retrieve the size of an `int`:</span></span>  
  
```csharp  
// Constant value 4:  
int intSize = sizeof(int);   
```  
  
## <a name="remarks"></a><span data-ttu-id="dd328-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="dd328-109">Remarks</span></span>  
 <span data-ttu-id="dd328-110">Начиная с версии 2.0 языка C# при применении оператора `sizeof` к встроенным типам больше не требуется использовать [небезопасный](../../../csharp/language-reference/keywords/unsafe.md) режим.</span><span class="sxs-lookup"><span data-stu-id="dd328-110">Starting with version 2.0 of C#, applying `sizeof` to built-in types no longer requires that [unsafe](../../../csharp/language-reference/keywords/unsafe.md) mode be used.</span></span>  
  
 <span data-ttu-id="dd328-111">Оператор `sizeof` перегрузить нельзя.</span><span class="sxs-lookup"><span data-stu-id="dd328-111">The `sizeof` operator cannot be overloaded.</span></span> <span data-ttu-id="dd328-112">Возвращаемые оператором `sizeof` значения принадлежат типу `int`.</span><span class="sxs-lookup"><span data-stu-id="dd328-112">The values returned by the `sizeof` operator are of type `int`.</span></span> <span data-ttu-id="dd328-113">В приведенной ниже таблице показаны константы, которые заменяются выражениями `sizeof`, содержащими некоторые операнды встроенных типов.</span><span class="sxs-lookup"><span data-stu-id="dd328-113">The following table shows the constant values that are substituted for `sizeof` expressions that have certain built-in types as operands.</span></span>  
  
|<span data-ttu-id="dd328-114">Выражение</span><span class="sxs-lookup"><span data-stu-id="dd328-114">Expression</span></span>|<span data-ttu-id="dd328-115">Константа</span><span class="sxs-lookup"><span data-stu-id="dd328-115">Constant value</span></span>|  
|----------------|--------------------|  
|`sizeof(sbyte)`|<span data-ttu-id="dd328-116">1</span><span class="sxs-lookup"><span data-stu-id="dd328-116">1</span></span>|  
|`sizeof(byte)`|<span data-ttu-id="dd328-117">1</span><span class="sxs-lookup"><span data-stu-id="dd328-117">1</span></span>|  
|`sizeof(short)`|<span data-ttu-id="dd328-118">2</span><span class="sxs-lookup"><span data-stu-id="dd328-118">2</span></span>|  
|`sizeof(ushort)`|<span data-ttu-id="dd328-119">2</span><span class="sxs-lookup"><span data-stu-id="dd328-119">2</span></span>|  
|`sizeof(int)`|<span data-ttu-id="dd328-120">4</span><span class="sxs-lookup"><span data-stu-id="dd328-120">4</span></span>|  
|`sizeof(uint)`|<span data-ttu-id="dd328-121">4</span><span class="sxs-lookup"><span data-stu-id="dd328-121">4</span></span>|  
|`sizeof(long)`|<span data-ttu-id="dd328-122">8</span><span class="sxs-lookup"><span data-stu-id="dd328-122">8</span></span>|  
|`sizeof(ulong)`|<span data-ttu-id="dd328-123">8</span><span class="sxs-lookup"><span data-stu-id="dd328-123">8</span></span>|  
|`sizeof(char)`|<span data-ttu-id="dd328-124">2 (Юникод)</span><span class="sxs-lookup"><span data-stu-id="dd328-124">2 (Unicode)</span></span>|  
|`sizeof(float)`|<span data-ttu-id="dd328-125">4</span><span class="sxs-lookup"><span data-stu-id="dd328-125">4</span></span>|  
|`sizeof(double)`|<span data-ttu-id="dd328-126">8</span><span class="sxs-lookup"><span data-stu-id="dd328-126">8</span></span>|  
|`sizeof(decimal)`|<span data-ttu-id="dd328-127">16</span><span class="sxs-lookup"><span data-stu-id="dd328-127">16</span></span>|  
|`sizeof(bool)`|<span data-ttu-id="dd328-128">1</span><span class="sxs-lookup"><span data-stu-id="dd328-128">1</span></span>|  
  
 <span data-ttu-id="dd328-129">Для всех остальных типов, в том числе для структур, оператор `sizeof` можно использовать только в блоках небезопасного кода.</span><span class="sxs-lookup"><span data-stu-id="dd328-129">For all other types, including structs, the `sizeof` operator can be used only in unsafe code blocks.</span></span> <span data-ttu-id="dd328-130">Несмотря на то, что вы можете использовать метод <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=fullName>, возвращаемое им значение не всегда совпадает со значением, которое возвращает метод `sizeof`.</span><span class="sxs-lookup"><span data-stu-id="dd328-130">Although you can use the <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=fullName> method, the value returned by this method is not always the same as the value returned by `sizeof`.</span></span> <span data-ttu-id="dd328-131">Метод <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=fullName> возвращает размер после маршалинга типа, тогда как оператор `sizeof` возвращает размер сразу после выделения памяти средой CLR, включая заполнения.</span><span class="sxs-lookup"><span data-stu-id="dd328-131"><xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=fullName> returns the size after the type has been marshaled, whereas `sizeof` returns the size as it has been allocated by the common language runtime, including any padding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd328-132">Пример</span><span class="sxs-lookup"><span data-stu-id="dd328-132">Example</span></span>  
 <span data-ttu-id="dd328-133">[!code-cs[csrefKeywordsOperator#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/sizeof_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="dd328-133">[!code-cs[csrefKeywordsOperator#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/sizeof_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="dd328-134">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="dd328-134">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="dd328-135">См. также</span><span class="sxs-lookup"><span data-stu-id="dd328-135">See Also</span></span>  
 <span data-ttu-id="dd328-136">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="dd328-136">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="dd328-137">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="dd328-137">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="dd328-138">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="dd328-138">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="dd328-139">[Ключевые слова операторов](../../../csharp/language-reference/keywords/operator-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="dd328-139">[Operator Keywords](../../../csharp/language-reference/keywords/operator-keywords.md) </span></span>  
 <span data-ttu-id="dd328-140">[enum](../../../csharp/language-reference/keywords/enum.md) </span><span class="sxs-lookup"><span data-stu-id="dd328-140">[enum](../../../csharp/language-reference/keywords/enum.md) </span></span>  
 <span data-ttu-id="dd328-141">[Небезопасный код и указатели](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span><span class="sxs-lookup"><span data-stu-id="dd328-141">[Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span></span>  
 <span data-ttu-id="dd328-142">[Структуры](../../../csharp/programming-guide/classes-and-structs/structs.md) </span><span class="sxs-lookup"><span data-stu-id="dd328-142">[Structs](../../../csharp/programming-guide/classes-and-structs/structs.md) </span></span>  
 [<span data-ttu-id="dd328-143">Константы</span><span class="sxs-lookup"><span data-stu-id="dd328-143">Constants</span></span>](../../../csharp/programming-guide/classes-and-structs/constants.md)

