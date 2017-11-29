---
title: "набор ассоциаций"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a65247b6-ce59-44ea-974c-14ae20a7995f
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: db293cbc636d0ae4e532f24b2852444395f603c3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="association-set"></a><span data-ttu-id="3510e-102">набор ассоциаций</span><span class="sxs-lookup"><span data-stu-id="3510e-102">association set</span></span>
<span data-ttu-id="3510e-103">*Набора ассоциаций* — это логический контейнер для [ассоциации](../../../../docs/framework/data/adonet/association-type.md) экземпляров того же типа.</span><span class="sxs-lookup"><span data-stu-id="3510e-103">An *association set* is a logical container for [association](../../../../docs/framework/data/adonet/association-type.md) instances of the same type.</span></span> <span data-ttu-id="3510e-104">Набор ассоциаций не является конструктом моделирования данных, то есть не описывает структуру данных или связи.</span><span class="sxs-lookup"><span data-stu-id="3510e-104">An association set is not a data modeling construct; that is, it does not describe the structure of data or relationships.</span></span> <span data-ttu-id="3510e-105">Вместо этого ассоциация обеспечивает конструкт для среды размещения или хранения (например, для среды CLR или базы данных сервера SQL), позволяя группировать экземпляры ассоциаций так, чтобы они были сопоставлены хранилищу данных.</span><span class="sxs-lookup"><span data-stu-id="3510e-105">Instead, an association set provides a construct for a hosting or storage environment (such as the common language runtime or a SQL Server database) to group association instances so that they can be mapped to a data store.</span></span>  
  
 <span data-ttu-id="3510e-106">Набор ассоциаций определяется внутри [контейнер сущностей](../../../../docs/framework/data/adonet/entity-container.md), который является логической группой [наборов сущностей](../../../../docs/framework/data/adonet/entity-set.md) и наборы ассоциаций.</span><span class="sxs-lookup"><span data-stu-id="3510e-106">An association set is defined within an [entity container](../../../../docs/framework/data/adonet/entity-container.md), which is a logical grouping of [entity sets](../../../../docs/framework/data/adonet/entity-set.md) and association sets.</span></span>  
  
 <span data-ttu-id="3510e-107">Определение набора ассоциаций содержит следующую информацию.</span><span class="sxs-lookup"><span data-stu-id="3510e-107">A definition for an association set contains the following information:</span></span>  
  
-   <span data-ttu-id="3510e-108">Имя набора ассоциаций.</span><span class="sxs-lookup"><span data-stu-id="3510e-108">The association set name.</span></span> <span data-ttu-id="3510e-109">(Обязательный атрибут).</span><span class="sxs-lookup"><span data-stu-id="3510e-109">(Required)</span></span>  
  
-   <span data-ttu-id="3510e-110">Ассоциация, экземпляры которой будут являться содержимым.</span><span class="sxs-lookup"><span data-stu-id="3510e-110">The association of which it will contain instances.</span></span> <span data-ttu-id="3510e-111">(Обязательный атрибут).</span><span class="sxs-lookup"><span data-stu-id="3510e-111">(Required)</span></span>  
  
-   <span data-ttu-id="3510e-112">Два [конечные точки набора ассоциаций](../../../../docs/framework/data/adonet/association-set-end.md).</span><span class="sxs-lookup"><span data-stu-id="3510e-112">Two [association set ends](../../../../docs/framework/data/adonet/association-set-end.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3510e-113">Пример</span><span class="sxs-lookup"><span data-stu-id="3510e-113">Example</span></span>  
 <span data-ttu-id="3510e-114">На приведенной ниже схеме показана концептуальная модель с двумя ассоциациями: `PublishedBy` и `WrittenBy`.</span><span class="sxs-lookup"><span data-stu-id="3510e-114">The diagram below shows a conceptual model with two associations: `PublishedBy`, and `WrittenBy`.</span></span> <span data-ttu-id="3510e-115">Информации о наборах ассоциаций не содержится в схеме, однако на следующей схеме показан пример наборов ассоциаций и наборов сущностей на основе этой модели.</span><span class="sxs-lookup"><span data-stu-id="3510e-115">Although information about association sets is not conveyed in the diagram, the next diagram shows an example of association sets and entity sets based on this model.</span></span>  
  
 <span data-ttu-id="3510e-116">![Пример модели](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="3510e-116">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="3510e-117">В следующем примере показан набор ассоциаций (`PublishedBy`) и два набора сущностей (`Books` и `Publishers`) на основе приведенной выше концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="3510e-117">The following example shows an association set (`PublishedBy`) and two entity sets (`Books` and `Publishers`) based on the conceptual model shown above.</span></span> <span data-ttu-id="3510e-118">Бизнес-аналитики в `Books` набор сущностей представляет экземпляр `Book` тип сущности во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="3510e-118">Bi in the `Books` entity set represents an instance of the `Book` entity type at run time.</span></span> <span data-ttu-id="3510e-119">Аналогичным образом представляет Pj `Publisher` экземпляра в `Publishers` набора сущностей.</span><span class="sxs-lookup"><span data-stu-id="3510e-119">Similarly, Pj represents a `Publisher` instance in the `Publishers` entity set.</span></span> <span data-ttu-id="3510e-120">BiPj представляет экземпляр `PublishedBy` ассоциации в `PublishedBy` набора ассоциаций.</span><span class="sxs-lookup"><span data-stu-id="3510e-120">BiPj represents an instance of the `PublishedBy` association in the `PublishedBy` association set.</span></span>  
  
 <span data-ttu-id="3510e-121">![Задает пример](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")</span><span class="sxs-lookup"><span data-stu-id="3510e-121">![Sets Example](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")</span></span>  
  
 <span data-ttu-id="3510e-122">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) для определения концептуальных моделей.</span><span class="sxs-lookup"><span data-stu-id="3510e-122">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="3510e-123">Далее на языке CSDL определяется контейнер сущностей с одним набором ассоциаций для каждой ассоциации на приведенной выше схеме.</span><span class="sxs-lookup"><span data-stu-id="3510e-123">The following CSDL defines an entity container with one association set for each association in the diagram above.</span></span> <span data-ttu-id="3510e-124">Обратите внимание, что имя и ассоциация для каждого набора ассоциаций определены при помощи атрибутов XML.</span><span class="sxs-lookup"><span data-stu-id="3510e-124">Note that the name and association for each association set are defined using XML attributes.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
 <span data-ttu-id="3510e-125">Можно определить несколько наборов ассоциаций на одну ассоциацию, при условии, что нет общей папки связи двух наборов [конечная точка набора ассоциаций](../../../../docs/framework/data/adonet/association-set-end.md).</span><span class="sxs-lookup"><span data-stu-id="3510e-125">It is possible to define multiple association sets per association, as long as no two association sets share an [association set end](../../../../docs/framework/data/adonet/association-set-end.md).</span></span> <span data-ttu-id="3510e-126">Далее на языке CSDL определяется контейнер сущностей с двумя наборами ассоциаций для ассоциации `WrittenBy`:</span><span class="sxs-lookup"><span data-stu-id="3510e-126">The following CSDL defines an entity container with two association sets for the `WrittenBy` association.</span></span> <span data-ttu-id="3510e-127">Обратите внимание, что несколько наборов сущностей были определены для типов сущностей `Book` и `Author` и что наборы ассоциаций не имеют одной и той же конечной точки ассоциации.</span><span class="sxs-lookup"><span data-stu-id="3510e-127">Notice that multiple entity sets have been defined for the `Book` and `Author` entity types and that no association set shares an association set end.</span></span>  
  
 [!code-xml[EDM_Example_Model#MultipleAssociationSets](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#multipleassociationsets)]  
  
## <a name="see-also"></a><span data-ttu-id="3510e-128">См. также</span><span class="sxs-lookup"><span data-stu-id="3510e-128">See Also</span></span>  
 [<span data-ttu-id="3510e-129">Основные понятия модели данных сущности</span><span class="sxs-lookup"><span data-stu-id="3510e-129">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="3510e-130">Модель EDM</span><span class="sxs-lookup"><span data-stu-id="3510e-130">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)  
 [<span data-ttu-id="3510e-131">Свойство внешнего ключа</span><span class="sxs-lookup"><span data-stu-id="3510e-131">foreign key property</span></span>](../../../../docs/framework/data/adonet/foreign-key-property.md)
