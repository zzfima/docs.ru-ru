---
title: "Практическое руководство. Поиск потомков с определенным именем элемента (C#)"
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
ms.assetid: f684da20-bee9-47f5-9607-7e3fd7e67470
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 72659358a50d3ae1de9c699bff0bdd9f4ac4f383
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-find-descendants-with-a-specific-element-name-c"></a><span data-ttu-id="8e88f-102">Практическое руководство. Поиск потомков с определенным именем элемента (C#)</span><span class="sxs-lookup"><span data-stu-id="8e88f-102">How to: Find Descendants with a Specific Element Name (C#)</span></span>
<span data-ttu-id="8e88f-103">Иногда возникает необходимость найти всех потомков с определенным именем.</span><span class="sxs-lookup"><span data-stu-id="8e88f-103">Sometimes you want to find all descendants with a particular name.</span></span> <span data-ttu-id="8e88f-104">В таких случаях можно написать код для просмотра всех потомков, но проще использовать ось <xref:System.Xml.Linq.XContainer.Descendants%2A>.</span><span class="sxs-lookup"><span data-stu-id="8e88f-104">You could write code to iterate through all of the descendants, but it is easier to use the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e88f-105">Пример</span><span class="sxs-lookup"><span data-stu-id="8e88f-105">Example</span></span>  
 <span data-ttu-id="8e88f-106">В следующем примере показано, как находить потомков на основе имени элемента.</span><span class="sxs-lookup"><span data-stu-id="8e88f-106">The following example shows how to find descendants based on the element name.</span></span>  
  
```csharp  
XElement root = XElement.Parse(@"<root>  
  <para>  
    <r>  
      <t>Some text </t>  
    </r>  
    <n>  
      <r>  
        <t>that is broken up into </t>  
      </r>  
    </n>  
    <n>  
      <r>  
        <t>multiple segments.</t>  
      </r>  
    </n>  
  </para>  
</root>");  
IEnumerable<string> textSegs =  
    from seg in root.Descendants("t")  
    select (string)seg;  
  
string str = textSegs.Aggregate(new StringBuilder(),  
    (sb, i) => sb.Append(i),  
    sp => sp.ToString()  
);  
  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="8e88f-107">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="8e88f-107">This code produces the following output:</span></span>  
  
```  
Some text that is broken up into multiple segments.  
```  
  
## <a name="example"></a><span data-ttu-id="8e88f-108">Пример</span><span class="sxs-lookup"><span data-stu-id="8e88f-108">Example</span></span>  
 <span data-ttu-id="8e88f-109">Следующий пример демонстрирует тот же запрос XML, что и в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="8e88f-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="8e88f-110">Дополнительные сведения см. в разделе [Работа с пространствами имен XML (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="8e88f-110">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
```csharp  
XElement root = XElement.Parse(@"<root xmlns='http://www.adatum.com'>  
  <para>  
    <r>  
      <t>Some text </t>  
    </r>  
    <n>  
      <r>  
        <t>that is broken up into </t>  
      </r>  
    </n>  
    <n>  
      <r>  
        <t>multiple segments.</t>  
      </r>  
    </n>  
  </para>  
</root>");  
XNamespace ad = "http://www.adatum.com";  
IEnumerable<string> textSegs =  
    from seg in root.Descendants(ad + "t")  
    select (string)seg;  
  
string str = textSegs.Aggregate(new StringBuilder(),  
    (sb, i) => sb.Append(i),  
    sp => sp.ToString()  
);  
  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="8e88f-111">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="8e88f-111">This code produces the following output:</span></span>  
  
```  
Some text that is broken up into multiple segments.  
```  
  
## <a name="see-also"></a><span data-ttu-id="8e88f-112">См. также</span><span class="sxs-lookup"><span data-stu-id="8e88f-112">See Also</span></span>  
 <span data-ttu-id="8e88f-113"><xref:System.Xml.Linq.XContainer.Descendants%2A></span><span class="sxs-lookup"><span data-stu-id="8e88f-113"><xref:System.Xml.Linq.XContainer.Descendants%2A></span></span>   
 [<span data-ttu-id="8e88f-114">Базовые запросы (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="8e88f-114">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)

