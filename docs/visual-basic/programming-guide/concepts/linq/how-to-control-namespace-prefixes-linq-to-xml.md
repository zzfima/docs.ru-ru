---
title: Руководство. Управление префиксами пространств имен (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 2fcf28a5-31b6-409d-84ea-27c22f71fc9f
ms.openlocfilehash: 5ba415452a8671466c3a4c71a88731e5bd3cda60
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348376"
---
# <a name="how-to-control-namespace-prefixes-visual-basic-linq-to-xml"></a><span data-ttu-id="200e4-102">Практическое руководство. Управление префиксами пространств имен (Visual Basic) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="200e4-102">How to: Control Namespace Prefixes (Visual Basic) (LINQ to XML)</span></span>
<span data-ttu-id="200e4-103">В этом разделе рассматривается управление префиксами пространств имен.</span><span class="sxs-lookup"><span data-stu-id="200e4-103">This topic describes how you can control namespace prefixes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="200e4-104">Пример</span><span class="sxs-lookup"><span data-stu-id="200e4-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="200e4-105">Описание</span><span class="sxs-lookup"><span data-stu-id="200e4-105">Description</span></span>  
 <span data-ttu-id="200e4-106">В этом примере объявляются два пространства имен.</span><span class="sxs-lookup"><span data-stu-id="200e4-106">This example declares two namespaces.</span></span> <span data-ttu-id="200e4-107">Он указывает, что `http://www.adventure-works.com` пространство имен содержит префикс `aw`, а пространство имен `www.fourthcoffee.com` имеет префикс `fc`.</span><span class="sxs-lookup"><span data-stu-id="200e4-107">It specifies that the `http://www.adventure-works.com` namespace has the prefix `aw`, and that the `www.fourthcoffee.com` namespace has the prefix of `fc`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="200e4-108">Код</span><span class="sxs-lookup"><span data-stu-id="200e4-108">Code</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="200e4-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="200e4-109">Comments</span></span>  
 <span data-ttu-id="200e4-110">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="200e4-110">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:fc="www.fourthcoffee.com" xmlns:aw="http://www.adventure-works.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="200e4-111">См. также</span><span class="sxs-lookup"><span data-stu-id="200e4-111">See also</span></span>

- [<span data-ttu-id="200e4-112">Общие сведения о пространствах имен (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="200e4-112">Namespaces Overview (LINQ to XML) (Visual Basic)</span></span>](namespaces-overview-linq-to-xml.md)
