---
title: "Удаление элементов, атрибутов и узлов из XML-дерева (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 5cf21919-4360-4b49-b29d-58ea3164ac72
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 8842858080ce1f27d997e6af61a8dd2301cdc2bc
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017


---
# <a name="removing-elements-attributes-and-nodes-from-an-xml-tree-visual-basic"></a><span data-ttu-id="95e56-102">Удаление элементов, атрибутов и узлов из XML-дерева (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="95e56-102">Removing Elements, Attributes, and Nodes from an XML Tree (Visual Basic)</span></span>
<span data-ttu-id="95e56-103">Можно вносить изменения в XML-дерево, удаляя элементы, атрибуты и узлы других типов.</span><span class="sxs-lookup"><span data-stu-id="95e56-103">You can modify an XML tree, removing elements, attributes, and other types of nodes.</span></span>  
  
 <span data-ttu-id="95e56-104">Удаление одного элемента или атрибута из XML-документа является простой операцией.</span><span class="sxs-lookup"><span data-stu-id="95e56-104">Removing a single element or a single attribute from an XML document is straightforward.</span></span> <span data-ttu-id="95e56-105">Но при удалении коллекций элементов или атрибутов необходимо вначале материализовать коллекцию в список, а затем удалить элементы или атрибуты из списка.</span><span class="sxs-lookup"><span data-stu-id="95e56-105">However, when removing collections of elements or attributes, you should first materialize a collection into a list, and then delete the elements or attributes from the list.</span></span> <span data-ttu-id="95e56-106">Лучше всего использовать <xref:System.Xml.Linq.Extensions.Remove%2A>метод расширения, который сделает это за вас.</xref:System.Xml.Linq.Extensions.Remove%2A></span><span class="sxs-lookup"><span data-stu-id="95e56-106">The best approach is to use the <xref:System.Xml.Linq.Extensions.Remove%2A> extension method, which will do this for you.</span></span>  
  
 <span data-ttu-id="95e56-107">Основной причиной этого является то, что большинство коллекций, получаемых из XML-дерева, формируется с помощью отложенного выполнения.</span><span class="sxs-lookup"><span data-stu-id="95e56-107">The main reason for doing this is that most of the collections you retrieve from an XML tree are yielded using deferred execution.</span></span> <span data-ttu-id="95e56-108">Если не проводится их предварительная материализация в список или не используются методы расширения, то становится возможным возникновение определенного класса ошибок.</span><span class="sxs-lookup"><span data-stu-id="95e56-108">If you do not first materialize them into a list, or if you do not use the extension methods, it is possible to encounter a certain class of bugs.</span></span> <span data-ttu-id="95e56-109">Дополнительные сведения см. в разделе [смешанного декларативного и императивного ошибки в коде (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/mixed-declarative-code-imperative-code-bugs-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="95e56-109">For more information, see [Mixed Declarative Code/Imperative Code Bugs (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/mixed-declarative-code-imperative-code-bugs-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="95e56-110">Следующие методы позволяют удалять узлы и атрибуты из XML-дерева.</span><span class="sxs-lookup"><span data-stu-id="95e56-110">The following methods remove nodes and attributes from an XML tree.</span></span>  
  
|<span data-ttu-id="95e56-111">Метод</span><span class="sxs-lookup"><span data-stu-id="95e56-111">Method</span></span>|<span data-ttu-id="95e56-112">Описание</span><span class="sxs-lookup"><span data-stu-id="95e56-112">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="95e56-113">[XAttribute.Remove](https://msdn.microsoft.com/library/system.xml.linq.xattribute.remove\(v=vs.110\).aspx)</span><span class="sxs-lookup"><span data-stu-id="95e56-113">[XAttribute.Remove](https://msdn.microsoft.com/library/system.xml.linq.xattribute.remove\(v=vs.110\).aspx)</span></span>|<span data-ttu-id="95e56-114">Удаляет <xref:System.Xml.Linq.XAttribute>от родительского.</xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="95e56-114">Removes an <xref:System.Xml.Linq.XAttribute> from its parent.</span></span>|  
|<span data-ttu-id="95e56-115">[XContainer.RemoveNodes](https://msdn.microsoft.com/library/system.xml.linq.xcontainer.removenodes\(v=vs.110\).aspx)</span><span class="sxs-lookup"><span data-stu-id="95e56-115">[XContainer.RemoveNodes](https://msdn.microsoft.com/library/system.xml.linq.xcontainer.removenodes\(v=vs.110\).aspx)</span></span>|<span data-ttu-id="95e56-116">Удаляет дочерние узлы из <xref:System.Xml.Linq.XContainer>.</xref:System.Xml.Linq.XContainer></span><span class="sxs-lookup"><span data-stu-id="95e56-116">Removes the child nodes from an <xref:System.Xml.Linq.XContainer>.</span></span>|  
|<span data-ttu-id="95e56-117"><xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="95e56-117"><xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=fullName></span></span>|<span data-ttu-id="95e56-118">Удаляет содержимое и атрибуты из <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="95e56-118">Removes content and attributes from an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<span data-ttu-id="95e56-119"><xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="95e56-119"><xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=fullName></span></span>|<span data-ttu-id="95e56-120">Удаляет атрибуты <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="95e56-120">Removes the attributes of an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<span data-ttu-id="95e56-121"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="95e56-121"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=fullName></span></span>|<span data-ttu-id="95e56-122">Передача `null` в качестве значения приводит к удалению атрибута.</span><span class="sxs-lookup"><span data-stu-id="95e56-122">If you pass `null` for value, then removes the attribute.</span></span>|  
|<span data-ttu-id="95e56-123"><xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="95e56-123"><xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=fullName></span></span>|<span data-ttu-id="95e56-124">Передача `null` в качестве значения приводит к удалению дочернего элемента.</span><span class="sxs-lookup"><span data-stu-id="95e56-124">If you pass `null` for value, then removes the child element.</span></span>|  
|<span data-ttu-id="95e56-125"><xref:System.Xml.Linq.XNode.Remove%2A?displayProperty=fullName></xref:System.Xml.Linq.XNode.Remove%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="95e56-125"><xref:System.Xml.Linq.XNode.Remove%2A?displayProperty=fullName></span></span>|<span data-ttu-id="95e56-126">Удаляет <xref:System.Xml.Linq.XNode>от родительского.</xref:System.Xml.Linq.XNode></span><span class="sxs-lookup"><span data-stu-id="95e56-126">Removes an <xref:System.Xml.Linq.XNode> from its parent.</span></span>|  
|<span data-ttu-id="95e56-127"><xref:System.Xml.Linq.Extensions.Remove%2A?displayProperty=fullName></xref:System.Xml.Linq.Extensions.Remove%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="95e56-127"><xref:System.Xml.Linq.Extensions.Remove%2A?displayProperty=fullName></span></span>|<span data-ttu-id="95e56-128">Удаляет каждый атрибут или элемент исходной коллекции из своего родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="95e56-128">Removes every attribute or element in the source collection from its parent element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="95e56-129">Пример</span><span class="sxs-lookup"><span data-stu-id="95e56-129">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="95e56-130">Описание</span><span class="sxs-lookup"><span data-stu-id="95e56-130">Description</span></span>  
 <span data-ttu-id="95e56-131">В этом примере показано три подхода к удалению элементов.</span><span class="sxs-lookup"><span data-stu-id="95e56-131">This example demonstrates three approaches to removing elements.</span></span> <span data-ttu-id="95e56-132">Сначала удаляется одиночный элемент.</span><span class="sxs-lookup"><span data-stu-id="95e56-132">First, it removes a single element.</span></span> <span data-ttu-id="95e56-133">Во-вторых, он возвращает коллекцию элементов, материализует их с помощью <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName>оператор и удаляет коллекцию.</xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="95e56-133">Second, it retrieves a collection of elements, materializes them using the <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName> operator, and removes the collection.</span></span> <span data-ttu-id="95e56-134">Наконец, он возвращает коллекцию элементов и удаляет их с помощью <xref:System.Xml.Linq.Extensions.Remove%2A>метода расширения.</xref:System.Xml.Linq.Extensions.Remove%2A></span><span class="sxs-lookup"><span data-stu-id="95e56-134">Finally, it retrieves a collection of elements and removes them using the <xref:System.Xml.Linq.Extensions.Remove%2A> extension method.</span></span>  
  
 <span data-ttu-id="95e56-135">Дополнительные сведения о <xref:System.Linq.Enumerable.ToList%2A>оператор, в разделе [преобразование типов данных (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/converting-data-types.md).</xref:System.Linq.Enumerable.ToList%2A></span><span class="sxs-lookup"><span data-stu-id="95e56-135">For more information on the <xref:System.Linq.Enumerable.ToList%2A> operator, see [Converting Data Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/converting-data-types.md).</span></span>  
  
### <a name="code"></a><span data-ttu-id="95e56-136">Код</span><span class="sxs-lookup"><span data-stu-id="95e56-136">Code</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="95e56-137">Комментарии</span><span class="sxs-lookup"><span data-stu-id="95e56-137">Comments</span></span>  
 <span data-ttu-id="95e56-138">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="95e56-138">This code produces the following output:</span></span>  
  
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
  
 <span data-ttu-id="95e56-139">Обратите внимание, что первый внучатый элемент был удален из `Child1`.</span><span class="sxs-lookup"><span data-stu-id="95e56-139">Notice that the first grandchild element has been removed from `Child1`.</span></span> <span data-ttu-id="95e56-140">Все внучатые элементы были удалены из `Child2` и `Child3`.</span><span class="sxs-lookup"><span data-stu-id="95e56-140">All grandchildren elements have been removed from `Child2` and from `Child3`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95e56-141">См. также</span><span class="sxs-lookup"><span data-stu-id="95e56-141">See Also</span></span>  
 [<span data-ttu-id="95e56-142">Изменение деревьев XML (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="95e56-142">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
