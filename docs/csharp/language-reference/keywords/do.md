---
title: "do (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- do_CSharpKeyword
- do
dev_langs:
- CSharp
helpviewer_keywords:
- do keyword [C#]
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
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
ms.openlocfilehash: 58a9361c440bc1b17c5ab929ff7b45ba71ce50a4
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="do-c-reference"></a><span data-ttu-id="f3d11-102">do (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="f3d11-102">do (C# Reference)</span></span>
<span data-ttu-id="f3d11-103">Оператор `do` выполняет оператор или блок операторов, пока определенное выражение не примет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="f3d11-103">The `do` statement executes a statement or a block of statements repeatedly until a specified expression evaluates to `false`.</span></span> <span data-ttu-id="f3d11-104">Тело цикла должно быть заключено в фигурные скобки `{}`, если оно не состоит из одного оператора.</span><span class="sxs-lookup"><span data-stu-id="f3d11-104">The body of the loop must be enclosed in braces, `{}`, unless it consists of a single statement.</span></span> <span data-ttu-id="f3d11-105">В этом случае фигурные скобки необязательны.</span><span class="sxs-lookup"><span data-stu-id="f3d11-105">In that case, the braces are optional.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3d11-106">Пример</span><span class="sxs-lookup"><span data-stu-id="f3d11-106">Example</span></span>  
 <span data-ttu-id="f3d11-107">В следующем примере операторы цикла `do-while` выполняются до тех пор, пока значение переменной `x` остается меньше 5.</span><span class="sxs-lookup"><span data-stu-id="f3d11-107">In the following example, the `do-while` loop statements execute as long as the variable `x` is less than 5.</span></span>  
  
 <span data-ttu-id="f3d11-108">[!code-cs[csrefKeywordsIteration#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/do_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f3d11-108">[!code-cs[csrefKeywordsIteration#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/do_1.cs)]</span></span>  
  
 <span data-ttu-id="f3d11-109">В отличие от оператора [while](../../../csharp/language-reference/keywords/while.md), цикл `do-while` выполняется один раз до вычисления значения условного выражения.</span><span class="sxs-lookup"><span data-stu-id="f3d11-109">Unlike the [while](../../../csharp/language-reference/keywords/while.md) statement, a `do-while` loop is executed one time before the conditional expression is evaluated.</span></span>  
  
 <span data-ttu-id="f3d11-110">В любой точке блока `do-while` можно разорвать цикл с помощью оператора [break](../../../csharp/language-reference/keywords/break.md).</span><span class="sxs-lookup"><span data-stu-id="f3d11-110">At any point in the `do-while` block, you can break out of the loop using the [break](../../../csharp/language-reference/keywords/break.md) statement.</span></span> <span data-ttu-id="f3d11-111">Можно перейти непосредственно к оператору оценки выражения `while`, воспользовавшись оператором [continue](../../../csharp/language-reference/keywords/continue.md).</span><span class="sxs-lookup"><span data-stu-id="f3d11-111">You can step directly to the `while` expression evaluation statement by using the [continue](../../../csharp/language-reference/keywords/continue.md) statement.</span></span> <span data-ttu-id="f3d11-112">Если выражение `while` принимает значение true, выполнение продолжается с первого оператора цикла.</span><span class="sxs-lookup"><span data-stu-id="f3d11-112">If the `while` expression evaluates to true, execution continues at the first statement in the loop.</span></span> <span data-ttu-id="f3d11-113">Если выражение принимает значение false, выполнение продолжается в первом операторе после цикла `do-while`.</span><span class="sxs-lookup"><span data-stu-id="f3d11-113">If the expression evaluates to false, execution continues at the first statement after the `do-while` loop.</span></span>  
  
 <span data-ttu-id="f3d11-114">Из цикла `do-while` также можно выйти с помощью операторов [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) или [throw](../../../csharp/language-reference/keywords/throw.md).</span><span class="sxs-lookup"><span data-stu-id="f3d11-114">A `do-while` loop can also be exited by the [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), or [throw](../../../csharp/language-reference/keywords/throw.md) statements.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="f3d11-115">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="f3d11-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f3d11-116">См. также</span><span class="sxs-lookup"><span data-stu-id="f3d11-116">See Also</span></span>  
 <span data-ttu-id="f3d11-117">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="f3d11-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="f3d11-118">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f3d11-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="f3d11-119">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="f3d11-119">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="f3d11-120">[Оператор do-while (C++)](/cpp/cpp/do-while-statement-cpp) </span><span class="sxs-lookup"><span data-stu-id="f3d11-120">[do-while Statement (C++)](/cpp/cpp/do-while-statement-cpp) </span></span>  
 [<span data-ttu-id="f3d11-121">Операторы итерации</span><span class="sxs-lookup"><span data-stu-id="f3d11-121">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)

