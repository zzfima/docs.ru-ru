---
title: Ключевые слова запроса (Справочник по C#)
ms.date: 07/20/2015
helpviewer_keywords:
- query keywords [C#]
- LINQ [C#], query keywords
ms.assetid: 6c9bec16-dbd7-4a7c-a060-fe4600b2021f
ms.openlocfilehash: 9ec163e1de018bd87348a5b39a1f34654d7d6d84
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2018
ms.locfileid: "45624766"
---
# <a name="query-keywords-c-reference"></a><span data-ttu-id="18159-102">Ключевые слова запроса (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="18159-102">Query keywords (C# Reference)</span></span>

<span data-ttu-id="18159-103">В этом разделе приводятся контекстные ключевые слова, используемые в выражениях запросов.</span><span class="sxs-lookup"><span data-stu-id="18159-103">This section contains the contextual keywords used in query expressions.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="18159-104">Содержание раздела</span><span class="sxs-lookup"><span data-stu-id="18159-104">In this section</span></span>

|<span data-ttu-id="18159-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="18159-105">Clause</span></span>|<span data-ttu-id="18159-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="18159-106">Description</span></span>|
|------------|-----------------|
|[<span data-ttu-id="18159-107">from</span><span class="sxs-lookup"><span data-stu-id="18159-107">from</span></span>](from-clause.md)|<span data-ttu-id="18159-108">Задает источник данных и переменную диапазона (аналогично переменной итерации).</span><span class="sxs-lookup"><span data-stu-id="18159-108">Specifies a data source and a range variable (similar to an iteration variable).</span></span>|
|[<span data-ttu-id="18159-109">where</span><span class="sxs-lookup"><span data-stu-id="18159-109">where</span></span>](where-clause.md)|<span data-ttu-id="18159-110">Фильтрует элементы источника на основе одного или нескольких логических выражений, разделенных операторами логического И и ИЛИ (`&&` или <code>&#124;&#124;</code>).</span><span class="sxs-lookup"><span data-stu-id="18159-110">Filters source elements based on one or more Boolean expressions separated by logical AND and OR operators ( `&&` or <code>&#124;&#124;</code> ).</span></span>|
|[<span data-ttu-id="18159-111">select</span><span class="sxs-lookup"><span data-stu-id="18159-111">select</span></span>](select-clause.md)|<span data-ttu-id="18159-112">Задает тип и форму, которые будут иметь элементы в возвращаемой последовательности при выполнении запроса.</span><span class="sxs-lookup"><span data-stu-id="18159-112">Specifies the type and shape that the elements in the returned sequence will have when the query is executed.</span></span>|
|[<span data-ttu-id="18159-113">group</span><span class="sxs-lookup"><span data-stu-id="18159-113">group</span></span>](group-clause.md)|<span data-ttu-id="18159-114">Группирует результаты запроса по заданному значению ключа.</span><span class="sxs-lookup"><span data-stu-id="18159-114">Groups query results according to a specified key value.</span></span>|
|[<span data-ttu-id="18159-115">into</span><span class="sxs-lookup"><span data-stu-id="18159-115">into</span></span>](into.md)|<span data-ttu-id="18159-116">Предоставляет идентификатор, который может использоваться в качестве ссылки на результаты предложения join, group или select.</span><span class="sxs-lookup"><span data-stu-id="18159-116">Provides an identifier that can serve as a reference to the results of a join, group or select clause.</span></span>|
|[<span data-ttu-id="18159-117">orderby</span><span class="sxs-lookup"><span data-stu-id="18159-117">orderby</span></span>](orderby-clause.md)|<span data-ttu-id="18159-118">Сортирует результаты запроса по возрастанию или убыванию на основе функции сравнения по умолчанию для соответствующего типа элемента.</span><span class="sxs-lookup"><span data-stu-id="18159-118">Sorts query results in ascending or descending order based on the default comparer for the element type.</span></span>|
|[<span data-ttu-id="18159-119">join</span><span class="sxs-lookup"><span data-stu-id="18159-119">join</span></span>](join-clause.md)|<span data-ttu-id="18159-120">Соединяет два источника данных посредством сравнения на равенство между двумя заданными критериями сопоставления.</span><span class="sxs-lookup"><span data-stu-id="18159-120">Joins two data sources based on an equality comparison between two specified matching criteria.</span></span>|
|[<span data-ttu-id="18159-121">let</span><span class="sxs-lookup"><span data-stu-id="18159-121">let</span></span>](let-clause.md)|<span data-ttu-id="18159-122">Предоставляет переменную диапазона для хранения результатов выражения, вложенного в выражение запроса.</span><span class="sxs-lookup"><span data-stu-id="18159-122">Introduces a range variable to store sub-expression results in a query expression.</span></span>|
|[<span data-ttu-id="18159-123">in</span><span class="sxs-lookup"><span data-stu-id="18159-123">in</span></span>](in.md)|<span data-ttu-id="18159-124">Контекстное ключевое слово в предложении [join](join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="18159-124">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="18159-125">on</span><span class="sxs-lookup"><span data-stu-id="18159-125">on</span></span>](on.md)|<span data-ttu-id="18159-126">Контекстное ключевое слово в предложении [join](join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="18159-126">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="18159-127">equals</span><span class="sxs-lookup"><span data-stu-id="18159-127">equals</span></span>](equals.md)|<span data-ttu-id="18159-128">Контекстное ключевое слово в предложении [join](join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="18159-128">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="18159-129">by</span><span class="sxs-lookup"><span data-stu-id="18159-129">by</span></span>](by.md)|<span data-ttu-id="18159-130">Контекстное ключевое слово в предложении [group](group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="18159-130">Contextual keyword in a [group](group-clause.md) clause.</span></span>|
|[<span data-ttu-id="18159-131">ascending</span><span class="sxs-lookup"><span data-stu-id="18159-131">ascending</span></span>](ascending.md)|<span data-ttu-id="18159-132">Контекстное ключевое слово в предложении [orderby](orderby-clause.md).</span><span class="sxs-lookup"><span data-stu-id="18159-132">Contextual keyword in an [orderby](orderby-clause.md) clause.</span></span>|
|[<span data-ttu-id="18159-133">descending</span><span class="sxs-lookup"><span data-stu-id="18159-133">descending</span></span>](descending.md)|<span data-ttu-id="18159-134">Контекстное ключевое слово в предложении [orderby](orderby-clause.md).</span><span class="sxs-lookup"><span data-stu-id="18159-134">Contextual keyword in an [orderby](orderby-clause.md) clause.</span></span>|

## <a name="see-also"></a><span data-ttu-id="18159-135">См. также</span><span class="sxs-lookup"><span data-stu-id="18159-135">See also</span></span>

- [<span data-ttu-id="18159-136">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="18159-136">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="18159-137">Встроенный язык запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="18159-137">LINQ (Language-Integrated Query)</span></span>](../../programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="18159-138">Выражения запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="18159-138">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)
- [<span data-ttu-id="18159-139">Приступая к работе с LINQ в C#</span><span class="sxs-lookup"><span data-stu-id="18159-139">Getting Started with LINQ in C#</span></span>](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)