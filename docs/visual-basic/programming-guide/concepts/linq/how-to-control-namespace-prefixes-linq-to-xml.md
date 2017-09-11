---
title: "Практическое руководство: управление префиксами пространств имен (Visual Basic) (LINQ to XML) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 2fcf28a5-31b6-409d-84ea-27c22f71fc9f
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 87db9e5384bee835ca4fde141765eabf9a7cfedb
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-control-namespace-prefixes-visual-basic-linq-to-xml"></a><span data-ttu-id="cb12b-102">Практическое руководство. Управление префиксами пространств имен (Visual Basic) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="cb12b-102">How to: Control Namespace Prefixes (Visual Basic) (LINQ to XML)</span></span>
<span data-ttu-id="cb12b-103">В этом разделе рассматривается управление префиксами пространств имен.</span><span class="sxs-lookup"><span data-stu-id="cb12b-103">This topic describes how you can control namespace prefixes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb12b-104">Пример</span><span class="sxs-lookup"><span data-stu-id="cb12b-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="cb12b-105">Описание</span><span class="sxs-lookup"><span data-stu-id="cb12b-105">Description</span></span>  
 <span data-ttu-id="cb12b-106">В этом примере объявляются два пространства имен.</span><span class="sxs-lookup"><span data-stu-id="cb12b-106">This example declares two namespaces.</span></span> <span data-ttu-id="cb12b-107">Указывает, что `http://www.adventure-works.com` пространства имен имеет префикс `aw`и что `www.fourthcoffee.com` пространства имен имеет префикс `fc`.</span><span class="sxs-lookup"><span data-stu-id="cb12b-107">It specifies that the `http://www.adventure-works.com` namespace has the prefix `aw`, and that the `www.fourthcoffee.com` namespace has the prefix of `fc`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="cb12b-108">Код</span><span class="sxs-lookup"><span data-stu-id="cb12b-108">Code</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
Imports <xmlns:fc="www.fourthcoffee.com">  
  
Module Module1  
  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <fc:Child>  
                    <aw:DifferentChild>other content</aw:DifferentChild>  
                </fc:Child>  
                <aw:Child2>c2 content</aw:Child2>  
                <fc:Child3>c3 content</fc:Child3>  
            </aw:Root>  
        Console.WriteLine(root)  
    End Sub  
  
End Module  
```  
  
### <a name="comments"></a><span data-ttu-id="cb12b-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="cb12b-109">Comments</span></span>  
 <span data-ttu-id="cb12b-110">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="cb12b-110">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:fc="www.fourthcoffee.com" xmlns:aw="http://www.adventure-works.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cb12b-111">См. также</span><span class="sxs-lookup"><span data-stu-id="cb12b-111">See Also</span></span>  
 [<span data-ttu-id="cb12b-112">Работа с пространствами имен XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cb12b-112">Working with XML Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
