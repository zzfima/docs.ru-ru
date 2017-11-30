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
# <a name="dynamic-updates-to-nodelists-and-namednodemaps"></a><span data-ttu-id="26799-102">Динамические обновления объектов NodeList и NamedNodeMap</span><span class="sxs-lookup"><span data-stu-id="26799-102">Dynamic Updates to NodeLists and NamedNodeMaps</span></span>
<span data-ttu-id="26799-103">Поскольку **XmlNodeList** и **XmlNamedNodeMap** содержат набор узлов, но XML-документ загружается в память и изменяется, консорциума World Wide Web (W3C), указывающее, что эти объекты содержащие наборы узлов должны быть динамическими.</span><span class="sxs-lookup"><span data-stu-id="26799-103">Because the **XmlNodeList** and the **XmlNamedNodeMap** contain a set of nodes, yet the XML document is loaded into memory and is being modified, the World Wide Web Consortium (W3C) states that these objects that contain sets of nodes need to be dynamic.</span></span> <span data-ttu-id="26799-104">Это значит, что изменение базового документа должно вызывать изменение этих двух объектов.</span><span class="sxs-lookup"><span data-stu-id="26799-104">That is, if the underlying document changes, then the data in these two objects should change also.</span></span> <span data-ttu-id="26799-105">Таким образом Если у вас есть **XmlNodeList** , содержащий все дочерние элементы определенного элемента (например, элемента X), а затем добавьте дополнительный элемент Q, в документ из элемента X. **XmlNodeList** также должен быть новый элемент Q, добавленный в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="26799-105">Therefore, if you have an **XmlNodeList** that contains all the child elements of a particular element (for example, element X), then you add an additional element, element Q, to the document under element X. The **XmlNodeList** should also have that new element Q added to its collection.</span></span> <span data-ttu-id="26799-106">Правило работает и в обратном направлении:</span><span class="sxs-lookup"><span data-stu-id="26799-106">The same is true in reverse.</span></span> <span data-ttu-id="26799-107">Если узел добавляется в **XmlNodeList**, базовый документ также обновляется.</span><span class="sxs-lookup"><span data-stu-id="26799-107">If a node is added to the **XmlNodeList**, the underlying document is updated as well.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26799-108">См. также</span><span class="sxs-lookup"><span data-stu-id="26799-108">See Also</span></span>  
 [<span data-ttu-id="26799-109">Модель объектов XML-документов (DOM)</span><span class="sxs-lookup"><span data-stu-id="26799-109">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
