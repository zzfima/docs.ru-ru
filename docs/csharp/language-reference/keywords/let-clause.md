---
title: "Предложение let (справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- let_CSharpKeyword
- let
helpviewer_keywords:
- let keyword [C#]
- let clause [C#]
ms.assetid: 13c9c1a4-ce57-48ef-8e1b-4c2a59b99fb4
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 077c5178946b85d0fb85aa8da94966e4c5821736
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="let-clause-c-reference"></a><span data-ttu-id="7bebe-102">Предложение let (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="7bebe-102">let clause (C# Reference)</span></span>
<span data-ttu-id="7bebe-103">В выражении запроса иногда требуется сохранить результат вложенного выражения, который будет использоваться в последующих предложениях.</span><span class="sxs-lookup"><span data-stu-id="7bebe-103">In a query expression, it is sometimes useful to store the result of a sub-expression in order to use it in subsequent clauses.</span></span> <span data-ttu-id="7bebe-104">Это можно сделать с помощью ключевого слова `let`, которое создает новую переменную диапазона и инициализирует ее, используя результат предоставленного выражения.</span><span class="sxs-lookup"><span data-stu-id="7bebe-104">You can do this with the `let` keyword, which creates a new range variable and initializes it with the result of the expression you supply.</span></span> <span data-ttu-id="7bebe-105">После инициализации с использованием этого значения такую переменную диапазона нельзя использовать для хранения других значений.</span><span class="sxs-lookup"><span data-stu-id="7bebe-105">Once initialized with a value, the range variable cannot be used to store another value.</span></span> <span data-ttu-id="7bebe-106">Тем не менее если переменная диапазона хранит запрашиваемый тип, к ней можно выполнять запросы.</span><span class="sxs-lookup"><span data-stu-id="7bebe-106">However, if the range variable holds a queryable type, it can be queried.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7bebe-107">Пример</span><span class="sxs-lookup"><span data-stu-id="7bebe-107">Example</span></span>  
 <span data-ttu-id="7bebe-108">В следующем примере показываются два способа использования `let`:</span><span class="sxs-lookup"><span data-stu-id="7bebe-108">In the following example `let` is used in two ways:</span></span>  
  
1.  <span data-ttu-id="7bebe-109">Создание перечисляемого типа, к которому можно выполнять запросы.</span><span class="sxs-lookup"><span data-stu-id="7bebe-109">To create an enumerable type that can itself be queried.</span></span>  
  
2.  <span data-ttu-id="7bebe-110">Реализация запроса с однократным вызовом `ToLower` для переменной диапазона `word`.</span><span class="sxs-lookup"><span data-stu-id="7bebe-110">To enable the query to call `ToLower` only one time on the range variable `word`.</span></span> <span data-ttu-id="7bebe-111">Если ключевое слово `let` не используется, потребуется выполнять вызов `ToLower` в каждом предикате предложения `where`.</span><span class="sxs-lookup"><span data-stu-id="7bebe-111">Without using `let`, you would have to call `ToLower` in each predicate in the `where` clause.</span></span>  
  
 [!code-csharp[cscsrefQueryKeywords#28](../../../csharp/language-reference/keywords/codesnippet/CSharp/let-clause_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="7bebe-112">См. также</span><span class="sxs-lookup"><span data-stu-id="7bebe-112">See Also</span></span>  
 [<span data-ttu-id="7bebe-113">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="7bebe-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="7bebe-114">Ключевые слова запроса (LINQ)</span><span class="sxs-lookup"><span data-stu-id="7bebe-114">Query Keywords (LINQ)</span></span>](../../../csharp/language-reference/keywords/query-keywords.md)  
 [<span data-ttu-id="7bebe-115">Выражения запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="7bebe-115">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [<span data-ttu-id="7bebe-116">Приступая к работе с LINQ в C#</span><span class="sxs-lookup"><span data-stu-id="7bebe-116">Getting Started with LINQ in C#</span></span>](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [<span data-ttu-id="7bebe-117">Практическое руководство. Обработка исключений в выражениях запросов</span><span class="sxs-lookup"><span data-stu-id="7bebe-117">How to: Handle Exceptions in Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/how-to-handle-exceptions-in-query-expressions.md)
