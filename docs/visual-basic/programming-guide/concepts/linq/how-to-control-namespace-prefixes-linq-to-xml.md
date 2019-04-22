---
title: Практическое руководство. управлять префиксами пространств имен (Visual Basic) (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 2fcf28a5-31b6-409d-84ea-27c22f71fc9f
ms.openlocfilehash: 7e5a05d2fa93e61338f450d0a4d890fa94c04fd2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58839042"
---
# <a name="how-to-control-namespace-prefixes-visual-basic-linq-to-xml"></a><span data-ttu-id="cdf83-102">Практическое руководство. управлять префиксами пространств имен (Visual Basic) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="cdf83-102">How to: Control Namespace Prefixes (Visual Basic) (LINQ to XML)</span></span>
<span data-ttu-id="cdf83-103">В этом разделе рассматривается управление префиксами пространств имен.</span><span class="sxs-lookup"><span data-stu-id="cdf83-103">This topic describes how you can control namespace prefixes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cdf83-104">Пример</span><span class="sxs-lookup"><span data-stu-id="cdf83-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="cdf83-105">Описание</span><span class="sxs-lookup"><span data-stu-id="cdf83-105">Description</span></span>  
 <span data-ttu-id="cdf83-106">В этом примере объявляются два пространства имен.</span><span class="sxs-lookup"><span data-stu-id="cdf83-106">This example declares two namespaces.</span></span> <span data-ttu-id="cdf83-107">Указывает, что `http://www.adventure-works.com` пространства имен имеет префикс `aw`и что `www.fourthcoffee.com` пространства имен имеет префикс `fc`.</span><span class="sxs-lookup"><span data-stu-id="cdf83-107">It specifies that the `http://www.adventure-works.com` namespace has the prefix `aw`, and that the `www.fourthcoffee.com` namespace has the prefix of `fc`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="cdf83-108">Код</span><span class="sxs-lookup"><span data-stu-id="cdf83-108">Code</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="cdf83-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="cdf83-109">Comments</span></span>  
 <span data-ttu-id="cdf83-110">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="cdf83-110">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:fc="www.fourthcoffee.com" xmlns:aw="http://www.adventure-works.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cdf83-111">См. также</span><span class="sxs-lookup"><span data-stu-id="cdf83-111">See also</span></span>

- [<span data-ttu-id="cdf83-112">Работа с пространствами имен XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cdf83-112">Working with XML Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
