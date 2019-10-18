---
title: Преобразование типов данных (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 9b0cf1ab-de48-4c6e-9f00-05b40fade46e
ms.openlocfilehash: 744dec0093384a15470186fc09695c17e79468fa
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524233"
---
# <a name="converting-data-types-visual-basic"></a><span data-ttu-id="b3ddb-102">Преобразование типов данных (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b3ddb-102">Converting Data Types (Visual Basic)</span></span>

<span data-ttu-id="b3ddb-103">Методы преобразования изменяют тип входных объектов.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-103">Conversion methods change the type of input objects.</span></span>

 <span data-ttu-id="b3ddb-104">Операции преобразования в запросах LINQ удобны в различных ситуациях.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-104">Conversion operations in LINQ queries are useful in a variety of applications.</span></span> <span data-ttu-id="b3ddb-105">Ниже приведены некоторые примеры.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-105">The following are some examples:</span></span>

- <span data-ttu-id="b3ddb-106">Метод <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> можно использовать, чтобы скрыть настраиваемую реализацию типа стандартного оператора запроса.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-106">The <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> method can be used to hide a type's custom implementation of a standard query operator.</span></span>

- <span data-ttu-id="b3ddb-107">Метод <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> позволяет использовать непараметризованные коллекции для запросов LINQ.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-107">The <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> method can be used to enable non-parameterized collections for LINQ querying.</span></span>

- <span data-ttu-id="b3ddb-108">Методы <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> и <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> можно использовать для принудительного немедленного выполнения запроса, не дожидаясь, пока этот запрос будет перечислен.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-108">The <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>, and <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> methods can be used to force immediate query execution instead of deferring it until the query is enumerated.</span></span>

## <a name="methods"></a><span data-ttu-id="b3ddb-109">Методы</span><span class="sxs-lookup"><span data-stu-id="b3ddb-109">Methods</span></span>

<span data-ttu-id="b3ddb-110">В следующей таблице перечислены методы стандартных операторов запросов, выполняющие преобразование типов данных.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-110">The following table lists the standard query operator methods that perform data-type conversions.</span></span>

<span data-ttu-id="b3ddb-111">Методы преобразования в этой таблице, имена которых начинаются с "As", изменяют статический тип исходной коллекции, но не выполняют перечисление.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-111">The conversion methods in this table whose names start with "As" change the static type of the source collection but do not enumerate it.</span></span> <span data-ttu-id="b3ddb-112">Методы, имена которых начинаются с "To", перечисляют исходную коллекцию и помещают элементы в соответствующий тип коллекции.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-112">The methods whose names start with "To" enumerate the source collection and put the items into the corresponding collection type.</span></span>

|<span data-ttu-id="b3ddb-113">Имя метода</span><span class="sxs-lookup"><span data-stu-id="b3ddb-113">Method Name</span></span>|<span data-ttu-id="b3ddb-114">Описание</span><span class="sxs-lookup"><span data-stu-id="b3ddb-114">Description</span></span>|<span data-ttu-id="b3ddb-115">Синтаксис выражения запроса Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b3ddb-115">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="b3ddb-116">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="b3ddb-116">More Information</span></span>|
|-----------------|-----------------|------------------------------------------|----------------------|
|<span data-ttu-id="b3ddb-117">AsEnumerable</span><span class="sxs-lookup"><span data-stu-id="b3ddb-117">AsEnumerable</span></span>|<span data-ttu-id="b3ddb-118">Возвращает входное значение, типизированное как <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-118">Returns the input typed as <xref:System.Collections.Generic.IEnumerable%601>.</span></span>|<span data-ttu-id="b3ddb-119">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType>|
|<span data-ttu-id="b3ddb-120">AsQueryable</span><span class="sxs-lookup"><span data-stu-id="b3ddb-120">AsQueryable</span></span>|<span data-ttu-id="b3ddb-121">Преобразует <xref:System.Collections.IEnumerable> (универсальный шаблон) в <xref:System.Linq.IQueryable> (универсальный шаблон).</span><span class="sxs-lookup"><span data-stu-id="b3ddb-121">Converts a (generic) <xref:System.Collections.IEnumerable> to a (generic) <xref:System.Linq.IQueryable>.</span></span>|<span data-ttu-id="b3ddb-122">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-122">Not applicable.</span></span>|<xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=nameWithType>|
|<span data-ttu-id="b3ddb-123">Cast</span><span class="sxs-lookup"><span data-stu-id="b3ddb-123">Cast</span></span>|<span data-ttu-id="b3ddb-124">Приводит элементы коллекции к указанному типу.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-124">Casts the elements of a collection to a specified type.</span></span>|`From … As …`|<xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Cast%2A?displayProperty=nameWithType>|
|<span data-ttu-id="b3ddb-125">OfType</span><span class="sxs-lookup"><span data-stu-id="b3ddb-125">OfType</span></span>|<span data-ttu-id="b3ddb-126">Фильтрует значения в зависимости от возможности их приведения к указанному типу.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-126">Filters values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="b3ddb-127">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-127">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|
|<span data-ttu-id="b3ddb-128">ToArray</span><span class="sxs-lookup"><span data-stu-id="b3ddb-128">ToArray</span></span>|<span data-ttu-id="b3ddb-129">Преобразует коллекцию в массив.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-129">Converts a collection to an array.</span></span> <span data-ttu-id="b3ddb-130">Этот метод принудительно выполняет запрос.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-130">This method forces query execution.</span></span>|<span data-ttu-id="b3ddb-131">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-131">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>|
|<span data-ttu-id="b3ddb-132">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="b3ddb-132">ToDictionary</span></span>|<span data-ttu-id="b3ddb-133">Помещает элементы в <xref:System.Collections.Generic.Dictionary%602> в зависимости от функции выбора ключа.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-133">Puts elements into a <xref:System.Collections.Generic.Dictionary%602> based on a key selector function.</span></span> <span data-ttu-id="b3ddb-134">Этот метод принудительно выполняет запрос.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-134">This method forces query execution.</span></span>|<span data-ttu-id="b3ddb-135">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-135">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>|
|<span data-ttu-id="b3ddb-136">ToList</span><span class="sxs-lookup"><span data-stu-id="b3ddb-136">ToList</span></span>|<span data-ttu-id="b3ddb-137">Преобразует коллекцию в <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-137">Converts a collection to a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="b3ddb-138">Этот метод принудительно выполняет запрос.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-138">This method forces query execution.</span></span>|<span data-ttu-id="b3ddb-139">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-139">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>|
|<span data-ttu-id="b3ddb-140">ToLookup</span><span class="sxs-lookup"><span data-stu-id="b3ddb-140">ToLookup</span></span>|<span data-ttu-id="b3ddb-141">Помещает элементы в <xref:System.Linq.Lookup%602> (словарь "один ко многим") в зависимости от функции выбора ключа.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-141">Puts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span> <span data-ttu-id="b3ddb-142">Этот метод принудительно выполняет запрос.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-142">This method forces query execution.</span></span>|<span data-ttu-id="b3ddb-143">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-143">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-example"></a><span data-ttu-id="b3ddb-144">Пример синтаксиса выражения запроса</span><span class="sxs-lookup"><span data-stu-id="b3ddb-144">Query Expression Syntax Example</span></span>

<span data-ttu-id="b3ddb-145">В следующем примере кода используется предложение `From As` для приведения типа к подтипу перед доступом к элементу, доступному только для подтипа.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-145">The following code example uses the `From As` clause to cast a type to a subtype before accessing a member that is available only on the subtype.</span></span>

```vb
Class Plant
    Public Property Name As String
End Class

Class CarnivorousPlant
    Inherits Plant
    Public Property TrapType As String
End Class

Sub Cast()

    Dim plants() As Plant = {
        New CarnivorousPlant With {.Name = "Venus Fly Trap", .TrapType = "Snap Trap"},
        New CarnivorousPlant With {.Name = "Pitcher Plant", .TrapType = "Pitfall Trap"},
        New CarnivorousPlant With {.Name = "Sundew", .TrapType = "Flypaper Trap"},
        New CarnivorousPlant With {.Name = "Waterwheel Plant", .TrapType = "Snap Trap"}}

    Dim query = From plant As CarnivorousPlant In plants
                Where plant.TrapType = "Snap Trap"
                Select plant

    Dim sb As New System.Text.StringBuilder()
    For Each plant In query
        sb.AppendLine(plant.Name)
    Next

    ' Display the results.
    MsgBox(sb.ToString())

    ' This code produces the following output:

    ' Venus Fly Trap
    ' Waterwheel Plant

End Sub
```

## <a name="see-also"></a><span data-ttu-id="b3ddb-146">См. также</span><span class="sxs-lookup"><span data-stu-id="b3ddb-146">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="b3ddb-147">Общие сведения о стандартных операторах запроса (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b3ddb-147">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="b3ddb-148">Предложение From</span><span class="sxs-lookup"><span data-stu-id="b3ddb-148">From Clause</span></span>](../../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="b3ddb-149">Как выполнить запрос к ArrayList с помощью LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b3ddb-149">How to: Query an ArrayList with LINQ (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)
