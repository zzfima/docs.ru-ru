---
title: "Практическое руководство. Преобразование строки в число (руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- conversions [C#]
- conversions [C#], string to int
- converting strings to int [C#]
- strings [C#], converting to int
ms.assetid: 467b9979-86ee-4afd-b734-30299cda91e3
caps.latest.revision: 34
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
ms.openlocfilehash: 08d13e40a385ce8e9011b508b04361b2e050f904
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-convert-a-string-to-a-number-c-programming-guide"></a><span data-ttu-id="d3c3d-102">Практическое руководство. Преобразование строки в число (руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="d3c3d-102">How to: Convert a String to a Number (C# Programming Guide)</span></span>
<span data-ttu-id="d3c3d-103">Вы можете преобразовывать [строку](../../../csharp/language-reference/keywords/string.md) в число с помощью методов в классе <xref:System.Convert> или с помощью метода `TryParse`, который можно найти в различных числовых типах (int, long, float и т. д.).</span><span class="sxs-lookup"><span data-stu-id="d3c3d-103">You can convert a [string](../../../csharp/language-reference/keywords/string.md) to a number by using methods in the <xref:System.Convert> class or by using the `TryParse` method found on the various numeric types (int, long, float, etc.).</span></span>  
  
 <span data-ttu-id="d3c3d-104">Если имеется строка, то немного более эффективно и проще вызвать метод `TryParse` (например, `int.TryParse("11")`).</span><span class="sxs-lookup"><span data-stu-id="d3c3d-104">If you have a string, it is slightly more efficient and straightforward to call a `TryParse` method (for example, `int.TryParse("11")`).</span></span>  <span data-ttu-id="d3c3d-105">Использование метода `Convert` более удобно для общих объектов, реализующих <xref:System.IConvertible>.</span><span class="sxs-lookup"><span data-stu-id="d3c3d-105">Using a `Convert` method is more useful for general objects that implement <xref:System.IConvertible>.</span></span>  
  
 <span data-ttu-id="d3c3d-106">Вы можете использовать методы `Parse` или `TryParse` в числовом типе, который предположительно содержит строка, таком как тип <xref:System.Int32?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="d3c3d-106">You can use `Parse` or `TryParse` methods on the numeric type you expect the string contains, such as the <xref:System.Int32?displayProperty=fullName> type.</span></span>  <span data-ttu-id="d3c3d-107">Метод <xref:System.Convert.ToUInt32%2A?displayProperty=fullName> использует <xref:System.Int32.Parse%2A> внутри себя.</span><span class="sxs-lookup"><span data-stu-id="d3c3d-107">The <xref:System.Convert.ToUInt32%2A?displayProperty=fullName> method uses <xref:System.Int32.Parse%2A> internally.</span></span>  <span data-ttu-id="d3c3d-108">Если строка имеет недопустимый формат, `Parse` создает исключение, а `TryParse` возвращает значение [false](../../../csharp/language-reference/keywords/false.md).</span><span class="sxs-lookup"><span data-stu-id="d3c3d-108">If the string is not in a valid format, `Parse` throws an exception whereas `TryParse` returns [false](../../../csharp/language-reference/keywords/false.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3c3d-109">Пример</span><span class="sxs-lookup"><span data-stu-id="d3c3d-109">Example</span></span>  
 <span data-ttu-id="d3c3d-110">Методы `Parse` и `TryParse` игнорируют пробелы в начале и в конце строки, но все остальные символы должны быть символами, которые образуют соответствующий числовой тип (int, long, ulong, float, decimal и т. д.).</span><span class="sxs-lookup"><span data-stu-id="d3c3d-110">The `Parse` and `TryParse` methods ignore whitespace at the beginning and at the end of the string, but all other characters must be characters that form the appropriate numeric type (int, long, ulong, float, decimal, etc.).</span></span>  <span data-ttu-id="d3c3d-111">Любые пробелы в символах, образующих число, приводят к ошибке.</span><span class="sxs-lookup"><span data-stu-id="d3c3d-111">Any whitespace within the characters that form the number cause an error.</span></span>  <span data-ttu-id="d3c3d-112">Например, можно использовать `decimal.TryParse` для анализа "10", "10.3", "  10  ", но этот метод нельзя использовать для анализа 10 из "10X", "1 0" (обратите внимание на пробел), "10 .3" (обратите внимание на пробел), "10e1" (здесь работает `float.TryParse`) и т. д.</span><span class="sxs-lookup"><span data-stu-id="d3c3d-112">For example, you can use `decimal.TryParse` to parse "10", "10.3", "  10  ", but you cannot use this method to parse 10 from "10X", "1 0" (note space), "10 .3" (note space), "10e1" (`float.TryParse` works here), and so on.</span></span>  
  
 <span data-ttu-id="d3c3d-113">В приведенных ниже примерах демонстрируются успешные и неуспешные вызовы методов `Parse` и `TryParse`.</span><span class="sxs-lookup"><span data-stu-id="d3c3d-113">The examples below demonstrate both successful and unsuccessful calls to `Parse` and `TryParse`.</span></span>  
  
 <span data-ttu-id="d3c3d-114">[!code-cs[csProgGuideTypes#5555](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d3c3d-114">[!code-cs[csProgGuideTypes#5555](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_1.cs)]</span></span>  
<span data-ttu-id="d3c3d-115">[!code-cs[csProgGuideTypes#25](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="d3c3d-115">[!code-cs[csProgGuideTypes#25](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_2.cs)]</span></span>  
<span data-ttu-id="d3c3d-116">[!code-cs[csProgGuideTypes#26](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="d3c3d-116">[!code-cs[csProgGuideTypes#26](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_3.cs)]</span></span>  
<span data-ttu-id="d3c3d-117">[!code-cs[csProgGuideTypes#27](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="d3c3d-117">[!code-cs[csProgGuideTypes#27](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_4.cs)]</span></span>  
<span data-ttu-id="d3c3d-118">[!code-cs[csProgGuideTypes#28](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="d3c3d-118">[!code-cs[csProgGuideTypes#28](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_5.cs)]</span></span>  
<span data-ttu-id="d3c3d-119">[!code-cs[csProgGuideTypes#100](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="d3c3d-119">[!code-cs[csProgGuideTypes#100](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_6.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3c3d-120">Пример</span><span class="sxs-lookup"><span data-stu-id="d3c3d-120">Example</span></span>  
 <span data-ttu-id="d3c3d-121">В следующей таблице перечислены некоторые методы класса <xref:System.Convert>, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="d3c3d-121">The following table lists some of the methods from the <xref:System.Convert> class that you can use.</span></span>  
  
|<span data-ttu-id="d3c3d-122">Числовой тип</span><span class="sxs-lookup"><span data-stu-id="d3c3d-122">Numeric Type</span></span>|<span data-ttu-id="d3c3d-123">Метод</span><span class="sxs-lookup"><span data-stu-id="d3c3d-123">Method</span></span>|  
|------------------|------------|  
|`decimal`|<xref:System.Convert.ToDecimal%28System.String%29>|  
|`float`|<xref:System.Convert.ToSingle%28System.String%29>|  
|`double`|<xref:System.Convert.ToDouble%28System.String%29>|  
|`short`|<xref:System.Convert.ToInt16%28System.String%29>|  
|`int`|<xref:System.Convert.ToInt32%28System.String%29>|  
|`long`|<xref:System.Convert.ToInt64%28System.String%29>|  
|`ushort`|<xref:System.Convert.ToUInt16%28System.String%29>|  
|`uint`|<xref:System.Convert.ToUInt32%28System.String%29>|  
|`ulong`|<xref:System.Convert.ToUInt64%28System.String%29>|  
  
 <span data-ttu-id="d3c3d-124">В данном примере вызывается метод <xref:System.Convert.ToInt32%28System.String%29?displayProperty=fullName> для преобразования входных данных типа [string](../../../csharp/language-reference/keywords/string.md) в значение типа [int](../../../csharp/language-reference/keywords/int.md).</span><span class="sxs-lookup"><span data-stu-id="d3c3d-124">This example calls the <xref:System.Convert.ToInt32%28System.String%29?displayProperty=fullName> method to convert an input [string](../../../csharp/language-reference/keywords/string.md) to an [int](../../../csharp/language-reference/keywords/int.md) .</span></span> <span data-ttu-id="d3c3d-125">Код перехватывает два наиболее распространенных исключения, которые могут создаваться этим методом, — <xref:System.FormatException> и <xref:System.OverflowException>.</span><span class="sxs-lookup"><span data-stu-id="d3c3d-125">The code catches the two most common exceptions that can be thrown by this method, <xref:System.FormatException> and <xref:System.OverflowException>.</span></span> <span data-ttu-id="d3c3d-126">Если число может быть увеличено без переполнения места хранения целого числа, программа добавляет к результату 1 и печатает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="d3c3d-126">If the number can be incremented without overflowing the integer storage location, the program adds 1 to the result and prints the output.</span></span>  
  
 <span data-ttu-id="d3c3d-127">[!code-cs[csProgGuideTypes#5555](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d3c3d-127">[!code-cs[csProgGuideTypes#5555](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_1.cs)]</span></span>  
<span data-ttu-id="d3c3d-128">[!code-cs[csProgGuideTypes#24](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="d3c3d-128">[!code-cs[csProgGuideTypes#24](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_7.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3c3d-129">См. также</span><span class="sxs-lookup"><span data-stu-id="d3c3d-129">See Also</span></span>  
 <span data-ttu-id="d3c3d-130">[Типы](../../../csharp/programming-guide/types/index.md) </span><span class="sxs-lookup"><span data-stu-id="d3c3d-130">[Types](../../../csharp/programming-guide/types/index.md) </span></span>  
 <span data-ttu-id="d3c3d-131">[Практическое руководство. Определение представления числового значения в строке](../../../csharp/programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md) </span><span class="sxs-lookup"><span data-stu-id="d3c3d-131">[How to: Determine Whether a String Represents a Numeric Value](../../../csharp/programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md) </span></span>  
 [<span data-ttu-id="d3c3d-132">Служебная программа форматирования .NET Framework 4</span><span class="sxs-lookup"><span data-stu-id="d3c3d-132">.NET Framework 4 Formatting Utility</span></span>](http://code.msdn.microsoft.com/NET-Framework-4-Formatting-9c4dae8d)

