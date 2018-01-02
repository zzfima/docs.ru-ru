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
ms.workload: dotnet
ms.openlocfilehash: 8ac310542ba9dea360acbc2a0fbcbb07b7a8d6fc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
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
  
## <a name="in-this-section"></a>В этом разделе  
 [Сопоставление уникальных ограничений схемы XML (XSD) с ограничениями DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-unique-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Описывает элементы схемы XML, используемые для создания ограничений unique в **набора данных**.  
  
 [Сопоставление ключевых ограничений схемы XML (XSD) с ограничениями DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-key-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Описывает элементы схемы XML, используемые для создания ключа ограничений (ограничения unique, где недопустимы значения null) в **набора данных**.  
  
 [Сопоставление ограничений схемы XML (XSD) keyref с ограничениями DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-keyref-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Описывает элементы схемы XML, используемые для создания keyref ограничений (внешний ключ) в **набора данных**.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Наследование реляционной структуры DataSet от схемы XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Описывает реляционную структуру или схему, из **набора данных** , созданную из схемы XSD.  
  
 [Создание отношений DataSet из схемы XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 Описывает элементы схемы XML, используемых для создания связей между столбцами таблиц в **набора данных**.  
  
## <a name="see-also"></a>См. также  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
