---
title: "Удаление содержимого узла в DOM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 615d81a7-f44f-416c-a9ab-bfe03f85e6e4
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 76be90829a414b091d3b311b96bf9bab9a2b56ed
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="removing-node-content-in-the-dom"></a><span data-ttu-id="44556-102">Удаление содержимого узла в DOM</span><span class="sxs-lookup"><span data-stu-id="44556-102">Removing Node Content in the DOM</span></span>
<span data-ttu-id="44556-103">Для типов узлов, наследующих от <xref:System.Xml.XmlCharacterData>, являющихся типами узлов <xref:System.Xml.XmlComment>,<xref:System.Xml.XmlText>,<xref:System.Xml.XmlCDataSection>,<xref:System.Xml.XmlWhitespace> и <xref:System.Xml.XmlSignificantWhitespace>, можно удалить символы с помощью метода <xref:System.Xml.XmlCharacterData.DeleteData%2A>, который удаляет диапазон символов из узла.</span><span class="sxs-lookup"><span data-stu-id="44556-103">For node types that inherit from <xref:System.Xml.XmlCharacterData>, which are the <xref:System.Xml.XmlComment>, <xref:System.Xml.XmlText>, <xref:System.Xml.XmlCDataSection>, <xref:System.Xml.XmlWhitespace>, and <xref:System.Xml.XmlSignificantWhitespace> node types, you can remove characters using the <xref:System.Xml.XmlCharacterData.DeleteData%2A> method, which removes a range of characters from the node.</span></span> <span data-ttu-id="44556-104">Если требуется полностью удалить содержимое, нужно удалить узел, содержащий содержимое.</span><span class="sxs-lookup"><span data-stu-id="44556-104">If you want to remove content completely, you remove the node that contains the content.</span></span> <span data-ttu-id="44556-105">Если требуется сохранить узел, содержимое которого неверно, нужно изменить содержимое.</span><span class="sxs-lookup"><span data-stu-id="44556-105">If you want to keep the node, but the content is incorrect, then modify the content.</span></span> <span data-ttu-id="44556-106">Сведения об изменении содержимого узла см. в разделе [изменение узлов, содержимого и значений в XML-документ](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="44556-106">For information on modifying the content of a node, see [Modifying Nodes, Content, and Values in an XML Document](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44556-107">См. также</span><span class="sxs-lookup"><span data-stu-id="44556-107">See Also</span></span>  
 [<span data-ttu-id="44556-108">Модель объектов XML-документов (DOM)</span><span class="sxs-lookup"><span data-stu-id="44556-108">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
