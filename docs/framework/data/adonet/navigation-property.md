---
title: Свойство навигации — ADO.NET
ms.date: 03/30/2017
ms.assetid: d0bf1a6a-1d84-484c-b7c3-b410fd8dc0b1
ms.openlocfilehash: b57ecf9329aa9ea8afc07507613c9e3961bfd0a9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58836603"
---
# <a name="navigation-property"></a><span data-ttu-id="f6f3f-102">Свойство навигации</span><span class="sxs-lookup"><span data-stu-id="f6f3f-102">Navigation property</span></span>

<span data-ttu-id="f6f3f-103">Объект *свойство навигации* — это необязательное свойство на [тип сущности](entity-type.md) , позволяет переходить от одной [окончания](association-end.md) из [ассоциации](association-type.md) для другой конец.</span><span class="sxs-lookup"><span data-stu-id="f6f3f-103">A *navigation property* is an optional property on an [entity type](entity-type.md) that allows for navigation from one [end](association-end.md) of an [association](association-type.md) to the other end.</span></span> <span data-ttu-id="f6f3f-104">В отличие от других [свойства](property.md), свойства навигации не содержат данных.</span><span class="sxs-lookup"><span data-stu-id="f6f3f-104">Unlike other [properties](property.md), navigation properties do not carry data.</span></span>

<span data-ttu-id="f6f3f-105">Определение свойства навигации содержит следующую информацию.</span><span class="sxs-lookup"><span data-stu-id="f6f3f-105">A navigation property definition includes the following:</span></span>

- <span data-ttu-id="f6f3f-106">Имя.</span><span class="sxs-lookup"><span data-stu-id="f6f3f-106">A name.</span></span> <span data-ttu-id="f6f3f-107">(Обязательный атрибут).</span><span class="sxs-lookup"><span data-stu-id="f6f3f-107">(Required)</span></span>

- <span data-ttu-id="f6f3f-108">Ассоциация, для которой осуществляется переход.</span><span class="sxs-lookup"><span data-stu-id="f6f3f-108">The association that it navigates.</span></span> <span data-ttu-id="f6f3f-109">(Обязательный атрибут).</span><span class="sxs-lookup"><span data-stu-id="f6f3f-109">(Required)</span></span>

- <span data-ttu-id="f6f3f-110">Конечные точки ассоциации, для которой осуществляется переход.</span><span class="sxs-lookup"><span data-stu-id="f6f3f-110">The ends of the association that it navigates.</span></span> <span data-ttu-id="f6f3f-111">(Обязательный атрибут).</span><span class="sxs-lookup"><span data-stu-id="f6f3f-111">(Required)</span></span>

<span data-ttu-id="f6f3f-112">Обратите внимание, что свойства навигации являются необязательными для обоих типов сущностей, расположенных в конечных элементах ассоциации.</span><span class="sxs-lookup"><span data-stu-id="f6f3f-112">Note that navigation properties are optional on both entity types at the ends of an association.</span></span> <span data-ttu-id="f6f3f-113">Если свойство навигации было определено для типа сущности на одном конечном элементе ассоциации, то определять его для типа сущности на другом конечном элементе необязательно.</span><span class="sxs-lookup"><span data-stu-id="f6f3f-113">If you define a navigation property on one entity type at the end of an association, you do not have to define a navigation property on the entity type at the other end of the association.</span></span>

<span data-ttu-id="f6f3f-114">Тип данных свойства навигации определяется [кратность](association-end-multiplicity.md) его удаленной [ассоциации](association-end.md).</span><span class="sxs-lookup"><span data-stu-id="f6f3f-114">The data type of a navigation property is determined by the [multiplicity](association-end-multiplicity.md) of its remote [association end](association-end.md).</span></span> <span data-ttu-id="f6f3f-115">Например, предположим, что свойство навигации `OrdersNavProp` существует для типа сущности `Customer` и осуществляет навигацию по ассоциации «один ко многим» между `Customer` и `Order`.</span><span class="sxs-lookup"><span data-stu-id="f6f3f-115">For example, suppose a navigation property, `OrdersNavProp`, exists on a `Customer` entity type and navigates a one-to-many association between `Customer` and `Order`.</span></span> <span data-ttu-id="f6f3f-116">Так как конечная точка удаленной ассоциации для свойства навигации имеет кратность многих (\*), он имеет тип данных коллекции (из `Order`).</span><span class="sxs-lookup"><span data-stu-id="f6f3f-116">Because the remote association end for the navigation property has multiplicity of many (\*), its data type is a collection (of `Order`).</span></span> <span data-ttu-id="f6f3f-117">Аналогично, если свойство навигации `CustomerNavProp` существует для типа сущности `Order`, то его тип данных будет `Customer`, поскольку кратность удаленного конечного элемента - «один» (1).</span><span class="sxs-lookup"><span data-stu-id="f6f3f-117">Similarly, if a navigation property, `CustomerNavProp`, exists on the `Order` entity type, its data type would be `Customer`, because the multiplicity of the remote end is one (1).</span></span>

## <a name="example"></a><span data-ttu-id="f6f3f-118">Пример</span><span class="sxs-lookup"><span data-stu-id="f6f3f-118">Example</span></span>

<span data-ttu-id="f6f3f-119">На приведенной ниже схеме показана концептуальная модель с тремя типами сущностей: `Book`, `Publisher` и `Author`.</span><span class="sxs-lookup"><span data-stu-id="f6f3f-119">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="f6f3f-120">Свойства навигации, `Publisher` и `Authors`, определены относительно типа сущности «Book».</span><span class="sxs-lookup"><span data-stu-id="f6f3f-120">Navigation properties, `Publisher` and `Authors`, are defined on the Book entity type.</span></span> <span data-ttu-id="f6f3f-121">Свойство навигации `Books` определено как относительно типа сущности «Publisher», так и относительно типа сущности `Author`.</span><span class="sxs-lookup"><span data-stu-id="f6f3f-121">Navigation property `Books` is defined on both the Publisher entity type and the `Author` entity type.</span></span>

 ![Схема, показывающая концептуальная модель с тремя типами сущностей.](./media/navigation-property/conceptual-model-entity-types-associations.gif)  

<span data-ttu-id="f6f3f-123">[ADO.NET Entity Framework](./ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](./ef/language-reference/csdl-specification.md)) для определения концептуальных моделей.</span><span class="sxs-lookup"><span data-stu-id="f6f3f-123">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](./ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="f6f3f-124">Ниже на языке CSDL определяется тип сущности `Book`, который ранее приводился в схеме.</span><span class="sxs-lookup"><span data-stu-id="f6f3f-124">The following CSDL defines the `Book` entity type shown in the diagram above:</span></span>

[!code-xml[EDM_Example_Model#EntityExample](~/samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]

<span data-ttu-id="f6f3f-125">Обратите внимание на то, что атрибуты XML используются для сообщения сведений, необходимых для определения свойства навигации: Атрибут `Name` содержит имя свойства, `Relationship` содержит имя ассоциации, осуществляется переход, и `FromRole` и `ToRole` содержат конечные точки ассоциации.</span><span class="sxs-lookup"><span data-stu-id="f6f3f-125">Note that XML attributes are used to communicate the information necessary to define a navigation property: The attribute `Name` contains the name of the property, `Relationship` contains the name of the association it navigates, and `FromRole` and `ToRole` contain the ends of the association.</span></span>

## <a name="see-also"></a><span data-ttu-id="f6f3f-126">См. также</span><span class="sxs-lookup"><span data-stu-id="f6f3f-126">See also</span></span>

- [<span data-ttu-id="f6f3f-127">Основные понятия модели EDM</span><span class="sxs-lookup"><span data-stu-id="f6f3f-127">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="f6f3f-128">Сущностная модель данных</span><span class="sxs-lookup"><span data-stu-id="f6f3f-128">Entity Data Model</span></span>](entity-data-model.md)
- [<span data-ttu-id="f6f3f-129">Связи, свойства навигации и внешние ключи</span><span class="sxs-lookup"><span data-stu-id="f6f3f-129">Relationships, navigation properties and foreign keys</span></span>](/ef/ef6/fundamentals/relationships)
