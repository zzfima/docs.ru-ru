---
title: Практическое руководство. Фильтрация по необязательным элементам (C#)
ms.date: 07/20/2015
ms.assetid: f99e2f93-fca5-403f-8a0c-770761d4905a
ms.openlocfilehash: c781db261dbf673af7a11150971956b4c07da774
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47076601"
---
# <a name="how-to-filter-on-an-optional-element-c"></a><span data-ttu-id="9e02e-102">Практическое руководство. Фильтрация по необязательным элементам (C#)</span><span class="sxs-lookup"><span data-stu-id="9e02e-102">How to: Filter on an Optional Element (C#)</span></span>
<span data-ttu-id="9e02e-103">Иногда необходимо выполнить фильтрацию элемента, даже если неизвестно, существует ли он в документе XML.</span><span class="sxs-lookup"><span data-stu-id="9e02e-103">Sometimes you want to filter for an element even though you are not sure it exists in your XML document.</span></span> <span data-ttu-id="9e02e-104">Поиск должен быть выполнен, чтобы, если конкретный элемент не имеет дочернего узла, при фильтрации по этому элементу не возникло исключение null reference.</span><span class="sxs-lookup"><span data-stu-id="9e02e-104">The search should be executed so that if the particular element does not have the child element, you do not trigger a null reference exception by filtering for it.</span></span> <span data-ttu-id="9e02e-105">В следующем примере элемент `Child5` не имеет дочернего узла `Type`, тем не менее запрос выполняется правильно.</span><span class="sxs-lookup"><span data-stu-id="9e02e-105">In the following example, the `Child5` element does not have a `Type` child element, but the query still executes correctly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e02e-106">Пример</span><span class="sxs-lookup"><span data-stu-id="9e02e-106">Example</span></span>  
 <span data-ttu-id="9e02e-107">Этот пример использует метод расширений <xref:System.Xml.Linq.Extensions.Elements%2A>.</span><span class="sxs-lookup"><span data-stu-id="9e02e-107">This example uses the <xref:System.Xml.Linq.Extensions.Elements%2A> extension method.</span></span>  
  
```csharp  
XElement root = XElement.Parse(@"<Root>  
  <Child1>  
    <Text>Child One Text</Text>  
    <Type Value=""Yes""/>  
  </Child1>  
  <Child2>  
    <Text>Child Two Text</Text>  
    <Type Value=""Yes""/>  
  </Child2>  
  <Child3>  
    <Text>Child Three Text</Text>  
    <Type Value=""No""/>  
  </Child3>  
  <Child4>  
    <Text>Child Four Text</Text>  
    <Type Value=""Yes""/>  
  </Child4>  
  <Child5>  
    <Text>Child Five Text</Text>  
  </Child5>  
</Root>");  
var cList =  
    from typeElement in root.Elements().Elements("Type")  
    where (string)typeElement.Attribute("Value") == "Yes"  
    select (string)typeElement.Parent.Element("Text");  
foreach(string str in cList)  
    Console.WriteLine(str);  
```  
  
 <span data-ttu-id="9e02e-108">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="9e02e-108">This code produces the following output:</span></span>  
  
```  
Child One Text  
Child Two Text  
Child Four Text  
```  
  
## <a name="example"></a><span data-ttu-id="9e02e-109">Пример</span><span class="sxs-lookup"><span data-stu-id="9e02e-109">Example</span></span>  
 <span data-ttu-id="9e02e-110">Следующий пример демонстрирует тот же запрос XML, что и в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="9e02e-110">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="9e02e-111">Дополнительные сведения см. в разделе [Работа с пространствами имен XML (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="9e02e-111">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
```csharp  
XElement root = XElement.Parse(@"<Root xmlns='http://www.adatum.com'>  
  <Child1>  
    <Text>Child One Text</Text>  
    <Type Value=""Yes""/>  
  </Child1>  
  <Child2>  
    <Text>Child Two Text</Text>  
    <Type Value=""Yes""/>  
  </Child2>  
  <Child3>  
    <Text>Child Three Text</Text>  
    <Type Value=""No""/>  
  </Child3>  
  <Child4>  
    <Text>Child Four Text</Text>  
    <Type Value=""Yes""/>  
  </Child4>  
  <Child5>  
    <Text>Child Five Text</Text>  
  </Child5>  
</Root>");  
XNamespace ad = "http://www.adatum.com";  
var cList =  
    from typeElement in root.Elements().Elements(ad + "Type")  
    where (string)typeElement.Attribute("Value") == "Yes"  
    select (string)typeElement.Parent.Element(ad + "Text");  
foreach (string str in cList)  
    Console.WriteLine(str);  
```  
  
 <span data-ttu-id="9e02e-112">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="9e02e-112">This code produces the following output:</span></span>  
  
```  
Child One Text  
Child Two Text  
Child Four Text  
```  
  
## <a name="see-also"></a><span data-ttu-id="9e02e-113">См. также</span><span class="sxs-lookup"><span data-stu-id="9e02e-113">See Also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=nameWithType>  
- <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>  
- <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType>  
- [<span data-ttu-id="9e02e-114">Базовые запросы (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="9e02e-114">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)  
- [<span data-ttu-id="9e02e-115">Общие сведения о стандартных операторах запроса (C#)</span><span class="sxs-lookup"><span data-stu-id="9e02e-115">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
- [<span data-ttu-id="9e02e-116">Операции проекции (C#)</span><span class="sxs-lookup"><span data-stu-id="9e02e-116">Projection Operations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projection-operations.md)
