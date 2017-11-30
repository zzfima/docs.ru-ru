---
title: "Модель EDM. Пространство имен"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 98ab4226-bb9f-44e7-af46-61a9b1a4e47c
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 3e473453576f04e89b58806c5140e29855d7d022
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="entity-data-model-namespaces"></a><span data-ttu-id="d4fd1-102">Модель EDM. Пространство имен</span><span class="sxs-lookup"><span data-stu-id="d4fd1-102">Entity Data Model: Namespaces</span></span>
<span data-ttu-id="d4fd1-103">Пространство имен в модели данных сущности (EDM) — абстрактный контейнер для [типов сущностей](../../../../docs/framework/data/adonet/entity-type.md), [сложные типы](../../../../docs/framework/data/adonet/complex-type.md), и [ассоциации](../../../../docs/framework/data/adonet/association-type.md).</span><span class="sxs-lookup"><span data-stu-id="d4fd1-103">A namespace in the Entity Data Model (EDM) is an abstract container for [entity types](../../../../docs/framework/data/adonet/entity-type.md), [complex types](../../../../docs/framework/data/adonet/complex-type.md), and [associations](../../../../docs/framework/data/adonet/association-type.md).</span></span> <span data-ttu-id="d4fd1-104">Пространства имен в модели EDM схожи с пространствами имен в языке программирования: они обеспечивают контекст для объектов, которые они содержат, а также являются способом устранения неопределенности в отношении объектов, которые имеют одно и то же имя (но содержатся в разных пространствах имен).</span><span class="sxs-lookup"><span data-stu-id="d4fd1-104">Namespaces in the EDM are similar to namespaces in a programming language: they provide context for the objects that they contain and they provide a way to disambiguate objects that have the same name (but are contained in different namespaces).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4fd1-105">Пример</span><span class="sxs-lookup"><span data-stu-id="d4fd1-105">Example</span></span>  
 <span data-ttu-id="d4fd1-106">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) для определения концептуальных моделей.</span><span class="sxs-lookup"><span data-stu-id="d4fd1-106">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="d4fd1-107">В следующем коде на языке CSDL используется пространство имен для идентификации типа, определенного в другой концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="d4fd1-107">The following CSDL code uses a namespace to identify a type that is defined in a different conceptual model.</span></span> <span data-ttu-id="d4fd1-108">В примере определяется тип сущности (`Publisher`), который имеет свойство сложного типа (`Address`), импортированного из пространства имен `ExtendedBooksModel`.</span><span class="sxs-lookup"><span data-stu-id="d4fd1-108">The example defines an entity type (`Publisher`) that has a complex type property (`Address`) that is imported from the `ExtendedBooksModel` namespace.</span></span> <span data-ttu-id="d4fd1-109">Обратите внимание, что элемент `Using` указывает на то, что пространство имен было импортировано.</span><span class="sxs-lookup"><span data-stu-id="d4fd1-109">Note that the `Using` element indicates that a namespace has been imported.</span></span> <span data-ttu-id="d4fd1-110">Также обратите внимание, что тип свойства `Address` определен при помощи своего полного имени (`ExtendedBooksModel.Address`) с указанием на то, что этот тип определен в пространстве имен `ExtendedBooksModel`.</span><span class="sxs-lookup"><span data-stu-id="d4fd1-110">Also note that the type of the `Address` property is defined by using its fully qualified name (`ExtendedBooksModel.Address`), indicating that this type is defined in the `ExtendedBooksModel` namespace.</span></span>  
  
 [!code-xml[EDM_Example_Model#ImportedNamespace](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books6.edmx#importednamespace)]  
  
## <a name="see-also"></a><span data-ttu-id="d4fd1-111">См. также</span><span class="sxs-lookup"><span data-stu-id="d4fd1-111">See Also</span></span>  
 [<span data-ttu-id="d4fd1-112">Основные понятия модели данных сущности</span><span class="sxs-lookup"><span data-stu-id="d4fd1-112">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="d4fd1-113">Модель EDM</span><span class="sxs-lookup"><span data-stu-id="d4fd1-113">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
