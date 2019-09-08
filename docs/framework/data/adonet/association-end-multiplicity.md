---
title: кратность конечной точки ассоциации
ms.date: 03/30/2017
ms.assetid: 340926ee-aefb-4bef-92cc-453e5251fd03
ms.openlocfilehash: cdcf69e7118620b2f8febd02d7695d429bf8cc2c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786943"
---
# <a name="association-end-multiplicity"></a><span data-ttu-id="a11d7-102">кратность конечной точки ассоциации</span><span class="sxs-lookup"><span data-stu-id="a11d7-102">association end multiplicity</span></span>
<span data-ttu-id="a11d7-103">*Кратность окончания ассоциации* определяет количество экземпляров [типа сущности](entity-type.md) , которые могут находиться в одном конце [ассоциации](association-type.md).</span><span class="sxs-lookup"><span data-stu-id="a11d7-103">*Association end multiplicity* defines the number of [entity type](entity-type.md) instances that can be at one end of an [association](association-type.md).</span></span>  
  
 <span data-ttu-id="a11d7-104">Кратность конечной точки ассоциации может иметь одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="a11d7-104">An association end multiplicity can have one of the following values:</span></span>  
  
- <span data-ttu-id="a11d7-105">один (1): Указывает, что в конце ассоциации существует ровно один экземпляр типа сущности.</span><span class="sxs-lookup"><span data-stu-id="a11d7-105">one (1): Indicates that exactly one entity type instance exists at the association end.</span></span>  
  
- <span data-ttu-id="a11d7-106">ноль или один (0.. 1): Указывает, что в конце ассоциации существует ноль или один экземпляр типа сущности.</span><span class="sxs-lookup"><span data-stu-id="a11d7-106">zero or one (0..1): Indicates that zero or one entity type instances exist at the association end.</span></span>  
  
- <span data-ttu-id="a11d7-107">Многие (\*): Указывает, что в конце ассоциации существует ноль, один или несколько экземпляров типа сущности.</span><span class="sxs-lookup"><span data-stu-id="a11d7-107">many (\*): Indicates that zero, one, or more entity type instances exist at the association end.</span></span>  
  
 <span data-ttu-id="a11d7-108">Ассоциация зачастую характеризуется кратностями конечной точки ассоциации.</span><span class="sxs-lookup"><span data-stu-id="a11d7-108">An association is often characterized by its association end multiplicities.</span></span> <span data-ttu-id="a11d7-109">Например, если элементы ассоциации имеют кратность один (1) и многие (\*), то Ассоциация называется связью «один ко многим».</span><span class="sxs-lookup"><span data-stu-id="a11d7-109">For example, if the ends of an association have multiplicities one (1) and many (\*), the association is called a one-to-many association.</span></span> <span data-ttu-id="a11d7-110">В следующем примере ассоциация `PublishedBy` является ассоциацией «один-ко-многим» (один издатель публикует много книг, а одна книга публикуется одним издателем).</span><span class="sxs-lookup"><span data-stu-id="a11d7-110">In the example below, the `PublishedBy` association is a one-to-many association (a publisher publishes many books and a book is published by one publisher).</span></span> <span data-ttu-id="a11d7-111">Ассоциация `WrittenBy` является ассоциацией «один-ко-многим» (одна книга может иметь несколько авторов, а один автор может написать несколько книг).</span><span class="sxs-lookup"><span data-stu-id="a11d7-111">The `WrittenBy` association is a many-to-many association (a book can have multiple authors and an author can write multiple books).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a11d7-112">Пример</span><span class="sxs-lookup"><span data-stu-id="a11d7-112">Example</span></span>  
 <span data-ttu-id="a11d7-113">На приведенной ниже схеме показана концептуальная модель с двумя ассоциациями: `PublishedBy` и `WrittenBy`.</span><span class="sxs-lookup"><span data-stu-id="a11d7-113">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="a11d7-114">Конечные точки ассоциации для ассоциации `PublishedBy` - это типы сущности `Book` и `Publisher`.</span><span class="sxs-lookup"><span data-stu-id="a11d7-114">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="a11d7-115">Кратность `Publisher` конца равна единице (1), а кратность `Book` элемента — many (\*).</span><span class="sxs-lookup"><span data-stu-id="a11d7-115">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (\*).</span></span>  
  
 ![Пример модели с тремя типами сущностей](./media/association-end-multiplicity/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="a11d7-117">Entity Framework ADO.NET использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](./ef/language-reference/csdl-specification.md)), для определения концептуальных моделей.</span><span class="sxs-lookup"><span data-stu-id="a11d7-117">The ADO.NET Entity Framework uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](./ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="a11d7-118">Далее язык CSDL определяет ассоциацию `PublishedBy`, которая ранее приводилась в схеме.</span><span class="sxs-lookup"><span data-stu-id="a11d7-118">The following CSDL defines the `PublishedBy` association shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a><span data-ttu-id="a11d7-119">См. также</span><span class="sxs-lookup"><span data-stu-id="a11d7-119">See also</span></span>

- [<span data-ttu-id="a11d7-120">Основные понятия модели EDM</span><span class="sxs-lookup"><span data-stu-id="a11d7-120">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="a11d7-121">Сущностная модель данных</span><span class="sxs-lookup"><span data-stu-id="a11d7-121">Entity Data Model</span></span>](entity-data-model.md)
