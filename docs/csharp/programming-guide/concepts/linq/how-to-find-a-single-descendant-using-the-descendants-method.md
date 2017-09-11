---
title: "Практическое руководство. Поиск одного потомка с помощью метода потомков (C#)"
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
ms.assetid: 6f735be9-0293-4680-8007-ca9d96bfebed
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 89e20ede65caf65e91a37cbee69c80146a1443f0
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-find-a-single-descendant-using-the-descendants-method-c"></a><span data-ttu-id="21ce0-102">Практическое руководство. Поиск одного потомка с помощью метода потомков (C#)</span><span class="sxs-lookup"><span data-stu-id="21ce0-102">How to: Find a Single Descendant Using the Descendants Method (C#)</span></span>
<span data-ttu-id="21ce0-103">Метод оси <xref:System.Xml.Linq.XContainer.Descendants%2A> можно использовать для быстрого написания кода с целью поиска одного уникально именованного элемента.</span><span class="sxs-lookup"><span data-stu-id="21ce0-103">You can use the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis method to quickly write code to find a single uniquely named element.</span></span> <span data-ttu-id="21ce0-104">Этот способ особенно полезен, если нужно найти конкретного потомка с заданным именем.</span><span class="sxs-lookup"><span data-stu-id="21ce0-104">This technique is especially useful when you want to find a particular descendant with a specific name.</span></span> <span data-ttu-id="21ce0-105">Можно написать собственный код для перехода к нужному элементу, но часто быстрей и легче написать такой код с помощью оси <xref:System.Xml.Linq.XContainer.Descendants%2A>.</span><span class="sxs-lookup"><span data-stu-id="21ce0-105">You could write the code to navigate to the desired element, but it is often faster and easier to write the code using the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21ce0-106">Пример</span><span class="sxs-lookup"><span data-stu-id="21ce0-106">Example</span></span>  
 <span data-ttu-id="21ce0-107">В этом примере используется стандартный оператор запроса <xref:System.Linq.Enumerable.First%2A>.</span><span class="sxs-lookup"><span data-stu-id="21ce0-107">This example uses the <xref:System.Linq.Enumerable.First%2A> standard query operator.</span></span>  
  
```csharp  
XElement root = XElement.Parse(@"<Root>  
  <Child1>  
    <GrandChild1>GC1 Value</GrandChild1>  
  </Child1>  
  <Child2>  
    <GrandChild2>GC2 Value</GrandChild2>  
  </Child2>  
  <Child3>  
    <GrandChild3>GC3 Value</GrandChild3>  
  </Child3>  
  <Child4>  
    <GrandChild4>GC4 Value</GrandChild4>  
  </Child4>  
</Root>");  
string grandChild3 = (string)  
    (from el in root.Descendants("GrandChild3")  
    select el).First();  
Console.WriteLine(grandChild3);  
```  
  
 <span data-ttu-id="21ce0-108">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="21ce0-108">This code produces the following output:</span></span>  
  
```  
GC3 Value  
```  
  
## <a name="example"></a><span data-ttu-id="21ce0-109">Пример</span><span class="sxs-lookup"><span data-stu-id="21ce0-109">Example</span></span>  
 <span data-ttu-id="21ce0-110">Следующий пример демонстрирует тот же запрос XML, что и в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="21ce0-110">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="21ce0-111">Дополнительные сведения см. в разделе [Работа с пространствами имен XML (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="21ce0-111">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
```csharp  
XElement root = XElement.Parse(@"<aw:Root xmlns:aw='http://www.adventure-works.com'>  
  <aw:Child1>  
    <aw:GrandChild1>GC1 Value</aw:GrandChild1>  
  </aw:Child1>  
  <aw:Child2>  
    <aw:GrandChild2>GC2 Value</aw:GrandChild2>  
  </aw:Child2>  
  <aw:Child3>  
    <aw:GrandChild3>GC3 Value</aw:GrandChild3>  
  </aw:Child3>  
  <aw:Child4>  
    <aw:GrandChild4>GC4 Value</aw:GrandChild4>  
  </aw:Child4>  
</aw:Root>");  
XNamespace aw = "http://www.adventure-works.com";  
string grandChild3 = (string)  
    (from el in root.Descendants(aw + "GrandChild3")  
     select el).First();  
Console.WriteLine(grandChild3);  
```  
  
 <span data-ttu-id="21ce0-112">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="21ce0-112">This code produces the following output:</span></span>  
  
```  
GC3 Value  
```  
  
## <a name="see-also"></a><span data-ttu-id="21ce0-113">См. также</span><span class="sxs-lookup"><span data-stu-id="21ce0-113">See Also</span></span>  
 [<span data-ttu-id="21ce0-114">Базовые запросы (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="21ce0-114">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)

