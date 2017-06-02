---
title: "Типы XML-узлов | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 71d03b78-6898-4ce7-b0fc-1282573f31f7
caps.latest.revision: 4
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Типы XML-узлов
Когда XML\-документ считывается в память в виде дерева узлов, типы для узлов выбираются во время их создания.  В модели XML DOM существует несколько типов узлов, определяемых консорциумом W3C и приведенных в разделе «1.1.1. Структурная модель DOM».  В следующей таблице перечислены типы узлов, объекты, назначаемые каждому типу узла, и дано краткое описание типов.  
  
|Тип узла модели DOM|Объект|Описание|  
|-------------------------|------------|--------------|  
|Document|[Класс XmlDocument](frlrfSystemXmlXmlDocumentClassTopic)|Контейнер для всех узлов в дереве.  Он также называется корнем документа, что не всегда совпадает с корневым элементом.|  
|DocumentFragment|[Класс XmlDocumentFragment](frlrfSystemXmlXmlDocumentFragmentClassTopic)|Временный контейнер, содержащий один или несколько узлов, не имеющих древовидной структуры.|  
|DocumentType;|[Класс XmlDocumentType](frlrfSystemXmlXmlDocumentTypeClassTopic)|Представляет узел `<!DOCTYPE…>`.|  
|EntityReference|[Класс XmlEntityReference](frlrfSystemXmlXmlEntityReferenceClassTopic)|Представляет текст нераскрытой ссылки на сущность.|  
|Элемент|[Класс XmlElement](frlrfSystemXmlXmlElementClassTopic)|Представляет узел элемента.|  
|Attr|[Класс XmlAttribute](frlrfSystemXmlXmlAttributeClassTopic)|Атрибут элемента.|  
|ProcessingInstruction;|[Класс XmlProcessingInstruction](frlrfSystemXmlXmlProcessingInstructionClassTopic)|Узел инструкций по обработке.|  
|Комментарий|[Класс XmlComment](frlrfSystemXmlXmlCommentClassTopic)|Узел комментария.|  
|Text|[Класс XmlText](frlrfSystemXmlXmlTextClassTopic)|Текст, принадлежащий элементу или атрибуту.|  
|CDATASection.|[Класс XmlCDataSection](frlrfSystemXmlXmlCDataSectionClassTopic)|Представляет CDATA.|  
|Сущность|[Класс XmlEntity](frlrfSystemXmlXmlEntityClassTopic)|Представляет декларации `<!ENTITY…>` в XML\-документе, полученные из встроенного DTD или из внешних DTD и сущностей параметров.|  
|Notation|[Класс XmlNotation](frlrfSystemXmlXmlNotationClassTopic)|Представляет нотацию, объявленную в DTD.|  
  
 Атрибут \(*attr*\) упомянут в числе узлов модели W3C DOM на уровне 1 в разделе «1.2. Фундаментальные интерфейсы», но не считается дочерним ни для какого узла элемента.  
  
 В следующей таблице показаны дополнительные типы узлов, которые не определены консорциумом W3C, но доступны для использования в модели объектов Microsoft .NET Framework в виде перечислений **XmlNodeType**.  Таким образом, для этих типов узлов отсутствует соответствующий столбец типа узла в модели DOM.  
  
|Тип узла|Описание|  
|--------------|--------------|  
|<xref:System.Xml.XmlDeclaration>|Представляет узел декларации `<?xml version="1.0"…>`.|  
|<xref:System.Xml.XmlSignificantWhitespace>|Представляет значимые пробелы, то есть пробелы в смешанном содержимом.|  
|<xref:System.Xml.XmlWhitespace>|Представляет пробелы в содержимом элемента.|  
|EndElement|Возвращается, когда модуль **XmlReader** достигает конца элемента.<br /><br /> Пример XML\-кода: **\<\/item\>**<br /><br /> Дополнительные сведения см. в разделе [Перечисление XmlNodeType](frlrfSystemXmlXmlNodeTypeClassTopic).|  
|EndEntity|Возвращается, когда модуль **XmlReader** достигает конца замещения сущности в результате вызова метода <xref:System.Xml.XmlReader.ResolveEntity%2A>.  Дополнительные сведения см. в разделе [Перечисление XmlNodeType](frlrfSystemXmlXmlNodeTypeClassTopic).|  
  
 Пример кода, считывающего XML и использующего конструкцию case с типами узлов для вывода сведений об узле и его содержимом, см. в разделе [Свойство XmlSignificantWhitespace.NodeType](frlrfSystemXmlXmlSignificantWhitespaceClassNodeTypeTopic).  
  
 Дополнительные сведения по иерархии объектов для типов узлов и именам эквивалентных объектов см. в разделе [Иерархия модели XML DOM](../../../../docs/standard/data/xml/xml-document-object-model-dom-hierarchy.md).  Дополнительные сведения об объектах, создаваемых в дереве узлов, см. в разделе [Сопоставление объектной иерархии с XML\-данными](../../../../docs/standard/data/xml/mapping-the-object-hierarchy-to-xml-data.md).  
  
## См. также  
 [Модель DOM для XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)