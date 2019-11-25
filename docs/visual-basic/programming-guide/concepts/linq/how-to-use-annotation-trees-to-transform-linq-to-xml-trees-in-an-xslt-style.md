---
title: Практическое руководство. Использование примечаний для преобразования деревьев LINQ to XML в стиль XSLT
ms.date: 07/20/2015
ms.assetid: 08e91fa2-dac2-4463-9ef1-87b1ac3fa890
ms.openlocfilehash: d9cb32462535f099107343bd9069b4da3508c5b0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348357"
---
# <a name="how-to-use-annotations-to-transform-linq-to-xml-trees-in-an-xslt-style-visual-basic"></a><span data-ttu-id="351ec-102">How to: Use Annotations to Transform LINQ to XML Trees in an XSLT Style (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="351ec-102">How to: Use Annotations to Transform LINQ to XML Trees in an XSLT Style (Visual Basic)</span></span>

<span data-ttu-id="351ec-103">Заметки можно использовать для упрощения преобразований XML-дерева.</span><span class="sxs-lookup"><span data-stu-id="351ec-103">Annotations can be used to facilitate transforms of an XML tree.</span></span>

<span data-ttu-id="351ec-104">Некоторые XML-документы рассматриваются как «предназначенные для обработки в виде документов со смешанным содержимым».</span><span class="sxs-lookup"><span data-stu-id="351ec-104">Some XML documents are "document centric with mixed content."</span></span> <span data-ttu-id="351ec-105">При использовании таких документов не требуется знать форму дочерних узлов элемента.</span><span class="sxs-lookup"><span data-stu-id="351ec-105">With such documents, you don't necessarily know the shape of child nodes of an element.</span></span> <span data-ttu-id="351ec-106">Например, узел, содержащий текст, может выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="351ec-106">For instance, a node that contains text may look like this:</span></span>

```xml
<text>A phrase with <b>bold</b> and <i>italic</i> text.</text>
```

<span data-ttu-id="351ec-107">У любого заданного текстового узла может быть любое количество дочерних элементов `<b>` и `<i>`.</span><span class="sxs-lookup"><span data-stu-id="351ec-107">For any given text node, there may be any number of child `<b>` and `<i>` elements.</span></span> <span data-ttu-id="351ec-108">This approach extends to a number of other situations: such as, pages that can contain a variety of child elements, such as regular paragraphs, bulleted paragraphs, and bitmaps.</span><span class="sxs-lookup"><span data-stu-id="351ec-108">This approach extends to a number of other situations: such as, pages that can contain a variety of child elements, such as regular paragraphs, bulleted paragraphs, and bitmaps.</span></span> <span data-ttu-id="351ec-109">Ячейки таблицы могут содержать текст, раскрывающиеся списки или битовые карты.</span><span class="sxs-lookup"><span data-stu-id="351ec-109">Cells in a table may contain text, drop down lists, or bitmaps.</span></span> <span data-ttu-id="351ec-110">Одной из основных отличительных особенностей кода XML, предназначенного для представления документов, является то, что неизвестно, какие дочерние элементы будет иметь тот или иной конкретный элемент.</span><span class="sxs-lookup"><span data-stu-id="351ec-110">One of the primary characteristics of document centric XML is that you do not know which child element any particular element will have.</span></span>

<span data-ttu-id="351ec-111">Если требуется преобразовать элементы в дереве, о дочерних элементах которого знать не обязательно, то данный подход, использующий заметки, становится эффективным.</span><span class="sxs-lookup"><span data-stu-id="351ec-111">If you want to transform elements in a tree where you don't necessarily know much about the children of the elements that you want to transform, then this approach that uses annotations is an effective approach.</span></span>

<span data-ttu-id="351ec-112">Сводка этого подхода состоит в следующем.</span><span class="sxs-lookup"><span data-stu-id="351ec-112">The summary of the approach is:</span></span>

- <span data-ttu-id="351ec-113">Во-первых, обозначить элементы в дереве заметками в виде элемента замены.</span><span class="sxs-lookup"><span data-stu-id="351ec-113">First, annotate elements in the tree with a replacement element.</span></span>

- <span data-ttu-id="351ec-114">Во-вторых, провести итерацию по всему дереву, создавая новое дерево, в котором каждый элемент заменяется его заметкой.</span><span class="sxs-lookup"><span data-stu-id="351ec-114">Second, iterate through the entire tree, creating a new tree where you replace each element with its annotation.</span></span> <span data-ttu-id="351ec-115">В этом примере реализуются итерация и создание нового дерева в функции с именем `XForm`.</span><span class="sxs-lookup"><span data-stu-id="351ec-115">This example implements the iteration and creation of the new tree in a function named `XForm`.</span></span>

<span data-ttu-id="351ec-116">В более подробном изложении этот подход состоит в следующем.</span><span class="sxs-lookup"><span data-stu-id="351ec-116">In detail, the approach consists of:</span></span>

- <span data-ttu-id="351ec-117">Выполняются один или несколько запросов LINQ to XML, возвращающих набор элементов, которые требуется преобразовать из одной формы в другую.</span><span class="sxs-lookup"><span data-stu-id="351ec-117">Execute one or more LINQ to XML queries that return the set of elements that you want to transform from one shape to another.</span></span> <span data-ttu-id="351ec-118">К каждому элементу запроса в качестве заметки добавляется новый объект <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="351ec-118">For each element in the query, add a new <xref:System.Xml.Linq.XElement> object as an annotation to the element.</span></span> <span data-ttu-id="351ec-119">Новый элемент заменяет элемент с заметкой в новом, преобразованном дереве.</span><span class="sxs-lookup"><span data-stu-id="351ec-119">This new element will replace the annotated element in the new, transformed tree.</span></span> <span data-ttu-id="351ec-120">Как видно из примера, этот код прост для написания.</span><span class="sxs-lookup"><span data-stu-id="351ec-120">This is simple code to write, as demonstrated by the example.</span></span>

- <span data-ttu-id="351ec-121">Новый элемент, добавляемый в виде заметки, может содержать новые дочерние узлы. Он может формировать поддерево любой необходимой формы.</span><span class="sxs-lookup"><span data-stu-id="351ec-121">The new element that is added as an annotation can contain new child nodes; it can form a sub-tree with any desired shape.</span></span>

- <span data-ttu-id="351ec-122">Предусмотрено специальное правило. Если дочерний узел нового элемента находится в другом пространстве имен, специально созданном для этой цели (в данном примере таким пространством имен является `http://www.microsoft.com/LinqToXmlTransform/2007`), то дочерний элемент не копируется в новое дерево.</span><span class="sxs-lookup"><span data-stu-id="351ec-122">There is a special rule: If a child node of the new element is in a different namespace, a namespace that is made up for this purpose (in this example, the namespace is `http://www.microsoft.com/LinqToXmlTransform/2007`), then that child element is not copied to the new tree.</span></span> <span data-ttu-id="351ec-123">Вместо этого, если пространство имен представляет собой упомянутое выше специальное пространство имен, а локальным именем элемента является `ApplyTransforms`, последовательно производится итерация по дочерним узлам элемента в исходном дереве и копирование их в новое дерево (за исключением того, что обозначенные заметками дочерние элементы преобразуются сами согласно этим правилам).</span><span class="sxs-lookup"><span data-stu-id="351ec-123">Instead, if the namespace is the above mentioned special namespace, and the local name of the element is `ApplyTransforms`, then the child nodes of the element in the source tree are iterated, and copied to the new tree (with the exception that annotated child elements are themselves transformed according to these rules).</span></span>

- <span data-ttu-id="351ec-124">Это в какой-то мере аналогично спецификации преобразований в XSL.</span><span class="sxs-lookup"><span data-stu-id="351ec-124">This is somewhat analogous to the specification of transforms in XSL.</span></span> <span data-ttu-id="351ec-125">Запрос, выбирающий набор узлов, аналогичен выражению XPath для шаблона.</span><span class="sxs-lookup"><span data-stu-id="351ec-125">The query that selects a set of nodes is analogous to the XPath expression for a template.</span></span> <span data-ttu-id="351ec-126">Код создания нового элемента <xref:System.Xml.Linq.XElement>, сохраняемого в виде заметки, аналогичен конструктору последовательности в XSL, а элемент `ApplyTransforms` по своему назначению аналогичен элементу `xsl:apply-templates` в XSL.</span><span class="sxs-lookup"><span data-stu-id="351ec-126">The code to create the new <xref:System.Xml.Linq.XElement> that is saved as an annotation is analogous to the sequence constructor in XSL, and the `ApplyTransforms` element is analogous in function to the `xsl:apply-templates` element in XSL.</span></span>

- <span data-ttu-id="351ec-127">Одним из преимуществ данного подхода является то, что запросы при формировании всегда создаются применительно к неизмененному исходному дереву.</span><span class="sxs-lookup"><span data-stu-id="351ec-127">One advantage to taking this approach - as you formulate queries, you are always writing queries on the unmodified source tree.</span></span> <span data-ttu-id="351ec-128">Можно не беспокоиться о том, как изменения в дереве повлияют на формируемые запросы.</span><span class="sxs-lookup"><span data-stu-id="351ec-128">You need not worry about how modifications to the tree affect the queries that you are writing.</span></span>

## <a name="transforming-a-tree"></a><span data-ttu-id="351ec-129">Преобразование дерева</span><span class="sxs-lookup"><span data-stu-id="351ec-129">Transforming a Tree</span></span>

<span data-ttu-id="351ec-130">This first example renames all `Paragraph` nodes to `para`:</span><span class="sxs-lookup"><span data-stu-id="351ec-130">This first example renames all `Paragraph` nodes to `para`:</span></span>

```vb
Imports <xmlns:xf="http://www.microsoft.com/LinqToXmlTransform/2007">

Module Module1
    Dim at As XName = GetXmlNamespace(xf) + "ApplyTransforms"

    Sub Main()
        Dim root As XElement = _
            <Root>
                <Paragraph>This is a sentence with <b>bold</b> and <i>italic</i> text.</Paragraph>
                <Paragraph>More text.</Paragraph>
            </Root>

        ' Replace Paragraph with p.
        For Each el In root...<Paragraph>
            ' same idea as xsl:apply-templates
            el.AddAnnotation( _
                <para>
                    <<%= at %>></>
                </para>)
        Next

        ' The XForm function, shown later in this topic, accomplishes the transform
        Dim newRoot As XElement = XForm(root)
        Console.WriteLine(newRoot)
    End Sub
End Module
```

 <span data-ttu-id="351ec-131">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="351ec-131">This example produces the following output:</span></span>

```xml
<Root>
  <para>This is a sentence with <b>bold</b> and <i>italic</i> text.</para>
  <para>More text.</para>
</Root>
```

## <a name="a-more-complicated-transform"></a><span data-ttu-id="351ec-132">A more complicated transform</span><span class="sxs-lookup"><span data-stu-id="351ec-132">A more complicated transform</span></span>

<span data-ttu-id="351ec-133">В следующем примере выполняется запрос к дереву и вычисляются среднее арифметическое и сумма элементов `Data`, а затем происходит их добавление в дерево в виде новых элементов.</span><span class="sxs-lookup"><span data-stu-id="351ec-133">The following example queries the tree and calculates the average and sum of the `Data` elements, and adds them as new elements to the tree.</span></span>

```vb
Imports <xmlns:xf="http://www.microsoft.com/LinqToXmlTransform/2007">

Module Module1
    Dim at As XName = GetXmlNamespace(xf) + "ApplyTransforms"

    Sub Main()
        Dim data As XElement = _
            <Root>
                <Data>20</Data>
                <Data>10</Data>
                <Data>3</Data>
            </Root>

        ' While adding annotations, you can query the source tree all you want,
        ' as the tree is not mutated while annotating.
        data.AddAnnotation( _
            <Root>
                <<%= at %>/>
                <Average>
                    <%= _
                        String.Format("{0:F4}", _
                        data.Elements("Data") _
                        .Select(Function(z) CDec(z)).Average()) _
                    %>
                </Average>
                <Sum>
                    <%= _
                        data.Elements("Data").Select(Function(z) CInt(z)).Sum() _
                    %>
                </Sum>
            </Root> _
        )

        Console.WriteLine("Before Transform")
        Console.WriteLine("----------------")
        Console.WriteLine(data)
        Console.WriteLine(vbNewLine)

        ' The XForm function, shown later in this topic, accomplishes the transform
        Dim newData As XElement = XForm(data)

        Console.WriteLine("After Transform")
        Console.WriteLine("----------------")
        Console.WriteLine(newData)
    End Sub
End Module
```

<span data-ttu-id="351ec-134">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="351ec-134">This example produces the following output:</span></span>

```console
Before Transform
----------------
<Root>
  <Data>20</Data>
  <Data>10</Data>
  <Data>3</Data>
</Root>

After Transform
----------------
<Root>
  <Data>20</Data>
  <Data>10</Data>
  <Data>3</Data>
  <Average>11.0000</Average>
  <Sum>33</Sum>
</Root>
```

## <a name="effecting-the-transform"></a><span data-ttu-id="351ec-135">Effecting the transform</span><span class="sxs-lookup"><span data-stu-id="351ec-135">Effecting the transform</span></span>

<span data-ttu-id="351ec-136">Небольшая функция `XForm` создает новое преобразованное дерево из исходного дерева, обозначенного заметками.</span><span class="sxs-lookup"><span data-stu-id="351ec-136">A small function, `XForm`, creates a new transformed tree from the original, annotated tree.</span></span>

<span data-ttu-id="351ec-137">Псевдокод для функции достаточно прост:</span><span class="sxs-lookup"><span data-stu-id="351ec-137">The pseudo code for the function is quite simple:</span></span>

> <span data-ttu-id="351ec-138">The function takes an XElement as an argument and returns an XElement.</span><span class="sxs-lookup"><span data-stu-id="351ec-138">The function takes an XElement as an argument and returns an XElement.</span></span>
>
> <span data-ttu-id="351ec-139">If an element has an XElement annotation, then return a new XElement:</span><span class="sxs-lookup"><span data-stu-id="351ec-139">If an element has an XElement annotation, then return a new XElement:</span></span>
>
> - <span data-ttu-id="351ec-140">The name of the new XElement is the annotation element's name.</span><span class="sxs-lookup"><span data-stu-id="351ec-140">The name of the new XElement is the annotation element's name.</span></span>
> - <span data-ttu-id="351ec-141">All attributes are copied from the annotation to the new node.</span><span class="sxs-lookup"><span data-stu-id="351ec-141">All attributes are copied from the annotation to the new node.</span></span>
> - <span data-ttu-id="351ec-142">All child nodes are copied from the annotation, with the exception that the special node xf:ApplyTransforms is recognized, and the source element's child nodes are iterated.</span><span class="sxs-lookup"><span data-stu-id="351ec-142">All child nodes are copied from the annotation, with the exception that the special node xf:ApplyTransforms is recognized, and the source element's child nodes are iterated.</span></span> <span data-ttu-id="351ec-143">If the source child node is not an XElement, it is copied to the new tree.</span><span class="sxs-lookup"><span data-stu-id="351ec-143">If the source child node is not an XElement, it is copied to the new tree.</span></span> <span data-ttu-id="351ec-144">If the source child is an XElement, then it is transformed by calling this function recursively.</span><span class="sxs-lookup"><span data-stu-id="351ec-144">If the source child is an XElement, then it is transformed by calling this function recursively.</span></span>
>
> <span data-ttu-id="351ec-145">If an element is not annotated:</span><span class="sxs-lookup"><span data-stu-id="351ec-145">If an element is not annotated:</span></span>
>
> - <span data-ttu-id="351ec-146">Return a new XElement</span><span class="sxs-lookup"><span data-stu-id="351ec-146">Return a new XElement</span></span>
>   - <span data-ttu-id="351ec-147">The name of the new XElement is the source element's name.</span><span class="sxs-lookup"><span data-stu-id="351ec-147">The name of the new XElement is the source element's name.</span></span>
>   - <span data-ttu-id="351ec-148">All attributes are copied from the source element to the destination's element.</span><span class="sxs-lookup"><span data-stu-id="351ec-148">All attributes are copied from the source element to the destination's element.</span></span>
>   - <span data-ttu-id="351ec-149">All child nodes are copied from the source element.</span><span class="sxs-lookup"><span data-stu-id="351ec-149">All child nodes are copied from the source element.</span></span>
>   - <span data-ttu-id="351ec-150">If the source child node is not an XElement, it is copied to the new tree.</span><span class="sxs-lookup"><span data-stu-id="351ec-150">If the source child node is not an XElement, it is copied to the new tree.</span></span> <span data-ttu-id="351ec-151">If the source child is an XElement, then it is transformed by calling this function recursively.</span><span class="sxs-lookup"><span data-stu-id="351ec-151">If the source child is an XElement, then it is transformed by calling this function recursively.</span></span>

<span data-ttu-id="351ec-152">The following code is the implementation of this function:</span><span class="sxs-lookup"><span data-stu-id="351ec-152">The following code is the implementation of this function:</span></span>

```vb
' Build a transformed XML tree per the annotations.
Function XForm(ByVal source As XElement) As XElement
    If source.Annotation(Of XElement)() IsNot Nothing Then
        Dim anno As XElement = source.Annotation(Of XElement)()
        Return _
            <<%= anno.Name.ToString() %>>
                <%= anno.Attributes() %>
                <%= anno.Nodes().Select(Function(n As XNode) _
                    GetSubNodes(n, source)) %>
            </>
    Else
        Return _
            <<%= source.Name %>>
                <%= source.Attributes() %>
                <%= source.Nodes().Select(Function(n) GetExpandedNodes(n)) %>
            </>
    End If
End Function

Private Function GetSubNodes(ByVal n As XNode, ByVal s As XElement) As Object
    Dim annoEl As XElement = TryCast(n, XElement)
    If annoEl IsNot Nothing Then
        If annoEl.Name = at Then
            Return s.Nodes().Select(Function(n2 As XNode) GetExpandedNodes(n2))
        End If
    End If
    Return n
End Function

Private Function GetExpandedNodes(ByVal n2 As XNode) As XNode
    Dim e2 As XElement = TryCast(n2, XElement)
    If e2 Is Nothing Then
        Return n2
    Else
        Return XForm(e2)
    End If
End Function
```

## <a name="complete-example"></a><span data-ttu-id="351ec-153">Полный пример</span><span class="sxs-lookup"><span data-stu-id="351ec-153">Complete example</span></span>

<span data-ttu-id="351ec-154">Следующий код является полным примером, включающим функцию `XForm`.</span><span class="sxs-lookup"><span data-stu-id="351ec-154">The following code is a complete example that includes the `XForm` function.</span></span> <span data-ttu-id="351ec-155">Он включает несколько типичных вариантов использования преобразования данного типа:</span><span class="sxs-lookup"><span data-stu-id="351ec-155">It includes a few of the typical uses of this type of transform:</span></span>

```vb
Imports System.Collections.Generic
Imports System.Linq
Imports System.Text
Imports System.Xml
Imports System.Xml.Linq

Imports <xmlns:xf="http://www.microsoft.com/LinqToXmlTransform/2007">

Module Module1
    Dim at As XName = GetXmlNamespace(xf) + "ApplyTransforms"

    ' Build a transformed XML tree per the annotations.
    Function XForm(ByVal source As XElement) As XElement
        If source.Annotation(Of XElement)() IsNot Nothing Then
            Dim anno As XElement = source.Annotation(Of XElement)()
            Return _
                <<%= anno.Name.ToString() %>>
                    <%= anno.Attributes() %>
                    <%= anno.Nodes().Select(Function(n As XNode) _
                        GetSubNodes(n, source)) %>
                </>
        Else
            Return _
                <<%= source.Name %>>
                    <%= source.Attributes() %>
                    <%= source.Nodes().Select(Function(n) GetExpandedNodes(n)) %>
                </>
        End If
    End Function

    Private Function GetSubNodes(ByVal n As XNode, ByVal s As XElement) As Object
        Dim annoEl As XElement = TryCast(n, XElement)
        If annoEl IsNot Nothing Then
            If annoEl.Name = at Then
                Return s.Nodes().Select(Function(n2 As XNode) GetExpandedNodes(n2))
            End If
        End If
        Return n
    End Function

    Private Function GetExpandedNodes(ByVal n2 As XNode) As XNode
        Dim e2 As XElement = TryCast(n2, XElement)
        If e2 Is Nothing Then
            Return n2
        Else
            Return XForm(e2)
        End If
    End Function

    Sub Main()
        Dim root As XElement = _
<Root Att1='123'>
    <!--A comment-->
    <Child>1</Child>
    <Child>2</Child>
    <Other>
        <GC>3</GC>
        <GC>4</GC>
    </Other>
    <SomeMixedContent>This is <i>an</i> element that <b>has</b> some mixed content</SomeMixedContent>
    <AnUnchangedElement>42</AnUnchangedElement>
</Root>

        ' Each of the following serves the same semantic purpose as
        ' XSLT templates and sequence constructors.

        ' Replace Child with NewChild.
        For Each el In root.<Child>
            el.AddAnnotation(<NewChild><%= CStr(el) %></NewChild>)
        Next

        ' Replace first GC with GrandChild, add an attribute.
        For Each el In root...<GC>.Take(1)
            el.AddAnnotation(<GrandChild ANewAttribute='999'><%= CStr(el) %></GrandChild>)
        Next

        ' Replace Other with NewOther, add new child elements around original content.
        For Each el In root.<Other>
            el.AddAnnotation( _
                <NewOther>
                    <MyNewChild>1</MyNewChild>
                    <<%= at %>></>
                    <ChildThatComesAfter/>
                </NewOther>)
        Next

        ' Change name of element that has mixed content.
        root...<SomeMixedContent>(0).AddAnnotation( _
                <MixedContent><<%= at %>></></MixedContent>)

        ' Replace <b> with <Bold>.
        For Each el In root...<b>
            el.AddAnnotation(<Bold><<%= at %>></></Bold>)
        Next

        ' Replace <i> with <Italic>.
        For Each el In root...<i>
            el.AddAnnotation(<Italic><<%= at %>></></Italic>)
        Next

        Console.WriteLine("Before Transform")
        Console.WriteLine("----------------")
        Console.WriteLine(root)
        Console.WriteLine(vbNewLine)
        Dim newRoot As XElement = XForm(root)

        Console.WriteLine("After Transform")
        Console.WriteLine("----------------")
        Console.WriteLine(newRoot)
    End Sub
End Module
```

<span data-ttu-id="351ec-156">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="351ec-156">This example produces the following output:</span></span>

```console
Before Transform
----------------
<Root Att1="123">
  <!--A comment-->
  <Child>1</Child>
  <Child>2</Child>
  <Other>
    <GC>3</GC>
    <GC>4</GC>
  </Other>
  <SomeMixedContent>This is <i>an</i> element that <b>has</b> some mixed content</SomeMixedContent>
  <AnUnchangedElement>42</AnUnchangedElement>
</Root>

After Transform
----------------
<Root Att1="123">
  <!--A comment-->
  <NewChild>1</NewChild>
  <NewChild>2</NewChild>
  <NewOther>
    <MyNewChild>1</MyNewChild>
    <GrandChild ANewAttribute="999">3</GrandChild>
    <GC>4</GC>
    <ChildThatComesAfter />
  </NewOther>
  <MixedContent>This is <Italic>an</Italic> element that <Bold>has</Bold> some mixed content</MixedContent>
  <AnUnchangedElement>42</AnUnchangedElement>
</Root>
```

## <a name="see-also"></a><span data-ttu-id="351ec-157">См. также</span><span class="sxs-lookup"><span data-stu-id="351ec-157">See also</span></span>

- [<span data-ttu-id="351ec-158">Advanced LINQ to XML Programming (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="351ec-158">Advanced LINQ to XML Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
