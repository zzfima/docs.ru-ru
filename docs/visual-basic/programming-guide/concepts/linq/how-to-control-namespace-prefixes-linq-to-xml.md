---
title: Практическое руководство. управлять префиксами пространств имен (Visual Basic) (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 2fcf28a5-31b6-409d-84ea-27c22f71fc9f
ms.openlocfilehash: 2b89b49aa76df526c08143cad49685386ffd5e7c
ms.sourcegitcommit: eb9ff6f364cde6f11322e03800d8f5ce302f3c73
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2019
ms.locfileid: "68709821"
---
# <a name="how-to-control-namespace-prefixes-visual-basic-linq-to-xml"></a>Практическое руководство. управлять префиксами пространств имен (Visual Basic) (LINQ to XML)
В этом разделе рассматривается управление префиксами пространств имен.  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
 В этом примере объявляются два пространства имен. Он указывает, что `http://www.adventure-works.com` пространство имен имеет префикс `aw`, а `www.fourthcoffee.com` пространство имен имеет префикс `fc`.  
  
### <a name="code"></a>Код  
  
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
  
### <a name="comments"></a>Комментарии  
 В этом примере выводятся следующие данные:  
  
```xml  
<aw:Root xmlns:fc="www.fourthcoffee.com" xmlns:aw="http://www.adventure-works.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a>См. также

- [Общие сведения о пространствах имен (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md)
