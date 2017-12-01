---
title: "Типы XML-узлов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 71d03b78-6898-4ce7-b0fc-1282573f31f7
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3914a2c5c06a2cc73f14bc473984094b474d537e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="types-of-xml-nodes"></a>Типы XML-узлов
Когда XML-документ считывается в память в виде дерева узлов, типы для узлов выбираются во время их создания. В модели XML DOM существует несколько типов узлов, определяемых консорциумом W3C и приведенных в разделе «1.1.1. Структурная модель DOM». В следующей таблице перечислены типы узлов, объекты, назначаемые каждому типу узла, и дано краткое описание типов.  
  
|Тип узла модели DOM|Объект|Описание|  
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
  
 Несмотря на то что атрибут (*attr*) указан в W3C DOM уровня 1 раздела 1.2 фундаментальные интерфейсы как узел, он не является потомком ни одного узла элемента.  
  
 В следующей таблице перечислены дополнительные типы узлов не определены консорциумом W3C, но доступны для использования в объектную модель Microsoft .NET Framework, как **XmlNodeType** перечисления. Таким образом, для этих типов узлов отсутствует соответствующий столбец типа узла в модели DOM.  
  
|Тип узла|Описание|  
|---------------|-----------------|  
|<xref:System.Xml.XmlDeclaration>|Представляет узел декларации `<?xml version="1.0"…>`.|  
|<xref:System.Xml.XmlSignificantWhitespace>|Представляет значимые пробелы, то есть пробелы в смешанном содержимом.|  
|<xref:System.Xml.XmlWhitespace>|Представляет пробелы в содержимом элемента.|  
|EndElement|Возвращается, когда **XmlReader** получает до конца элемента.<br /><br /> Пример XML-кода:  **\< /товар >**<br /><br /> Для получения дополнительной информации см. <xref:System.Xml.XmlNodeType>.|  
|EndEntity|Возвращается, когда **XmlReader** возвращает до конца замещения сущности в результате вызова <xref:System.Xml.XmlReader.ResolveEntity%2A>. Для получения дополнительной информации см. <xref:System.Xml.XmlNodeType>.|  
  
 Чтобы просмотреть пример кода, считывающего XML и использующего конструкцию case с типами узлов для вывода сведений об узле и его содержимом, см. <xref:System.Xml.XmlSignificantWhitespace.NodeType%2A>.  
  
 Дополнительные сведения об иерархии объектов типы узлов и именам эквивалентных объектов см. в разделе [иерархии объектной модели XML документа (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom-hierarchy.md). Дополнительные сведения об объектах, создаваемых в дереве узлов см. в разделе [сопоставление объектной иерархии с XML-данными](../../../../docs/standard/data/xml/mapping-the-object-hierarchy-to-xml-data.md).  
  
## <a name="see-also"></a>См. также  
 [Модель объектов XML-документов (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
