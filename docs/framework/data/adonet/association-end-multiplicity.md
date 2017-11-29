---
title: "кратность конечной точки ассоциации"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 340926ee-aefb-4bef-92cc-453e5251fd03
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 3d6071b2dfab4a1f057c9e04b84e1163fb0a53c0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="association-end-multiplicity"></a><span data-ttu-id="6d2a5-102">кратность конечной точки ассоциации</span><span class="sxs-lookup"><span data-stu-id="6d2a5-102">association end multiplicity</span></span>
<span data-ttu-id="6d2a5-103">*Кратность конечной точки ассоциации* определяет количество [тип сущности](../../../../docs/framework/data/adonet/entity-type.md) экземпляров, которые могут быть на одном конце [ассоциации](../../../../docs/framework/data/adonet/association-type.md).</span><span class="sxs-lookup"><span data-stu-id="6d2a5-103">*Association end multiplicity* defines the number of [entity type](../../../../docs/framework/data/adonet/entity-type.md) instances that can be at one end of an [association](../../../../docs/framework/data/adonet/association-type.md).</span></span>  
  
 <span data-ttu-id="6d2a5-104">Кратность конечной точки ассоциации может иметь одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="6d2a5-104">An association end multiplicity can have one of the following values:</span></span>  
  
-   <span data-ttu-id="6d2a5-105">«один» (1): показывает, что на конечной точке ассоциации существует ровно один экземпляр типа сущности.</span><span class="sxs-lookup"><span data-stu-id="6d2a5-105">one (1): Indicates that exactly one entity type instance exists at the association end.</span></span>  
  
-   <span data-ttu-id="6d2a5-106">«ноль или один» (0..1): показывает, что на конечной точке ассоциации существует ноль, один или несколько экземпляров типа сущности.</span><span class="sxs-lookup"><span data-stu-id="6d2a5-106">zero or one (0..1): Indicates that zero or one entity type instances exist at the association end.</span></span>  
  
-   <span data-ttu-id="6d2a5-107">«много» (*): показывает, что на конечной точке ассоциации существует ноль, один или несколько экземпляров типа сущности.</span><span class="sxs-lookup"><span data-stu-id="6d2a5-107">many (*): Indicates that zero, one, or more entity type instances exist at the association end.</span></span>  
  
 <span data-ttu-id="6d2a5-108">Ассоциация зачастую характеризуется кратностями конечной точки ассоциации.</span><span class="sxs-lookup"><span data-stu-id="6d2a5-108">An association is often characterized by its association end multiplicities.</span></span> <span data-ttu-id="6d2a5-109">Например, если конечные точки ассоциации имеют кратности «один» (1) и «много» (*), ассоциация называется ассоциацией «один-ко-многим».</span><span class="sxs-lookup"><span data-stu-id="6d2a5-109">For example, if the ends of an association have multiplicities one (1) and many (*), the association is called a one-to-many association.</span></span> <span data-ttu-id="6d2a5-110">В следующем примере ассоциация `PublishedBy` является ассоциацией «один-ко-многим» (один издатель публикует много книг, а одна книга публикуется одним издателем).</span><span class="sxs-lookup"><span data-stu-id="6d2a5-110">In the example below, the `PublishedBy` association is a one-to-many association (a publisher publishes many books and a book is published by one publisher).</span></span> <span data-ttu-id="6d2a5-111">Ассоциация `WrittenBy` является ассоциацией «один-ко-многим» (одна книга может иметь несколько авторов, а один автор может написать несколько книг).</span><span class="sxs-lookup"><span data-stu-id="6d2a5-111">The `WrittenBy` association is a many-to-many association (a book can have multiple authors and an author can write multiple books).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d2a5-112">Пример</span><span class="sxs-lookup"><span data-stu-id="6d2a5-112">Example</span></span>  
 <span data-ttu-id="6d2a5-113">На приведенной ниже схеме показана концептуальная модель с двумя ассоциациями: `PublishedBy` и `WrittenBy`.</span><span class="sxs-lookup"><span data-stu-id="6d2a5-113">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="6d2a5-114">Конечные точки ассоциации для ассоциации `PublishedBy` - это типы сущности `Book` и `Publisher`.</span><span class="sxs-lookup"><span data-stu-id="6d2a5-114">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="6d2a5-115">Кратность конечной точки `Publisher` - «один» (1), а кратность конечной точки `Book` - «много» (*).</span><span class="sxs-lookup"><span data-stu-id="6d2a5-115">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (*).</span></span>  
  
 <span data-ttu-id="6d2a5-116">![Пример модели](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="6d2a5-116">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="6d2a5-117">Платформа ADO.NET Entity Framework использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) для определения концептуальных моделей.</span><span class="sxs-lookup"><span data-stu-id="6d2a5-117">The ADO.NET Entity Framework uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="6d2a5-118">Далее язык CSDL определяет ассоциацию `PublishedBy`, которая ранее приводилась в схеме.</span><span class="sxs-lookup"><span data-stu-id="6d2a5-118">The following CSDL defines the `PublishedBy` association shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a><span data-ttu-id="6d2a5-119">См. также</span><span class="sxs-lookup"><span data-stu-id="6d2a5-119">See Also</span></span>  
 [<span data-ttu-id="6d2a5-120">Основные понятия модели данных сущности</span><span class="sxs-lookup"><span data-stu-id="6d2a5-120">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="6d2a5-121">Модель EDM</span><span class="sxs-lookup"><span data-stu-id="6d2a5-121">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
