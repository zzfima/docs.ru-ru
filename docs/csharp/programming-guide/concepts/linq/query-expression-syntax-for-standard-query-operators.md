---
title: "Синтаксис выражений запроса для стандартных операторов запроса (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: e1e17ef2-68ff-4c26-b6e2-015668227fa5
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 30e994329234b8bd455f739694e50121bac63d5d
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="query-expression-syntax-for-standard-query-operators-c"></a><span data-ttu-id="87c5d-102">Синтаксис выражений запроса для стандартных операторов запроса (C#)</span><span class="sxs-lookup"><span data-stu-id="87c5d-102">Query Expression Syntax for Standard Query Operators (C#)</span></span>
<span data-ttu-id="87c5d-103">Некоторые из наиболее часто используемых стандартных операторов запросов имеют представление в виде ключевых слов в синтаксисе языка C#, что позволяет вызывать их как часть *выражения запроса*.</span><span class="sxs-lookup"><span data-stu-id="87c5d-103">Some of the more frequently used standard query operators have dedicated C# language keyword syntax that enables them to be called as part of a *query expression*.</span></span> <span data-ttu-id="87c5d-104">Выражение запроса является более удобочитаемой формой задания запроса, чем его *основанный на методах* эквивалент.</span><span class="sxs-lookup"><span data-stu-id="87c5d-104">A query expression is a different, more readable form of expressing a query than its *method-based*  equivalent.</span></span> <span data-ttu-id="87c5d-105">Предложения выражений запросов преобразуются в вызовы методов запросов во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="87c5d-105">Query expression clauses are translated into calls to the query methods at compile time.</span></span>  
  
## <a name="query-expression-syntax-table"></a><span data-ttu-id="87c5d-106">Таблица синтаксиса выражений запросов</span><span class="sxs-lookup"><span data-stu-id="87c5d-106">Query Expression Syntax Table</span></span>  
 <span data-ttu-id="87c5d-107">В следующей таблице приводится список стандартных операторов запросов, имеющих эквивалентные предложения выражений запросов.</span><span class="sxs-lookup"><span data-stu-id="87c5d-107">The following table lists the standard query operators that have equivalent query expression clauses.</span></span>  
  
|<span data-ttu-id="87c5d-108">Метод</span><span class="sxs-lookup"><span data-stu-id="87c5d-108">Method</span></span>|<span data-ttu-id="87c5d-109">Синтаксис выражения запроса C#</span><span class="sxs-lookup"><span data-stu-id="87c5d-109">C# Query Expression Syntax</span></span>|  
|------------|---------------------------------|  
|<xref:System.Linq.Enumerable.Cast%2A>|<span data-ttu-id="87c5d-110">Использование явным образом типизированной переменной диапазона, например:</span><span class="sxs-lookup"><span data-stu-id="87c5d-110">Use an explicitly typed range variable, for example:</span></span><br /><br /> `from int i in numbers`<br /><br /> <span data-ttu-id="87c5d-111">(Дополнительные сведения см. в разделе [Предложение from](../../../../csharp/language-reference/keywords/from-clause.md).)</span><span class="sxs-lookup"><span data-stu-id="87c5d-111">(For more information, see [from clause](../../../../csharp/language-reference/keywords/from-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.GroupBy%2A>|`group … by`<br /><br /> <span data-ttu-id="87c5d-112">-или-</span><span class="sxs-lookup"><span data-stu-id="87c5d-112">-or-</span></span><br /><br /> `group … by … into …`<br /><br /> <span data-ttu-id="87c5d-113">(Дополнительные сведения см. в разделе [Предложение group](../../../../csharp/language-reference/keywords/group-clause.md).)</span><span class="sxs-lookup"><span data-stu-id="87c5d-113">(For more information, see [group clause](../../../../csharp/language-reference/keywords/group-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.GroupJoin%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2C%60%603%7D%29>|`join … in … on … equals … into …`<br /><br /> <span data-ttu-id="87c5d-114">(Дополнительные сведения см. в разделе [Предложение join](../../../../csharp/language-reference/keywords/join-clause.md).)</span><span class="sxs-lookup"><span data-stu-id="87c5d-114">(For more information, see [join clause](../../../../csharp/language-reference/keywords/join-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.Join%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%603%7D%29>|`join … in … on … equals …`<br /><br /> <span data-ttu-id="87c5d-115">(Дополнительные сведения см. в разделе [Предложение join](../../../../csharp/language-reference/keywords/join-clause.md).)</span><span class="sxs-lookup"><span data-stu-id="87c5d-115">(For more information, see [join clause](../../../../csharp/language-reference/keywords/join-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.OrderBy%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby`<br /><br /> <span data-ttu-id="87c5d-116">(Дополнительные сведения см. в разделе [Предложение orderby](../../../../csharp/language-reference/keywords/orderby-clause.md).)</span><span class="sxs-lookup"><span data-stu-id="87c5d-116">(For more information, see [orderby clause](../../../../csharp/language-reference/keywords/orderby-clause.md).)</span></span>|  
<xref:System.Linq.Enumerable.OrderByDescending%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby … descending`<br /><br /> <span data-ttu-id="87c5d-117">(Дополнительные сведения см. в разделе [Предложение orderby](../../../../csharp/language-reference/keywords/orderby-clause.md).)</span><span class="sxs-lookup"><span data-stu-id="87c5d-117">(For more information, see [orderby clause](../../../../csharp/language-reference/keywords/orderby-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.Select%2A>|`select`<br /><br /> <span data-ttu-id="87c5d-118">(Дополнительные сведения см. в разделе [Предложение select](../../../../csharp/language-reference/keywords/select-clause.md).)</span><span class="sxs-lookup"><span data-stu-id="87c5d-118">(For more information, see [select clause](../../../../csharp/language-reference/keywords/select-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.SelectMany%2A>|<span data-ttu-id="87c5d-119">Несколько предложений `from`.</span><span class="sxs-lookup"><span data-stu-id="87c5d-119">Multiple `from` clauses.</span></span><br /><br /> <span data-ttu-id="87c5d-120">(Дополнительные сведения см. в разделе [Предложение from](../../../../csharp/language-reference/keywords/from-clause.md).)</span><span class="sxs-lookup"><span data-stu-id="87c5d-120">(For more information, see [from clause](../../../../csharp/language-reference/keywords/from-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.ThenBy%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby …, …`<br /><br /> <span data-ttu-id="87c5d-121">(Дополнительные сведения см. в разделе [Предложение orderby](../../../../csharp/language-reference/keywords/orderby-clause.md).)</span><span class="sxs-lookup"><span data-stu-id="87c5d-121">(For more information, see [orderby clause](../../../../csharp/language-reference/keywords/orderby-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.ThenByDescending%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby …, … descending`<br /><br /> <span data-ttu-id="87c5d-122">(Дополнительные сведения см. в разделе [Предложение orderby](../../../../csharp/language-reference/keywords/orderby-clause.md).)</span><span class="sxs-lookup"><span data-stu-id="87c5d-122">(For more information, see [orderby clause](../../../../csharp/language-reference/keywords/orderby-clause.md).)</span></span>|  
|<xref:System.Linq.Enumerable.Where%2A>|`where`<br /><br /> <span data-ttu-id="87c5d-123">(Дополнительные сведения см. в разделе [Предложение where](../../../../csharp/language-reference/keywords/where-clause.md).)</span><span class="sxs-lookup"><span data-stu-id="87c5d-123">(For more information, see [where clause](../../../../csharp/language-reference/keywords/where-clause.md).)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="87c5d-124">См. также</span><span class="sxs-lookup"><span data-stu-id="87c5d-124">See Also</span></span>  
 <span data-ttu-id="87c5d-125"><xref:System.Linq.Enumerable></span><span class="sxs-lookup"><span data-stu-id="87c5d-125"><xref:System.Linq.Enumerable></span></span>   
 <span data-ttu-id="87c5d-126"><xref:System.Linq.Queryable></span><span class="sxs-lookup"><span data-stu-id="87c5d-126"><xref:System.Linq.Queryable></span></span>   
 <span data-ttu-id="87c5d-127">[Общие сведения о стандартных операторах запроса (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="87c5d-127">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
 [<span data-ttu-id="87c5d-128">Классификация стандартных операторов запросов по способу выполнения (C#)</span><span class="sxs-lookup"><span data-stu-id="87c5d-128">Classification of Standard Query Operators by Manner of Execution (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/classification-of-standard-query-operators-by-manner-of-execution.md)

