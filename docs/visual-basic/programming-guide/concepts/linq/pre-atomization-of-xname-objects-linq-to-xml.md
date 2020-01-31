---
title: Предварительная атомизация объектов XName (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 06ea104b-f44c-4bb2-9c34-889ae025c80d
ms.openlocfilehash: c0e75afa797d2b20f32fc55e6c19d0c1593d174c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740792"
---
# <a name="pre-atomization-of-xname-objects-linq-to-xml-visual-basic"></a><span data-ttu-id="fafea-102">Предварительное разъединение объектов XName (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fafea-102">Pre-Atomization of XName Objects (LINQ to XML) (Visual Basic)</span></span>

<span data-ttu-id="fafea-103">Одним из способов повышения производительности в LINQ to XML является предварительная атомизация объектов <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="fafea-103">One way to improve performance in LINQ to XML is to pre-atomize <xref:System.Xml.Linq.XName> objects.</span></span> <span data-ttu-id="fafea-104">Перед созданием XML-дерева с помощью конструкторов классов <xref:System.Xml.Linq.XElement> и <xref:System.Xml.Linq.XAttribute> необходимо назначить строку объекту <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="fafea-104">Pre-atomization means that you assign a string to an <xref:System.Xml.Linq.XName> object before you create the XML tree by using the constructors of the <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XAttribute> classes.</span></span> <span data-ttu-id="fafea-105">Затем, вместо того чтобы передавать строку в конструктор, где будет выполнено ее неявное преобразование в объект <xref:System.Xml.Linq.XName>, можно передать инициализированный объект <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="fafea-105">Then, instead of passing a string to the constructor, which would use the implicit conversion from string to <xref:System.Xml.Linq.XName>, you pass the initialized <xref:System.Xml.Linq.XName> object.</span></span>

<span data-ttu-id="fafea-106">Таким способом можно повысить производительность при создании большого XML-дерева с рядом повторяющихся имен.</span><span class="sxs-lookup"><span data-stu-id="fafea-106">This improves performance when you create a large XML tree in which specific names are repeated.</span></span> <span data-ttu-id="fafea-107">Для этого перед построением XML-дерева необходимо объявить и инициализировать объекты <xref:System.Xml.Linq.XName>, а затем в качестве имен элементов и атрибутов указать эти объекты <xref:System.Xml.Linq.XName> вместо строк.</span><span class="sxs-lookup"><span data-stu-id="fafea-107">To do this, you declare and initialize <xref:System.Xml.Linq.XName> objects before you construct the XML tree, and then use the <xref:System.Xml.Linq.XName> objects instead of specifying strings for the element and attribute names.</span></span> <span data-ttu-id="fafea-108">Эта техника может дать существенный рост производительности, когда создается большое количество элементов (или атрибутов) с одним и тем же именем.</span><span class="sxs-lookup"><span data-stu-id="fafea-108">This technique can yield significant performance gains if you are creating a large number of elements (or attributes) with the same name.</span></span>

<span data-ttu-id="fafea-109">Чтобы принять решение об использовании предварительной атомизации, протестируйте этот прием в вашем конкретном случае.</span><span class="sxs-lookup"><span data-stu-id="fafea-109">You should test pre-atomization with your scenario to decide if you should use it.</span></span>

## <a name="example"></a><span data-ttu-id="fafea-110">Пример</span><span class="sxs-lookup"><span data-stu-id="fafea-110">Example</span></span>

<span data-ttu-id="fafea-111">Следующий пример демонстрирует это:</span><span class="sxs-lookup"><span data-stu-id="fafea-111">The following example demonstrates this:</span></span>

```vb
Dim root1 As XName = "Root"
Dim data As XName = "Data"
Dim id As XName = "ID"

Dim root2 As New XElement(root1, New XElement(data, New XAttribute(id, "1"), "4,100,000"),
                          New XElement(data, New XAttribute(id, "2"), "3,700,000"),
                          New XElement(data, New XAttribute(id, "3"), "1,150,000"))

Console.WriteLine(root2)
```

<span data-ttu-id="fafea-112">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="fafea-112">This example produces the following output:</span></span>

```xml
<Root>
  <Data ID="1">4,100,000</Data>
  <Data ID="2">3,700,000</Data>
  <Data ID="3">1,150,000</Data>
</Root>
```

<span data-ttu-id="fafea-113">Следующий пример демонстрирует ту же технику, когда XML-документ находится в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="fafea-113">The following example shows the same technique where the XML document is in a namespace:</span></span>

```vb
Dim aw As XNamespace = "http://www.adventure-works.com"
Dim root1 As XName = aw + "Root"
Dim data As XName = aw + "Data"
Dim id As XName = "ID"

Dim root2 As New XElement(root1, New XAttribute(XNamespace.Xmlns + "aw", aw),
                          New XElement(data, New XAttribute(id, "1"), "4,100,000"),
                          New XElement(data, New XAttribute(id, "2"), "3,700,000"),
                          New XElement(data, New XAttribute(id, "3"), "1,150,000"))

Console.WriteLine(root2)
```

<span data-ttu-id="fafea-114">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="fafea-114">This example produces the following output:</span></span>

```xml
<aw:Root xmlns:aw="http://www.adventure-works.com">
  <aw:Data ID="1">4,100,000</aw:Data>
  <aw:Data ID="2">3,700,000</aw:Data>
  <aw:Data ID="3">1,150,000</aw:Data>
</aw:Root>
```

<span data-ttu-id="fafea-115">Следующий пример наиболее приближен к реальной ситуации.</span><span class="sxs-lookup"><span data-stu-id="fafea-115">The following example is more similar to what you will likely encounter in the real world.</span></span> <span data-ttu-id="fafea-116">В этом примере содержимое элементов предоставляется запросом.</span><span class="sxs-lookup"><span data-stu-id="fafea-116">In this example, the content of the element is supplied by a query:</span></span>

```vb
Dim root1 As XName = "Root"
Dim data As XName = "Data"
Dim id As XName = "ID"
  
Dim sw As Stopwatch = Stopwatch.StartNew()
Dim root2 As New XElement(root1, From i In Enumerable.Range(1, 100000)
                                 Select New XElement(data, New XAttribute(ID, i), i * 5))
sw.Stop()
Console.WriteLine($"Time to construct: {sw.ElapsedMilliseconds} milliseconds")
```  

<span data-ttu-id="fafea-117">Производительность кода в предыдущем примере выше, чем в следующем, где не выполняется предварительная атомизация имен.</span><span class="sxs-lookup"><span data-stu-id="fafea-117">The previous example performs better than the following example, in which names are not pre-atomized:</span></span>

```vb
Dim sw As Stopwatch = Stopwatch.StartNew()
Dim root As New XElement("Root", From i In Enumerable.Range(1, 100000)
                                 Select New XElement("Data", New XAttribute("ID", i), i * 5))
sw.Stop()
Console.WriteLine($"Time to construct: {sw.ElapsedMilliseconds} milliseconds")
```

## <a name="see-also"></a><span data-ttu-id="fafea-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="fafea-118">See also</span></span>

- [<span data-ttu-id="fafea-119">Производительность (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fafea-119">Performance (LINQ to XML) (Visual Basic)</span></span>](performance-linq-to-xml.md)
- [<span data-ttu-id="fafea-120">Атомарные объекты XName и XNamespace (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fafea-120">Atomized XName and XNamespace Objects (LINQ to XML) (Visual Basic)</span></span>](atomized-xname-and-xnamespace-objects-linq-to-xml.md)
