---
title: Определение реляционной структуры набора данных из XML
ms.date: 03/30/2017
ms.assetid: cd2f41c6-6785-420e-aa43-3ceb0bdccdce
ms.openlocfilehash: 6ded5e893ccca973f8be5f070f68d9d8c7e09678
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="inferring-dataset-relational-structure-from-xml"></a>Определение реляционной структуры набора данных из XML
Реляционная структура (или схема) набора данных <xref:System.Data.DataSet> состоит из таблиц, столбцов, ограничений и связей. При загрузке <xref:System.Data.DataSet> из кода XML схема может быть определена заранее или создана, либо явно, либо с помощью вывода, на основании загружаемого кода XML. Дополнительные сведения о загрузке схемы и содержимое <xref:System.Data.DataSet> из XML, в разделе [загрузка DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md) и [загрузки набора данных сведения о схеме из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md).  
  
 Если схема <xref:System.Data.DataSet> создается из XML, рекомендуется явно указать схему с помощью любого языка определения схем XML (XSD) (как описано в [наследование реляционной структуры набора данных из схемы XML (XSD) ](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)) или XML-Data Reduced (XDR). Если в коде XML отсутствуют схемы XSD или XDR , то схема <xref:System.Data.DataSet> может быть выведена на основании структуры элементов и атрибутов XML.  
  
 В настоящем разделе описаны правила вывода схемы <xref:System.Data.DataSet>; для этого показаны элементы, атрибуты XML и их структура, а затем схема <xref:System.Data.DataSet>, полученная путем вывода.  
  
 Не все атрибуты, присутствующие в XML-документе, должны быть включены в процесс вывода. Атрибуты с уточнением в виде пространств имен могут включать метаданные, которые являются значимыми для XML-документа, но не для схемы <xref:System.Data.DataSet>. Используя <xref:System.Data.DataSet.InferXmlSchema%2A>, можно указывать пространства имен, которые не должны учитываться в процессе вывода. Дополнительные сведения см. в разделе [загрузки набора данных сведения о схеме из XML-кода](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Общие сведения о процессе определения схемы DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/summary-of-the-dataset-schema-inference-process.md)  
 Предоставляет высокоуровневую сводку правил для вывода схемы <xref:System.Data.DataSet> с использованием кода XML.  
  
 [Определение таблиц](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-tables.md)  
 Описывает элементы XML, которые в результате вывода становятся основанием для создания таблиц в <xref:System.Data.DataSet>.  
  
 [Определение столбцов](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-columns.md)  
 Описывает элементы и атрибуты XML, которые в результате вывода становятся основанием для создания столбцов таблиц.  
  
 [Определение отношений](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-relationships.md)  
 Описывает объекты <xref:System.Data.DataRelation> и <xref:System.Data.ForeignKeyConstraint>, создаваемые для вложенных таблиц, полученных на основании вывода.  
  
 [Определение текста элемента](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-element-text.md)  
 Описывает столбцы, которые создаются для текста в элементах XML, и поясняет условия, при которых текст в элементах XML не учитываются.  
  
 [Ограничения определения](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inference-limitations.md)  
 Обсуждает ограничения вывода схемы.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Использование XML в наборах данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 Описывает, как объект <xref:System.Data.DataSet> взаимодействует с XML-данными.  
  
 [Наследование реляционной структуры DataSet от схемы XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Описывает реляционную структуру (или схему) набора данных <xref:System.Data.DataSet>, которая создается с помощью схемы XSD.  
  
 [Общие сведения об ADO.NET](../../../../../docs/framework/data/adonet/ado-net-overview.md)  
 Описывает архитектуру, компоненты ADO.NET и способы их использования для доступа к существующим источникам данных и управления данными приложения.  
  
## <a name="see-also"></a>См. также  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
