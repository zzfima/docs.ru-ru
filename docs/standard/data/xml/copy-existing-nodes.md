---
title: Копирование существующих узлов
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 2aa8f65c-cc62-4638-9c46-129dc15be786
ms.openlocfilehash: fb9ccd7b16d00355ba87bb32f5447906feeecd94
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711068"
---
# <a name="copy-existing-nodes"></a><span data-ttu-id="6dc0f-102">Копирование существующих узлов</span><span class="sxs-lookup"><span data-stu-id="6dc0f-102">Copy Existing Nodes</span></span>
<span data-ttu-id="6dc0f-103">Модель XML DOM включает множество методов и свойств, которые можно использовать для выбора узла, например **SelectSingleNode**, **ChildNodes[int i]** , **Attributes[int i]** .</span><span class="sxs-lookup"><span data-stu-id="6dc0f-103">There are many methods and properties in the XML Document Object Model (DOM)you can use to select a node, such as **SelectSingleNode**, **ChildNodes[int i]**, **Attributes[int i]**.</span></span> <span data-ttu-id="6dc0f-104">После выбора узла его можно вставить в дерево с помощью одного из методов вставки, допустимых для данного типа узла.</span><span class="sxs-lookup"><span data-stu-id="6dc0f-104">Once the node is selected, you can insert it into the tree using one of the insert methods that work for that particular node type.</span></span> <span data-ttu-id="6dc0f-105">Единственное ограничение при выполнении операции вставки узла в дерево состоит в том, что по ее завершении документ должен оставаться документом правильного формата.</span><span class="sxs-lookup"><span data-stu-id="6dc0f-105">The only restriction to inserting a node into the tree is that the document must still be well-formed after the node is inserted.</span></span> <span data-ttu-id="6dc0f-106">При вставке существующего узла в дерево DOM узел удаляется из своей исходной позиции и добавляется в целевую позицию.</span><span class="sxs-lookup"><span data-stu-id="6dc0f-106">When an existing node is inserted into the DOM tree, it is removed from its original position and added to its target position.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dc0f-107">См. также:</span><span class="sxs-lookup"><span data-stu-id="6dc0f-107">See also</span></span>

- [<span data-ttu-id="6dc0f-108">Модель объектов документов XML (DOM)</span><span class="sxs-lookup"><span data-stu-id="6dc0f-108">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
