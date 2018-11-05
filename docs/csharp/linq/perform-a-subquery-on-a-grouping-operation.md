---
title: Вложенный запрос в операции группирования (LINQ в C#)
description: Как выполнять вложенный запрос в операции группирования с помощью LINQ в C#.
ms.date: 12/1/2016
ms.assetid: d75a588e-9b6f-4f37-b195-f99ec8503855
ms.openlocfilehash: 19be93fe695982e93abea9a59153a4245dce4a60
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2018
ms.locfileid: "48846322"
---
# <a name="perform-a-subquery-on-a-grouping-operation"></a><span data-ttu-id="36faa-103">Вложенный запрос в операции группирования</span><span class="sxs-lookup"><span data-stu-id="36faa-103">Perform a subquery on a grouping operation</span></span>

<span data-ttu-id="36faa-104">В этой статье показаны два разных способа создания запроса, упорядочивающего исходные данные в группы и затем выполняющего вложенный запрос для каждой группы по отдельности.</span><span class="sxs-lookup"><span data-stu-id="36faa-104">This article shows two different ways to create a query that orders the source data into groups, and then performs a subquery over each group individually.</span></span> <span data-ttu-id="36faa-105">Основное действие в каждом примере заключается в группировании исходных элементов с помощью *продолжения* с именем `newGroup` с последующим созданием вложенного запроса для `newGroup`.</span><span class="sxs-lookup"><span data-stu-id="36faa-105">The basic technique in each example is to group the source elements by using a *continuation* named `newGroup`, and then generating a new subquery against `newGroup`.</span></span> <span data-ttu-id="36faa-106">Этот вложенный запрос выполняется для каждой новой группы, создаваемой внешним запросом.</span><span class="sxs-lookup"><span data-stu-id="36faa-106">This subquery is run against each new group that is created by the outer query.</span></span> <span data-ttu-id="36faa-107">В этом конкретном примере следует обратить внимание на то, что в конечном итоге получается не группа, а простая последовательность анонимных типов.</span><span class="sxs-lookup"><span data-stu-id="36faa-107">Note that in this particular example the final output is not a group, but a flat sequence of anonymous types.</span></span>  
  
<span data-ttu-id="36faa-108">Дополнительные сведения о способах группирования см. в разделе [Предложение group](../language-reference/keywords/group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="36faa-108">For more information about how to group, see [group clause](../language-reference/keywords/group-clause.md).</span></span>  
  
<span data-ttu-id="36faa-109">Дополнительные сведения о продолжениях см. в разделе [into](../language-reference/keywords/into.md).</span><span class="sxs-lookup"><span data-stu-id="36faa-109">For more information about continuations, see [into](../language-reference/keywords/into.md).</span></span> <span data-ttu-id="36faa-110">В приведенном ниже примере в качестве источника данных используется структура данных в памяти, но те же принципы действуют для любого типа источника данных LINQ.</span><span class="sxs-lookup"><span data-stu-id="36faa-110">The following example uses an in-memory data structure as the data source, but the same principles apply for any kind of LINQ data source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36faa-111">Пример</span><span class="sxs-lookup"><span data-stu-id="36faa-111">Example</span></span>

> [!NOTE]
> <span data-ttu-id="36faa-112">Этот пример содержит ссылки на объекты, определенные в примере кода в разделе [Запрос коллекции объектов](query-a-collection-of-objects.md).</span><span class="sxs-lookup"><span data-stu-id="36faa-112">This example contains references to objects that are defined in the sample code in [Query a collection of objects](query-a-collection-of-objects.md).</span></span>

[!code-csharp[csProgGuideLINQ#23](~/samples/snippets/csharp/concepts/linq/how-to-perform-a-subquery-on-a-grouping-operation_1.cs)] 

<span data-ttu-id="36faa-113">Запрос, который приведен в фрагменте кода выше, можно записать, используя синтаксис метода.</span><span class="sxs-lookup"><span data-stu-id="36faa-113">The query in the snippet above can also be written using method syntax.</span></span> <span data-ttu-id="36faa-114">В следующем фрагменте кода приведен семантически эквивалентный запрос, написанный с использованием синтаксиса метода.</span><span class="sxs-lookup"><span data-stu-id="36faa-114">The following code snippet has a semantically equivalent query written using method syntax.</span></span>

[!code-csharp[csProgGuideLINQ#86](~/samples/snippets/csharp/concepts/linq/how-to-perform-a-subquery-on-a-grouping-operation_2.cs)]

## <a name="see-also"></a><span data-ttu-id="36faa-115">См. также</span><span class="sxs-lookup"><span data-stu-id="36faa-115">See also</span></span>

- [<span data-ttu-id="36faa-116">LINQ</span><span class="sxs-lookup"><span data-stu-id="36faa-116">Language Integrated Query (LINQ)</span></span>](index.md)
