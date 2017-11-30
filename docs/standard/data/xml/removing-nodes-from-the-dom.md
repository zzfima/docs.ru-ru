---
title: "Удаление узлов из DOM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0a98e0ca-0555-45c1-ab69-0d8d20ca1abd
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0885d53e737153448fabfd394d49bfdc793e0599
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="removing-nodes-from-the-dom"></a><span data-ttu-id="98fe3-102">Удаление узлов из DOM</span><span class="sxs-lookup"><span data-stu-id="98fe3-102">Removing Nodes from the DOM</span></span>
<span data-ttu-id="98fe3-103">Для удаления узла из модели DOM XML-документа используется метод <xref:System.Xml.XmlNode.RemoveChild%2A>, с помощью которого удаляется конкретный узел.</span><span class="sxs-lookup"><span data-stu-id="98fe3-103">To remove a node from the XML Document Object Model (DOM), use the <xref:System.Xml.XmlNode.RemoveChild%2A> method to remove a specific node.</span></span> <span data-ttu-id="98fe3-104">При удалении узла метод удаляет поддерево, принадлежащее удаляемому узлу т.е. если это не конечный узел.</span><span class="sxs-lookup"><span data-stu-id="98fe3-104">When you remove a node, the method removes the subtree belonging to the node being removed; that is, if it is not a leaf node.</span></span>  
  
 <span data-ttu-id="98fe3-105">Для удаления нескольких узлов из DOM используется метод <xref:System.Xml.XmlNode.RemoveAll%2A>, удаляющий все дочерние узлы и атрибуты (если применимо) текущего узла.</span><span class="sxs-lookup"><span data-stu-id="98fe3-105">To remove multiple nodes from the DOM, use the <xref:System.Xml.XmlNode.RemoveAll%2A> method to remove all the children and attributes, if applicable, of the current node.</span></span>  
  
 <span data-ttu-id="98fe3-106">При работе с классом <xref:System.Xml.XmlNamedNodeMap> можно удалить узел с помощью метода <xref:System.Xml.XmlNamedNodeMap.RemoveNamedItem%2A>.</span><span class="sxs-lookup"><span data-stu-id="98fe3-106">If you are working with an <xref:System.Xml.XmlNamedNodeMap>, you can remove a node using the <xref:System.Xml.XmlNamedNodeMap.RemoveNamedItem%2A> method.</span></span>  
  
 <span data-ttu-id="98fe3-107">Удаление атрибутов, в разделе [удаление атрибутов из узла элемента в DOM](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="98fe3-107">To remove attributes, see [Removing Attributes from an Element Node in the DOM](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98fe3-108">См. также</span><span class="sxs-lookup"><span data-stu-id="98fe3-108">See Also</span></span>  
 [<span data-ttu-id="98fe3-109">Модель объектов XML-документов (DOM)</span><span class="sxs-lookup"><span data-stu-id="98fe3-109">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
