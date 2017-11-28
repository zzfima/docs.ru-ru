---
title: "Выполнение левых внешних соединений"
description: "Сведения о выполнении левых внешних соединений."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: f542cee6-3169-4dcf-a631-3a6a79ccd473
ms.openlocfilehash: 0c28c85bf933a411403aefcb91801d28fe1c268e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="perform-left-outer-joins"></a><span data-ttu-id="3754f-104">Выполнение левых внешних соединений</span><span class="sxs-lookup"><span data-stu-id="3754f-104">Perform left outer joins</span></span>
<span data-ttu-id="3754f-105">Левое внешнее соединение — это соединение, при котором каждый элемент первой коллекции возвращается независимо от наличия взаимосвязанных элементов во второй коллекции.</span><span class="sxs-lookup"><span data-stu-id="3754f-105">A left outer join is a join in which each element of the first collection is returned, regardless of whether it has any correlated elements in the second collection.</span></span> <span data-ttu-id="3754f-106">LINQ можно использовать для левого внешнего соединения, вызвав метод <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> на основании результатов группового соединения.</span><span class="sxs-lookup"><span data-stu-id="3754f-106">You can use LINQ to perform a left outer join by calling the <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> method on the results of a group join.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3754f-107">Пример</span><span class="sxs-lookup"><span data-stu-id="3754f-107">Example</span></span>  
 <span data-ttu-id="3754f-108">В приведенном ниже примере показано, как использовать метод <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> применительно к результатам группового соединения для выполнения левого внешнего соединения.</span><span class="sxs-lookup"><span data-stu-id="3754f-108">The following example demonstrates how to use the <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> method on the results of a group join to perform a left outer join.</span></span>  
  
 <span data-ttu-id="3754f-109">Первым шагом выполнения левого внешнего соединения двух коллекций является выполнение внутреннего соединения с помощью группового соединения.</span><span class="sxs-lookup"><span data-stu-id="3754f-109">The first step in producing a left outer join of two collections is to perform an inner join by using a group join.</span></span> <span data-ttu-id="3754f-110">(Описание этой процедуры см. в разделе [Выполнение внутренних соединений](perform-inner-joins.md).) В этом примере список объектов `Person` соединен посредством внутреннего соединения со списком объектов `Pet` на основе объекта `Person`, соответствующего `Pet.Owner`.</span><span class="sxs-lookup"><span data-stu-id="3754f-110">(See [Perform inner joins](perform-inner-joins.md) for an explanation of this process.) In this example, the list of `Person` objects is inner-joined to the list of `Pet` objects based on a `Person` object that matches `Pet.Owner`.</span></span>  
  
 <span data-ttu-id="3754f-111">Вторым шагом является включение каждого элемента первой (левой) коллекции в набор результатов, даже если элемент не имеет совпадений в правой коллекции.</span><span class="sxs-lookup"><span data-stu-id="3754f-111">The second step is to include each element of the first (left) collection in the result set even if that element has no matches in the right collection.</span></span> <span data-ttu-id="3754f-112">Эта процедура выполняется путем вызова метода <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> для каждой последовательности совпадающих элементов из группового соединения.</span><span class="sxs-lookup"><span data-stu-id="3754f-112">This is accomplished by calling <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> on each sequence of matching elements from the group join.</span></span> <span data-ttu-id="3754f-113">В этом примере <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> вызывается для каждой последовательности совпадающих объектов `Pet`.</span><span class="sxs-lookup"><span data-stu-id="3754f-113">In this example, <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> is called on each sequence of matching `Pet` objects.</span></span> <span data-ttu-id="3754f-114">Метод возвращает коллекцию, содержащую одно значение по умолчанию, если последовательность соответствующих объектов `Pet` пуста для любого объекта `Person`, обеспечивая представление каждого объекта `Person` в коллекции результатов.</span><span class="sxs-lookup"><span data-stu-id="3754f-114">The method returns a collection that contains a single, default value if the sequence of matching `Pet` objects is empty for any `Person` object, thereby ensuring that each `Person` object is represented in the result collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3754f-115">Значение по умолчанию для ссылочного типа — `null`, поэтому в примере проверяется пустая ссылка перед доступом к каждому элементу в каждой коллекции `Pet`.</span><span class="sxs-lookup"><span data-stu-id="3754f-115">The default value for a reference type is `null`; therefore, the example checks for a null reference before accessing each element of each `Pet` collection.</span></span>  
  
 [!code-csharp[CsLINQProgJoining#7](../../../samples/snippets/csharp/concepts/linq/how-to-perform-left-outer-joins_1.cs)]  
 
## <a name="see-also"></a><span data-ttu-id="3754f-116">См. также</span><span class="sxs-lookup"><span data-stu-id="3754f-116">See also</span></span>  
 <xref:System.Linq.Enumerable.Join%2A>  
 <xref:System.Linq.Enumerable.GroupJoin%2A>  
 [<span data-ttu-id="3754f-117">Выполнение внутренних соединений</span><span class="sxs-lookup"><span data-stu-id="3754f-117">Perform inner joins</span></span>](perform-inner-joins.md)  
 [<span data-ttu-id="3754f-118">Выполнение групповых соединений</span><span class="sxs-lookup"><span data-stu-id="3754f-118">Perform grouped joins</span></span>](perform-grouped-joins.md)  
 [<span data-ttu-id="3754f-119">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="3754f-119">Anonymous types</span></span>](../programming-guide/classes-and-structs/anonymous-types.md)  
 
