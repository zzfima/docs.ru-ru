---
title: свойство
ms.date: 03/30/2017
ms.assetid: a941c53f-fc97-42c2-8832-0fb9f1d55c06
ms.openlocfilehash: 97d934ac581e7b1a923bf77dcf46121782fe8eab
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783174"
---
# <a name="property"></a><span data-ttu-id="70a1c-102">свойство</span><span class="sxs-lookup"><span data-stu-id="70a1c-102">property</span></span>
<span data-ttu-id="70a1c-103">*Свойства* являются фундаментальными строительными блоками [типов сущностей](entity-type.md) и [сложных типов](complex-type.md).</span><span class="sxs-lookup"><span data-stu-id="70a1c-103">*Properties* are the fundamental building blocks of [entity types](entity-type.md) and [complex types](complex-type.md).</span></span> <span data-ttu-id="70a1c-104">Свойства определяют форму и характеристики данных, которые экземпляр типа сущности или сложного типа будет содержать.</span><span class="sxs-lookup"><span data-stu-id="70a1c-104">Properties define the shape and characteristics of data that an entity type instance or complex type instance will contain.</span></span> <span data-ttu-id="70a1c-105">Свойства в концептуальной модели аналогичны свойствам, которые определены применительно к классу.</span><span class="sxs-lookup"><span data-stu-id="70a1c-105">Properties in a conceptual model are analogous to properties defined on a class.</span></span> <span data-ttu-id="70a1c-106">По такому же принципу, как свойства, относящиеся к классу, определяют форму класса и несут информацию об объектах, свойства в концептуальной модели определяют форму типа сущности и несут информацию об экземплярах типа сущности.</span><span class="sxs-lookup"><span data-stu-id="70a1c-106">In the same way that properties on a class define the shape of the class and carry information about objects, properties in a conceptual model define the shape of an entity type and carry information about entity type instances.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="70a1c-107">Свойства, как они описаны в этом разделе, отличаются от свойств навигации.</span><span class="sxs-lookup"><span data-stu-id="70a1c-107">Properties, as described in this topic, are different from navigation properties.</span></span> <span data-ttu-id="70a1c-108">Дополнительные сведения см. в разделе [Свойства навигации](navigation-property.md).</span><span class="sxs-lookup"><span data-stu-id="70a1c-108">For more information, see [navigation properties](navigation-property.md).</span></span>  
  
 <span data-ttu-id="70a1c-109">Определение свойства содержит следующую информацию.</span><span class="sxs-lookup"><span data-stu-id="70a1c-109">A property definition contains the following information:</span></span>  
  
- <span data-ttu-id="70a1c-110">Имя свойства.</span><span class="sxs-lookup"><span data-stu-id="70a1c-110">A property name.</span></span> <span data-ttu-id="70a1c-111">(Обязательный атрибут).</span><span class="sxs-lookup"><span data-stu-id="70a1c-111">(Required)</span></span>  
  
- <span data-ttu-id="70a1c-112">Тип свойства.</span><span class="sxs-lookup"><span data-stu-id="70a1c-112">A property type.</span></span> <span data-ttu-id="70a1c-113">(Обязательный атрибут).</span><span class="sxs-lookup"><span data-stu-id="70a1c-113">(Required)</span></span>  
  
- <span data-ttu-id="70a1c-114">Набор [аспектов](facet.md).</span><span class="sxs-lookup"><span data-stu-id="70a1c-114">A set of [facets](facet.md).</span></span> <span data-ttu-id="70a1c-115">(Необязательный параметр).</span><span class="sxs-lookup"><span data-stu-id="70a1c-115">(Optional)</span></span>  
  
 <span data-ttu-id="70a1c-116">Свойство может содержать примитивные данные (такие как строка, целое число, логическое значение) или структурированные данные (такие как сложный тип).</span><span class="sxs-lookup"><span data-stu-id="70a1c-116">A property can contain primitive data (such as a string, an integer, or a Boolean value), or structured data (such as a complex type).</span></span> <span data-ttu-id="70a1c-117">Свойства примитивного типа также называются скалярными свойствами.</span><span class="sxs-lookup"><span data-stu-id="70a1c-117">Properties that are of primitive type are also called scalar properties.</span></span> <span data-ttu-id="70a1c-118">Дополнительные сведения см. в [разделе EDM: Примитивные типы](entity-data-model-primitive-data-types.md)данных.</span><span class="sxs-lookup"><span data-stu-id="70a1c-118">For more information, see [Entity Data Model: Primitive Data Types](entity-data-model-primitive-data-types.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="70a1c-119">Сложный тип может сам по себе иметь свойства, которые являются сложными типами.</span><span class="sxs-lookup"><span data-stu-id="70a1c-119">A complex type can, itself, have properties that are complex types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70a1c-120">Пример</span><span class="sxs-lookup"><span data-stu-id="70a1c-120">Example</span></span>  
 <span data-ttu-id="70a1c-121">На приведенной ниже схеме показана концептуальная модель с тремя типами сущностей: `Book`, `Publisher` и `Author`.</span><span class="sxs-lookup"><span data-stu-id="70a1c-121">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="70a1c-122">Каждый тип сущности имеет несколько свойств, однако сведений о типе для каждого свойства в схеме не содержится.</span><span class="sxs-lookup"><span data-stu-id="70a1c-122">Each entity type has several properties, although type information for each property is not conveyed in the diagram.</span></span> <span data-ttu-id="70a1c-123">Свойства, являющиеся [ключами сущности](entity-key.md) , обозначаются ключевыми знаками (Key).</span><span class="sxs-lookup"><span data-stu-id="70a1c-123">Properties that are [entity keys](entity-key.md) are denoted with (Key).</span></span>  
  
 ![Пример модели с тремя типами сущностей](./media/property/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="70a1c-125">[Entity Framework ADO.NET](./ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](./ef/language-reference/csdl-specification.md)), для определения концептуальных моделей.</span><span class="sxs-lookup"><span data-stu-id="70a1c-125">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](./ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="70a1c-126">Далее на языке CSDL определяется тип сущности `Book` (как показано на схеме выше), и при помощи атрибутов XML указываются тип и имя каждого свойства.</span><span class="sxs-lookup"><span data-stu-id="70a1c-126">The following CSDL defines the `Book` entity type (as shown in the diagram above) and indicates the type and name of each property by using XML attributes.</span></span> <span data-ttu-id="70a1c-127">Дополнительный аспект, `Nullable`, также определяется при помощи атрибута XML.</span><span class="sxs-lookup"><span data-stu-id="70a1c-127">An optional facet, `Nullable`, is also defined by using an XML attribute.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
 <span data-ttu-id="70a1c-128">Ни одно из свойств на схеме не может быть свойством сложного типа.</span><span class="sxs-lookup"><span data-stu-id="70a1c-128">It is possible that one of the properties shown in the diagram is a complex type property.</span></span> <span data-ttu-id="70a1c-129">Например, свойство `Address` в типе сущности `Publisher` может быть свойством сложного типа, состоящего из нескольких скалярных свойств, таких как `StreetAddress`, `City`, `StateOrProvince`, `Country` и `PostalCode`.</span><span class="sxs-lookup"><span data-stu-id="70a1c-129">For example, the `Address` property on the `Publisher` entity type could be a complex type property composed of several scalar properties, such as `StreetAddress`, `City`, `StateOrProvince`, `Country`, and `PostalCode`.</span></span> <span data-ttu-id="70a1c-130">Представление такого сложного типа на языке CSDL может быть следующим.</span><span class="sxs-lookup"><span data-stu-id="70a1c-130">The CSDL representation of such a complex type would be as follows:</span></span>  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
## <a name="see-also"></a><span data-ttu-id="70a1c-131">См. также</span><span class="sxs-lookup"><span data-stu-id="70a1c-131">See also</span></span>

- [<span data-ttu-id="70a1c-132">Основные понятия модели EDM</span><span class="sxs-lookup"><span data-stu-id="70a1c-132">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="70a1c-133">Сущностная модель данных</span><span class="sxs-lookup"><span data-stu-id="70a1c-133">Entity Data Model</span></span>](entity-data-model.md)
