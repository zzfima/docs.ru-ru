---
title: Выполнение групповых соединений (LINQ в C#)
description: Узнайте, как выполнять групповые соединения с помощью LINQ в C#.
ms.date: 12/01/2016
ms.assetid: 9667daf9-a5fd-4b43-a5c4-a9c2b744000e
ms.openlocfilehash: dfb75b55336d8ca486d5f10b187e955d20cd06fd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "61689142"
---
# <a name="perform-grouped-joins"></a><span data-ttu-id="4674e-103">Выполнение групповых соединений</span><span class="sxs-lookup"><span data-stu-id="4674e-103">Perform grouped joins</span></span>

<span data-ttu-id="4674e-104">Групповое соединение можно использовать для создания иерархических структур данных.</span><span class="sxs-lookup"><span data-stu-id="4674e-104">The group join is useful for producing hierarchical data structures.</span></span> <span data-ttu-id="4674e-105">Каждый элемент из первой коллекции группируется с набором соответствующих элементов из второй коллекции.</span><span class="sxs-lookup"><span data-stu-id="4674e-105">It pairs each element from the first collection with a set of correlated elements from the second collection.</span></span>

<span data-ttu-id="4674e-106">Например, класс или таблица реляционной базы данных под названием `Student` может содержать два поля: `Id` и `Name`.</span><span class="sxs-lookup"><span data-stu-id="4674e-106">For example, a class or a relational database table named `Student` might contain two fields: `Id` and `Name`.</span></span> <span data-ttu-id="4674e-107">Второй класс или таблица реляционной базы данных под названием `Course` может содержать два поля: `StudentId` и `CourseTitle`.</span><span class="sxs-lookup"><span data-stu-id="4674e-107">A second class or relational database table named `Course` might contain two fields: `StudentId` and `CourseTitle`.</span></span> <span data-ttu-id="4674e-108">Групповое соединение этих двух источников данных, основанное на сравнении `Student.Id` и `Course.StudentId`, приведет к группировке каждого объекта `Student` с коллекцией объектов `Course` (которая может быть пустой).</span><span class="sxs-lookup"><span data-stu-id="4674e-108">A group join of these two data sources, based on matching `Student.Id` and `Course.StudentId`, would group each `Student` with a collection of `Course` objects (which might be empty).</span></span>

> [!NOTE]
> <span data-ttu-id="4674e-109">Каждый элемент первой коллекции отображается в результирующем наборе группового соединения вне зависимости от того, найдены ли соответствующие ему элементы во второй коллекции.</span><span class="sxs-lookup"><span data-stu-id="4674e-109">Each element of the first collection appears in the result set of a group join regardless of whether correlated elements are found in the second collection.</span></span> <span data-ttu-id="4674e-110">В случае, если такие элементы не найдены, последовательность соответствующих элементов будет пуста.</span><span class="sxs-lookup"><span data-stu-id="4674e-110">In the case where no correlated elements are found, the sequence of correlated elements for that element is empty.</span></span> <span data-ttu-id="4674e-111">Селектор результата имеет доступ к каждому элементу первой коллекции.</span><span class="sxs-lookup"><span data-stu-id="4674e-111">The result selector therefore has access to every element of the first collection.</span></span> <span data-ttu-id="4674e-112">При этом следует учесть отличие от селектора результата в негрупповом соединении: в этом случае селектор не имеет доступа к элементам из первой коллекции, для которых нет совпадений во второй коллекции.</span><span class="sxs-lookup"><span data-stu-id="4674e-112">This differs from the result selector in a non-group join, which cannot access elements from the first collection that have no match in the second collection.</span></span>

<span data-ttu-id="4674e-113">В первом примере этой статьи показано, как выполнить групповое соединение.</span><span class="sxs-lookup"><span data-stu-id="4674e-113">The first example in this article shows you how to perform a group join.</span></span> <span data-ttu-id="4674e-114">Во втором примере — как использовать групповое соединение для создания XML-элементов.</span><span class="sxs-lookup"><span data-stu-id="4674e-114">The second example shows you how to use a group join to create XML elements.</span></span>

## <a name="example---group-join"></a><span data-ttu-id="4674e-115">Пример группового соединения</span><span class="sxs-lookup"><span data-stu-id="4674e-115">Example - Group join</span></span>

<span data-ttu-id="4674e-116">В приведенном ниже примере выполняется групповое соединение объектов типа `Person` и `Pet` на основе сравнения `Person` свойства `Pet.Owner`.</span><span class="sxs-lookup"><span data-stu-id="4674e-116">The following example performs a group join of objects of type `Person` and `Pet` based on the `Person` matching the `Pet.Owner` property.</span></span> <span data-ttu-id="4674e-117">В отличие от негруппового соединения, в котором создается пара элементов для каждого точного совпадения, групповое соединение создает один результирующий объект для каждого элемента первой коллекции, то есть объекта `Person` в данном примере.</span><span class="sxs-lookup"><span data-stu-id="4674e-117">Unlike a non-group join, which would produce a pair of elements for each match, the group join produces only one resulting object for each element of the first collection, which in this example is a `Person` object.</span></span> <span data-ttu-id="4674e-118">Соответствующие элементы из второй коллекции (в данном примере — объекты `Pet`) группируются в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="4674e-118">The corresponding elements from the second collection, which in this example are `Pet` objects, are grouped into a collection.</span></span> <span data-ttu-id="4674e-119">Наконец, результирующая функция селектора создает для каждого совпадения анонимный тип, состоящий из `Person.FirstName` и коллекции объектов `Pet`.</span><span class="sxs-lookup"><span data-stu-id="4674e-119">Finally, the result selector function creates an anonymous type for each match that consists of `Person.FirstName` and a collection of `Pet` objects.</span></span>

[!code-csharp[CsLINQProgJoining#5](~/samples/snippets/csharp/concepts/linq/how-to-perform-grouped-joins_1.cs)]

## <a name="example---group-join-to-create-xml"></a><span data-ttu-id="4674e-120">Пример группового соединения для создания XML</span><span class="sxs-lookup"><span data-stu-id="4674e-120">Example - Group join to create XML</span></span>

<span data-ttu-id="4674e-121">Групповые соединения идеально подходят для создания XML с помощью LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="4674e-121">Group joins are ideal for creating XML by using LINQ to XML.</span></span> <span data-ttu-id="4674e-122">Приведенный ниже пример аналогичен предыдущему за исключением того, что вместо создания анонимных типов результирующая функция селектора создает XML-элементы, представляющие соединенные объекты.</span><span class="sxs-lookup"><span data-stu-id="4674e-122">The following example is similar to the previous example except that instead of creating anonymous types, the result selector function creates XML elements that represent the joined objects.</span></span>

[!code-csharp[CsLINQProgJoining#6](~/samples/snippets/csharp/concepts/linq/how-to-perform-grouped-joins_2.cs)]

## <a name="see-also"></a><span data-ttu-id="4674e-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4674e-123">See also</span></span>

- <xref:System.Linq.Enumerable.Join%2A>
- <xref:System.Linq.Enumerable.GroupJoin%2A>
- [<span data-ttu-id="4674e-124">Выполнение внутренних соединений</span><span class="sxs-lookup"><span data-stu-id="4674e-124">Perform inner joins</span></span>](perform-inner-joins.md)
- [<span data-ttu-id="4674e-125">Выполнение левых внешних соединений</span><span class="sxs-lookup"><span data-stu-id="4674e-125">Perform left outer joins</span></span>](perform-left-outer-joins.md)
- [<span data-ttu-id="4674e-126">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="4674e-126">Anonymous types</span></span>](../programming-guide/classes-and-structs/anonymous-types.md)
