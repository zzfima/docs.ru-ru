---
title: "Копирование фрагментов документа | Microsoft Docs"
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
ms.assetid: cf424bbe-81b7-40d2-9978-9b727da94d80
caps.latest.revision: 3
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Копирование фрагментов документа
Можно создать узел **XmlDocumentFragment**, а затем добавлять к нему нижележащие узлы.  При вставке узла **XmlDocumentFragment** с помощью метода **InsertNode** узел **XmlDocumentFragment** не копируется, но его дочерние узлы вставляются в модель XML DOM.  
  
## См. также  
 [Модель DOM для XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)