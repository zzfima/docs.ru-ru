---
title: "набор ассоциаций | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a65247b6-ce59-44ea-974c-14ae20a7995f
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# набор ассоциаций
*Набор ассоциаций* \- это логический контейнер для экземпляров [ассоциации](../../../../docs/framework/data/adonet/association-type.md) одного и того же типа.  Набор ассоциаций не является конструктом моделирования данных, то есть не описывает структуру данных или связи.  Вместо этого ассоциация обеспечивает конструкт для среды размещения или хранения \(например, для среды CLR или базы данных сервера SQL\), позволяя группировать экземпляры ассоциаций так, чтобы они были сопоставлены хранилищу данных.  
  
 Набор ассоциаций определяется внутри [контейнера сущностей](../../../../docs/framework/data/adonet/entity-container.md), который является логической группой наборов сущностей и [наборов ассоциаций](../../../../docs/framework/data/adonet/entity-set.md).  
  
 Определение набора ассоциаций содержит следующую информацию.  
  
-   Имя набора ассоциаций.  \(Обязательный атрибут\).  
  
-   Ассоциация, экземпляры которой будут являться содержимым.  \(Обязательный атрибут\).  
  
-   Две [конечные точки набора ассоциаций](../../../../docs/framework/data/adonet/association-set-end.md).  
  
## Пример  
 На приведенной ниже схеме показана концептуальная модель с двумя ассоциациями: `PublishedBy` и `WrittenBy`.  Информации о наборах ассоциаций не содержится в схеме, однако на следующей схеме показан пример наборов ассоциаций и наборов сущностей на основе этой модели.  
  
 ![Пример модели](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 В следующем примере показан набор ассоциаций \(`PublishedBy`\) и два набора сущностей \(`Books` и `Publishers`\) на основе приведенной выше концептуальной модели.  Bi в наборе сущностей `Books` представляет экземпляр типа сущности `Book` во время выполнения.  Аналогично Pj представляет экземпляр `Publisher` в наборе сущностей `Publishers`.  BiPj представляет экземпляр ассоциации `PublishedBy` в наборе ассоциаций `PublishedBy`.  
  
 ![Пример наборов](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")  
  
 Платформа [Платформа ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует доменный язык DSL, называемый языком CSDL \([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)\), для определения концептуальных моделей.  Далее на языке CSDL определяется контейнер сущностей с одним набором ассоциаций для каждой ассоциации на приведенной выше схеме.  Обратите внимание, что имя и ассоциация для каждого набора ассоциаций определены при помощи атрибутов XML.  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
 Можно определить несколько наборов ассоциаций на одну ассоциацию, если два набора ассоциаций не имеют одной и той же [конечной точки ассоциации](../../../../docs/framework/data/adonet/association-set-end.md).  Далее на языке CSDL определяется контейнер сущностей с двумя наборами ассоциаций для ассоциации `WrittenBy`:  Обратите внимание, что несколько наборов сущностей были определены для типов сущностей `Book` и `Author` и что наборы ассоциаций не имеют одной и той же конечной точки ассоциации.  
  
 [!code-xml[EDM_Example_Model#MultipleAssociationSets](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#multipleassociationsets)]  
  
## См. также  
 [Основные понятия модели EDM](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)   
 [Модель EDM](../../../../docs/framework/data/adonet/entity-data-model.md)   
 [свойство внешнего ключа](../../../../docs/framework/data/adonet/foreign-key-property.md)