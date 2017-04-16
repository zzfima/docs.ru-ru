---
title: "объявляемая моделью функция | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: aba87f13-5685-4f6b-ad14-918e8a7d5c2a
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# объявляемая моделью функция
*Объявляемая моделью функция* \- это функция, которая объявлена в концептуальной модели, но не определена в этой концептуальной модели.  Функция может быть определена в среде размещения или хранения.  Например, объявляемая моделью функция может быть сопоставлена функции, определенной в базе данных, экспонируя таким образом функцию в концептуальной модели на стороне сервера.  
  
 Объявление объявляемой моделью функции содержит следующую информацию.  
  
-   Имя функции.  \(Обязательный атрибут\).  
  
-   Тип возвращаемого значения.  \(Необязательный параметр\).  
  
    > [!NOTE]
    >  Если возвращаемое значение не задано, возвращаемого значения не будет.  
  
-   Сведения о параметрах, включая имя и тип параметров.  \(Необязательный параметр\).  
  
## Пример  
 Платформа [Платформа ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует доменный язык DSL, называемый языком CSDL \([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)\), для определения концептуальных моделей.  На языке CSDL одной реализацией объявляемой моделью функции является [импорт функции](http://msdn.microsoft.com/ru-ru/125704ae-56c7-4233-80b7-389a10f3a65d).  Далее на языке CSDL определяется контейнер сущностей с определением импорта функции.  Обратите внимание, что возвращаемый тип для функции отсутствует, поскольку возвращаемый тип не задан.  
  
 [!code-xml[EDM_Example_Model#FunctionImport](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#functionimport)]  
  
## См. также  
 [Основные понятия модели EDM](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)   
 [Модель EDM](../../../../docs/framework/data/adonet/entity-data-model.md)