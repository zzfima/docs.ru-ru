---
title: Коллекции узлов в NamedNodeMap и NodeList
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 025954b8-7aa8-47c5-a1c1-f81064fb4d65
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6b1ffe5eb791decfd7d36f7e8ecd29fa80e8e983
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="node-collections-in-namednodemaps-and-nodelists"></a><span data-ttu-id="8d4c8-102">Коллекции узлов в NamedNodeMap и NodeList</span><span class="sxs-lookup"><span data-stu-id="8d4c8-102">Node Collections in NamedNodeMaps and NodeLists</span></span>
<span data-ttu-id="8d4c8-103">Можно получить набор узлов и поместить его в упорядоченную или неупорядоченную коллекцию.</span><span class="sxs-lookup"><span data-stu-id="8d4c8-103">You can retrieve a set of nodes and put it in an ordered or unordered collection.</span></span> <span data-ttu-id="8d4c8-104">Если набор узлов помещается в неупорядоченную коллекцию, он получает имя NamedNodeMap согласно спецификации консорциума W3C. В этом типе коллекции данные можно получить по имени или по индексу.</span><span class="sxs-lookup"><span data-stu-id="8d4c8-104">When putting a set of nodes into an unordered collection, the set is called a NamedNodeMap by the World Wide Web Consortium (W3C); you can retrieve the data by name or index in this type of collection.</span></span> <span data-ttu-id="8d4c8-105">Набор узлов, помещенный в упорядоченную коллекцию, согласно спецификации W3C называется NodeList, и данные можно получить по индексу, начинающемуся с нуля.</span><span class="sxs-lookup"><span data-stu-id="8d4c8-105">Putting a set of nodes in an ordered collection is called a NodeList by the W3C, and the data can be retrieved by a zero-based index.</span></span> <span data-ttu-id="8d4c8-106">Коллекции NamedNodeMap и NodeList описаны в документах W3C.</span><span class="sxs-lookup"><span data-stu-id="8d4c8-106">NamedNodeMaps and NodeLists are described by the W3C.</span></span> <span data-ttu-id="8d4c8-107">Реализацией коллекции NamedNodeMap в платформе Microsoft .NET Framework является класс **XmlNamedNodeMap**, а коллекция NodeList реализована в классе **XmlNodeList**.</span><span class="sxs-lookup"><span data-stu-id="8d4c8-107">The implementations in the Microsoft .NET Framework for the NamedNodeMap is the **XmlNamedNodeMap**, and the NodeList is implemented by the **XmlNodeList**.</span></span>  
  
 <span data-ttu-id="8d4c8-108">Дополнительные сведения о неупорядоченных коллекциях см. в руководстве по [получению неупорядоченных узлов по имени или индексу](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md).</span><span class="sxs-lookup"><span data-stu-id="8d4c8-108">For information on the unordered collection, see [Unordered Node Retrieval by Name or Index](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md).</span></span> <span data-ttu-id="8d4c8-109">Дополнительные сведения об упорядоченных коллекциях см. в руководстве по [получению упорядоченных узлов по индексу](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).</span><span class="sxs-lookup"><span data-stu-id="8d4c8-109">For information on the ordered collection, see [Ordered Node Retrieval by Index](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d4c8-110">См. также</span><span class="sxs-lookup"><span data-stu-id="8d4c8-110">See Also</span></span>  
 [<span data-ttu-id="8d4c8-111">Модель объектов документов XML (DOM)</span><span class="sxs-lookup"><span data-stu-id="8d4c8-111">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
