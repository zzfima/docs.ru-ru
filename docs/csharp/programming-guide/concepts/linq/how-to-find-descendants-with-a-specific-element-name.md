---
title: Практическое руководство. Поиск потомков с определенным именем элемента (C#)
ms.date: 07/20/2015
ms.assetid: f684da20-bee9-47f5-9607-7e3fd7e67470
ms.openlocfilehash: c54b3c6a01459781b8ed9d5495bf9eb8937363fa
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66486753"
---
# <a name="how-to-find-descendants-with-a-specific-element-name-c"></a><span data-ttu-id="95a1f-102">Практическое руководство. Поиск потомков с определенным именем элемента (C#)</span><span class="sxs-lookup"><span data-stu-id="95a1f-102">How to: Find Descendants with a Specific Element Name (C#)</span></span>
<span data-ttu-id="95a1f-103">Иногда возникает необходимость найти всех потомков с определенным именем.</span><span class="sxs-lookup"><span data-stu-id="95a1f-103">Sometimes you want to find all descendants with a particular name.</span></span> <span data-ttu-id="95a1f-104">В таких случаях можно написать код для просмотра всех потомков, но проще использовать ось <xref:System.Xml.Linq.XContainer.Descendants%2A>.</span><span class="sxs-lookup"><span data-stu-id="95a1f-104">You could write code to iterate through all of the descendants, but it is easier to use the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>  
  
## <a name="example"></a><span data-ttu-id="95a1f-105">Пример</span><span class="sxs-lookup"><span data-stu-id="95a1f-105">Example</span></span>  
 <span data-ttu-id="95a1f-106">В следующем примере показано, как находить потомков на основе имени элемента.</span><span class="sxs-lookup"><span data-stu-id="95a1f-106">The following example shows how to find descendants based on the element name.</span></span>  
  
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
  
 <span data-ttu-id="95a1f-107">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="95a1f-107">This code produces the following output:</span></span>  
  
```  
Some text that is broken up into multiple segments.  
```  
  
## <a name="example"></a><span data-ttu-id="95a1f-108">Пример</span><span class="sxs-lookup"><span data-stu-id="95a1f-108">Example</span></span>  
 <span data-ttu-id="95a1f-109">Следующий пример демонстрирует тот же запрос XML, что и в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="95a1f-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="95a1f-110">Дополнительные сведения см. в разделе [Работа с пространствами имен XML (C#)](../../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="95a1f-110">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="95a1f-111">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="95a1f-111">This code produces the following output:</span></span>  
  
```  
Some text that is broken up into multiple segments.  
```  
  
## <a name="see-also"></a><span data-ttu-id="95a1f-112">См. также</span><span class="sxs-lookup"><span data-stu-id="95a1f-112">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Descendants%2A>
