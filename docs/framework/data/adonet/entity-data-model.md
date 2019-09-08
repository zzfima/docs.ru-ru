---
title: EDM (модель данных с использованием сущностей)
ms.date: 03/30/2017
ms.assetid: 2dda3d5b-4582-4ba0-a91d-fcd7a1498137
ms.openlocfilehash: 1742b04d0e3d8387e990d40d832e355dd15c4311
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783961"
---
# <a name="entity-data-model"></a><span data-ttu-id="c2d39-102">EDM (модель данных с использованием сущностей)</span><span class="sxs-lookup"><span data-stu-id="c2d39-102">Entity Data Model</span></span>
<span data-ttu-id="c2d39-103">Модель EDM - это набор основных понятий, которые описывают структуру данных независимо от формы хранения.</span><span class="sxs-lookup"><span data-stu-id="c2d39-103">The Entity Data Model (EDM) is a set of concepts that describe the structure of data, regardless of its stored form.</span></span> <span data-ttu-id="c2d39-104">Модель EDM заимствует свойства модели «сущность-связь», описанной Питером Ченом в 1976 г., более того, она строится на модели «сущность-связь» и расширяет возможности ее традиционного использования.</span><span class="sxs-lookup"><span data-stu-id="c2d39-104">The EDM borrows from the Entity-Relationship Model described by Peter Chen in 1976, but it also builds on the Entity-Relationship Model and extends its traditional uses.</span></span>  
  
 <span data-ttu-id="c2d39-105">Модель EDM решает проблемы, возникающие из необходимости хранить данные в различных формах.</span><span class="sxs-lookup"><span data-stu-id="c2d39-105">The EDM addresses the challenges that arise from having data stored in many forms.</span></span> <span data-ttu-id="c2d39-106">Например, предположим, есть фирма, которая хранит данные в реляционных базах данных, текстовых файлах, файлах XML, электронных таблицах и отчетах.</span><span class="sxs-lookup"><span data-stu-id="c2d39-106">For example, consider a business that stores data in relational databases, text files, XML files, spreadsheets, and reports.</span></span> <span data-ttu-id="c2d39-107">Это является значительным препятствием для моделирования данных, проектирования приложений и доступа к данным.</span><span class="sxs-lookup"><span data-stu-id="c2d39-107">This presents significant challenges in data modeling, application design, and data access.</span></span> <span data-ttu-id="c2d39-108">Во время проектирования приложения, ориентированного на работу с данными, сложность заключается в написании эффективного и поддерживаемого кода без ущерба для эффективности доступа к данным, хранения и масштабируемости.</span><span class="sxs-lookup"><span data-stu-id="c2d39-108">When designing a data-oriented application, the challenge is to write efficient and maintainable code without sacrificing efficient data access, storage, and scalability.</span></span> <span data-ttu-id="c2d39-109">Если данные имеют реляционную структуру, доступ к данным, хранение и масштабируемость будут весьма эффективными, однако написание эффективного и поддерживаемого кода становится более сложным.</span><span class="sxs-lookup"><span data-stu-id="c2d39-109">When data has a relational structure, data access, storage, and scalability are very efficient, but writing efficient and maintainable code becomes more difficult.</span></span> <span data-ttu-id="c2d39-110">Если данные имеют структуру объектов, компромиссы отменяются: Написание эффективных и обслуживаемых кодов обусловлено затратами на эффективный доступ к данным, их хранение и масштабируемость.</span><span class="sxs-lookup"><span data-stu-id="c2d39-110">When data has an object structure, the trade-offs are reversed: Writing efficient and maintainable code comes at the cost of efficient data access, storage, and scalability.</span></span> <span data-ttu-id="c2d39-111">Даже если для этих компромиссов будут найдены правильные решения, при перемещении данных из одной формы в другую возникают новые трудности.</span><span class="sxs-lookup"><span data-stu-id="c2d39-111">Even if the right balance between these trade-offs can be found, new challenges arise when data is moved from one form to another.</span></span> <span data-ttu-id="c2d39-112">Модель EDM решает эти трудности путем описания структуры данных на основе сущностей и связей, которые являются независимыми от схем хранения.</span><span class="sxs-lookup"><span data-stu-id="c2d39-112">The Entity Data Model addresses these challenges by describing the structure of data in terms of entities and relationships that are independent of any storage schema.</span></span> <span data-ttu-id="c2d39-113">В результате форма хранения данных уже не имеет отношения к проектированию приложений и разработке.</span><span class="sxs-lookup"><span data-stu-id="c2d39-113">This makes the stored form of data irrelevant to application design and development.</span></span> <span data-ttu-id="c2d39-114">Поскольку сущности и связи описывают структуру данных так, как она используется в приложении (а не ее форму хранения), они могут эволюционировать по мере эволюции приложения.</span><span class="sxs-lookup"><span data-stu-id="c2d39-114">And, because entities and relationships describe the structure of data as it is used in an application (not its stored form), they can evolve as an application evolves.</span></span>  
  
 <span data-ttu-id="c2d39-115">`conceptual model` - это специфическое представление структуры данных в виде сущностей и связей, которое обычно определяется на доменном языке DSL, реализующем основные понятия модели EDM.</span><span class="sxs-lookup"><span data-stu-id="c2d39-115">A `conceptual model` is a specific representation of the structure of data as entities and relationships, and is generally defined in a domain-specific language (DSL) that implements the concepts of the EDM.</span></span> <span data-ttu-id="c2d39-116">[Язык CSDL](./ef/language-reference/csdl-specification.md) — это пример такого доменного языка.</span><span class="sxs-lookup"><span data-stu-id="c2d39-116">[Conceptual schema definition language (CSDL)](./ef/language-reference/csdl-specification.md) is an example of such a domain-specific language.</span></span> <span data-ttu-id="c2d39-117">Сущности и связи, описанные в концептуальной модели, можно представить в виде абстракций объектов и ассоциаций в приложении.</span><span class="sxs-lookup"><span data-stu-id="c2d39-117">Entities and relationships described in a conceptual model can be thought of as abstractions of objects and associations in an application.</span></span> <span data-ttu-id="c2d39-118">Это позволяет разработчикам сфокусировать внимание на концептуальной модели, не думая о схеме хранения, и писать эффективный и поддерживаемый код.</span><span class="sxs-lookup"><span data-stu-id="c2d39-118">This allows developers to focus on the conceptual model without concern for the storage schema, and allows them to write code with efficiency and maintainability in mind.</span></span> <span data-ttu-id="c2d39-119">Одновременно разработчики схем хранения могут сфокусировать внимание на эффективности доступа к данным, хранения и масштабируемости.</span><span class="sxs-lookup"><span data-stu-id="c2d39-119">Meanwhile storage schema designers can focus on the efficiency of data access, storage, and scalability.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c2d39-120">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="c2d39-120">In This Section</span></span>  
 <span data-ttu-id="c2d39-121">В подразделах этого раздела описываются основные понятия модели EDM.</span><span class="sxs-lookup"><span data-stu-id="c2d39-121">Topics in this section describe the concepts of the Entity Data Model.</span></span> <span data-ttu-id="c2d39-122">Любой специфический язык домена (DSL), реализующий модель EDM, должен включать основные понятия, описанные в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="c2d39-122">Any DSL that implements the EDM should include the concepts described here.</span></span> <span data-ttu-id="c2d39-123">Обратите внимание, что [ADO.NET Entity Framework](./ef/index.md) использует язык CSDL для определения концептуальных моделей.</span><span class="sxs-lookup"><span data-stu-id="c2d39-123">Note that the [ADO.NET Entity Framework](./ef/index.md) uses CSDL to define conceptual models.</span></span> <span data-ttu-id="c2d39-124">Для получения дополнительной информации см. [CSDL Specification](./ef/language-reference/csdl-specification.md).</span><span class="sxs-lookup"><span data-stu-id="c2d39-124">For more information, see [CSDL Specification](./ef/language-reference/csdl-specification.md).</span></span>  
  
 [<span data-ttu-id="c2d39-125">Основные понятия модели EDM</span><span class="sxs-lookup"><span data-stu-id="c2d39-125">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)  
  
 [<span data-ttu-id="c2d39-126">EDM: Пространства имен</span><span class="sxs-lookup"><span data-stu-id="c2d39-126">Entity Data Model: Namespaces</span></span>](entity-data-model-namespaces.md)  
  
 [<span data-ttu-id="c2d39-127">EDM: Примитивные типы данных</span><span class="sxs-lookup"><span data-stu-id="c2d39-127">Entity Data Model: Primitive Data Types</span></span>](entity-data-model-primitive-data-types.md)  
  
 [<span data-ttu-id="c2d39-128">EDM: Цепочк</span><span class="sxs-lookup"><span data-stu-id="c2d39-128">Entity Data Model: Inheritance</span></span>](entity-data-model-inheritance.md)  
  
 [<span data-ttu-id="c2d39-129">конечная точка ассоциации</span><span class="sxs-lookup"><span data-stu-id="c2d39-129">association end</span></span>](association-end.md)  
  
 [<span data-ttu-id="c2d39-130">кратность конечной точки ассоциации</span><span class="sxs-lookup"><span data-stu-id="c2d39-130">association end multiplicity</span></span>](association-end-multiplicity.md)  
  
 [<span data-ttu-id="c2d39-131">набор ассоциаций</span><span class="sxs-lookup"><span data-stu-id="c2d39-131">association set</span></span>](association-set.md)  
  
 [<span data-ttu-id="c2d39-132">конечная точка набора ассоциаций</span><span class="sxs-lookup"><span data-stu-id="c2d39-132">association set end</span></span>](association-set-end.md)  
  
 [<span data-ttu-id="c2d39-133">тип ассоциации</span><span class="sxs-lookup"><span data-stu-id="c2d39-133">association type</span></span>](association-type.md)  
  
 [<span data-ttu-id="c2d39-134">сложный тип</span><span class="sxs-lookup"><span data-stu-id="c2d39-134">complex type</span></span>](complex-type.md)  
  
 [<span data-ttu-id="c2d39-135">контейнер сущности</span><span class="sxs-lookup"><span data-stu-id="c2d39-135">entity container</span></span>](entity-container.md)  
  
 [<span data-ttu-id="c2d39-136">ключ сущности</span><span class="sxs-lookup"><span data-stu-id="c2d39-136">entity key</span></span>](entity-key.md)  
  
 [<span data-ttu-id="c2d39-137">набор сущности</span><span class="sxs-lookup"><span data-stu-id="c2d39-137">entity set</span></span>](entity-set.md)  
  
 [<span data-ttu-id="c2d39-138">тип сущности</span><span class="sxs-lookup"><span data-stu-id="c2d39-138">entity type</span></span>](entity-type.md)  
  
 [<span data-ttu-id="c2d39-139">facet</span><span class="sxs-lookup"><span data-stu-id="c2d39-139">facet</span></span>](facet.md)  
  
 [<span data-ttu-id="c2d39-140">свойство внешнего ключа</span><span class="sxs-lookup"><span data-stu-id="c2d39-140">foreign key property</span></span>](foreign-key-property.md)  
  
 [<span data-ttu-id="c2d39-141">объявляемая моделью функция</span><span class="sxs-lookup"><span data-stu-id="c2d39-141">model-declared function</span></span>](model-declared-function.md)  
  
 [<span data-ttu-id="c2d39-142">определяемая моделью функция</span><span class="sxs-lookup"><span data-stu-id="c2d39-142">model-defined function</span></span>](model-defined-function.md)  
  
 [<span data-ttu-id="c2d39-143">свойство навигации</span><span class="sxs-lookup"><span data-stu-id="c2d39-143">navigation property</span></span>](navigation-property.md)  
  
 [<span data-ttu-id="c2d39-144">свойство</span><span class="sxs-lookup"><span data-stu-id="c2d39-144">property</span></span>](property.md)  
  
 [<span data-ttu-id="c2d39-145">ограничение ссылочной целостности</span><span class="sxs-lookup"><span data-stu-id="c2d39-145">referential integrity constraint</span></span>](referential-integrity-constraint.md)  
  
## <a name="see-also"></a><span data-ttu-id="c2d39-146">См. также</span><span class="sxs-lookup"><span data-stu-id="c2d39-146">See also</span></span>

- <span data-ttu-id="c2d39-147">[Средства EDM ADO.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c2d39-147">[ADO.NET Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
- <span data-ttu-id="c2d39-148">[Общие сведения о файле EDMX](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c2d39-148">[.edmx File Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span></span>
- [<span data-ttu-id="c2d39-149">Спецификация CSDL</span><span class="sxs-lookup"><span data-stu-id="c2d39-149">CSDL Specification</span></span>](./ef/language-reference/csdl-specification.md)
