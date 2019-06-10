---
title: Практическое руководство. Извлечение одного атрибута (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 1b6b07b9-933f-47e9-874e-e790cab49dc5
ms.openlocfilehash: cfab2cbb80eb330a5fd745871eb272cca0b37798
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66486444"
---
# <a name="how-to-retrieve-a-single-attribute-linq-to-xml-c"></a><span data-ttu-id="2c127-102">Практическое руководство. Извлечение одного атрибута (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="2c127-102">How to: Retrieve a Single Attribute (LINQ to XML) (C#)</span></span>
<span data-ttu-id="2c127-103">В этом разделе приведены объяснения способа получения одного атрибута элемента при условии, что название атрибута известно.</span><span class="sxs-lookup"><span data-stu-id="2c127-103">This topic explains how to retrieve a single attribute of an element, given the attribute name.</span></span> <span data-ttu-id="2c127-104">Это полезно для составления выражений запросов, при которых требуется найти элемент с определенным атрибутом.</span><span class="sxs-lookup"><span data-stu-id="2c127-104">This is useful for writing query expressions where you want to find an element that has a particular attribute.</span></span>  
  
 <span data-ttu-id="2c127-105">Метод <xref:System.Xml.Linq.XElement.Attribute%2A> класса <xref:System.Xml.Linq.XElement> возвращает значение <xref:System.Xml.Linq.XAttribute> с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="2c127-105">The <xref:System.Xml.Linq.XElement.Attribute%2A> method of the <xref:System.Xml.Linq.XElement> class returns the <xref:System.Xml.Linq.XAttribute> with the specified name.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c127-106">Пример</span><span class="sxs-lookup"><span data-stu-id="2c127-106">Example</span></span>  
 <span data-ttu-id="2c127-107">В следующем примере используется метод <xref:System.Xml.Linq.XElement.Attribute%2A>.</span><span class="sxs-lookup"><span data-stu-id="2c127-107">The following example uses the <xref:System.Xml.Linq.XElement.Attribute%2A> method.</span></span>  
  
```csharp  
XElement cust = new XElement("PhoneNumbers",  
    new XElement("Phone",  
        new XAttribute("type", "home"),  
        "555-555-5555"),  
    new XElement("Phone",  
        new XAttribute("type", "work"),  
        "555-555-6666")  
);  
IEnumerable<XElement> elList =  
    from el in cust.Descendants("Phone")  
    select el;  
foreach (XElement el in elList)  
    Console.WriteLine((string)el.Attribute("type"));  
```  
  
 <span data-ttu-id="2c127-108">В этом примере выполняется поиск всех потомков в дереве с названием `Phone`, затем атрибута с названием `type`.</span><span class="sxs-lookup"><span data-stu-id="2c127-108">This example finds all the descendants in the tree named `Phone`, and then finds the attribute named `type`.</span></span>  
  
 <span data-ttu-id="2c127-109">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="2c127-109">This code produces the following output:</span></span>  
  
```  
home  
work  
```  
  
## <a name="example"></a><span data-ttu-id="2c127-110">Пример</span><span class="sxs-lookup"><span data-stu-id="2c127-110">Example</span></span>  
 <span data-ttu-id="2c127-111">Если требуется получить значение атрибута, можно его задать точно так же, как при работе с объектами <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="2c127-111">If you want to retrieve the value of the attribute, you can cast it, just as you do for with <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="2c127-112">В следующем примере это показано.</span><span class="sxs-lookup"><span data-stu-id="2c127-112">The following example demonstrates this.</span></span>  
  
```csharp  
XElement cust = new XElement("PhoneNumbers",  
    new XElement("Phone",  
        new XAttribute("type", "home"),  
        "555-555-5555"),  
    new XElement("Phone",  
        new XAttribute("type", "work"),  
        "555-555-6666")  
);  
IEnumerable<XElement> elList =   
    from el in cust.Descendants("Phone")  
    select el;  
foreach (XElement el in elList)  
    Console.WriteLine((string)el.Attribute("type"));  
```  
  
 <span data-ttu-id="2c127-113">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="2c127-113">This code produces the following output:</span></span>  
  
```  
home  
work  
```  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="2c127-114">предоставляет явные операторы приведения класса <xref:System.Xml.Linq.XAttribute> к `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID` и `GUID?`.</span><span class="sxs-lookup"><span data-stu-id="2c127-114">provides explicit cast operators for the <xref:System.Xml.Linq.XAttribute> class to `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`, and `GUID?`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c127-115">Пример</span><span class="sxs-lookup"><span data-stu-id="2c127-115">Example</span></span>  
 <span data-ttu-id="2c127-116">Следующий пример демонстрирует тот же код атрибута, что и в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="2c127-116">The following example shows the same code for an attribute that is in a namespace.</span></span> <span data-ttu-id="2c127-117">Дополнительные сведения см. в разделе [Работа с пространствами имен XML (C#)](../../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="2c127-117">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md).</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement cust = new XElement(aw + "PhoneNumbers",  
    new XElement(aw + "Phone",  
        new XAttribute(aw + "type", "home"),  
        "555-555-5555"),  
    new XElement(aw + "Phone",  
        new XAttribute(aw + "type", "work"),  
        "555-555-6666")  
);  
IEnumerable<XElement> elList =  
    from el in cust.Descendants(aw + "Phone")  
    select el;  
foreach (XElement el in elList)  
    Console.WriteLine((string)el.Attribute(aw + "type"));  
```  
  
 <span data-ttu-id="2c127-118">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="2c127-118">This code produces the following output:</span></span>  
  
```  
home  
work  
```  
  
## <a name="see-also"></a><span data-ttu-id="2c127-119">См. также</span><span class="sxs-lookup"><span data-stu-id="2c127-119">See also</span></span>

- [<span data-ttu-id="2c127-120">Оси LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="2c127-120">LINQ to XML Axes (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes-overview.md)
