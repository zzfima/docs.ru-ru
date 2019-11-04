---
title: Ключевые слова запроса. Справочник по C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- query keywords [C#]
- LINQ [C#], query keywords
ms.assetid: 6c9bec16-dbd7-4a7c-a060-fe4600b2021f
ms.openlocfilehash: 44af3bf1a7c013c16c7b4a4528c3516621bea149
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73422541"
---
# <a name="query-keywords-c-reference"></a><span data-ttu-id="d1bea-102">Ключевые слова запроса (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="d1bea-102">Query keywords (C# Reference)</span></span>

<span data-ttu-id="d1bea-103">В этом разделе приводятся контекстные ключевые слова, используемые в выражениях запросов.</span><span class="sxs-lookup"><span data-stu-id="d1bea-103">This section contains the contextual keywords used in query expressions.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="d1bea-104">Содержание раздела</span><span class="sxs-lookup"><span data-stu-id="d1bea-104">In this section</span></span>

|<span data-ttu-id="d1bea-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="d1bea-105">Clause</span></span>|<span data-ttu-id="d1bea-106">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="d1bea-106">Description</span></span>|
|------------|-----------------|
|[<span data-ttu-id="d1bea-107">from</span><span class="sxs-lookup"><span data-stu-id="d1bea-107">from</span></span>](from-clause.md)|<span data-ttu-id="d1bea-108">Задает источник данных и переменную диапазона (аналогично переменной итерации).</span><span class="sxs-lookup"><span data-stu-id="d1bea-108">Specifies a data source and a range variable (similar to an iteration variable).</span></span>|
|[<span data-ttu-id="d1bea-109">where</span><span class="sxs-lookup"><span data-stu-id="d1bea-109">where</span></span>](where-clause.md)|<span data-ttu-id="d1bea-110">Фильтрует элементы источника на основе одного или нескольких логических выражений, разделенных операторами логического И и ИЛИ (`&&` или <code>&#124;&#124;</code>).</span><span class="sxs-lookup"><span data-stu-id="d1bea-110">Filters source elements based on one or more Boolean expressions separated by logical AND and OR operators ( `&&` or <code>&#124;&#124;</code> ).</span></span>|
|[<span data-ttu-id="d1bea-111">select</span><span class="sxs-lookup"><span data-stu-id="d1bea-111">select</span></span>](select-clause.md)|<span data-ttu-id="d1bea-112">Задает тип и форму, которые будут иметь элементы в возвращаемой последовательности при выполнении запроса.</span><span class="sxs-lookup"><span data-stu-id="d1bea-112">Specifies the type and shape that the elements in the returned sequence will have when the query is executed.</span></span>|
|[<span data-ttu-id="d1bea-113">group</span><span class="sxs-lookup"><span data-stu-id="d1bea-113">group</span></span>](group-clause.md)|<span data-ttu-id="d1bea-114">Группирует результаты запроса по заданному значению ключа.</span><span class="sxs-lookup"><span data-stu-id="d1bea-114">Groups query results according to a specified key value.</span></span>|
|[<span data-ttu-id="d1bea-115">into</span><span class="sxs-lookup"><span data-stu-id="d1bea-115">into</span></span>](into.md)|<span data-ttu-id="d1bea-116">Предоставляет идентификатор, который может использоваться в качестве ссылки на результаты предложения join, group или select.</span><span class="sxs-lookup"><span data-stu-id="d1bea-116">Provides an identifier that can serve as a reference to the results of a join, group or select clause.</span></span>|
|[<span data-ttu-id="d1bea-117">orderby</span><span class="sxs-lookup"><span data-stu-id="d1bea-117">orderby</span></span>](orderby-clause.md)|<span data-ttu-id="d1bea-118">Сортирует результаты запроса по возрастанию или убыванию на основе функции сравнения по умолчанию для соответствующего типа элемента.</span><span class="sxs-lookup"><span data-stu-id="d1bea-118">Sorts query results in ascending or descending order based on the default comparer for the element type.</span></span>|
|[<span data-ttu-id="d1bea-119">join</span><span class="sxs-lookup"><span data-stu-id="d1bea-119">join</span></span>](join-clause.md)|<span data-ttu-id="d1bea-120">Соединяет два источника данных посредством сравнения на равенство между двумя заданными критериями сопоставления.</span><span class="sxs-lookup"><span data-stu-id="d1bea-120">Joins two data sources based on an equality comparison between two specified matching criteria.</span></span>|
|[<span data-ttu-id="d1bea-121">let</span><span class="sxs-lookup"><span data-stu-id="d1bea-121">let</span></span>](let-clause.md)|<span data-ttu-id="d1bea-122">Предоставляет переменную диапазона для хранения результатов выражения, вложенного в выражение запроса.</span><span class="sxs-lookup"><span data-stu-id="d1bea-122">Introduces a range variable to store sub-expression results in a query expression.</span></span>|
|[<span data-ttu-id="d1bea-123">in</span><span class="sxs-lookup"><span data-stu-id="d1bea-123">in</span></span>](in.md)|<span data-ttu-id="d1bea-124">Контекстное ключевое слово в предложении [join](join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="d1bea-124">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="d1bea-125">on</span><span class="sxs-lookup"><span data-stu-id="d1bea-125">on</span></span>](on.md)|<span data-ttu-id="d1bea-126">Контекстное ключевое слово в предложении [join](join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="d1bea-126">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="d1bea-127">equals</span><span class="sxs-lookup"><span data-stu-id="d1bea-127">equals</span></span>](equals.md)|<span data-ttu-id="d1bea-128">Контекстное ключевое слово в предложении [join](join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="d1bea-128">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="d1bea-129">by</span><span class="sxs-lookup"><span data-stu-id="d1bea-129">by</span></span>](by.md)|<span data-ttu-id="d1bea-130">Контекстное ключевое слово в предложении [group](group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="d1bea-130">Contextual keyword in a [group](group-clause.md) clause.</span></span>|
|[<span data-ttu-id="d1bea-131">ascending</span><span class="sxs-lookup"><span data-stu-id="d1bea-131">ascending</span></span>](ascending.md)|<span data-ttu-id="d1bea-132">Контекстное ключевое слово в предложении [orderby](orderby-clause.md).</span><span class="sxs-lookup"><span data-stu-id="d1bea-132">Contextual keyword in an [orderby](orderby-clause.md) clause.</span></span>|
|[<span data-ttu-id="d1bea-133">descending</span><span class="sxs-lookup"><span data-stu-id="d1bea-133">descending</span></span>](descending.md)|<span data-ttu-id="d1bea-134">Контекстное ключевое слово в предложении [orderby](orderby-clause.md).</span><span class="sxs-lookup"><span data-stu-id="d1bea-134">Contextual keyword in an [orderby](orderby-clause.md) clause.</span></span>|

## <a name="see-also"></a><span data-ttu-id="d1bea-135">См. также</span><span class="sxs-lookup"><span data-stu-id="d1bea-135">See also</span></span>

- [<span data-ttu-id="d1bea-136">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="d1bea-136">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="d1bea-137">Встроенный язык запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="d1bea-137">LINQ (Language-Integrated Query)</span></span>](../../programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="d1bea-138">LINQ в C#</span><span class="sxs-lookup"><span data-stu-id="d1bea-138">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="d1bea-139">Приступая к работе с LINQ в C#</span><span class="sxs-lookup"><span data-stu-id="d1bea-139">Getting Started with LINQ in C#</span></span>](/dotnet/csharp/programming-guide/concepts/linq/)
