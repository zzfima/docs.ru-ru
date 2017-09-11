---
title: "Предварительная атомизация объектов XName (LINQ to XML) (C#)"
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
ms.assetid: e84fbbe7-f072-4771-bfbb-059d18e1ad15
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: bc71a1a5b6d8fe038a9eefaff1649df0ea81aa02
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="pre-atomization-of-xname-objects-linq-to-xml-c"></a><span data-ttu-id="5b37f-102">Предварительная атомизация объектов XName (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="5b37f-102">Pre-Atomization of XName Objects (LINQ to XML) (C#)</span></span>
<span data-ttu-id="5b37f-103">Одним из способов повышения производительности в LINQ to XML является предварительная атомизация объектов <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="5b37f-103">One way to improve performance in LINQ to XML is to pre-atomize <xref:System.Xml.Linq.XName> objects.</span></span> <span data-ttu-id="5b37f-104">Предварительная атомизация состоит в том, что необходимо назначить строке объект <xref:System.Xml.Linq.XName>, прежде чем создавать XML-дерево с использованием конструкторов классов <xref:System.Xml.Linq.XElement> и <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="5b37f-104">Pre-atomization means that you assign a string to an <xref:System.Xml.Linq.XName> object before you create the XML tree by using the constructors of the <xref:System.Xml.Linq.XElement> and  <xref:System.Xml.Linq.XAttribute> classes.</span></span> <span data-ttu-id="5b37f-105">Затем, вместо того чтобы передавать строку в конструктор, где будет выполнено ее неявное преобразование в объект <xref:System.Xml.Linq.XName>, можно передать инициализированный объект <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="5b37f-105">Then, instead of passing a string to the constructor, which would use the implicit conversion from string to <xref:System.Xml.Linq.XName>, you pass the initialized <xref:System.Xml.Linq.XName> object.</span></span>  
  
 <span data-ttu-id="5b37f-106">Таким способом можно повысить производительность при создании большого XML-дерева с рядом повторяющихся имен.</span><span class="sxs-lookup"><span data-stu-id="5b37f-106">This improves performance when you create a large XML tree in which specific names are repeated.</span></span> <span data-ttu-id="5b37f-107">Для этого перед построением XML-дерева необходимо объявить и инициализировать объекты <xref:System.Xml.Linq.XName>, а затем в качестве имен элементов и атрибутов указать эти объекты <xref:System.Xml.Linq.XName> вместо строк.</span><span class="sxs-lookup"><span data-stu-id="5b37f-107">To do this, you declare and initialize <xref:System.Xml.Linq.XName> objects before you construct the XML tree, and then use the <xref:System.Xml.Linq.XName> objects instead of specifying strings for the element and attribute names.</span></span> <span data-ttu-id="5b37f-108">Эта техника может дать существенный рост производительности, когда создается большое количество элементов (или атрибутов) с одним и тем же именем.</span><span class="sxs-lookup"><span data-stu-id="5b37f-108">This technique can yield significant performance gains if you are creating a large number of elements (or attributes) with the same name.</span></span>  
  
 <span data-ttu-id="5b37f-109">Чтобы принять решение об использовании предварительной атомизации, протестируйте этот прием в вашем конкретном случае.</span><span class="sxs-lookup"><span data-stu-id="5b37f-109">You should test pre-atomization with your scenario to decide if you should use it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b37f-110">Пример</span><span class="sxs-lookup"><span data-stu-id="5b37f-110">Example</span></span>  
 <span data-ttu-id="5b37f-111">В следующем примере это показано.</span><span class="sxs-lookup"><span data-stu-id="5b37f-111">The following example demonstrates this.</span></span>  
  
```csharp  
XName Root = "Root";  
XName Data = "Data";  
XName ID = "ID";  
  
XElement root = new XElement(Root,  
    new XElement(Data,  
        new XAttribute(ID, "1"),  
        "4,100,000"),  
    new XElement(Data,  
        new XAttribute(ID, "2"),  
        "3,700,000"),  
    new XElement(Data,  
        new XAttribute(ID, "3"),  
        "1,150,000")  
);  
  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="5b37f-112">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="5b37f-112">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Data ID="1">4,100,000</Data>  
  <Data ID="2">3,700,000</Data>  
  <Data ID="3">1,150,000</Data>  
</Root>  
```  
  
 <span data-ttu-id="5b37f-113">Следующий пример демонстрирует ту же технику, когда XML-документ находится в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="5b37f-113">The following example shows the same technique where the XML document is in a namespace:</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XName Root = aw + "Root";  
XName Data = aw + "Data";  
XName ID = "ID";  
  
XElement root = new XElement(Root,  
    new XAttribute(XNamespace.Xmlns + "aw", aw),  
    new XElement(Data,  
        new XAttribute(ID, "1"),  
        "4,100,000"),  
    new XElement(Data,  
        new XAttribute(ID, "2"),  
        "3,700,000"),  
    new XElement(Data,  
        new XAttribute(ID, "3"),  
        "1,150,000")  
);  
  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="5b37f-114">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="5b37f-114">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Data ID="1">4,100,000</aw:Data>  
  <aw:Data ID="2">3,700,000</aw:Data>  
  <aw:Data ID="3">1,150,000</aw:Data>  
</aw:Root>  
```  
  
 <span data-ttu-id="5b37f-115">Следующий пример наиболее приближен к реальной ситуации.</span><span class="sxs-lookup"><span data-stu-id="5b37f-115">The following example is more similar to what you will likely encounter in the real world.</span></span> <span data-ttu-id="5b37f-116">В этом примере содержимое элементов предоставляется запросом.</span><span class="sxs-lookup"><span data-stu-id="5b37f-116">In this example, the content of the element is supplied by a query:</span></span>  
  
```csharp  
XName Root = "Root";  
XName Data = "Data";  
XName ID = "ID";  
  
DateTime t1 = DateTime.Now;  
XElement root = new XElement(Root,  
    from i in System.Linq.Enumerable.Range(1, 100000)  
    select new XElement(Data,  
        new XAttribute(ID, i),  
        i * 5)  
);  
DateTime t2 = DateTime.Now;  
  
Console.WriteLine("Time to construct:{0}", t2 - t1);  
```  
  
 <span data-ttu-id="5b37f-117">Производительность кода в предыдущем примере выше, чем в следующем, где не выполняется предварительная атомизация имен.</span><span class="sxs-lookup"><span data-stu-id="5b37f-117">The previous example performs better than the following example, in which names are not pre-atomized:</span></span>  
  
```csharp  
DateTime t1 = DateTime.Now;  
XElement root = new XElement("Root",  
    from i in System.Linq.Enumerable.Range(1, 100000)  
    select new XElement("Data",  
        new XAttribute("ID", i),  
        i * 5)  
);  
DateTime t2 = DateTime.Now;  
  
Console.WriteLine("Time to construct:{0}", t2 - t1);  
```  
  
## <a name="see-also"></a><span data-ttu-id="5b37f-118">См. также</span><span class="sxs-lookup"><span data-stu-id="5b37f-118">See Also</span></span>  
 <span data-ttu-id="5b37f-119">[Производительность (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/performance-linq-to-xml.md) </span><span class="sxs-lookup"><span data-stu-id="5b37f-119">[Performance (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/performance-linq-to-xml.md) </span></span>  
 [<span data-ttu-id="5b37f-120">Атомарные объекты XName и XNamespace (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="5b37f-120">Atomized XName and XNamespace Objects (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/atomized-xname-and-xnamespace-objects-linq-to-xml.md)

