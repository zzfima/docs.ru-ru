---
title: "набор сущностей"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59ec6ab0-88e5-4d25-b112-7a4eccbe61f0
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 050c73d3fd9146c8eee83baf1bd504acc18c8718
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="entity-set"></a><span data-ttu-id="2c7cd-102">набор сущностей</span><span class="sxs-lookup"><span data-stu-id="2c7cd-102">entity set</span></span>
<span data-ttu-id="2c7cd-103">*Набора сущностей* — это логический контейнер для экземпляров [тип сущности](../../../../docs/framework/data/adonet/entity-type.md) и экземпляров любого типа, производного от этого типа сущности.</span><span class="sxs-lookup"><span data-stu-id="2c7cd-103">An *entity set* is a logical container for instances of an [entity type](../../../../docs/framework/data/adonet/entity-type.md) and instances of any type derived from that entity type.</span></span> <span data-ttu-id="2c7cd-104">(Сведения о производных типов см. в разделе [модель EDM: наследование](../../../../docs/framework/data/adonet/entity-data-model-inheritance.md).) Связь между типом сущности и набором сущностей схожа со связью между строкой и таблицей в реляционной базе данных. Как и строка, тип сущности описывает структуру данных, и, как и таблица, набор сущностей содержит экземпляры данной структуры.</span><span class="sxs-lookup"><span data-stu-id="2c7cd-104">(For information about derived types, see [Entity Data Model: Inheritance](../../../../docs/framework/data/adonet/entity-data-model-inheritance.md).) The relationship between an entity type and an entity set is analogous to the relationship between a row and a table in a relational database: Like a row, an entity type describes data structure, and, like a table, an entity set contains instances of a given structure.</span></span> <span data-ttu-id="2c7cd-105">Набор сущностей не является конструктом моделирования данных; он не описывает структуру данных.</span><span class="sxs-lookup"><span data-stu-id="2c7cd-105">An entity set is not a data modeling construct; it does not describe the structure of data.</span></span> <span data-ttu-id="2c7cd-106">Вместо этого набор сущностей обеспечивает конструкт для среды размещения или хранения (например, для среды CLR или базы данных сервера SQL), позволяя группировать экземпляры типа сущности так, чтобы они были сопоставлены хранилищу данных.</span><span class="sxs-lookup"><span data-stu-id="2c7cd-106">Instead, an entity set provides a construct for a hosting or storage environment (such as the common language runtime or a SQL Server database) to group entity type instances so that they can be mapped to a data store.</span></span>  
  
 <span data-ttu-id="2c7cd-107">Набор сущностей, определенных в [контейнер сущностей](../../../../docs/framework/data/adonet/entity-container.md), который является логической группой наборов сущностей и [наборов ассоциаций](../../../../docs/framework/data/adonet/association-set.md).</span><span class="sxs-lookup"><span data-stu-id="2c7cd-107">An entity set is defined within an [entity container](../../../../docs/framework/data/adonet/entity-container.md), which is a logical grouping of entity sets and [association sets](../../../../docs/framework/data/adonet/association-set.md).</span></span>  
  
 <span data-ttu-id="2c7cd-108">Чтобы экземпляр типа сущности существовал в наборе сущности, должны быть выполнены следующие условия.</span><span class="sxs-lookup"><span data-stu-id="2c7cd-108">For an entity type instance to exist in an entity set, the following must be true:</span></span>  
  
-   <span data-ttu-id="2c7cd-109">Тип экземпляра является либо тем же, что и тип сущности, в котором находится набор сущностей, либо подтипом типа сущности.</span><span class="sxs-lookup"><span data-stu-id="2c7cd-109">The type of the instance is either the same as the entity type on which the entity set is based, or the type of the instance is a subtype of the entity type.</span></span>  
  
-   <span data-ttu-id="2c7cd-110">[Ключ сущности](../../../../docs/framework/data/adonet/entity-key.md) для экземпляра является уникальным в пределах набора сущностей.</span><span class="sxs-lookup"><span data-stu-id="2c7cd-110">The [entity key](../../../../docs/framework/data/adonet/entity-key.md) for the instance is unique within the entity set.</span></span>  
  
-   <span data-ttu-id="2c7cd-111">Экземпляр не существует ни в каком другом наборе сущностей.</span><span class="sxs-lookup"><span data-stu-id="2c7cd-111">The instance does not exist in any other entity set.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2c7cd-112">Несколько наборов сущностей могут быть определены при помощи одного и того же типа сущности, однако экземпляр одного типа сущности может существовать только в одном наборе сущностей.</span><span class="sxs-lookup"><span data-stu-id="2c7cd-112">Multiple entity sets can be defined using the same entity type, but an instance of a given entity type can only exist in one entity set.</span></span>  
  
 <span data-ttu-id="2c7cd-113">Нет необходимости определять набор сущностей для каждого типа сущности в концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="2c7cd-113">You do not have to define an entity set for each entity type in a conceptual model.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c7cd-114">Пример</span><span class="sxs-lookup"><span data-stu-id="2c7cd-114">Example</span></span>  
 <span data-ttu-id="2c7cd-115">На приведенной ниже схеме показана концептуальная модель с тремя типами сущностей: `Book`, `Publisher` и `Author`.</span><span class="sxs-lookup"><span data-stu-id="2c7cd-115">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span>  
  
 <span data-ttu-id="2c7cd-116">![Пример модели](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="2c7cd-116">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="2c7cd-117">На следующей схеме показаны два набора сущностей (`Books` и `Publishers`) и набор ассоциаций (`PublishedBy`), основанный на приведенной выше концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="2c7cd-117">The following diagram shows two entity sets (`Books` and `Publishers`) and an association set (`PublishedBy`) based on the conceptual model shown above.</span></span> <span data-ttu-id="2c7cd-118">Бизнес-аналитики в `Books` набор сущностей представляет экземпляр `Book` тип сущности во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="2c7cd-118">Bi in the `Books` entity set represents an instance of the `Book` entity type at run time.</span></span> <span data-ttu-id="2c7cd-119">Подобным образом представляют собой Pj `Publisher` экземпляра в `Publishers` набора сущностей.</span><span class="sxs-lookup"><span data-stu-id="2c7cd-119">Similarly, Pj represent a `Publisher` instance in the `Publishers` entity set.</span></span> <span data-ttu-id="2c7cd-120">BiPj представляет экземпляр `PublishedBy` ассоциации в `PublishedBy` набора ассоциаций.</span><span class="sxs-lookup"><span data-stu-id="2c7cd-120">BiPj represents an instance of the `PublishedBy` association in the `PublishedBy` association set.</span></span>  
  
 <span data-ttu-id="2c7cd-121">![Задает пример](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")</span><span class="sxs-lookup"><span data-stu-id="2c7cd-121">![Sets Example](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")</span></span>  
  
 <span data-ttu-id="2c7cd-122">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) для определения концептуальных моделей.</span><span class="sxs-lookup"><span data-stu-id="2c7cd-122">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="2c7cd-123">Далее язык CSDL определяет контейнер сущностей с одним набором сущностей для каждого типа сущностей в приведенной выше концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="2c7cd-123">The following CSDL defines an entity container with one entity set for each entity type in the conceptual model shown above.</span></span> <span data-ttu-id="2c7cd-124">Обратите внимание, что имя и тип сущности для каждого набора сущностей определены при помощи атрибутов XML.</span><span class="sxs-lookup"><span data-stu-id="2c7cd-124">Note that the name and entity type for each entity set are defined using XML attributes.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
 <span data-ttu-id="2c7cd-125">Предусмотрена возможность определять несколько наборов сущностей на тип (модель MEST).</span><span class="sxs-lookup"><span data-stu-id="2c7cd-125">It is possible to define multiple entity sets per type (MEST).</span></span> <span data-ttu-id="2c7cd-126">Далее язык CSDL определяет контейнер сущностей с двумя наборами сущностей для типа сущности `Book`.</span><span class="sxs-lookup"><span data-stu-id="2c7cd-126">The following CSDL defines an entity container with two entity sets for the `Book` entity type:</span></span>  
  
 [!code-xml[EDM_Example_Model#MESTExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#mestexample)]  
  
## <a name="see-also"></a><span data-ttu-id="2c7cd-127">См. также</span><span class="sxs-lookup"><span data-stu-id="2c7cd-127">See Also</span></span>  
 [<span data-ttu-id="2c7cd-128">Основные понятия модели EDM</span><span class="sxs-lookup"><span data-stu-id="2c7cd-128">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="2c7cd-129">Сущностная модель данных</span><span class="sxs-lookup"><span data-stu-id="2c7cd-129">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
