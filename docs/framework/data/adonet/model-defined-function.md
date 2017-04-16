---
title: "функция определенной модели | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8bb2edc8-e8e7-44c2-adc7-f44e11bda4f0
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# функция определенной модели
*Определяемая моделью функция* \- это функция, определяемая в концептуальной модели.  Текст определяемой моделью функции представлен в [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md), при этом функция может быть представлена независимо от правил или языков, поддерживаемых в источнике данных.  
  
 Определение определяемой моделью функции содержит следующие сведения.  
  
-   Имя функции.  \(Обязательный атрибут\).  
  
-   Тип возвращаемого значения.  \(Необязательный параметр\).  
  
    > [!NOTE]
    >  Если тип возвращаемого значения не задан, возвращаемого значения не будет.  
  
-   Сведения о параметрах.  \(Необязательный параметр\).  
  
-   Выражение [сущности SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md), которое определяет текст функции.  
  
 Обратите внимание, что определяемые моделью функции не поддерживают выходные параметры.  Это ограничение введено, чтобы определяемые моделью функции можно было сочетать.  
  
## Пример  
 На приведенной ниже схеме показана концептуальная модель с тремя типами сущностей: `Book`, `Publisher` и `Author`.  
  
 ![Модель с датой публикации](../../../../docs/framework/data/adonet/media/modelwithpublisheddate.gif "ModelWithPublishedDate")  
  
 Платформа [Платформа ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует доменный язык DSL, называемый языком CSDL \([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)\), для определения концептуальных моделей.  Следующий язык CSDL определяет функцию в концептуальной модели, которая возвращает числа лет с момента публикации экземпляра `Book` \(ранее приведенного на схеме\).  
  
 [!code-xml[EDM_Example_Model#ModelDefinedFunction](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#modeldefinedfunction)]  
  
## См. также  
 [Основные понятия модели EDM](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)   
 [Модель EDM](../../../../docs/framework/data/adonet/entity-data-model.md)   
 [Модель EDM. Примитивные типы данных](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)