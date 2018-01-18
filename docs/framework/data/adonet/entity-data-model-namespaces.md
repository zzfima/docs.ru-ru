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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: b3e69017b5f617cff9bf2c159d5538a8c41e4cc0
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="entity-data-model-namespaces"></a><span data-ttu-id="5ee4e-102">Модель EDM. Пространство имен</span><span class="sxs-lookup"><span data-stu-id="5ee4e-102">Entity Data Model: Namespaces</span></span>
<span data-ttu-id="5ee4e-103">Пространство имен в модели данных сущности (EDM) — абстрактный контейнер для [типов сущностей](../../../../docs/framework/data/adonet/entity-type.md), [сложные типы](../../../../docs/framework/data/adonet/complex-type.md), и [ассоциации](../../../../docs/framework/data/adonet/association-type.md).</span><span class="sxs-lookup"><span data-stu-id="5ee4e-103">A namespace in the Entity Data Model (EDM) is an abstract container for [entity types](../../../../docs/framework/data/adonet/entity-type.md), [complex types](../../../../docs/framework/data/adonet/complex-type.md), and [associations](../../../../docs/framework/data/adonet/association-type.md).</span></span> <span data-ttu-id="5ee4e-104">Пространства имен в модели EDM схожи с пространствами имен в языке программирования: они обеспечивают контекст для объектов, которые они содержат, а также являются способом устранения неопределенности в отношении объектов, которые имеют одно и то же имя (но содержатся в разных пространствах имен).</span><span class="sxs-lookup"><span data-stu-id="5ee4e-104">Namespaces in the EDM are similar to namespaces in a programming language: they provide context for the objects that they contain and they provide a way to disambiguate objects that have the same name (but are contained in different namespaces).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ee4e-105">Пример</span><span class="sxs-lookup"><span data-stu-id="5ee4e-105">Example</span></span>  
 <span data-ttu-id="5ee4e-106">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) для определения концептуальных моделей.</span><span class="sxs-lookup"><span data-stu-id="5ee4e-106">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="5ee4e-107">В следующем коде на языке CSDL используется пространство имен для идентификации типа, определенного в другой концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="5ee4e-107">The following CSDL code uses a namespace to identify a type that is defined in a different conceptual model.</span></span> <span data-ttu-id="5ee4e-108">В примере определяется тип сущности (`Publisher`), который имеет свойство сложного типа (`Address`), импортированного из пространства имен `ExtendedBooksModel`.</span><span class="sxs-lookup"><span data-stu-id="5ee4e-108">The example defines an entity type (`Publisher`) that has a complex type property (`Address`) that is imported from the `ExtendedBooksModel` namespace.</span></span> <span data-ttu-id="5ee4e-109">Обратите внимание, что элемент `Using` указывает на то, что пространство имен было импортировано.</span><span class="sxs-lookup"><span data-stu-id="5ee4e-109">Note that the `Using` element indicates that a namespace has been imported.</span></span> <span data-ttu-id="5ee4e-110">Также обратите внимание, что тип свойства `Address` определен при помощи своего полного имени (`ExtendedBooksModel.Address`) с указанием на то, что этот тип определен в пространстве имен `ExtendedBooksModel`.</span><span class="sxs-lookup"><span data-stu-id="5ee4e-110">Also note that the type of the `Address` property is defined by using its fully qualified name (`ExtendedBooksModel.Address`), indicating that this type is defined in the `ExtendedBooksModel` namespace.</span></span>  
  
 [!code-xml[EDM_Example_Model#ImportedNamespace](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books6.edmx#importednamespace)]  
  
## <a name="see-also"></a><span data-ttu-id="5ee4e-111">См. также</span><span class="sxs-lookup"><span data-stu-id="5ee4e-111">See Also</span></span>  
 [<span data-ttu-id="5ee4e-112">Основные понятия модели EDM</span><span class="sxs-lookup"><span data-stu-id="5ee4e-112">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="5ee4e-113">Сущностная модель данных</span><span class="sxs-lookup"><span data-stu-id="5ee4e-113">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
