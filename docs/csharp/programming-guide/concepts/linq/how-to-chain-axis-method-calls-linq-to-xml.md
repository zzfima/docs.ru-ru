---
title: Практическое руководство. Связанные вызовы метода оси (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 067e6da2-ee32-486d-803c-e611b328e39a
ms.openlocfilehash: ccfbf516a7fddbef357bfb0072288e250768616b
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141435"
---
# <a name="how-to-chain-axis-method-calls-linq-to-xml-c"></a><span data-ttu-id="f64e3-102">Практическое руководство. Связанные вызовы метода оси (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="f64e3-102">How to chain axis method calls (LINQ to XML) (C#)</span></span>
<span data-ttu-id="f64e3-103">Обычно при написании кода вы будете придерживаться схемы, по которой вызывается метод оси, после чего вызывается одна из осей метода расширений.</span><span class="sxs-lookup"><span data-stu-id="f64e3-103">A common pattern that you will use in your code is to call an axis method, then call one of the extension method axes.</span></span>  
  
 <span data-ttu-id="f64e3-104">Существуют две оси с именем `Elements`, которые возвращают коллекцию элементов: методы <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> и <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f64e3-104">There are two axes with the name of `Elements` that return a collection of elements: the <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> method and the <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="f64e3-105">Можно сочетать эти две оси таким образом, чтобы найти все элементы с указанным именем на заданной глубине дерева.</span><span class="sxs-lookup"><span data-stu-id="f64e3-105">You can combine these two axes to find all elements of a specified name at a given depth in the tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f64e3-106">Пример</span><span class="sxs-lookup"><span data-stu-id="f64e3-106">Example</span></span>  
 <span data-ttu-id="f64e3-107">В этом примере с помощью методов<xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> и <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> выполняется поиск всех элементов `Name` во всех элементах `Address` во всех элементах `PurchaseOrder`.</span><span class="sxs-lookup"><span data-stu-id="f64e3-107">This example uses <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> and <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> to find all `Name` elements in all `Address` elements in all `PurchaseOrder` elements.</span></span>  
  
 <span data-ttu-id="f64e3-108">В этом примере используется следующий XML-документ: [Пример XML-файла. Несколько заказов на покупку (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="f64e3-108">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="f64e3-109">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="f64e3-109">This example produces the following output:</span></span>  
  
```xml  
<Name>Ellen Adams</Name>  
<Name>Tai Yee</Name>  
<Name>Cristian Osorio</Name>  
<Name>Cristian Osorio</Name>  
<Name>Jessica Arnold</Name>  
<Name>Jessica Arnold</Name>  
```  
  
 <span data-ttu-id="f64e3-110">Такой подход оправдан, поскольку одна из реализаций оси `Elements` представляет собой метод расширений <xref:System.Collections.Generic.IEnumerable%601> по отношению к <xref:System.Xml.Linq.XContainer>.</span><span class="sxs-lookup"><span data-stu-id="f64e3-110">This works because one of the implementations of the `Elements` axis is as an extension method on <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XContainer>.</span></span> <span data-ttu-id="f64e3-111"><xref:System.Xml.Linq.XElement> вычисляется из <xref:System.Xml.Linq.XContainer>, что позволяет вызвать метод <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> по результатам вызова метода <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f64e3-111"><xref:System.Xml.Linq.XElement> derives from <xref:System.Xml.Linq.XContainer>, so you can call the <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> method on the results of a call to the <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f64e3-112">Пример</span><span class="sxs-lookup"><span data-stu-id="f64e3-112">Example</span></span>  
 <span data-ttu-id="f64e3-113">Иногда может потребоваться получить все элементы с определенной глубины структуры элементов при условии, что неизвестно, имеются промежуточные предки или нет.</span><span class="sxs-lookup"><span data-stu-id="f64e3-113">Sometimes you want to retrieve all elements at a particular element depth when there might or might not be intervening ancestors.</span></span> <span data-ttu-id="f64e3-114">Например, в следующем документе может потребоваться получение всех элементов `ConfigParameter`, которые являются дочерними по отношению к элементу `Customer`, кроме `ConfigParameter`, которые являются дочерними по отношению к элементу `Root`.</span><span class="sxs-lookup"><span data-stu-id="f64e3-114">For example, in the following document, you might want to retrieve all the `ConfigParameter` elements that are children of the `Customer` element, but not the `ConfigParameter` that is a child of the `Root` element.</span></span>  
  
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
  
 <span data-ttu-id="f64e3-115">Чтобы это реализовать, можно использовать ось <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> следующим образом.</span><span class="sxs-lookup"><span data-stu-id="f64e3-115">To do this, you can use the <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> axis, as follows:</span></span>  
  
```csharp  
XElement root = XElement.Load("Irregular.xml");  
IEnumerable<XElement> configParameters =   
    root.Elements("Customer").Elements("Config").  
    Elements("ConfigParameter");  
foreach (XElement cp in configParameters)  
    Console.WriteLine(cp);  
```  
  
 <span data-ttu-id="f64e3-116">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="f64e3-116">This example produces the following output:</span></span>  
  
```xml  
<ConfigParameter>FirstConfigParameter</ConfigParameter>  
<ConfigParameter>SecondConfigParameter</ConfigParameter>  
```  
  
## <a name="example"></a><span data-ttu-id="f64e3-117">Пример</span><span class="sxs-lookup"><span data-stu-id="f64e3-117">Example</span></span>  
 <span data-ttu-id="f64e3-118">Следующий пример демонстрирует тот же способ обработки XML, что и в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="f64e3-118">The following example shows the same technique for XML that is in a namespace.</span></span> <span data-ttu-id="f64e3-119">Дополнительные сведения см. в статье [Обзор пространств имен DFS (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="f64e3-119">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="f64e3-120">В этом примере используется следующий XML-документ: [Пример XML-файла. Несколько заказов на покупку в пространстве имен](./sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="f64e3-120">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders in a Namespace](./sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span></span>  
  
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
  
 <span data-ttu-id="f64e3-121">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="f64e3-121">This example produces the following output:</span></span>  
  
```xml  
<aw:Name xmlns:aw="http://www.adventure-works.com">Ellen Adams</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Tai Yee</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Cristian Osorio</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Cristian Osorio</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Jessica Arnold</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Jessica Arnold</aw:Name>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f64e3-122">См. также</span><span class="sxs-lookup"><span data-stu-id="f64e3-122">See also</span></span>

- [<span data-ttu-id="f64e3-123">Оси LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="f64e3-123">LINQ to XML Axes (C#)</span></span>](linq-to-xml-axes-overview.md)
