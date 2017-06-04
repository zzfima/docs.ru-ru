---
title: "конечная точка набора ассоциаций | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fe4bf1d3-047a-4a37-98c5-a66e70811346
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# конечная точка набора ассоциаций
*Конечная точка набора ассоциаций* идентифицирует [тип сущности](../../../../docs/framework/data/adonet/entity-type.md) и [набор сущностей](../../../../docs/framework/data/adonet/entity-set.md) на конечной точке [набора сущностей](../../../../docs/framework/data/adonet/association-set.md).  Конечные точки набора ассоциаций определяются как часть набора ассоциаций; набор ассоциаций должен иметь ровно две конечные точки.  
  
 Определение конечной точки набора ассоциаций содержит следующую информацию.  
  
-   Один из типов сущностей, участвующих в наборе ассоциаций.  \(Обязательный атрибут\).  
  
-   Набор сущностей для типа сущностей, участвующих в наборе ассоциаций.  \(Обязательный атрибут\).  
  
## Пример  
 На приведенной ниже схеме показана концептуальная модель с двумя ассоциациями: `WrittenBy` и `PublishedBy`.  
  
 ![Пример модели](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 На следующей схеме показаны один набор ассоциаций \(`PublishedBy` и `Books`\) и два набора сущностей \(`Publishers`\) на основе приведенной выше концептуальной модели.  Конечные точки набора ассоциаций \- это наборы сущностей `Books` и `Publishers`.  Bi в наборе сущностей `Books` представляет экземпляр типа сущности `Book` во время выполнения.  Аналогично Pj представляет экземпляр `Publisher` в наборе сущностей `Publishers`.  BiPj представляет экземпляр ассоциации `PublishedBy` в наборе ассоциаций `PublishedBy`.  
  
 ![Пример наборов](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")  
  
 Платформа [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует доменный язык DSL, называемый языком CSDL \([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)\), для определения концептуальных моделей.  Далее на языке CSDL определяется контейнер сущностей с одним набором ассоциаций для каждой ассоциации на приведенной выше схеме.  Обратите внимание, что конечные точки набора ассоциаций определяются как часть каждого определения набора ассоциаций.  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## См. также  
 [Основные понятия модели EDM](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)   
 [Модель EDM](../../../../docs/framework/data/adonet/entity-data-model.md)