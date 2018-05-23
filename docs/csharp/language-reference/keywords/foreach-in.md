---
title: foreach, in (Справочник по C#)
ms.date: 10/11/2017
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: f00ae873e615f653d3e760f82b157a57fdaef6ed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="2e4fb-102">foreach, in (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="2e4fb-102">foreach, in (C# Reference)</span></span>
<span data-ttu-id="2e4fb-103">Оператор `foreach` повторяет группу встроенных операторов для каждого элемента в массиве или коллекции объектов, которые реализуют интерфейс <xref:System.Collections.IEnumerable?displayProperty=nameWithType> или <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2e4fb-103">The `foreach` statement repeats a group of embedded statements for each element in an array or an object collection that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="2e4fb-104">Оператор `foreach` используется для итерации по коллекции для получения необходимых сведений, однако его нельзя использовать для добавления или удаления элементов из исходной коллекции во избежание непредвиденных побочных эффектов.</span><span class="sxs-lookup"><span data-stu-id="2e4fb-104">The `foreach` statement is used to iterate through the collection to get the information that you want, but can not be used to add or remove items from the source collection to avoid unpredictable side effects.</span></span> <span data-ttu-id="2e4fb-105">Если требуется добавить или удалить элементы из исходной коллекции, используйте цикл [for](for.md).</span><span class="sxs-lookup"><span data-stu-id="2e4fb-105">If you need to add or remove items from the source collection, use a [for](for.md) loop.</span></span>
  
 <span data-ttu-id="2e4fb-106">Внедренные операторы продолжают выполняться для каждого элемента массива или коллекции.</span><span class="sxs-lookup"><span data-stu-id="2e4fb-106">The embedded statements continue to execute for each element in the array or collection.</span></span> <span data-ttu-id="2e4fb-107">После завершения итерации для всех элементов коллекции управление передается следующему оператору после блока `foreach`.</span><span class="sxs-lookup"><span data-stu-id="2e4fb-107">After the iteration has been completed for all the elements in the collection, control is transferred to the next statement following the `foreach` block.</span></span>
  
 <span data-ttu-id="2e4fb-108">В любой момент в блоке `foreach` вы можете прервать цикл с помощью ключевого слова [break](break.md) или перейти к следующей итерации с помощью ключевого слова [continue](continue.md).</span><span class="sxs-lookup"><span data-stu-id="2e4fb-108">At any point within the `foreach` block, you can break out of the loop by using the [break](break.md) keyword, or step to the next iteration in the loop by using the [continue](continue.md) keyword.</span></span>

 <span data-ttu-id="2e4fb-109">Из цикла `foreach` также можно выйти с помощью операторов [goto](goto.md), [return](return.md) или [throw](throw.md).</span><span class="sxs-lookup"><span data-stu-id="2e4fb-109">A `foreach` loop can also be exited by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

 <span data-ttu-id="2e4fb-110">Дополнительные сведения о ключевом слове `foreach` и примеры кода см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="2e4fb-110">For more information about the `foreach` keyword and code samples, see the following topics:</span></span>  

 [<span data-ttu-id="2e4fb-111">Использование оператора foreach с массивами</span><span class="sxs-lookup"><span data-stu-id="2e4fb-111">Using foreach with Arrays</span></span>](../../programming-guide/arrays/using-foreach-with-arrays.md)  

 [<span data-ttu-id="2e4fb-112">Практическое руководство. Доступ к классу коллекции с помощью оператора foreach</span><span class="sxs-lookup"><span data-stu-id="2e4fb-112">How to: Access a Collection Class with foreach</span></span>](../../programming-guide/classes-and-structs/how-to-access-a-collection-class-with-foreach.md)  

## <a name="example"></a><span data-ttu-id="2e4fb-113">Пример</span><span class="sxs-lookup"><span data-stu-id="2e4fb-113">Example</span></span>
 <span data-ttu-id="2e4fb-114">В коде ниже приведено три примера.</span><span class="sxs-lookup"><span data-stu-id="2e4fb-114">The following code shows three examples.</span></span>

> [!TIP]
> <span data-ttu-id="2e4fb-115">Вы можете менять примеры, чтобы поэкспериментировать с синтаксисом и попробовать другие варианты использования, более похожие на ваш.</span><span class="sxs-lookup"><span data-stu-id="2e4fb-115">You can modify the examples to experiment with the syntax and try different usages that are more similar to your use case.</span></span> <span data-ttu-id="2e4fb-116">Нажмите кнопку Run, чтобы выполнить код, а затем внесите изменения и нажмите кнопку еще раз.</span><span class="sxs-lookup"><span data-stu-id="2e4fb-116">Press "Run" to run the code, then edit and press "Run" again.</span></span>

-   <span data-ttu-id="2e4fb-117">типичный цикл `foreach`, который отображает содержимое массива целых чисел;</span><span class="sxs-lookup"><span data-stu-id="2e4fb-117">a typical `foreach` loop that displays the contents of an array of integers</span></span>

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L12-L26)]

-   <span data-ttu-id="2e4fb-118">цикл [for](../../../csharp/language-reference/keywords/for.md), который делает то же самое;</span><span class="sxs-lookup"><span data-stu-id="2e4fb-118">a [for](../../../csharp/language-reference/keywords/for.md) loop that does the same thing</span></span>

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L31-L46)]

-   <span data-ttu-id="2e4fb-119">цикл `foreach`, который ведет подсчет числа элементов в массиве.</span><span class="sxs-lookup"><span data-stu-id="2e4fb-119">a `foreach` loop that maintains a count of the number of elements in the array</span></span>

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L51-L69)]
 
## <a name="c-language-specification"></a><span data-ttu-id="2e4fb-120">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="2e4fb-120">C# Language Specification</span></span>
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="2e4fb-121">См. также</span><span class="sxs-lookup"><span data-stu-id="2e4fb-121">See Also</span></span>  

[<span data-ttu-id="2e4fb-122">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="2e4fb-122">C# Reference</span></span>](../index.md)

[<span data-ttu-id="2e4fb-123">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="2e4fb-123">C# Programming Guide</span></span>](../../programming-guide/index.md)

[<span data-ttu-id="2e4fb-124">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="2e4fb-124">C# Keywords</span></span>](index.md)

[<span data-ttu-id="2e4fb-125">Операторы итерации</span><span class="sxs-lookup"><span data-stu-id="2e4fb-125">Iteration Statements</span></span>](iteration-statements.md)

[<span data-ttu-id="2e4fb-126">for</span><span class="sxs-lookup"><span data-stu-id="2e4fb-126">for</span></span>](for.md)
