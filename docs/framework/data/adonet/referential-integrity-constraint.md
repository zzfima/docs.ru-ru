---
title: "ограничение ссылочной целостности"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d3ba44b-4302-40d8-a7a9-62932e0395e5
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c343a0eba2478e041186f7bef18a85400c54bb5c
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="referential-integrity-constraint"></a><span data-ttu-id="fa856-102">ограничение ссылочной целостности</span><span class="sxs-lookup"><span data-stu-id="fa856-102">referential integrity constraint</span></span>
<span data-ttu-id="fa856-103">Объект *ограничение ссылочной целостности* в модель данных сущности (EDM) похоже на ограничение ссылочной целостности в реляционной базе данных.</span><span class="sxs-lookup"><span data-stu-id="fa856-103">A *referential integrity constraint* in the Entity Data Model (EDM) is similar to a referential integrity constraint in a relational database.</span></span> <span data-ttu-id="fa856-104">Таким же образом, столбец (или столбцы) из таблицы базы данных может ссылаться первичный ключ другой таблицы [свойство](../../../../docs/framework/data/adonet/property.md) (или свойства) из [тип сущности](../../../../docs/framework/data/adonet/entity-type.md) могут ссылаться на [ключ сущности ](../../../../docs/framework/data/adonet/entity-key.md) другого типа сущности.</span><span class="sxs-lookup"><span data-stu-id="fa856-104">In the same way that a column (or columns) from a database table can reference the primary key of another table, a [property](../../../../docs/framework/data/adonet/property.md) (or properties) of an [entity type](../../../../docs/framework/data/adonet/entity-type.md) can reference the [entity key](../../../../docs/framework/data/adonet/entity-key.md) of another entity type.</span></span> <span data-ttu-id="fa856-105">Тип сущности, на который имеется ссылка называется *основной элемент* ограничения.</span><span class="sxs-lookup"><span data-stu-id="fa856-105">The entity type that is referenced is called the *principal end* of the constraint.</span></span> <span data-ttu-id="fa856-106">Тип сущности, который ссылается на основной элемент называется *зависимом* ограничения.</span><span class="sxs-lookup"><span data-stu-id="fa856-106">The entity type that references the principal end is called the *dependent end* of the constraint.</span></span>  
  
 <span data-ttu-id="fa856-107">Ограничение ссылочной целостности определяется как часть [ассоциации](../../../../docs/framework/data/adonet/association-type.md) между двумя типами сущностей.</span><span class="sxs-lookup"><span data-stu-id="fa856-107">A referential integrity constraint is defined as part of an [association](../../../../docs/framework/data/adonet/association-type.md) between two entity types.</span></span> <span data-ttu-id="fa856-108">Определение ограничения ссылочной целостности включает следующую информацию.</span><span class="sxs-lookup"><span data-stu-id="fa856-108">The definition for a referential integrity constraint specifies the following information:</span></span>  
  
-   <span data-ttu-id="fa856-109">Основной конец ограничения.</span><span class="sxs-lookup"><span data-stu-id="fa856-109">The principal end of the constraint.</span></span> <span data-ttu-id="fa856-110">(Тип сущности, ключ сущности которого имеет ссылку на зависимый конец.)</span><span class="sxs-lookup"><span data-stu-id="fa856-110">(An entity type whose entity key is referenced by the dependent end.)</span></span>  
  
-   <span data-ttu-id="fa856-111">Ключ сущности основного конца.</span><span class="sxs-lookup"><span data-stu-id="fa856-111">The entity key of the principal end.</span></span>  
  
-   <span data-ttu-id="fa856-112">Зависимый конец ограничения.</span><span class="sxs-lookup"><span data-stu-id="fa856-112">The dependent end of the constraint.</span></span> <span data-ttu-id="fa856-113">(Тип сущности, который имеет свойство или свойства, ссылающиеся на ключ сущности основного конца.)</span><span class="sxs-lookup"><span data-stu-id="fa856-113">(An entity type that has a property or properties that reference the entity key of the principal end.)</span></span>  
  
-   <span data-ttu-id="fa856-114">Ссылка на свойство или свойства зависимого конца.</span><span class="sxs-lookup"><span data-stu-id="fa856-114">The referencing property or properties of the dependent end.</span></span>  
  
 <span data-ttu-id="fa856-115">Целью ограничения ссылочной целостности в модели EDM является обеспечение постоянного существования допустимых ассоциаций.</span><span class="sxs-lookup"><span data-stu-id="fa856-115">The purpose of referential integrity constraints in the EDM is to ensure that valid associations always exist.</span></span> <span data-ttu-id="fa856-116">Дополнительные сведения см. в разделе [свойство внешнего ключа](../../../../docs/framework/data/adonet/foreign-key-property.md).</span><span class="sxs-lookup"><span data-stu-id="fa856-116">For more information, see [foreign key property](../../../../docs/framework/data/adonet/foreign-key-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa856-117">Пример</span><span class="sxs-lookup"><span data-stu-id="fa856-117">Example</span></span>  
 <span data-ttu-id="fa856-118">На приведенной ниже схеме показана концептуальная модель с двумя ассоциациями: `WrittenBy` и `PublishedBy`.</span><span class="sxs-lookup"><span data-stu-id="fa856-118">The diagram below shows a conceptual model with two associations: `WrittenBy` and `PublishedBy`.</span></span> <span data-ttu-id="fa856-119">Тип сущности `Book` имеет свойство `PublisherId`, которое ссылается на ключ сущности типа сущности `Publisher` при определении ограничения ссылочной целостности ассоциации `PublishedBy`.</span><span class="sxs-lookup"><span data-stu-id="fa856-119">The `Book` entity type has a property, `PublisherId`, that references the entity key of the `Publisher` entity type when you define a referential integrity constraint on the `PublishedBy` association.</span></span>  
  
 <span data-ttu-id="fa856-120">![RefConstraintModel](../../../../docs/framework/data/adonet/media/refconstraintmodel.gif "RefConstraintModel")</span><span class="sxs-lookup"><span data-stu-id="fa856-120">![RefConstraintModel](../../../../docs/framework/data/adonet/media/refconstraintmodel.gif "RefConstraintModel")</span></span>  
  
 <span data-ttu-id="fa856-121">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) для определения концептуальных моделей.</span><span class="sxs-lookup"><span data-stu-id="fa856-121">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="fa856-122">Далее на языке CSDL определяется ограничение ссылочной целостности для ассоциации `PublishedBy`, которая ранее приводилась в концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="fa856-122">The following CSDL defines a referential integrity constraint on the `PublishedBy` association shown in the conceptual model above.</span></span>  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a><span data-ttu-id="fa856-123">См. также</span><span class="sxs-lookup"><span data-stu-id="fa856-123">See Also</span></span>  
 [<span data-ttu-id="fa856-124">Основные понятия модели EDM</span><span class="sxs-lookup"><span data-stu-id="fa856-124">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="fa856-125">Сущностная модель данных</span><span class="sxs-lookup"><span data-stu-id="fa856-125">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
