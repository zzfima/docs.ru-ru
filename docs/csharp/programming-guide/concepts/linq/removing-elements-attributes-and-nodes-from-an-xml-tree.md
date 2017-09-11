---
title: "Удаление элементов, атрибутов и узлов из дерева XML (C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 07dd06d6-1117-4077-bf98-9120cf51176e
caps.latest.revision: 4
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 75642ff3beb4462faa9068db76c89f3cb5f75ab8
ms.openlocfilehash: 40be8959c731746df9392e3cbf29c88fce222b0b
ms.contentlocale: ru-ru
ms.lasthandoff: 08/10/2017

---
# <a name="removing-elements-attributes-and-nodes-from-an-xml-tree-c"></a><span data-ttu-id="cb0d5-102">Удаление элементов, атрибутов и узлов из дерева XML (C#)</span><span class="sxs-lookup"><span data-stu-id="cb0d5-102">Removing Elements, Attributes, and Nodes from an XML Tree (C#)</span></span>
<span data-ttu-id="cb0d5-103">Можно вносить изменения в XML-дерево, удаляя элементы, атрибуты и узлы других типов.</span><span class="sxs-lookup"><span data-stu-id="cb0d5-103">You can modify an XML tree, removing elements, attributes, and other types of nodes.</span></span>  
  
 <span data-ttu-id="cb0d5-104">Удаление одного элемента или атрибута из XML-документа является простой операцией.</span><span class="sxs-lookup"><span data-stu-id="cb0d5-104">Removing a single element or a single attribute from an XML document is straightforward.</span></span> <span data-ttu-id="cb0d5-105">Но при удалении коллекций элементов или атрибутов необходимо вначале материализовать коллекцию в список, а затем удалить элементы или атрибуты из списка.</span><span class="sxs-lookup"><span data-stu-id="cb0d5-105">However, when removing collections of elements or attributes, you should first materialize a collection into a list, and then delete the elements or attributes from the list.</span></span> <span data-ttu-id="cb0d5-106">Наилучшим подходом является использование метода расширения <xref:System.Xml.Linq.Extensions.Remove%2A>, позволяющего выполнить эту задачу.</span><span class="sxs-lookup"><span data-stu-id="cb0d5-106">The best approach is to use the <xref:System.Xml.Linq.Extensions.Remove%2A> extension method, which will do this for you.</span></span>  
  
 <span data-ttu-id="cb0d5-107">Основной причиной этого является то, что большинство коллекций, получаемых из XML-дерева, формируется с помощью отложенного выполнения.</span><span class="sxs-lookup"><span data-stu-id="cb0d5-107">The main reason for doing this is that most of the collections you retrieve from an XML tree are yielded using deferred execution.</span></span> <span data-ttu-id="cb0d5-108">Если не проводится их предварительная материализация в список или не используются методы расширения, то становится возможным возникновение определенного класса ошибок.</span><span class="sxs-lookup"><span data-stu-id="cb0d5-108">If you do not first materialize them into a list, or if you do not use the extension methods, it is possible to encounter a certain class of bugs.</span></span> <span data-ttu-id="cb0d5-109">Дополнительные сведения см. в разделе [Ошибки смешанного декларативного и императивного кода (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/mixed-declarative-code-imperative-code-bugs-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="cb0d5-109">For more information, see [Mixed Declarative Code/Imperative Code Bugs (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/mixed-declarative-code-imperative-code-bugs-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="cb0d5-110">Следующие методы позволяют удалять узлы и атрибуты из XML-дерева.</span><span class="sxs-lookup"><span data-stu-id="cb0d5-110">The following methods remove nodes and attributes from an XML tree.</span></span>  
  
|<span data-ttu-id="cb0d5-111">Метод</span><span class="sxs-lookup"><span data-stu-id="cb0d5-111">Method</span></span>|<span data-ttu-id="cb0d5-112">Описание</span><span class="sxs-lookup"><span data-stu-id="cb0d5-112">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Remove%2A?displayProperty=fullName>|<span data-ttu-id="cb0d5-113">Удаляет <xref:System.Xml.Linq.XAttribute> из его родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="cb0d5-113">Removes an <xref:System.Xml.Linq.XAttribute> from its parent.</span></span>|  
|<xref:System.Xml.Linq.XContainer.RemoveNodes%2A?displayProperty=fullName>|<span data-ttu-id="cb0d5-114">Удаляет дочерние узлы из <xref:System.Xml.Linq.XContainer>.</span><span class="sxs-lookup"><span data-stu-id="cb0d5-114">Removes the child nodes from an <xref:System.Xml.Linq.XContainer>.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=fullName>|<span data-ttu-id="cb0d5-115">Удаляет содержимое и атрибуты из <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="cb0d5-115">Removes content and attributes from an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=fullName>|<span data-ttu-id="cb0d5-116">Удаляет атрибуты <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="cb0d5-116">Removes the attributes of an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=fullName>|<span data-ttu-id="cb0d5-117">Передача `null` в качестве значения приводит к удалению атрибута.</span><span class="sxs-lookup"><span data-stu-id="cb0d5-117">If you pass `null` for value, then removes the attribute.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=fullName>|<span data-ttu-id="cb0d5-118">Передача `null` в качестве значения приводит к удалению дочернего элемента.</span><span class="sxs-lookup"><span data-stu-id="cb0d5-118">If you pass `null` for value, then removes the child element.</span></span>|  
|<xref:System.Xml.Linq.XNode.Remove%2A?displayProperty=fullName>|<span data-ttu-id="cb0d5-119">Удаляет <xref:System.Xml.Linq.XNode> из его родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="cb0d5-119">Removes an <xref:System.Xml.Linq.XNode> from its parent.</span></span>|  
|<xref:System.Xml.Linq.Extensions.Remove%2A?displayProperty=fullName>|<span data-ttu-id="cb0d5-120">Удаляет каждый атрибут или элемент исходной коллекции из своего родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="cb0d5-120">Removes every attribute or element in the source collection from its parent element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="cb0d5-121">Пример</span><span class="sxs-lookup"><span data-stu-id="cb0d5-121">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="cb0d5-122">Описание</span><span class="sxs-lookup"><span data-stu-id="cb0d5-122">Description</span></span>  
 <span data-ttu-id="cb0d5-123">В этом примере показано три подхода к удалению элементов.</span><span class="sxs-lookup"><span data-stu-id="cb0d5-123">This example demonstrates three approaches to removing elements.</span></span> <span data-ttu-id="cb0d5-124">Сначала удаляется одиночный элемент.</span><span class="sxs-lookup"><span data-stu-id="cb0d5-124">First, it removes a single element.</span></span> <span data-ttu-id="cb0d5-125">Затем он возвращает коллекцию элементов, материализует их с помощью оператора <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName> и удаляет коллекцию.</span><span class="sxs-lookup"><span data-stu-id="cb0d5-125">Second, it retrieves a collection of elements, materializes them using the <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName> operator, and removes the collection.</span></span> <span data-ttu-id="cb0d5-126">Наконец, он получает коллекцию элементов и удаляет их с помощью метода расширения <xref:System.Xml.Linq.Extensions.Remove%2A>.</span><span class="sxs-lookup"><span data-stu-id="cb0d5-126">Finally, it retrieves a collection of elements and removes them using the <xref:System.Xml.Linq.Extensions.Remove%2A> extension method.</span></span>  
  
 <span data-ttu-id="cb0d5-127">Дополнительные сведения об операторе <xref:System.Linq.Enumerable.ToList%2A> см. в разделе [Преобразование типов данных (C#)](../../../../csharp/programming-guide/concepts/linq/converting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="cb0d5-127">For more information on the <xref:System.Linq.Enumerable.ToList%2A> operator, see [Converting Data Types (C#)](../../../../csharp/programming-guide/concepts/linq/converting-data-types.md).</span></span>  
  
### <a name="code"></a><span data-ttu-id="cb0d5-128">Код</span><span class="sxs-lookup"><span data-stu-id="cb0d5-128">Code</span></span>  
  
```csharp  
XElement root = XElement.Parse(@"<Root>  
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
</Root>");  
root.Element("Child1").Element("GrandChild1").Remove();  
root.Element("Child2").Elements().ToList().Remove();  
root.Element("Child3").Elements().Remove();  
Console.WriteLine(root);  
```  
  
### <a name="comments"></a><span data-ttu-id="cb0d5-129">Комментарии</span><span class="sxs-lookup"><span data-stu-id="cb0d5-129">Comments</span></span>  
 <span data-ttu-id="cb0d5-130">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="cb0d5-130">This code produces the following output:</span></span>  
  
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
  
 <span data-ttu-id="cb0d5-131">Обратите внимание, что первый внучатый элемент был удален из `Child1`.</span><span class="sxs-lookup"><span data-stu-id="cb0d5-131">Notice that the first grandchild element has been removed from `Child1`.</span></span> <span data-ttu-id="cb0d5-132">Все внучатые элементы были удалены из `Child2` и `Child3`.</span><span class="sxs-lookup"><span data-stu-id="cb0d5-132">All grandchildren elements have been removed from `Child2` and from `Child3`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb0d5-133">См. также</span><span class="sxs-lookup"><span data-stu-id="cb0d5-133">See Also</span></span>  
 [<span data-ttu-id="cb0d5-134">Изменение деревьев XML (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="cb0d5-134">Modifying XML Trees (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)

