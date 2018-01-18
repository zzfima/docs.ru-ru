---
title: "свойство;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a941c53f-fc97-42c2-8832-0fb9f1d55c06
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 50cd2f2678d304af8b898380645424e0635891d2
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="property"></a><span data-ttu-id="5da53-102">свойство;</span><span class="sxs-lookup"><span data-stu-id="5da53-102">property</span></span>
<span data-ttu-id="5da53-103">*Свойства* являются фундаментальные строительные блоки [типов сущностей](../../../../docs/framework/data/adonet/entity-type.md) и [сложные типы](../../../../docs/framework/data/adonet/complex-type.md).</span><span class="sxs-lookup"><span data-stu-id="5da53-103">*Properties* are the fundamental building blocks of [entity types](../../../../docs/framework/data/adonet/entity-type.md) and [complex types](../../../../docs/framework/data/adonet/complex-type.md).</span></span> <span data-ttu-id="5da53-104">Свойства определяют форму и характеристики данных, которые экземпляр типа сущности или сложного типа будет содержать.</span><span class="sxs-lookup"><span data-stu-id="5da53-104">Properties define the shape and characteristics of data that an entity type instance or complex type instance will contain.</span></span> <span data-ttu-id="5da53-105">Свойства в концептуальной модели аналогичны свойствам, которые определены применительно к классу.</span><span class="sxs-lookup"><span data-stu-id="5da53-105">Properties in a conceptual model are analogous to properties defined on a class.</span></span> <span data-ttu-id="5da53-106">По такому же принципу, как свойства, относящиеся к классу, определяют форму класса и несут информацию об объектах, свойства в концептуальной модели определяют форму типа сущности и несут информацию об экземплярах типа сущности.</span><span class="sxs-lookup"><span data-stu-id="5da53-106">In the same way that properties on a class define the shape of the class and carry information about objects, properties in a conceptual model define the shape of an entity type and carry information about entity type instances.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5da53-107">Свойства, как они описаны в этом разделе, отличаются от свойств навигации.</span><span class="sxs-lookup"><span data-stu-id="5da53-107">Properties, as described in this topic, are different from navigation properties.</span></span> <span data-ttu-id="5da53-108">Дополнительные сведения см. в разделе [свойства навигации](../../../../docs/framework/data/adonet/navigation-property.md).</span><span class="sxs-lookup"><span data-stu-id="5da53-108">For more information, see [navigation properties](../../../../docs/framework/data/adonet/navigation-property.md).</span></span>  
  
 <span data-ttu-id="5da53-109">Определение свойства содержит следующую информацию.</span><span class="sxs-lookup"><span data-stu-id="5da53-109">A property definition contains the following information:</span></span>  
  
-   <span data-ttu-id="5da53-110">Имя свойства.</span><span class="sxs-lookup"><span data-stu-id="5da53-110">A property name.</span></span> <span data-ttu-id="5da53-111">(Обязательный атрибут).</span><span class="sxs-lookup"><span data-stu-id="5da53-111">(Required)</span></span>  
  
-   <span data-ttu-id="5da53-112">Тип свойства.</span><span class="sxs-lookup"><span data-stu-id="5da53-112">A property type.</span></span> <span data-ttu-id="5da53-113">(Обязательный атрибут).</span><span class="sxs-lookup"><span data-stu-id="5da53-113">(Required)</span></span>  
  
-   <span data-ttu-id="5da53-114">Набор [аспекты](../../../../docs/framework/data/adonet/facet.md).</span><span class="sxs-lookup"><span data-stu-id="5da53-114">A set of [facets](../../../../docs/framework/data/adonet/facet.md).</span></span> <span data-ttu-id="5da53-115">(Необязательный параметр).</span><span class="sxs-lookup"><span data-stu-id="5da53-115">(Optional)</span></span>  
  
 <span data-ttu-id="5da53-116">Свойство может содержать примитивные данные (такие как строка, целое число, логическое значение) или структурированные данные (такие как сложный тип).</span><span class="sxs-lookup"><span data-stu-id="5da53-116">A property can contain primitive data (such as a string, an integer, or a Boolean value), or structured data (such as a complex type).</span></span> <span data-ttu-id="5da53-117">Свойства примитивного типа также называются скалярными свойствами.</span><span class="sxs-lookup"><span data-stu-id="5da53-117">Properties that are of primitive type are also called scalar properties.</span></span> <span data-ttu-id="5da53-118">Дополнительные сведения см. в разделе [модель данных сущности: примитивные типы данных](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="5da53-118">For more information, see [Entity Data Model: Primitive Data Types](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5da53-119">Сложный тип может сам по себе иметь свойства, которые являются сложными типами.</span><span class="sxs-lookup"><span data-stu-id="5da53-119">A complex type can, itself, have properties that are complex types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5da53-120">Пример</span><span class="sxs-lookup"><span data-stu-id="5da53-120">Example</span></span>  
 <span data-ttu-id="5da53-121">На приведенной ниже схеме показана концептуальная модель с тремя типами сущностей: `Book`, `Publisher` и `Author`.</span><span class="sxs-lookup"><span data-stu-id="5da53-121">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="5da53-122">Каждый тип сущности имеет несколько свойств, однако сведений о типе для каждого свойства в схеме не содержится.</span><span class="sxs-lookup"><span data-stu-id="5da53-122">Each entity type has several properties, although type information for each property is not conveyed in the diagram.</span></span> <span data-ttu-id="5da53-123">Свойства, которые являются [ключи сущности](../../../../docs/framework/data/adonet/entity-key.md) , обозначаются знаком (ключ).</span><span class="sxs-lookup"><span data-stu-id="5da53-123">Properties that are [entity keys](../../../../docs/framework/data/adonet/entity-key.md) are denoted with (Key).</span></span>  
  
 <span data-ttu-id="5da53-124">![Пример модели](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="5da53-124">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="5da53-125">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) для определения концептуальных моделей.</span><span class="sxs-lookup"><span data-stu-id="5da53-125">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="5da53-126">Далее на языке CSDL определяется тип сущности `Book` (как показано на схеме выше), и при помощи атрибутов XML указываются тип и имя каждого свойства.</span><span class="sxs-lookup"><span data-stu-id="5da53-126">The following CSDL defines the `Book` entity type (as shown in the diagram above) and indicates the type and name of each property by using XML attributes.</span></span> <span data-ttu-id="5da53-127">Дополнительный аспект, `Nullable`, также определяется при помощи атрибута XML.</span><span class="sxs-lookup"><span data-stu-id="5da53-127">An optional facet, `Nullable`, is also defined by using an XML attribute.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
 <span data-ttu-id="5da53-128">Ни одно из свойств на схеме не может быть свойством сложного типа.</span><span class="sxs-lookup"><span data-stu-id="5da53-128">It is possible that one of the properties shown in the diagram is a complex type property.</span></span> <span data-ttu-id="5da53-129">Например, свойство `Address` в типе сущности `Publisher` может быть свойством сложного типа, состоящего из нескольких скалярных свойств, таких как `StreetAddress`, `City`, `StateOrProvince`, `Country` и `PostalCode`.</span><span class="sxs-lookup"><span data-stu-id="5da53-129">For example, the `Address` property on the `Publisher` entity type could be a complex type property composed of several scalar properties, such as `StreetAddress`, `City`, `StateOrProvince`, `Country`, and `PostalCode`.</span></span> <span data-ttu-id="5da53-130">Представление такого сложного типа на языке CSDL может быть следующим.</span><span class="sxs-lookup"><span data-stu-id="5da53-130">The CSDL representation of such a complex type would be as follows:</span></span>  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
## <a name="see-also"></a><span data-ttu-id="5da53-131">См. также</span><span class="sxs-lookup"><span data-stu-id="5da53-131">See Also</span></span>  
 [<span data-ttu-id="5da53-132">Основные понятия модели EDM</span><span class="sxs-lookup"><span data-stu-id="5da53-132">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="5da53-133">Сущностная модель данных</span><span class="sxs-lookup"><span data-stu-id="5da53-133">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
