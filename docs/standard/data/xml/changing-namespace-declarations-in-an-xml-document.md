---
title: Изменение деклараций пространств имен в XML-документе
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: a2758f40-e497-4964-8d8d-1bb68af14dcd
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5457eab1f34eb3e7424d508509f5dd6a42ffb51f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976939"
---
# <a name="changing-namespace-declarations-in-an-xml-document"></a><span data-ttu-id="bbd3d-102">Изменение деклараций пространств имен в XML-документе</span><span class="sxs-lookup"><span data-stu-id="bbd3d-102">Changing Namespace Declarations in an XML Document</span></span>
<span data-ttu-id="bbd3d-103">Класс **XmlDocument** представляет декларацию пространств имен и атрибуты **xmlns** как часть модели DOM.</span><span class="sxs-lookup"><span data-stu-id="bbd3d-103">The **XmlDocument** exposes namespace declarations and **xmlns** attributes as part of the document object model.</span></span> <span data-ttu-id="bbd3d-104">Они хранятся в объекте **XmlDocument**, поэтому при сохранении документа он может сохранить расположение этих атрибутов.</span><span class="sxs-lookup"><span data-stu-id="bbd3d-104">These are stored in the **XmlDocument**, so when you save the document, it can preserve the location of those attributes.</span></span> <span data-ttu-id="bbd3d-105">Изменение этих атрибутов не влияет на свойства **Name**, **NamespaceURI** и **Prefix** других узлов, уже находящихся в дереве.</span><span class="sxs-lookup"><span data-stu-id="bbd3d-105">Changing these attributes has no affect on the **Name**, **NamespaceURI**, and **Prefix** properties of other nodes already in the tree.</span></span> <span data-ttu-id="bbd3d-106">Например, при загрузке следующего документа свойство `test`NamespaceURI**элемента** будет иметь значение `123.`</span><span class="sxs-lookup"><span data-stu-id="bbd3d-106">For example, if you load the following document, then the `test` element has **NamespaceURI** `123.`</span></span>  
  
```xml  
<test xmlns="123"/>  
```  
  
 <span data-ttu-id="bbd3d-107">Если удалить атрибут `xmlns` следующим образом, то элемент `test` все равно будет содержать свойство **NamespaceURI**, которое имеет значение `123`.</span><span class="sxs-lookup"><span data-stu-id="bbd3d-107">If you remove the `xmlns` attribute as follows, then the `test` element still has the **NamespaceURI** of `123`.</span></span>  
  
```vb  
doc.documentElement.RemoveAttribute("xmlns")  
```  
  
```csharp  
doc.documentElement.RemoveAttribute("xmlns");  
```  
  
 <span data-ttu-id="bbd3d-108">Точно так же, если добавить другой атрибут `xmlns` в элемент `doc` следующим образом, элемент `test` все равно будет содержать свойство **NamespaceURI**, которое имеет значение `123`.</span><span class="sxs-lookup"><span data-stu-id="bbd3d-108">Likewise, if you add a different `xmlns` attribute to the `doc` element as follows, then the `test` element still has **NamespaceURI** `123`.</span></span>  
  
```vb  
doc.documentElement.SetAttribute("xmlns","456")
```  
  
```csharp  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
 <span data-ttu-id="bbd3d-109">Поэтому изменение атрибутов `xmlns` не оказывает никакого влияния, пока объект **XmlDocument** не будет сохранен и перезагружен.</span><span class="sxs-lookup"><span data-stu-id="bbd3d-109">Therefore, changing `xmlns` attributes will have no affect until you save and reload the **XmlDocument** object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbd3d-110">См. также</span><span class="sxs-lookup"><span data-stu-id="bbd3d-110">See also</span></span>

- [<span data-ttu-id="bbd3d-111">Модель объектов документов XML (DOM)</span><span class="sxs-lookup"><span data-stu-id="bbd3d-111">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
