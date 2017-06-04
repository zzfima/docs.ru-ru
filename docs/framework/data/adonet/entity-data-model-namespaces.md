---
title: "Модель EDM. Пространство имен | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 98ab4226-bb9f-44e7-af46-61a9b1a4e47c
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Модель EDM. Пространство имен
Пространство имен в модели EDM \- это абстрактный контейнер для [типов сущностей](../../../../docs/framework/data/adonet/entity-type.md), [сложных типов](../../../../docs/framework/data/adonet/complex-type.md) и [ассоциаций](../../../../docs/framework/data/adonet/association-type.md).  Пространства имен в модели EDM схожи с пространствами имен в языке программирования: они обеспечивают контекст для объектов, которые они содержат, а также являются способом устранения неопределенности в отношении объектов, которые имеют одно и то же имя \(но содержатся в разных пространствах имен\).  
  
## Пример  
 Платформа [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует доменный язык DSL, называемый языком CSDL \([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)\), для определения концептуальных моделей.  В следующем коде на языке CSDL используется пространство имен для идентификации типа, определенного в другой концептуальной модели.  В примере определяется тип сущности \(`Publisher`\), который имеет свойство сложного типа \(`Address`\), импортированного из пространства имен `ExtendedBooksModel`.  Обратите внимание, что элемент `Using` указывает на то, что пространство имен было импортировано.  Также обратите внимание, что тип свойства `Address` определен при помощи своего полного имени \(`ExtendedBooksModel.Address`\) с указанием на то, что этот тип определен в пространстве имен `ExtendedBooksModel`.  
  
 [!code-xml[EDM_Example_Model#ImportedNamespace](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books6.edmx#importednamespace)]  
  
## См. также  
 [Основные понятия модели EDM](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)   
 [Модель EDM](../../../../docs/framework/data/adonet/entity-data-model.md)