---
title: "Ключевые слова запроса (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- query keywords [C#]
- LINQ [C#], query keywords
ms.assetid: 6c9bec16-dbd7-4a7c-a060-fe4600b2021f
caps.latest.revision: 15
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
ms.openlocfilehash: 6dadce6d48e711032cca03a7f7c2ba02360e685f
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="query-keywords-c-reference"></a><span data-ttu-id="a8d82-102">Ключевые слова запроса (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="a8d82-102">Query Keywords (C# Reference)</span></span>
<span data-ttu-id="a8d82-103">В этом разделе приводятся контекстные ключевые слова, используемые в выражениях запросов.</span><span class="sxs-lookup"><span data-stu-id="a8d82-103">This section contains the contextual keywords used in query expressions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a8d82-104">Содержание</span><span class="sxs-lookup"><span data-stu-id="a8d82-104">In This Section</span></span>  
  
|<span data-ttu-id="a8d82-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="a8d82-105">Clause</span></span>|<span data-ttu-id="a8d82-106">Описание</span><span class="sxs-lookup"><span data-stu-id="a8d82-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a8d82-107">from</span><span class="sxs-lookup"><span data-stu-id="a8d82-107">from</span></span>](../../../csharp/language-reference/keywords/from-clause.md)|<span data-ttu-id="a8d82-108">Задает источник данных и переменную диапазона (аналогично переменной итерации).</span><span class="sxs-lookup"><span data-stu-id="a8d82-108">Specifies a data source and a range variable (similar to an iteration variable).</span></span>|  
|[<span data-ttu-id="a8d82-109">where</span><span class="sxs-lookup"><span data-stu-id="a8d82-109">where</span></span>](../../../csharp/language-reference/keywords/where-clause.md)|<span data-ttu-id="a8d82-110">Фильтрует элементы источника на основе одного или нескольких логических выражений, разделенных операторами логического И и ИЛИ (`&&` или <code>&#124;&#124;</code>).</span><span class="sxs-lookup"><span data-stu-id="a8d82-110">Filters source elements based on one or more Boolean expressions separated by logical AND and OR operators ( `&&` or <code>&#124;&#124;</code> ).</span></span>|  
|[<span data-ttu-id="a8d82-111">select</span><span class="sxs-lookup"><span data-stu-id="a8d82-111">select</span></span>](../../../csharp/language-reference/keywords/select-clause.md)|<span data-ttu-id="a8d82-112">Задает тип и форму, которые будут иметь элементы в возвращаемой последовательности при выполнении запроса.</span><span class="sxs-lookup"><span data-stu-id="a8d82-112">Specifies the type and shape that the elements in the returned sequence will have when the query is executed.</span></span>|  
|[<span data-ttu-id="a8d82-113">group</span><span class="sxs-lookup"><span data-stu-id="a8d82-113">group</span></span>](../../../csharp/language-reference/keywords/group-clause.md)|<span data-ttu-id="a8d82-114">Группирует результаты запроса по заданному значению ключа.</span><span class="sxs-lookup"><span data-stu-id="a8d82-114">Groups query results according to a specified key value.</span></span>|  
|[<span data-ttu-id="a8d82-115">into</span><span class="sxs-lookup"><span data-stu-id="a8d82-115">into</span></span>](../../../csharp/language-reference/keywords/into.md)|<span data-ttu-id="a8d82-116">Предоставляет идентификатор, который может использоваться в качестве ссылки на результаты предложения join, group или select.</span><span class="sxs-lookup"><span data-stu-id="a8d82-116">Provides an identifier that can serve as a reference to the results of a join, group or select clause.</span></span>|  
|[<span data-ttu-id="a8d82-117">orderby</span><span class="sxs-lookup"><span data-stu-id="a8d82-117">orderby</span></span>](../../../csharp/language-reference/keywords/orderby-clause.md)|<span data-ttu-id="a8d82-118">Сортирует результаты запроса по возрастанию или убыванию на основе функции сравнения по умолчанию для соответствующего типа элемента.</span><span class="sxs-lookup"><span data-stu-id="a8d82-118">Sorts query results in ascending or descending order based on the default comparer for the element type.</span></span>|  
|[<span data-ttu-id="a8d82-119">join</span><span class="sxs-lookup"><span data-stu-id="a8d82-119">join</span></span>](../../../csharp/language-reference/keywords/join-clause.md)|<span data-ttu-id="a8d82-120">Соединяет два источника данных посредством сравнения на равенство между двумя заданными критериями сопоставления.</span><span class="sxs-lookup"><span data-stu-id="a8d82-120">Joins two data sources based on an equality comparison between two specified matching criteria.</span></span>|  
|[<span data-ttu-id="a8d82-121">let</span><span class="sxs-lookup"><span data-stu-id="a8d82-121">let</span></span>](../../../csharp/language-reference/keywords/let-clause.md)|<span data-ttu-id="a8d82-122">Предоставляет переменную диапазона для хранения результатов выражения, вложенного в выражение запроса.</span><span class="sxs-lookup"><span data-stu-id="a8d82-122">Introduces a range variable to store sub-expression results in a query expression.</span></span>|  
|[<span data-ttu-id="a8d82-123">in</span><span class="sxs-lookup"><span data-stu-id="a8d82-123">in</span></span>](../../../csharp/language-reference/keywords/in.md)|<span data-ttu-id="a8d82-124">Контекстное ключевое слово в предложении [join](../../../csharp/language-reference/keywords/join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="a8d82-124">Contextual keyword in a [join](../../../csharp/language-reference/keywords/join-clause.md) clause.</span></span>|  
|[<span data-ttu-id="a8d82-125">on</span><span class="sxs-lookup"><span data-stu-id="a8d82-125">on</span></span>](../../../csharp/language-reference/keywords/on.md)|<span data-ttu-id="a8d82-126">Контекстное ключевое слово в предложении [join](../../../csharp/language-reference/keywords/join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="a8d82-126">Contextual keyword in a [join](../../../csharp/language-reference/keywords/join-clause.md) clause.</span></span>|  
|[<span data-ttu-id="a8d82-127">equals</span><span class="sxs-lookup"><span data-stu-id="a8d82-127">equals</span></span>](../../../csharp/language-reference/keywords/equals.md)|<span data-ttu-id="a8d82-128">Контекстное ключевое слово в предложении [join](../../../csharp/language-reference/keywords/join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="a8d82-128">Contextual keyword in a [join](../../../csharp/language-reference/keywords/join-clause.md) clause.</span></span>|  
|[<span data-ttu-id="a8d82-129">by</span><span class="sxs-lookup"><span data-stu-id="a8d82-129">by</span></span>](../../../csharp/language-reference/keywords/by.md)|<span data-ttu-id="a8d82-130">Контекстное ключевое слово в предложении [group](../../../csharp/language-reference/keywords/group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="a8d82-130">Contextual keyword in a [group](../../../csharp/language-reference/keywords/group-clause.md) clause.</span></span>|  
|[<span data-ttu-id="a8d82-131">ascending</span><span class="sxs-lookup"><span data-stu-id="a8d82-131">ascending</span></span>](../../../csharp/language-reference/keywords/ascending.md)|<span data-ttu-id="a8d82-132">Контекстное ключевое слово в предложении [orderby](../../../csharp/language-reference/keywords/orderby-clause.md).</span><span class="sxs-lookup"><span data-stu-id="a8d82-132">Contextual keyword in an [orderby](../../../csharp/language-reference/keywords/orderby-clause.md) clause.</span></span>|  
|[<span data-ttu-id="a8d82-133">descending</span><span class="sxs-lookup"><span data-stu-id="a8d82-133">descending</span></span>](../../../csharp/language-reference/keywords/descending.md)|<span data-ttu-id="a8d82-134">Контекстное ключевое слово в предложении [orderby](../../../csharp/language-reference/keywords/orderby-clause.md).</span><span class="sxs-lookup"><span data-stu-id="a8d82-134">Contextual keyword in an [orderby](../../../csharp/language-reference/keywords/orderby-clause.md) clause.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a8d82-135">См. также</span><span class="sxs-lookup"><span data-stu-id="a8d82-135">See Also</span></span>  
 <span data-ttu-id="a8d82-136">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="a8d82-136">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="a8d82-137">[Встроенный язык запросов LINQ](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) </span><span class="sxs-lookup"><span data-stu-id="a8d82-137">[LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) </span></span>  
 <span data-ttu-id="a8d82-138">[Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="a8d82-138">[LINQ Query Expressions](../../../csharp/programming-guide/linq-query-expressions/index.md) </span></span>  
 [<span data-ttu-id="a8d82-139">Приступая к работе с LINQ в C#</span><span class="sxs-lookup"><span data-stu-id="a8d82-139">Getting Started with LINQ in C#</span></span>](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)

