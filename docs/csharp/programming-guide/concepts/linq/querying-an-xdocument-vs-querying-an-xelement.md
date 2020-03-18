---
title: Сравнение запросов к XML-документам Запросы к XElement (C#)
ms.date: 07/20/2015
ms.assetid: 46221ff5-62ee-4de8-93ba-66465facb5c1
ms.openlocfilehash: 475c77934ad535bad9ef79ff58bbddf991dc8f5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "70253129"
---
# <a name="querying-an-xdocument-vs-querying-an-xelement-c"></a><span data-ttu-id="ab369-102">Сравнение запросов к XML-документам Запросы к XElement (C#)</span><span class="sxs-lookup"><span data-stu-id="ab369-102">Querying an XDocument vs. Querying an XElement (C#)</span></span>
<span data-ttu-id="ab369-103">При загрузке документа через <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> обратите внимание на то, что запросы придется составлять не так, как при загрузке через <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ab369-103">When you load a document via <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>, you will notice that you have to write queries slightly differently than when you load via <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="comparison-of-xdocumentload-and-xelementload"></a><span data-ttu-id="ab369-104">Сравнение XDocument.Load и XElement.Load</span><span class="sxs-lookup"><span data-stu-id="ab369-104">Comparison of XDocument.Load and XElement.Load</span></span>  
 <span data-ttu-id="ab369-105">При загрузке XML-документа в <xref:System.Xml.Linq.XElement> через <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType><xref:System.Xml.Linq.XElement> в корне XML-дерева содержит корневой элемент загруженного документа.</span><span class="sxs-lookup"><span data-stu-id="ab369-105">When you load an XML document into an <xref:System.Xml.Linq.XElement> via <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>, the <xref:System.Xml.Linq.XElement> at the root of the XML tree contains the root element of the loaded document.</span></span> <span data-ttu-id="ab369-106">Однако при загрузке этого же XML-документа в <xref:System.Xml.Linq.XDocument> через <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> корень дерева - это узел <xref:System.Xml.Linq.XDocument>, а элемент корня загруженного документа - это один разрешенный дочерний узел <xref:System.Xml.Linq.XElement><xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="ab369-106">However, when you load the same XML document into an <xref:System.Xml.Linq.XDocument> via <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>, the root of the tree is an <xref:System.Xml.Linq.XDocument> node, and the root element of the loaded document is the one allowed child <xref:System.Xml.Linq.XElement> node of the <xref:System.Xml.Linq.XDocument>.</span></span> <span data-ttu-id="ab369-107">Оси [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] работают в зависимости от корневого узла.</span><span class="sxs-lookup"><span data-stu-id="ab369-107">The [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] axes operate relative to the root node.</span></span>  
  
 <span data-ttu-id="ab369-108">В этом первом примере выполняется загрузка XML-дерева при помощи <xref:System.Xml.Linq.XElement.Load%2A>.</span><span class="sxs-lookup"><span data-stu-id="ab369-108">This first example loads an XML tree using <xref:System.Xml.Linq.XElement.Load%2A>.</span></span> <span data-ttu-id="ab369-109">Затем выполняется запрос по дочерним элементам корня дерева.</span><span class="sxs-lookup"><span data-stu-id="ab369-109">It then queries for the child elements of the root of the tree.</span></span>  
  
```csharp  
// Create a simple document and write it to a file  
File.WriteAllText("Test.xml", @"<Root>  
    <Child1>1</Child1>  
    <Child2>2</Child2>  
    <Child3>3</Child3>  
</Root>");  
  
Console.WriteLine("Querying tree loaded with XElement.Load");  
Console.WriteLine("----");  
XElement doc = XElement.Load("Test.xml");  
IEnumerable<XElement> childList =  
    from el in doc.Elements()  
    select el;  
foreach (XElement e in childList)  
    Console.WriteLine(e);  
```  
  
 <span data-ttu-id="ab369-110">Как и ожидается, выполняется вывод следующих данных:</span><span class="sxs-lookup"><span data-stu-id="ab369-110">As expected, this example produces the following output:</span></span>  
  
```output  
Querying tree loaded with XElement.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
 <span data-ttu-id="ab369-111">Следующий пример такой же, как и пример выше, за исключением того, что XML-дерево загружается в <xref:System.Xml.Linq.XDocument>, а не в <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="ab369-111">The following example is the same as the one above, with the exception that the XML tree is loaded into an <xref:System.Xml.Linq.XDocument> instead of an <xref:System.Xml.Linq.XElement>.</span></span>  
  
```csharp  
// Create a simple document and write it to a file  
File.WriteAllText("Test.xml", @"<Root>  
    <Child1>1</Child1>  
    <Child2>2</Child2>  
    <Child3>3</Child3>  
</Root>");  
  
Console.WriteLine("Querying tree loaded with XDocument.Load");  
Console.WriteLine("----");  
XDocument doc = XDocument.Load("Test.xml");  
IEnumerable<XElement> childList =  
    from el in doc.Elements()  
    select el;  
foreach (XElement e in childList)  
    Console.WriteLine(e);  
```  
  
 <span data-ttu-id="ab369-112">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="ab369-112">This example produces the following output:</span></span>  
  
```output  
Querying tree loaded with XDocument.Load  
----  
<Root>  
  <Child1>1</Child1>  
  <Child2>2</Child2>  
  <Child3>3</Child3>  
</Root>  
```  
  
 <span data-ttu-id="ab369-113">Обратите внимание, что при таком же запросе выводится только узел `Root`, а не три дочерних узла.</span><span class="sxs-lookup"><span data-stu-id="ab369-113">Notice that the same query returned the one `Root` node instead of the three child nodes.</span></span>  
  
 <span data-ttu-id="ab369-114">Одним из подходов при этом может быть использование свойства <xref:System.Xml.Linq.XDocument.Root%2A> перед доступом к методам оси:</span><span class="sxs-lookup"><span data-stu-id="ab369-114">One approach to dealing with this is to use the <xref:System.Xml.Linq.XDocument.Root%2A> property before accessing the axes methods, as follows:</span></span>  
  
```csharp  
// Create a simple document and write it to a file  
File.WriteAllText("Test.xml", @"<Root>  
    <Child1>1</Child1>  
    <Child2>2</Child2>  
    <Child3>3</Child3>  
</Root>");  
  
Console.WriteLine("Querying tree loaded with XDocument.Load");  
Console.WriteLine("----");  
XDocument doc = XDocument.Load("Test.xml");  
IEnumerable<XElement> childList =  
    from el in doc.Root.Elements()  
    select el;  
foreach (XElement e in childList)  
    Console.WriteLine(e);  
```  
  
 <span data-ttu-id="ab369-115">Теперь на этот запрос выводятся те же результаты, что и при запросе по дереву, корень которого размещен в <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="ab369-115">This query now performs in the same way as the query on the tree rooted in <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="ab369-116">Пример выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="ab369-116">The example produces the following output:</span></span>  
  
```output  
Querying tree loaded with XDocument.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  