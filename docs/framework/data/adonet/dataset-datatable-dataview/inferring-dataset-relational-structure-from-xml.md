---
title: "Вывод реляционной структуры DataSet из XML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cd2f41c6-6785-420e-aa43-3ceb0bdccdce
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Вывод реляционной структуры DataSet из XML
Реляционная структура \(или схема\) набора данных <xref:System.Data.DataSet> состоит из таблиц, столбцов, ограничений и связей.  При загрузке <xref:System.Data.DataSet> из кода XML схема может быть определена заранее или создана, либо явно, либо с помощью вывода, на основании загружаемого кода XML.  Дополнительные сведения о загрузке схемы и содержимого набора данных <xref:System.Data.DataSet> из кода XML см. в разделах [Загрузка DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md) и [Загрузка сведений о схеме DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md).  
  
 Если схема набора данных <xref:System.Data.DataSet> создается из кода XML, то предпочтительным методом является явное определение схемы с использованием либо языка XSD \(как описано в разделе [Выведение реляционной структуры DataSet из схемы XML \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)\), либо языка XDR.  Если в коде XML отсутствуют схемы XSD или XDR , то схема <xref:System.Data.DataSet> может быть выведена на основании структуры элементов и атрибутов XML.  
  
 В настоящем разделе описаны правила вывода схемы <xref:System.Data.DataSet>; для этого показаны элементы, атрибуты XML и их структура, а затем схема <xref:System.Data.DataSet>, полученная путем вывода.  
  
 Не все атрибуты, присутствующие в XML\-документе, должны быть включены в процесс вывода.  Атрибуты с уточнением в виде пространств имен могут включать метаданные, которые являются значимыми для XML\-документа, но не для схемы <xref:System.Data.DataSet>.  Используя <xref:System.Data.DataSet.InferXmlSchema%2A>, можно указывать пространства имен, которые не должны учитываться в процессе вывода.  Для получения дополнительной информации см. [Загрузка сведений о схеме DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md).  
  
## В этом подразделе  
 [Сводка процесса вывода схемы DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/summary-of-the-dataset-schema-inference-process.md)  
 Предоставляет высокоуровневую сводку правил для вывода схемы <xref:System.Data.DataSet> с использованием кода XML.  
  
 [Выведение таблиц](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-tables.md)  
 Описывает элементы XML, которые в результате вывода становятся основанием для создания таблиц в <xref:System.Data.DataSet>.  
  
 [Вывод столбцов](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-columns.md)  
 Описывает элементы и атрибуты XML, которые в результате вывода становятся основанием для создания столбцов таблиц.  
  
 [Выведение связей](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-relationships.md)  
 Описывает объекты <xref:System.Data.DataRelation> и <xref:System.Data.ForeignKeyConstraint>, создаваемые для вложенных таблиц, полученных на основании вывода.  
  
 [Выведение текста элементов](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-element-text.md)  
 Описывает столбцы, которые создаются для текста в элементах XML, и поясняет условия, при которых текст в элементах XML не учитываются.  
  
 [Ограничения на вывод](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inference-limitations.md)  
 Обсуждает ограничения вывода схемы.  
  
## Связанные подразделы  
 [Использование XML в DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 Описывает, как объект <xref:System.Data.DataSet> взаимодействует с XML\-данными.  
  
 [Выведение реляционной структуры DataSet из схемы XML \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Описывает реляционную структуру \(или схему\) набора данных <xref:System.Data.DataSet>, которая создается с помощью схемы XSD.  
  
 [Общие сведения об ADO.NET](../../../../../docs/framework/data/adonet/ado-net-overview.md)  
 Описывает архитектуру, компоненты ADO.NET и способы их использования для доступа к существующим источникам данных и управления данными приложения.  
  
## См. также  
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)