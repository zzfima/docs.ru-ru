---
title: "Удаление узлов из DOM | Microsoft Docs"
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
ms.assetid: 0a98e0ca-0555-45c1-ab69-0d8d20ca1abd
caps.latest.revision: 3
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Удаление узлов из DOM
Для удаления узла из модели DOM XML\-документа используется метод <xref:System.Xml.XmlNode.RemoveChild%2A>, с помощью которого удаляется конкретный узел.  При удалении узла метод удаляет поддерево, принадлежащее удаляемому узлу т.е. если это не конечный узел.  
  
 Для удаления нескольких узлов из DOM используется метод <xref:System.Xml.XmlNode.RemoveAll%2A>, удаляющий все дочерние узлы и атрибуты \(если применимо\) текущего узла.  
  
 При работе с классом <xref:System.Xml.XmlNamedNodeMap> можно удалить узел с помощью метода <xref:System.Xml.XmlNamedNodeMap.RemoveNamedItem%2A>.  
  
 Чтобы удалить атрибуты, см. раздел [Удаление атрибутов из узла элемента в DOM](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md).  
  
## См. также  
 [Модель DOM для XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)