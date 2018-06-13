---
title: Изменение свойств префикса пространства имен
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: d5c87cbe-4d69-429f-aad5-3103c2ca2770
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e3f41ba7281d67cc2ce848597926f5efebf4d489
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33568697"
---
# <a name="changing-namespace-prefix-properties"></a><span data-ttu-id="86d25-102">Изменение свойств префикса пространства имен</span><span class="sxs-lookup"><span data-stu-id="86d25-102">Changing Namespace Prefix Properties</span></span>
<span data-ttu-id="86d25-103">Класс **XmlNode** позволяет изменять префикс пространства имен, связанный с данным узлом.</span><span class="sxs-lookup"><span data-stu-id="86d25-103">The **XmlNode** class allows you to change the namespace prefix associated with a given node.</span></span> <span data-ttu-id="86d25-104">Изменение префикса элемента показано в следующем фрагменте кода.</span><span class="sxs-lookup"><span data-stu-id="86d25-104">For example, the following code shows the prefix of an element being changed.</span></span>  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
doc.LoadXml("<a:test xmlns:a='123' xmlns:b='456'/>")  
Dim e as XmlElement = doc.DocumentElement  
e.Prefix = "b"  
Console.WriteLine(doc.InnerXml)  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.LoadXml("<a:test xmlns:a='123' xmlns:b='456'/>");  
XmlElement e = doc.DocumentElement;         
e.Prefix = "b";  
Console.WriteLine(doc.InnerXml);  
```  
  
 <span data-ttu-id="86d25-105">**Вывод**</span><span class="sxs-lookup"><span data-stu-id="86d25-105">**Output**</span></span>  
  
```xml  
<b:test xmlns:a="123" xmlns:b="456" />  
```  
  
 <span data-ttu-id="86d25-106">Изменение префикса узла не меняет его пространства имен.</span><span class="sxs-lookup"><span data-stu-id="86d25-106">Changing the prefix of a node does not change its namespace.</span></span> <span data-ttu-id="86d25-107">Пространство имен можно задавать только при создании узла.</span><span class="sxs-lookup"><span data-stu-id="86d25-107">The namespace can only be set when the node is created.</span></span> <span data-ttu-id="86d25-108">При сохранении дерева новые атрибуты пространства имен можно сохранять с учетом присвоенного префикса.</span><span class="sxs-lookup"><span data-stu-id="86d25-108">When you persist the tree, new namespace attributes may be persisted out to satisfy the prefix you set.</span></span> <span data-ttu-id="86d25-109">Если нельзя создать новое пространство узлов, префикс изменяется, так что узел сохраняет свое локальное имя и пространство имен.</span><span class="sxs-lookup"><span data-stu-id="86d25-109">If the new namespace cannot be created, then the prefix is changed so the node preserves its local name and namespace.</span></span> <span data-ttu-id="86d25-110">В следующем примере показано добавление атрибута в пространство имен.</span><span class="sxs-lookup"><span data-stu-id="86d25-110">The following example shows a namespace attribute being added.</span></span>  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
doc.LoadXml("<test xmlns='123'/>")  
Dim e as XmlElement = doc.DocumentElement  
e.Prefix = "a"  
Console.WriteLine(doc.InnerXml)  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.LoadXml("<test xmlns='123'/>");  
XmlElement e = doc.DocumentElement;         
e.Prefix = "a";  
Console.WriteLine(doc.InnerXml);  
```  
  
 <span data-ttu-id="86d25-111">**Вывод**</span><span class="sxs-lookup"><span data-stu-id="86d25-111">**Output**</span></span>  
  
```xml  
<a:test xmlns="123" xmlns:a="123" />  
```  
  
 <span data-ttu-id="86d25-112">При сохранении дерева в виде строки с помощью метода **doc.InnerXml** был добавлен атрибут `xmlns:a='123'`, чтобы сохранить пространство имен элемента `test`.</span><span class="sxs-lookup"><span data-stu-id="86d25-112">When the tree was persisted to a string as a result of the call to **doc.InnerXml**, the `xmlns:a='123'` attribute was added to preserve the namespace of the `test` element.</span></span> <span data-ttu-id="86d25-113">Он имел значение `'123'` и сохранил `'123'`.</span><span class="sxs-lookup"><span data-stu-id="86d25-113">It was `'123'`, and it remained `'123'`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86d25-114">См. также</span><span class="sxs-lookup"><span data-stu-id="86d25-114">See Also</span></span>  
 [<span data-ttu-id="86d25-115">Модель объектов документов XML (DOM)</span><span class="sxs-lookup"><span data-stu-id="86d25-115">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
