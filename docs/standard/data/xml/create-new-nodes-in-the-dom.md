---
title: Создание новых узлов в модели DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 6c2b9789-b61a-49f9-b33f-db01a945edf2
ms.openlocfilehash: f48990286405baee347becef87d0511cd42e9e77
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711003"
---
# <a name="create-new-nodes-in-the-dom"></a>Создание новых узлов в модели DOM
К классе <xref:System.Xml.XmlDocument> доступен метод для создания всех типов узлов. Для создания узла методу нужно передать имя (если необходимо) и содержимое или другие параметры для узлов, имеющих содержимое (например, текстовый узел). Далее представлены методы, которым необходимо передать имя и некоторые другие параметры для создания нужного узла.  
  
- <xref:System.Xml.XmlDocument.CreateCDataSection%2A>  
  
- <xref:System.Xml.XmlDocument.CreateComment%2A>  
  
- <xref:System.Xml.XmlDocument.CreateDocumentFragment%2A>  
  
- <xref:System.Xml.XmlDocument.CreateDocumentType%2A>  
  
- <xref:System.Xml.XmlDocument.CreateElement%2A>  
  
- <xref:System.Xml.XmlDocument.CreateNode%2A>  
  
- <xref:System.Xml.XmlDocument.CreateProcessingInstruction%2A>  
  
- <xref:System.Xml.XmlDocument.CreateSignificantWhitespace%2A>  
  
- <xref:System.Xml.XmlDocument.CreateTextNode%2A>  
  
- <xref:System.Xml.XmlDocument.CreateWhitespace%2A>  
  
- <xref:System.Xml.XmlDocument.CreateXmlDeclaration%2A>  
  
 Для других типов узлов недостаточно просто задать данные параметров.  
  
 См. дополнительные сведения по [созданию атрибутов для элементов в модели DOM](../../../../docs/standard/data/xml/creating-new-attributes-for-elements-in-the-dom.md). См. дополнительные сведения о [проверке имен атрибутов и элементов XML при создании узлов](../../../../docs/standard/data/xml/xml-element-and-attribute-name-verification-when-creating-new-nodes.md). См. дополнительные сведения о [создании ссылок на сущности](../../../../docs/standard/data/xml/creating-new-entity-references.md). См. дополнительные сведения о [влиянии пространства имен на раскрытие ссылок на сущности для новых узлов, содержащих элементы и атрибуты](../../../../docs/standard/data/xml/namespace-affect-on-entity-ref-expansion-for-new-nodes.md).  
  
 После создания новых узлов становятся доступны несколько методов для вставки узлов в дерево. В таблице перечислены методы и описано место появления нового узла в модели XML DOM.  
  
|Метод|Размещение узла|  
|------------|--------------------|  
|<xref:System.Xml.XmlNode.InsertBefore%2A>|Вставляется перед узлом ссылки. Например, следующий код вставляет новый узел в позицию 5:<br /><br /> `Dim refChild As XmlNode = node.ChildNodes(4) 'The reference is zero-based.node.InsertBefore(newChild, refChild);`<br /><br /> `XmlNode refChild = node.ChildNodes[4]; //The reference is zero-based. node.InsertBefore(newChild, refChild);`<br /><br /> Дополнительные сведения см. в описании метода <xref:System.Xml.XmlNode.InsertBefore%2A>.|  
|<xref:System.Xml.XmlNode.InsertAfter%2A>|Вставляется после узла ссылки. Например:<br /><br /> `node.InsertAfter(newChild, refChild)`<br /><br /> `node.InsertAfter(newChild, refChild);`<br /><br /> Дополнительные сведения см. в описании метода <xref:System.Xml.XmlNode.InsertAfter%2A>.|  
|<xref:System.Xml.XmlNode.AppendChild%2A>|Добавляет узел в конец списка дочерних узлов заданного узла. Если добавляемый узел представляет собой <xref:System.Xml.XmlDocumentFragment>, все содержимое фрагмента документа перемещается в дочерний список этого узла. Дополнительные сведения см. в описании метода <xref:System.Xml.XmlNode.AppendChild%2A>.|  
|<xref:System.Xml.XmlNode.PrependChild%2A>|Добавляет узел в начало списка дочерних узлов заданного узла. Если добавляемый узел представляет собой <xref:System.Xml.XmlDocumentFragment>, все содержимое фрагмента документа перемещается в дочерний список этого узла. Дополнительные сведения см. в описании метода <xref:System.Xml.XmlNode.PrependChild%2A>.|  
|<xref:System.Xml.XmlAttributeCollection.Append%2A>|Добавляет узел <xref:System.Xml.XmlAttribute> в конец коллекции атрибутов, связанной с элементом. Дополнительные сведения см. в описании метода <xref:System.Xml.XmlAttributeCollection.Append%2A>.|  
  
## <a name="see-also"></a>См. также:

- [Модель объектов документов XML (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
