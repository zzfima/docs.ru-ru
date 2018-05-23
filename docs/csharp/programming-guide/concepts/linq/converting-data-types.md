---
title: Преобразование типов данных (C#)
ms.date: 07/20/2015
ms.assetid: 46e5682f-77a1-4302-8f93-a2b53c408808
ms.openlocfilehash: 374ce15b8329c02c6b496a276a40fd9a60596e1f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="converting-data-types-c"></a><span data-ttu-id="81272-102">Преобразование типов данных (C#)</span><span class="sxs-lookup"><span data-stu-id="81272-102">Converting Data Types (C#)</span></span>
<span data-ttu-id="81272-103">Методы преобразования изменяют тип входных объектов.</span><span class="sxs-lookup"><span data-stu-id="81272-103">Conversion methods change the type of input objects.</span></span>  
  
 <span data-ttu-id="81272-104">Операции преобразования в запросах LINQ удобны в различных ситуациях.</span><span class="sxs-lookup"><span data-stu-id="81272-104">Conversion operations in LINQ queries are useful in a variety of applications.</span></span> <span data-ttu-id="81272-105">Ниже приводятся некоторые примеры.</span><span class="sxs-lookup"><span data-stu-id="81272-105">Following are some examples:</span></span>  
  
-   <span data-ttu-id="81272-106">Метод <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> можно использовать, чтобы скрыть настраиваемую реализацию типа стандартного оператора запроса.</span><span class="sxs-lookup"><span data-stu-id="81272-106">The <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> method can be used to hide a type's custom implementation of a standard query operator.</span></span>  
  
-   <span data-ttu-id="81272-107">Метод <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> позволяет использовать непараметризованные коллекции для запросов LINQ.</span><span class="sxs-lookup"><span data-stu-id="81272-107">The <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> method can be used to enable non-parameterized collections for LINQ querying.</span></span>  
  
-   <span data-ttu-id="81272-108">Методы <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> и <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> можно использовать для принудительного немедленного выполнения запроса, не дожидаясь, пока этот запрос будет перечислен.</span><span class="sxs-lookup"><span data-stu-id="81272-108">The <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>, and <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> methods can be used to force immediate query execution instead of deferring it until the query is enumerated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="81272-109">Методы</span><span class="sxs-lookup"><span data-stu-id="81272-109">Methods</span></span>  
 <span data-ttu-id="81272-110">В следующей таблице перечислены методы стандартных операторов запросов, выполняющие преобразование типов данных.</span><span class="sxs-lookup"><span data-stu-id="81272-110">The following table lists the standard query operator methods that perform data-type conversions.</span></span>  
  
 <span data-ttu-id="81272-111">Методы преобразования в этой таблице, имена которых начинаются с "As", изменяют статический тип исходной коллекции, но не выполняют перечисление.</span><span class="sxs-lookup"><span data-stu-id="81272-111">The conversion methods in this table whose names start with "As" change the static type of the source collection but do not enumerate it.</span></span> <span data-ttu-id="81272-112">Методы, имена которых начинаются с "To", перечисляют исходную коллекцию и помещают элементы в соответствующий тип коллекции.</span><span class="sxs-lookup"><span data-stu-id="81272-112">The methods whose names start with "To" enumerate the source collection and put the items into the corresponding collection type.</span></span>  
  
|<span data-ttu-id="81272-113">Имя метода</span><span class="sxs-lookup"><span data-stu-id="81272-113">Method Name</span></span>|<span data-ttu-id="81272-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="81272-114">Description</span></span>|<span data-ttu-id="81272-115">Синтаксис выражения запроса C#</span><span class="sxs-lookup"><span data-stu-id="81272-115">C# Query Expression Syntax</span></span>|<span data-ttu-id="81272-116">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="81272-116">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="81272-117">AsEnumerable</span><span class="sxs-lookup"><span data-stu-id="81272-117">AsEnumerable</span></span>|<span data-ttu-id="81272-118">Возвращает входное значение, типизированное как <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="81272-118">Returns the input typed as <xref:System.Collections.Generic.IEnumerable%601>.</span></span>|<span data-ttu-id="81272-119">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="81272-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="81272-120">AsQueryable</span><span class="sxs-lookup"><span data-stu-id="81272-120">AsQueryable</span></span>|<span data-ttu-id="81272-121">Преобразует <xref:System.Collections.IEnumerable> (универсальный шаблон) в <xref:System.Linq.IQueryable> (универсальный шаблон).</span><span class="sxs-lookup"><span data-stu-id="81272-121">Converts a (generic) <xref:System.Collections.IEnumerable> to a (generic) <xref:System.Linq.IQueryable>.</span></span>|<span data-ttu-id="81272-122">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="81272-122">Not applicable.</span></span>|<xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="81272-123">Cast</span><span class="sxs-lookup"><span data-stu-id="81272-123">Cast</span></span>|<span data-ttu-id="81272-124">Приводит элементы коллекции к указанному типу.</span><span class="sxs-lookup"><span data-stu-id="81272-124">Casts the elements of a collection to a specified type.</span></span>|<span data-ttu-id="81272-125">Используйте явно типизированную переменную диапазона.</span><span class="sxs-lookup"><span data-stu-id="81272-125">Use an explicitly typed range variable.</span></span> <span data-ttu-id="81272-126">Пример:</span><span class="sxs-lookup"><span data-stu-id="81272-126">For example:</span></span><br /><br /> `from string str in words`|<xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Cast%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="81272-127">OfType</span><span class="sxs-lookup"><span data-stu-id="81272-127">OfType</span></span>|<span data-ttu-id="81272-128">Фильтрует значения в зависимости от возможности их приведения к указанному типу.</span><span class="sxs-lookup"><span data-stu-id="81272-128">Filters values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="81272-129">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="81272-129">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="81272-130">ToArray</span><span class="sxs-lookup"><span data-stu-id="81272-130">ToArray</span></span>|<span data-ttu-id="81272-131">Преобразует коллекцию в массив.</span><span class="sxs-lookup"><span data-stu-id="81272-131">Converts a collection to an array.</span></span> <span data-ttu-id="81272-132">Этот метод принудительно выполняет запрос.</span><span class="sxs-lookup"><span data-stu-id="81272-132">This method forces query execution.</span></span>|<span data-ttu-id="81272-133">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="81272-133">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="81272-134">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="81272-134">ToDictionary</span></span>|<span data-ttu-id="81272-135">Помещает элементы в <xref:System.Collections.Generic.Dictionary%602> в зависимости от функции выбора ключа.</span><span class="sxs-lookup"><span data-stu-id="81272-135">Puts elements into a <xref:System.Collections.Generic.Dictionary%602> based on a key selector function.</span></span> <span data-ttu-id="81272-136">Этот метод принудительно выполняет запрос.</span><span class="sxs-lookup"><span data-stu-id="81272-136">This method forces query execution.</span></span>|<span data-ttu-id="81272-137">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="81272-137">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="81272-138">ToList</span><span class="sxs-lookup"><span data-stu-id="81272-138">ToList</span></span>|<span data-ttu-id="81272-139">Преобразует коллекцию в <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="81272-139">Converts a collection to a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="81272-140">Этот метод принудительно выполняет запрос.</span><span class="sxs-lookup"><span data-stu-id="81272-140">This method forces query execution.</span></span>|<span data-ttu-id="81272-141">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="81272-141">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="81272-142">ToLookup</span><span class="sxs-lookup"><span data-stu-id="81272-142">ToLookup</span></span>|<span data-ttu-id="81272-143">Помещает элементы в <xref:System.Linq.Lookup%602> (словарь "один ко многим") в зависимости от функции выбора ключа.</span><span class="sxs-lookup"><span data-stu-id="81272-143">Puts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span> <span data-ttu-id="81272-144">Этот метод принудительно выполняет запрос.</span><span class="sxs-lookup"><span data-stu-id="81272-144">This method forces query execution.</span></span>|<span data-ttu-id="81272-145">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="81272-145">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="81272-146">Пример синтаксиса выражения запроса</span><span class="sxs-lookup"><span data-stu-id="81272-146">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="81272-147">В следующем примере кода явным образом типизированная переменная диапазона используется для приведения типа к подтипу перед доступом к члену, доступному только для подтипа.</span><span class="sxs-lookup"><span data-stu-id="81272-147">The following code example uses an explicitly-typed range variable  to cast a type to a subtype before accessing a member that is available only on the subtype.</span></span>  
  
```csharp  
class Plant  
{  
    public string Name { get; set; }  
}  
  
class CarnivorousPlant : Plant  
{  
    public string TrapType { get; set; }  
}  
  
static void Cast()  
{  
    Plant[] plants = new Plant[] {  
        new CarnivorousPlant { Name = "Venus Fly Trap", TrapType = "Snap Trap" },  
        new CarnivorousPlant { Name = "Pitcher Plant", TrapType = "Pitfall Trap" },  
        new CarnivorousPlant { Name = "Sundew", TrapType = "Flypaper Trap" },  
        new CarnivorousPlant { Name = "Waterwheel Plant", TrapType = "Snap Trap" }  
    };  
  
    var query = from CarnivorousPlant cPlant in plants  
                where cPlant.TrapType == "Snap Trap"  
                select cPlant;  
  
    foreach (Plant plant in query)  
        Console.WriteLine(plant.Name);  
  
    /* This code produces the following output:  
  
        Venus Fly Trap  
        Waterwheel Plant  
    */  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="81272-148">См. также</span><span class="sxs-lookup"><span data-stu-id="81272-148">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="81272-149">Общие сведения о стандартных операторах запроса (C#)</span><span class="sxs-lookup"><span data-stu-id="81272-149">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="81272-150">предложение from</span><span class="sxs-lookup"><span data-stu-id="81272-150">from clause</span></span>](../../../../csharp/language-reference/keywords/from-clause.md)  
 [<span data-ttu-id="81272-151">Выражения запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="81272-151">LINQ Query Expressions</span></span>](../../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [<span data-ttu-id="81272-152">Практическое руководство. Выполнение запроса к ArrayList с помощью LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="81272-152">How to: Query an ArrayList with LINQ (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)
