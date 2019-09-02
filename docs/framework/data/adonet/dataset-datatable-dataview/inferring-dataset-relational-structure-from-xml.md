---
title: Определение реляционной структуры набора данных из XML
ms.date: 03/30/2017
ms.assetid: cd2f41c6-6785-420e-aa43-3ceb0bdccdce
ms.openlocfilehash: 9b1932807058777a532457c99efc49f3ddfdf4ae
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204802"
---
# <a name="inferring-dataset-relational-structure-from-xml"></a>Определение реляционной структуры набора данных из XML
Реляционная структура (или схема) набора данных <xref:System.Data.DataSet> состоит из таблиц, столбцов, ограничений и связей. При загрузке <xref:System.Data.DataSet> из кода XML схема может быть определена заранее или создана, либо явно, либо с помощью вывода, на основании загружаемого кода XML. Дополнительные сведения о загрузке схемы и содержимого <xref:System.Data.DataSet> из XML-кода см. в разделе [Загрузка набора данных из XML](loading-a-dataset-from-xml.md) и [Загрузка данных схемы набора данных из XML](loading-dataset-schema-information-from-xml.md).  
  
 Если схема <xref:System.Data.DataSet> создается из XML, предпочтительным методом является явное указание схемы с помощью языка определения схемы XML (XSD) (как описано в разделе [наследование реляционной структуры набора данных из схемы XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)) или XML-Data Reduced (XDR). Если в коде XML отсутствуют схемы XSD или XDR , то схема <xref:System.Data.DataSet> может быть выведена на основании структуры элементов и атрибутов XML.  
  
 В настоящем разделе описаны правила вывода схемы <xref:System.Data.DataSet>; для этого показаны элементы, атрибуты XML и их структура, а затем схема <xref:System.Data.DataSet>, полученная путем вывода.  
  
 Не все атрибуты, присутствующие в XML-документе, должны быть включены в процесс вывода. Атрибуты с уточнением в виде пространств имен могут включать метаданные, которые являются значимыми для XML-документа, но не для схемы <xref:System.Data.DataSet>. Используя <xref:System.Data.DataSet.InferXmlSchema%2A>, можно указывать пространства имен, которые не должны учитываться в процессе вывода. Дополнительные сведения см. [в разделе Загрузка данных схемы набора данных из XML](loading-dataset-schema-information-from-xml.md).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Общие сведения о процессе определения схемы DataSet](summary-of-the-dataset-schema-inference-process.md)  
 Предоставляет высокоуровневую сводку правил для вывода схемы <xref:System.Data.DataSet> с использованием кода XML.  
  
 [Определение таблиц](inferring-tables.md)  
 Описывает элементы XML, которые в результате вывода становятся основанием для создания таблиц в <xref:System.Data.DataSet>.  
  
 [Определение столбцов](inferring-columns.md)  
 Описывает элементы и атрибуты XML, которые в результате вывода становятся основанием для создания столбцов таблиц.  
  
 [Определение отношений](inferring-relationships.md)  
 Описывает объекты <xref:System.Data.DataRelation> и <xref:System.Data.ForeignKeyConstraint>, создаваемые для вложенных таблиц, полученных на основании вывода.  
  
 [Определение текста элемента](inferring-element-text.md)  
 Описывает столбцы, которые создаются для текста в элементах XML, и поясняет условия, при которых текст в элементах XML не учитываются.  
  
 [Ограничения определения](inference-limitations.md)  
 Обсуждает ограничения вывода схемы.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Использование XML в наборах данных](using-xml-in-a-dataset.md)  
 Описывает, как объект <xref:System.Data.DataSet> взаимодействует с XML-данными.  
  
 [Наследование реляционной структуры DataSet от схемы XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Описывает реляционную структуру (или схему) набора данных <xref:System.Data.DataSet>, которая создается с помощью схемы XSD.  
  
 [Общие сведения об ADO.NET](../ado-net-overview.md)  
 Описывает архитектуру, компоненты ADO.NET и способы их использования для доступа к существующим источникам данных и управления данными приложения.  
  
## <a name="see-also"></a>См. также

- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
