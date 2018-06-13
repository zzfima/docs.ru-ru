---
title: Вложенный запрос в операции группирования
description: Сведения о выполнении вложенного запроса в операции группирования.
ms.date: 12/1/2016
ms.assetid: d75a588e-9b6f-4f37-b195-f99ec8503855
ms.openlocfilehash: 209d05c2fe8719fa9116061d199272366146f465
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33277333"
---
# <a name="perform-a-subquery-on-a-grouping-operation"></a><span data-ttu-id="c7dc5-103">Вложенный запрос в операции группирования</span><span class="sxs-lookup"><span data-stu-id="c7dc5-103">Perform a subquery on a grouping operation</span></span>

<span data-ttu-id="c7dc5-104">В этом разделе показаны два разных способа создания запроса, упорядочивающего исходные данные в группы и затем выполняющего вложенный запрос для каждой группы по отдельности.</span><span class="sxs-lookup"><span data-stu-id="c7dc5-104">This topic shows two different ways to create a query that orders the source data into groups, and then performs a subquery over each group individually.</span></span> <span data-ttu-id="c7dc5-105">Основное действие в каждом примере заключается в группировании исходных элементов с помощью *продолжения* с именем `newGroup` с последующим созданием вложенного запроса для `newGroup`.</span><span class="sxs-lookup"><span data-stu-id="c7dc5-105">The basic technique in each example is to group the source elements by using a *continuation* named `newGroup`, and then generating a new subquery against `newGroup`.</span></span> <span data-ttu-id="c7dc5-106">Этот вложенный запрос выполняется для каждой новой группы, создаваемой внешним запросом.</span><span class="sxs-lookup"><span data-stu-id="c7dc5-106">This subquery is run against each new group that is created by the outer query.</span></span> <span data-ttu-id="c7dc5-107">В этом конкретном примере следует обратить внимание на то, что в конечном итоге получается не группа, а простая последовательность анонимных типов.</span><span class="sxs-lookup"><span data-stu-id="c7dc5-107">Note that in this particular example the final output is not a group, but a flat sequence of anonymous types.</span></span>  
  
 <span data-ttu-id="c7dc5-108">Дополнительные сведения о способах группирования см. в разделе [Предложение group](../language-reference/keywords/group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="c7dc5-108">For more information about how to group, see [group clause](../language-reference/keywords/group-clause.md).</span></span>  
  
 <span data-ttu-id="c7dc5-109">Дополнительные сведения о продолжениях см. в разделе [into](../language-reference/keywords/into.md).</span><span class="sxs-lookup"><span data-stu-id="c7dc5-109">For more information about continuations, see [into](../language-reference/keywords/into.md).</span></span> <span data-ttu-id="c7dc5-110">В приведенном ниже примере в качестве источника данных используется структура данных в памяти, но те же принципы действуют для любого типа источника данных LINQ.</span><span class="sxs-lookup"><span data-stu-id="c7dc5-110">The following example uses an in-memory data structure as the data source, but the same principles apply for any kind of LINQ data source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7dc5-111">Пример</span><span class="sxs-lookup"><span data-stu-id="c7dc5-111">Example</span></span> 

 > [!NOTE]
 > <span data-ttu-id="c7dc5-112">Этот пример содержит ссылки на объекты, определенные в примере кода в разделе [Запрос коллекции объектов](query-a-collection-of-objects.md).</span><span class="sxs-lookup"><span data-stu-id="c7dc5-112">This example contains references to objects that are defined in the sample code in [Query a collection of objects](query-a-collection-of-objects.md).</span></span>

 [!code-csharp[csProgGuideLINQ#23](../../../samples/snippets/csharp/concepts/linq/how-to-perform-a-subquery-on-a-grouping-operation_1.cs)]  
   
## <a name="see-also"></a><span data-ttu-id="c7dc5-113">См. также</span><span class="sxs-lookup"><span data-stu-id="c7dc5-113">See also</span></span>  
 [<span data-ttu-id="c7dc5-114">Выражения запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="c7dc5-114">LINQ Query Expressions</span></span>](index.md)
