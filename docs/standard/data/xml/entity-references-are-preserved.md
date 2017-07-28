---
title: "Сохраняемые ссылки на сущности | Microsoft Docs"
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
ms.assetid: 000a6cae-5972-40d6-bd6c-a9b7d9649b3c
caps.latest.revision: 3
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Сохраняемые ссылки на сущности
Если ссылки на сущности не разворачиваются, но сохраняются, модель XML DOM строит узел **XmlEntityReference**, когда обнаруживается ссылка на сущность.  
  
 Используя следующий XML\-код,  
  
```  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 Модель DOM строит узел **XmlEntityReference**, когда встречает ссылку `&publisher;` .  Узел **XmlEntityReference** содержит дочерние узлы, которые копируются из содержимого в декларации сущности.  В предыдущем примере кода присутствует текст в декларации, поэтому узел **XmlText** создается как дочерний узла ссылки на сущность.  
  
 ![Древовидная структура для сохраненных ссылок на сущности](../../../../docs/standard/data/xml/media/xmlentityref-notexpanded-nodes.gif "xmlentityref\_notexpanded\_nodes")  
Древовидная структура для сохраняемых ссылок на сущности  
  
 Дочерние узлы **XmlEntityReference** являются копиями всех дочерних узлов, созданных из узла **XmlEntity** в момент, когда была обнаружена декларация ссылки.  
  
> [!NOTE]
>  Узлы, копируемые из **XmlEntity**, не всегда остаются точными копиями после помещения под узел ссылки на сущность.  Могут существовать пространства имен, лежащие в области узла ссылки на сущность, которые оказывают влияние на конечную конфигурацию дочерних узлов.  
  
 Сущности общего вида, такие как `&abc;`, по умолчанию сохраняются, и для них всегда создаются узлы **XmlEntityReference**.  
  
## См. также  
 [Модель DOM для XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)