---
title: "EDM (модель данных с использованием сущностей)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2dda3d5b-4582-4ba0-a91d-fcd7a1498137
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: e1a1bdeffcc85383d241c277240187ede41401cd
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="entity-data-model"></a><span data-ttu-id="ae5f2-102">EDM (модель данных с использованием сущностей)</span><span class="sxs-lookup"><span data-stu-id="ae5f2-102">Entity Data Model</span></span>
<span data-ttu-id="ae5f2-103">Модель EDM - это набор основных понятий, которые описывают структуру данных независимо от формы хранения.</span><span class="sxs-lookup"><span data-stu-id="ae5f2-103">The Entity Data Model (EDM) is a set of concepts that describe the structure of data, regardless of its stored form.</span></span> <span data-ttu-id="ae5f2-104">Модель EDM заимствует свойства модели «сущность-связь», описанной Питером Ченом в 1976 г., более того, она строится на модели «сущность-связь» и расширяет возможности ее традиционного использования.</span><span class="sxs-lookup"><span data-stu-id="ae5f2-104">The EDM borrows from the Entity-Relationship Model described by Peter Chen in 1976, but it also builds on the Entity-Relationship Model and extends its traditional uses.</span></span>  
  
 <span data-ttu-id="ae5f2-105">Модель EDM решает проблемы, возникающие из необходимости хранить данные в различных формах.</span><span class="sxs-lookup"><span data-stu-id="ae5f2-105">The EDM addresses the challenges that arise from having data stored in many forms.</span></span> <span data-ttu-id="ae5f2-106">Например, предположим, есть фирма, которая хранит данные в реляционных базах данных, текстовых файлах, файлах XML, электронных таблицах и отчетах.</span><span class="sxs-lookup"><span data-stu-id="ae5f2-106">For example, consider a business that stores data in relational databases, text files, XML files, spreadsheets, and reports.</span></span> <span data-ttu-id="ae5f2-107">Это является значительным препятствием для моделирования данных, проектирования приложений и доступа к данным.</span><span class="sxs-lookup"><span data-stu-id="ae5f2-107">This presents significant challenges in data modeling, application design, and data access.</span></span> <span data-ttu-id="ae5f2-108">Во время проектирования приложения, ориентированного на работу с данными, сложность заключается в написании эффективного и поддерживаемого кода без ущерба для эффективности доступа к данным, хранения и масштабируемости.</span><span class="sxs-lookup"><span data-stu-id="ae5f2-108">When designing a data-oriented application, the challenge is to write efficient and maintainable code without sacrificing efficient data access, storage, and scalability.</span></span> <span data-ttu-id="ae5f2-109">Если данные имеют реляционную структуру, доступ к данным, хранение и масштабируемость будут весьма эффективными, однако написание эффективного и поддерживаемого кода становится более сложным.</span><span class="sxs-lookup"><span data-stu-id="ae5f2-109">When data has a relational structure, data access, storage, and scalability are very efficient, but writing efficient and maintainable code becomes more difficult.</span></span> <span data-ttu-id="ae5f2-110">Если данные имеют структуру объекта, компромиссы приобретают обратный характер: написание эффективного и поддерживаемого кода наносит ущерб эффективности доступа к данным, хранения и масштабируемости.</span><span class="sxs-lookup"><span data-stu-id="ae5f2-110">When data has an object structure, the trade-offs are reversed: Writing efficient and maintainable code comes at the cost of efficient data access, storage, and scalability.</span></span> <span data-ttu-id="ae5f2-111">Даже если для этих компромиссов будут найдены правильные решения, при перемещении данных из одной формы в другую возникают новые трудности.</span><span class="sxs-lookup"><span data-stu-id="ae5f2-111">Even if the right balance between these trade-offs can be found, new challenges arise when data is moved from one form to another.</span></span> <span data-ttu-id="ae5f2-112">Модель EDM решает эти трудности путем описания структуры данных на основе сущностей и связей, которые являются независимыми от схем хранения.</span><span class="sxs-lookup"><span data-stu-id="ae5f2-112">The Entity Data Model addresses these challenges by describing the structure of data in terms of entities and relationships that are independent of any storage schema.</span></span> <span data-ttu-id="ae5f2-113">В результате форма хранения данных уже не имеет отношения к проектированию приложений и разработке.</span><span class="sxs-lookup"><span data-stu-id="ae5f2-113">This makes the stored form of data irrelevant to application design and development.</span></span> <span data-ttu-id="ae5f2-114">Поскольку сущности и связи описывают структуру данных так, как она используется в приложении (а не ее форму хранения), они могут эволюционировать по мере эволюции приложения.</span><span class="sxs-lookup"><span data-stu-id="ae5f2-114">And, because entities and relationships describe the structure of data as it is used in an application (not its stored form), they can evolve as an application evolves.</span></span>  
  
 <span data-ttu-id="ae5f2-115">`conceptual model` - это специфическое представление структуры данных в виде сущностей и связей, которое обычно определяется на доменном языке DSL, реализующем основные понятия модели EDM.</span><span class="sxs-lookup"><span data-stu-id="ae5f2-115">A `conceptual model` is a specific representation of the structure of data as entities and relationships, and is generally defined in a domain-specific language (DSL) that implements the concepts of the EDM.</span></span> <span data-ttu-id="ae5f2-116">[Язык определения концептуальной схемы (CSDL)](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md) приведен пример такого доменного языка.</span><span class="sxs-lookup"><span data-stu-id="ae5f2-116">[Conceptual schema definition language (CSDL)](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md) is an example of such a domain-specific language.</span></span> <span data-ttu-id="ae5f2-117">Сущности и связи, описанные в концептуальной модели, можно представить в виде абстракций объектов и ассоциаций в приложении.</span><span class="sxs-lookup"><span data-stu-id="ae5f2-117">Entities and relationships described in a conceptual model can be thought of as abstractions of objects and associations in an application.</span></span> <span data-ttu-id="ae5f2-118">Это позволяет разработчикам сфокусировать внимание на концептуальной модели, не думая о схеме хранения, и писать эффективный и поддерживаемый код.</span><span class="sxs-lookup"><span data-stu-id="ae5f2-118">This allows developers to focus on the conceptual model without concern for the storage schema, and allows them to write code with efficiency and maintainability in mind.</span></span> <span data-ttu-id="ae5f2-119">Одновременно разработчики схем хранения могут сфокусировать внимание на эффективности доступа к данным, хранения и масштабируемости.</span><span class="sxs-lookup"><span data-stu-id="ae5f2-119">Meanwhile storage schema designers can focus on the efficiency of data access, storage, and scalability.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ae5f2-120">Содержание</span><span class="sxs-lookup"><span data-stu-id="ae5f2-120">In This Section</span></span>  
 <span data-ttu-id="ae5f2-121">В подразделах этого раздела описываются основные понятия модели EDM.</span><span class="sxs-lookup"><span data-stu-id="ae5f2-121">Topics in this section describe the concepts of the Entity Data Model.</span></span> <span data-ttu-id="ae5f2-122">Любой специфический язык домена (DSL), реализующий модель EDM, должен включать основные понятия, описанные в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="ae5f2-122">Any DSL that implements the EDM should include the concepts described here.</span></span> <span data-ttu-id="ae5f2-123">Обратите внимание, что [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует язык CSDL для определения концептуальных моделей.</span><span class="sxs-lookup"><span data-stu-id="ae5f2-123">Note that the [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses CSDL to define conceptual models.</span></span> <span data-ttu-id="ae5f2-124">Дополнительные сведения см. в разделе [спецификация языка CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md).</span><span class="sxs-lookup"><span data-stu-id="ae5f2-124">For more information, see [CSDL Specification](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md).</span></span>  
  
 [<span data-ttu-id="ae5f2-125">Основные понятия модели EDM</span><span class="sxs-lookup"><span data-stu-id="ae5f2-125">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
  
 [<span data-ttu-id="ae5f2-126">Модель EDM. Пространство имен</span><span class="sxs-lookup"><span data-stu-id="ae5f2-126">Entity Data Model: Namespaces</span></span>](../../../../docs/framework/data/adonet/entity-data-model-namespaces.md)  
  
 [<span data-ttu-id="ae5f2-127">Модель EDM. Примитивные типы данных</span><span class="sxs-lookup"><span data-stu-id="ae5f2-127">Entity Data Model: Primitive Data Types</span></span>](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)  
  
 [<span data-ttu-id="ae5f2-128">Модель EDM. Наследование</span><span class="sxs-lookup"><span data-stu-id="ae5f2-128">Entity Data Model: Inheritance</span></span>](../../../../docs/framework/data/adonet/entity-data-model-inheritance.md)  
  
 [<span data-ttu-id="ae5f2-129">конечная точка ассоциации</span><span class="sxs-lookup"><span data-stu-id="ae5f2-129">association end</span></span>](../../../../docs/framework/data/adonet/association-end.md)  
  
 [<span data-ttu-id="ae5f2-130">кратность конечной точки ассоциации</span><span class="sxs-lookup"><span data-stu-id="ae5f2-130">association end multiplicity</span></span>](../../../../docs/framework/data/adonet/association-end-multiplicity.md)  
  
 [<span data-ttu-id="ae5f2-131">набор ассоциаций</span><span class="sxs-lookup"><span data-stu-id="ae5f2-131">association set</span></span>](../../../../docs/framework/data/adonet/association-set.md)  
  
 [<span data-ttu-id="ae5f2-132">конечная точка набора ассоциаций</span><span class="sxs-lookup"><span data-stu-id="ae5f2-132">association set end</span></span>](../../../../docs/framework/data/adonet/association-set-end.md)  
  
 [<span data-ttu-id="ae5f2-133">тип ассоциации</span><span class="sxs-lookup"><span data-stu-id="ae5f2-133">association type</span></span>](../../../../docs/framework/data/adonet/association-type.md)  
  
 [<span data-ttu-id="ae5f2-134">сложный тип</span><span class="sxs-lookup"><span data-stu-id="ae5f2-134">complex type</span></span>](../../../../docs/framework/data/adonet/complex-type.md)  
  
 [<span data-ttu-id="ae5f2-135">контейнер сущности</span><span class="sxs-lookup"><span data-stu-id="ae5f2-135">entity container</span></span>](../../../../docs/framework/data/adonet/entity-container.md)  
  
 [<span data-ttu-id="ae5f2-136">ключ сущности</span><span class="sxs-lookup"><span data-stu-id="ae5f2-136">entity key</span></span>](../../../../docs/framework/data/adonet/entity-key.md)  
  
 [<span data-ttu-id="ae5f2-137">набор сущности</span><span class="sxs-lookup"><span data-stu-id="ae5f2-137">entity set</span></span>](../../../../docs/framework/data/adonet/entity-set.md)  
  
 [<span data-ttu-id="ae5f2-138">тип сущности</span><span class="sxs-lookup"><span data-stu-id="ae5f2-138">entity type</span></span>](../../../../docs/framework/data/adonet/entity-type.md)  
  
 [<span data-ttu-id="ae5f2-139">facet</span><span class="sxs-lookup"><span data-stu-id="ae5f2-139">facet</span></span>](../../../../docs/framework/data/adonet/facet.md)  
  
 [<span data-ttu-id="ae5f2-140">свойство внешнего ключа</span><span class="sxs-lookup"><span data-stu-id="ae5f2-140">foreign key property</span></span>](../../../../docs/framework/data/adonet/foreign-key-property.md)  
  
 [<span data-ttu-id="ae5f2-141">объявляемая моделью функция</span><span class="sxs-lookup"><span data-stu-id="ae5f2-141">model-declared function</span></span>](../../../../docs/framework/data/adonet/model-declared-function.md)  
  
 [<span data-ttu-id="ae5f2-142">определяемая моделью функция</span><span class="sxs-lookup"><span data-stu-id="ae5f2-142">model-defined function</span></span>](../../../../docs/framework/data/adonet/model-defined-function.md)  
  
 [<span data-ttu-id="ae5f2-143">свойство навигации</span><span class="sxs-lookup"><span data-stu-id="ae5f2-143">navigation property</span></span>](../../../../docs/framework/data/adonet/navigation-property.md)  
  
 [<span data-ttu-id="ae5f2-144">свойство</span><span class="sxs-lookup"><span data-stu-id="ae5f2-144">property</span></span>](../../../../docs/framework/data/adonet/property.md)  
  
 [<span data-ttu-id="ae5f2-145">ограничение ссылочной целостности</span><span class="sxs-lookup"><span data-stu-id="ae5f2-145">referential integrity constraint</span></span>](../../../../docs/framework/data/adonet/referential-integrity-constraint.md)  
  
## <a name="see-also"></a><span data-ttu-id="ae5f2-146">См. также</span><span class="sxs-lookup"><span data-stu-id="ae5f2-146">See Also</span></span>  
 [<span data-ttu-id="ae5f2-147">Средства работы с моделью EDM ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ae5f2-147">ADO.NET Entity Data Model  Tools</span></span>](http://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)  
 [<span data-ttu-id="ae5f2-148">Общие сведения о файлах .edmx</span><span class="sxs-lookup"><span data-stu-id="ae5f2-148">.edmx File Overview</span></span>](http://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
 [<span data-ttu-id="ae5f2-149">Спецификация CSDL</span><span class="sxs-lookup"><span data-stu-id="ae5f2-149">CSDL Specification</span></span>](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)
