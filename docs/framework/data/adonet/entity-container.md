---
title: контейнер сущностей
ms.date: 03/30/2017
ms.assetid: 16e80405-2c75-42fc-b0e4-b1df53b1c584
ms.openlocfilehash: 4a629a800df63c67dc17d3fc1531a9862861e9c4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144070"
---
# <a name="entity-container"></a><span data-ttu-id="44b7d-102">контейнер сущностей</span><span class="sxs-lookup"><span data-stu-id="44b7d-102">entity container</span></span>
<span data-ttu-id="44b7d-103">*Контейнер сущностей* — это логическая группа из [наборы сущностей](../../../../docs/framework/data/adonet/entity-set.md), [наборы ассоциаций](../../../../docs/framework/data/adonet/association-set.md), и [функции imports](../../../../docs/framework/data/adonet/model-declared-function.md).</span><span class="sxs-lookup"><span data-stu-id="44b7d-103">An *entity container* is a logical grouping of [entity sets](../../../../docs/framework/data/adonet/entity-set.md), [association sets](../../../../docs/framework/data/adonet/association-set.md), and [function imports](../../../../docs/framework/data/adonet/model-declared-function.md).</span></span>  
  
 <span data-ttu-id="44b7d-104">Для контейнера сущностей, определенного в концептуальной модели, должны выполняться следующие условия.</span><span class="sxs-lookup"><span data-stu-id="44b7d-104">The following must be true of an entity container defined in a conceptual model:</span></span>  
  
-   <span data-ttu-id="44b7d-105">В каждой концептуальной модели должен быть определен по крайней мере один контейнер сущностей.</span><span class="sxs-lookup"><span data-stu-id="44b7d-105">At least one entity container must be defined in each conceptual model.</span></span>  
  
-   <span data-ttu-id="44b7d-106">Контейнер сущностей должен иметь уникальное имя внутри концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="44b7d-106">The entity container must have a unique name within each conceptual model.</span></span>  
  
 <span data-ttu-id="44b7d-107">Контейнер сущностей может определять наборы сущностей или наборы ассоциаций, которые используют типы сущностей или ассоциации, определенные в одном или нескольких пространствах имен.</span><span class="sxs-lookup"><span data-stu-id="44b7d-107">An entity container can define entity sets or association sets that use entity types or associations defined in one or more namespaces.</span></span> <span data-ttu-id="44b7d-108">Дополнительные сведения см. в разделе [модели EDM: Пространства имен](../../../../docs/framework/data/adonet/entity-data-model-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="44b7d-108">For more information, see [Entity Data Model: Namespaces](../../../../docs/framework/data/adonet/entity-data-model-namespaces.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="44b7d-109">Пример</span><span class="sxs-lookup"><span data-stu-id="44b7d-109">Example</span></span>  
 <span data-ttu-id="44b7d-110">На приведенной ниже схеме показана концептуальная модель с тремя типами сущностей: `Book`, `Publisher` и `Author`.</span><span class="sxs-lookup"><span data-stu-id="44b7d-110">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span>  <span data-ttu-id="44b7d-111">Дополнительные сведения см. в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="44b7d-111">See the next example for more information.</span></span>  
  
 ![Пример модели с тремя типами сущностей](./media/entity-container/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="44b7d-113">Схема не содержит сведений о контейнере сущностей, тем не менее, концептуальная модель должна определять контейнер сущностей.</span><span class="sxs-lookup"><span data-stu-id="44b7d-113">Although the diagram does not convey entity container information, the conceptual model must define an entity container.</span></span> <span data-ttu-id="44b7d-114">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует DSL, называемый языком определения концептуальной схемы ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) для определения концептуальных моделей.</span><span class="sxs-lookup"><span data-stu-id="44b7d-114">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a DSL called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="44b7d-115">Далее на языке CSDL определяется контейнер сущностей для концептуальной модели, приведенной на схеме выше.</span><span class="sxs-lookup"><span data-stu-id="44b7d-115">The following CSDL defines an entity container for the conceptual model shown in the diagram above.</span></span> <span data-ttu-id="44b7d-116">Обратите внимание, что имя контейнера сущностей определяется в атрибуте XML.</span><span class="sxs-lookup"><span data-stu-id="44b7d-116">Note that the entity container name is defined in an XML attribute.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="44b7d-117">См. также</span><span class="sxs-lookup"><span data-stu-id="44b7d-117">See also</span></span>

- [<span data-ttu-id="44b7d-118">Основные понятия модели EDM</span><span class="sxs-lookup"><span data-stu-id="44b7d-118">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="44b7d-119">EDM (модель данных с использованием сущностей)</span><span class="sxs-lookup"><span data-stu-id="44b7d-119">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
