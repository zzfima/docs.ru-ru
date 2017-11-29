---
title: "Как: проецирование анонимного типа (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 30b42987-0e0e-4b2b-adb1-5255ddfbcd7b
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b383b0a7e0fc0aa22bdcc8ed87628947858986da
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-project-an-anonymous-type-visual-basic"></a>Как: проецирование анонимного типа (Visual Basic)
В некоторых случаях может потребоваться проецировать запрос на новый тип, даже если известно, что этот тип будет использоваться недолго. Создание нового типа для использования в проекции требует много дополнительной работы. Гораздо более эффективный подход заключается в проецировании на анонимный тип. Анонимные типы позволяют определять класс и инициализировать его объект, не присваивая имя этому классу.  
  
 Анонимные типы являются реализацией в языке C# математического понятия *кортежа*. Математический термин «кортеж» обозначает одноэлементные, двухэлементные, трехэлементные, четырехэлементные, пятиэлементные и n-элементные последовательности. Он относится к конечной последовательности объектов, каждый из которых имеет конкретный тип. Иногда такую последовательность называют списком пар «имя/значение». Например, содержимое адреса в XML-документе [Пример XML-файла. Стандартный заказ на покупку (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md) можно представить следующим образом.  
  
```  
Name: Ellen Adams  
Street: 123 Maple Street  
City: Mill Valley  
State: CA  
Zip: 90952  
Country: USA  
```  
  
 Создание экземпляра анонимного типа удобно трактовать как создание n-элементного кортежа. При написании запроса, создающего кортеж в предложении `Select`, запрос возвращает объект `IEnumerable` кортежа.  
  
## <a name="example"></a>Пример  
 В этом примере предложение `Select` проецирует анонимный тип. Затем в этом примере используется тип `Dim` для создания объекта `IEnumerable`. В цикле `For Each` переменная итерации становится экземпляром анонимного типа, созданного в выражении запроса.  
  
 В этом примере используется следующий XML-документ: [Пример XML-файла. Клиенты и заказы (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).  
  
```vb  
Dim custOrd As XElement = XElement.Load("CustomersOrders.xml")  
Dim custList = _  
    From el In custOrd.<Customers>.<Customer> _  
    Select New With { _  
        .CustomerID = el.@<CustomerID>, _  
        .CompanyName = el.<CompanyName>.Value, _  
        .ContactName = el.<ContactName>.Value _  
    }  
For Each cust In custList  
    Console.WriteLine("{0}:{1}:{2}", cust.CustomerID, cust.CompanyName, cust.ContactName)  
Next  
```  
  
 Этот код выводит следующие результаты:  
  
```  
GREAL:Great Lakes Food Market:Howard Snyder  
HUNGC:Hungry Coyote Import Store:Yoshi Latimer  
LAZYK:Lazy K Kountry Store:John Steel  
LETSS:Let's Stop N Shop:Jaime Yorres  
```  
  
## <a name="see-also"></a>См. также  
 [Проекции и преобразования (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)
