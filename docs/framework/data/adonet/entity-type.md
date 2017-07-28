---
title: "тип сущности | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a6dee9ab-9e4a-48f2-a169-3f79cc15821c
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# тип сущности
*Тип сущности* \- это фундаментальный блок построения для описания структуры данных при помощи модели EDM.  В концептуальной модели тип сущности представляет структуру основных концептуальных элементов верхнего уровня, таких как клиенты или заказы.  Тип сущности \- это шаблон для экземпляров типов сущностей.  Каждый шаблон содержит следующие сведения.  
  
-   Уникальное имя.  \(Обязательно\).  
  
-   [Ключ сущности](../../../../docs/framework/data/adonet/entity-key.md), определенный одним или несколькими свойствами.  \(Обязательно\).  
  
-   Данные в форме одного или нескольких [свойств](../../../../docs/framework/data/adonet/property.md).  \(Необязательно.\)  
  
-   [Свойства навигации](../../../../docs/framework/data/adonet/navigation-property.md), которые позволяют переходить от одной [конечной точки](../../../../docs/framework/data/adonet/association-end.md) [ассоциации](../../../../docs/framework/data/adonet/association-type.md) к другой конечной точке.  \(Необязательный параметр\).  
  
 В приложении экземпляр типа сущности представляет определенный объект \(например, определенного клиента или заказ\).  Каждый экземпляр типа сущности должен иметь уникальный [ключ сущности](../../../../docs/framework/data/adonet/entity-key.md) внутри [набора сущностей](../../../../docs/framework/data/adonet/entity-set.md).  
  
 Два экземпляра типа сущности считаются равными, только если они являются экземплярами одного типа и значения их ключей сущности равны.  
  
## Пример  
 На приведенной ниже схеме показана концептуальная модель с тремя типами сущностей: `Book`, `Publisher` и `Author`.  
  
 ![Пример модели](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 Обратите внимание, что свойства каждого типа сущности, составляющего его ключ сущности, обозначаются знаком «\(Ключ\)».  
  
 Платформа [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует доменный язык DSL, называемый языком CSDL \([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)\), для определения концептуальных моделей.  Ниже на языке CSDL определяется тип сущности `Book`, который ранее приводился в схеме.  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## См. также  
 [Основные понятия модели EDM](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)   
 [Модель EDM](../../../../docs/framework/data/adonet/entity-data-model.md)   
 [facet \(аспект\)](../../../../docs/framework/data/adonet/facet.md)