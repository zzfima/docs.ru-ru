---
title: "Преобразование типов данных (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 9b0cf1ab-de48-4c6e-9f00-05b40fade46e
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 948779e1648291b00a68bfd83d57750d48a9a6d8
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="converting-data-types-visual-basic"></a><span data-ttu-id="67737-102">Преобразование типов данных (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67737-102">Converting Data Types (Visual Basic)</span></span>
<span data-ttu-id="67737-103">Методы преобразования изменяют тип входных объектов.</span><span class="sxs-lookup"><span data-stu-id="67737-103">Conversion methods change the type of input objects.</span></span>  
  
 <span data-ttu-id="67737-104">Операции преобразования в запросах LINQ полезны для различных приложений.</span><span class="sxs-lookup"><span data-stu-id="67737-104">Conversion operations in LINQ queries are useful in a variety of applications.</span></span> <span data-ttu-id="67737-105">Ниже приведены некоторые примеры:</span><span class="sxs-lookup"><span data-stu-id="67737-105">Following are some examples:</span></span>  
  
-   <span data-ttu-id="67737-106"><xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName>Метод может использоваться для скрытия пользовательскую реализацию стандартного оператора запроса типа.</xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="67737-106">The <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName> method can be used to hide a type's custom implementation of a standard query operator.</span></span>  
  
-   <span data-ttu-id="67737-107"><xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName>Метод может использоваться для включения непараметризованным коллекциям для запросов LINQ.</xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="67737-107">The <xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName> method can be used to enable non-parameterized collections for LINQ querying.</span></span>  
  
-   <span data-ttu-id="67737-108"><xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName>, И <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName>методы можно использовать для принудительного немедленного выполнения запроса вместо откладывания до перечисления запроса.</xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName> </xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName> </xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName> </xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="67737-108">The <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName>, and <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName> methods can be used to force immediate query execution instead of deferring it until the query is enumerated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="67737-109">Методы</span><span class="sxs-lookup"><span data-stu-id="67737-109">Methods</span></span>  
 <span data-ttu-id="67737-110">В следующей таблице перечислены методы стандартных операторов запросов, выполняющие преобразование типов данных.</span><span class="sxs-lookup"><span data-stu-id="67737-110">The following table lists the standard query operator methods that perform data-type conversions.</span></span>  
  
 <span data-ttu-id="67737-111">Методы преобразования в этой таблице, имена которых начинаются с «As», изменяют статический тип исходной коллекции, но не перечислить.</span><span class="sxs-lookup"><span data-stu-id="67737-111">The conversion methods in this table whose names start with "As" change the static type of the source collection but do not enumerate it.</span></span> <span data-ttu-id="67737-112">Методы, имена которых начинаются с «To», перечисляют исходную коллекцию и помещают элементы в коллекции, соответствующий тип.</span><span class="sxs-lookup"><span data-stu-id="67737-112">The methods whose names start with "To" enumerate the source collection and put the items into the corresponding collection type.</span></span>  
  
|<span data-ttu-id="67737-113">Имя метода</span><span class="sxs-lookup"><span data-stu-id="67737-113">Method Name</span></span>|<span data-ttu-id="67737-114">Описание</span><span class="sxs-lookup"><span data-stu-id="67737-114">Description</span></span>|<span data-ttu-id="67737-115">Синтаксис выражения запроса для Visual Basic</span><span class="sxs-lookup"><span data-stu-id="67737-115">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="67737-116">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="67737-116">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="67737-117">AsEnumerable</span><span class="sxs-lookup"><span data-stu-id="67737-117">AsEnumerable</span></span>|<span data-ttu-id="67737-118">Возвращает входные данные, типизированного как <xref:System.Collections.Generic.IEnumerable%601>.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="67737-118">Returns the input typed as <xref:System.Collections.Generic.IEnumerable%601>.</span></span>|<span data-ttu-id="67737-119">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="67737-119">Not applicable.</span></span>|<span data-ttu-id="67737-120"><xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName></xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="67737-120"><xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="67737-121">AsQueryable</span><span class="sxs-lookup"><span data-stu-id="67737-121">AsQueryable</span></span>|<span data-ttu-id="67737-122">Преобразует (универсальный) <xref:System.Collections.IEnumerable>для <xref:System.Linq.IQueryable>.</xref:System.Linq.IQueryable> (универсальный)</xref:System.Collections.IEnumerable></span><span class="sxs-lookup"><span data-stu-id="67737-122">Converts a (generic) <xref:System.Collections.IEnumerable> to a (generic) <xref:System.Linq.IQueryable>.</span></span>|<span data-ttu-id="67737-123">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="67737-123">Not applicable.</span></span>|<span data-ttu-id="67737-124"><xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=fullName></xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="67737-124"><xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="67737-125">Cast</span><span class="sxs-lookup"><span data-stu-id="67737-125">Cast</span></span>|<span data-ttu-id="67737-126">Приводит элементы коллекции в указанный тип.</span><span class="sxs-lookup"><span data-stu-id="67737-126">Casts the elements of a collection to a specified type.</span></span>|`From … As …`|<span data-ttu-id="67737-127"><xref:System.Linq.Enumerable.Cast%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Cast%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="67737-127"><xref:System.Linq.Enumerable.Cast%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="67737-128"><xref:System.Linq.Queryable.Cast%2A?displayProperty=fullName></xref:System.Linq.Queryable.Cast%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="67737-128"><xref:System.Linq.Queryable.Cast%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="67737-129">OfType</span><span class="sxs-lookup"><span data-stu-id="67737-129">OfType</span></span>|<span data-ttu-id="67737-130">Фильтрует значения в зависимости от их возможности приведения к указанному типу.</span><span class="sxs-lookup"><span data-stu-id="67737-130">Filters values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="67737-131">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="67737-131">Not applicable.</span></span>|<span data-ttu-id="67737-132"><xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="67737-132"><xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="67737-133"><xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName></xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="67737-133"><xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="67737-134">ToArray</span><span class="sxs-lookup"><span data-stu-id="67737-134">ToArray</span></span>|<span data-ttu-id="67737-135">Преобразует коллекцию в массив.</span><span class="sxs-lookup"><span data-stu-id="67737-135">Converts a collection to an array.</span></span> <span data-ttu-id="67737-136">Этот метод вызывает выполнение запроса.</span><span class="sxs-lookup"><span data-stu-id="67737-136">This method forces query execution.</span></span>|<span data-ttu-id="67737-137">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="67737-137">Not applicable.</span></span>|<span data-ttu-id="67737-138"><xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="67737-138"><xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="67737-139">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="67737-139">ToDictionary</span></span>|<span data-ttu-id="67737-140">Помещает элементы в <xref:System.Collections.Generic.Dictionary%602>на основании функции выбора ключа.</xref:System.Collections.Generic.Dictionary%602></span><span class="sxs-lookup"><span data-stu-id="67737-140">Puts elements into a <xref:System.Collections.Generic.Dictionary%602> based on a key selector function.</span></span> <span data-ttu-id="67737-141">Этот метод вызывает выполнение запроса.</span><span class="sxs-lookup"><span data-stu-id="67737-141">This method forces query execution.</span></span>|<span data-ttu-id="67737-142">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="67737-142">Not applicable.</span></span>|<span data-ttu-id="67737-143"><xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="67737-143"><xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="67737-144">ToList</span><span class="sxs-lookup"><span data-stu-id="67737-144">ToList</span></span>|<span data-ttu-id="67737-145">Преобразует коллекцию <xref:System.Collections.Generic.List%601>.</xref:System.Collections.Generic.List%601></span><span class="sxs-lookup"><span data-stu-id="67737-145">Converts a collection to a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="67737-146">Этот метод вызывает выполнение запроса.</span><span class="sxs-lookup"><span data-stu-id="67737-146">This method forces query execution.</span></span>|<span data-ttu-id="67737-147">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="67737-147">Not applicable.</span></span>|<span data-ttu-id="67737-148"><xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="67737-148"><xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="67737-149">ToLookup</span><span class="sxs-lookup"><span data-stu-id="67737-149">ToLookup</span></span>|<span data-ttu-id="67737-150">Помещает элементы в <xref:System.Linq.Lookup%602>(словарь "один ко многим") на основании функции выбора ключа.</xref:System.Linq.Lookup%602></span><span class="sxs-lookup"><span data-stu-id="67737-150">Puts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span> <span data-ttu-id="67737-151">Этот метод вызывает выполнение запроса.</span><span class="sxs-lookup"><span data-stu-id="67737-151">This method forces query execution.</span></span>|<span data-ttu-id="67737-152">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="67737-152">Not applicable.</span></span>|<span data-ttu-id="67737-153"><xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="67737-153"><xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName></span></span>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="67737-154">Пример синтаксиса выражения запроса</span><span class="sxs-lookup"><span data-stu-id="67737-154">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="67737-155">В следующем примере кода `From As` предложение для приведения типа к подтипу перед доступом к члену, доступному только для подтипа.</span><span class="sxs-lookup"><span data-stu-id="67737-155">The following code example uses the `From As` clause to cast a type to a subtype before accessing a member that is available only on the subtype.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="67737-156">См. также</span><span class="sxs-lookup"><span data-stu-id="67737-156">See Also</span></span>  
 <span data-ttu-id="67737-157"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="67737-157"><xref:System.Linq></span></span>   
<span data-ttu-id="67737-158"> [Общие сведения о стандартных операторах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="67737-158"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="67737-159"> [Предложение FROM](../../../../visual-basic/language-reference/queries/from-clause.md) </span><span class="sxs-lookup"><span data-stu-id="67737-159"> [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md) </span></span>  
<span data-ttu-id="67737-160"> [Практическое руководство: запроса к ArrayList с помощью LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)</span><span class="sxs-lookup"><span data-stu-id="67737-160"> [How to: Query an ArrayList with LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)</span></span>
