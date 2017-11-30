---
title: "Изменение деклараций пространств имен в XML-документе"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: a2758f40-e497-4964-8d8d-1bb68af14dcd
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 627882efcbc41310ee177cba984e4add5b07bd15
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="changing-namespace-declarations-in-an-xml-document"></a><span data-ttu-id="78018-102">Изменение деклараций пространств имен в XML-документе</span><span class="sxs-lookup"><span data-stu-id="78018-102">Changing Namespace Declarations in an XML Document</span></span>
<span data-ttu-id="78018-103">**XmlDocument** представляет декларацию пространств имен и **xmlns** атрибутов как часть объектной модели документа.</span><span class="sxs-lookup"><span data-stu-id="78018-103">The **XmlDocument** exposes namespace declarations and **xmlns** attributes as part of the document object model.</span></span> <span data-ttu-id="78018-104">Эти значения хранятся в **XmlDocument**, поэтому при сохранении документа он может сохранить расположение этих атрибутов.</span><span class="sxs-lookup"><span data-stu-id="78018-104">These are stored in the **XmlDocument**, so when you save the document, it can preserve the location of those attributes.</span></span> <span data-ttu-id="78018-105">Изменение этих атрибутов не оказывает никакого влияния **имя**, **NamespaceURI**, и **префикса** других узлов, уже находящихся в дереве.</span><span class="sxs-lookup"><span data-stu-id="78018-105">Changing these attributes has no affect on the **Name**, **NamespaceURI**, and **Prefix** properties of other nodes already in the tree.</span></span> <span data-ttu-id="78018-106">Например, если загрузить документ а затем `test` элемент имеет **NamespaceURI**`123.`</span><span class="sxs-lookup"><span data-stu-id="78018-106">For example, if you load the following document, then the `test` element has **NamespaceURI** `123.`</span></span>  
  
```xml  
<test xmlns="123"/>  
```  
  
 <span data-ttu-id="78018-107">При удалении `xmlns` атрибута следующим образом, то `test` по-прежнему содержит элемент **NamespaceURI** из `123`.</span><span class="sxs-lookup"><span data-stu-id="78018-107">If you remove the `xmlns` attribute as follows, then the `test` element still has the **NamespaceURI** of `123`.</span></span>  
  
```vb  
doc.documentElement.RemoveAttribute("xmlns")  
```  
  
```csharp  
doc.documentElement.RemoveAttribute("xmlns");  
```  
  
 <span data-ttu-id="78018-108">Аналогичным образом Если добавить другой `xmlns` атрибут `doc` элемента, как показано ниже, то `test` по-прежнему содержит элемент **NamespaceURI** `123`.</span><span class="sxs-lookup"><span data-stu-id="78018-108">Likewise, if you add a different `xmlns` attribute to the `doc` element as follows, then the `test` element still has **NamespaceURI** `123`.</span></span>  
  
```vb  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
```csharp  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
 <span data-ttu-id="78018-109">Поэтому изменение `xmlns` атрибуты не действуют, пока не будет сохранен и перезагружен **XmlDocument** объекта.</span><span class="sxs-lookup"><span data-stu-id="78018-109">Therefore, changing `xmlns` attributes will have no affect until you save and reload the **XmlDocument** object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78018-110">См. также</span><span class="sxs-lookup"><span data-stu-id="78018-110">See Also</span></span>  
 [<span data-ttu-id="78018-111">Модель объектов XML-документов (DOM)</span><span class="sxs-lookup"><span data-stu-id="78018-111">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
