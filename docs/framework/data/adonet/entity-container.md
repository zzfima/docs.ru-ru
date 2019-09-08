---
title: контейнер сущностей
ms.date: 03/30/2017
ms.assetid: 16e80405-2c75-42fc-b0e4-b1df53b1c584
ms.openlocfilehash: 95740fb9d8b357a4fa160af6fdafb139711283cd
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795258"
---
# <a name="entity-container"></a><span data-ttu-id="e857e-102">контейнер сущностей</span><span class="sxs-lookup"><span data-stu-id="e857e-102">entity container</span></span>
<span data-ttu-id="e857e-103">*Контейнер сущностей* — это логическая группа [наборов сущностей](entity-set.md), [наборов ассоциаций](association-set.md)и [импортов функций](model-declared-function.md).</span><span class="sxs-lookup"><span data-stu-id="e857e-103">An *entity container* is a logical grouping of [entity sets](entity-set.md), [association sets](association-set.md), and [function imports](model-declared-function.md).</span></span>  
  
 <span data-ttu-id="e857e-104">Для контейнера сущностей, определенного в концептуальной модели, должны выполняться следующие условия.</span><span class="sxs-lookup"><span data-stu-id="e857e-104">The following must be true of an entity container defined in a conceptual model:</span></span>  
  
- <span data-ttu-id="e857e-105">В каждой концептуальной модели должен быть определен по крайней мере один контейнер сущностей.</span><span class="sxs-lookup"><span data-stu-id="e857e-105">At least one entity container must be defined in each conceptual model.</span></span>  
  
- <span data-ttu-id="e857e-106">Контейнер сущностей должен иметь уникальное имя внутри концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="e857e-106">The entity container must have a unique name within each conceptual model.</span></span>  
  
 <span data-ttu-id="e857e-107">Контейнер сущностей может определять наборы сущностей или наборы ассоциаций, которые используют типы сущностей или ассоциации, определенные в одном или нескольких пространствах имен.</span><span class="sxs-lookup"><span data-stu-id="e857e-107">An entity container can define entity sets or association sets that use entity types or associations defined in one or more namespaces.</span></span> <span data-ttu-id="e857e-108">Дополнительные сведения см. в [разделе EDM: Пространства имен](entity-data-model-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="e857e-108">For more information, see [Entity Data Model: Namespaces](entity-data-model-namespaces.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e857e-109">Пример</span><span class="sxs-lookup"><span data-stu-id="e857e-109">Example</span></span>  
 <span data-ttu-id="e857e-110">На приведенной ниже схеме показана концептуальная модель с тремя типами сущностей: `Book`, `Publisher` и `Author`.</span><span class="sxs-lookup"><span data-stu-id="e857e-110">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span>  <span data-ttu-id="e857e-111">Дополнительные сведения см. в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="e857e-111">See the next example for more information.</span></span>  
  
 ![Пример модели с тремя типами сущностей](./media/entity-container/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="e857e-113">Схема не содержит сведений о контейнере сущностей, тем не менее, концептуальная модель должна определять контейнер сущностей.</span><span class="sxs-lookup"><span data-stu-id="e857e-113">Although the diagram does not convey entity container information, the conceptual model must define an entity container.</span></span> <span data-ttu-id="e857e-114">В [Entity Framework ADO.NET](./ef/index.md) для определения концептуальных моделей используется DSL, именуемое языком определения концептуальной схемы ([CSDL](./ef/language-reference/csdl-specification.md)).</span><span class="sxs-lookup"><span data-stu-id="e857e-114">The [ADO.NET Entity Framework](./ef/index.md) uses a DSL called conceptual schema definition language ([CSDL](./ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="e857e-115">Далее на языке CSDL определяется контейнер сущностей для концептуальной модели, приведенной на схеме выше.</span><span class="sxs-lookup"><span data-stu-id="e857e-115">The following CSDL defines an entity container for the conceptual model shown in the diagram above.</span></span> <span data-ttu-id="e857e-116">Обратите внимание, что имя контейнера сущностей определяется в атрибуте XML.</span><span class="sxs-lookup"><span data-stu-id="e857e-116">Note that the entity container name is defined in an XML attribute.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="e857e-117">См. также</span><span class="sxs-lookup"><span data-stu-id="e857e-117">See also</span></span>

- [<span data-ttu-id="e857e-118">Основные понятия модели EDM</span><span class="sxs-lookup"><span data-stu-id="e857e-118">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="e857e-119">Сущностная модель данных</span><span class="sxs-lookup"><span data-stu-id="e857e-119">Entity Data Model</span></span>](entity-data-model.md)
