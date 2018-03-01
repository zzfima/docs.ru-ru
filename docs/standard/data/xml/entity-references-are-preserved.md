---
title: "Сохраняемые ссылки на сущности"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 000a6cae-5972-40d6-bd6c-a9b7d9649b3c
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: f5a867d1301355f4c9a77654556229274f96d00c
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="entity-references-are-preserved"></a>Сохраняемые ссылки на сущности
Если ссылки на сущности не разворачиваются, а сохраняются, модель XML DOM строит узел **XmlEntityReference**, когда обнаруживает ссылку на сущность.  
  
 Используя следующий XML-код,  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 Модель DOM строит узел **XmlEntityReference**, когда встречает ссылку `&publisher;`. Узел **XmlEntityReference** содержит дочерние узлы, которые копируются из содержимого декларации сущности. В предыдущем примере присутствует текст в декларации сущности, поэтому узел **XmlText** создается как дочерний узел для узла ссылки на сущность.  
  
 ![Древовидная структура для сохраненных ссылок на сущности](../../../../docs/standard/data/xml/media/xmlentityref-notexpanded-nodes.gif "xmlentityref_notexpanded_nodes")  
Древовидная структура для сохраняемых ссылок на сущности  
  
 Дочерние узлы **XmlEntityReference** являются копиями всех дочерних узлов, созданных из узла **XmlEntity** в момент, когда была обнаружена декларация сущности.  
  
> [!NOTE]
>  Узлы, копируемые из **XmlEntity**, не всегда остаются точными копиями после помещения в узел ссылки на сущность. Могут существовать пространства имен, лежащие в области узла ссылки на сущность, которые оказывают влияние на конечную конфигурацию дочерних узлов.  
  
 По умолчанию сохраняются сущности общего вида, такие как `&abc;`, и всегда создаются узлы **XmlEntityReference**.  
  
## <a name="see-also"></a>См. также  
 [Модель объектов документов XML (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
