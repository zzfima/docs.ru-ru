---
title: конечная точка набора ассоциаций
ms.date: 03/30/2017
ms.assetid: fe4bf1d3-047a-4a37-98c5-a66e70811346
ms.openlocfilehash: f7ec1ca6fcdf299b9fcfc78f299ea4c6c5267cd3
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738619"
---
# <a name="association-set-end"></a><span data-ttu-id="a2112-102">конечная точка набора ассоциаций</span><span class="sxs-lookup"><span data-stu-id="a2112-102">association set end</span></span>
<span data-ttu-id="a2112-103">*Конец набора ассоциаций* определяет [тип сущности](entity-type.md) и [набор сущностей](entity-set.md) в конце [набора ассоциаций](association-set.md).</span><span class="sxs-lookup"><span data-stu-id="a2112-103">An *association set end* identifies the [entity type](entity-type.md) and the [entity set](entity-set.md) at the end of an [association set](association-set.md).</span></span> <span data-ttu-id="a2112-104">Конечные точки набора ассоциаций определяются как часть набора ассоциаций; набор ассоциаций должен иметь ровно две конечные точки.</span><span class="sxs-lookup"><span data-stu-id="a2112-104">Association set ends are defined as part of an association set; an association set must have exactly two association set ends.</span></span>  
  
 <span data-ttu-id="a2112-105">Определение конечной точки набора ассоциаций содержит следующую информацию.</span><span class="sxs-lookup"><span data-stu-id="a2112-105">An association set end definition contains the following information:</span></span>  
  
- <span data-ttu-id="a2112-106">Один из типов сущностей, участвующих в наборе ассоциаций.</span><span class="sxs-lookup"><span data-stu-id="a2112-106">One of the entity types involved in the association set.</span></span> <span data-ttu-id="a2112-107">(Обязательный атрибут).</span><span class="sxs-lookup"><span data-stu-id="a2112-107">(Required)</span></span>  
  
- <span data-ttu-id="a2112-108">Набор сущностей для типа сущностей, участвующих в наборе ассоциаций.</span><span class="sxs-lookup"><span data-stu-id="a2112-108">The entity set for the entity type involved in the association set.</span></span> <span data-ttu-id="a2112-109">(Обязательный атрибут).</span><span class="sxs-lookup"><span data-stu-id="a2112-109">(Required)</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2112-110">Пример</span><span class="sxs-lookup"><span data-stu-id="a2112-110">Example</span></span>  
 <span data-ttu-id="a2112-111">На приведенной ниже схеме показана концептуальная модель с двумя ассоциациями: `WrittenBy` и `PublishedBy`.</span><span class="sxs-lookup"><span data-stu-id="a2112-111">The diagram below shows a conceptual model with two associations: `WrittenBy` and `PublishedBy`.</span></span>  
  
 ![Пример модели с тремя типами сущностей](./media/association-set-end/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="a2112-113">На следующей схеме показаны один набор ассоциаций (`PublishedBy` и `Books`) и два набора сущностей (`Publishers`) на основе приведенной выше концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="a2112-113">The following diagram shows an association set (`PublishedBy`) and two entity sets (`Books` and `Publishers`) based on the conceptual model shown above.</span></span> <span data-ttu-id="a2112-114">Конечные точки набора ассоциаций - это наборы сущностей `Books` и `Publishers`.</span><span class="sxs-lookup"><span data-stu-id="a2112-114">The association set ends are the `Books` and `Publishers` entity sets.</span></span> <span data-ttu-id="a2112-115">Бизнес-аналитика в наборе сущностей `Books` представляет экземпляр `Book` типа сущности во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="a2112-115">Bi in the `Books` entity set represents an instance of the `Book` entity type at run time.</span></span> <span data-ttu-id="a2112-116">Аналогичным образом PJ представляет экземпляр `Publisher` в `Publishers`ном наборе сущностей.</span><span class="sxs-lookup"><span data-stu-id="a2112-116">Similarly, Pj represents a `Publisher` instance in the `Publishers` entity set.</span></span> <span data-ttu-id="a2112-117">Бипж представляет экземпляр `PublishedBy` ассоциации в наборе ассоциаций `PublishedBy`.</span><span class="sxs-lookup"><span data-stu-id="a2112-117">BiPj represents an instance of the `PublishedBy` association in the `PublishedBy` association set.</span></span>  
  
 ![Снимок экрана, на котором показан пример набора.](./media/association-set-end/sets-example-association.gif)  
  
 <span data-ttu-id="a2112-119">В [Entity Framework ADO.NET](./ef/index.md) для определения концептуальных моделей используется DSL, именуемое языком определения концептуальной схемы ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)).</span><span class="sxs-lookup"><span data-stu-id="a2112-119">The [ADO.NET Entity Framework](./ef/index.md) uses a DSL called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="a2112-120">Далее на языке CSDL определяется контейнер сущностей с одним набором ассоциаций для каждой ассоциации на приведенной выше схеме.</span><span class="sxs-lookup"><span data-stu-id="a2112-120">The following CSDL defines an entity container with one association set for each association in the diagram above.</span></span> <span data-ttu-id="a2112-121">Обратите внимание, что конечные точки набора ассоциаций определяются как часть каждого определения набора ассоциаций.</span><span class="sxs-lookup"><span data-stu-id="a2112-121">Note that association set ends are defined as part of each association set definition.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="a2112-122">См. также</span><span class="sxs-lookup"><span data-stu-id="a2112-122">See also</span></span>

- [<span data-ttu-id="a2112-123">Основные понятия модели EDM</span><span class="sxs-lookup"><span data-stu-id="a2112-123">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="a2112-124">Сущностная модель данных</span><span class="sxs-lookup"><span data-stu-id="a2112-124">Entity Data Model</span></span>](entity-data-model.md)
