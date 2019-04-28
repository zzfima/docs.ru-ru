---
title: сложный тип
ms.date: 03/30/2017
ms.assetid: 63efbd23-11d4-4871-bc88-ad01b9837553
ms.openlocfilehash: 9d63660c441192bbc9ecb48bb3a86030b46461cc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61880021"
---
# <a name="complex-type"></a><span data-ttu-id="526da-102">сложный тип</span><span class="sxs-lookup"><span data-stu-id="526da-102">complex type</span></span>
<span data-ttu-id="526da-103">Объект *сложного типа* — это шаблон для определения расширенных структурированных свойств в [типы сущностей](../../../../docs/framework/data/adonet/entity-type.md) или на других сложных типов.</span><span class="sxs-lookup"><span data-stu-id="526da-103">A *complex type* is a template for defining rich, structured properties on [entity types](../../../../docs/framework/data/adonet/entity-type.md) or on other complex types.</span></span> <span data-ttu-id="526da-104">Каждый шаблон содержит следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="526da-104">Each template contains the following:</span></span>  
  
- <span data-ttu-id="526da-105">Уникальное имя.</span><span class="sxs-lookup"><span data-stu-id="526da-105">A unique name.</span></span> <span data-ttu-id="526da-106">(Обязательный атрибут).</span><span class="sxs-lookup"><span data-stu-id="526da-106">(Required)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="526da-107">Имя сложного типа не может быть таким же, что и имя типа сущности внутри одного и того же пространства имени.</span><span class="sxs-lookup"><span data-stu-id="526da-107">The name of a complex type cannot be the same as an entity type name within the same namespace.</span></span>  
  
- <span data-ttu-id="526da-108">Данные в виде одного или нескольких [свойства](../../../../docs/framework/data/adonet/property.md).</span><span class="sxs-lookup"><span data-stu-id="526da-108">Data in the form of one or more [properties](../../../../docs/framework/data/adonet/property.md).</span></span> <span data-ttu-id="526da-109">(Необязательно.)</span><span class="sxs-lookup"><span data-stu-id="526da-109">(Optional.)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="526da-110">Свойство сложного типа может быть другим сложным типом.</span><span class="sxs-lookup"><span data-stu-id="526da-110">A property of a complex type can be another complex type.</span></span>  
  
 <span data-ttu-id="526da-111">Сложный тип похож на тип сущности тем, что сложный тип может содержать полезные данные в форме свойств примитивного типа или других сложных типов.</span><span class="sxs-lookup"><span data-stu-id="526da-111">A complex type is similar to an entity type in that a complex type can carry a data payload in the form of primitive type properties or other complex types.</span></span> <span data-ttu-id="526da-112">Однако между сложными типами и типами сущности существуют некоторые ключевые различия.</span><span class="sxs-lookup"><span data-stu-id="526da-112">However, there are some key differences between complex types and entity types:</span></span>  
  
- <span data-ttu-id="526da-113">Сложные типы не имеют идентификаторов и поэтому не могут существовать независимо.</span><span class="sxs-lookup"><span data-stu-id="526da-113">Complex types do not have identities and therefore cannot exist independently.</span></span> <span data-ttu-id="526da-114">Сложные типы могут существовать только как свойства типов сущностей или других сложных типов.</span><span class="sxs-lookup"><span data-stu-id="526da-114">Complex types can only exist as properties on entity types or other complex types.</span></span>  
  
- <span data-ttu-id="526da-115">Сложные типы не могут участвовать в [ассоциации](../../../../docs/framework/data/adonet/association-type.md).</span><span class="sxs-lookup"><span data-stu-id="526da-115">Complex types cannot participate in [associations](../../../../docs/framework/data/adonet/association-type.md).</span></span> <span data-ttu-id="526da-116">Ни один конец ассоциации может быть сложным типом и поэтому [свойства навигации](../../../../docs/framework/data/adonet/navigation-property.md) нельзя определить для сложных типов.</span><span class="sxs-lookup"><span data-stu-id="526da-116">Neither end of an association can be a complex type, and therefore [navigation properties](../../../../docs/framework/data/adonet/navigation-property.md) cannot be defined on complex types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="526da-117">Пример</span><span class="sxs-lookup"><span data-stu-id="526da-117">Example</span></span>  
 <span data-ttu-id="526da-118">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) для определения концептуальных моделей.</span><span class="sxs-lookup"><span data-stu-id="526da-118">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="526da-119">Далее на языке CSDL определяется сложный тип, адрес со свойствами примитивного типа `StreetAddress`, `City`, `StateOrProvince`, `Country` и `PostalCode`.</span><span class="sxs-lookup"><span data-stu-id="526da-119">The following CSDL defines a complex type, Address, with the primitive type properties `StreetAddress`, `City`, `StateOrProvince`, `Country`, and `PostalCode`.</span></span>  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
 <span data-ttu-id="526da-120">Чтобы определить сложный тип `Address` (показанный выше) как свойство типа сущности, необходимо объявить тип свойства в определении типа сущности.</span><span class="sxs-lookup"><span data-stu-id="526da-120">To define the complex type `Address` (above) as a property on an entity type, you must declare the property type in the entity type definition.</span></span> <span data-ttu-id="526da-121">Далее на языке CSDL объявляется свойство `Address` в виде сложного типа в типе сущности (издателе).</span><span class="sxs-lookup"><span data-stu-id="526da-121">The following CSDL declares the `Address` property as a complex type on an entity type (Publisher):</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityWithComplexType](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#entitywithcomplextype)]  
  
## <a name="see-also"></a><span data-ttu-id="526da-122">См. также</span><span class="sxs-lookup"><span data-stu-id="526da-122">See also</span></span>

- [<span data-ttu-id="526da-123">Основные понятия модели EDM</span><span class="sxs-lookup"><span data-stu-id="526da-123">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="526da-124">Сущностная модель данных</span><span class="sxs-lookup"><span data-stu-id="526da-124">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
