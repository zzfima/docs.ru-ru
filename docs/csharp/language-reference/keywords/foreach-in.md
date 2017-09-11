---
title: "foreach, in (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- foreach
- foreach_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
caps.latest.revision: 29
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
ms.openlocfilehash: aed1d4f086f0b1334df750fd912d20d66326a043
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="9d68a-102">foreach, in (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="9d68a-102">foreach, in (C# Reference)</span></span>
<span data-ttu-id="9d68a-103">Оператор `foreach` повторяет группу встроенных операторов для каждого элемента в массиве или коллекции объектов, которые реализуют интерфейс <xref:System.Collections.IEnumerable?displayProperty=fullName> или <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="9d68a-103">The `foreach` statement repeats a group of embedded statements for each element in an array or an object collection that implements the <xref:System.Collections.IEnumerable?displayProperty=fullName> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> interface.</span></span> <span data-ttu-id="9d68a-104">Оператор `foreach` используется для итерации по коллекции для получения необходимых сведений, однако его нельзя использовать для добавления или удаления элементов из исходной коллекции во избежание непредвиденных побочных эффектов.</span><span class="sxs-lookup"><span data-stu-id="9d68a-104">The `foreach` statement is used to iterate through the collection to get the information that you want, but can not be used to add or remove items from the source collection to avoid unpredictable side effects.</span></span> <span data-ttu-id="9d68a-105">Если требуется добавить или удалить элементы из исходной коллекции, используйте цикл [for](../../../csharp/language-reference/keywords/for.md).</span><span class="sxs-lookup"><span data-stu-id="9d68a-105">If you need to add or remove items from the source collection, use a [for](../../../csharp/language-reference/keywords/for.md) loop.</span></span>  
  
 <span data-ttu-id="9d68a-106">Внедренные операторы продолжают выполняться для каждого элемента массива или коллекции.</span><span class="sxs-lookup"><span data-stu-id="9d68a-106">The embedded statements continue to execute for each element in the array or collection.</span></span> <span data-ttu-id="9d68a-107">После завершения итерации для всех элементов коллекции управление передается следующему оператору после блока `foreach`.</span><span class="sxs-lookup"><span data-stu-id="9d68a-107">After the iteration has been completed for all the elements in the collection, control is transferred to the next statement following the `foreach` block.</span></span>  
  
 <span data-ttu-id="9d68a-108">В любой момент в блоке `foreach` вы можете прервать цикл с помощью ключевого слова [break](../../../csharp/language-reference/keywords/break.md) или перейти к следующей итерации с помощью ключевого слова [continue](../../../csharp/language-reference/keywords/continue.md).</span><span class="sxs-lookup"><span data-stu-id="9d68a-108">At any point within the `foreach` block, you can break out of the loop by using the [break](../../../csharp/language-reference/keywords/break.md) keyword, or step to the next iteration in the loop by using the [continue](../../../csharp/language-reference/keywords/continue.md) keyword.</span></span>  
  
 <span data-ttu-id="9d68a-109">Из цикла `foreach` также можно выйти с помощью операторов [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) или [throw](../../../csharp/language-reference/keywords/throw.md).</span><span class="sxs-lookup"><span data-stu-id="9d68a-109">A `foreach` loop can also be exited by the [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), or [throw](../../../csharp/language-reference/keywords/throw.md) statements.</span></span>  
  
 <span data-ttu-id="9d68a-110">Дополнительные сведения о ключевом слове `foreach` и примеры кода см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="9d68a-110">For more information about the `foreach` keyword and code samples, see the following topics:</span></span>  
  
 [<span data-ttu-id="9d68a-111">Использование оператора foreach с массивами</span><span class="sxs-lookup"><span data-stu-id="9d68a-111">Using foreach with Arrays</span></span>](../../../csharp/programming-guide/arrays/using-foreach-with-arrays.md)  
  
 [<span data-ttu-id="9d68a-112">Практическое руководство. Доступ к классу коллекции с помощью оператора foreach</span><span class="sxs-lookup"><span data-stu-id="9d68a-112">How to: Access a Collection Class with foreach</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-access-a-collection-class-with-foreach.md)  
  
## <a name="example"></a><span data-ttu-id="9d68a-113">Пример</span><span class="sxs-lookup"><span data-stu-id="9d68a-113">Example</span></span>  
 <span data-ttu-id="9d68a-114">В коде ниже приведено три примера:</span><span class="sxs-lookup"><span data-stu-id="9d68a-114">The following code shows three examples:</span></span>  
  
-   <span data-ttu-id="9d68a-115">типичный цикл `foreach`, который отображает содержимое массива целых чисел;</span><span class="sxs-lookup"><span data-stu-id="9d68a-115">a typical `foreach` loop that displays the contents of an array of integers</span></span>  
  
-   <span data-ttu-id="9d68a-116">цикл [for](../../../csharp/language-reference/keywords/for.md), который делает то же самое;</span><span class="sxs-lookup"><span data-stu-id="9d68a-116">a [for](../../../csharp/language-reference/keywords/for.md) loop that does the same thing</span></span>  
  
-   <span data-ttu-id="9d68a-117">цикл `foreach`, который ведет подсчет числа элементов в массиве.</span><span class="sxs-lookup"><span data-stu-id="9d68a-117">a `foreach` loop that maintains a count of the number of elements in the array</span></span>  
  
 <span data-ttu-id="9d68a-118">[!code-cs[csrefKeywordsIteration#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/foreach-in_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="9d68a-118">[!code-cs[csrefKeywordsIteration#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/foreach-in_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="9d68a-119">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="9d68a-119">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9d68a-120">См. также</span><span class="sxs-lookup"><span data-stu-id="9d68a-120">See Also</span></span>  
 <span data-ttu-id="9d68a-121">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="9d68a-121">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="9d68a-122">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9d68a-122">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="9d68a-123">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="9d68a-123">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="9d68a-124">[Операторы итерации](../../../csharp/language-reference/keywords/iteration-statements.md) </span><span class="sxs-lookup"><span data-stu-id="9d68a-124">[Iteration Statements](../../../csharp/language-reference/keywords/iteration-statements.md) </span></span>  
 [<span data-ttu-id="9d68a-125">for</span><span class="sxs-lookup"><span data-stu-id="9d68a-125">for</span></span>](../../../csharp/language-reference/keywords/for.md)

