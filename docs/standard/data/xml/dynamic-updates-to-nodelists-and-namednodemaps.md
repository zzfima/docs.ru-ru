---
title: "Динамические обновления объектов NodeList и NamedNodeMap"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 76c511fd-6704-4ca4-8078-860a68d898ad
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 459d746ff278ac4affa0318c1fad0aeb6a73e560
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="dynamic-updates-to-nodelists-and-namednodemaps"></a>Динамические обновления объектов NodeList и NamedNodeMap
Поскольку **XmlNodeList** и **XmlNamedNodeMap** содержат набор узлов, но XML-документ загружается в память и изменяется, консорциума World Wide Web (W3C), указывающее, что эти объекты содержащие наборы узлов должны быть динамическими. Это значит, что изменение базового документа должно вызывать изменение этих двух объектов. Таким образом Если у вас есть **XmlNodeList** , содержащий все дочерние элементы определенного элемента (например, элемента X), а затем добавьте дополнительный элемент Q, в документ из элемента X. **XmlNodeList** также должен быть новый элемент Q, добавленный в коллекцию. Правило работает и в обратном направлении: Если узел добавляется в **XmlNodeList**, базовый документ также обновляется.  
  
## <a name="see-also"></a>См. также  
 [Модель объектов XML-документов (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
