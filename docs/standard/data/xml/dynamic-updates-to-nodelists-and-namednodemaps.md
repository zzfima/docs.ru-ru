---
title: Динамические обновления объектов NodeList и NamedNodeMap
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 76c511fd-6704-4ca4-8078-860a68d898ad
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1de133d0208f1b86ad3240cdc00d8016af0a160c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33568970"
---
# <a name="dynamic-updates-to-nodelists-and-namednodemaps"></a>Динамические обновления объектов NodeList и NamedNodeMap
Так как объекты **XmlNodeList** и **XmlNamedNodeMap** содержат набор узлов, но XML-документ загружается в память и изменяется, консорциум W3C требует, чтобы такие объекты, содержащие наборы узлов, были динамическими. Это значит, что изменение базового документа должно вызывать изменение этих двух объектов. Таким образом, если у вас есть объект **XmlNodeList**, содержащий все дочерние элементы некоторого элемента (например, элемента X), и затем в документ добавляется дополнительный элемент Q, дочерний относительно элемента X, то в коллекцию объекта **XmlNodeList** также должен быть добавлен новый элемент Q. Правило работает и в обратном направлении: если узел добавляется в объект **XmlNodeList**, необходимо обновить базовый документ.  
  
## <a name="see-also"></a>См. также  
 [Модель объектов документов XML (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
