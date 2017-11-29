---
title: "Вложенный запрос в операции группирования"
description: "Сведения о выполнении вложенного запроса в операции группирования."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: d75a588e-9b6f-4f37-b195-f99ec8503855
ms.openlocfilehash: f638b8a679a15891d04e02f1597d6bf7934a9e74
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2017
---
# <a name="perform-a-subquery-on-a-grouping-operation"></a><span data-ttu-id="a4367-104">Вложенный запрос в операции группирования</span><span class="sxs-lookup"><span data-stu-id="a4367-104">Perform a subquery on a grouping operation</span></span>

<span data-ttu-id="a4367-105">В этом разделе показаны два разных способа создания запроса, упорядочивающего исходные данные в группы и затем выполняющего вложенный запрос для каждой группы по отдельности.</span><span class="sxs-lookup"><span data-stu-id="a4367-105">This topic shows two different ways to create a query that orders the source data into groups, and then performs a subquery over each group individually.</span></span> <span data-ttu-id="a4367-106">Основное действие в каждом примере заключается в группировании исходных элементов с помощью *продолжения* с именем `newGroup` с последующим созданием вложенного запроса для `newGroup`.</span><span class="sxs-lookup"><span data-stu-id="a4367-106">The basic technique in each example is to group the source elements by using a *continuation* named `newGroup`, and then generating a new subquery against `newGroup`.</span></span> <span data-ttu-id="a4367-107">Этот вложенный запрос выполняется для каждой новой группы, создаваемой внешним запросом.</span><span class="sxs-lookup"><span data-stu-id="a4367-107">This subquery is run against each new group that is created by the outer query.</span></span> <span data-ttu-id="a4367-108">В этом конкретном примере следует обратить внимание на то, что в конечном итоге получается не группа, а простая последовательность анонимных типов.</span><span class="sxs-lookup"><span data-stu-id="a4367-108">Note that in this particular example the final output is not a group, but a flat sequence of anonymous types.</span></span>  
  
 <span data-ttu-id="a4367-109">Дополнительные сведения о способах группирования см. в разделе [Предложение group](../language-reference/keywords/group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="a4367-109">For more information about how to group, see [group clause](../language-reference/keywords/group-clause.md).</span></span>  
  
 <span data-ttu-id="a4367-110">Дополнительные сведения о продолжениях см. в разделе [into](../language-reference/keywords/into.md).</span><span class="sxs-lookup"><span data-stu-id="a4367-110">For more information about continuations, see [into](../language-reference/keywords/into.md).</span></span> <span data-ttu-id="a4367-111">В приведенном ниже примере в качестве источника данных используется структура данных в памяти, но те же принципы действуют для любого типа источника данных LINQ.</span><span class="sxs-lookup"><span data-stu-id="a4367-111">The following example uses an in-memory data structure as the data source, but the same principles apply for any kind of LINQ data source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4367-112">Пример</span><span class="sxs-lookup"><span data-stu-id="a4367-112">Example</span></span> 

 > [!NOTE]
 > <span data-ttu-id="a4367-113">Этот пример содержит ссылки на объекты, определенные в примере кода в разделе [Запрос коллекции объектов](query-a-collection-of-objects.md).</span><span class="sxs-lookup"><span data-stu-id="a4367-113">This example contains references to objects that are defined in the sample code in [Query a collection of objects](query-a-collection-of-objects.md).</span></span>

 [!code-csharp[csProgGuideLINQ#23](../../../samples/snippets/csharp/concepts/linq/how-to-perform-a-subquery-on-a-grouping-operation_1.cs)]  
   
## <a name="see-also"></a><span data-ttu-id="a4367-114">См. также</span><span class="sxs-lookup"><span data-stu-id="a4367-114">See also</span></span>  
 [<span data-ttu-id="a4367-115">Выражения запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="a4367-115">LINQ Query Expressions</span></span>](index.md)
