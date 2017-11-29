---
title: "Удаление элементов, атрибутов и узлов из XML-дерева (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5cf21919-4360-4b49-b29d-58ea3164ac72
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c1662f0cd1461cc00a8859464b8da3ecb8fd9faf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="removing-elements-attributes-and-nodes-from-an-xml-tree-visual-basic"></a><span data-ttu-id="e0603-102">Удаление элементов, атрибутов и узлов из XML-дерева (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0603-102">Removing Elements, Attributes, and Nodes from an XML Tree (Visual Basic)</span></span>
<span data-ttu-id="e0603-103">Можно вносить изменения в XML-дерево, удаляя элементы, атрибуты и узлы других типов.</span><span class="sxs-lookup"><span data-stu-id="e0603-103">You can modify an XML tree, removing elements, attributes, and other types of nodes.</span></span>  
  
 <span data-ttu-id="e0603-104">Удаление одного элемента или атрибута из XML-документа является простой операцией.</span><span class="sxs-lookup"><span data-stu-id="e0603-104">Removing a single element or a single attribute from an XML document is straightforward.</span></span> <span data-ttu-id="e0603-105">Но при удалении коллекций элементов или атрибутов необходимо вначале материализовать коллекцию в список, а затем удалить элементы или атрибуты из списка.</span><span class="sxs-lookup"><span data-stu-id="e0603-105">However, when removing collections of elements or attributes, you should first materialize a collection into a list, and then delete the elements or attributes from the list.</span></span> <span data-ttu-id="e0603-106">Наилучшим подходом является использование метода расширения <xref:System.Xml.Linq.Extensions.Remove%2A>, позволяющего выполнить эту задачу.</span><span class="sxs-lookup"><span data-stu-id="e0603-106">The best approach is to use the <xref:System.Xml.Linq.Extensions.Remove%2A> extension method, which will do this for you.</span></span>  
  
 <span data-ttu-id="e0603-107">Основной причиной этого является то, что большинство коллекций, получаемых из XML-дерева, формируется с помощью отложенного выполнения.</span><span class="sxs-lookup"><span data-stu-id="e0603-107">The main reason for doing this is that most of the collections you retrieve from an XML tree are yielded using deferred execution.</span></span> <span data-ttu-id="e0603-108">Если не проводится их предварительная материализация в список или не используются методы расширения, то становится возможным возникновение определенного класса ошибок.</span><span class="sxs-lookup"><span data-stu-id="e0603-108">If you do not first materialize them into a list, or if you do not use the extension methods, it is possible to encounter a certain class of bugs.</span></span> <span data-ttu-id="e0603-109">Дополнительные сведения см. в разделе [смешанного декларативного и императивного ошибки в коде (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/mixed-declarative-code-imperative-code-bugs-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="e0603-109">For more information, see [Mixed Declarative Code/Imperative Code Bugs (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/mixed-declarative-code-imperative-code-bugs-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="e0603-110">Следующие методы позволяют удалять узлы и атрибуты из XML-дерева.</span><span class="sxs-lookup"><span data-stu-id="e0603-110">The following methods remove nodes and attributes from an XML tree.</span></span>  
  
|<span data-ttu-id="e0603-111">Метод</span><span class="sxs-lookup"><span data-stu-id="e0603-111">Method</span></span>|<span data-ttu-id="e0603-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e0603-112">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Remove%2A?displayProperty=nameWithType>|<span data-ttu-id="e0603-113">Удаляет <xref:System.Xml.Linq.XAttribute> из его родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="e0603-113">Removes an <xref:System.Xml.Linq.XAttribute> from its parent.</span></span>|  
|<xref:System.Xml.Linq.XContainer.RemoveNodes%2A?displayProperty=nameWithType>|<span data-ttu-id="e0603-114">Удаляет дочерние узлы из <xref:System.Xml.Linq.XContainer>.</span><span class="sxs-lookup"><span data-stu-id="e0603-114">Removes the child nodes from an <xref:System.Xml.Linq.XContainer>.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=nameWithType>|<span data-ttu-id="e0603-115">Удаляет содержимое и атрибуты из <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="e0603-115">Removes content and attributes from an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="e0603-116">Удаляет атрибуты <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="e0603-116">Removes the attributes of an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=nameWithType>|<span data-ttu-id="e0603-117">Передача `null` в качестве значения приводит к удалению атрибута.</span><span class="sxs-lookup"><span data-stu-id="e0603-117">If you pass `null` for value, then removes the attribute.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=nameWithType>|<span data-ttu-id="e0603-118">Передача `null` в качестве значения приводит к удалению дочернего элемента.</span><span class="sxs-lookup"><span data-stu-id="e0603-118">If you pass `null` for value, then removes the child element.</span></span>|  
|<xref:System.Xml.Linq.XNode.Remove%2A?displayProperty=nameWithType>|<span data-ttu-id="e0603-119">Удаляет <xref:System.Xml.Linq.XNode> из его родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="e0603-119">Removes an <xref:System.Xml.Linq.XNode> from its parent.</span></span>|  
|<xref:System.Xml.Linq.Extensions.Remove%2A?displayProperty=nameWithType>|<span data-ttu-id="e0603-120">Удаляет каждый атрибут или элемент исходной коллекции из своего родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="e0603-120">Removes every attribute or element in the source collection from its parent element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e0603-121">Пример</span><span class="sxs-lookup"><span data-stu-id="e0603-121">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="e0603-122">Описание</span><span class="sxs-lookup"><span data-stu-id="e0603-122">Description</span></span>  
 <span data-ttu-id="e0603-123">В этом примере показано три подхода к удалению элементов.</span><span class="sxs-lookup"><span data-stu-id="e0603-123">This example demonstrates three approaches to removing elements.</span></span> <span data-ttu-id="e0603-124">Сначала удаляется одиночный элемент.</span><span class="sxs-lookup"><span data-stu-id="e0603-124">First, it removes a single element.</span></span> <span data-ttu-id="e0603-125">Затем он возвращает коллекцию элементов, материализует их с помощью оператора <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> и удаляет коллекцию.</span><span class="sxs-lookup"><span data-stu-id="e0603-125">Second, it retrieves a collection of elements, materializes them using the <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> operator, and removes the collection.</span></span> <span data-ttu-id="e0603-126">Наконец, он получает коллекцию элементов и удаляет их с помощью метода расширения <xref:System.Xml.Linq.Extensions.Remove%2A>.</span><span class="sxs-lookup"><span data-stu-id="e0603-126">Finally, it retrieves a collection of elements and removes them using the <xref:System.Xml.Linq.Extensions.Remove%2A> extension method.</span></span>  
  
 <span data-ttu-id="e0603-127">Дополнительные сведения о <xref:System.Linq.Enumerable.ToList%2A> оператор, в разделе [преобразование типов данных (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/converting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="e0603-127">For more information on the <xref:System.Linq.Enumerable.ToList%2A> operator, see [Converting Data Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/converting-data-types.md).</span></span>  
  
### <a name="code"></a><span data-ttu-id="e0603-128">Код</span><span class="sxs-lookup"><span data-stu-id="e0603-128">Code</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <Child1>  
            <GrandChild1/>  
            <GrandChild2/>  
            <GrandChild3/>  
        </Child1>  
        <Child2>  
            <GrandChild4/>  
            <GrandChild5/>  
            <GrandChild6/>  
        </Child2>  
        <Child3>  
            <GrandChild7/>  
            <GrandChild8/>  
            <GrandChild9/>  
        </Child3>  
    </Root>  
root.<Child1>.<GrandChild1>.Remove()  
root.<Child2>.Elements().ToList().Remove()  
root.<Child3>.Elements().Remove()  
Console.WriteLine(root)  
```  
  
### <a name="comments"></a><span data-ttu-id="e0603-129">Комментарии</span><span class="sxs-lookup"><span data-stu-id="e0603-129">Comments</span></span>  
 <span data-ttu-id="e0603-130">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="e0603-130">This code produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child1>  
    <GrandChild2 />  
    <GrandChild3 />  
  </Child1>  
  <Child2 />  
  <Child3 />  
</Root>  
```  
  
 <span data-ttu-id="e0603-131">Обратите внимание, что первый внучатый элемент был удален из `Child1`.</span><span class="sxs-lookup"><span data-stu-id="e0603-131">Notice that the first grandchild element has been removed from `Child1`.</span></span> <span data-ttu-id="e0603-132">Все внучатые элементы были удалены из `Child2` и `Child3`.</span><span class="sxs-lookup"><span data-stu-id="e0603-132">All grandchildren elements have been removed from `Child2` and from `Child3`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0603-133">См. также</span><span class="sxs-lookup"><span data-stu-id="e0603-133">See Also</span></span>  
 [<span data-ttu-id="e0603-134">Изменение деревьев XML (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0603-134">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
