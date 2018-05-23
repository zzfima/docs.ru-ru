---
title: Предложение let (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- let_CSharpKeyword
- let
helpviewer_keywords:
- let keyword [C#]
- let clause [C#]
ms.assetid: 13c9c1a4-ce57-48ef-8e1b-4c2a59b99fb4
ms.openlocfilehash: 9d625db1231687cdad2e24303b2e08ecf736a50c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="let-clause-c-reference"></a><span data-ttu-id="a58c2-102">Предложение let (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="a58c2-102">let clause (C# Reference)</span></span>
<span data-ttu-id="a58c2-103">В выражении запроса иногда требуется сохранить результат вложенного выражения, который будет использоваться в последующих предложениях.</span><span class="sxs-lookup"><span data-stu-id="a58c2-103">In a query expression, it is sometimes useful to store the result of a sub-expression in order to use it in subsequent clauses.</span></span> <span data-ttu-id="a58c2-104">Это можно сделать с помощью ключевого слова `let`, которое создает новую переменную диапазона и инициализирует ее, используя результат предоставленного выражения.</span><span class="sxs-lookup"><span data-stu-id="a58c2-104">You can do this with the `let` keyword, which creates a new range variable and initializes it with the result of the expression you supply.</span></span> <span data-ttu-id="a58c2-105">После инициализации с использованием этого значения такую переменную диапазона нельзя использовать для хранения других значений.</span><span class="sxs-lookup"><span data-stu-id="a58c2-105">Once initialized with a value, the range variable cannot be used to store another value.</span></span> <span data-ttu-id="a58c2-106">Тем не менее если переменная диапазона хранит запрашиваемый тип, к ней можно выполнять запросы.</span><span class="sxs-lookup"><span data-stu-id="a58c2-106">However, if the range variable holds a queryable type, it can be queried.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a58c2-107">Пример</span><span class="sxs-lookup"><span data-stu-id="a58c2-107">Example</span></span>  
 <span data-ttu-id="a58c2-108">В следующем примере показываются два способа использования `let`:</span><span class="sxs-lookup"><span data-stu-id="a58c2-108">In the following example `let` is used in two ways:</span></span>  
  
1.  <span data-ttu-id="a58c2-109">Создание перечисляемого типа, к которому можно выполнять запросы.</span><span class="sxs-lookup"><span data-stu-id="a58c2-109">To create an enumerable type that can itself be queried.</span></span>  
  
2.  <span data-ttu-id="a58c2-110">Реализация запроса с однократным вызовом `ToLower` для переменной диапазона `word`.</span><span class="sxs-lookup"><span data-stu-id="a58c2-110">To enable the query to call `ToLower` only one time on the range variable `word`.</span></span> <span data-ttu-id="a58c2-111">Если ключевое слово `let` не используется, потребуется выполнять вызов `ToLower` в каждом предикате предложения `where`.</span><span class="sxs-lookup"><span data-stu-id="a58c2-111">Without using `let`, you would have to call `ToLower` in each predicate in the `where` clause.</span></span>  
  
 [!code-csharp[cscsrefQueryKeywords#28](../../../csharp/language-reference/keywords/codesnippet/CSharp/let-clause_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="a58c2-112">См. также</span><span class="sxs-lookup"><span data-stu-id="a58c2-112">See Also</span></span>  
 [<span data-ttu-id="a58c2-113">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="a58c2-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="a58c2-114">Ключевые слова запроса (LINQ)</span><span class="sxs-lookup"><span data-stu-id="a58c2-114">Query Keywords (LINQ)</span></span>](../../../csharp/language-reference/keywords/query-keywords.md)  
 [<span data-ttu-id="a58c2-115">Выражения запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="a58c2-115">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [<span data-ttu-id="a58c2-116">Приступая к работе с LINQ в C#</span><span class="sxs-lookup"><span data-stu-id="a58c2-116">Getting Started with LINQ in C#</span></span>](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [<span data-ttu-id="a58c2-117">Практическое руководство. Обработка исключений в выражениях запросов</span><span class="sxs-lookup"><span data-stu-id="a58c2-117">How to: Handle Exceptions in Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/how-to-handle-exceptions-in-query-expressions.md)
