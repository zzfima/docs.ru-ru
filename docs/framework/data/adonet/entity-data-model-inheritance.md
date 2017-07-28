---
title: "Модель EDM: наследование | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 42c7ef24-710a-4af9-8493-cd41c399ecb0
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Модель EDM: наследование
Модель EDM поддерживает наследование для [типов сущности](../../../../docs/framework/data/adonet/entity-type.md).  Наследование в модели \(EDM\) схоже с наследованием для классов в языках объектно\-ориентированного программирования.  Как и в случае с классами в языках объектно\-ориентированного программирования, в концептуальной модели можно определить тип сущности \( *производный тип*\), который наследует свойства другого типа сущности \(*базовый тип*\).  Тем не менее, в отличие от классов в объектно\-ориентированном программировании, в концептуальной модели производный тип всегда наследует все [свойства](../../../../docs/framework/data/adonet/property.md) и [свойства навигации](../../../../docs/framework/data/adonet/navigation-property.md) базового типа.  В производном типе нельзя отменить унаследованные свойства.  
  
 В концептуальной модели можно построить иерархию наследования, в которой один производный тип наследует свойства другого производного типа.  Тип наверху иерархии \(тип в иерархии, который не является производным типом\) называется *корневым типом*.  В иерархии наследования [ключ сущности](../../../../docs/framework/data/adonet/entity-key.md) должен быть определен в корневом типе.  
  
 Нельзя построить иерархии наследования, в которых один производный тип наследует свойства более чем одного типа.  Например, в концептуальной модели с типом сущности `Book` можно определить производные типы `FictionBook` и `NonFictionBook`, из которых каждый наследует свойства `Book`.  Тем не менее, в дальнейшем нельзя определить тип, который бы наследовал свойства обоих типов `FictionBook` и `NonFictionBook`.  
  
## Пример  
 На приведенной ниже схеме показана концептуальная модель с четырьмя типами сущностей: `Book`, `FictionBook`, `Publisher` и `Author`.  Тип сущности `FictionBook` является производным типом, который наследует свойства от типа сущности `Book`.  Тип `FictionBook` наследует свойства `ISBN (Key)`, `Title` и `Revision`, а также определяет дополнительное свойство `Genre`.  
  
 ![Наследование](../../../../docs/framework/data/adonet/media/inheritanceexample.gif "InheritanceExample")  
  
 Платформа [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует доменный язык DSL, называемый языком CSDL \([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)\), для определения концептуальных моделей.  Далее язык CSDL определяет тип сущности, `FictionBook`, который наследует свойства типа `Book` \(как показано на схеме выше\).  
  
 [!code-xml[EDM_Example_Model#DerivedType](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books5.edmx#derivedtype)]  
  
## См. также  
 [Основные понятия модели EDM](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)   
 [Модель EDM](../../../../docs/framework/data/adonet/entity-data-model.md)