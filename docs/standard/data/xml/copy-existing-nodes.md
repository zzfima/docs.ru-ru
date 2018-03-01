---
title: "Копирование существующих узлов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2aa8f65c-cc62-4638-9c46-129dc15be786
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c026d9f825375d74d53d5cc46969ff0f713bab1c
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="copy-existing-nodes"></a><span data-ttu-id="0dd34-102">Копирование существующих узлов</span><span class="sxs-lookup"><span data-stu-id="0dd34-102">Copy Existing Nodes</span></span>
<span data-ttu-id="0dd34-103">Модель XML DOM включает множество методов и свойств, которые можно использовать для выбора узла, например **SelectSingleNode**, **ChildNodes[int i]**, **Attributes[int i]**.</span><span class="sxs-lookup"><span data-stu-id="0dd34-103">There are many methods and properties in the XML Document Object Model (DOM)you can use to select a node, such as **SelectSingleNode**, **ChildNodes[int i]**, **Attributes[int i]**.</span></span> <span data-ttu-id="0dd34-104">После выбора узла его можно вставить в дерево с помощью одного из методов вставки, допустимых для данного типа узла.</span><span class="sxs-lookup"><span data-stu-id="0dd34-104">Once the node is selected, you can insert it into the tree using one of the insert methods that work for that particular node type.</span></span> <span data-ttu-id="0dd34-105">Единственное ограничение при выполнении операции вставки узла в дерево состоит в том, что по ее завершении документ должен оставаться документом правильного формата.</span><span class="sxs-lookup"><span data-stu-id="0dd34-105">The only restriction to inserting a node into the tree is that the document must still be well-formed after the node is inserted.</span></span> <span data-ttu-id="0dd34-106">При вставке существующего узла в дерево DOM узел удаляется из своей исходной позиции и добавляется в целевую позицию.</span><span class="sxs-lookup"><span data-stu-id="0dd34-106">When an existing node is inserted into the DOM tree, it is removed from its original position and added to its target position.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dd34-107">См. также</span><span class="sxs-lookup"><span data-stu-id="0dd34-107">See Also</span></span>  
 [<span data-ttu-id="0dd34-108">Модель объектов документов XML (DOM)</span><span class="sxs-lookup"><span data-stu-id="0dd34-108">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
