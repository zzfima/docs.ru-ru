---
title: Обработка незначительных и значительных пробелов при загрузке DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 1b141a0a-50d8-4ebd-83cd-a84449bb22b2
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f8e2279023029b5047cc7d9b4d0d97ac1f21e3f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="white-space-and-significant-white-space-handling-when-loading-the-dom"></a><span data-ttu-id="44f91-102">Обработка незначительных и значительных пробелов при загрузке DOM</span><span class="sxs-lookup"><span data-stu-id="44f91-102">White Space and Significant White Space Handling when Loading the DOM</span></span>
<span data-ttu-id="44f91-103">При загрузке документа можно установить параметр, требующий сохранять пробелы и создавать узлы **XmlWhitespace** в дереве документа.</span><span class="sxs-lookup"><span data-stu-id="44f91-103">When loading the document, you can set the option to preserve white space and create **XmlWhitespace** nodes in the document tree.</span></span> <span data-ttu-id="44f91-104">Чтобы создавать узлы пробелов, задайте для свойства **PreserveWhitespace** значение true.</span><span class="sxs-lookup"><span data-stu-id="44f91-104">To create white space nodes, set the **PreserveWhitespace** property to true.</span></span> <span data-ttu-id="44f91-105">Если свойство имеет значение **false**, используемое по умолчанию, то узлы пробелов не создаются.</span><span class="sxs-lookup"><span data-stu-id="44f91-105">If the property is set to **false**, which is the default, white space nodes are not created.</span></span> <span data-ttu-id="44f91-106">Узлы существенных пробелов сохраняются всегда, и узлы **XmlSignificantWhitespace** всегда создаются в памяти для представления этих данных, независимо от значения флага **PreserveWhitespace**.</span><span class="sxs-lookup"><span data-stu-id="44f91-106">Significant white spaces nodes are always preserved, and **XmlSignificantWhitespace** nodes are always created in memory to represent this data, regardless of the setting of the **PreserveWhitespace** flag.</span></span>  
  
 <span data-ttu-id="44f91-107">Если документ загружается из средства чтения, то свойства флага **PreserveWhitespace** для класса **XmlDocument** влияют на создание узлов **XmlWhitespace** только в том случае, когда свойство **WhitespaceHandling** для **XmlTextReader** не имеет значения **WhitespaceHandling.None**.</span><span class="sxs-lookup"><span data-stu-id="44f91-107">If the document is loaded from a reader, then setting of the **PreserveWhitespace** flag property on the **XmlDocument** class affects the creation of **XmlWhitespace** nodes only when the **WhitespaceHandling** property on the **XmlTextReader** is not set to **WhitespaceHandling.None**.</span></span> <span data-ttu-id="44f91-108">Значение свойства **WhitespaceHandling** в средстве чтения имеет приоритет над значением этого флага для **XmlDocument**.</span><span class="sxs-lookup"><span data-stu-id="44f91-108">It is the value of the **WhitespaceHandling** property on the reader that takes precedence over the setting of that flag on the **XmlDocument**.</span></span> <span data-ttu-id="44f91-109">Дополнительные сведения о флаге **XmlSignificantWhitespace** см. в статье <xref:System.Xml.XmlSignificantWhitespace>.</span><span class="sxs-lookup"><span data-stu-id="44f91-109">For more information on **XmlSignificantWhitespace**, see <xref:System.Xml.XmlSignificantWhitespace>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44f91-110">См. также</span><span class="sxs-lookup"><span data-stu-id="44f91-110">See Also</span></span>  
 [<span data-ttu-id="44f91-111">Модель объектов документов XML (DOM)</span><span class="sxs-lookup"><span data-stu-id="44f91-111">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
