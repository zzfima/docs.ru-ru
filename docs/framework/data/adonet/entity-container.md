---
title: "контейнер сущностей"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 16e80405-2c75-42fc-b0e4-b1df53b1c584
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 5ac4383e68aad49af1a65988d9993f6fa018b31a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="entity-container"></a><span data-ttu-id="006e5-102">контейнер сущностей</span><span class="sxs-lookup"><span data-stu-id="006e5-102">entity container</span></span>
<span data-ttu-id="006e5-103">*Контейнер сущностей* представляет собой логическое группирование [наборов сущностей](../../../../docs/framework/data/adonet/entity-set.md), [наборов ассоциаций](../../../../docs/framework/data/adonet/association-set.md), и [функции imports](../../../../docs/framework/data/adonet/model-declared-function.md).</span><span class="sxs-lookup"><span data-stu-id="006e5-103">An *entity container* is a logical grouping of [entity sets](../../../../docs/framework/data/adonet/entity-set.md), [association sets](../../../../docs/framework/data/adonet/association-set.md), and [function imports](../../../../docs/framework/data/adonet/model-declared-function.md).</span></span>  
  
 <span data-ttu-id="006e5-104">Для контейнера сущностей, определенного в концептуальной модели, должны выполняться следующие условия.</span><span class="sxs-lookup"><span data-stu-id="006e5-104">The following must be true of an entity container defined in a conceptual model:</span></span>  
  
-   <span data-ttu-id="006e5-105">В каждой концептуальной модели должен быть определен по крайней мере один контейнер сущностей.</span><span class="sxs-lookup"><span data-stu-id="006e5-105">At least one entity container must be defined in each conceptual model.</span></span>  
  
-   <span data-ttu-id="006e5-106">Контейнер сущностей должен иметь уникальное имя внутри концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="006e5-106">The entity container must have a unique name within each conceptual model.</span></span>  
  
 <span data-ttu-id="006e5-107">Контейнер сущностей может определять наборы сущностей или наборы ассоциаций, которые используют типы сущностей или ассоциации, определенные в одном или нескольких пространствах имен.</span><span class="sxs-lookup"><span data-stu-id="006e5-107">An entity container can define entity sets or association sets that use entity types or associations defined in one or more namespaces.</span></span> <span data-ttu-id="006e5-108">Дополнительные сведения см. в разделе [модель EDM: пространства имен](../../../../docs/framework/data/adonet/entity-data-model-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="006e5-108">For more information, see [Entity Data Model: Namespaces](../../../../docs/framework/data/adonet/entity-data-model-namespaces.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="006e5-109">Пример</span><span class="sxs-lookup"><span data-stu-id="006e5-109">Example</span></span>  
 <span data-ttu-id="006e5-110">На приведенной ниже схеме показана концептуальная модель с тремя типами сущностей: `Book`, `Publisher` и `Author`.</span><span class="sxs-lookup"><span data-stu-id="006e5-110">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span>  <span data-ttu-id="006e5-111">Дополнительные сведения см. в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="006e5-111">See the next example for more information.</span></span>  
  
 <span data-ttu-id="006e5-112">![Пример модели](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="006e5-112">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="006e5-113">Схема не содержит сведений о контейнере сущностей, тем не менее, концептуальная модель должна определять контейнер сущностей.</span><span class="sxs-lookup"><span data-stu-id="006e5-113">Although the diagram does not convey entity container information, the conceptual model must define an entity container.</span></span> <span data-ttu-id="006e5-114">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует доменный язык DSL, называемый языком определения концептуальной схемы ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) для определения концептуальных моделей.</span><span class="sxs-lookup"><span data-stu-id="006e5-114">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a DSL called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="006e5-115">Далее на языке CSDL определяется контейнер сущностей для концептуальной модели, приведенной на схеме выше.</span><span class="sxs-lookup"><span data-stu-id="006e5-115">The following CSDL defines an entity container for the conceptual model shown in the diagram above.</span></span> <span data-ttu-id="006e5-116">Обратите внимание, что имя контейнера сущностей определяется в атрибуте XML.</span><span class="sxs-lookup"><span data-stu-id="006e5-116">Note that the entity container name is defined in an XML attribute.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="006e5-117">См. также</span><span class="sxs-lookup"><span data-stu-id="006e5-117">See Also</span></span>  
 [<span data-ttu-id="006e5-118">Основные понятия модели данных сущности</span><span class="sxs-lookup"><span data-stu-id="006e5-118">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="006e5-119">Модель EDM</span><span class="sxs-lookup"><span data-stu-id="006e5-119">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
