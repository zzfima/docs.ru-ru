---
title: "Сохраняемые ссылки на сущности"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 000a6cae-5972-40d6-bd6c-a9b7d9649b3c
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 770c714e8f5942ea733c417ae9b06f69e4acf1a5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="entity-references-are-preserved"></a><span data-ttu-id="ce84e-102">Сохраняемые ссылки на сущности</span><span class="sxs-lookup"><span data-stu-id="ce84e-102">Entity References are Preserved</span></span>
<span data-ttu-id="ce84e-103">Если ссылки на сущности не разворачиваются, но сохраняются, модель объектов документов (DOM) XML-выполняется построение **XmlEntityReference** узла, когда он встречает ссылку на сущность.</span><span class="sxs-lookup"><span data-stu-id="ce84e-103">When the entity reference is not expanded, but preserved, the XML Document Object Model (DOM) builds an **XmlEntityReference** node when it encounters an entity reference.</span></span>  
  
 <span data-ttu-id="ce84e-104">Используя следующий XML-код,</span><span class="sxs-lookup"><span data-stu-id="ce84e-104">Using the following XML,</span></span>  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 <span data-ttu-id="ce84e-105">модель DOM строит **XmlEntityReference** узла, когда он встречает `&publisher;` ссылки.</span><span class="sxs-lookup"><span data-stu-id="ce84e-105">the DOM builds an **XmlEntityReference** node when it encounters the `&publisher;` reference.</span></span> <span data-ttu-id="ce84e-106">**XmlEntityReference** содержит дочерние узлы, скопированные из содержимого в декларации сущности.</span><span class="sxs-lookup"><span data-stu-id="ce84e-106">The **XmlEntityReference** contains child nodes copied from the content in the entity declaration.</span></span> <span data-ttu-id="ce84e-107">В предыдущем примере кода присутствует текст в декларации, поэтому **XmlText** узел создается как дочерний узел узла ссылки на сущность.</span><span class="sxs-lookup"><span data-stu-id="ce84e-107">The preceding code example contains text in the entity declaration, so an **XmlText** node is created as the child node of the entity reference node.</span></span>  
  
 <span data-ttu-id="ce84e-108">![Древовидная структура для сохраненных ссылок на сущности](../../../../docs/standard/data/xml/media/xmlentityref-notexpanded-nodes.gif "xmlentityref_notexpanded_nodes")</span><span class="sxs-lookup"><span data-stu-id="ce84e-108">![Tree structure for preserved entity references](../../../../docs/standard/data/xml/media/xmlentityref-notexpanded-nodes.gif "xmlentityref_notexpanded_nodes")</span></span>  
<span data-ttu-id="ce84e-109">Древовидная структура для сохраняемых ссылок на сущности</span><span class="sxs-lookup"><span data-stu-id="ce84e-109">Tree structure for entity references that are preserved</span></span>  
  
 <span data-ttu-id="ce84e-110">Дочерние узлы **XmlEntityReference** являются копиями всех дочерних узлов, созданных из **XmlEntity** узла, когда была обнаружена декларация сущности.</span><span class="sxs-lookup"><span data-stu-id="ce84e-110">The child nodes of the **XmlEntityReference** are copies of all the child nodes created from the **XmlEntity** node when the entity declaration was encountered.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ce84e-111">Узлы, скопированные из **XmlEntity** не всегда являются точными копиями после помещения под узел ссылки на сущность.</span><span class="sxs-lookup"><span data-stu-id="ce84e-111">The nodes copied from the **XmlEntity** are not always exact copies once placed under the entity reference node.</span></span> <span data-ttu-id="ce84e-112">Могут существовать пространства имен, лежащие в области узла ссылки на сущность, которые оказывают влияние на конечную конфигурацию дочерних узлов.</span><span class="sxs-lookup"><span data-stu-id="ce84e-112">There can be namespaces that are in scope at the entity reference node, and that affects the final configuration of the child nodes.</span></span>  
  
 <span data-ttu-id="ce84e-113">По умолчанию общие сущности, такие как `&abc;` сохраняются и **XmlEntityReference** всегда создаются узлы.</span><span class="sxs-lookup"><span data-stu-id="ce84e-113">By default, general entities like `&abc;` are preserved and **XmlEntityReference** nodes always created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce84e-114">См. также</span><span class="sxs-lookup"><span data-stu-id="ce84e-114">See Also</span></span>  
 [<span data-ttu-id="ce84e-115">Модель объектов XML-документов (DOM)</span><span class="sxs-lookup"><span data-stu-id="ce84e-115">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
