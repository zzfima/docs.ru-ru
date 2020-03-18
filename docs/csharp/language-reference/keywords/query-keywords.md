---
title: Ключевые слова запроса. Справочник по C#
ms.date: 07/20/2015
helpviewer_keywords:
- query keywords [C#]
- LINQ [C#], query keywords
ms.assetid: 6c9bec16-dbd7-4a7c-a060-fe4600b2021f
ms.openlocfilehash: 01134eda540c5141afbd11b2c89ff779da495a9a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173527"
---
# <a name="query-keywords-c-reference"></a><span data-ttu-id="e9f3a-102">Ключевые слова запроса (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="e9f3a-102">Query keywords (C# Reference)</span></span>

<span data-ttu-id="e9f3a-103">В этом разделе приводятся контекстные ключевые слова, используемые в выражениях запросов.</span><span class="sxs-lookup"><span data-stu-id="e9f3a-103">This section contains the contextual keywords used in query expressions.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="e9f3a-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="e9f3a-104">In this section</span></span>

|<span data-ttu-id="e9f3a-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="e9f3a-105">Clause</span></span>|<span data-ttu-id="e9f3a-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="e9f3a-106">Description</span></span>|
|------------|-----------------|
|[<span data-ttu-id="e9f3a-107">from</span><span class="sxs-lookup"><span data-stu-id="e9f3a-107">from</span></span>](from-clause.md)|<span data-ttu-id="e9f3a-108">Задает источник данных и переменную диапазона (аналогично переменной итерации).</span><span class="sxs-lookup"><span data-stu-id="e9f3a-108">Specifies a data source and a range variable (similar to an iteration variable).</span></span>|
|[<span data-ttu-id="e9f3a-109">where</span><span class="sxs-lookup"><span data-stu-id="e9f3a-109">where</span></span>](where-clause.md)|<span data-ttu-id="e9f3a-110">Фильтрует элементы источника на основе одного или нескольких логических выражений, разделенных операторами логического И и ИЛИ (`&&` или <code>&#124;&#124;</code>).</span><span class="sxs-lookup"><span data-stu-id="e9f3a-110">Filters source elements based on one or more Boolean expressions separated by logical AND and OR operators ( `&&` or <code>&#124;&#124;</code> ).</span></span>|
|[<span data-ttu-id="e9f3a-111">select</span><span class="sxs-lookup"><span data-stu-id="e9f3a-111">select</span></span>](select-clause.md)|<span data-ttu-id="e9f3a-112">Задает тип и форму, которые будут иметь элементы в возвращаемой последовательности при выполнении запроса.</span><span class="sxs-lookup"><span data-stu-id="e9f3a-112">Specifies the type and shape that the elements in the returned sequence will have when the query is executed.</span></span>|
|[<span data-ttu-id="e9f3a-113">группа</span><span class="sxs-lookup"><span data-stu-id="e9f3a-113">group</span></span>](group-clause.md)|<span data-ttu-id="e9f3a-114">Группирует результаты запроса по заданному значению ключа.</span><span class="sxs-lookup"><span data-stu-id="e9f3a-114">Groups query results according to a specified key value.</span></span>|
|[<span data-ttu-id="e9f3a-115">into</span><span class="sxs-lookup"><span data-stu-id="e9f3a-115">into</span></span>](into.md)|<span data-ttu-id="e9f3a-116">Предоставляет идентификатор, который может использоваться в качестве ссылки на результаты предложения join, group или select.</span><span class="sxs-lookup"><span data-stu-id="e9f3a-116">Provides an identifier that can serve as a reference to the results of a join, group or select clause.</span></span>|
|[<span data-ttu-id="e9f3a-117">OrderBy</span><span class="sxs-lookup"><span data-stu-id="e9f3a-117">orderby</span></span>](orderby-clause.md)|<span data-ttu-id="e9f3a-118">Сортирует результаты запроса по возрастанию или убыванию на основе функции сравнения по умолчанию для соответствующего типа элемента.</span><span class="sxs-lookup"><span data-stu-id="e9f3a-118">Sorts query results in ascending or descending order based on the default comparer for the element type.</span></span>|
|[<span data-ttu-id="e9f3a-119">join</span><span class="sxs-lookup"><span data-stu-id="e9f3a-119">join</span></span>](join-clause.md)|<span data-ttu-id="e9f3a-120">Соединяет два источника данных посредством сравнения на равенство между двумя заданными критериями сопоставления.</span><span class="sxs-lookup"><span data-stu-id="e9f3a-120">Joins two data sources based on an equality comparison between two specified matching criteria.</span></span>|
|[<span data-ttu-id="e9f3a-121">let</span><span class="sxs-lookup"><span data-stu-id="e9f3a-121">let</span></span>](let-clause.md)|<span data-ttu-id="e9f3a-122">Предоставляет переменную диапазона для хранения результатов выражения, вложенного в выражение запроса.</span><span class="sxs-lookup"><span data-stu-id="e9f3a-122">Introduces a range variable to store sub-expression results in a query expression.</span></span>|
|[<span data-ttu-id="e9f3a-123">in</span><span class="sxs-lookup"><span data-stu-id="e9f3a-123">in</span></span>](in.md)|<span data-ttu-id="e9f3a-124">Контекстное ключевое слово в предложении [join](join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="e9f3a-124">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="e9f3a-125">on</span><span class="sxs-lookup"><span data-stu-id="e9f3a-125">on</span></span>](on.md)|<span data-ttu-id="e9f3a-126">Контекстное ключевое слово в предложении [join](join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="e9f3a-126">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="e9f3a-127">equals</span><span class="sxs-lookup"><span data-stu-id="e9f3a-127">equals</span></span>](equals.md)|<span data-ttu-id="e9f3a-128">Контекстное ключевое слово в предложении [join](join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="e9f3a-128">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="e9f3a-129">by</span><span class="sxs-lookup"><span data-stu-id="e9f3a-129">by</span></span>](by.md)|<span data-ttu-id="e9f3a-130">Контекстное ключевое слово в предложении [group](group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="e9f3a-130">Contextual keyword in a [group](group-clause.md) clause.</span></span>|
|[<span data-ttu-id="e9f3a-131">ascending</span><span class="sxs-lookup"><span data-stu-id="e9f3a-131">ascending</span></span>](ascending.md)|<span data-ttu-id="e9f3a-132">Контекстное ключевое слово в предложении [orderby](orderby-clause.md).</span><span class="sxs-lookup"><span data-stu-id="e9f3a-132">Contextual keyword in an [orderby](orderby-clause.md) clause.</span></span>|
|[<span data-ttu-id="e9f3a-133">descending</span><span class="sxs-lookup"><span data-stu-id="e9f3a-133">descending</span></span>](descending.md)|<span data-ttu-id="e9f3a-134">Контекстное ключевое слово в предложении [orderby](orderby-clause.md).</span><span class="sxs-lookup"><span data-stu-id="e9f3a-134">Contextual keyword in an [orderby](orderby-clause.md) clause.</span></span>|

## <a name="see-also"></a><span data-ttu-id="e9f3a-135">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e9f3a-135">See also</span></span>

- [<span data-ttu-id="e9f3a-136">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="e9f3a-136">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="e9f3a-137">Встроенный язык запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="e9f3a-137">LINQ (Language-Integrated Query)</span></span>](../../programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="e9f3a-138">LINQ в C#</span><span class="sxs-lookup"><span data-stu-id="e9f3a-138">LINQ in C#</span></span>](../../linq/index.md)
