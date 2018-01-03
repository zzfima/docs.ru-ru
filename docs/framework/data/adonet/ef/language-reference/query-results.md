---
title: "Результаты запроса"
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
ms.assetid: bcd7b699-4e50-4523-8c33-2f54a103d94e
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 5ff674cbbe0a5d52a4bc4b4de55e0ae3c49395d9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="query-results"></a><span data-ttu-id="8d491-102">Результаты запроса</span><span class="sxs-lookup"><span data-stu-id="8d491-102">Query Results</span></span>
<span data-ttu-id="8d491-103">После преобразования запроса [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] в деревья команд и последующего выполнения результаты запроса обычно возвращаются в одной из следующих форм.</span><span class="sxs-lookup"><span data-stu-id="8d491-103">After a [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] query is converted to command trees and executed, the query results are usually returned as one of the following:</span></span>  
  
-   <span data-ttu-id="8d491-104">Коллекция из нуля или большего числа типизированных объектов сущностей или проекция сложных типов в концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="8d491-104">A collection of zero or more typed entity objects or a projection of complex types in the conceptual model.</span></span>  
  
-   <span data-ttu-id="8d491-105">Типы CLR, поддерживаемые концептуальной моделью.</span><span class="sxs-lookup"><span data-stu-id="8d491-105">CLR types supported by the conceptual model.</span></span>  
  
-   <span data-ttu-id="8d491-106">Встроенные коллекции.</span><span class="sxs-lookup"><span data-stu-id="8d491-106">Inline collections.</span></span>  
  
-   <span data-ttu-id="8d491-107">Анонимные типы.</span><span class="sxs-lookup"><span data-stu-id="8d491-107">Anonymous types.</span></span>  
  
 <span data-ttu-id="8d491-108">При выполнении запроса к источнику данных результаты материализуются в типы CLR и возвращаются клиенту.</span><span class="sxs-lookup"><span data-stu-id="8d491-108">When the query has executed against the data source, the results are materialized into CLR types and returned to the client.</span></span> <span data-ttu-id="8d491-109">Материализация объектов полностью обеспечивается платформой [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d491-109">All object materialization is performed by the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="8d491-110">Любые ошибки, вызванные невозможностью сопоставления объектов платформы [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] и среды CLR, вызовут исключения во время материализации объекта.</span><span class="sxs-lookup"><span data-stu-id="8d491-110">Any errors that result from an inability to map between the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] and the CLR will cause exceptions to be thrown during object materialization.</span></span>  
  
 <span data-ttu-id="8d491-111">Если в результате выполнения запроса возвращаются типы-примитивы концептуальной модели, то результаты состоят из изолированных типов CLR, которые не связаны с платформой [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d491-111">If the query execution returns primitive conceptual model types, the results consist of CLR types that are stand-alone and disconnected from the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="8d491-112">Однако если запрос вернул коллекцию типизированных объектов сущностей, представленных <xref:System.Data.Objects.ObjectQuery%601>, то эти типы отслеживаются контекстом объекта.</span><span class="sxs-lookup"><span data-stu-id="8d491-112">However, if the query returns a collection of typed entity objects, represented by <xref:System.Data.Objects.ObjectQuery%601>, those types are tracked by the object context.</span></span> <span data-ttu-id="8d491-113">Все объекта (например, дочерние и родительские коллекции, отслеживание изменений, полиморфизм и т. д.) выполнятся согласно определениям в [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d491-113">All object behavior (such as child/parent collections, change tracking, polymorphism, and so on) are as defined in the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="8d491-114">Эти функции можно могут быть использованы в пределах, определяемых [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d491-114">This functionality can be used in its capacity, as defined in the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="8d491-115">Дополнительные сведения см. в разделе [работа с объектами](../../../../../../docs/framework/data/adonet/ef/working-with-objects.md).</span><span class="sxs-lookup"><span data-stu-id="8d491-115">For more information, see [Working with Objects](../../../../../../docs/framework/data/adonet/ef/working-with-objects.md).</span></span>  
  
 <span data-ttu-id="8d491-116">Типы структур, возвращаемые из запросов (например, анонимные и сложные типы, допускающие значение null), могут иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="8d491-116">Struct types returned from queries (such as anonymous types and nullable complex types) can be of `null` value.</span></span> <span data-ttu-id="8d491-117">Свойство <xref:System.Data.Objects.DataClasses.EntityCollection%601> возвращаемой сущности также может иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="8d491-117">An <xref:System.Data.Objects.DataClasses.EntityCollection%601> property of a returned entity can also be of `null` value.</span></span> <span data-ttu-id="8d491-118">Это может произойти в результате проецирования свойства коллекции для сущности, имеющей значение `null`, например, при вызове метода <xref:System.Linq.Queryable.FirstOrDefault%2A> для объекта <xref:System.Data.Objects.ObjectQuery%601>, который не содержит элементов.</span><span class="sxs-lookup"><span data-stu-id="8d491-118">This can result from projecting the collection property of an entity that is of `null` value, such as calling <xref:System.Linq.Queryable.FirstOrDefault%2A> on an <xref:System.Data.Objects.ObjectQuery%601> that has no elements.</span></span>  
  
 <span data-ttu-id="8d491-119">В некоторых ситуациях может показаться, что запрос создает материализованный результат во время выполнения, но в действительности запрос будет выполняться на сервере и объект сущности никогда не окажется материализован в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="8d491-119">In certain situations, a query might appear to generate a materialized result during its execution, but the query will be executed on the server and the entity object will never be materialized in the CLR.</span></span> <span data-ttu-id="8d491-120">Это может вызвать проблемы, если приложение рассчитывает на побочные эффекты материализации.</span><span class="sxs-lookup"><span data-stu-id="8d491-120">This can cause problems if you are depending on side effects of object materialization.</span></span>  
  
 <span data-ttu-id="8d491-121">В следующем примере имеется пользовательский класс `MyContact` со свойством `LastName`.</span><span class="sxs-lookup"><span data-stu-id="8d491-121">The following example contains a custom class, `MyContact`, with a `LastName` property.</span></span> <span data-ttu-id="8d491-122">При присваивании значения свойству `LastName` переменная `count` увеличивается на единицу.</span><span class="sxs-lookup"><span data-stu-id="8d491-122">When the `LastName` property is set, a `count` variable is incremented.</span></span> <span data-ttu-id="8d491-123">Если выполнить два приведенных ниже запроса, то первый запрос увеличит значение `count` на единицу, а второй - нет.</span><span class="sxs-lookup"><span data-stu-id="8d491-123">If you execute the two following queries, the first query will increment `count` while the second query will not.</span></span> <span data-ttu-id="8d491-124">Причина этого заключается в том, что во втором запросе свойство `LastName` спроецировано из результатов, а класс `MyContact` не создается, поскольку он не является необходимым для выполнения запроса в хранилище.</span><span class="sxs-lookup"><span data-stu-id="8d491-124">This is because in the second query the `LastName` property is projected from the results and the `MyContact` class is never created, because it is not required to execute the query on the store.</span></span>  
  
 [!code-csharp[DP L2E Materialization Example#MaterializationSideEffects](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Materialization Example/CS/Program.cs#materializationsideeffects)]
 [!code-vb[DP L2E Materialization Example#MaterializationSideEffects](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Materialization Example/VB/Module1.vb#materializationsideeffects)]  
  
 [!code-csharp[DP L2E Materialization Example#MyContactClass](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Materialization Example/CS/Program.cs#mycontactclass)]
 [!code-vb[DP L2E Materialization Example#MyContactClass](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Materialization Example/VB/Module1.vb#mycontactclass)]
