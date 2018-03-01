---
title: "goto (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- goto_CSharpKeyword
- goto
helpviewer_keywords:
- goto keyword [C#]
ms.assetid: 2c03c9c1-8119-44ef-b740-fb3d287a42fe
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: aa12a7547cfcd4a2076b5b0a308139f8a823f482
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="goto-c-reference"></a><span data-ttu-id="28182-102">goto (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="28182-102">goto (C# Reference)</span></span>
<span data-ttu-id="28182-103">Оператор `goto` передает управление программой непосредственно оператору с меткой.</span><span class="sxs-lookup"><span data-stu-id="28182-103">The `goto` statement transfers the program control directly to a labeled statement.</span></span>  
  
 <span data-ttu-id="28182-104">Оператор `goto` часто используется для передачи управления определенной метке смены регистра или метке по умолчанию в операторе `switch`.</span><span class="sxs-lookup"><span data-stu-id="28182-104">A common use of `goto` is to transfer control to a specific switch-case label or the default label in a `switch` statement.</span></span>  
  
 <span data-ttu-id="28182-105">`goto` Этот оператор также удобно использовать для выхода из глубоко вложенных циклов.</span><span class="sxs-lookup"><span data-stu-id="28182-105">The `goto` statement is also useful to get out of deeply nested loops.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28182-106">Пример</span><span class="sxs-lookup"><span data-stu-id="28182-106">Example</span></span>  
 <span data-ttu-id="28182-107">В следующем примере демонстрируется использование `goto` в операторе [switch](../../../csharp/language-reference/keywords/switch.md).</span><span class="sxs-lookup"><span data-stu-id="28182-107">The following example demonstrates using `goto` in a [switch](../../../csharp/language-reference/keywords/switch.md) statement.</span></span>  
  
 [!code-csharp[csrefKeywordsJump#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/goto_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="28182-108">Пример</span><span class="sxs-lookup"><span data-stu-id="28182-108">Example</span></span>  
 <span data-ttu-id="28182-109">В следующем примере демонстрируется использование `goto` для выхода из вложенных циклов.</span><span class="sxs-lookup"><span data-stu-id="28182-109">The following example demonstrates using `goto` to break out from nested loops.</span></span>  
  
 [!code-csharp[csrefKeywordsJump#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/goto_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="28182-110">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="28182-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="28182-111">См. также</span><span class="sxs-lookup"><span data-stu-id="28182-111">See Also</span></span>  
 [<span data-ttu-id="28182-112">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="28182-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="28182-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="28182-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="28182-114">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="28182-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="28182-115">Оператор GoTo</span><span class="sxs-lookup"><span data-stu-id="28182-115">goto Statement</span></span>](/cpp/cpp/goto-statement-cpp)  
 [<span data-ttu-id="28182-116">Операторы перехода</span><span class="sxs-lookup"><span data-stu-id="28182-116">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)
