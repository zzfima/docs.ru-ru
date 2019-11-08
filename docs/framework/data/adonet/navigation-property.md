---
title: Свойство навигации — ADO.NET
ms.date: 03/30/2017
ms.assetid: d0bf1a6a-1d84-484c-b7c3-b410fd8dc0b1
ms.openlocfilehash: afb2043abf70fa92ea7cdf8d1e8246d5cdfdba74
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738390"
---
# <a name="navigation-property"></a><span data-ttu-id="f280e-102">Свойство навигации</span><span class="sxs-lookup"><span data-stu-id="f280e-102">Navigation property</span></span>

<span data-ttu-id="f280e-103">*Свойство навигации* — это необязательное свойство для [типа сущности](entity-type.md) , позволяющее переходить с одного [конца](association-end.md) [ассоциации](association-type.md) на другой конец.</span><span class="sxs-lookup"><span data-stu-id="f280e-103">A *navigation property* is an optional property on an [entity type](entity-type.md) that allows for navigation from one [end](association-end.md) of an [association](association-type.md) to the other end.</span></span> <span data-ttu-id="f280e-104">В отличие от других [свойств](property.md), свойства навигации не содержат данных.</span><span class="sxs-lookup"><span data-stu-id="f280e-104">Unlike other [properties](property.md), navigation properties do not carry data.</span></span>

<span data-ttu-id="f280e-105">Определение свойства навигации содержит следующую информацию.</span><span class="sxs-lookup"><span data-stu-id="f280e-105">A navigation property definition includes the following:</span></span>

- <span data-ttu-id="f280e-106">Имя.</span><span class="sxs-lookup"><span data-stu-id="f280e-106">A name.</span></span> <span data-ttu-id="f280e-107">(Обязательный атрибут).</span><span class="sxs-lookup"><span data-stu-id="f280e-107">(Required)</span></span>

- <span data-ttu-id="f280e-108">Ассоциация, для которой осуществляется переход.</span><span class="sxs-lookup"><span data-stu-id="f280e-108">The association that it navigates.</span></span> <span data-ttu-id="f280e-109">(Обязательный атрибут).</span><span class="sxs-lookup"><span data-stu-id="f280e-109">(Required)</span></span>

- <span data-ttu-id="f280e-110">Конечные точки ассоциации, для которой осуществляется переход.</span><span class="sxs-lookup"><span data-stu-id="f280e-110">The ends of the association that it navigates.</span></span> <span data-ttu-id="f280e-111">(Обязательный атрибут).</span><span class="sxs-lookup"><span data-stu-id="f280e-111">(Required)</span></span>

<span data-ttu-id="f280e-112">Обратите внимание, что свойства навигации являются необязательными для обоих типов сущностей, расположенных в конечных элементах ассоциации.</span><span class="sxs-lookup"><span data-stu-id="f280e-112">Note that navigation properties are optional on both entity types at the ends of an association.</span></span> <span data-ttu-id="f280e-113">Если свойство навигации было определено для типа сущности на одном конечном элементе ассоциации, то определять его для типа сущности на другом конечном элементе необязательно.</span><span class="sxs-lookup"><span data-stu-id="f280e-113">If you define a navigation property on one entity type at the end of an association, you do not have to define a navigation property on the entity type at the other end of the association.</span></span>

<span data-ttu-id="f280e-114">Тип данных свойства навигации определяется [кратностью](association-end-multiplicity.md) его удаленной [ассоциации](association-end.md).</span><span class="sxs-lookup"><span data-stu-id="f280e-114">The data type of a navigation property is determined by the [multiplicity](association-end-multiplicity.md) of its remote [association end](association-end.md).</span></span> <span data-ttu-id="f280e-115">Например, предположим, что свойство навигации `OrdersNavProp` существует для типа сущности `Customer` и осуществляет навигацию по ассоциации «один ко многим» между `Customer` и `Order`.</span><span class="sxs-lookup"><span data-stu-id="f280e-115">For example, suppose a navigation property, `OrdersNavProp`, exists on a `Customer` entity type and navigates a one-to-many association between `Customer` and `Order`.</span></span> <span data-ttu-id="f280e-116">Так как удаленная ассоциация для свойства навигации имеет кратность many (\*), ее тип данных — это коллекция (из `Order`).</span><span class="sxs-lookup"><span data-stu-id="f280e-116">Because the remote association end for the navigation property has multiplicity of many (\*), its data type is a collection (of `Order`).</span></span> <span data-ttu-id="f280e-117">Аналогично, если свойство навигации `CustomerNavProp` существует для типа сущности `Order`, то его тип данных будет `Customer`, поскольку кратность удаленного конечного элемента - «один» (1).</span><span class="sxs-lookup"><span data-stu-id="f280e-117">Similarly, if a navigation property, `CustomerNavProp`, exists on the `Order` entity type, its data type would be `Customer`, because the multiplicity of the remote end is one (1).</span></span>

## <a name="example"></a><span data-ttu-id="f280e-118">Пример</span><span class="sxs-lookup"><span data-stu-id="f280e-118">Example</span></span>

<span data-ttu-id="f280e-119">На приведенной ниже схеме показана концептуальная модель с тремя типами сущностей: `Book`, `Publisher` и `Author`.</span><span class="sxs-lookup"><span data-stu-id="f280e-119">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="f280e-120">Свойства навигации, `Publisher` и `Authors`, определены относительно типа сущности «Book».</span><span class="sxs-lookup"><span data-stu-id="f280e-120">Navigation properties, `Publisher` and `Authors`, are defined on the Book entity type.</span></span> <span data-ttu-id="f280e-121">Свойство навигации `Books` определено как относительно типа сущности «Publisher», так и относительно типа сущности `Author`.</span><span class="sxs-lookup"><span data-stu-id="f280e-121">Navigation property `Books` is defined on both the Publisher entity type and the `Author` entity type.</span></span>

 ![Схема, демонстрирующая концептуальную модель с тремя типами сущностей.](./media/navigation-property/conceptual-model-entity-types-associations.gif)  

<span data-ttu-id="f280e-123">[Entity Framework ADO.NET](./ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)), для определения концептуальных моделей.</span><span class="sxs-lookup"><span data-stu-id="f280e-123">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="f280e-124">Ниже на языке CSDL определяется тип сущности `Book`, который ранее приводился в схеме.</span><span class="sxs-lookup"><span data-stu-id="f280e-124">The following CSDL defines the `Book` entity type shown in the diagram above:</span></span>

[!code-xml[EDM_Example_Model#EntityExample](~/samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]

<span data-ttu-id="f280e-125">Обратите внимание, что атрибуты XML используются для сообщения сведений, необходимых для определения свойства навигации: атрибут `Name` содержит имя свойства, `Relationship` содержит имя ассоциации, для которой осуществляется переход, и `FromRole` и `ToRole` содержат конечные точки ассоциации.</span><span class="sxs-lookup"><span data-stu-id="f280e-125">Note that XML attributes are used to communicate the information necessary to define a navigation property: The attribute `Name` contains the name of the property, `Relationship` contains the name of the association it navigates, and `FromRole` and `ToRole` contain the ends of the association.</span></span>

## <a name="see-also"></a><span data-ttu-id="f280e-126">См. также</span><span class="sxs-lookup"><span data-stu-id="f280e-126">See also</span></span>

- [<span data-ttu-id="f280e-127">Основные понятия модели EDM</span><span class="sxs-lookup"><span data-stu-id="f280e-127">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="f280e-128">Сущностная модель данных</span><span class="sxs-lookup"><span data-stu-id="f280e-128">Entity Data Model</span></span>](entity-data-model.md)
- [<span data-ttu-id="f280e-129">Связи, свойства навигации и внешние ключи</span><span class="sxs-lookup"><span data-stu-id="f280e-129">Relationships, navigation properties and foreign keys</span></span>](/ef/ef6/fundamentals/relationships)
