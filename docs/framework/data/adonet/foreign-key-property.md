---
title: "свойство внешнего ключа"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 23cb6729-544d-4f67-9ee7-44e8a6545587
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 626feac70099667e0dc15b12043834bda6d4b20e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="foreign-key-property"></a><span data-ttu-id="eb58e-102">свойство внешнего ключа</span><span class="sxs-lookup"><span data-stu-id="eb58e-102">foreign key property</span></span>
<span data-ttu-id="eb58e-103">Объект *свойство внешнего ключа* в модель данных сущности (EDM) является типом-примитивом [свойство](../../../../docs/framework/data/adonet/property.md) (или набор свойств примитивного типа) на [тип сущности](../../../../docs/framework/data/adonet/entity-type.md) , содержащий [ключ сущности](../../../../docs/framework/data/adonet/entity-key.md) другого типа сущности.</span><span class="sxs-lookup"><span data-stu-id="eb58e-103">A *foreign key property* in the Entity Data Model (EDM) is a primitive type [property](../../../../docs/framework/data/adonet/property.md) (or a set of primitive type properties) on an [entity type](../../../../docs/framework/data/adonet/entity-type.md) that contains the [entity key](../../../../docs/framework/data/adonet/entity-key.md) of another entity type.</span></span>  
  
 <span data-ttu-id="eb58e-104">Свойство внешнего ключа схоже со столбцом внешнего ключа в реляционной базе данных.</span><span class="sxs-lookup"><span data-stu-id="eb58e-104">A foreign key property is analogous to a foreign key column in a relational database.</span></span> <span data-ttu-id="eb58e-105">Таким же образом, что столбцы внешних ключей в реляционной базе данных используются для создания связей между строками в таблицах, свойства внешнего ключа в концептуальной модели используются для установления [ассоциации](../../../../docs/framework/data/adonet/association-type.md) между типами сущностей.</span><span class="sxs-lookup"><span data-stu-id="eb58e-105">In the same way that foreign key columns are used in a relational database to create relationships between rows in tables, foreign key properties in a conceptual model are used to establish [associations](../../../../docs/framework/data/adonet/association-type.md) between entity types.</span></span> <span data-ttu-id="eb58e-106">Объект [ограничение ссылочной целостности](../../../../docs/framework/data/adonet/referential-integrity-constraint.md) используется для определения связи между двумя типами сущностей, если один из типов имеет свойство внешнего ключа.</span><span class="sxs-lookup"><span data-stu-id="eb58e-106">A [referential integrity constraint](../../../../docs/framework/data/adonet/referential-integrity-constraint.md) is used to define an association between two entity types when one of the types has a foreign key property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb58e-107">Пример</span><span class="sxs-lookup"><span data-stu-id="eb58e-107">Example</span></span>  
 <span data-ttu-id="eb58e-108">На приведенной ниже схеме показана концептуальная модель с тремя типами сущностей: `Book`, `Publisher` и `Author`.</span><span class="sxs-lookup"><span data-stu-id="eb58e-108">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="eb58e-109">Тип сущности `Book` имеет свойство `PublisherId`, которое ссылается на ключ сущности типа сущности `Publisher` при определении ограничения ссылочной целостности ассоциации `PublishedBy`.</span><span class="sxs-lookup"><span data-stu-id="eb58e-109">The `Book` entity type has a property, `PublisherId`, that references the entity key of the `Publisher` entity type when you define a referential integrity constraint on the `PublishedBy` association.</span></span>  
  
 <span data-ttu-id="eb58e-110">![RefConstraintModel](../../../../docs/framework/data/adonet/media/refconstraintmodel.gif "RefConstraintModel")</span><span class="sxs-lookup"><span data-stu-id="eb58e-110">![RefConstraintModel](../../../../docs/framework/data/adonet/media/refconstraintmodel.gif "RefConstraintModel")</span></span>  
  
 <span data-ttu-id="eb58e-111">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) для определения концептуальных моделей.</span><span class="sxs-lookup"><span data-stu-id="eb58e-111">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="eb58e-112">Следующий язык CSDL использует свойство внешнего ключа `PublisherId` для определения ограничения ссылочной целостности в ассоциации `PublishedBy`, приведенной ранее в концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="eb58e-112">The following CSDL uses the foreign key property `PublisherId` to define a referential integrity constraint on the `PublishedBy` association shown in the conceptual model shown above.</span></span>  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a><span data-ttu-id="eb58e-113">См. также</span><span class="sxs-lookup"><span data-stu-id="eb58e-113">See Also</span></span>  
 [<span data-ttu-id="eb58e-114">Основные понятия модели данных сущности</span><span class="sxs-lookup"><span data-stu-id="eb58e-114">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="eb58e-115">Модель EDM</span><span class="sxs-lookup"><span data-stu-id="eb58e-115">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
