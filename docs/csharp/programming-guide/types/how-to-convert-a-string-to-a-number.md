---
title: Как выполнить Руководство по программированию на C#. Преобразование строки в число
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [C#]
- conversions [C#], string to int
- converting strings to int [C#]
- strings [C#], converting to int
ms.assetid: 467b9979-86ee-4afd-b734-30299cda91e3
ms.openlocfilehash: d7971bfb4b6f96a2d8efb9c09f96c0bd2856b9d0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54528723"
---
# <a name="how-to-convert-a-string-to-a-number-c-programming-guide"></a><span data-ttu-id="8e010-102">Как выполнить Руководство по программированию на C#. Преобразование строки в число</span><span class="sxs-lookup"><span data-stu-id="8e010-102">How to: Convert a String to a Number (C# Programming Guide)</span></span>
<span data-ttu-id="8e010-103">Вы можете преобразовывать [строку](../../../csharp/language-reference/keywords/string.md) в число с помощью методов в классе <xref:System.Convert> или с помощью метода `TryParse`, который можно найти в различных числовых типах (int, long, float и т. д.).</span><span class="sxs-lookup"><span data-stu-id="8e010-103">You can convert a [string](../../../csharp/language-reference/keywords/string.md) to a number by using methods in the <xref:System.Convert> class or by using the `TryParse` method found on the various numeric types (int, long, float, etc.).</span></span>  
  
 <span data-ttu-id="8e010-104">Если имеется строка, то немного эффективнее и проще вызвать метод `TryParse` (например, [`int.TryParse("11", out number)`](xref:System.Int32.TryParse%2A)).</span><span class="sxs-lookup"><span data-stu-id="8e010-104">If you have a string, it is slightly more efficient and straightforward to call a `TryParse` method (for example, [`int.TryParse("11", out number)`](xref:System.Int32.TryParse%2A)).</span></span>  <span data-ttu-id="8e010-105">Использование метода <xref:System.Convert> более удобно для общих объектов, реализующих <xref:System.IConvertible>.</span><span class="sxs-lookup"><span data-stu-id="8e010-105">Using a <xref:System.Convert> method is more useful for general objects that implement <xref:System.IConvertible>.</span></span>  
  
 <span data-ttu-id="8e010-106">Вы можете использовать методы `Parse` или `TryParse` в числовом типе, который предположительно содержит строка, таком как тип <xref:System.Int32?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8e010-106">You can use `Parse` or `TryParse` methods on the numeric type you expect the string contains, such as the <xref:System.Int32?displayProperty=nameWithType> type.</span></span>  <span data-ttu-id="8e010-107">Метод <xref:System.Convert.ToUInt32%2A?displayProperty=nameWithType> использует <xref:System.Int32.Parse%2A> внутри себя.</span><span class="sxs-lookup"><span data-stu-id="8e010-107">The <xref:System.Convert.ToUInt32%2A?displayProperty=nameWithType> method uses <xref:System.Int32.Parse%2A> internally.</span></span>  <span data-ttu-id="8e010-108">Если строка имеет недопустимый формат, `Parse` создает исключение, а `TryParse` возвращает значение [false](../../../csharp/language-reference/keywords/false.md).</span><span class="sxs-lookup"><span data-stu-id="8e010-108">If the string is not in a valid format, `Parse` throws an exception whereas `TryParse` returns [false](../../../csharp/language-reference/keywords/false.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e010-109">Пример</span><span class="sxs-lookup"><span data-stu-id="8e010-109">Example</span></span>  
 <span data-ttu-id="8e010-110">Методы `Parse` и `TryParse` игнорируют пробелы в начале и в конце строки, но все остальные символы должны быть символами, которые образуют соответствующий числовой тип (int, long, ulong, float, decimal и т. д.).</span><span class="sxs-lookup"><span data-stu-id="8e010-110">The `Parse` and `TryParse` methods ignore white space at the beginning and at the end of the string, but all other characters must be characters that form the appropriate numeric type (int, long, ulong, float, decimal, etc.).</span></span>  <span data-ttu-id="8e010-111">Любые пробелы между символов, образующих число, приводят к ошибке.</span><span class="sxs-lookup"><span data-stu-id="8e010-111">Any white space within the characters that form the number cause an error.</span></span>  <span data-ttu-id="8e010-112">Например, можно использовать `decimal.TryParse` для анализа "10", "10.3", "  10  ", но этот метод нельзя использовать для анализа 10 из "10X", "1 0" (обратите внимание на пробел), "10 .3" (обратите внимание на пробел), "10e1" (здесь работает `float.TryParse`) и т. д.</span><span class="sxs-lookup"><span data-stu-id="8e010-112">For example, you can use `decimal.TryParse` to parse "10", "10.3", "  10  ", but you cannot use this method to parse 10 from "10X", "1 0" (note space), "10 .3" (note space), "10e1" (`float.TryParse` works here), and so on.</span></span>  
  
 <span data-ttu-id="8e010-113">В приведенных ниже примерах демонстрируются успешные и неуспешные вызовы методов `Parse` и `TryParse`.</span><span class="sxs-lookup"><span data-stu-id="8e010-113">The examples below demonstrate both successful and unsuccessful calls to `Parse` and `TryParse`.</span></span>  
  
 [!code-csharp[csProgGuideTypes#5555](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_1.cs)]  
[!code-csharp[csProgGuideTypes#25](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_2.cs)]  
[!code-csharp[csProgGuideTypes#26](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_3.cs)]  
[!code-csharp[csProgGuideTypes#27](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_4.cs)]  
[!code-csharp[csProgGuideTypes#28](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_5.cs)]  
[!code-csharp[csProgGuideTypes#100](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_6.cs)]  
  
## <a name="example"></a><span data-ttu-id="8e010-114">Пример</span><span class="sxs-lookup"><span data-stu-id="8e010-114">Example</span></span>  
 <span data-ttu-id="8e010-115">В следующей таблице перечислены некоторые методы класса <xref:System.Convert>, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="8e010-115">The following table lists some of the methods from the <xref:System.Convert> class that you can use.</span></span>  
  
|<span data-ttu-id="8e010-116">Числовой тип</span><span class="sxs-lookup"><span data-stu-id="8e010-116">Numeric Type</span></span>|<span data-ttu-id="8e010-117">Метод</span><span class="sxs-lookup"><span data-stu-id="8e010-117">Method</span></span>|  
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
  
 <span data-ttu-id="8e010-118">В данном примере вызывается метод <xref:System.Convert.ToInt32%28System.String%29?displayProperty=nameWithType> для преобразования входных данных типа [string](../../../csharp/language-reference/keywords/string.md) в значение типа [int](../../../csharp/language-reference/keywords/int.md).</span><span class="sxs-lookup"><span data-stu-id="8e010-118">This example calls the <xref:System.Convert.ToInt32%28System.String%29?displayProperty=nameWithType> method to convert an input [string](../../../csharp/language-reference/keywords/string.md) to an [int](../../../csharp/language-reference/keywords/int.md) .</span></span> <span data-ttu-id="8e010-119">Код перехватывает два наиболее распространенных исключения, которые могут создаваться этим методом, — <xref:System.FormatException> и <xref:System.OverflowException>.</span><span class="sxs-lookup"><span data-stu-id="8e010-119">The code catches the two most common exceptions that can be thrown by this method, <xref:System.FormatException> and <xref:System.OverflowException>.</span></span> <span data-ttu-id="8e010-120">Если число может быть увеличено без переполнения места хранения целого числа, программа добавляет к результату 1 и печатает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="8e010-120">If the number can be incremented without overflowing the integer storage location, the program adds 1 to the result and prints the output.</span></span>  
  
 [!code-csharp[csProgGuideTypes#5555](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_1.cs)]  
[!code-csharp[csProgGuideTypes#24](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_7.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="8e010-121">См. также</span><span class="sxs-lookup"><span data-stu-id="8e010-121">See also</span></span>

- [<span data-ttu-id="8e010-122">Типы</span><span class="sxs-lookup"><span data-stu-id="8e010-122">Types</span></span>](../../../csharp/programming-guide/types/index.md)
- [<span data-ttu-id="8e010-123">Практическое руководство. Определение представления числового значения в строке</span><span class="sxs-lookup"><span data-stu-id="8e010-123">How to: Determine Whether a String Represents a Numeric Value</span></span>](../../../csharp/programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)
- [<span data-ttu-id="8e010-124">Служебная программа форматирования .NET Framework 4</span><span class="sxs-lookup"><span data-stu-id="8e010-124">.NET Framework 4 Formatting Utility</span></span>](https://code.msdn.microsoft.com/NET-Framework-4-Formatting-9c4dae8d)
