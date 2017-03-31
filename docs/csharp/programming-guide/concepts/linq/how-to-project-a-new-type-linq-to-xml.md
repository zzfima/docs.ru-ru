---
title: "Практическое руководство. Проецирование нового типа (LINQ to XML) (C#) | Документы Майкрософт"
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
ms.assetid: 48145cf9-1e0b-4e73-bbfd-28fc04800dc4
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1aa8c4676890dcc25108d919a501bde44299db04
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-project-a-new-type-linq-to-xml-c"></a>Практическое руководство. Проецирование нового типа (LINQ to XML) (C#)
В других примерах в этом разделе показаны запросы, возвращающие результаты в виде <xref:System.Collections.Generic.IEnumerable%601> из <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601> из `string` и <xref:System.Collections.Generic.IEnumerable%601> из `int`. Это наиболее распространенные типы результатов, но подходят не для всех сценариев. Во многих случаях требуется, чтобы запросы возвращали <xref:System.Collections.Generic.IEnumerable%601> другого типа.  
  
## <a name="example"></a>Пример  
 В данном примере показано, как создавать экземпляры объектов в предложении `select`. Сначала в коде определяется новый класс с помощью конструктора, а затем модифицируется инструкция `select`, чтобы это выражение представляло новый экземпляр нового класса.  
  
 В этом примере используется следующий XML-документ: [Пример XML-файла. Стандартный заказ на покупку (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).  
  
```csharp  
class NameQty {  
    public string name;  
    public int qty;  
    public NameQty(string n, int q)  
    {  
        name = n;  
        qty = q;  
    }  
};  
  
class Program {  
    public static void Main() {  
        XElement po = XElement.Load("PurchaseOrder.xml");  
  
        IEnumerable<NameQty> nqList =  
            from n in po.Descendants("Item")  
            select new NameQty(  
                    (string)n.Element("ProductName"),  
                    (int)n.Element("Quantity")  
                );  
  
        foreach (NameQty n in nqList)  
            Console.WriteLine(n.name + ":" + n.qty);  
    }  
}  
```  
  
 В этом примере используется метод `M:System.Xml.Linq.XElement.Element`, который был представлен в разделе [Практическое руководство. Извлечение одного дочернего элемента (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md). В нем также используется приведение для получения значений элементов, возвращаемых методом `M:System.Xml.Linq.XElement.Element`.  
  
 В этом примере выводятся следующие данные:  
  
```  
Lawnmower:1  
Baby Monitor:2  
```  
  
## <a name="see-also"></a>См. также  
 [Проекции и преобразования (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)
