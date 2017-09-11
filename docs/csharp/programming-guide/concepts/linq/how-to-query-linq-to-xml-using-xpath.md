---
title: "Практическое руководство. Запрос LINQ to XML с использованием XPath (C#)"
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
ms.assetid: ee5af263-4ab1-45e5-b792-33a3221b426d
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6d7acf7519e6ab3384f2f34b8435fe96307921f0
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-query-linq-to-xml-using-xpath-c"></a><span data-ttu-id="ba024-102">Практическое руководство. Запрос LINQ to XML с использованием XPath (C#)</span><span class="sxs-lookup"><span data-stu-id="ba024-102">How to: Query LINQ to XML Using XPath (C#)</span></span>
<span data-ttu-id="ba024-103">В этом разделе описываются методы расширения, обеспечивающие запрос XML-дерева с помощью XPath.</span><span class="sxs-lookup"><span data-stu-id="ba024-103">This topic introduces the extension methods that enable you to query an XML tree by using XPath.</span></span> <span data-ttu-id="ba024-104">Подробные сведения об использовании данных методов расширения см. в разделе <xref:System.Xml.XPath.Extensions?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="ba024-104">For detailed information about using these extension methods, see <xref:System.Xml.XPath.Extensions?displayProperty=fullName>.</span></span>  
  
 <span data-ttu-id="ba024-105">Рекомендуется использовать XPath с LINQ to XML, только если есть основательная причина для применения запросов на основе XPath, такая как широкое использование кода прежних версий.</span><span class="sxs-lookup"><span data-stu-id="ba024-105">Unless you have a very specific reason for querying using XPath, such as extensive use of legacy code, using XPath with LINQ to XML is not recommended.</span></span> <span data-ttu-id="ba024-106">Запросы XPath не действуют столь эффективно, как запросы [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ba024-106">XPath queries will not perform as well as [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] queries.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba024-107">Пример</span><span class="sxs-lookup"><span data-stu-id="ba024-107">Example</span></span>  
 <span data-ttu-id="ba024-108">В следующем примере создается небольшое XML-дерево и для получения набора элементов используется запрос <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A>.</span><span class="sxs-lookup"><span data-stu-id="ba024-108">The following example creates a small XML tree and uses <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> to select a set of elements.</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child1", 1),  
    new XElement("Child1", 2),  
    new XElement("Child1", 3),  
    new XElement("Child2", 4),  
    new XElement("Child2", 5),  
    new XElement("Child2", 6)  
);  
IEnumerable<XElement> list = root.XPathSelectElements("./Child2");  
foreach (XElement el in list)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="ba024-109">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="ba024-109">This example produces the following output:</span></span>  
  
```xml  
<Child2>4</Child2>  
<Child2>5</Child2>  
<Child2>6</Child2>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ba024-110">См. также</span><span class="sxs-lookup"><span data-stu-id="ba024-110">See Also</span></span>  
 [<span data-ttu-id="ba024-111">Дополнительные способы создания запросов (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="ba024-111">Advanced Query Techniques (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)

