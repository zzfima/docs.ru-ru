---
title: Преобразование типов данных (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 9b0cf1ab-de48-4c6e-9f00-05b40fade46e
ms.openlocfilehash: ad9594cabe0e2382ae4e19f2541eec4aa74ccd75
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58837056"
---
# <a name="converting-data-types-visual-basic"></a><span data-ttu-id="21023-102">Преобразование типов данных (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="21023-102">Converting Data Types (Visual Basic)</span></span>
<span data-ttu-id="21023-103">Методы преобразования изменяют тип входных объектов.</span><span class="sxs-lookup"><span data-stu-id="21023-103">Conversion methods change the type of input objects.</span></span>  
  
 <span data-ttu-id="21023-104">Операции преобразования в запросах LINQ удобны в различных ситуациях.</span><span class="sxs-lookup"><span data-stu-id="21023-104">Conversion operations in LINQ queries are useful in a variety of applications.</span></span> <span data-ttu-id="21023-105">Ниже приводятся некоторые примеры.</span><span class="sxs-lookup"><span data-stu-id="21023-105">Following are some examples:</span></span>  
  
-   <span data-ttu-id="21023-106">Метод <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> можно использовать, чтобы скрыть настраиваемую реализацию типа стандартного оператора запроса.</span><span class="sxs-lookup"><span data-stu-id="21023-106">The <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> method can be used to hide a type's custom implementation of a standard query operator.</span></span>  
  
-   <span data-ttu-id="21023-107">Метод <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> позволяет использовать непараметризованные коллекции для запросов LINQ.</span><span class="sxs-lookup"><span data-stu-id="21023-107">The <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> method can be used to enable non-parameterized collections for LINQ querying.</span></span>  
  
-   <span data-ttu-id="21023-108">Методы <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> и <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> можно использовать для принудительного немедленного выполнения запроса, не дожидаясь, пока этот запрос будет перечислен.</span><span class="sxs-lookup"><span data-stu-id="21023-108">The <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>, and <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> methods can be used to force immediate query execution instead of deferring it until the query is enumerated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="21023-109">Методы</span><span class="sxs-lookup"><span data-stu-id="21023-109">Methods</span></span>  
 <span data-ttu-id="21023-110">В следующей таблице перечислены методы стандартных операторов запросов, выполняющие преобразование типов данных.</span><span class="sxs-lookup"><span data-stu-id="21023-110">The following table lists the standard query operator methods that perform data-type conversions.</span></span>  
  
 <span data-ttu-id="21023-111">Методы преобразования в этой таблице, имена которых начинаются с "As", изменяют статический тип исходной коллекции, но не выполняют перечисление.</span><span class="sxs-lookup"><span data-stu-id="21023-111">The conversion methods in this table whose names start with "As" change the static type of the source collection but do not enumerate it.</span></span> <span data-ttu-id="21023-112">Методы, имена которых начинаются с "To", перечисляют исходную коллекцию и помещают элементы в соответствующий тип коллекции.</span><span class="sxs-lookup"><span data-stu-id="21023-112">The methods whose names start with "To" enumerate the source collection and put the items into the corresponding collection type.</span></span>  
  
|<span data-ttu-id="21023-113">Имя метода</span><span class="sxs-lookup"><span data-stu-id="21023-113">Method Name</span></span>|<span data-ttu-id="21023-114">Описание</span><span class="sxs-lookup"><span data-stu-id="21023-114">Description</span></span>|<span data-ttu-id="21023-115">Синтаксис выражений запросов Visual Basic</span><span class="sxs-lookup"><span data-stu-id="21023-115">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="21023-116">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="21023-116">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="21023-117">AsEnumerable</span><span class="sxs-lookup"><span data-stu-id="21023-117">AsEnumerable</span></span>|<span data-ttu-id="21023-118">Возвращает входное значение, типизированное как <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="21023-118">Returns the input typed as <xref:System.Collections.Generic.IEnumerable%601>.</span></span>|<span data-ttu-id="21023-119">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="21023-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="21023-120">AsQueryable</span><span class="sxs-lookup"><span data-stu-id="21023-120">AsQueryable</span></span>|<span data-ttu-id="21023-121">Преобразует <xref:System.Collections.IEnumerable> (универсальный шаблон) в <xref:System.Linq.IQueryable> (универсальный шаблон).</span><span class="sxs-lookup"><span data-stu-id="21023-121">Converts a (generic) <xref:System.Collections.IEnumerable> to a (generic) <xref:System.Linq.IQueryable>.</span></span>|<span data-ttu-id="21023-122">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="21023-122">Not applicable.</span></span>|<xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="21023-123">Cast</span><span class="sxs-lookup"><span data-stu-id="21023-123">Cast</span></span>|<span data-ttu-id="21023-124">Приводит элементы коллекции к указанному типу.</span><span class="sxs-lookup"><span data-stu-id="21023-124">Casts the elements of a collection to a specified type.</span></span>|`From … As …`|<xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Cast%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="21023-125">OfType</span><span class="sxs-lookup"><span data-stu-id="21023-125">OfType</span></span>|<span data-ttu-id="21023-126">Фильтрует значения в зависимости от возможности их приведения к указанному типу.</span><span class="sxs-lookup"><span data-stu-id="21023-126">Filters values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="21023-127">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="21023-127">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="21023-128">ToArray</span><span class="sxs-lookup"><span data-stu-id="21023-128">ToArray</span></span>|<span data-ttu-id="21023-129">Преобразует коллекцию в массив.</span><span class="sxs-lookup"><span data-stu-id="21023-129">Converts a collection to an array.</span></span> <span data-ttu-id="21023-130">Этот метод принудительно выполняет запрос.</span><span class="sxs-lookup"><span data-stu-id="21023-130">This method forces query execution.</span></span>|<span data-ttu-id="21023-131">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="21023-131">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="21023-132">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="21023-132">ToDictionary</span></span>|<span data-ttu-id="21023-133">Помещает элементы в <xref:System.Collections.Generic.Dictionary%602> в зависимости от функции выбора ключа.</span><span class="sxs-lookup"><span data-stu-id="21023-133">Puts elements into a <xref:System.Collections.Generic.Dictionary%602> based on a key selector function.</span></span> <span data-ttu-id="21023-134">Этот метод принудительно выполняет запрос.</span><span class="sxs-lookup"><span data-stu-id="21023-134">This method forces query execution.</span></span>|<span data-ttu-id="21023-135">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="21023-135">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="21023-136">ToList</span><span class="sxs-lookup"><span data-stu-id="21023-136">ToList</span></span>|<span data-ttu-id="21023-137">Преобразует коллекцию в <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="21023-137">Converts a collection to a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="21023-138">Этот метод принудительно выполняет запрос.</span><span class="sxs-lookup"><span data-stu-id="21023-138">This method forces query execution.</span></span>|<span data-ttu-id="21023-139">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="21023-139">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="21023-140">ToLookup</span><span class="sxs-lookup"><span data-stu-id="21023-140">ToLookup</span></span>|<span data-ttu-id="21023-141">Помещает элементы в <xref:System.Linq.Lookup%602> (словарь "один ко многим") в зависимости от функции выбора ключа.</span><span class="sxs-lookup"><span data-stu-id="21023-141">Puts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span> <span data-ttu-id="21023-142">Этот метод принудительно выполняет запрос.</span><span class="sxs-lookup"><span data-stu-id="21023-142">This method forces query execution.</span></span>|<span data-ttu-id="21023-143">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="21023-143">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="21023-144">Пример синтаксиса выражения запроса</span><span class="sxs-lookup"><span data-stu-id="21023-144">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="21023-145">В следующем примере кода используется `From As` предложение для приведения типа к подтипу перед доступом к члену, который доступен только для подтипа.</span><span class="sxs-lookup"><span data-stu-id="21023-145">The following code example uses the `From As` clause to cast a type to a subtype before accessing a member that is available only on the subtype.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="21023-146">См. также</span><span class="sxs-lookup"><span data-stu-id="21023-146">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="21023-147">Общие сведения о стандартных операторах запроса (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="21023-147">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="21023-148">Предложение From</span><span class="sxs-lookup"><span data-stu-id="21023-148">From Clause</span></span>](../../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="21023-149">Практическое руководство. Выполнение запроса к ArrayList с помощью LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="21023-149">How to: Query an ArrayList with LINQ (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)
