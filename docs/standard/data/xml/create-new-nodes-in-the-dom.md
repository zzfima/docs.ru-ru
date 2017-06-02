---
title: "Создание новых узлов в модели DOM | Microsoft Docs"
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
ms.assetid: 6c2b9789-b61a-49f9-b33f-db01a945edf2
caps.latest.revision: 4
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 4
---
# Создание новых узлов в модели DOM
<xref:System.Xml.XmlDocument> метод create для всех типов узлов. Для создания узла методу нужно передать имя (если необходимо) и содержимое или другие параметры для узлов, имеющих содержимое (например, текстовый узел). Далее представлены методы, которым необходимо передать имя и некоторые другие параметры для создания нужного узла.  
  
-   <xref:System.Xml.XmlDocument.CreateCDataSection%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateComment%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateDocumentFragment%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateDocumentType%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateElement%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateNode%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateProcessingInstruction%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateSignificantWhitespace%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateTextNode%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateWhitespace%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateXmlDeclaration%2A>  
  
 Для других типов узлов недостаточно просто задать данные параметров.  
  
 Сведения об атрибутах см. в разделе [создание новых атрибутов для элементов в модели DOM](../../../../docs/standard/data/xml/creating-new-attributes-for-elements-in-the-dom.md). Сведения о проверке имен элементов и атрибутов см. в разделе [-XML-элемент Проверка имен и атрибутов при создании новых узлов](../../../../docs/standard/data/xml/xml-element-and-attribute-name-verification-when-creating-new-nodes.md). Создание ссылок на сущности, в разделе [создание новых ссылок на сущности](../../../../docs/standard/data/xml/creating-new-entity-references.md). Сведения о влиянии пространств имен на раскрытие ссылок на сущности см. в разделе [влияние пространства имен на раскрытие ссылок на сущности для новых узлов, содержащих элементы и атрибуты](../../../../docs/standard/data/xml/namespace-affect-on-entity-ref-expansion-for-new-nodes.md).  
  
 После создания новых узлов становятся доступны несколько методов для вставки узлов в дерево. В таблице перечислены методы и описано место появления нового узла в модели XML DOM.  
  
|Метод|Размещение узла|  
|------------|--------------------|  
|<xref:System.Xml.XmlNode.InsertBefore%2A>|Вставляется перед узлом ссылки. Например, следующий код вставляет новый узел в позицию 5:<br /><br /> `Dim refChild As XmlNode = node.ChildNodes(4) 'The reference is zero-based.node.InsertBefore(newChild, refChild);`<br /><br /> `XmlNode refChild = node.ChildNodes[4]; //The reference is zero-based. node.InsertBefore(newChild, refChild);`<br /><br /> Дополнительные сведения см. в разделе <xref:System.Xml.XmlNode.InsertBefore%2A> метод.|  
|<xref:System.Xml.XmlNode.InsertAfter%2A>|Вставляется после узла ссылки. Например:<br /><br /> `node.InsertAfter(newChild, refChild)`<br /><br /> `node.InsertAfter(newChild, refChild);`<br /><br /> Дополнительные сведения см. в разделе <xref:System.Xml.XmlNode.InsertAfter%2A> метод.|  
|<xref:System.Xml.XmlNode.AppendChild%2A>|Добавляет узел в конец списка дочерних узлов заданного узла. Если добавляемый узел имеет <xref:System.Xml.XmlDocumentFragment>, все содержимое фрагмента документа перемещается в список дочерних узлов данного узла. Дополнительные сведения см. в разделе <xref:System.Xml.XmlNode.AppendChild%2A> метод.|  
|<xref:System.Xml.XmlNode.PrependChild%2A>|Добавляет узел в начало списка дочерних узлов заданного узла. Если добавляемый узел имеет <xref:System.Xml.XmlDocumentFragment>, все содержимое фрагмента документа перемещается в список дочерних узлов данного узла. Дополнительные сведения см. в разделе <xref:System.Xml.XmlNode.PrependChild%2A> метод.|  
|<xref:System.Xml.XmlAttributeCollection.Append%2A>|Добавляет <xref:System.Xml.XmlAttribute> узел в конец коллекции атрибутов, связанной с элементом. Дополнительные сведения см. в разделе <xref:System.Xml.XmlAttributeCollection.Append%2A> метод.|  
  
## <a name="see-also"></a>См. также  
 [Модель объектов XML-документов (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)