---
title: "Коллекции узлов в NamedNodeMap и NodeList | Microsoft Docs"
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
ms.assetid: 025954b8-7aa8-47c5-a1c1-f81064fb4d65
caps.latest.revision: 3
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Коллекции узлов в NamedNodeMap и NodeList
Можно получить набор узлов и поместить его в упорядоченную или неупорядоченную коллекцию.  Если набор узлов помещается в неупорядоченную коллекцию, он получает имя NamedNodeMap согласно спецификации консорциума W3C. В этом типе коллекции данные можно получить по имени или по индексу.  Набор узлов, помещенный в упорядоченную коллекцию, согласно спецификации W3C называется NodeList, и данные можно получить по индексу, начинающемуся с нуля.  Коллекции NamedNodeMap и NodeList описаны в документах W3C.  Реализацией коллекции NamedNodeMap в платформе Microsoft .NET Framework является класс **XmlNamedNodeMap**, а коллекция NodeList реализована в классе **XmlNodeList**.  
  
 Сведения о неупорядоченных коллекциях см. в разделе [Получение неупорядоченных узлов по имени или индексу](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md).  Сведения об упорядоченных коллекциях см. в разделе [Получение упорядоченных узлов по индексу](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).  
  
## См. также  
 [Модель DOM для XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)