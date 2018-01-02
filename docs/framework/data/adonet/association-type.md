---
title: "тип ассоциации"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 26c409f6-06e8-4441-ac78-1b1076a3c005
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: bf109cac6446feb6cfe6b126cadcf4fc008d1579
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="association-type"></a><span data-ttu-id="ad439-102">тип ассоциации</span><span class="sxs-lookup"><span data-stu-id="ad439-102">association type</span></span>
<span data-ttu-id="ad439-103">*Тип ассоциации* (также называемый ассоциацией) это фундаментальный блок построения для описания связей в модели данных сущности (EDM).</span><span class="sxs-lookup"><span data-stu-id="ad439-103">An *association type* (also called an association) is the fundamental building block for describing relationships in the Entity Data Model (EDM).</span></span> <span data-ttu-id="ad439-104">В концептуальной модели ассоциация представляет собой связь между двумя [типов сущностей](../../../../docs/framework/data/adonet/entity-type.md) (такие как `Customer` и `Order`).</span><span class="sxs-lookup"><span data-stu-id="ad439-104">In a conceptual model, an association represents a relationship between two [entity types](../../../../docs/framework/data/adonet/entity-type.md) (such as `Customer` and `Order`).</span></span> <span data-ttu-id="ad439-105">В приложении экземпляр ассоциации представляет собой специфическую ассоциацию (такую как ассоциация между экземпляром `Customer` и экземпляром `Order`).</span><span class="sxs-lookup"><span data-stu-id="ad439-105">In an application, an instance of an association represents a specific association (such as an association between an instance of `Customer` and an instance of `Order`).</span></span> <span data-ttu-id="ad439-106">Экземпляры ассоциации логически сгруппированы в [набора ассоциаций](../../../../docs/framework/data/adonet/association-set.md).</span><span class="sxs-lookup"><span data-stu-id="ad439-106">Association instances are logically grouped in an [association set](../../../../docs/framework/data/adonet/association-set.md).</span></span>  
  
 <span data-ttu-id="ad439-107">Определение ассоциации содержит следующую информацию.</span><span class="sxs-lookup"><span data-stu-id="ad439-107">An association definition contains the following information:</span></span>  
  
-   <span data-ttu-id="ad439-108">Уникальное имя.</span><span class="sxs-lookup"><span data-stu-id="ad439-108">A unique name.</span></span> <span data-ttu-id="ad439-109">(Обязательный атрибут).</span><span class="sxs-lookup"><span data-stu-id="ad439-109">(Required)</span></span>  
  
-   <span data-ttu-id="ad439-110">Два [ассоциации](../../../../docs/framework/data/adonet/association-end.md), один для каждого типа сущности в связи.</span><span class="sxs-lookup"><span data-stu-id="ad439-110">Two [association ends](../../../../docs/framework/data/adonet/association-end.md), one for each entity type in the relationship.</span></span> <span data-ttu-id="ad439-111">(Обязательный атрибут).</span><span class="sxs-lookup"><span data-stu-id="ad439-111">(Required)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ad439-112">Ассоциация не может представлять связь между более чем двумя типами сущностей.</span><span class="sxs-lookup"><span data-stu-id="ad439-112">An association cannot represent a relationship among more than two entity types.</span></span> <span data-ttu-id="ad439-113">Ассоциация может, тем не менее, определять связь с самим собой посредством указания одного и того же типа сущности для каждой из его конечных точек ассоциаций.</span><span class="sxs-lookup"><span data-stu-id="ad439-113">An association can, however, define a self-relationship by specifying the same entity type for each of its association ends.</span></span>  
  
-   <span data-ttu-id="ad439-114">Объект [ограничение ссылочной целостности](../../../../docs/framework/data/adonet/referential-integrity-constraint.md).</span><span class="sxs-lookup"><span data-stu-id="ad439-114">A [referential integrity constraint](../../../../docs/framework/data/adonet/referential-integrity-constraint.md).</span></span> <span data-ttu-id="ad439-115">(Необязательный параметр).</span><span class="sxs-lookup"><span data-stu-id="ad439-115">(Optional)</span></span>  
  
 <span data-ttu-id="ad439-116">Каждая конечная точка ассоциации необходимо указать [кратность конечной точки ассоциации](../../../../docs/framework/data/adonet/association-end-multiplicity.md) , указывающее количество экземпляров типа сущности, которые могут быть на одном конце связи.</span><span class="sxs-lookup"><span data-stu-id="ad439-116">Each association end must specify an [association end multiplicity](../../../../docs/framework/data/adonet/association-end-multiplicity.md) that indicates the number of entity type instances that can be at one end of the association.</span></span> <span data-ttu-id="ad439-117">Кратность конечной точки ассоциации может иметь значение «один» (1), «нуль или один» (0..1) или «много» (*).</span><span class="sxs-lookup"><span data-stu-id="ad439-117">An association end multiplicity can have a value of one (1), zero or one (0..1), or many (*).</span></span> <span data-ttu-id="ad439-118">Экземпляры типа сущности на одном конце связи может осуществляться через [свойства навигации](../../../../docs/framework/data/adonet/navigation-property.md) или внешних ключей, если они предоставляются в типе сущности.</span><span class="sxs-lookup"><span data-stu-id="ad439-118">Entity type instances at one end of an association can be accessed through [navigation properties](../../../../docs/framework/data/adonet/navigation-property.md) or foreign keys if they are exposed on an entity type.</span></span> <span data-ttu-id="ad439-119">Дополнительные сведения см. в разделе [модель EDM: внешние ключи](../../../../docs/framework/data/adonet/foreign-key-property.md).</span><span class="sxs-lookup"><span data-stu-id="ad439-119">For more information, see [Entity Data Model: Foreign Keys](../../../../docs/framework/data/adonet/foreign-key-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad439-120">Пример</span><span class="sxs-lookup"><span data-stu-id="ad439-120">Example</span></span>  
 <span data-ttu-id="ad439-121">На приведенной ниже схеме показана концептуальная модель с двумя ассоциациями: `PublishedBy` и `WrittenBy`.</span><span class="sxs-lookup"><span data-stu-id="ad439-121">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="ad439-122">Конечные точки ассоциации для ассоциации `PublishedBy` - это типы сущности `Book` и `Publisher`.</span><span class="sxs-lookup"><span data-stu-id="ad439-122">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="ad439-123">Кратность конечной точки `Publisher` - «один» (1), а кратность конечной точки `Book` - «много» (*), что означает, что издатель публикует много книг, а одна книга публикуется одним издателем.</span><span class="sxs-lookup"><span data-stu-id="ad439-123">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (*), indicating that a publisher publishes many books and a book is published by one publisher.</span></span>  
  
 <span data-ttu-id="ad439-124">![Пример модели](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="ad439-124">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="ad439-125">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) для определения концептуальных моделей.</span><span class="sxs-lookup"><span data-stu-id="ad439-125">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="ad439-126">Далее язык CSDL определяет ассоциацию `PublishedBy`, которая ранее приводилась в схеме.</span><span class="sxs-lookup"><span data-stu-id="ad439-126">The following CSDL defines the `PublishedBy` association shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a><span data-ttu-id="ad439-127">См. также</span><span class="sxs-lookup"><span data-stu-id="ad439-127">See Also</span></span>  
 [<span data-ttu-id="ad439-128">Основные понятия модели EDM</span><span class="sxs-lookup"><span data-stu-id="ad439-128">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="ad439-129">Сущностная модель данных</span><span class="sxs-lookup"><span data-stu-id="ad439-129">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
