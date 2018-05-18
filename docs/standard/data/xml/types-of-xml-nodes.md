---
title: Типы XML-узлов
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 71d03b78-6898-4ce7-b0fc-1282573f31f7
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7f62a113865a481276c371f2fce55a5d9486eb00
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="types-of-xml-nodes"></a>Типы XML-узлов
Когда XML-документ считывается в память в виде дерева узлов, типы для узлов выбираются во время их создания. В модели XML DOM существует несколько типов узлов, определяемых консорциумом W3C и приведенных в разделе «1.1.1. Структурная модель DOM». В следующей таблице перечислены типы узлов, объекты, назначаемые каждому типу узла, и дано краткое описание типов.  
  
|Тип узла модели DOM|Object|Описание:|  
|-------------------|------------|-----------------|  
|Document|<xref:System.Xml.XmlDocument>|Контейнер для всех узлов в дереве. Он также называется корнем документа, что не всегда совпадает с корневым элементом.|  
|DocumentFragment|<xref:System.Xml.XmlDocumentFragment>|Временный контейнер, содержащий один или несколько узлов, не имеющих древовидной структуры.|  
|DocumentType;|<xref:System.Xml.XmlDocumentType>|Представляет узел `<!DOCTYPE…>`.|  
|EntityReference|<xref:System.Xml.XmlEntityReference>|Представляет текст нераскрытой ссылки на сущность.|  
|Элемент|<xref:System.Xml.XmlElement>|Представляет узел элемента.|  
|Attr|<xref:System.Xml.XmlAttribute>|Атрибут элемента.|  
|ProcessingInstruction;|<xref:System.Xml.XmlProcessingInstruction>|Узел инструкций по обработке.|  
|Комментарий|<xref:System.Xml.XmlComment>|Узел комментария.|  
|Text|<xref:System.Xml.XmlText>|Текст, принадлежащий элементу или атрибуту.|  
|CDATASection.|<xref:System.Xml.XmlCDataSection>|Представляет CDATA.|  
|Объект|<xref:System.Xml.XmlEntity>|Представляет декларации `<!ENTITY…>` в XML-документе, полученные из встроенного DTD или из внешних DTD и сущностей параметров.|  
|Notation|<xref:System.Xml.XmlNotation>|Представляет нотацию, объявленную в DTD.|  
  
 Атрибут (*attr*) упомянут в числе узлов модели W3C DOM на уровне 1 в разделе "1.2. Фундаментальные интерфейсы", но не считается дочерним ни для какого узла элемента.  
  
 В следующей таблице представлены дополнительные типы узлов, которые не определены консорциумом W3C, но доступны для использования в модели объектов Microsoft .NET Framework в виде перечислений **XmlNodeType**. Таким образом, для этих типов узлов отсутствует соответствующий столбец типа узла в модели DOM.  
  
|Тип узла|Описание:|  
|---------------|-----------------|  
|<xref:System.Xml.XmlDeclaration>|Представляет узел декларации `<?xml version="1.0"…>`.|  
|<xref:System.Xml.XmlSignificantWhitespace>|Представляет значимые пробелы, то есть пробелы в смешанном содержимом.|  
|<xref:System.Xml.XmlWhitespace>|Представляет пробелы в содержимом элемента.|  
|EndElement|Возвращается, когда модуль **XmlReader** достигает конца элемента.<br /><br /> Пример XML-кода: **\</item>**<br /><br /> Дополнительные сведения см. в разделе <xref:System.Xml.XmlNodeType>.|  
|EndEntity|Возвращается, когда модуль **XmlReader** достигает конца замещения сущности в результате вызова метода <xref:System.Xml.XmlReader.ResolveEntity%2A>. Дополнительные сведения см. в разделе <xref:System.Xml.XmlNodeType>.|  
  
 Пример кода, считывающего XML и использующего конструкцию case с типами узлов для вывода сведений об узле и его содержимом, см. в статье <xref:System.Xml.XmlSignificantWhitespace.NodeType%2A>.  
  
 Дополнительные сведения об иерархии объектов для типов узлов с указанием имен эквивалентных объектов см. в статье [Иерархия объектной модели (DOM) XML-документа](../../../../docs/standard/data/xml/xml-document-object-model-dom-hierarchy.md). Дополнительные сведения об объектах, создаваемых в дереве узлов, см. в статье [Сопоставление объектной иерархии с XML-данными](../../../../docs/standard/data/xml/mapping-the-object-hierarchy-to-xml-data.md).  
  
## <a name="see-also"></a>См. также  
 [Модель объектов документов XML (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
