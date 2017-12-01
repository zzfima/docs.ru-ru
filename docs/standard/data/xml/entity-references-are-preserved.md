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
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 770c714e8f5942ea733c417ae9b06f69e4acf1a5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="entity-references-are-preserved"></a>Сохраняемые ссылки на сущности
Если ссылки на сущности не разворачиваются, но сохраняются, модель объектов документов (DOM) XML-выполняется построение **XmlEntityReference** узла, когда он встречает ссылку на сущность.  
  
 Используя следующий XML-код,  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 модель DOM строит **XmlEntityReference** узла, когда он встречает `&publisher;` ссылки. **XmlEntityReference** содержит дочерние узлы, скопированные из содержимого в декларации сущности. В предыдущем примере кода присутствует текст в декларации, поэтому **XmlText** узел создается как дочерний узел узла ссылки на сущность.  
  
 ![Древовидная структура для сохраненных ссылок на сущности](../../../../docs/standard/data/xml/media/xmlentityref-notexpanded-nodes.gif "xmlentityref_notexpanded_nodes")  
Древовидная структура для сохраняемых ссылок на сущности  
  
 Дочерние узлы **XmlEntityReference** являются копиями всех дочерних узлов, созданных из **XmlEntity** узла, когда была обнаружена декларация сущности.  
  
> [!NOTE]
>  Узлы, скопированные из **XmlEntity** не всегда являются точными копиями после помещения под узел ссылки на сущность. Могут существовать пространства имен, лежащие в области узла ссылки на сущность, которые оказывают влияние на конечную конфигурацию дочерних узлов.  
  
 По умолчанию общие сущности, такие как `&abc;` сохраняются и **XmlEntityReference** всегда создаются узлы.  
  
## <a name="see-also"></a>См. также  
 [Модель объектов XML-документов (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
