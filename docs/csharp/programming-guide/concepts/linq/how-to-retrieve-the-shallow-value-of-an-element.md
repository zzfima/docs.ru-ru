---
title: Практическое руководство. Извлечение поверхностного значения элемента (C#)
ms.date: 07/20/2015
ms.assetid: 924a2699-72f6-4be1-aaa6-de62f8ec73b9
ms.openlocfilehash: 7e1a5b216a02ca72fa49785e50ed262a89abfcdf
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43505308"
---
# <a name="how-to-retrieve-the-shallow-value-of-an-element-c"></a>Практическое руководство. Извлечение поверхностного значения элемента (C#)
В этом разделе показано, как получить неглубокое значение элемента. Неглубокое значение - это значение только конкретного элемента, в отличие от глубокого значения, которое содержит значения всех элементов-потомков, объединенные в одной строке.  
  
 При получении значения элемента при помощи приведения или свойства <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> выполняется извлечение глубокого значения. Чтобы получить неглубокое значение, можно использовать метод расширений `ShallowValue`, как это показано в следующем примере. Извлечение неглубокого значения полезно тогда, когда требуется выбрать элементы в зависимости от их содержимого.  
  
 В следующем примере объявляется метод расширений, который извлекает неглубокое значение элемента. После этого метод расширения используется в запросе, чтобы вывести список всех элементов с вычисленным значением.  
  
## <a name="example"></a>Пример  
 Следующий текстовый файл Report.xml в этом примере будет исходным.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<Report>  
  <Section>  
    <Heading>  
      <Column Name="CustomerId">=Customer.CustomerId.Heading</Column>  
      <Column Name="Name">=Customer.Name.Heading</Column>  
    </Heading>  
    <Detail>  
      <Column Name="CustomerId">=Customer.CustomerId</Column>  
      <Column Name="Name">=Customer.Name</Column>  
    </Detail>  
  </Section>  
</Report>  
```  
  
```csharp  
public static class MyExtensions  
{  
    public static string ShallowValue(this XElement xe)  
    {  
        return xe  
               .Nodes()  
               .OfType<XText>()  
               .Aggregate(new StringBuilder(),  
                          (s, c) => s.Append(c),  
                          s => s.ToString());  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        XElement root = XElement.Load("Report.xml");  
  
        IEnumerable<XElement> query = from el in root.Descendants()  
                                      where el.ShallowValue().StartsWith("=")  
                                      select el;  
  
        foreach (var q in query)  
        {  
            Console.WriteLine("{0}{1}{2}",  
                q.Name.ToString().PadRight(8),  
                q.Attribute("Name").ToString().PadRight(20),  
                q.ShallowValue());  
        }  
    }  
}  
```  
  
 В этом примере выводятся следующие данные:  
  
```  
Column  Name="CustomerId"   =Customer.CustomerId.Heading  
Column  Name="Name"         =Customer.Name.Heading  
Column  Name="CustomerId"   =Customer.CustomerId  
Column  Name="Name"         =Customer.Name  
```  
  
## <a name="see-also"></a>См. также

- [Оси LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)
