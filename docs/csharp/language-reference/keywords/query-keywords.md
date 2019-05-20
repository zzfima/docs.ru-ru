---
title: Ключевые слова запроса. Справочник по C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- query keywords [C#]
- LINQ [C#], query keywords
ms.assetid: 6c9bec16-dbd7-4a7c-a060-fe4600b2021f
ms.openlocfilehash: dde621395f407cd64e047ddfe8c6539e976b3061
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633014"
---
# <a name="query-keywords-c-reference"></a><span data-ttu-id="b4f6c-102">Ключевые слова запроса (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="b4f6c-102">Query keywords (C# Reference)</span></span>

<span data-ttu-id="b4f6c-103">В этом разделе приводятся контекстные ключевые слова, используемые в выражениях запросов.</span><span class="sxs-lookup"><span data-stu-id="b4f6c-103">This section contains the contextual keywords used in query expressions.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="b4f6c-104">Содержание раздела</span><span class="sxs-lookup"><span data-stu-id="b4f6c-104">In this section</span></span>

|<span data-ttu-id="b4f6c-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="b4f6c-105">Clause</span></span>|<span data-ttu-id="b4f6c-106">Описание</span><span class="sxs-lookup"><span data-stu-id="b4f6c-106">Description</span></span>|
|------------|-----------------|
|[<span data-ttu-id="b4f6c-107">from</span><span class="sxs-lookup"><span data-stu-id="b4f6c-107">from</span></span>](from-clause.md)|<span data-ttu-id="b4f6c-108">Задает источник данных и переменную диапазона (аналогично переменной итерации).</span><span class="sxs-lookup"><span data-stu-id="b4f6c-108">Specifies a data source and a range variable (similar to an iteration variable).</span></span>|
|[<span data-ttu-id="b4f6c-109">where</span><span class="sxs-lookup"><span data-stu-id="b4f6c-109">where</span></span>](where-clause.md)|<span data-ttu-id="b4f6c-110">Фильтрует элементы источника на основе одного или нескольких логических выражений, разделенных операторами логического И и ИЛИ (`&&` или <code>&#124;&#124;</code>).</span><span class="sxs-lookup"><span data-stu-id="b4f6c-110">Filters source elements based on one or more Boolean expressions separated by logical AND and OR operators ( `&&` or <code>&#124;&#124;</code> ).</span></span>|
|[<span data-ttu-id="b4f6c-111">select</span><span class="sxs-lookup"><span data-stu-id="b4f6c-111">select</span></span>](select-clause.md)|<span data-ttu-id="b4f6c-112">Задает тип и форму, которые будут иметь элементы в возвращаемой последовательности при выполнении запроса.</span><span class="sxs-lookup"><span data-stu-id="b4f6c-112">Specifies the type and shape that the elements in the returned sequence will have when the query is executed.</span></span>|
|[<span data-ttu-id="b4f6c-113">group</span><span class="sxs-lookup"><span data-stu-id="b4f6c-113">group</span></span>](group-clause.md)|<span data-ttu-id="b4f6c-114">Группирует результаты запроса по заданному значению ключа.</span><span class="sxs-lookup"><span data-stu-id="b4f6c-114">Groups query results according to a specified key value.</span></span>|
|[<span data-ttu-id="b4f6c-115">into</span><span class="sxs-lookup"><span data-stu-id="b4f6c-115">into</span></span>](into.md)|<span data-ttu-id="b4f6c-116">Предоставляет идентификатор, который может использоваться в качестве ссылки на результаты предложения join, group или select.</span><span class="sxs-lookup"><span data-stu-id="b4f6c-116">Provides an identifier that can serve as a reference to the results of a join, group or select clause.</span></span>|
|[<span data-ttu-id="b4f6c-117">orderby</span><span class="sxs-lookup"><span data-stu-id="b4f6c-117">orderby</span></span>](orderby-clause.md)|<span data-ttu-id="b4f6c-118">Сортирует результаты запроса по возрастанию или убыванию на основе функции сравнения по умолчанию для соответствующего типа элемента.</span><span class="sxs-lookup"><span data-stu-id="b4f6c-118">Sorts query results in ascending or descending order based on the default comparer for the element type.</span></span>|
|[<span data-ttu-id="b4f6c-119">join</span><span class="sxs-lookup"><span data-stu-id="b4f6c-119">join</span></span>](join-clause.md)|<span data-ttu-id="b4f6c-120">Соединяет два источника данных посредством сравнения на равенство между двумя заданными критериями сопоставления.</span><span class="sxs-lookup"><span data-stu-id="b4f6c-120">Joins two data sources based on an equality comparison between two specified matching criteria.</span></span>|
|[<span data-ttu-id="b4f6c-121">let</span><span class="sxs-lookup"><span data-stu-id="b4f6c-121">let</span></span>](let-clause.md)|<span data-ttu-id="b4f6c-122">Предоставляет переменную диапазона для хранения результатов выражения, вложенного в выражение запроса.</span><span class="sxs-lookup"><span data-stu-id="b4f6c-122">Introduces a range variable to store sub-expression results in a query expression.</span></span>|
|[<span data-ttu-id="b4f6c-123">in</span><span class="sxs-lookup"><span data-stu-id="b4f6c-123">in</span></span>](in.md)|<span data-ttu-id="b4f6c-124">Контекстное ключевое слово в предложении [join](join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="b4f6c-124">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="b4f6c-125">on</span><span class="sxs-lookup"><span data-stu-id="b4f6c-125">on</span></span>](on.md)|<span data-ttu-id="b4f6c-126">Контекстное ключевое слово в предложении [join](join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="b4f6c-126">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="b4f6c-127">equals</span><span class="sxs-lookup"><span data-stu-id="b4f6c-127">equals</span></span>](equals.md)|<span data-ttu-id="b4f6c-128">Контекстное ключевое слово в предложении [join](join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="b4f6c-128">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="b4f6c-129">by</span><span class="sxs-lookup"><span data-stu-id="b4f6c-129">by</span></span>](by.md)|<span data-ttu-id="b4f6c-130">Контекстное ключевое слово в предложении [group](group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="b4f6c-130">Contextual keyword in a [group](group-clause.md) clause.</span></span>|
|[<span data-ttu-id="b4f6c-131">ascending</span><span class="sxs-lookup"><span data-stu-id="b4f6c-131">ascending</span></span>](ascending.md)|<span data-ttu-id="b4f6c-132">Контекстное ключевое слово в предложении [orderby](orderby-clause.md).</span><span class="sxs-lookup"><span data-stu-id="b4f6c-132">Contextual keyword in an [orderby](orderby-clause.md) clause.</span></span>|
|[<span data-ttu-id="b4f6c-133">descending</span><span class="sxs-lookup"><span data-stu-id="b4f6c-133">descending</span></span>](descending.md)|<span data-ttu-id="b4f6c-134">Контекстное ключевое слово в предложении [orderby](orderby-clause.md).</span><span class="sxs-lookup"><span data-stu-id="b4f6c-134">Contextual keyword in an [orderby](orderby-clause.md) clause.</span></span>|

## <a name="see-also"></a><span data-ttu-id="b4f6c-135">См. также</span><span class="sxs-lookup"><span data-stu-id="b4f6c-135">See also</span></span>

- [<span data-ttu-id="b4f6c-136">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="b4f6c-136">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="b4f6c-137">Встроенный язык запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="b4f6c-137">LINQ (Language-Integrated Query)</span></span>](../../programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="b4f6c-138">Выражения запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="b4f6c-138">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)
- [<span data-ttu-id="b4f6c-139">Приступая к работе с LINQ в C#</span><span class="sxs-lookup"><span data-stu-id="b4f6c-139">Getting Started with LINQ in C#</span></span>](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)
