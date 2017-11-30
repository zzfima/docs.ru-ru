---
title: "Сопоставление ограничений XML-схемы (XSD) с ограничениями набора данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d0d1a4b-9104-434f-ac04-6c01ab5716b5
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 9ac8e64c02d96450d41233cfbe65e1db839df9e7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="mapping-xml-schema-xsd-constraints-to-dataset-constraints"></a>Сопоставление ограничений XML-схемы (XSD) с ограничениями набора данных
Язык XSD позволяет задавать ограничения применительно к элементам и атрибутам, которые он определяет. При сопоставлении XML-схемы с реляционной схемой в <xref:System.Data.DataSet>, ограничения XML-схемы сопоставляются с соответствующими реляционными ограничениями таблиц и столбцов в **набора данных**.  
  
 В этом разделе рассматривается сопоставление следующих ограничений схемы XML:  
  
-   Ограничение уникальности, заданное с помощью **уникальный** элемента.  
  
-   Ограничение ключа, заданное с помощью **ключ** элемента.  
  
-   Ограничение keyref, заданное с помощью **keyref** элемента.  
  
 С помощью ограничения элемента или атрибута задаются определенные ограничения значений элемента в любом экземпляре документа. Например, ограничение по ключу **CustomerID** дочерний элемент элемента **клиента** элемента в схеме указывает, что значения **CustomerID** дочерний элемент должен быть Уникальный в любом экземпляре документа и не допускаются значения null.  
  
 Ограничения также можно указывать между элементами и атрибутами документа для установления связи внутри документа. Ограничения key и keyref используются в схеме для указания ограничения внутри документа, что приводит к созданию связи между элементами и атрибутами документа.  
  
 Процесс сопоставления преобразует ограничения схемы в соответствующие ограничения таблицы, созданные в **набора данных**.  
  
## <a name="in-this-section"></a>Содержание  
 [Сопоставление уникальных ограничений XML-схемы (XSD) набора данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-unique-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Описывает элементы схемы XML, используемые для создания ограничений unique в **набора данных**.  
  
 [Сопоставление ключевых ограничений XML-схемы (XSD) для ограничения набора данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-key-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Описывает элементы схемы XML, используемые для создания ключа ограничений (ограничения unique, где недопустимы значения null) в **набора данных**.  
  
 [Сопоставление ограничений схемы XML (XSD) keyref набора данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-keyref-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Описывает элементы схемы XML, используемые для создания keyref ограничений (внешний ключ) в **набора данных**.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Наследование реляционной структуры набора данных из схемы XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Описывает реляционную структуру или схему, из **набора данных** , созданную из схемы XSD.  
  
 [Создание отношений наборов данных из XML-схемы (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 Описывает элементы схемы XML, используемых для создания связей между столбцами таблиц в **набора данных**.  
  
## <a name="see-also"></a>См. также  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
