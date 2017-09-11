---
title: "Сравнение клонирования и Присоединение (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 357c5efa-7b73-4f14-aa67-6bebdba4e7ea
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 672bea849949ecfbf0aef3390556950356b5caff
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="cloning-vs-attaching-c"></a><span data-ttu-id="d4774-102">Сравнение клонирования и Присоединение (C#)</span><span class="sxs-lookup"><span data-stu-id="d4774-102">Cloning vs. Attaching (C#)</span></span>
<span data-ttu-id="d4774-103">При добавлении объекта <xref:System.Xml.Linq.XNode> (включая <xref:System.Xml.Linq.XElement>) или объекта <xref:System.Xml.Linq.XAttribute> в новое дерево, если новое содержимое не имеет родителя, объекты просто добавляются к XML-дереву.</span><span class="sxs-lookup"><span data-stu-id="d4774-103">When adding <xref:System.Xml.Linq.XNode> (including <xref:System.Xml.Linq.XElement>) or <xref:System.Xml.Linq.XAttribute> objects to a new tree, if the new content has no parent, the objects are simply attached to the XML tree.</span></span> <span data-ttu-id="d4774-104">Если у нового содержимого уже есть родитель и оно является частью другого XML-дерева, то новое содержимое клонируется.</span><span class="sxs-lookup"><span data-stu-id="d4774-104">If the new content already is parented, and is part of another XML tree, the new content is cloned.</span></span> <span data-ttu-id="d4774-105">Затем клонированное содержимое присоединяется к XML-дереву.</span><span class="sxs-lookup"><span data-stu-id="d4774-105">The newly cloned content is then attached to the XML tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4774-106">Пример</span><span class="sxs-lookup"><span data-stu-id="d4774-106">Example</span></span>  
 <span data-ttu-id="d4774-107">Следующий код демонстрирует поведение при добавлении к дереву элемента с родителем и при добавлении к дереву элемента без родителей.</span><span class="sxs-lookup"><span data-stu-id="d4774-107">The following code demonstrates the behavior when you add a parented element to a tree, and when you add an element with no parent to a tree.</span></span>  
  
```csharp  
// Create a tree with a child element.  
XElement xmlTree1 = new XElement("Root",  
    new XElement("Child1", 1)  
);  
  
// Create an element that is not parented.  
XElement child2 = new XElement("Child2", 2);  
  
// Create a tree and add Child1 and Child2 to it.  
XElement xmlTree2 = new XElement("Root",  
    xmlTree1.Element("Child1"),  
    child2  
);  
  
// Compare Child1 identity.  
Console.WriteLine("Child1 was {0}",  
    xmlTree1.Element("Child1") == xmlTree2.Element("Child1") ?  
    "attached" : "cloned");  
  
// Compare Child2 identity.  
Console.WriteLine("Child2 was {0}",  
    child2 == xmlTree2.Element("Child2") ?  
    "attached" : "cloned");  
```  
  
 <span data-ttu-id="d4774-108">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="d4774-108">This example produces the following output:</span></span>  
  
```  
Child1 was cloned  
Child2 was attached  
```  
  
## <a name="see-also"></a><span data-ttu-id="d4774-109">См. также</span><span class="sxs-lookup"><span data-stu-id="d4774-109">See Also</span></span>  
 [<span data-ttu-id="d4774-110">Создание деревьев XML (C#)</span><span class="sxs-lookup"><span data-stu-id="d4774-110">Creating XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md)

