---
title: "свойство навигации"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d0bf1a6a-1d84-484c-b7c3-b410fd8dc0b1
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 1677ab1be071eeabd72b29c7ce61d01aaf6164a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="navigation-property"></a><span data-ttu-id="2f5a0-102">свойство навигации</span><span class="sxs-lookup"><span data-stu-id="2f5a0-102">navigation property</span></span>
<span data-ttu-id="2f5a0-103">Объект *свойство навигации* — это необязательное свойство на [тип сущности](../../../../docs/framework/data/adonet/entity-type.md) , позволяет переходить от одной [окончания](../../../../docs/framework/data/adonet/association-end.md) из [ассоциации](../../../../docs/framework/data/adonet/association-type.md) для другой конец.</span><span class="sxs-lookup"><span data-stu-id="2f5a0-103">A *navigation property* is an optional property on an [entity type](../../../../docs/framework/data/adonet/entity-type.md) that allows for navigation from one [end](../../../../docs/framework/data/adonet/association-end.md) of an [association](../../../../docs/framework/data/adonet/association-type.md) to the other end.</span></span> <span data-ttu-id="2f5a0-104">В отличие от других [свойства](../../../../docs/framework/data/adonet/property.md), свойства навигации не содержат данных.</span><span class="sxs-lookup"><span data-stu-id="2f5a0-104">Unlike other [properties](../../../../docs/framework/data/adonet/property.md), navigation properties do not carry data.</span></span>  
  
 <span data-ttu-id="2f5a0-105">Определение свойства навигации содержит следующую информацию.</span><span class="sxs-lookup"><span data-stu-id="2f5a0-105">A navigation property definition includes the following:</span></span>  
  
-   <span data-ttu-id="2f5a0-106">Имя.</span><span class="sxs-lookup"><span data-stu-id="2f5a0-106">A name.</span></span> <span data-ttu-id="2f5a0-107">(Обязательный атрибут).</span><span class="sxs-lookup"><span data-stu-id="2f5a0-107">(Required)</span></span>  
  
-   <span data-ttu-id="2f5a0-108">Ассоциация, для которой осуществляется переход.</span><span class="sxs-lookup"><span data-stu-id="2f5a0-108">The association that it navigates.</span></span> <span data-ttu-id="2f5a0-109">(Обязательный атрибут).</span><span class="sxs-lookup"><span data-stu-id="2f5a0-109">(Required)</span></span>  
  
-   <span data-ttu-id="2f5a0-110">Конечные точки ассоциации, для которой осуществляется переход.</span><span class="sxs-lookup"><span data-stu-id="2f5a0-110">The ends of the association that it navigates.</span></span> <span data-ttu-id="2f5a0-111">(Обязательный атрибут).</span><span class="sxs-lookup"><span data-stu-id="2f5a0-111">(Required)</span></span>  
  
 <span data-ttu-id="2f5a0-112">Обратите внимание, что свойства навигации являются необязательными для обоих типов сущностей, расположенных в конечных элементах ассоциации.</span><span class="sxs-lookup"><span data-stu-id="2f5a0-112">Note that navigation properties are optional on both entity types at the ends of an association.</span></span> <span data-ttu-id="2f5a0-113">Если свойство навигации было определено для типа сущности на одном конечном элементе ассоциации, то определять его для типа сущности на другом конечном элементе необязательно.</span><span class="sxs-lookup"><span data-stu-id="2f5a0-113">If you define a navigation property on one entity type at the end of an association, you do not have to define a navigation property on the entity type at the other end of the association.</span></span>  
  
 <span data-ttu-id="2f5a0-114">Тип данных свойства навигации определяется [кратность](../../../../docs/framework/data/adonet/association-end-multiplicity.md) его удаленной [ассоциации](../../../../docs/framework/data/adonet/association-end.md).</span><span class="sxs-lookup"><span data-stu-id="2f5a0-114">The data type of a navigation property is determined by the [multiplicity](../../../../docs/framework/data/adonet/association-end-multiplicity.md) of its remote [association end](../../../../docs/framework/data/adonet/association-end.md).</span></span> <span data-ttu-id="2f5a0-115">Например, предположим, что свойство навигации `OrdersNavProp` существует для типа сущности `Customer` и осуществляет навигацию по ассоциации «один ко многим» между `Customer` и `Order`.</span><span class="sxs-lookup"><span data-stu-id="2f5a0-115">For example, suppose a navigation property, `OrdersNavProp`, exists on a `Customer` entity type and navigates a one-to-many association between `Customer` and `Order`.</span></span> <span data-ttu-id="2f5a0-116">Поскольку конечная точка удаленной ассоциации для свойства навигации имеет кратность «много» (*), его тип данных - коллекция (элемент `Order`).</span><span class="sxs-lookup"><span data-stu-id="2f5a0-116">Because the remote association end for the navigation property has multiplicity of many (*), its data type is a collection (of `Order`).</span></span> <span data-ttu-id="2f5a0-117">Аналогично, если свойство навигации `CustomerNavProp` существует для типа сущности `Order`, то его тип данных будет `Customer`, поскольку кратность удаленного конечного элемента - «один» (1).</span><span class="sxs-lookup"><span data-stu-id="2f5a0-117">Similarly, if a navigation property, `CustomerNavProp`, exists on the `Order` entity type, its data type would be `Customer`, because the multiplicity of the remote end is one (1).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f5a0-118">Пример</span><span class="sxs-lookup"><span data-stu-id="2f5a0-118">Example</span></span>  
 <span data-ttu-id="2f5a0-119">На приведенной ниже схеме показана концептуальная модель с тремя типами сущностей: `Book`, `Publisher` и `Author`.</span><span class="sxs-lookup"><span data-stu-id="2f5a0-119">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="2f5a0-120">Свойства навигации, `Publisher` и `Authors`, определены относительно типа сущности «Book».</span><span class="sxs-lookup"><span data-stu-id="2f5a0-120">Navigation properties, `Publisher` and `Authors`, are defined on the Book entity type.</span></span> <span data-ttu-id="2f5a0-121">Свойство навигации `Books` определено как относительно типа сущности «Publisher», так и относительно типа сущности `Author`.</span><span class="sxs-lookup"><span data-stu-id="2f5a0-121">Navigation property `Books` is defined on both the Publisher entity type and the `Author` entity type.</span></span>  
  
 <span data-ttu-id="2f5a0-122">![Модель со свойствами навигации](../../../../docs/framework/data/adonet/media/modelwithnavprops.gif "ModelWithNavProps")</span><span class="sxs-lookup"><span data-stu-id="2f5a0-122">![Model with Navigation Properties](../../../../docs/framework/data/adonet/media/modelwithnavprops.gif "ModelWithNavProps")</span></span>  
  
 <span data-ttu-id="2f5a0-123">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) для определения концептуальных моделей.</span><span class="sxs-lookup"><span data-stu-id="2f5a0-123">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="2f5a0-124">Ниже на языке CSDL определяется тип сущности `Book`, который ранее приводился в схеме.</span><span class="sxs-lookup"><span data-stu-id="2f5a0-124">The following CSDL defines the `Book` entity type shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
 <span data-ttu-id="2f5a0-125">Обратите внимание, что атрибуты XML используются для сообщения сведений, необходимых для определения свойства навигации: атрибут `Name` содержит имя свойства, `Relationship` содержит имя ассоциации, для которой осуществляется переход, и `FromRole` и `ToRole` содержат конечные точки ассоциации.</span><span class="sxs-lookup"><span data-stu-id="2f5a0-125">Note that XML attributes are used to communicate the information necessary to define a navigation property: The attribute `Name` contains the name of the property, `Relationship` contains the name of the association it navigates, and `FromRole` and `ToRole` contain the ends of the association.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f5a0-126">См. также</span><span class="sxs-lookup"><span data-stu-id="2f5a0-126">See Also</span></span>  
 [<span data-ttu-id="2f5a0-127">Основные понятия модели данных сущности</span><span class="sxs-lookup"><span data-stu-id="2f5a0-127">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="2f5a0-128">Модель EDM</span><span class="sxs-lookup"><span data-stu-id="2f5a0-128">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
