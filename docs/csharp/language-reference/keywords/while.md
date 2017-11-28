---
title: "while (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- while_CSharpKeyword
- while
helpviewer_keywords: while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
caps.latest.revision: "22"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 420b409689d877c3e1ac744e8d7a65500cf8f964
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="while-c-reference"></a><span data-ttu-id="58788-102">while (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="58788-102">while (C# Reference)</span></span>
<span data-ttu-id="58788-103">Оператор `while` выполняет оператор или блок операторов, пока определенное выражение не примет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="58788-103">The `while` statement executes a statement or a block of statements until a specified expression evaluates to `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58788-104">Пример</span><span class="sxs-lookup"><span data-stu-id="58788-104">Example</span></span>  
 [!code-csharp[csrefKeywordsIteration#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="58788-105">Пример</span><span class="sxs-lookup"><span data-stu-id="58788-105">Example</span></span>  
 [!code-csharp[csrefKeywordsIteration#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="58788-106">Пример</span><span class="sxs-lookup"><span data-stu-id="58788-106">Example</span></span>  
 <span data-ttu-id="58788-107">Значение выражения `while` проверяется перед каждым выполнением цикла, поэтому цикл `while` выполняется ноль или несколько раз.</span><span class="sxs-lookup"><span data-stu-id="58788-107">Because the test of the `while` expression takes place before each execution of the loop, a `while` loop executes zero or more times.</span></span> <span data-ttu-id="58788-108">Это отличает его от цикла [do](../../../csharp/language-reference/keywords/do.md), который выполняется от одного до нескольких раз.</span><span class="sxs-lookup"><span data-stu-id="58788-108">This differs from the [do](../../../csharp/language-reference/keywords/do.md) loop, which executes one or more times.</span></span>  
  
 <span data-ttu-id="58788-109">Цикл `while` может быть завершен, если оператор [break](../../../csharp/language-reference/keywords/break.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) или [throw](../../../csharp/language-reference/keywords/throw.md) передает управление за пределы цикла.</span><span class="sxs-lookup"><span data-stu-id="58788-109">A `while` loop can be terminated when a [break](../../../csharp/language-reference/keywords/break.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), or [throw](../../../csharp/language-reference/keywords/throw.md) statement transfers control outside the loop.</span></span> <span data-ttu-id="58788-110">Чтобы передать управление в следующую итерацию без выхода из цикла, используйте оператор [continue](../../../csharp/language-reference/keywords/continue.md).</span><span class="sxs-lookup"><span data-stu-id="58788-110">To pass control to the next iteration without exiting the loop, use the [continue](../../../csharp/language-reference/keywords/continue.md) statement.</span></span> <span data-ttu-id="58788-111">Обратите внимание на разницу в результатах трех предыдущих примеров, которые зависят от места увеличения `int n`.</span><span class="sxs-lookup"><span data-stu-id="58788-111">Notice the difference in output in the three previous examples, depending on where `int n` is incremented.</span></span> <span data-ttu-id="58788-112">В приведенном ниже примере результат отсутствует.</span><span class="sxs-lookup"><span data-stu-id="58788-112">In the example below no output is generated.</span></span>  
  
 [!code-csharp[csrefKeywordsIteration#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_3.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="58788-113">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="58788-113">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="58788-114">См. также</span><span class="sxs-lookup"><span data-stu-id="58788-114">See Also</span></span>  
 [<span data-ttu-id="58788-115">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="58788-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="58788-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="58788-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="58788-117">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="58788-117">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="58788-118">Оператор while (C++)</span><span class="sxs-lookup"><span data-stu-id="58788-118">while Statement (C++)</span></span>](/cpp/cpp/while-statement-cpp)  
 [<span data-ttu-id="58788-119">Операторы итерации</span><span class="sxs-lookup"><span data-stu-id="58788-119">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)
