---
title: Практическое руководство. Сцепка нескольких строк (руководство по C#)
description: C# поддерживает различные способы сцепки строк. Узнайте, какие доступны варианты и как выбирать между ними.
ms.date: 02/20/2018
helpviewer_keywords:
- joining strings [C#]
- concatenating strings [C#]
- strings [C#], concatenation
ms.assetid: 8e16736f-4096-4f3f-be0f-9d4c3ff63520
ms.openlocfilehash: 9a0640a7ce73fa8454442cd301157bf5c265f9de
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713901"
---
# <a name="how-to-concatenate-multiple-strings-c-guide"></a><span data-ttu-id="fb2d5-104">Практическое руководство. Сцепка нескольких строк (руководство по C#)</span><span class="sxs-lookup"><span data-stu-id="fb2d5-104">How to concatenate multiple strings (C# Guide)</span></span>

<span data-ttu-id="fb2d5-105">*Объединение* подразумевает добавление одной строки к концу другой.</span><span class="sxs-lookup"><span data-stu-id="fb2d5-105">*Concatenation* is the process of appending one string to the end of another string.</span></span> <span data-ttu-id="fb2d5-106">Вы можете сцеплять строки с помощью оператора `+`.</span><span class="sxs-lookup"><span data-stu-id="fb2d5-106">You concatenate strings by using the `+` operator.</span></span> <span data-ttu-id="fb2d5-107">Строковые литералы и константы сцепляются во время компиляции, а не во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="fb2d5-107">For string literals and string constants, concatenation occurs at compile time; no run-time concatenation occurs.</span></span> <span data-ttu-id="fb2d5-108">Строковые переменные сцепляются только во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="fb2d5-108">For string variables, concatenation occurs only at run time.</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="fb2d5-109">Следующий пример показывает использование сцепки для разделения длинного строкового литерала на строки меньшего размера, чтобы повысить удобочитаемость исходного кода.</span><span class="sxs-lookup"><span data-stu-id="fb2d5-109">The following example uses concatenation to split a long string literal into smaller strings in order to improve readability in the source code.</span></span> <span data-ttu-id="fb2d5-110">Эти части объединяются в одну строку во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="fb2d5-110">These parts are concatenated into a single string at compile time.</span></span> <span data-ttu-id="fb2d5-111">Количество строк не влияет на производительность во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="fb2d5-111">There is no run-time performance cost regardless of the number of strings involved.</span></span>  
  
 [!code-csharp-interactive[Combining strings at compile time](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#1)]  

<span data-ttu-id="fb2d5-112">Для сцепки строковых переменных вы можете использовать операторы `+` или `+=`, [интерполяцию строк](../language-reference/tokens/interpolated.md), а также методы <xref:System.String.Format%2A?displayProperty=nameWithType>, <xref:System.String.Concat%2A?displayProperty=nameWithType>, <xref:System.String.Join%2A?displayProperty=nameWithType> или <xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fb2d5-112">To concatenate string variables, you can use the `+` or `+=` operators, [string interpolation](../language-reference/tokens/interpolated.md) or the <xref:System.String.Format%2A?displayProperty=nameWithType>, <xref:System.String.Concat%2A?displayProperty=nameWithType>, <xref:System.String.Join%2A?displayProperty=nameWithType> or <xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="fb2d5-113">Оператор `+` прост в использовании и позволяет получить интуитивно понятный код.</span><span class="sxs-lookup"><span data-stu-id="fb2d5-113">The `+` operator is easy to use and makes for intuitive code.</span></span> <span data-ttu-id="fb2d5-114">Даже если в одном выражении используется несколько операторов `+`, содержимое строки копируется только один раз.</span><span class="sxs-lookup"><span data-stu-id="fb2d5-114">Even if you use several `+` operators in one statement, the string content is copied only once.</span></span> <span data-ttu-id="fb2d5-115">В следующем коде показаны примеры использования операторов `+` и `+=` для сцепки строк:</span><span class="sxs-lookup"><span data-stu-id="fb2d5-115">The following code shows examples of using the `+` and `+=` operators to concatenate strings:</span></span>

[!code-csharp-interactive[combining strings using +](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#2)]  

<span data-ttu-id="fb2d5-116">В некоторых выражениях строки проще сцепить с помощью интерполяции, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="fb2d5-116">In some expressions, it's easier to concatenate strings using string interpolation, as the following code shows:</span></span>
  
[!code-csharp-interactive[building strings using string interpolation](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#3)]  
  
> [!NOTE]
> <span data-ttu-id="fb2d5-117">В операциях сцепки строк компилятор C# обрабатывает строки NULL так же, как пустые строки.</span><span class="sxs-lookup"><span data-stu-id="fb2d5-117">In string concatenation operations, the C# compiler treats a null string the same as an empty string.</span></span>

<span data-ttu-id="fb2d5-118">Другие методы сцепки строк: <xref:System.String.Format%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fb2d5-118">Other method to concatenate strings is <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="fb2d5-119">Этот метод лучше использовать при создании строки из небольшого числа строк-компонентов.</span><span class="sxs-lookup"><span data-stu-id="fb2d5-119">This method works well when you are building a string from a small number of component strings.</span></span>

<span data-ttu-id="fb2d5-120">В других случаях вы можете сцеплять строки во время цикла и не знать, сколько исходных строк вы сцепляете. При этом фактическое число исходных строк может быть довольно большим.</span><span class="sxs-lookup"><span data-stu-id="fb2d5-120">In other cases you may be combining strings in a loop, where you don't know how many source strings you are combining, and the actual number of source strings may be quite large.</span></span> <span data-ttu-id="fb2d5-121">Для этих сценариев предназначен класс <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="fb2d5-121">The <xref:System.Text.StringBuilder> class was designed for these scenarios.</span></span> <span data-ttu-id="fb2d5-122">В следующем коде для сцепки строк используется метод <xref:System.Text.StringBuilder.Append%2A> класса <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="fb2d5-122">The following code uses the <xref:System.Text.StringBuilder.Append%2A> method of the <xref:System.Text.StringBuilder> class to concatenate strings.</span></span>  
  
[!code-csharp-interactive[string concatenation using string builder](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#4)]  

<span data-ttu-id="fb2d5-123">См. дополнительные сведения о [причинах для выбора объединения строк или класса `StringBuilder` ](xref:System.Text.StringBuilder#StringAndSB).</span><span class="sxs-lookup"><span data-stu-id="fb2d5-123">You can read more about the [reasons to choose string concatenation or the `StringBuilder` class](xref:System.Text.StringBuilder#StringAndSB).</span></span>

<span data-ttu-id="fb2d5-124">Другой вариант объединения строк из коллекции — использовать метод <xref:System.String.Concat%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fb2d5-124">Another option to join strings from a collection is to use <xref:System.String.Concat%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="fb2d5-125">Используйте метод <xref:System.String.Join%2A?displayProperty=nameWithType>, если исходные строки должны быть разделены разделителем.</span><span class="sxs-lookup"><span data-stu-id="fb2d5-125">Use <xref:System.String.Join%2A?displayProperty=nameWithType> method if source strings should be separated by a delimeter.</span></span> <span data-ttu-id="fb2d5-126">Следующий код объединяет массив слов с помощью обоих методов:</span><span class="sxs-lookup"><span data-stu-id="fb2d5-126">The following code combines an array of words using both methods:</span></span>

[!code-csharp-interactive[concatenation of string collection](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#5)]

<span data-ttu-id="fb2d5-127">Другой вариант объединения строк из коллекции — использовать [LINQ](../programming-guide/concepts/linq/index.md) и метод <xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fb2d5-127">At last, you can use [LINQ](../programming-guide/concepts/linq/index.md) and the <xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType> method to join strings from a collection.</span></span> <span data-ttu-id="fb2d5-128">Этот метод объединяет исходные строки с помощью лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="fb2d5-128">This method combines the source strings using a lambda expression.</span></span> <span data-ttu-id="fb2d5-129">Лямбда-выражение добавляет каждую строку к существующему накоплению.</span><span class="sxs-lookup"><span data-stu-id="fb2d5-129">The lambda expression does the work to add each string to the existing accumulation.</span></span> <span data-ttu-id="fb2d5-130">Следующий пример показывает объединение массива слов путем добавления пробелов между словами.</span><span class="sxs-lookup"><span data-stu-id="fb2d5-130">The following example combines an array of words by adding a space between each word in the array:</span></span>

[!code-csharp-interactive[string concatenation using LINQ expressions](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#6)]  

<span data-ttu-id="fb2d5-131">Вы можете оценить эти примеры, просмотрев код в нашем [репозитории GitHub](https://github.com/dotnet/samples/tree/master/snippets/csharp/how-to/strings).</span><span class="sxs-lookup"><span data-stu-id="fb2d5-131">You can try these samples by looking at the code in our [GitHub repository](https://github.com/dotnet/samples/tree/master/snippets/csharp/how-to/strings).</span></span> <span data-ttu-id="fb2d5-132">Или можете загрузить образцы [в ZIP-файле](https://github.com/dotnet/samples/raw/master/snippets/csharp/how-to/strings.zip).</span><span class="sxs-lookup"><span data-stu-id="fb2d5-132">Or you can download the samples [as a zip file](https://github.com/dotnet/samples/raw/master/snippets/csharp/how-to/strings.zip).</span></span>

## <a name="see-also"></a><span data-ttu-id="fb2d5-133">См. также</span><span class="sxs-lookup"><span data-stu-id="fb2d5-133">See also</span></span>

- <xref:System.String>
- <xref:System.Text.StringBuilder>
- [<span data-ttu-id="fb2d5-134">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="fb2d5-134">C# Programming Guide</span></span>](../programming-guide/index.md)
- [<span data-ttu-id="fb2d5-135">Строки</span><span class="sxs-lookup"><span data-stu-id="fb2d5-135">Strings</span></span>](../programming-guide/strings/index.md)
