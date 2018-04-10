---
title: continue (Справочник по C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- continue_CSharpKeyword
- continue
helpviewer_keywords:
- continue keyword [C#]
ms.assetid: 8a5ac96f-f98a-4519-b32d-345847ed7be0
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1ace2c90d03593b51b9ea461a47e122c5da1ab81
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="continue-c-reference"></a><span data-ttu-id="393b7-102">continue (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="393b7-102">continue (C# Reference)</span></span>
<span data-ttu-id="393b7-103">Оператор `continue` передает управление следующей итерации вложенного оператора [while](../../../csharp/language-reference/keywords/while.md), [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md) или [foreach](../../../csharp/language-reference/keywords/foreach-in.md), в котором она встречается.</span><span class="sxs-lookup"><span data-stu-id="393b7-103">The `continue` statement passes control to the next iteration of the enclosing [while](../../../csharp/language-reference/keywords/while.md), [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md), or [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement in which it appears.</span></span>  
  
## <a name="example"></a><span data-ttu-id="393b7-104">Пример</span><span class="sxs-lookup"><span data-stu-id="393b7-104">Example</span></span>  
 <span data-ttu-id="393b7-105">В этом примере инициализируется счетчик, выполняющий отсчет от 1 до 10.</span><span class="sxs-lookup"><span data-stu-id="393b7-105">In this example, a counter is initialized to count from 1 to 10.</span></span> <span data-ttu-id="393b7-106">Благодаря использованию оператора `continue` в сочетании с выражением `(i < 9)` операторы между `continue` и концом текста `for` пропускаются.</span><span class="sxs-lookup"><span data-stu-id="393b7-106">By using the `continue` statement in conjunction with the expression `(i < 9)`, the statements between `continue` and the end of the `for` body are skipped.</span></span>  
  
 [!code-csharp[csrefKeywordsJump#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/continue_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="393b7-107">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="393b7-107">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="393b7-108">См. также</span><span class="sxs-lookup"><span data-stu-id="393b7-108">See Also</span></span>  
 [<span data-ttu-id="393b7-109">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="393b7-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="393b7-110">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="393b7-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="393b7-111">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="393b7-111">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="393b7-112">Оператор break</span><span class="sxs-lookup"><span data-stu-id="393b7-112">break Statement</span></span>](/cpp/cpp/break-statement-cpp)  
 [<span data-ttu-id="393b7-113">Операторы перехода</span><span class="sxs-lookup"><span data-stu-id="393b7-113">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)
