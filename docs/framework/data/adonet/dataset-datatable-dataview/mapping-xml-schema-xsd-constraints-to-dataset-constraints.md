---
title: "Сопоставление ограничений схемы XML (XSD) с ограничениями DataSet | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3d0d1a4b-9104-434f-ac04-6c01ab5716b5
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Сопоставление ограничений схемы XML (XSD) с ограничениями DataSet
Язык XSD позволяет задавать ограничения применительно к элементам и атрибутам, которые он определяет.  При сопоставлении схемы XML с реляционной схемой в <xref:System.Data.DataSet> ограничения XML\-схемы сопоставляются с соответствующими реляционными ограничениями таблиц и столбцов в наборе данных **DataSet**.  
  
 В этом разделе рассматривается сопоставление следующих ограничений схемы XML:  
  
-   Ограничение уникальности, заданное с помощью элемента **unique**.  
  
-   Ограничение key, заданное с помощью элемента **key**.  
  
-   Ограничение keyref, заданное с помощью элемента **keyref**.  
  
 С помощью ограничения элемента или атрибута задаются определенные ограничения значений элемента в любом экземпляре документа.  Например, ограничение key для дочернего элемента **CustomerID** элемента **Customer** в схеме определяет, что значения дочернего элемента **CustomerID** должны быть уникальными в любом экземпляре документа, а значения NULL являются недопустимыми.  
  
 Ограничения также можно указывать между элементами и атрибутами документа для установления связи внутри документа.  Ограничения key и keyref используются в схеме для указания ограничения внутри документа, что приводит к созданию связи между элементами и атрибутами документа.  
  
 Процесс сопоставления преобразует ограничения схемы в соответствующие ограничения таблицы, созданные внутри **DataSet**.  
  
## В этом подразделе  
 [Сопоставление ограничений уникальности схемы XML \(XSD\) с ограничениями DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-unique-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Описывает элементы схемы XML, используемые для создания ограничений unique в **DataSet**.  
  
 [Сопоставление ограничений key схемы XML \(XSD\) с ограничениями DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-key-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Описывает элементы схемы XML, используемые для создания ограничений key \(либо ограничений unique там, где недопустимы значения NULL\) в **DataSet**.  
  
 [Сопоставление ограничений keyref схемы XML \(XSD\) с ограничениями DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-keyref-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Описывает элементы схемы XML, используемые для создания ограничений keyref \(внешнего ключа\) в **DataSet**.  
  
## Связанные подразделы  
 [Выведение реляционной структуры DataSet из схемы XML \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Описывает реляционную структуру \(схему\) **DataSet**, созданную из схемы XSD.  
  
 [Формирование связей DataSet на основе схемы XML \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 Описание элементов схемы XML, используемых для создания связей между столбцами таблиц в **DataSet**.  
  
## См. также  
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)