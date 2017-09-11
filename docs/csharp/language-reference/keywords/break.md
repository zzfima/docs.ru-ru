---
title: "break (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- break
- break_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- break keyword [C#]
ms.assetid: be2571ed-efb0-4965-b122-81e5b09db0b9
caps.latest.revision: 21
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
ms.openlocfilehash: 73f6b6a37513b3aed796d811672fa43fa9e1c0b1
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="break-c-reference"></a><span data-ttu-id="c6ade-102">break (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="c6ade-102">break (C# Reference)</span></span>
<span data-ttu-id="c6ade-103">Оператор `break` завершает выполнение ближайшего оператора внешнего цикла или [switch](../../../csharp/language-reference/keywords/switch.md), в котором он находится.</span><span class="sxs-lookup"><span data-stu-id="c6ade-103">The `break` statement terminates the closest enclosing loop or [switch](../../../csharp/language-reference/keywords/switch.md) statement in which it appears.</span></span> <span data-ttu-id="c6ade-104">Управление передается оператору, который расположен после завершенного оператора.</span><span class="sxs-lookup"><span data-stu-id="c6ade-104">Control is passed to the statement that follows the terminated statement, if any.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6ade-105">Пример</span><span class="sxs-lookup"><span data-stu-id="c6ade-105">Example</span></span>  
 <span data-ttu-id="c6ade-106">В этом примере условный оператор содержит счетчик, который должен выполнять отсчет от 1 до 100; при этом оператор `break` завершает цикл после четырех отсчетов.</span><span class="sxs-lookup"><span data-stu-id="c6ade-106">In this example, the conditional statement contains a counter that is supposed to count from 1 to 100; however, the `break` statement terminates the loop after 4 counts.</span></span>  
  
 <span data-ttu-id="c6ade-107">[!code-cs[csrefKeywordsJump#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/break_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="c6ade-107">[!code-cs[csrefKeywordsJump#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/break_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6ade-108">Пример</span><span class="sxs-lookup"><span data-stu-id="c6ade-108">Example</span></span>  
 <span data-ttu-id="c6ade-109">В этом примере оператор `break` используется для выхода из внутреннего вложенного цикла и возвращения управления внешнему циклу.</span><span class="sxs-lookup"><span data-stu-id="c6ade-109">In this example, the `break` statement is used to break out of an inner nested loop, and return control to the outer loop.</span></span>  
  
 <span data-ttu-id="c6ade-110">[!code-cs[csrefKeywordsJump#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/break_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="c6ade-110">[!code-cs[csrefKeywordsJump#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/break_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6ade-111">Пример</span><span class="sxs-lookup"><span data-stu-id="c6ade-111">Example</span></span>  
 <span data-ttu-id="c6ade-112">В этом примере демонстрируется использование `break` в операторе [switch](../../../csharp/language-reference/keywords/switch.md).</span><span class="sxs-lookup"><span data-stu-id="c6ade-112">This example demonstrates the use of `break` in a [switch](../../../csharp/language-reference/keywords/switch.md) statement.</span></span>  
  
 <span data-ttu-id="c6ade-113">[!code-cs[csrefKeywordsJump#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/break_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="c6ade-113">[!code-cs[csrefKeywordsJump#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/break_3.cs)]</span></span>  
  
 <span data-ttu-id="c6ade-114">Если вы ввели `4`, выходные данные будут следующими:</span><span class="sxs-lookup"><span data-stu-id="c6ade-114">If you entered `4`, the output would be:</span></span>  
  
```  
Enter your selection (1, 2, or 3): 4  
Sorry, invalid selection.  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="c6ade-115">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="c6ade-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c6ade-116">См. также</span><span class="sxs-lookup"><span data-stu-id="c6ade-116">See Also</span></span>  
 <span data-ttu-id="c6ade-117">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="c6ade-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="c6ade-118">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c6ade-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="c6ade-119">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="c6ade-119">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="c6ade-120">[switch](../../../csharp/language-reference/keywords/switch.md) </span><span class="sxs-lookup"><span data-stu-id="c6ade-120">[switch](../../../csharp/language-reference/keywords/switch.md) </span></span>  
 <span data-ttu-id="c6ade-121">[Операторы перехода](../../../csharp/language-reference/keywords/jump-statements.md) </span><span class="sxs-lookup"><span data-stu-id="c6ade-121">[Jump Statements](../../../csharp/language-reference/keywords/jump-statements.md) </span></span>  
 [<span data-ttu-id="c6ade-122">Операторы итерации</span><span class="sxs-lookup"><span data-stu-id="c6ade-122">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)

