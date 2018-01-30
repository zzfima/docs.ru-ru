---
title: "Практическое руководство. Сцепка нескольких строк (руководство по C#)"
description: "C# поддерживает различные способы сцепки строк. Узнайте, какие доступны варианты и как выбирать между ними."
ms.date: 01/11/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- joining strings [C#]
- concatenating strings [C#]
- strings [C#], concatenation
ms.assetid: 8e16736f-4096-4f3f-be0f-9d4c3ff63520
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a4bc5e04edba48065746b96841b628ec5843c5e9
ms.sourcegitcommit: f28752eab00d2bd97e971542c0f49ce63cfbc239
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2018
---
# <a name="how-to-concatenate-multiple-strings-c-guide"></a><span data-ttu-id="10583-104">Практическое руководство. Сцепка нескольких строк (руководство по C#)</span><span class="sxs-lookup"><span data-stu-id="10583-104">How to: Concatenate Multiple Strings (C# Guide)</span></span>

<span data-ttu-id="10583-105">*Объединение* подразумевает добавление одной строки к концу другой.</span><span class="sxs-lookup"><span data-stu-id="10583-105">*Concatenation* is the process of appending one string to the end of another string.</span></span> <span data-ttu-id="10583-106">Вы можете сцеплять строки с помощью оператора "+".</span><span class="sxs-lookup"><span data-stu-id="10583-106">You concatenate strings by using the + operator.</span></span> <span data-ttu-id="10583-107">Строковые литералы и константы сцепляются во время компиляции, а не во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="10583-107">For string literals and string constants, concatenation occurs at compile time; no run-time concatenation occurs.</span></span> <span data-ttu-id="10583-108">Строковые переменные сцепляются только во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="10583-108">For string variables, concatenation occurs only at run time.</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="10583-109">Следующий пример показывает использование сцепки для разделения длинного строкового литерала на строки меньшего размера, чтобы повысить удобочитаемость исходного кода.</span><span class="sxs-lookup"><span data-stu-id="10583-109">The following example uses concatenation to split a long string literal into smaller strings in order to improve readability in the source code.</span></span> <span data-ttu-id="10583-110">Эти части будут объединены в одну строку во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="10583-110">These parts will be concatenated into a single string at compile time.</span></span> <span data-ttu-id="10583-111">Количество строк не влияет на производительность во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="10583-111">There is no run-time performance cost regardless of the number of strings involved.</span></span>  
  
 [!code-csharp-interactive[Combining strings at compile time](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#1)]  
  

<span data-ttu-id="10583-112">Для сцепки строковых переменных вы можете использовать операторы `+` или `+=`, [интерполяцию строк](../tutorials/string-interpolation.md), а также методы <xref:System.String.Concat%2A?displayProperty=nameWithType>, <xref:System.String.Format%2A?displayProperty=nameWithType> или <xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="10583-112">To concatenate string variables, you can use the `+` or `+=` operators, [string interpolation](../tutorials/string-interpolation.md) or the <xref:System.String.Concat%2A?displayProperty=nameWithType>, <xref:System.String.Format%2A?displayProperty=nameWithType> or <xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="10583-113">Оператор `+` прост в использовании и позволяет получить интуитивно понятный код.</span><span class="sxs-lookup"><span data-stu-id="10583-113">The `+` operator is easy to use and makes for intuitive code.</span></span> <span data-ttu-id="10583-114">Даже если в одном выражении используется несколько операторов +, содержимое строки копируется только один раз.</span><span class="sxs-lookup"><span data-stu-id="10583-114">Even if you use several + operators in one statement, the string content is copied only once.</span></span> <span data-ttu-id="10583-115">В следующем коде показаны два примера использования оператора `+` для сцепки строк.</span><span class="sxs-lookup"><span data-stu-id="10583-115">The following code shows two examples of using the `+` operator to concatenate strings:</span></span>

[!code-csharp-interactive[combining strings using +](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#2)]  

<span data-ttu-id="10583-116">В некоторых выражениях строки проще сцепить с помощью интерполяции, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="10583-116">In some expressions, it is easier to concatenate strings using string interpolation, as the following code shows:</span></span>
  
[!code-csharp-interactive[building strings using string interpolation](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#3)]  
  
> [!NOTE]
>  <span data-ttu-id="10583-117">В операциях сцепки строк компилятор C# обрабатывает строки NULL так же, как пустые строки.</span><span class="sxs-lookup"><span data-stu-id="10583-117">In string concatenation operations, the C# compiler treats a null string the same as an empty string.</span></span>

<span data-ttu-id="10583-118">Другие методы сцепки строк: <xref:System.String.Concat%2A?displayProperty=nameWithType> и <xref:System.String.Format%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="10583-118">Other methods to concatenate strings are <xref:System.String.Concat%2A?displayProperty=nameWithType> and <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="10583-119">Эти методы лучше использовать при создании строки из небольшого числа строк-компонентов.</span><span class="sxs-lookup"><span data-stu-id="10583-119">These methods work well when you are building a string from a small number of component strings.</span></span> <span data-ttu-id="10583-120">Они также отлично подойдут, если вы знаете количество строк, составляющих сцепленную строку.</span><span class="sxs-lookup"><span data-stu-id="10583-120">These methdos are also a great choice when you know the number of strings that make up your concatenated string.</span></span>

<span data-ttu-id="10583-121">В других случаях вы можете сцеплять строки во время цикла и не знать, сколько исходных строк вы сцепляете. При этом фактическое число исходных строк может быть довольно большим.</span><span class="sxs-lookup"><span data-stu-id="10583-121">In other cases you may be combining strings in a loop, where you don't know how many source strings you are combining, and the actual number of source strings may be quite large.</span></span> <span data-ttu-id="10583-122">Для этих сценариев предназначен класс <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="10583-122">The <xref:System.Text.StringBuilder> class was designed for these scenarios.</span></span> <span data-ttu-id="10583-123">В следующем коде для сцепки строк используется метод <xref:System.Text.StringBuilder.Append%2A> класса <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="10583-123">The following code uses the <xref:System.Text.StringBuilder.Append%2A> method of the <xref:System.Text.StringBuilder> class to concatenate strings.</span></span>  
  
[!code-csharp-interactive[string concatenation using string builder](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#4)]  

<span data-ttu-id="10583-124">См. дополнительные сведения о [причинах для выбора сцепки строк или класса `StringBuilder`](xref:System.Text.StringBuilder#StringAndSB).</span><span class="sxs-lookup"><span data-stu-id="10583-124">You can read more about the [reasons to choose string concatenation or the `StringBuilder` class](xref:System.Text.StringBuilder#StringAndSB)</span></span>

<span data-ttu-id="10583-125">Другой вариант объединения строк из коллекции — использовать [LINQ](../programming-guide/concepts/linq/index.md) и метод <xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="10583-125">Another option to join strings from a collection is to use [LINQ](../programming-guide/concepts/linq/index.md) and the <xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="10583-126">Этот метод объединяет исходные строки с помощью лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="10583-126">This method combines the source strings using a lambda expression.</span></span> <span data-ttu-id="10583-127">Лямбда-выражение добавляет каждую строку к существующему накоплению.</span><span class="sxs-lookup"><span data-stu-id="10583-127">The lambda expression does the work to add each string to the existing accumulation.</span></span> <span data-ttu-id="10583-128">Следующий пример показывает объединение массива слов путем добавления пробелов между словами.</span><span class="sxs-lookup"><span data-stu-id="10583-128">The following example combines an array of words by adding a space between each word in the array:</span></span>

[!code-csharp-interactive[string concatenation using LINQ expressions](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#5)]  


## <a name="see-also"></a><span data-ttu-id="10583-129">См. также</span><span class="sxs-lookup"><span data-stu-id="10583-129">See Also</span></span>  
 <xref:System.String>  
 <xref:System.Text.StringBuilder>  
 [<span data-ttu-id="10583-130">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="10583-130">C# Programming Guide</span></span>](../programming-guide/index.md)  
 [<span data-ttu-id="10583-131">Строки</span><span class="sxs-lookup"><span data-stu-id="10583-131">Strings</span></span>](../programming-guide/strings/index.md)
