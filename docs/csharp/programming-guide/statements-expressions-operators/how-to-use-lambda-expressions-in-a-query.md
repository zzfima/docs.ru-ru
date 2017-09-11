---
title: "Практическое руководство. Использование лямбда-выражений в запросах (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- lambda expressions [C#], in LINQ
ms.assetid: 3cac4d25-d11f-4abd-9e7c-0f02e97ae06d
caps.latest.revision: 16
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
ms.openlocfilehash: 5ad819a0e4d441f6ea092480544195b89e0796ca
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-lambda-expressions-in-a-query-c-programming-guide"></a><span data-ttu-id="f1017-102">Практическое руководство. Использование лямбда-выражений в запросах (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="f1017-102">How to: Use Lambda Expressions in a Query (C# Programming Guide)</span></span>
<span data-ttu-id="f1017-103">Использовать лямбда-выражения непосредственно в синтаксисе запросов нельзя, однако их включают в вызовы методов, а те, в свою очередь, могут содержаться в выражениях запросов.</span><span class="sxs-lookup"><span data-stu-id="f1017-103">You do not use lambda expressions directly in query syntax, but you do use them in method calls, and query expressions can contain method calls.</span></span> <span data-ttu-id="f1017-104">Фактически некоторые операции запросов могут быть выражены только в синтаксисе методов.</span><span class="sxs-lookup"><span data-stu-id="f1017-104">In fact, some query operations can only be expressed in method syntax.</span></span> <span data-ttu-id="f1017-105">Дополнительные сведения о различиях между синтаксисом запросов и синтаксисом методов см. в разделе [Синтаксис запросов и синтаксис методов в LINQ](../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).</span><span class="sxs-lookup"><span data-stu-id="f1017-105">For more information about the difference between query syntax and method syntax, see [Query Syntax and Method Syntax in LINQ](../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1017-106">Пример</span><span class="sxs-lookup"><span data-stu-id="f1017-106">Example</span></span>  
 <span data-ttu-id="f1017-107">Следующий пример демонстрирует, как можно применить лямбда-выражение в запросе, основанном на методе, с помощью стандартного оператора запросов <xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="f1017-107">The following example demonstrates how to use a lambda expression in a method-based query by using the <xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName> standard query operator.</span></span> <span data-ttu-id="f1017-108">Обратите внимание на то, что метод <xref:System.Linq.Enumerable.Where%2A> в этом примере имеет входной параметр с типом делегата <xref:System.Func%601>, а этот делегат принимает на вход целое число и возвращает логическое значение.</span><span class="sxs-lookup"><span data-stu-id="f1017-108">Note that the <xref:System.Linq.Enumerable.Where%2A> method in this example has an input parameter of the delegate type <xref:System.Func%601> and that delegate takes an integer as input and returns a Boolean.</span></span> <span data-ttu-id="f1017-109">Лямбда-выражение может быть преобразовано в этот делегат.</span><span class="sxs-lookup"><span data-stu-id="f1017-109">The lambda expression can be converted to that delegate.</span></span> <span data-ttu-id="f1017-110">Если вы примените запрос [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], в котором используется метод <xref:System.Linq.Queryable.Where%2A?displayProperty=fullName>, параметр будет иметь тип `Expression<Func\<int,bool>>`, но лямбда-выражение останется точно таким же.</span><span class="sxs-lookup"><span data-stu-id="f1017-110">If this were a [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] query that used the <xref:System.Linq.Queryable.Where%2A?displayProperty=fullName> method, the parameter type would be an `Expression<Func\<int,bool>>` but the lambda expression would look exactly the same.</span></span> <span data-ttu-id="f1017-111">Дополнительные сведения о типах выражений см. в статье <xref:System.Linq.Expressions.Expression?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="f1017-111">For more information on the Expression type, see <xref:System.Linq.Expressions.Expression?displayProperty=fullName>.</span></span>  
  
 <span data-ttu-id="f1017-112">[!code-cs[csProgGuideLINQ#1](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-lambda-expressions-in-a-query_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f1017-112">[!code-cs[csProgGuideLINQ#1](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-lambda-expressions-in-a-query_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1017-113">Пример</span><span class="sxs-lookup"><span data-stu-id="f1017-113">Example</span></span>  
 <span data-ttu-id="f1017-114">В приведенном ниже примере показано, как использовать лямбда-выражение в вызове метода выражения запроса.</span><span class="sxs-lookup"><span data-stu-id="f1017-114">The following example demonstrates how to use a lambda expression in a method call of a query expression.</span></span> <span data-ttu-id="f1017-115">Мы вынуждены использовать лямбда-выражения, поскольку синтаксис запросов не позволяет вызвать стандартный оператор запроса <xref:System.Linq.Enumerable.Sum%2A>.</span><span class="sxs-lookup"><span data-stu-id="f1017-115">The lambda is necessary because the <xref:System.Linq.Enumerable.Sum%2A> standard query operator cannot be invoked by using query syntax.</span></span>  
  
 <span data-ttu-id="f1017-116">Сначала запрос группирует учащихся по успеваемости, как задано в перечислении `GradeLevel`.</span><span class="sxs-lookup"><span data-stu-id="f1017-116">The query first groups the students according to their grade level, as defined in the `GradeLevel` enum.</span></span> <span data-ttu-id="f1017-117">Затем для каждой группы он добавляет итоговые оценки каждого учащегося.</span><span class="sxs-lookup"><span data-stu-id="f1017-117">Then for each group it adds the total scores for each student.</span></span> <span data-ttu-id="f1017-118">Для этого требуются две операции `Sum`.</span><span class="sxs-lookup"><span data-stu-id="f1017-118">This requires two `Sum` operations.</span></span> <span data-ttu-id="f1017-119">Внутренняя операция `Sum` вычисляет общий результат для каждого учащегося, а внешняя операция `Sum` рассчитывает промежуточный общий результат по всем учащимся в группе.</span><span class="sxs-lookup"><span data-stu-id="f1017-119">The inner `Sum` calculates the total score for each student, and the outer `Sum` keeps a running, combined total for all students in the group.</span></span>  
  
 <span data-ttu-id="f1017-120">[!code-cs[csProgGuideLINQ#2](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-lambda-expressions-in-a-query_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="f1017-120">[!code-cs[csProgGuideLINQ#2](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-lambda-expressions-in-a-query_2.cs)]</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f1017-121">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="f1017-121">Compiling the Code</span></span>  
 <span data-ttu-id="f1017-122">Чтобы выполнить этот код, скопируйте и вставьте метод в `StudentClass`, описанный в документе [Практическое руководство. Запрос коллекции объектов](../../../csharp/programming-guide/linq-query-expressions/how-to-query-a-collection-of-objects.md), а затем вызовите его из метода `Main`.</span><span class="sxs-lookup"><span data-stu-id="f1017-122">To run this code, copy and paste the method into the `StudentClass` that is provided in [How to: Query a Collection of Objects](../../../csharp/programming-guide/linq-query-expressions/how-to-query-a-collection-of-objects.md) and call it from the `Main` method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1017-123">См. также</span><span class="sxs-lookup"><span data-stu-id="f1017-123">See Also</span></span>  
 <span data-ttu-id="f1017-124">[Лямбда-выражения](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="f1017-124">[Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) </span></span>  
 [<span data-ttu-id="f1017-125">Деревья выражений</span><span class="sxs-lookup"><span data-stu-id="f1017-125">Expression Trees</span></span>](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b)

