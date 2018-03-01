---
title: "do (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- do_CSharpKeyword
- do
helpviewer_keywords:
- do keyword [C#]
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d24078d3fb985f643fb66aa456900d03d2ff3fce
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="do-c-reference"></a><span data-ttu-id="939ff-102">do (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="939ff-102">do (C# Reference)</span></span>
<span data-ttu-id="939ff-103">Оператор `do` выполняет оператор или блок операторов, пока определенное выражение не примет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="939ff-103">The `do` statement executes a statement or a block of statements repeatedly until a specified expression evaluates to `false`.</span></span> <span data-ttu-id="939ff-104">Тело цикла должно быть заключено в фигурные скобки `{}`, если оно не состоит из одного оператора.</span><span class="sxs-lookup"><span data-stu-id="939ff-104">The body of the loop must be enclosed in braces, `{}`, unless it consists of a single statement.</span></span> <span data-ttu-id="939ff-105">В этом случае фигурные скобки необязательны.</span><span class="sxs-lookup"><span data-stu-id="939ff-105">In that case, the braces are optional.</span></span>  
  
## <a name="example"></a><span data-ttu-id="939ff-106">Пример</span><span class="sxs-lookup"><span data-stu-id="939ff-106">Example</span></span>  
 <span data-ttu-id="939ff-107">В следующем примере операторы цикла `do-while` выполняются до тех пор, пока значение переменной `x` остается меньше 5.</span><span class="sxs-lookup"><span data-stu-id="939ff-107">In the following example, the `do-while` loop statements execute as long as the variable `x` is less than 5.</span></span>  
  
 [!code-csharp[csrefKeywordsIteration#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/do_1.cs)]  
  
 <span data-ttu-id="939ff-108">В отличие от оператора [while](../../../csharp/language-reference/keywords/while.md), цикл `do-while` выполняется один раз до вычисления значения условного выражения.</span><span class="sxs-lookup"><span data-stu-id="939ff-108">Unlike the [while](../../../csharp/language-reference/keywords/while.md) statement, a `do-while` loop is executed one time before the conditional expression is evaluated.</span></span>  
  
 <span data-ttu-id="939ff-109">В любой точке блока `do-while` можно разорвать цикл с помощью оператора [break](../../../csharp/language-reference/keywords/break.md).</span><span class="sxs-lookup"><span data-stu-id="939ff-109">At any point in the `do-while` block, you can break out of the loop using the [break](../../../csharp/language-reference/keywords/break.md) statement.</span></span> <span data-ttu-id="939ff-110">Можно перейти непосредственно к оператору оценки выражения `while`, воспользовавшись оператором [continue](../../../csharp/language-reference/keywords/continue.md).</span><span class="sxs-lookup"><span data-stu-id="939ff-110">You can step directly to the `while` expression evaluation statement by using the [continue](../../../csharp/language-reference/keywords/continue.md) statement.</span></span> <span data-ttu-id="939ff-111">Если выражение `while` принимает значение true, выполнение продолжается с первого оператора цикла.</span><span class="sxs-lookup"><span data-stu-id="939ff-111">If the `while` expression evaluates to true, execution continues at the first statement in the loop.</span></span> <span data-ttu-id="939ff-112">Если выражение принимает значение false, выполнение продолжается в первом операторе после цикла `do-while`.</span><span class="sxs-lookup"><span data-stu-id="939ff-112">If the expression evaluates to false, execution continues at the first statement after the `do-while` loop.</span></span>  
  
 <span data-ttu-id="939ff-113">Из цикла `do-while` также можно выйти с помощью операторов [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) или [throw](../../../csharp/language-reference/keywords/throw.md).</span><span class="sxs-lookup"><span data-stu-id="939ff-113">A `do-while` loop can also be exited by the [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), or [throw](../../../csharp/language-reference/keywords/throw.md) statements.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="939ff-114">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="939ff-114">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="939ff-115">См. также</span><span class="sxs-lookup"><span data-stu-id="939ff-115">See Also</span></span>  
 [<span data-ttu-id="939ff-116">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="939ff-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="939ff-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="939ff-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="939ff-118">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="939ff-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="939ff-119">Оператор do-while (C)</span><span class="sxs-lookup"><span data-stu-id="939ff-119">do-while Statement (C++)</span></span>](/cpp/cpp/do-while-statement-cpp)  
 [<span data-ttu-id="939ff-120">Операторы итерации</span><span class="sxs-lookup"><span data-stu-id="939ff-120">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)
