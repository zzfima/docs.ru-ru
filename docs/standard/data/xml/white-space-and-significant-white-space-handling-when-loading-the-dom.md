---
title: "Обработка незначительных и значительных пробелов при загрузке DOM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1b141a0a-50d8-4ebd-83cd-a84449bb22b2
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 82401a18132801f9aa5368832b96be3cb67a8642
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="white-space-and-significant-white-space-handling-when-loading-the-dom"></a><span data-ttu-id="64460-102">Обработка незначительных и значительных пробелов при загрузке DOM</span><span class="sxs-lookup"><span data-stu-id="64460-102">White Space and Significant White Space Handling when Loading the DOM</span></span>
<span data-ttu-id="64460-103">При загрузке документа можно задать параметр, чтобы сохранить пробел и создать **XmlWhitespace** узлов в дереве документа.</span><span class="sxs-lookup"><span data-stu-id="64460-103">When loading the document, you can set the option to preserve white space and create **XmlWhitespace** nodes in the document tree.</span></span> <span data-ttu-id="64460-104">Чтобы создать узлы пробелов, задайте **PreserveWhitespace** значение true.</span><span class="sxs-lookup"><span data-stu-id="64460-104">To create white space nodes, set the **PreserveWhitespace** property to true.</span></span> <span data-ttu-id="64460-105">Если свойство имеет значение **false**, используемого по умолчанию, узлы пробелов не создаются.</span><span class="sxs-lookup"><span data-stu-id="64460-105">If the property is set to **false**, which is the default, white space nodes are not created.</span></span> <span data-ttu-id="64460-106">Узлы значительные пробелы всегда сохраняются, и **XmlSignificantWhitespace** всегда создаются в памяти для представления этих данных, независимо от значения **PreserveWhitespace** флаг.</span><span class="sxs-lookup"><span data-stu-id="64460-106">Significant white spaces nodes are always preserved, and **XmlSignificantWhitespace** nodes are always created in memory to represent this data, regardless of the setting of the **PreserveWhitespace** flag.</span></span>  
  
 <span data-ttu-id="64460-107">Если документ загружается из средства чтения, задав для **PreserveWhitespace** флаг свойство **XmlDocument** класса влияет на создание **XmlWhitespace** узлов только если **WhitespaceHandling** свойство **XmlTextReader** равно **WhitespaceHandling.None**.</span><span class="sxs-lookup"><span data-stu-id="64460-107">If the document is loaded from a reader, then setting of the **PreserveWhitespace** flag property on the **XmlDocument** class affects the creation of **XmlWhitespace** nodes only when the **WhitespaceHandling** property on the **XmlTextReader** is not set to **WhitespaceHandling.None**.</span></span> <span data-ttu-id="64460-108">Это значение **WhitespaceHandling** свойство для чтения, которое имеет приоритет над значением этого флага в **XmlDocument**.</span><span class="sxs-lookup"><span data-stu-id="64460-108">It is the value of the **WhitespaceHandling** property on the reader that takes precedence over the setting of that flag on the **XmlDocument**.</span></span> <span data-ttu-id="64460-109">Дополнительные сведения о **XmlSignificantWhitespace**, в разделе <xref:System.Xml.XmlSignificantWhitespace>.</span><span class="sxs-lookup"><span data-stu-id="64460-109">For more information on **XmlSignificantWhitespace**, see <xref:System.Xml.XmlSignificantWhitespace>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64460-110">См. также</span><span class="sxs-lookup"><span data-stu-id="64460-110">See Also</span></span>  
 [<span data-ttu-id="64460-111">Модель объектов XML-документов (DOM)</span><span class="sxs-lookup"><span data-stu-id="64460-111">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
