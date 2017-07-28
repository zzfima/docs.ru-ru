---
title: "Обработка незначительных и значительных пробелов при загрузке DOM | Microsoft Docs"
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
ms.assetid: 1b141a0a-50d8-4ebd-83cd-a84449bb22b2
caps.latest.revision: 4
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Обработка незначительных и значительных пробелов при загрузке DOM
При загрузке документа можно назначить параметр, сохраняющий пробел и создающий узлы **XmlWhitespace** в дереве документа.  Чтобы создать узлы пробелов, задайте для свойства **PreserveWhitespace** значение true.  Если свойство имеет значение по умолчанию **false**, то узлы пробелов не создаются.  Узлы существенных пробелов всегда сохраняются, а узлы **XmlSignificantWhitespace** всегда создаются в памяти для представления этих данных, независимо от флага **PreserveWhitespace**.  
  
 Если документ загружается в средство чтения, то создание узлов **XmlWhitespace** будет зависеть от свойства флага **PreserveWhitespace** для класса **XmlDocument** \(кроме случая, когда свойство **WhitespaceHandling** для **XmlTextReader** имеет значение **WhitespaceHandling.None**\).  Значение свойства **WhitespaceHandling** для средства чтения имеет приоритет перед значением этого флага для **XmlDocument**.  Дополнительные сведения о **XmlSignificantWhitespace** см. в разделе [XmlSignificantWhitespace Class](frlrfSystemXmlXmlSignificantWhitespaceClassTopic).  
  
## См. также  
 [Модель DOM для XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)