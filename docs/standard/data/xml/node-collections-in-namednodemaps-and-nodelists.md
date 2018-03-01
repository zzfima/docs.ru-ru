---
title: "Коллекции узлов в NamedNodeMap и NodeList"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 025954b8-7aa8-47c5-a1c1-f81064fb4d65
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ff327c1a450e9ce712d496bdca2cd2ebbff6adda
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="node-collections-in-namednodemaps-and-nodelists"></a>Коллекции узлов в NamedNodeMap и NodeList
Можно получить набор узлов и поместить его в упорядоченную или неупорядоченную коллекцию. Если набор узлов помещается в неупорядоченную коллекцию, он получает имя NamedNodeMap согласно спецификации консорциума W3C. В этом типе коллекции данные можно получить по имени или по индексу. Набор узлов, помещенный в упорядоченную коллекцию, согласно спецификации W3C называется NodeList, и данные можно получить по индексу, начинающемуся с нуля. Коллекции NamedNodeMap и NodeList описаны в документах W3C. Реализацией коллекции NamedNodeMap в платформе Microsoft .NET Framework является класс **XmlNamedNodeMap**, а коллекция NodeList реализована в классе **XmlNodeList**.  
  
 Дополнительные сведения о неупорядоченных коллекциях см. в руководстве по [получению неупорядоченных узлов по имени или индексу](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md). Дополнительные сведения об упорядоченных коллекциях см. в руководстве по [получению упорядоченных узлов по индексу](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).  
  
## <a name="see-also"></a>См. также  
 [Модель объектов документов XML (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
