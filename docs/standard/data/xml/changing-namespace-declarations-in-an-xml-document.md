---
title: Изменение деклараций пространств имен в XML-документе
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: a2758f40-e497-4964-8d8d-1bb68af14dcd
ms.openlocfilehash: b8aa670764deb8e77cfb67fd16dbcf8b1cc9b4c0
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711133"
---
# <a name="changing-namespace-declarations-in-an-xml-document"></a><span data-ttu-id="11c1c-102">Изменение деклараций пространств имен в XML-документе</span><span class="sxs-lookup"><span data-stu-id="11c1c-102">Changing Namespace Declarations in an XML Document</span></span>
<span data-ttu-id="11c1c-103">Класс **XmlDocument** представляет декларацию пространств имен и атрибуты **xmlns** как часть модели DOM.</span><span class="sxs-lookup"><span data-stu-id="11c1c-103">The **XmlDocument** exposes namespace declarations and **xmlns** attributes as part of the document object model.</span></span> <span data-ttu-id="11c1c-104">Они хранятся в объекте **XmlDocument**, поэтому при сохранении документа он может сохранить расположение этих атрибутов.</span><span class="sxs-lookup"><span data-stu-id="11c1c-104">These are stored in the **XmlDocument**, so when you save the document, it can preserve the location of those attributes.</span></span> <span data-ttu-id="11c1c-105">Изменение этих атрибутов не влияет на свойства **Name**, **NamespaceURI** и **Prefix** других узлов, уже находящихся в дереве.</span><span class="sxs-lookup"><span data-stu-id="11c1c-105">Changing these attributes has no affect on the **Name**, **NamespaceURI**, and **Prefix** properties of other nodes already in the tree.</span></span> <span data-ttu-id="11c1c-106">Например, если загрузить следующий документ, то элемент `test` имеет значение **NamespaceURI** `123.`</span><span class="sxs-lookup"><span data-stu-id="11c1c-106">For example, if you load the following document, then the `test` element has **NamespaceURI** `123.`</span></span>  
  
```xml  
<test xmlns="123"/>  
```  
  
 <span data-ttu-id="11c1c-107">Если удалить атрибут `xmlns` следующим образом, то элемент `test` все равно будет содержать свойство **NamespaceURI**, которое имеет значение `123`.</span><span class="sxs-lookup"><span data-stu-id="11c1c-107">If you remove the `xmlns` attribute as follows, then the `test` element still has the **NamespaceURI** of `123`.</span></span>  
  
```vb  
doc.documentElement.RemoveAttribute("xmlns")  
```  
  
```csharp  
doc.documentElement.RemoveAttribute("xmlns");  
```  
  
 <span data-ttu-id="11c1c-108">Аналогичным образом, если добавить другой атрибут `xmlns` к элементу `doc`, как показано ниже, элемент `test` все еще имеет `123`**NamespaceURI** .</span><span class="sxs-lookup"><span data-stu-id="11c1c-108">Likewise, if you add a different `xmlns` attribute to the `doc` element as follows, then the `test` element still has **NamespaceURI** `123`.</span></span>  
  
```vb  
doc.documentElement.SetAttribute("xmlns","456")
```  
  
```csharp  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
 <span data-ttu-id="11c1c-109">Поэтому изменение атрибутов `xmlns` не оказывает никакого влияния, пока объект **XmlDocument** не будет сохранен и перезагружен.</span><span class="sxs-lookup"><span data-stu-id="11c1c-109">Therefore, changing `xmlns` attributes will have no affect until you save and reload the **XmlDocument** object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11c1c-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="11c1c-110">See also</span></span>

- [<span data-ttu-id="11c1c-111">Модель объектов документов XML (DOM)</span><span class="sxs-lookup"><span data-stu-id="11c1c-111">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
