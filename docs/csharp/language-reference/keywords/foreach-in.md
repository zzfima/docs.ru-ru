---
title: "foreach, in (Справочник по C#)"
ms.date: 10/11/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
caps.latest.revision: "29"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d5601682d53a01ff07aba7e416aa81ded4c03e4e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="dd90e-102">foreach, in (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="dd90e-102">foreach, in (C# Reference)</span></span>
<span data-ttu-id="dd90e-103">Оператор `foreach` повторяет группу встроенных операторов для каждого элемента в массиве или коллекции объектов, которые реализуют интерфейс <xref:System.Collections.IEnumerable?displayProperty=nameWithType> или <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="dd90e-103">The `foreach` statement repeats a group of embedded statements for each element in an array or an object collection that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="dd90e-104">Оператор `foreach` используется для итерации по коллекции для получения необходимых сведений, однако его нельзя использовать для добавления или удаления элементов из исходной коллекции во избежание непредвиденных побочных эффектов.</span><span class="sxs-lookup"><span data-stu-id="dd90e-104">The `foreach` statement is used to iterate through the collection to get the information that you want, but can not be used to add or remove items from the source collection to avoid unpredictable side effects.</span></span> <span data-ttu-id="dd90e-105">Если требуется добавить или удалить элементы из исходной коллекции, используйте цикл [for](for.md).</span><span class="sxs-lookup"><span data-stu-id="dd90e-105">If you need to add or remove items from the source collection, use a [for](for.md) loop.</span></span>
  
 <span data-ttu-id="dd90e-106">Внедренные операторы продолжают выполняться для каждого элемента массива или коллекции.</span><span class="sxs-lookup"><span data-stu-id="dd90e-106">The embedded statements continue to execute for each element in the array or collection.</span></span> <span data-ttu-id="dd90e-107">После завершения итерации для всех элементов коллекции управление передается следующему оператору после блока `foreach`.</span><span class="sxs-lookup"><span data-stu-id="dd90e-107">After the iteration has been completed for all the elements in the collection, control is transferred to the next statement following the `foreach` block.</span></span>
  
 <span data-ttu-id="dd90e-108">В любой момент в блоке `foreach` вы можете прервать цикл с помощью ключевого слова [break](break.md) или перейти к следующей итерации с помощью ключевого слова [continue](continue.md).</span><span class="sxs-lookup"><span data-stu-id="dd90e-108">At any point within the `foreach` block, you can break out of the loop by using the [break](break.md) keyword, or step to the next iteration in the loop by using the [continue](continue.md) keyword.</span></span>

 <span data-ttu-id="dd90e-109">Из цикла `foreach` также можно выйти с помощью операторов [goto](goto.md), [return](return.md) или [throw](throw.md).</span><span class="sxs-lookup"><span data-stu-id="dd90e-109">A `foreach` loop can also be exited by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

 <span data-ttu-id="dd90e-110">Дополнительные сведения о ключевом слове `foreach` и примеры кода см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="dd90e-110">For more information about the `foreach` keyword and code samples, see the following topics:</span></span>  

 [<span data-ttu-id="dd90e-111">Использование оператора foreach с массивами</span><span class="sxs-lookup"><span data-stu-id="dd90e-111">Using foreach with Arrays</span></span>](../../programming-guide/arrays/using-foreach-with-arrays.md)  

 [<span data-ttu-id="dd90e-112">Практическое руководство. Доступ к классу коллекции с помощью оператора foreach</span><span class="sxs-lookup"><span data-stu-id="dd90e-112">How to: Access a Collection Class with foreach</span></span>](../../programming-guide/classes-and-structs/how-to-access-a-collection-class-with-foreach.md)  

## <a name="example"></a><span data-ttu-id="dd90e-113">Пример</span><span class="sxs-lookup"><span data-stu-id="dd90e-113">Example</span></span>
 <span data-ttu-id="dd90e-114">Ниже приведены три примера.</span><span class="sxs-lookup"><span data-stu-id="dd90e-114">The following code shows three examples.</span></span>

> [!TIP]
> <span data-ttu-id="dd90e-115">Примеры, чтобы поэкспериментировать с синтаксисом и попробуйте другой вариант использования больше похожи на вариант использования можно изменить.</span><span class="sxs-lookup"><span data-stu-id="dd90e-115">You can modify the examples to experiment with the syntax and try different usages that are more similar to your use case.</span></span> <span data-ttu-id="dd90e-116">Нажмите кнопку «Выполнить», чтобы выполнить код, а затем изменить и нажмите клавишу «запуск» еще раз.</span><span class="sxs-lookup"><span data-stu-id="dd90e-116">Press "Run" to run the code, then edit and press "Run" again.</span></span>

-   <span data-ttu-id="dd90e-117">типичный цикл `foreach`, который отображает содержимое массива целых чисел;</span><span class="sxs-lookup"><span data-stu-id="dd90e-117">a typical `foreach` loop that displays the contents of an array of integers</span></span>

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L12-L26)]

-   <span data-ttu-id="dd90e-118">цикл [for](../../../csharp/language-reference/keywords/for.md), который делает то же самое;</span><span class="sxs-lookup"><span data-stu-id="dd90e-118">a [for](../../../csharp/language-reference/keywords/for.md) loop that does the same thing</span></span>

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L31-L46)]

-   <span data-ttu-id="dd90e-119">цикл `foreach`, который ведет подсчет числа элементов в массиве.</span><span class="sxs-lookup"><span data-stu-id="dd90e-119">a `foreach` loop that maintains a count of the number of elements in the array</span></span>

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L51-L69)]
 
## <a name="c-language-specification"></a><span data-ttu-id="dd90e-120">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="dd90e-120">C# Language Specification</span></span>
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="dd90e-121">См. также</span><span class="sxs-lookup"><span data-stu-id="dd90e-121">See Also</span></span>  

[<span data-ttu-id="dd90e-122">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="dd90e-122">C# Reference</span></span>](../index.md)

[<span data-ttu-id="dd90e-123">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="dd90e-123">C# Programming Guide</span></span>](../../programming-guide/index.md)

[<span data-ttu-id="dd90e-124">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="dd90e-124">C# Keywords</span></span>](index.md)

[<span data-ttu-id="dd90e-125">Операторы итерации</span><span class="sxs-lookup"><span data-stu-id="dd90e-125">Iteration Statements</span></span>](iteration-statements.md)

[<span data-ttu-id="dd90e-126">for</span><span class="sxs-lookup"><span data-stu-id="dd90e-126">for</span></span>](for.md)
