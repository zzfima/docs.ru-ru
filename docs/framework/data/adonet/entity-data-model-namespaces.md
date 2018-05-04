---
title: Модель EDM. Пространство имен
ms.date: 03/30/2017
ms.assetid: 98ab4226-bb9f-44e7-af46-61a9b1a4e47c
ms.openlocfilehash: 0fdb007e70b7dd2e4a812d711cb6348e3f563bad
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="entity-data-model-namespaces"></a>Модель EDM. Пространство имен
Пространство имен в модели данных сущности (EDM) — абстрактный контейнер для [типов сущностей](../../../../docs/framework/data/adonet/entity-type.md), [сложные типы](../../../../docs/framework/data/adonet/complex-type.md), и [ассоциации](../../../../docs/framework/data/adonet/association-type.md). Пространства имен в модели EDM схожи с пространствами имен в языке программирования: они обеспечивают контекст для объектов, которые они содержат, а также являются способом устранения неопределенности в отношении объектов, которые имеют одно и то же имя (но содержатся в разных пространствах имен).  
  
## <a name="example"></a>Пример  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) для определения концептуальных моделей. В следующем коде на языке CSDL используется пространство имен для идентификации типа, определенного в другой концептуальной модели. В примере определяется тип сущности (`Publisher`), который имеет свойство сложного типа (`Address`), импортированного из пространства имен `ExtendedBooksModel`. Обратите внимание, что элемент `Using` указывает на то, что пространство имен было импортировано. Также обратите внимание, что тип свойства `Address` определен при помощи своего полного имени (`ExtendedBooksModel.Address`) с указанием на то, что этот тип определен в пространстве имен `ExtendedBooksModel`.  
  
 [!code-xml[EDM_Example_Model#ImportedNamespace](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books6.edmx#importednamespace)]  
  
## <a name="see-also"></a>См. также  
 [Основные понятия модели EDM](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [Сущностная модель данных](../../../../docs/framework/data/adonet/entity-data-model.md)
