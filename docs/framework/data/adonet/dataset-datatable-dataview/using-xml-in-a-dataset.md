---
title: "Использование XML в наборах данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 35138159-e199-49ec-baf7-1ec6777e171e
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 28c1668dcb9678b65db62c0040adcd116221b92e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="using-xml-in-a-dataset"></a>Использование XML в наборах данных
В ADO.NET можно заполнить <xref:System.Data.DataSet> из XML-потока или документа. XML-поток или XML-документ можно использовать для предоставления объекту <xref:System.Data.DataSet> данных, информации о схеме или того и другого. Данные из XML-потока или документа можно комбинировать с существующими в <xref:System.Data.DataSet> данными или сведениями о схеме.  
  
 ADO.NET также позволяет создавать XML-представление <xref:System.Data.DataSet> с его схемой или без нее с целью передать <xref:System.Data.DataSet> по HTTP для использования в другом приложении или на платформе, поддерживающей XML. В XML-представлении набора данных <xref:System.Data.DataSet> данные записываются на языке XML, а схема, если она встроена в представление, записывается на языке XSD. XML и схема XML предоставляют удобный формат для передачи содержимого объекта <xref:System.Data.DataSet> удаленному клиенту и обратно.  
  
## <a name="in-this-section"></a>Содержание  
 [Дельты](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)  
 Содержит подробные сведения о DiffGram, XML-формате, который используется для чтения и записи содержимого класса <xref:System.Data.DataSet>.  
  
 [Загрузка набора данных из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 Объясняет различные параметры, которые следует учитывать при загрузке содержимого класса <xref:System.Data.DataSet> из XML-документа.  
  
 [Запись содержимого набора как XML-данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)  
 Объясняет способы создания содержимого класса <xref:System.Data.DataSet> в виде XML-данных и различные доступные параметры XML-формата.  
  
 [Загрузка сведений о схеме набора данных из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 Объясняет методы класса <xref:System.Data.DataSet>, которые используются для загрузки схемы <xref:System.Data.DataSet> из XML.  
  
 [Запись сведений о схеме набора данных как XSD](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-schema-information-as-xsd.md)  
 Объясняет использование схемы XML и ее создание из класса <xref:System.Data.DataSet>.  
  
 [Набор данных и XmlDataDocument синхронизации](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)  
 Объясняет доступные в .NET Framework возможности синхронного доступа как к реляционным, так и иерархическим представлениям одного набора данных, а также демонстрирует создание синхронных связей между <xref:System.Data.DataSet> и <xref:System.Xml.XmlDataDocument>.  
  
 [Вложение отношений DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 Объясняет значение вложенных объектов <xref:System.Data.DataRelation> при представлении содержимого класса <xref:System.Data.DataSet> как XML-данных и описывает создание этих объектов.  
  
 [Наследование реляционной структуры набора данных из схемы XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Объясняет реляционную структуру (схему) класса <xref:System.Data.DataSet>, созданную из схемы XML.  
  
 [Определение реляционной структуры набора данных из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 Объясняет полученную реляционную структуру (или схему) класса <xref:System.Data.DataSet>, созданную при использовании XML-элементов.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Общие сведения об ADO.NET](../../../../../docs/framework/data/adonet/ado-net-overview.md)  
 Описывает архитектуру и компоненты ADO.NET, а также способы их использования для доступа к существующим источникам данных и управления данными приложения.  
  
## <a name="see-also"></a>См. также  
 [Наборы данных, таблицы данных и объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
