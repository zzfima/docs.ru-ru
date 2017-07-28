---
title: "тип ассоциации | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 26c409f6-06e8-4441-ac78-1b1076a3c005
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# тип ассоциации
*Тип ассоциации* \(также называемый ассоциацией\) \- это фундаментальный блок построения для описания связей в модели EDM.  В концептуальной модели ассоциация представляет собой связь между двумя [типами сущностей](../../../../docs/framework/data/adonet/entity-type.md) \(такими как `Customer` и `Order`\).  В приложении экземпляр ассоциации представляет собой специфическую ассоциацию \(такую как ассоциация между экземпляром `Customer` и экземпляром `Order`\).  Экземпляры ассоциации логически сгруппированы в [набор ассоциаций](../../../../docs/framework/data/adonet/association-set.md).  
  
 Определение ассоциации содержит следующую информацию.  
  
-   Уникальное имя.  \(Обязательный атрибут\).  
  
-   Две [конечные точки ассоциаций](../../../../docs/framework/data/adonet/association-end.md), по одной на каждый из типов сущностей в связи.  \(Обязательный атрибут\).  
  
    > [!NOTE]
    >  Ассоциация не может представлять связь между более чем двумя типами сущностей.  Ассоциация может, тем не менее, определять связь с самим собой посредством указания одного и того же типа сущности для каждой из его конечных точек ассоциаций.  
  
-   [Ограничение ссылочной целостности](../../../../docs/framework/data/adonet/referential-integrity-constraint.md).  \(Необязательный параметр\).  
  
 Каждая конечная точка ассоциации должна определять [кратность конечной точки ассоциации](../../../../docs/framework/data/adonet/association-end-multiplicity.md), которая указывает число экземпляров типа сущности, могущих присутствовать на одной конечной точке ассоциации.  Кратность конечной точки ассоциации может иметь значение «один» \(1\), «нуль или один» \(0..1\) или «много» \(\*\).  Экземпляры типа сущности одной конечной точки ассоциации доступны посредством [свойств навигации](../../../../docs/framework/data/adonet/navigation-property.md) или внешних ключей, если они экспонируются в типе сущности.  Дополнительные сведения см. в разделе [Модель EDM: внешние ключи](../../../../docs/framework/data/adonet/foreign-key-property.md).  
  
## Пример  
 На приведенной ниже схеме показана концептуальная модель с двумя ассоциациями: `PublishedBy` и `WrittenBy`.  Конечные точки ассоциации для ассоциации `PublishedBy` \- это типы сущности `Book` и `Publisher`.  Кратность конечной точки `Publisher` \- «один» \(1\), а кратность конечной точки `Book` \- «много» \(\*\), что означает, что издатель публикует много книг, а одна книга публикуется одним издателем.  
  
 ![Пример модели](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 Платформа [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует доменный язык DSL, называемый языком CSDL \([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)\), для определения концептуальных моделей.  Далее язык CSDL определяет ассоциацию `PublishedBy`, которая ранее приводилась в схеме.  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## См. также  
 [Основные понятия модели EDM](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)   
 [Модель EDM](../../../../docs/framework/data/adonet/entity-data-model.md)