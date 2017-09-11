---
title: "return (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- return_CSharpKeyword
- return
dev_langs:
- CSharp
helpviewer_keywords:
- return statement [C#]
- return keyword [C#]
ms.assetid: 6da6e152-5b58-4448-8f3f-470dd0617ecd
caps.latest.revision: 18
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
ms.openlocfilehash: 596375a1cba8f5ecbad636a6829c1a0599f8c0f4
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="return-c-reference"></a><span data-ttu-id="e0a71-102">return (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="e0a71-102">return (C# Reference)</span></span>
<span data-ttu-id="e0a71-103">Оператор `return` завершает выполнение метода, в котором он присутствует, и возвращает управление вызывавшему методу.</span><span class="sxs-lookup"><span data-stu-id="e0a71-103">The `return` statement terminates execution of the method in which it appears and returns control to the calling method.</span></span> <span data-ttu-id="e0a71-104">Он также возвращает необязательное значение.</span><span class="sxs-lookup"><span data-stu-id="e0a71-104">It can also return an optional value.</span></span> <span data-ttu-id="e0a71-105">Если метод имеет тип `void`, оператор `return` можно опустить.</span><span class="sxs-lookup"><span data-stu-id="e0a71-105">If the method is a `void` type, the `return` statement can be omitted.</span></span>  
  
 <span data-ttu-id="e0a71-106">Если оператор return находится внутри блока `try`, блок `finally`, если он существует, будет выполняться до возврата управления вызывающему методу.</span><span class="sxs-lookup"><span data-stu-id="e0a71-106">If the return statement is inside a `try` block, the `finally` block, if one exists, will be executed before control returns to the calling method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0a71-107">Пример</span><span class="sxs-lookup"><span data-stu-id="e0a71-107">Example</span></span>  
 <span data-ttu-id="e0a71-108">В приведенном ниже примере метод `A()` возвращает переменную `Area` в виде значения [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="e0a71-108">In the following example, the method `A()` returns the variable `Area` as a [double](../../../csharp/language-reference/keywords/double.md) value.</span></span>  
  
 <span data-ttu-id="e0a71-109">[!code-cs[csrefKeywordsJump#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/return_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e0a71-109">[!code-cs[csrefKeywordsJump#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/return_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="e0a71-110">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="e0a71-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e0a71-111">См. также</span><span class="sxs-lookup"><span data-stu-id="e0a71-111">See Also</span></span>  
 <span data-ttu-id="e0a71-112">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="e0a71-112">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="e0a71-113">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e0a71-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="e0a71-114">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="e0a71-114">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="e0a71-115">[Оператор return](/cpp/cpp/return-statement-cpp) </span><span class="sxs-lookup"><span data-stu-id="e0a71-115">[return Statement](/cpp/cpp/return-statement-cpp) </span></span>  
 [<span data-ttu-id="e0a71-116">Операторы перехода</span><span class="sxs-lookup"><span data-stu-id="e0a71-116">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)

