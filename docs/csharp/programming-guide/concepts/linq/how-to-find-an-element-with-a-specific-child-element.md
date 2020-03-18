---
title: Практическое руководство. Поиск элементов с определенным дочерним элементом (C#)
ms.date: 07/20/2015
ms.assetid: 00cf5555-374e-4369-bf93-7bd2e7f21db3
ms.openlocfilehash: 0536b1b92d4d7fc18b5d406bbcd24aefc6a840c6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141145"
---
# <a name="how-to-find-an-element-with-a-specific-child-element-c"></a><span data-ttu-id="2fad3-102">Практическое руководство. Поиск элементов с определенным дочерним элементом (C#)</span><span class="sxs-lookup"><span data-stu-id="2fad3-102">How to find an element with a specific child element (C#)</span></span>
<span data-ttu-id="2fad3-103">В этом разделе показан определенный элемент, имеющий дочерний элемент с заданным значением.</span><span class="sxs-lookup"><span data-stu-id="2fad3-103">This topic shows how to find a particular element that has a child element with a specific value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2fad3-104">Пример</span><span class="sxs-lookup"><span data-stu-id="2fad3-104">Example</span></span>  
 <span data-ttu-id="2fad3-105">В этом примере осуществляется поиск элемента `Test`, имеющего дочерний элемент `CommandLine` со значением «Examp2.EXE».</span><span class="sxs-lookup"><span data-stu-id="2fad3-105">The example finds the `Test` element that has a `CommandLine` child element with the value of "Examp2.EXE".</span></span>  
  
 <span data-ttu-id="2fad3-106">В этом примере используется следующий XML-документ: [Пример XML-файла. Конфигурация тестирования (LINQ to XML)](./sample-xml-file-test-configuration-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="2fad3-106">This example uses the following XML document: [Sample XML File: Test Configuration (LINQ to XML)](./sample-xml-file-test-configuration-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("TestConfig.xml");  
IEnumerable<XElement> tests =  
    from el in root.Elements("Test")  
    where (string)el.Element("CommandLine") == "Examp2.EXE"  
    select el;  
foreach (XElement el in tests)  
    Console.WriteLine((string)el.Attribute("TestId"));  
```  
  
 <span data-ttu-id="2fad3-107">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="2fad3-107">This code produces the following output:</span></span>  
  
```output  
0002  
0006  
```  
  
## <a name="example"></a><span data-ttu-id="2fad3-108">Пример</span><span class="sxs-lookup"><span data-stu-id="2fad3-108">Example</span></span>  
 <span data-ttu-id="2fad3-109">Следующий пример демонстрирует тот же запрос XML, что и в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="2fad3-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="2fad3-110">Дополнительные сведения см. в статье [Обзор пространств имен DFS (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="2fad3-110">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="2fad3-111">В этом примере используется следующий XML-документ: [Пример XML-файла. Конфигурация тестирования в пространстве имен](./sample-xml-file-test-configuration-in-a-namespace1.md).</span><span class="sxs-lookup"><span data-stu-id="2fad3-111">This example uses the following XML document: [Sample XML File: Test Configuration in a Namespace](./sample-xml-file-test-configuration-in-a-namespace1.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("TestConfigInNamespace.xml");  
XNamespace ad = "http://www.adatum.com";  
IEnumerable<XElement> tests =  
    from el in root.Elements(ad + "Test")  
    where (string)el.Element(ad + "CommandLine") == "Examp2.EXE"  
    select el;  
foreach (XElement el in tests)  
    Console.WriteLine((string)el.Attribute("TestId"));  
```  
  
 <span data-ttu-id="2fad3-112">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="2fad3-112">This code produces the following output:</span></span>  
  
```output  
0002  
0006  
```  
  
## <a name="see-also"></a><span data-ttu-id="2fad3-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2fad3-113">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [<span data-ttu-id="2fad3-114">Общие сведения о стандартных операторах запроса (C#)</span><span class="sxs-lookup"><span data-stu-id="2fad3-114">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="2fad3-115">Операции проекции (C#)</span><span class="sxs-lookup"><span data-stu-id="2fad3-115">Projection Operations (C#)</span></span>](./projection-operations.md)
