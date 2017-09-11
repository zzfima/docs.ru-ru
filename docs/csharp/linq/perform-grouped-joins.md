---
title: "Выполнение групповых соединений"
description: "Сведения о выполнении групповых соединений."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 9667daf9-a5fd-4b43-a5c4-a9c2b744000e
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0410c5f673e61f91c00a69cb1659e0d72852f128
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="perform-grouped-joins"></a><span data-ttu-id="a2d49-104">Выполнение групповых соединений</span><span class="sxs-lookup"><span data-stu-id="a2d49-104">Perform grouped joins</span></span>

<span data-ttu-id="a2d49-105">Групповое соединение можно использовать для создания иерархических структур данных.</span><span class="sxs-lookup"><span data-stu-id="a2d49-105">The group join is useful for producing hierarchical data structures.</span></span> <span data-ttu-id="a2d49-106">Каждый элемент из первой коллекции группируется с набором соответствующих элементов из второй коллекции.</span><span class="sxs-lookup"><span data-stu-id="a2d49-106">It pairs each element from the first collection with a set of correlated elements from the second collection.</span></span>  
  
 <span data-ttu-id="a2d49-107">Например, класс или таблица реляционной базы данных под названием `Student` может содержать два поля: `Id` и `Name`.</span><span class="sxs-lookup"><span data-stu-id="a2d49-107">For example, a class or a relational database table named `Student` might contain two fields: `Id` and `Name`.</span></span> <span data-ttu-id="a2d49-108">Второй класс или таблица реляционной базы данных под названием `Course` может содержать два поля: `StudentId` и `CourseTitle`.</span><span class="sxs-lookup"><span data-stu-id="a2d49-108">A second class or relational database table named `Course` might contain two fields: `StudentId` and `CourseTitle`.</span></span> <span data-ttu-id="a2d49-109">Групповое соединение этих двух источников данных, основанное на сравнении `Student.Id` и `Course.StudentId`, приведет к группировке каждого объекта `Student` с коллекцией объектов `Course` (которая может быть пустой).</span><span class="sxs-lookup"><span data-stu-id="a2d49-109">A group join of these two data sources, based on matching `Student.Id` and `Course.StudentId`, would group each `Student` with a collection of `Course` objects (which might be empty).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2d49-110">Каждый элемент первой коллекции отображается в результирующем наборе группового соединения вне зависимости от того, найдены ли соответствующие ему элементы во второй коллекции.</span><span class="sxs-lookup"><span data-stu-id="a2d49-110">Each element of the first collection appears in the result set of a group join regardless of whether correlated elements are found in the second collection.</span></span> <span data-ttu-id="a2d49-111">В случае, если такие элементы не найдены, последовательность соответствующих элементов будет пуста.</span><span class="sxs-lookup"><span data-stu-id="a2d49-111">In the case where no correlated elements are found, the sequence of correlated elements for that element is empty.</span></span> <span data-ttu-id="a2d49-112">Селектор результата имеет доступ к каждому элементу первой коллекции.</span><span class="sxs-lookup"><span data-stu-id="a2d49-112">The result selector therefore has access to every element of the first collection.</span></span> <span data-ttu-id="a2d49-113">При этом следует учесть отличие от селектора результата в негрупповом соединении: в этом случае селектор не имеет доступа к элементам из первой коллекции, для которых нет совпадений во второй коллекции.</span><span class="sxs-lookup"><span data-stu-id="a2d49-113">This differs from the result selector in a non-group join, which cannot access elements from the first collection that have no match in the second collection.</span></span>  
  
 <span data-ttu-id="a2d49-114">В первом примере этого раздела показано, как выполнить групповое соединение.</span><span class="sxs-lookup"><span data-stu-id="a2d49-114">The first example in this topic shows you how to perform a group join.</span></span> <span data-ttu-id="a2d49-115">Во втором примере — как использовать групповое соединение для создания XML-элементов.</span><span class="sxs-lookup"><span data-stu-id="a2d49-115">The second example shows you how to use a group join to create XML elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2d49-116">Пример</span><span class="sxs-lookup"><span data-stu-id="a2d49-116">Example</span></span>  
  
### <a name="group-join-example"></a><span data-ttu-id="a2d49-117">Пример группового соединения</span><span class="sxs-lookup"><span data-stu-id="a2d49-117">Group join example</span></span>  
 <span data-ttu-id="a2d49-118">В приведенном ниже примере выполняется групповое соединение объектов типа `Person` и `Pet` на основе сравнения `Person` свойства `Pet.Owner`.</span><span class="sxs-lookup"><span data-stu-id="a2d49-118">The following example performs a group join of objects of type `Person` and `Pet` based on the `Person` matching the `Pet.Owner` property.</span></span> <span data-ttu-id="a2d49-119">В отличие от негруппового соединения, в котором создается пара элементов для каждого точного совпадения, групповое соединение создает один результирующий объект для каждого элемента первой коллекции, то есть объекта `Person` в данном примере.</span><span class="sxs-lookup"><span data-stu-id="a2d49-119">Unlike a non-group join, which would produce a pair of elements for each match, the group join produces only one resulting object for each element of the first collection, which in this example is a `Person` object.</span></span> <span data-ttu-id="a2d49-120">Соответствующие элементы из второй коллекции (в данном примере — объекты `Pet`) группируются в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="a2d49-120">The corresponding elements from the second collection, which in this example are `Pet` objects, are grouped into a collection.</span></span> <span data-ttu-id="a2d49-121">Наконец, результирующая функция селектора создает для каждого совпадения анонимный тип, состоящий из `Person.FirstName` и коллекции объектов `Pet`.</span><span class="sxs-lookup"><span data-stu-id="a2d49-121">Finally, the result selector function creates an anonymous type for each match that consists of `Person.FirstName` and a collection of `Pet` objects.</span></span>  
  
 <span data-ttu-id="a2d49-122">[!code-cs[CsLINQProgJoining#5](../../../samples/snippets/csharp/concepts/linq/how-to-perform-grouped-joins_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="a2d49-122">[!code-cs[CsLINQProgJoining#5](../../../samples/snippets/csharp/concepts/linq/how-to-perform-grouped-joins_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2d49-123">Пример</span><span class="sxs-lookup"><span data-stu-id="a2d49-123">Example</span></span>  
  
### <a name="group-join-to-create-xml-example"></a><span data-ttu-id="a2d49-124">Пример группового соединения для создания XML</span><span class="sxs-lookup"><span data-stu-id="a2d49-124">Group join to create XML example</span></span>  
 <span data-ttu-id="a2d49-125">Групповые соединения идеально подходят для создания XML с помощью LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="a2d49-125">Group joins are ideal for creating XML by using LINQ to XML.</span></span> <span data-ttu-id="a2d49-126">Приведенный ниже пример аналогичен предыдущему за исключением того, что вместо создания анонимных типов результирующая функция селектора создает XML-элементы, представляющие соединенные объекты.</span><span class="sxs-lookup"><span data-stu-id="a2d49-126">The following example is similar to the previous example except that instead of creating anonymous types, the result selector function creates XML elements that represent the joined objects.</span></span>  
  
 <span data-ttu-id="a2d49-127">[!code-cs[CsLINQProgJoining#6](../../../samples/snippets/csharp/concepts/linq/how-to-perform-grouped-joins_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="a2d49-127">[!code-cs[CsLINQProgJoining#6](../../../samples/snippets/csharp/concepts/linq/how-to-perform-grouped-joins_2.cs)]</span></span>  
 
## <a name="see-also"></a><span data-ttu-id="a2d49-128">См. также</span><span class="sxs-lookup"><span data-stu-id="a2d49-128">See also</span></span>  
 <span data-ttu-id="a2d49-129"><xref:System.Linq.Enumerable.Join%2A></span><span class="sxs-lookup"><span data-stu-id="a2d49-129"><xref:System.Linq.Enumerable.Join%2A></span></span>   
 <span data-ttu-id="a2d49-130"><xref:System.Linq.Enumerable.GroupJoin%2A></span><span class="sxs-lookup"><span data-stu-id="a2d49-130"><xref:System.Linq.Enumerable.GroupJoin%2A></span></span>   
 <span data-ttu-id="a2d49-131">[Выполнение внутренних соединений](perform-inner-joins.md) </span><span class="sxs-lookup"><span data-stu-id="a2d49-131">[Perform inner joins](perform-inner-joins.md) </span></span>  
 <span data-ttu-id="a2d49-132">[Выполнение левых внешних соединений](perform-left-outer-joins.md) </span><span class="sxs-lookup"><span data-stu-id="a2d49-132">[Perform left outer joins](perform-left-outer-joins.md) </span></span>  
 [<span data-ttu-id="a2d49-133">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="a2d49-133">Anonymous types</span></span>](../programming-guide/classes-and-structs/anonymous-types.md)   
 

