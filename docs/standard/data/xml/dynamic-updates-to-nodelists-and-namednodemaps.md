---
title: "Динамические обновления объектов NodeList и NamedNodeMap | Microsoft Docs"
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
ms.assetid: 76c511fd-6704-4ca4-8078-860a68d898ad
caps.latest.revision: 3
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Динамические обновления объектов NodeList и NamedNodeMap
Поскольку объекты **XmlNodeList** и **XmlNamedNodeMap** содержат набор узлов, но XML\-документ загружается в память и изменяется, консорциум W3C требует, чтобы такие объекты, содержащие наборы узлов, были динамическими.  Это значит, что изменение базового документа должно вызывать изменение этих двух объектов.  Таким образом, если имеется объект **XmlNodeList**, содержащий все дочерние элементы некоторого элемента \(например, элемента X\), то в документ добавляется дополнительный элемент Q, дочерний по отношению к элементу X.  В коллекцию объекта **XmlNodeList** также должен быть добавлен новый элемент Q.  Правило работает и в обратном направлении:  если узел добавляется в объект **XmlNodeList**, необходимо обновить базовый документ.  
  
## См. также  
 [Модель DOM для XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)