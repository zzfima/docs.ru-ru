---
title: Практическое руководство. Изменение пространства имен для всего дерева XML
ms.date: 07/20/2015
ms.assetid: 1837324b-5cb5-4fa8-95b9-3071efa0f913
ms.openlocfilehash: 37edb426b106d3fbf90ea06118526abab0a78bf8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346929"
---
# <a name="how-to-change-the-namespace-for-an-entire-xml-tree-visual-basic"></a><span data-ttu-id="3a83f-102">Как изменить пространство имен для всего дерева XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3a83f-102">How to: Change the Namespace for an Entire XML Tree (Visual Basic)</span></span>
<span data-ttu-id="3a83f-103">Иногда необходимо программно изменить пространство имен для элемента или атрибута.</span><span class="sxs-lookup"><span data-stu-id="3a83f-103">You sometimes have to programmatically change the namespace for an element or an attribute.</span></span> <span data-ttu-id="3a83f-104">В LINQ to XML это делается легко.</span><span class="sxs-lookup"><span data-stu-id="3a83f-104">LINQ to XML makes this easy.</span></span> <span data-ttu-id="3a83f-105">Можно установить свойство <xref:System.Xml.Linq.XElement.Name%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3a83f-105">The <xref:System.Xml.Linq.XElement.Name%2A?displayProperty=nameWithType> property can be set.</span></span> <span data-ttu-id="3a83f-106">Свойство <xref:System.Xml.Linq.XAttribute.Name%2A?displayProperty=nameWithType> не может быть установлено, но можно легко скопировать атрибуты в объект <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>, заменив существующие атрибуты, а затем добавить новые атрибуты из нового пространства имен.</span><span class="sxs-lookup"><span data-stu-id="3a83f-106">The <xref:System.Xml.Linq.XAttribute.Name%2A?displayProperty=nameWithType> property cannot be set, but you can easily copy the attributes into a <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>, remove the existing attributes, and then add new attributes that are in the new desired namespace.</span></span>  
  
 <span data-ttu-id="3a83f-107">Дополнительные сведения см. в разделе [Общие сведения о пространствах имен (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="3a83f-107">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a83f-108">Пример</span><span class="sxs-lookup"><span data-stu-id="3a83f-108">Example</span></span>  
 <span data-ttu-id="3a83f-109">Следующий код создает два XML-дерева без пространства имен.</span><span class="sxs-lookup"><span data-stu-id="3a83f-109">The following code creates two XML trees in no namespace.</span></span> <span data-ttu-id="3a83f-110">Затем он изменяет пространства имен каждого дерева и объединяет их в одно дерево.</span><span class="sxs-lookup"><span data-stu-id="3a83f-110">It then changes the namespace of each of the trees, and combines them into a single tree.</span></span>  
  
```vb  
Dim tree1 As XElement = _  
    <Data>  
        <Child MyAttr="content">content</Child>  
    </Data>  
Dim tree2 As XElement = _  
    <Data>  
        <Child MyAttr="content">content</Child>  
    </Data>  
Dim aw As XNamespace = "http://www.adventure-works.com"  
Dim ad As XNamespace = "http://www.adatum.com"  
' change the namespace of every element and attribute in the first tree  
For Each el As XElement In tree1.DescendantsAndSelf  
    el.Name = aw.GetName(el.Name.LocalName)  
    Dim atList As List(Of XAttribute) = el.Attributes().ToList()  
    el.Attributes().Remove()  
    For Each at As XAttribute In atList  
        el.Add(New XAttribute(aw.GetName(at.Name.LocalName), at.Value))  
    Next  
Next  
' change the namespace of every element and attribute in the second tree  
For Each el As XElement In tree2.DescendantsAndSelf()  
    el.Name = ad.GetName(el.Name.LocalName)  
    Dim atList As List(Of XAttribute) = el.Attributes().ToList()  
    el.Attributes().Remove()  
    For Each at As XAttribute In atList  
        el.Add(New XAttribute(ad.GetName(at.Name.LocalName), at.Value))  
    Next  
Next  
' add attribute namespaces so that the tree will be serialized with  
' the aw and ad namespace prefixes  
tree1.Add( _  
    New XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com") _  
)  
tree2.Add( _  
    New XAttribute(XNamespace.Xmlns + "ad", "http://www.adatum.com") _  
)  
' create a new composite tree  
Dim root As XElement = _  
    <Root>  
        <%= tree1 %>  
        <%= tree2 %>  
    </Root>  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="3a83f-111">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="3a83f-111">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <aw:Data xmlns:aw="http://www.adventure-works.com">  
    <aw:Child aw:MyAttr="content">content</aw:Child>  
  </aw:Data>  
  <ad:Data xmlns:ad="http://www.adatum.com">  
    <ad:Child ad:MyAttr="content">content</ad:Child>  
  </ad:Data>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3a83f-112">См. также</span><span class="sxs-lookup"><span data-stu-id="3a83f-112">See also</span></span>

- [<span data-ttu-id="3a83f-113">Изменение деревьев XML (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3a83f-113">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
