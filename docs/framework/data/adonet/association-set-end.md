---
title: "конечная точка набора ассоциаций"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe4bf1d3-047a-4a37-98c5-a66e70811346
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: ddb7dc758de8d40a2c80a09f93d44600b7c75b56
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="association-set-end"></a><span data-ttu-id="4efbe-102">конечная точка набора ассоциаций</span><span class="sxs-lookup"><span data-stu-id="4efbe-102">association set end</span></span>
<span data-ttu-id="4efbe-103">*Конечная точка набора ассоциаций* идентифицирует [тип сущности](../../../../docs/framework/data/adonet/entity-type.md) и [набора сущностей](../../../../docs/framework/data/adonet/entity-set.md) в конце [набора ассоциаций](../../../../docs/framework/data/adonet/association-set.md).</span><span class="sxs-lookup"><span data-stu-id="4efbe-103">An *association set end* identifies the [entity type](../../../../docs/framework/data/adonet/entity-type.md) and the [entity set](../../../../docs/framework/data/adonet/entity-set.md) at the end of an [association set](../../../../docs/framework/data/adonet/association-set.md).</span></span> <span data-ttu-id="4efbe-104">Конечные точки набора ассоциаций определяются как часть набора ассоциаций; набор ассоциаций должен иметь ровно две конечные точки.</span><span class="sxs-lookup"><span data-stu-id="4efbe-104">Association set ends are defined as part of an association set; an association set must have exactly two association set ends.</span></span>  
  
 <span data-ttu-id="4efbe-105">Определение конечной точки набора ассоциаций содержит следующую информацию.</span><span class="sxs-lookup"><span data-stu-id="4efbe-105">An association set end definition contains the following information:</span></span>  
  
-   <span data-ttu-id="4efbe-106">Один из типов сущностей, участвующих в наборе ассоциаций.</span><span class="sxs-lookup"><span data-stu-id="4efbe-106">One of the entity types involved in the association set.</span></span> <span data-ttu-id="4efbe-107">(Обязательный атрибут).</span><span class="sxs-lookup"><span data-stu-id="4efbe-107">(Required)</span></span>  
  
-   <span data-ttu-id="4efbe-108">Набор сущностей для типа сущностей, участвующих в наборе ассоциаций.</span><span class="sxs-lookup"><span data-stu-id="4efbe-108">The entity set for the entity type involved in the association set.</span></span> <span data-ttu-id="4efbe-109">(Обязательный атрибут).</span><span class="sxs-lookup"><span data-stu-id="4efbe-109">(Required)</span></span>  
  
## <a name="example"></a><span data-ttu-id="4efbe-110">Пример</span><span class="sxs-lookup"><span data-stu-id="4efbe-110">Example</span></span>  
 <span data-ttu-id="4efbe-111">На приведенной ниже схеме показана концептуальная модель с двумя ассоциациями: `WrittenBy` и `PublishedBy`.</span><span class="sxs-lookup"><span data-stu-id="4efbe-111">The diagram below shows a conceptual model with two associations: `WrittenBy` and `PublishedBy`.</span></span>  
  
 <span data-ttu-id="4efbe-112">![Пример модели](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="4efbe-112">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="4efbe-113">На следующей схеме показаны один набор ассоциаций (`PublishedBy` и `Books`) и два набора сущностей (`Publishers`) на основе приведенной выше концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="4efbe-113">The following diagram shows an association set (`PublishedBy`) and two entity sets (`Books` and `Publishers`) based on the conceptual model shown above.</span></span> <span data-ttu-id="4efbe-114">Конечные точки набора ассоциаций - это наборы сущностей `Books` и `Publishers`.</span><span class="sxs-lookup"><span data-stu-id="4efbe-114">The association set ends are the `Books` and `Publishers` entity sets.</span></span> <span data-ttu-id="4efbe-115">Бизнес-аналитики в `Books` набор сущностей представляет экземпляр `Book` тип сущности во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="4efbe-115">Bi in the `Books` entity set represents an instance of the `Book` entity type at run time.</span></span> <span data-ttu-id="4efbe-116">Аналогичным образом представляет Pj `Publisher` экземпляра в `Publishers` набора сущностей.</span><span class="sxs-lookup"><span data-stu-id="4efbe-116">Similarly, Pj represents a `Publisher` instance in the `Publishers` entity set.</span></span> <span data-ttu-id="4efbe-117">BiPj представляет экземпляр `PublishedBy` ассоциации в `PublishedBy` набора ассоциаций.</span><span class="sxs-lookup"><span data-stu-id="4efbe-117">BiPj represents an instance of the `PublishedBy` association in the `PublishedBy` association set.</span></span>  
  
 <span data-ttu-id="4efbe-118">![Задает пример](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")</span><span class="sxs-lookup"><span data-stu-id="4efbe-118">![Sets Example](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")</span></span>  
  
 <span data-ttu-id="4efbe-119">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует доменный язык DSL, называемый языком определения концептуальной схемы ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) для определения концептуальных моделей.</span><span class="sxs-lookup"><span data-stu-id="4efbe-119">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a DSL called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="4efbe-120">Далее на языке CSDL определяется контейнер сущностей с одним набором ассоциаций для каждой ассоциации на приведенной выше схеме.</span><span class="sxs-lookup"><span data-stu-id="4efbe-120">The following CSDL defines an entity container with one association set for each association in the diagram above.</span></span> <span data-ttu-id="4efbe-121">Обратите внимание, что конечные точки набора ассоциаций определяются как часть каждого определения набора ассоциаций.</span><span class="sxs-lookup"><span data-stu-id="4efbe-121">Note that association set ends are defined as part of each association set definition.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="4efbe-122">См. также</span><span class="sxs-lookup"><span data-stu-id="4efbe-122">See Also</span></span>  
 [<span data-ttu-id="4efbe-123">Основные понятия модели EDM</span><span class="sxs-lookup"><span data-stu-id="4efbe-123">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="4efbe-124">Сущностная модель данных</span><span class="sxs-lookup"><span data-stu-id="4efbe-124">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
