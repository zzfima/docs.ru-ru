---
title: "return (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- return_CSharpKeyword
- return
helpviewer_keywords:
- return statement [C#]
- return keyword [C#]
ms.assetid: 6da6e152-5b58-4448-8f3f-470dd0617ecd
caps.latest.revision: "18"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 90c84b51c6ee57864eac552bc488c9f9c15e9394
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="return-c-reference"></a><span data-ttu-id="dd4fa-102">return (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="dd4fa-102">return (C# Reference)</span></span>
<span data-ttu-id="dd4fa-103">Оператор `return` завершает выполнение метода, в котором он присутствует, и возвращает управление вызывавшему методу.</span><span class="sxs-lookup"><span data-stu-id="dd4fa-103">The `return` statement terminates execution of the method in which it appears and returns control to the calling method.</span></span> <span data-ttu-id="dd4fa-104">Он также возвращает необязательное значение.</span><span class="sxs-lookup"><span data-stu-id="dd4fa-104">It can also return an optional value.</span></span> <span data-ttu-id="dd4fa-105">Если метод имеет тип `void`, оператор `return` можно опустить.</span><span class="sxs-lookup"><span data-stu-id="dd4fa-105">If the method is a `void` type, the `return` statement can be omitted.</span></span>  
  
 <span data-ttu-id="dd4fa-106">Если оператор return находится внутри блока `try`, блок `finally`, если он существует, будет выполняться до возврата управления вызывающему методу.</span><span class="sxs-lookup"><span data-stu-id="dd4fa-106">If the return statement is inside a `try` block, the `finally` block, if one exists, will be executed before control returns to the calling method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd4fa-107">Пример</span><span class="sxs-lookup"><span data-stu-id="dd4fa-107">Example</span></span>  
 <span data-ttu-id="dd4fa-108">В следующем примере метод `CalculateArea()` возвращает локальную переменную `area` как [двойные](../../../csharp/language-reference/keywords/double.md) значение.</span><span class="sxs-lookup"><span data-stu-id="dd4fa-108">In the following example, the method `CalculateArea()` returns the local variable `area` as a [double](../../../csharp/language-reference/keywords/double.md) value.</span></span>  
  
 [!code-csharp[csrefKeywordsJump#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/return_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="dd4fa-109">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="dd4fa-109">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="dd4fa-110">См. также</span><span class="sxs-lookup"><span data-stu-id="dd4fa-110">See Also</span></span>  
 [<span data-ttu-id="dd4fa-111">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="dd4fa-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="dd4fa-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="dd4fa-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="dd4fa-113">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="dd4fa-113">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="dd4fa-114">Оператор return</span><span class="sxs-lookup"><span data-stu-id="dd4fa-114">return Statement</span></span>](/cpp/cpp/return-statement-cpp)  
 [<span data-ttu-id="dd4fa-115">Операторы перехода</span><span class="sxs-lookup"><span data-stu-id="dd4fa-115">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)
