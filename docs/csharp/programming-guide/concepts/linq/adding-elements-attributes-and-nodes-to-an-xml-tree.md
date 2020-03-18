---
title: Добавление элементов, атрибутов и узлов в дерево XML (C#)
ms.date: 07/20/2015
ms.assetid: db911e4f-40aa-499a-9500-a9763bb6df56
ms.openlocfilehash: 20d8d9d9c592f5f570d7c94298dcee41763c1f1f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79169579"
---
# <a name="adding-elements-attributes-and-nodes-to-an-xml-tree-c"></a><span data-ttu-id="2d084-102">Добавление элементов, атрибутов и узлов в дерево XML (C#)</span><span class="sxs-lookup"><span data-stu-id="2d084-102">Adding Elements, Attributes, and Nodes to an XML Tree (C#)</span></span>
<span data-ttu-id="2d084-103">Можно добавлять содержимое (элементы, атрибуты, комментарии, инструкции по обработке, текст и CDATA) к существующему XML-дереву.</span><span class="sxs-lookup"><span data-stu-id="2d084-103">You can add content (elements, attributes, comments, processing instructions, text, and CDATA) to an existing XML tree.</span></span>  
  
## <a name="methods-for-adding-content"></a><span data-ttu-id="2d084-104">Методы добавления содержимого</span><span class="sxs-lookup"><span data-stu-id="2d084-104">Methods for Adding Content</span></span>  
 <span data-ttu-id="2d084-105">Следующие методы позволяют добавить дочернее содержимое к <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="2d084-105">The following methods add child content to an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XDocument>:</span></span>  
  
|<span data-ttu-id="2d084-106">Метод</span><span class="sxs-lookup"><span data-stu-id="2d084-106">Method</span></span>|<span data-ttu-id="2d084-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="2d084-107">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.Add%2A>|<span data-ttu-id="2d084-108">Добавляет содержимое в конце дочернего содержимого <xref:System.Xml.Linq.XContainer>.</span><span class="sxs-lookup"><span data-stu-id="2d084-108">Adds content at the end of the child content of the <xref:System.Xml.Linq.XContainer>.</span></span>|  
|<xref:System.Xml.Linq.XContainer.AddFirst%2A>|<span data-ttu-id="2d084-109">Добавляет содержимое в начале дочернего содержимого <xref:System.Xml.Linq.XContainer>.</span><span class="sxs-lookup"><span data-stu-id="2d084-109">Adds content at the beginning of the child content of the <xref:System.Xml.Linq.XContainer>.</span></span>|  
  
 <span data-ttu-id="2d084-110">Следующие методы позволяют добавлять содержимое как одноуровневые узлы для <xref:System.Xml.Linq.XNode>.</span><span class="sxs-lookup"><span data-stu-id="2d084-110">The following methods add content as sibling nodes of an <xref:System.Xml.Linq.XNode>.</span></span> <span data-ttu-id="2d084-111">Самым распространенным узлом, к которому можно добавлять содержимое как одноуровневые узлы, является <xref:System.Xml.Linq.XElement>, хотя можно добавлять содержимое в виде таких узлов и к другим типам узлов, например <xref:System.Xml.Linq.XText> или <xref:System.Xml.Linq.XComment>.</span><span class="sxs-lookup"><span data-stu-id="2d084-111">The most common node to which you add sibling content is <xref:System.Xml.Linq.XElement>, although you can add valid sibling content to other types of nodes such as <xref:System.Xml.Linq.XText> or <xref:System.Xml.Linq.XComment>.</span></span>  
  
|<span data-ttu-id="2d084-112">Метод</span><span class="sxs-lookup"><span data-stu-id="2d084-112">Method</span></span>|<span data-ttu-id="2d084-113">Описание:</span><span class="sxs-lookup"><span data-stu-id="2d084-113">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.AddAfterSelf%2A>|<span data-ttu-id="2d084-114">Добавляет содержимое после <xref:System.Xml.Linq.XNode>.</span><span class="sxs-lookup"><span data-stu-id="2d084-114">Adds content after the <xref:System.Xml.Linq.XNode>.</span></span>|  
|<xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>|<span data-ttu-id="2d084-115">Добавляет содержимое перед <xref:System.Xml.Linq.XNode>.</span><span class="sxs-lookup"><span data-stu-id="2d084-115">Adds content before the <xref:System.Xml.Linq.XNode>.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2d084-116">Пример</span><span class="sxs-lookup"><span data-stu-id="2d084-116">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="2d084-117">Описание:</span><span class="sxs-lookup"><span data-stu-id="2d084-117">Description</span></span>  
 <span data-ttu-id="2d084-118">В следующем примере создаются два XML-дерева, затем выполняется изменение одного из них.</span><span class="sxs-lookup"><span data-stu-id="2d084-118">The following example creates two XML trees, and then modifies one of the trees.</span></span>  
  
### <a name="code"></a><span data-ttu-id="2d084-119">Код</span><span class="sxs-lookup"><span data-stu-id="2d084-119">Code</span></span>  
  
```csharp  
XElement srcTree = new XElement("Root",
    new XElement("Element1", 1),  
    new XElement("Element2", 2),  
    new XElement("Element3", 3),  
    new XElement("Element4", 4),  
    new XElement("Element5", 5)  
);  
XElement xmlTree = new XElement("Root",  
    new XElement("Child1", 1),  
    new XElement("Child2", 2),  
    new XElement("Child3", 3),  
    new XElement("Child4", 4),  
    new XElement("Child5", 5)  
);  
xmlTree.Add(new XElement("NewChild", "new content"));  
xmlTree.Add(  
    from el in srcTree.Elements()  
    where (int)el > 3  
    select el  
);  
// Even though Child9 does not exist in srcTree, the following statement will not  
// throw an exception, and nothing will be added to xmlTree.  
xmlTree.Add(srcTree.Element("Child9"));  
Console.WriteLine(xmlTree);  
```  
  
### <a name="comments"></a><span data-ttu-id="2d084-120">Комментарии</span><span class="sxs-lookup"><span data-stu-id="2d084-120">Comments</span></span>  
 <span data-ttu-id="2d084-121">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="2d084-121">This code produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child1>1</Child1>  
  <Child2>2</Child2>  
  <Child3>3</Child3>  
  <Child4>4</Child4>  
  <Child5>5</Child5>  
  <NewChild>new content</NewChild>  
  <Element4>4</Element4>  
  <Element5>5</Element5>  
</Root>  
```  
  