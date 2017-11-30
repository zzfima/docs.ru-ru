---
title: "Выполнение запросов в связях"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 297878d0-685b-4c01-b2e0-9d731b7322bc
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: a347818818fe7c6e15535fd0c2c24548c52e57d5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="querying-across-relationships"></a><span data-ttu-id="7121b-102">Выполнение запросов в связях</span><span class="sxs-lookup"><span data-stu-id="7121b-102">Querying Across Relationships</span></span>
<span data-ttu-id="7121b-103">Ссылки на другие объекты или коллекции других объектов в определениях классов указывают непосредственно на связи внешнего ключа в базе данных.</span><span class="sxs-lookup"><span data-stu-id="7121b-103">References to other objects or collections of other objects in your class definitions directly correspond to foreign-key relationships in the database.</span></span> <span data-ttu-id="7121b-104">Эти связи можно использовать при осуществлении запроса с помощью точечной нотации для доступа к свойствам связей и перехода от одного объекта к другому.</span><span class="sxs-lookup"><span data-stu-id="7121b-104">You can use these relationships when you query by using dot notation to access the relationship properties and navigate from one object to another.</span></span> <span data-ttu-id="7121b-105">Эти операции доступа преобразуются в более сложные соединения или коррелированные подзапросы в эквивалентном SQL.</span><span class="sxs-lookup"><span data-stu-id="7121b-105">These access operations translate to more complex joins or correlated subqueries in the equivalent SQL.</span></span>  
  
 <span data-ttu-id="7121b-106">Например, следующий запрос переходит от заказов к клиентам в качестве способа ограничения результатов только заказами для клиентов, находящихся в Лондоне.</span><span class="sxs-lookup"><span data-stu-id="7121b-106">For example, the following query navigates from orders to customers as a way to restrict the results to only those orders for customers located in London.</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#3)]
 [!code-vb[DLinqQueryConcepts#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#3)]  
  
 <span data-ttu-id="7121b-107">Если свойства связи не существуют придется написать их вручную как *соединения*так же, как это делается в SQL-запрос, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="7121b-107">If relationship properties did not exist you would have to write them manually as *joins*, just as you would do in a SQL query, as in the following code:</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#4)]
 [!code-vb[DLinqQueryConcepts#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#4)]  
  
 <span data-ttu-id="7121b-108">Можно использовать *связь* свойство, чтобы определить один раз для данной конкретной связи.</span><span class="sxs-lookup"><span data-stu-id="7121b-108">You can use the *relationship* property to define this particular relationship one time.</span></span> <span data-ttu-id="7121b-109">После этого можно применять более удобный точечный синтаксис.</span><span class="sxs-lookup"><span data-stu-id="7121b-109">You can then use the more convenient dot syntax.</span></span> <span data-ttu-id="7121b-110">Однако существование свойств связи более важно, поскольку объектные модели, характерные для доменов, обычно определяются как иерархии или графики.</span><span class="sxs-lookup"><span data-stu-id="7121b-110">But relationship properties exist more importantly because domain-specific object models are typically defined as hierarchies or graphs.</span></span> <span data-ttu-id="7121b-111">Программируемые объекты имеют ссылки на другие объекты.</span><span class="sxs-lookup"><span data-stu-id="7121b-111">The objects that you program against have references to other objects.</span></span> <span data-ttu-id="7121b-112">Соответствие связей "объект-объект" связям внешнего ключа в базах данных является лишь совпадением.</span><span class="sxs-lookup"><span data-stu-id="7121b-112">It is only a happy coincidence that object-to-object relationships correspond to foreign-key-styled relationships in databases.</span></span> <span data-ttu-id="7121b-113">Доступ к свойству предоставляет удобный способ для написания соединений.</span><span class="sxs-lookup"><span data-stu-id="7121b-113">Property access then provides a convenient way to write joins.</span></span>  
  
 <span data-ttu-id="7121b-114">В связи с этим свойства связи являются более важными как результаты запроса, чем как часть самого запроса.</span><span class="sxs-lookup"><span data-stu-id="7121b-114">With regard to this, relationship properties are more important on the results side of a query than as part of the query itself.</span></span> <span data-ttu-id="7121b-115">После того, как запрос извлечет, данные о конкретном клиенте, определение класса указывает наличие заказов.</span><span class="sxs-lookup"><span data-stu-id="7121b-115">After the query has retrieved data about a particular customer, the class definition indicates that customers have orders.</span></span> <span data-ttu-id="7121b-116">Другими словами, ожидается, что свойство `Orders` конкретного клиента является коллекцией, заполняемой всеми заказами данного клиента.</span><span class="sxs-lookup"><span data-stu-id="7121b-116">In other words, you expect the `Orders` property of a particular customer to be a collection that is populated with all the orders from that customer.</span></span> <span data-ttu-id="7121b-117">На самом деле это контракт, объявленный путем подобного определения классов.</span><span class="sxs-lookup"><span data-stu-id="7121b-117">That is in fact the contract you declared by defining the classes in this manner.</span></span> <span data-ttu-id="7121b-118">Вы хотите увидеть в нем заказы, даже если они не требуются для запроса.</span><span class="sxs-lookup"><span data-stu-id="7121b-118">You expect to see the orders there even if the query did not request orders.</span></span> <span data-ttu-id="7121b-119">Вы хотите, чтобы объектная модель поддерживала представление о том, что это находящееся в памяти расширение базы данных со связанными и немедленно доступными объектами.</span><span class="sxs-lookup"><span data-stu-id="7121b-119">You expect your object model to maintain an illusion that it is an in-memory extension of the database with related objects immediately available.</span></span>  
  
 <span data-ttu-id="7121b-120">Теперь при наличии связей можно писать запросы, обращаясь к свойствам связей, определенным в классах.</span><span class="sxs-lookup"><span data-stu-id="7121b-120">Now that you have relationships, you can write queries by referring to the relationship properties defined in your classes.</span></span> <span data-ttu-id="7121b-121">Эти ссылки на связи соответствуют связям внешнего ключа в базе данных.</span><span class="sxs-lookup"><span data-stu-id="7121b-121">These relationship references correspond to foreign-key relationships in the database.</span></span> <span data-ttu-id="7121b-122">Операции, использующие эти связи, преобразуются в более сложные соединения в эквивалентном SQL.</span><span class="sxs-lookup"><span data-stu-id="7121b-122">Operations that use these relationships translate to more complex joins in the equivalent SQL.</span></span> <span data-ttu-id="7121b-123">После определения связи (с помощью атрибута <xref:System.Data.Linq.Mapping.AssociationAttribute>) не требуется кодировать явное соединение в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7121b-123">As long as you have defined a relationship (using the <xref:System.Data.Linq.Mapping.AssociationAttribute> attribute), you do not have to code an explicit join in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 <span data-ttu-id="7121b-124">Для поддержки этого представления [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] реализует метод, называемый *отложенная загрузка*.</span><span class="sxs-lookup"><span data-stu-id="7121b-124">To help maintain this illusion, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] implements a technique called *deferred loading*.</span></span> <span data-ttu-id="7121b-125">Дополнительные сведения см. в разделе [отложенное или немедленное загрузки](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).</span><span class="sxs-lookup"><span data-stu-id="7121b-125">For more information, see [Deferred versus Immediate Loading](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).</span></span>  
  
 <span data-ttu-id="7121b-126">Рассмотрим следующий запрос SQL для создания списка `CustomerID` - `OrderID` пары:</span><span class="sxs-lookup"><span data-stu-id="7121b-126">Consider the following SQL query to project a list of `CustomerID`-`OrderID` pairs:</span></span>  
  
```  
SELECT t0.CustomerID, t1.OrderID  
FROM   Customers AS t0 INNER JOIN  
          Orders AS t1 ON t0.CustomerID = t1.CustomerID  
WHERE  (t0.City = @p0)  
```  
  
 <span data-ttu-id="7121b-127">Чтобы получить такие же результаты с помощью [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], используйте ссылку на свойство `Orders`, уже существующую в классе `Customer`.</span><span class="sxs-lookup"><span data-stu-id="7121b-127">To obtain the same results by using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you use the `Orders` property reference already existing in the `Customer` class.</span></span> <span data-ttu-id="7121b-128">`Orders` Справочник предоставляет сведения, необходимые для выполнения запроса и `CustomerID` - `OrderID` пары, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="7121b-128">The `Orders` reference provides the necessary information to execute the query and project the `CustomerID`-`OrderID` pairs, as in the following code:</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#5)]
 [!code-vb[DLinqQueryConcepts#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#5)]  
  
 <span data-ttu-id="7121b-129">Также можно выполнить обратное.</span><span class="sxs-lookup"><span data-stu-id="7121b-129">You can also do the reverse.</span></span> <span data-ttu-id="7121b-130">Это значит, что можно запросить `Orders` и использовать ссылку на связь `Customer` для получения сведений о связанном объекте `Customer`.</span><span class="sxs-lookup"><span data-stu-id="7121b-130">That is, you can query `Orders` and use its `Customer` relationship reference to access information about the associated `Customer` object.</span></span> <span data-ttu-id="7121b-131">В следующем коде создаются те же `CustomerID` - `OrderID` пары как и раньше, но на этот раз запрашивая `Orders` вместо `Customers`.</span><span class="sxs-lookup"><span data-stu-id="7121b-131">The following code projects the same `CustomerID`-`OrderID` pairs as before, but this time by querying `Orders` instead of `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#6)]
 [!code-vb[DLinqQueryConcepts#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="7121b-132">См. также</span><span class="sxs-lookup"><span data-stu-id="7121b-132">See Also</span></span>  
 [<span data-ttu-id="7121b-133">Основные принципы запросов</span><span class="sxs-lookup"><span data-stu-id="7121b-133">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
