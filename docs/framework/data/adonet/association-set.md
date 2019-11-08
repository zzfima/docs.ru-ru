---
title: набор ассоциаций
ms.date: 03/30/2017
ms.assetid: a65247b6-ce59-44ea-974c-14ae20a7995f
ms.openlocfilehash: e279322f9e950cd4359db8c6dce39bfc46d188f6
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732376"
---
# <a name="association-set"></a><span data-ttu-id="6c905-102">набор ассоциаций</span><span class="sxs-lookup"><span data-stu-id="6c905-102">association set</span></span>
<span data-ttu-id="6c905-103">*Набор ассоциаций* — это логический контейнер для экземпляров [ассоциаций](association-type.md) того же типа.</span><span class="sxs-lookup"><span data-stu-id="6c905-103">An *association set* is a logical container for [association](association-type.md) instances of the same type.</span></span> <span data-ttu-id="6c905-104">Набор ассоциаций не является конструктом моделирования данных, то есть не описывает структуру данных или связи.</span><span class="sxs-lookup"><span data-stu-id="6c905-104">An association set is not a data modeling construct; that is, it does not describe the structure of data or relationships.</span></span> <span data-ttu-id="6c905-105">Вместо этого ассоциация обеспечивает конструкт для среды размещения или хранения (например, для среды CLR или базы данных сервера SQL), позволяя группировать экземпляры ассоциаций так, чтобы они были сопоставлены хранилищу данных.</span><span class="sxs-lookup"><span data-stu-id="6c905-105">Instead, an association set provides a construct for a hosting or storage environment (such as the common language runtime or a SQL Server database) to group association instances so that they can be mapped to a data store.</span></span>  
  
 <span data-ttu-id="6c905-106">Набор ассоциаций определяется в [контейнере сущностей](entity-container.md), который является логической группировкой [наборов сущностей](entity-set.md) и наборов ассоциаций.</span><span class="sxs-lookup"><span data-stu-id="6c905-106">An association set is defined within an [entity container](entity-container.md), which is a logical grouping of [entity sets](entity-set.md) and association sets.</span></span>  
  
 <span data-ttu-id="6c905-107">Определение набора ассоциаций содержит следующую информацию.</span><span class="sxs-lookup"><span data-stu-id="6c905-107">A definition for an association set contains the following information:</span></span>  
  
- <span data-ttu-id="6c905-108">Имя набора ассоциаций.</span><span class="sxs-lookup"><span data-stu-id="6c905-108">The association set name.</span></span> <span data-ttu-id="6c905-109">(Обязательный атрибут).</span><span class="sxs-lookup"><span data-stu-id="6c905-109">(Required)</span></span>  
  
- <span data-ttu-id="6c905-110">Ассоциация, экземпляры которой будут являться содержимым.</span><span class="sxs-lookup"><span data-stu-id="6c905-110">The association of which it will contain instances.</span></span> <span data-ttu-id="6c905-111">(Обязательный атрибут).</span><span class="sxs-lookup"><span data-stu-id="6c905-111">(Required)</span></span>  
  
- <span data-ttu-id="6c905-112">Два [конца набора ассоциаций](association-set-end.md).</span><span class="sxs-lookup"><span data-stu-id="6c905-112">Two [association set ends](association-set-end.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c905-113">Пример</span><span class="sxs-lookup"><span data-stu-id="6c905-113">Example</span></span>  
 <span data-ttu-id="6c905-114">На приведенной ниже схеме показана концептуальная модель с двумя ассоциациями: `PublishedBy` и `WrittenBy`.</span><span class="sxs-lookup"><span data-stu-id="6c905-114">The diagram below shows a conceptual model with two associations: `PublishedBy`, and `WrittenBy`.</span></span> <span data-ttu-id="6c905-115">Информации о наборах ассоциаций не содержится в схеме, однако на следующей схеме показан пример наборов ассоциаций и наборов сущностей на основе этой модели.</span><span class="sxs-lookup"><span data-stu-id="6c905-115">Although information about association sets is not conveyed in the diagram, the next diagram shows an example of association sets and entity sets based on this model.</span></span>  
  
 ![Пример модели с тремя типами сущностей](./media/association-set/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="6c905-117">В следующем примере показан набор ассоциаций (`PublishedBy`) и два набора сущностей (`Books` и `Publishers`) на основе приведенной выше концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="6c905-117">The following example shows an association set (`PublishedBy`) and two entity sets (`Books` and `Publishers`) based on the conceptual model shown above.</span></span> <span data-ttu-id="6c905-118">Бизнес-аналитика в наборе сущностей `Books` представляет экземпляр `Book` типа сущности во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="6c905-118">Bi in the `Books` entity set represents an instance of the `Book` entity type at run time.</span></span> <span data-ttu-id="6c905-119">Аналогичным образом PJ представляет экземпляр `Publisher` в `Publishers`ном наборе сущностей.</span><span class="sxs-lookup"><span data-stu-id="6c905-119">Similarly, Pj represents a `Publisher` instance in the `Publishers` entity set.</span></span> <span data-ttu-id="6c905-120">Бипж представляет экземпляр `PublishedBy` ассоциации в наборе ассоциаций `PublishedBy`.</span><span class="sxs-lookup"><span data-stu-id="6c905-120">BiPj represents an instance of the `PublishedBy` association in the `PublishedBy` association set.</span></span>  
  
 ![Снимок экрана, на котором показан пример набора.](./media/association-set/sets-example-association.gif)  
  
 <span data-ttu-id="6c905-122">[Entity Framework ADO.NET](./ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)), для определения концептуальных моделей.</span><span class="sxs-lookup"><span data-stu-id="6c905-122">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="6c905-123">Далее на языке CSDL определяется контейнер сущностей с одним набором ассоциаций для каждой ассоциации на приведенной выше схеме.</span><span class="sxs-lookup"><span data-stu-id="6c905-123">The following CSDL defines an entity container with one association set for each association in the diagram above.</span></span> <span data-ttu-id="6c905-124">Обратите внимание, что имя и ассоциация для каждого набора ассоциаций определены при помощи атрибутов XML.</span><span class="sxs-lookup"><span data-stu-id="6c905-124">Note that the name and association for each association set are defined using XML attributes.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
 <span data-ttu-id="6c905-125">Можно определить несколько наборов ассоциаций для каждой ассоциации, если ни один из двух наборов связей не имеет общего доступа к [концу набора ассоциаций](association-set-end.md).</span><span class="sxs-lookup"><span data-stu-id="6c905-125">It is possible to define multiple association sets per association, as long as no two association sets share an [association set end](association-set-end.md).</span></span> <span data-ttu-id="6c905-126">Далее на языке CSDL определяется контейнер сущностей с двумя наборами ассоциаций для ассоциации `WrittenBy`:</span><span class="sxs-lookup"><span data-stu-id="6c905-126">The following CSDL defines an entity container with two association sets for the `WrittenBy` association.</span></span> <span data-ttu-id="6c905-127">Обратите внимание, что несколько наборов сущностей были определены для типов сущностей `Book` и `Author` и что наборы ассоциаций не имеют одной и той же конечной точки ассоциации.</span><span class="sxs-lookup"><span data-stu-id="6c905-127">Notice that multiple entity sets have been defined for the `Book` and `Author` entity types and that no association set shares an association set end.</span></span>  
  
 [!code-xml[EDM_Example_Model#MultipleAssociationSets](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#multipleassociationsets)]  
  
## <a name="see-also"></a><span data-ttu-id="6c905-128">См. также</span><span class="sxs-lookup"><span data-stu-id="6c905-128">See also</span></span>

- [<span data-ttu-id="6c905-129">Основные понятия модели EDM</span><span class="sxs-lookup"><span data-stu-id="6c905-129">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="6c905-130">Сущностная модель данных</span><span class="sxs-lookup"><span data-stu-id="6c905-130">Entity Data Model</span></span>](entity-data-model.md)
- [<span data-ttu-id="6c905-131">свойство внешнего ключа</span><span class="sxs-lookup"><span data-stu-id="6c905-131">foreign key property</span></span>](foreign-key-property.md)
