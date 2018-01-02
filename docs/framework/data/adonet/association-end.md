---
title: "конечная точка ассоциации"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2c345213-0296-4d90-ac6d-cef179798a75
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 53e52a09533f3e1ead240ec3284371603c82ce53
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="association-end"></a><span data-ttu-id="8a654-102">конечная точка ассоциации</span><span class="sxs-lookup"><span data-stu-id="8a654-102">association end</span></span>
<span data-ttu-id="8a654-103">*Ассоциации* идентифицирует [тип сущности](../../../../docs/framework/data/adonet/entity-type.md) на одном конце [ассоциации](../../../../docs/framework/data/adonet/association-type.md) и число сущностей введите экземпляров, которые могут существовать в конечной точке ассоциации.</span><span class="sxs-lookup"><span data-stu-id="8a654-103">An *association end* identifies the [entity type](../../../../docs/framework/data/adonet/entity-type.md) on one end of an [association](../../../../docs/framework/data/adonet/association-type.md) and the number of entity type instances that can exist at that end of an association.</span></span> <span data-ttu-id="8a654-104">Элементы ассоциации определяются при определении ассоциации; ассоциация должна иметь два элемента.</span><span class="sxs-lookup"><span data-stu-id="8a654-104">Association ends are defined as part of an association; an association must have exactly two association ends.</span></span> <span data-ttu-id="8a654-105">[Свойства навигации](../../../../docs/framework/data/adonet/navigation-property.md) позволяют осуществлять переход от одного конечного элемента ассоциации к другому.</span><span class="sxs-lookup"><span data-stu-id="8a654-105">[Navigation properties](../../../../docs/framework/data/adonet/navigation-property.md) allow for navigation from one association end to the other.</span></span>  
  
 <span data-ttu-id="8a654-106">Определение конечной точки ассоциации содержит следующую информацию.</span><span class="sxs-lookup"><span data-stu-id="8a654-106">An association end definition contains the following information:</span></span>  
  
-   <span data-ttu-id="8a654-107">Один из типов сущности, участвующий в ассоциации.</span><span class="sxs-lookup"><span data-stu-id="8a654-107">One of the entity types involved in the association.</span></span> <span data-ttu-id="8a654-108">(Обязательный атрибут).</span><span class="sxs-lookup"><span data-stu-id="8a654-108">(Required)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8a654-109">Для одной ассоциации тип сущности, указанный для каждой конечной точки ассоциации, может быть одним и тем же.</span><span class="sxs-lookup"><span data-stu-id="8a654-109">For a given association, the entity type specified for each association end can be the same.</span></span> <span data-ttu-id="8a654-110">Так создается самоассоциация.</span><span class="sxs-lookup"><span data-stu-id="8a654-110">This creates a self-association.</span></span>  
  
-   <span data-ttu-id="8a654-111">[Кратность конечной точки ассоциации](../../../../docs/framework/data/adonet/association-end-multiplicity.md) , указывающее количество экземпляров типа сущности, которые могут быть на одном конце связи.</span><span class="sxs-lookup"><span data-stu-id="8a654-111">An [association end multiplicity](../../../../docs/framework/data/adonet/association-end-multiplicity.md) that indicates the number of entity type instances that can be at one end of the association.</span></span> <span data-ttu-id="8a654-112">Кратность конечной точки ассоциации может иметь значение «один» (1), «нуль или один» (0..1) или «много» (*).</span><span class="sxs-lookup"><span data-stu-id="8a654-112">An association end multiplicity can have a value of one (1), zero or one (0..1), or many (*).</span></span>  
  
-   <span data-ttu-id="8a654-113">Имя для элемента ассоциации.</span><span class="sxs-lookup"><span data-stu-id="8a654-113">A name for the association end.</span></span> <span data-ttu-id="8a654-114">(Необязательный параметр).</span><span class="sxs-lookup"><span data-stu-id="8a654-114">(Optional)</span></span>  
  
-   <span data-ttu-id="8a654-115">Сведения об операциях, которые выполняются на конечной точке ассоциации, например каскадная операция удаления.</span><span class="sxs-lookup"><span data-stu-id="8a654-115">Information about operations that are performed on the association end, such as cascade on delete.</span></span> <span data-ttu-id="8a654-116">(Необязательный параметр).</span><span class="sxs-lookup"><span data-stu-id="8a654-116">(Optional)</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a654-117">Пример</span><span class="sxs-lookup"><span data-stu-id="8a654-117">Example</span></span>  
 <span data-ttu-id="8a654-118">На приведенной ниже схеме показана концептуальная модель с двумя ассоциациями: `PublishedBy` и `WrittenBy`.</span><span class="sxs-lookup"><span data-stu-id="8a654-118">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="8a654-119">Конечные точки ассоциации для ассоциации `PublishedBy` - это типы сущности `Book` и `Publisher`.</span><span class="sxs-lookup"><span data-stu-id="8a654-119">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="8a654-120">Кратность конечной точки `Publisher` - «один» (1), а кратность конечной точки `Book` - «много» (*), что означает, что издатель публикует много книг, а одна книга публикуется одним издателем.</span><span class="sxs-lookup"><span data-stu-id="8a654-120">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (*), indicating that a publisher publishes many books and a book is published by one publisher.</span></span>  
  
 <span data-ttu-id="8a654-121">![Пример модели](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="8a654-121">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="8a654-122">Платформа ADO.NET Entity Framework использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) для определения концептуальных моделей.</span><span class="sxs-lookup"><span data-stu-id="8a654-122">The ADO.NET Entity Framework uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="8a654-123">Ниже язык определения концептуальной схемы определяет ассоциацию `PublishedBy`, которая ранее приводилась в схеме.</span><span class="sxs-lookup"><span data-stu-id="8a654-123">The CSDL below defines the `PublishedBy` association shown in the diagram above.</span></span> <span data-ttu-id="8a654-124">Обратите внимание, что тип, имя и кратность каждой конечной точки ассоциации указаны атрибутами XML (атрибуты `Type`, `Role` и `Multiplicity` соответственно).</span><span class="sxs-lookup"><span data-stu-id="8a654-124">Note that the type, name, and multiplicity of each association end are specified by XML attributes (the `Type`, `Role`, and `Multiplicity` attributes, respectively).</span></span> <span data-ttu-id="8a654-125">Дополнительные сведения об операциях, выполненных на конечной точке, указываются в элементе XML (элемент `OnDelete`).</span><span class="sxs-lookup"><span data-stu-id="8a654-125">Optional information about operations performed on an end is specified in an XML element (the `OnDelete` element).</span></span> <span data-ttu-id="8a654-126">В данном случае, если издатель удаляется, удаляются и все связанные книги.</span><span class="sxs-lookup"><span data-stu-id="8a654-126">In this case, if a publisher is deleted, so are all associated books.</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationEnd](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#associationend)]  
  
## <a name="see-also"></a><span data-ttu-id="8a654-127">См. также</span><span class="sxs-lookup"><span data-stu-id="8a654-127">See Also</span></span>  
 [<span data-ttu-id="8a654-128">Основные понятия модели EDM</span><span class="sxs-lookup"><span data-stu-id="8a654-128">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="8a654-129">Сущностная модель данных</span><span class="sxs-lookup"><span data-stu-id="8a654-129">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
