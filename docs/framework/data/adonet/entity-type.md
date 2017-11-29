---
title: "тип сущности"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6dee9ab-9e4a-48f2-a169-3f79cc15821c
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 1b84ff5a55cff4548539e81b16406e234dcb43f9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="entity-type"></a><span data-ttu-id="c6748-102">тип сущности</span><span class="sxs-lookup"><span data-stu-id="c6748-102">entity type</span></span>
<span data-ttu-id="c6748-103">*Тип сущности* это фундаментальный блок построения для описания структуры данных с помощью модели данных сущности (EDM).</span><span class="sxs-lookup"><span data-stu-id="c6748-103">The *entity type* is the fundamental building block for describing the structure of data with the Entity Data Model (EDM).</span></span> <span data-ttu-id="c6748-104">В концептуальной модели тип сущности представляет структуру основных концептуальных элементов верхнего уровня, таких как клиенты или заказы.</span><span class="sxs-lookup"><span data-stu-id="c6748-104">In a conceptual model, an entity type represents the structure of top-level concepts, such as customers or orders.</span></span> <span data-ttu-id="c6748-105">Тип сущности - это шаблон для экземпляров типов сущностей.</span><span class="sxs-lookup"><span data-stu-id="c6748-105">An entity type is a template for entity type instances.</span></span> <span data-ttu-id="c6748-106">Каждый шаблон содержит следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="c6748-106">Each template contains the following information:</span></span>  
  
-   <span data-ttu-id="c6748-107">Уникальное имя.</span><span class="sxs-lookup"><span data-stu-id="c6748-107">A unique name.</span></span> <span data-ttu-id="c6748-108">(Обязательно).</span><span class="sxs-lookup"><span data-stu-id="c6748-108">(Required.)</span></span>  
  
-   <span data-ttu-id="c6748-109">[Ключ сущности](../../../../docs/framework/data/adonet/entity-key.md) определяется одно или несколько свойств.</span><span class="sxs-lookup"><span data-stu-id="c6748-109">An [entity key](../../../../docs/framework/data/adonet/entity-key.md) defined by one or more properties.</span></span> <span data-ttu-id="c6748-110">(Обязательно).</span><span class="sxs-lookup"><span data-stu-id="c6748-110">(Required.)</span></span>  
  
-   <span data-ttu-id="c6748-111">Данные в виде [свойства](../../../../docs/framework/data/adonet/property.md).</span><span class="sxs-lookup"><span data-stu-id="c6748-111">Data in the form of [properties](../../../../docs/framework/data/adonet/property.md).</span></span> <span data-ttu-id="c6748-112">(Необязательно.)</span><span class="sxs-lookup"><span data-stu-id="c6748-112">(Optional.)</span></span>  
  
-   <span data-ttu-id="c6748-113">[Свойства навигации](../../../../docs/framework/data/adonet/navigation-property.md) , которые позволяют переходить от одного [окончания](../../../../docs/framework/data/adonet/association-end.md) из [ассоциации](../../../../docs/framework/data/adonet/association-type.md) к другой стороне.</span><span class="sxs-lookup"><span data-stu-id="c6748-113">[Navigation properties](../../../../docs/framework/data/adonet/navigation-property.md) that allow for navigation from one [end](../../../../docs/framework/data/adonet/association-end.md) of an [association](../../../../docs/framework/data/adonet/association-type.md) to the other end.</span></span> <span data-ttu-id="c6748-114">(Необязательный параметр).</span><span class="sxs-lookup"><span data-stu-id="c6748-114">(Optional)</span></span>  
  
 <span data-ttu-id="c6748-115">В приложении экземпляр типа сущности представляет определенный объект (например, определенного клиента или заказ).</span><span class="sxs-lookup"><span data-stu-id="c6748-115">In an application, an instance of an entity type represents a specific object (such as a specific customer or order).</span></span> <span data-ttu-id="c6748-116">Каждый экземпляр типа сущности должен иметь уникальный [ключ сущности](../../../../docs/framework/data/adonet/entity-key.md) в [набора сущностей](../../../../docs/framework/data/adonet/entity-set.md).</span><span class="sxs-lookup"><span data-stu-id="c6748-116">Each instance of an entity type must have a unique [entity key](../../../../docs/framework/data/adonet/entity-key.md) within an [entity set](../../../../docs/framework/data/adonet/entity-set.md).</span></span>  
  
 <span data-ttu-id="c6748-117">Два экземпляра типа сущности считаются равными, только если они являются экземплярами одного типа и значения их ключей сущности равны.</span><span class="sxs-lookup"><span data-stu-id="c6748-117">Two entity type instances are considered equal only if they are of the same type and the values of their entity keys are the same.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6748-118">Пример</span><span class="sxs-lookup"><span data-stu-id="c6748-118">Example</span></span>  
 <span data-ttu-id="c6748-119">На приведенной ниже схеме показана концептуальная модель с тремя типами сущностей: `Book`, `Publisher` и `Author`.</span><span class="sxs-lookup"><span data-stu-id="c6748-119">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`:</span></span>  
  
 <span data-ttu-id="c6748-120">![Пример модели](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="c6748-120">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="c6748-121">Обратите внимание, что свойства каждого типа сущности, составляющего его ключ сущности, обозначаются знаком «(Ключ)».</span><span class="sxs-lookup"><span data-stu-id="c6748-121">Note that the properties of each entity type that make up its entity key are denoted with "(Key)".</span></span>  
  
 <span data-ttu-id="c6748-122">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) для определения концептуальных моделей.</span><span class="sxs-lookup"><span data-stu-id="c6748-122">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="c6748-123">Ниже на языке CSDL определяется тип сущности `Book`, который ранее приводился в схеме.</span><span class="sxs-lookup"><span data-stu-id="c6748-123">The following CSDL defines the `Book` entity type shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## <a name="see-also"></a><span data-ttu-id="c6748-124">См. также</span><span class="sxs-lookup"><span data-stu-id="c6748-124">See Also</span></span>  
 [<span data-ttu-id="c6748-125">Основные понятия модели данных сущности</span><span class="sxs-lookup"><span data-stu-id="c6748-125">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="c6748-126">Модель EDM</span><span class="sxs-lookup"><span data-stu-id="c6748-126">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)  
 [<span data-ttu-id="c6748-127">facet</span><span class="sxs-lookup"><span data-stu-id="c6748-127">facet</span></span>](../../../../docs/framework/data/adonet/facet.md)
