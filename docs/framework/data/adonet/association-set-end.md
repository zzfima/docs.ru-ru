---
title: конечная точка набора ассоциаций
ms.date: 03/30/2017
ms.assetid: fe4bf1d3-047a-4a37-98c5-a66e70811346
ms.openlocfilehash: 7b6c646592c1878ea30396d98b4976dc8fa0be12
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769594"
---
# <a name="association-set-end"></a><span data-ttu-id="662a9-102">конечная точка набора ассоциаций</span><span class="sxs-lookup"><span data-stu-id="662a9-102">association set end</span></span>
<span data-ttu-id="662a9-103">*Конечная точка набора ассоциаций* идентифицирует [тип сущности](../../../../docs/framework/data/adonet/entity-type.md) и [набор сущностей](../../../../docs/framework/data/adonet/entity-set.md) в конце [набор ассоциаций](../../../../docs/framework/data/adonet/association-set.md).</span><span class="sxs-lookup"><span data-stu-id="662a9-103">An *association set end* identifies the [entity type](../../../../docs/framework/data/adonet/entity-type.md) and the [entity set](../../../../docs/framework/data/adonet/entity-set.md) at the end of an [association set](../../../../docs/framework/data/adonet/association-set.md).</span></span> <span data-ttu-id="662a9-104">Конечные точки набора ассоциаций определяются как часть набора ассоциаций; набор ассоциаций должен иметь ровно две конечные точки.</span><span class="sxs-lookup"><span data-stu-id="662a9-104">Association set ends are defined as part of an association set; an association set must have exactly two association set ends.</span></span>  
  
 <span data-ttu-id="662a9-105">Определение конечной точки набора ассоциаций содержит следующую информацию.</span><span class="sxs-lookup"><span data-stu-id="662a9-105">An association set end definition contains the following information:</span></span>  
  
- <span data-ttu-id="662a9-106">Один из типов сущностей, участвующих в наборе ассоциаций.</span><span class="sxs-lookup"><span data-stu-id="662a9-106">One of the entity types involved in the association set.</span></span> <span data-ttu-id="662a9-107">(Обязательный атрибут).</span><span class="sxs-lookup"><span data-stu-id="662a9-107">(Required)</span></span>  
  
- <span data-ttu-id="662a9-108">Набор сущностей для типа сущностей, участвующих в наборе ассоциаций.</span><span class="sxs-lookup"><span data-stu-id="662a9-108">The entity set for the entity type involved in the association set.</span></span> <span data-ttu-id="662a9-109">(Обязательный атрибут).</span><span class="sxs-lookup"><span data-stu-id="662a9-109">(Required)</span></span>  
  
## <a name="example"></a><span data-ttu-id="662a9-110">Пример</span><span class="sxs-lookup"><span data-stu-id="662a9-110">Example</span></span>  
 <span data-ttu-id="662a9-111">На приведенной ниже схеме показана концептуальная модель с двумя ассоциациями: `WrittenBy` и `PublishedBy`.</span><span class="sxs-lookup"><span data-stu-id="662a9-111">The diagram below shows a conceptual model with two associations: `WrittenBy` and `PublishedBy`.</span></span>  
  
 ![Пример модели с тремя типами сущностей](./media/association-set-end/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="662a9-113">На следующей схеме показаны один набор ассоциаций (`PublishedBy` и `Books`) и два набора сущностей (`Publishers`) на основе приведенной выше концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="662a9-113">The following diagram shows an association set (`PublishedBy`) and two entity sets (`Books` and `Publishers`) based on the conceptual model shown above.</span></span> <span data-ttu-id="662a9-114">Конечные точки набора ассоциаций - это наборы сущностей `Books` и `Publishers`.</span><span class="sxs-lookup"><span data-stu-id="662a9-114">The association set ends are the `Books` and `Publishers` entity sets.</span></span> <span data-ttu-id="662a9-115">Бизнес-аналитики в `Books` набор сущностей представляет экземпляр `Book` тип сущности во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="662a9-115">Bi in the `Books` entity set represents an instance of the `Book` entity type at run time.</span></span> <span data-ttu-id="662a9-116">Аналогичным образом, представляет Pj `Publisher` в экземпляре `Publishers` набора сущностей.</span><span class="sxs-lookup"><span data-stu-id="662a9-116">Similarly, Pj represents a `Publisher` instance in the `Publishers` entity set.</span></span> <span data-ttu-id="662a9-117">BiPj представляет экземпляр `PublishedBy` ассоциации в `PublishedBy` набора ассоциаций.</span><span class="sxs-lookup"><span data-stu-id="662a9-117">BiPj represents an instance of the `PublishedBy` association in the `PublishedBy` association set.</span></span>  
  
 ![Снимок экрана, показывающий пример наборов.](./media/association-set-end/sets-example-association.gif)  
  
 <span data-ttu-id="662a9-119">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует DSL, называемый языком определения концептуальной схемы ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) для определения концептуальных моделей.</span><span class="sxs-lookup"><span data-stu-id="662a9-119">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a DSL called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="662a9-120">Далее на языке CSDL определяется контейнер сущностей с одним набором ассоциаций для каждой ассоциации на приведенной выше схеме.</span><span class="sxs-lookup"><span data-stu-id="662a9-120">The following CSDL defines an entity container with one association set for each association in the diagram above.</span></span> <span data-ttu-id="662a9-121">Обратите внимание, что конечные точки набора ассоциаций определяются как часть каждого определения набора ассоциаций.</span><span class="sxs-lookup"><span data-stu-id="662a9-121">Note that association set ends are defined as part of each association set definition.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="662a9-122">См. также</span><span class="sxs-lookup"><span data-stu-id="662a9-122">See also</span></span>

- [<span data-ttu-id="662a9-123">Основные понятия модели EDM</span><span class="sxs-lookup"><span data-stu-id="662a9-123">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="662a9-124">Сущностная модель данных</span><span class="sxs-lookup"><span data-stu-id="662a9-124">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
