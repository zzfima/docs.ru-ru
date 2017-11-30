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
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7eeed46782eb6c55af23559035fb8b6bcb14301f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="node-collections-in-namednodemaps-and-nodelists"></a><span data-ttu-id="40045-102">Коллекции узлов в NamedNodeMap и NodeList</span><span class="sxs-lookup"><span data-stu-id="40045-102">Node Collections in NamedNodeMaps and NodeLists</span></span>
<span data-ttu-id="40045-103">Можно получить набор узлов и поместить его в упорядоченную или неупорядоченную коллекцию.</span><span class="sxs-lookup"><span data-stu-id="40045-103">You can retrieve a set of nodes and put it in an ordered or unordered collection.</span></span> <span data-ttu-id="40045-104">Если набор узлов помещается в неупорядоченную коллекцию, он получает имя NamedNodeMap согласно спецификации консорциума W3C. В этом типе коллекции данные можно получить по имени или по индексу.</span><span class="sxs-lookup"><span data-stu-id="40045-104">When putting a set of nodes into an unordered collection, the set is called a NamedNodeMap by the World Wide Web Consortium (W3C); you can retrieve the data by name or index in this type of collection.</span></span> <span data-ttu-id="40045-105">Набор узлов, помещенный в упорядоченную коллекцию, согласно спецификации W3C называется NodeList, и данные можно получить по индексу, начинающемуся с нуля.</span><span class="sxs-lookup"><span data-stu-id="40045-105">Putting a set of nodes in an ordered collection is called a NodeList by the W3C, and the data can be retrieved by a zero-based index.</span></span> <span data-ttu-id="40045-106">Коллекции NamedNodeMap и NodeList описаны в документах W3C.</span><span class="sxs-lookup"><span data-stu-id="40045-106">NamedNodeMaps and NodeLists are described by the W3C.</span></span> <span data-ttu-id="40045-107">Реализации NamedNodeMap в платформе Microsoft .NET Framework — **XmlNamedNodeMap**, и реализуется класс NodeList **XmlNodeList**.</span><span class="sxs-lookup"><span data-stu-id="40045-107">The implementations in the Microsoft .NET Framework for the NamedNodeMap is the **XmlNamedNodeMap**, and the NodeList is implemented by the **XmlNodeList**.</span></span>  
  
 <span data-ttu-id="40045-108">Сведения о неупорядоченных коллекциях см. в разделе [получение неупорядоченных узлов по имени или индексу](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md).</span><span class="sxs-lookup"><span data-stu-id="40045-108">For information on the unordered collection, see [Unordered Node Retrieval by Name or Index](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md).</span></span> <span data-ttu-id="40045-109">Сведения об упорядоченных коллекциях см. в разделе [получение упорядоченных узлов по индексу](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).</span><span class="sxs-lookup"><span data-stu-id="40045-109">For information on the ordered collection, see [Ordered Node Retrieval by Index](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40045-110">См. также</span><span class="sxs-lookup"><span data-stu-id="40045-110">See Also</span></span>  
 [<span data-ttu-id="40045-111">Модель объектов XML-документов (DOM)</span><span class="sxs-lookup"><span data-stu-id="40045-111">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
