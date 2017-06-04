---
title: "кратность конечной точки ассоциации | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 340926ee-aefb-4bef-92cc-453e5251fd03
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# кратность конечной точки ассоциации
*Кратность конечной точки* определяет количество экземпляров [типа сущности](../../../../docs/framework/data/adonet/entity-type.md), которые могут быть на одной конечной точке [ассоциации](../../../../docs/framework/data/adonet/association-type.md).  
  
 Кратность конечной точки ассоциации может иметь одно из следующих значений.  
  
-   «один» \(1\): показывает, что на конечной точке ассоциации существует ровно один экземпляр типа сущности.  
  
-   «ноль или один» \(0..1\): показывает, что на конечной точке ассоциации существует ноль, один или несколько экземпляров типа сущности.  
  
-   «много» \(\*\): показывает, что на конечной точке ассоциации существует ноль, один или несколько экземпляров типа сущности.  
  
 Ассоциация зачастую характеризуется кратностями конечной точки ассоциации.  Например, если конечные точки ассоциации имеют кратности «один» \(1\) и «много» \(\*\), ассоциация называется ассоциацией «один\-ко\-многим».  В следующем примере ассоциация `PublishedBy` является ассоциацией «один\-ко\-многим» \(один издатель публикует много книг, а одна книга публикуется одним издателем\).  Ассоциация `WrittenBy` является ассоциацией «один\-ко\-многим» \(одна книга может иметь несколько авторов, а один автор может написать несколько книг\).  
  
## Пример  
 На приведенной ниже схеме показана концептуальная модель с двумя ассоциациями: `PublishedBy` и `WrittenBy`.  Конечные точки ассоциации для ассоциации `PublishedBy` \- это типы сущности `Book` и `Publisher`.  Кратность конечной точки `Publisher` \- «один» \(1\), а кратность конечной точки `Book` \- «много» \(\*\).  
  
 ![Пример модели](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 Платформа ADO.NET Entity Framework использует доменный язык DSL, называемый языком CSDL \([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)\), для определения концептуальных моделей.  Далее язык CSDL определяет ассоциацию `PublishedBy`, которая ранее приводилась в схеме.  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## См. также  
 [Основные понятия модели EDM](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)   
 [Модель EDM](../../../../docs/framework/data/adonet/entity-data-model.md)