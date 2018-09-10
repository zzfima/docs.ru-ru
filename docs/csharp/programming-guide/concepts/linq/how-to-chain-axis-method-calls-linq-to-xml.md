---
title: Практическое руководство. Связанные вызовы метода оси (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 067e6da2-ee32-486d-803c-e611b328e39a
ms.openlocfilehash: b486ef5cbf1f9752077cfa8d774184c7be90f6f2
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2018
ms.locfileid: "44212104"
---
# <a name="how-to-chain-axis-method-calls-linq-to-xml-c"></a>Практическое руководство. Связанные вызовы метода оси (LINQ to XML) (C#)
Обычно при написании кода вы будете придерживаться схемы, по которой вызывается метод оси, после чего вызывается одна из осей метода расширений.  
  
 Существуют две оси с именем `Elements`, которые возвращают коллекцию элементов: методы <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> и <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType>. Можно сочетать эти две оси таким образом, чтобы найти все элементы с указанным именем на заданной глубине дерева.  
  
## <a name="example"></a>Пример  
 В этом примере с помощью методов<xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> и <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> выполняется поиск всех элементов `Name` во всех элементах `Address` во всех элементах `PurchaseOrder`.  
  
 В этом примере используется следующий XML-документ: [Пример XML-файла. Несколько заказов на покупку (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).  
  
```csharp  
XElement purchaseOrders = XElement.Load("PurchaseOrders.xml");  
IEnumerable<XElement> names =  
    from el in purchaseOrders  
        .Elements("PurchaseOrder")  
        .Elements("Address")  
        .Elements("Name")  
    select el;  
foreach (XElement e in names)  
    Console.WriteLine(e);  
```  
  
 В этом примере выводятся следующие данные:  
  
```xml  
<Name>Ellen Adams</Name>  
<Name>Tai Yee</Name>  
<Name>Cristian Osorio</Name>  
<Name>Cristian Osorio</Name>  
<Name>Jessica Arnold</Name>  
<Name>Jessica Arnold</Name>  
```  
  
 Такой подход оправдан, поскольку одна из реализаций оси `Elements` представляет собой метод расширений <xref:System.Collections.Generic.IEnumerable%601> по отношению к <xref:System.Xml.Linq.XContainer>. <xref:System.Xml.Linq.XElement> вычисляется из <xref:System.Xml.Linq.XContainer>, что позволяет вызвать метод <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> по результатам вызова метода <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>.  
  
## <a name="example"></a>Пример  
 Иногда может потребоваться получить все элементы с определенной глубины структуры элементов при условии, что неизвестно, имеются промежуточные предки или нет. Например, в следующем документе может потребоваться получение всех элементов `ConfigParameter`, которые являются дочерними по отношению к элементу `Customer`, кроме `ConfigParameter`, которые являются дочерними по отношению к элементу `Root`.  
  
```xml  
<Root>  
  <ConfigParameter>RootConfigParameter</ConfigParameter>  
  <Customer>  
    <Name>Frank</Name>  
    <Config>  
      <ConfigParameter>FirstConfigParameter</ConfigParameter>  
    </Config>  
  </Customer>  
  <Customer>  
    <Name>Bob</Name>  
    <!--This customer doesn't have a Config element-->  
  </Customer>  
  <Customer>  
    <Name>Bill</Name>  
    <Config>  
      <ConfigParameter>SecondConfigParameter</ConfigParameter>  
    </Config>  
  </Customer>  
</Root>  
```  
  
 Чтобы это реализовать, можно использовать ось <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> следующим образом.  
  
```csharp  
XElement root = XElement.Load("Irregular.xml");  
IEnumerable<XElement> configParameters =   
    root.Elements("Customer").Elements("Config").  
    Elements("ConfigParameter");  
foreach (XElement cp in configParameters)  
    Console.WriteLine(cp);  
```  
  
 В этом примере выводятся следующие данные:  
  
```xml  
<ConfigParameter>FirstConfigParameter</ConfigParameter>  
<ConfigParameter>SecondConfigParameter</ConfigParameter>  
```  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует тот же способ обработки XML, что и в пространстве имен. Дополнительные сведения см. в разделе [Работа с пространствами имен XML (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).  
  
 В этом примере используется следующий XML-документ: [Пример XML-файла. Несколько заказов на покупку в пространстве имен](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md).  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement purchaseOrders = XElement.Load("PurchaseOrdersInNamespace.xml");  
IEnumerable<XElement> names =  
    from el in purchaseOrders  
        .Elements(aw + "PurchaseOrder")  
        .Elements(aw + "Address")  
        .Elements(aw + "Name")  
    select el;  
foreach (XElement e in names)  
    Console.WriteLine(e);  
```  
  
 В этом примере выводятся следующие данные:  
  
```xml  
<aw:Name xmlns:aw="http://www.adventure-works.com">Ellen Adams</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Tai Yee</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Cristian Osorio</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Cristian Osorio</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Jessica Arnold</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Jessica Arnold</aw:Name>  
```  
  
## <a name="see-also"></a>См. также

- [Оси LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)
