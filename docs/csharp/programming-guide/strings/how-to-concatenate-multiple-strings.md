---
title: "Практическое руководство. Сцепка нескольких строк (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- joining strings [C#]
- concatenating strings [C#]
- strings [C#], concatenation
ms.assetid: 8e16736f-4096-4f3f-be0f-9d4c3ff63520
caps.latest.revision: 21
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
ms.openlocfilehash: b191a61258a496115a4d7045046f9b4a2dbee58c
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-concatenate-multiple-strings-c-programming-guide"></a><span data-ttu-id="5a3e1-102">Практическое руководство. Сцепка нескольких строк (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="5a3e1-102">How to: Concatenate Multiple Strings (C# Programming Guide)</span></span>
<span data-ttu-id="5a3e1-103">*Объединение* подразумевает добавление одной строки к концу другой.</span><span class="sxs-lookup"><span data-stu-id="5a3e1-103">*Concatenation* is the process of appending one string to the end of another string.</span></span> <span data-ttu-id="5a3e1-104">При объединении строковых литералов или строковых констант с помощью оператора `+` компилятор создает одну строку.</span><span class="sxs-lookup"><span data-stu-id="5a3e1-104">When you concatenate string literals or string constants by using the `+` operator, the compiler creates a single string.</span></span> <span data-ttu-id="5a3e1-105">Объединение не осуществляется во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="5a3e1-105">No run time concatenation occurs.</span></span> <span data-ttu-id="5a3e1-106">Тем не менее строковые переменные могут быть объединены только во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="5a3e1-106">However, string variables can be concatenated only at run time.</span></span> <span data-ttu-id="5a3e1-107">В этом случае необходимо понимать влияние различных подходов на общую производительность.</span><span class="sxs-lookup"><span data-stu-id="5a3e1-107">In this case, you should understand the performance implications of the various approaches.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a3e1-108">Пример</span><span class="sxs-lookup"><span data-stu-id="5a3e1-108">Example</span></span>  
 <span data-ttu-id="5a3e1-109">В следующем примере показано, как разделить длинный строковый литерал на маленькие строки для повышения удобочитаемости исходного кода.</span><span class="sxs-lookup"><span data-stu-id="5a3e1-109">The following example shows how to split a long string literal into smaller strings in order to improve readability in the source code.</span></span> <span data-ttu-id="5a3e1-110">Эти части будут объединены в одну строку во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="5a3e1-110">These parts will be concatenated into a single string at compile time.</span></span> <span data-ttu-id="5a3e1-111">Независимо от числа включаемых в операцию строк, производительность во время выполнения снижаться не будет.</span><span class="sxs-lookup"><span data-stu-id="5a3e1-111">There is no run time performance cost regardless of the number of strings involved.</span></span>  
  
 <span data-ttu-id="5a3e1-112">[!code-cs[csProgGuideStrings#30](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="5a3e1-112">[!code-cs[csProgGuideStrings#30](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a3e1-113">Пример</span><span class="sxs-lookup"><span data-stu-id="5a3e1-113">Example</span></span>  
 <span data-ttu-id="5a3e1-114">Для объединения строковых переменных можно использовать операторы `+` или `+=`, а также методы <xref:System.String.Concat%2A?displayProperty=fullName>, <xref:System.String.Format%2A?displayProperty=fullName> или <xref:System.Text.StringBuilder.Append%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="5a3e1-114">To concatenate string variables, you can use the `+` or `+=` operators, or the <xref:System.String.Concat%2A?displayProperty=fullName>, <xref:System.String.Format%2A?displayProperty=fullName> or <xref:System.Text.StringBuilder.Append%2A?displayProperty=fullName> methods.</span></span> <span data-ttu-id="5a3e1-115">Оператор `+` прост в использовании и позволяет получить интуитивно понятный код.</span><span class="sxs-lookup"><span data-stu-id="5a3e1-115">The `+` operator is easy to use and makes for intuitive code.</span></span> <span data-ttu-id="5a3e1-116">Даже если в одном выражении используется несколько операторов +, содержимое строки копируется только один раз.</span><span class="sxs-lookup"><span data-stu-id="5a3e1-116">Even if you use several + operators in one statement, the string content is copied only once.</span></span> <span data-ttu-id="5a3e1-117">Однако если эта операция повторяется многократно, например в цикле, возможно ухудшение эффективности.</span><span class="sxs-lookup"><span data-stu-id="5a3e1-117">But if you repeat this operation multiple times, for example in a loop, it might cause efficiency problems.</span></span> <span data-ttu-id="5a3e1-118">Например, изучите следующий код:</span><span class="sxs-lookup"><span data-stu-id="5a3e1-118">For example, note the following code:</span></span>  
  
 <span data-ttu-id="5a3e1-119">[!code-cs[csProgGuideStrings#23](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="5a3e1-119">[!code-cs[csProgGuideStrings#23](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_2.cs)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5a3e1-120">В операциях объединения строк компилятор C# обрабатывает строки NULL так же, как и пустые строки, однако при этом не преобразует значение исходной строки NULL.</span><span class="sxs-lookup"><span data-stu-id="5a3e1-120">In string concatenation operations, the C# compiler treats a null string the same as an empty string, but it does not convert the value of the original null string.</span></span>  
  
 <span data-ttu-id="5a3e1-121">Если вы не объединяете большое число строк (например, в цикле), влияние на производительность будет незначительным.</span><span class="sxs-lookup"><span data-stu-id="5a3e1-121">If you are not concatenating large numbers of strings (for example, in a loop), the performance cost of this code is probably not significant.</span></span> <span data-ttu-id="5a3e1-122">Это справедливо также для методов <xref:System.String.Concat%2A?displayProperty=fullName> и <xref:System.String.Format%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="5a3e1-122">The same is true for the <xref:System.String.Concat%2A?displayProperty=fullName> and <xref:System.String.Format%2A?displayProperty=fullName> methods.</span></span>  
  
 <span data-ttu-id="5a3e1-123">Тем не менее, если производительность имеет первоочередное значение, для объединения строк всегда следует использовать класс <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="5a3e1-123">However, when performance is important, you should always use the <xref:System.Text.StringBuilder> class to concatenate strings.</span></span> <span data-ttu-id="5a3e1-124">В следующем коде для объединения строк используется метод <xref:System.Text.StringBuilder.Append%2A> класса <xref:System.Text.StringBuilder>, не дающий того эффекта цепочки, который характерен для оператора `+`.</span><span class="sxs-lookup"><span data-stu-id="5a3e1-124">The following code uses the <xref:System.Text.StringBuilder.Append%2A> method of the <xref:System.Text.StringBuilder> class to concatenate strings without the chaining effect of the `+` operator.</span></span>  
  
 <span data-ttu-id="5a3e1-125">[!code-cs[csProgGuideStrings#22](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="5a3e1-125">[!code-cs[csProgGuideStrings#22](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a3e1-126">См. также</span><span class="sxs-lookup"><span data-stu-id="5a3e1-126">See Also</span></span>  
 <span data-ttu-id="5a3e1-127"><xref:System.String></span><span class="sxs-lookup"><span data-stu-id="5a3e1-127"><xref:System.String></span></span>   
 <span data-ttu-id="5a3e1-128"><xref:System.Text.StringBuilder></span><span class="sxs-lookup"><span data-stu-id="5a3e1-128"><xref:System.Text.StringBuilder></span></span>   
 <span data-ttu-id="5a3e1-129">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="5a3e1-129">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="5a3e1-130">Строки</span><span class="sxs-lookup"><span data-stu-id="5a3e1-130">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)

