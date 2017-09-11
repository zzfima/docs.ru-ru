---
title: "while (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- while_CSharpKeyword
- while
dev_langs:
- CSharp
helpviewer_keywords:
- while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
caps.latest.revision: 22
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
ms.openlocfilehash: ed531c83dba02b38576bf8354b1ff92f075048bc
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="while-c-reference"></a><span data-ttu-id="ae217-102">while (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="ae217-102">while (C# Reference)</span></span>
<span data-ttu-id="ae217-103">Оператор `while` выполняет оператор или блок операторов, пока определенное выражение не примет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="ae217-103">The `while` statement executes a statement or a block of statements until a specified expression evaluates to `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae217-104">Пример</span><span class="sxs-lookup"><span data-stu-id="ae217-104">Example</span></span>  
 <span data-ttu-id="ae217-105">[!code-cs[csrefKeywordsIteration#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="ae217-105">[!code-cs[csrefKeywordsIteration#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae217-106">Пример</span><span class="sxs-lookup"><span data-stu-id="ae217-106">Example</span></span>  
 <span data-ttu-id="ae217-107">[!code-cs[csrefKeywordsIteration#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="ae217-107">[!code-cs[csrefKeywordsIteration#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae217-108">Пример</span><span class="sxs-lookup"><span data-stu-id="ae217-108">Example</span></span>  
 <span data-ttu-id="ae217-109">Значение выражения `while` проверяется перед каждым выполнением цикла, поэтому цикл `while` выполняется ноль или несколько раз.</span><span class="sxs-lookup"><span data-stu-id="ae217-109">Because the test of the `while` expression takes place before each execution of the loop, a `while` loop executes zero or more times.</span></span> <span data-ttu-id="ae217-110">Это отличает его от цикла [do](../../../csharp/language-reference/keywords/do.md), который выполняется от одного до нескольких раз.</span><span class="sxs-lookup"><span data-stu-id="ae217-110">This differs from the [do](../../../csharp/language-reference/keywords/do.md) loop, which executes one or more times.</span></span>  
  
 <span data-ttu-id="ae217-111">Цикл `while` может быть завершен, если оператор [break](../../../csharp/language-reference/keywords/break.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) или [throw](../../../csharp/language-reference/keywords/throw.md) передает управление за пределы цикла.</span><span class="sxs-lookup"><span data-stu-id="ae217-111">A `while` loop can be terminated when a [break](../../../csharp/language-reference/keywords/break.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), or [throw](../../../csharp/language-reference/keywords/throw.md) statement transfers control outside the loop.</span></span> <span data-ttu-id="ae217-112">Чтобы передать управление в следующую итерацию без выхода из цикла, используйте оператор [continue](../../../csharp/language-reference/keywords/continue.md).</span><span class="sxs-lookup"><span data-stu-id="ae217-112">To pass control to the next iteration without exiting the loop, use the [continue](../../../csharp/language-reference/keywords/continue.md) statement.</span></span> <span data-ttu-id="ae217-113">Обратите внимание на разницу в результатах трех предыдущих примеров, которые зависят от места увеличения `int n`.</span><span class="sxs-lookup"><span data-stu-id="ae217-113">Notice the difference in output in the three previous examples, depending on where `int n` is incremented.</span></span> <span data-ttu-id="ae217-114">В приведенном ниже примере результат отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ae217-114">In the example below no output is generated.</span></span>  
  
 <span data-ttu-id="ae217-115">[!code-cs[csrefKeywordsIteration#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="ae217-115">[!code-cs[csrefKeywordsIteration#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_3.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="ae217-116">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="ae217-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ae217-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ae217-117">See Also</span></span>  
 <span data-ttu-id="ae217-118">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="ae217-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="ae217-119">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="ae217-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="ae217-120">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="ae217-120">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="ae217-121">[Оператор while (C++)](/cpp/cpp/while-statement-cpp) </span><span class="sxs-lookup"><span data-stu-id="ae217-121">[while Statement (C++)](/cpp/cpp/while-statement-cpp) </span></span>  
 [<span data-ttu-id="ae217-122">Операторы итерации</span><span class="sxs-lookup"><span data-stu-id="ae217-122">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)

