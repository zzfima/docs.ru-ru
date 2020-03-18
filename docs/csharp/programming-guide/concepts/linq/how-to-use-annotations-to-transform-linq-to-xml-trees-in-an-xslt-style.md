---
title: Как использовать заметки для преобразования деревьев LINQ to XML в стиль XSLT (C#)
ms.date: 07/20/2015
ms.assetid: 12a95902-a6b7-4a1e-ad52-04a518db226f
ms.openlocfilehash: 7d6d646bb9b7b344750c22cb24bc81999da5210d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79168561"
---
# <a name="how-to-use-annotations-to-transform-linq-to-xml-trees-in-an-xslt-style-c"></a><span data-ttu-id="9e54c-102">Как использовать заметки для преобразования деревьев LINQ to XML в стиль XSLT (C#)</span><span class="sxs-lookup"><span data-stu-id="9e54c-102">How to use annotations to transform LINQ to XML trees in an XSLT style (C#)</span></span>
<span data-ttu-id="9e54c-103">Заметки можно использовать для упрощения преобразований XML-дерева.</span><span class="sxs-lookup"><span data-stu-id="9e54c-103">Annotations can be used to facilitate transforms of an XML tree.</span></span>  
  
 <span data-ttu-id="9e54c-104">Некоторые XML-документы рассматриваются как «предназначенные для обработки в виде документов со смешанным содержимым».</span><span class="sxs-lookup"><span data-stu-id="9e54c-104">Some XML documents are "document centric with mixed content."</span></span> <span data-ttu-id="9e54c-105">При использовании таких документов не требуется знать форму дочерних узлов элемента.</span><span class="sxs-lookup"><span data-stu-id="9e54c-105">With such documents, you don't necessarily know the shape of child nodes of an element.</span></span> <span data-ttu-id="9e54c-106">Например, узел, содержащий текст, может выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="9e54c-106">For instance, a node that contains text may look like this:</span></span>  
  
```xml  
<text>A phrase with <b>bold</b> and <i>italic</i> text.</text>  
```  
  
 <span data-ttu-id="9e54c-107">У любого заданного текстового узла может быть любое количество дочерних элементов `<b>` и `<i>`.</span><span class="sxs-lookup"><span data-stu-id="9e54c-107">For any given text node, there may be any number of child `<b>` and `<i>` elements.</span></span> <span data-ttu-id="9e54c-108">Этот подход можно применять в ряде других ситуаций, например для страниц, которые содержат разнообразные дочерние элементы, такие как обычные абзацы, маркированные абзацы и растровые изображения.</span><span class="sxs-lookup"><span data-stu-id="9e54c-108">This approach extends to a number of other situations, such as pages that can contain a variety of child elements, such as regular paragraphs, bulleted paragraphs, and bitmaps.</span></span> <span data-ttu-id="9e54c-109">Ячейки таблицы могут содержать текст, раскрывающиеся списки или битовые карты.</span><span class="sxs-lookup"><span data-stu-id="9e54c-109">Cells in a table may contain text, drop down lists, or bitmaps.</span></span> <span data-ttu-id="9e54c-110">Одной из основных отличительных особенностей кода XML, предназначенного для представления документов, является то, что неизвестно, какие дочерние элементы будет иметь тот или иной конкретный элемент.</span><span class="sxs-lookup"><span data-stu-id="9e54c-110">One of the primary characteristics of document centric XML is that you do not know which child element any particular element will have.</span></span>  
  
 <span data-ttu-id="9e54c-111">Если требуется преобразовать элементы в дереве, о дочерних элементах которого знать не обязательно, то данный подход, использующий заметки, становится эффективным.</span><span class="sxs-lookup"><span data-stu-id="9e54c-111">If you want to transform elements in a tree where you don't necessarily know much about the children of the elements that you want to transform, then this approach that uses annotations is an effective approach.</span></span>  
  
 <span data-ttu-id="9e54c-112">Сводка этого подхода состоит в следующем.</span><span class="sxs-lookup"><span data-stu-id="9e54c-112">The summary of the approach is:</span></span>  
  
- <span data-ttu-id="9e54c-113">Во-первых, обозначить элементы в дереве заметками в виде элемента замены.</span><span class="sxs-lookup"><span data-stu-id="9e54c-113">First, annotate elements in the tree with a replacement element.</span></span>  
  
- <span data-ttu-id="9e54c-114">Во-вторых, провести итерацию по всему дереву, создавая новое дерево, в котором каждый элемент заменяется его заметкой.</span><span class="sxs-lookup"><span data-stu-id="9e54c-114">Second, iterate through the entire tree, creating a new tree where you replace each element with its annotation.</span></span> <span data-ttu-id="9e54c-115">В этом примере реализуются итерация и создание нового дерева в функции с именем `XForm`.</span><span class="sxs-lookup"><span data-stu-id="9e54c-115">This example implements the iteration and creation of the new tree in a function named `XForm`.</span></span>  
  
 <span data-ttu-id="9e54c-116">В более подробном изложении этот подход состоит в следующем.</span><span class="sxs-lookup"><span data-stu-id="9e54c-116">In detail, the approach consists of:</span></span>  
  
- <span data-ttu-id="9e54c-117">Выполняются один или несколько запросов LINQ to XML, возвращающих набор элементов, которые требуется преобразовать из одной формы в другую.</span><span class="sxs-lookup"><span data-stu-id="9e54c-117">Execute one or more LINQ to XML queries that return the set of elements that you want to transform from one shape to another.</span></span> <span data-ttu-id="9e54c-118">К каждому элементу запроса в качестве заметки добавляется новый объект <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="9e54c-118">For each element in the query, add a new <xref:System.Xml.Linq.XElement> object as an annotation to the element.</span></span> <span data-ttu-id="9e54c-119">Новый элемент заменяет элемент с заметкой в новом, преобразованном дереве.</span><span class="sxs-lookup"><span data-stu-id="9e54c-119">This new element will replace the annotated element in the new, transformed tree.</span></span> <span data-ttu-id="9e54c-120">Как видно из примера, этот код прост для написания.</span><span class="sxs-lookup"><span data-stu-id="9e54c-120">This is simple code to write, as demonstrated by the example.</span></span>  
  
- <span data-ttu-id="9e54c-121">Новый элемент, добавляемый в виде заметки, может содержать новые дочерние узлы. Он может формировать поддерево любой необходимой формы.</span><span class="sxs-lookup"><span data-stu-id="9e54c-121">The new element that is added as an annotation can contain new child nodes; it can form a sub-tree with any desired shape.</span></span>  
  
- <span data-ttu-id="9e54c-122">Предусмотрено специальное правило. Если дочерний узел нового элемента находится в другом пространстве имен, специально созданном для этой цели (в данном примере таким пространством имен является `http://www.microsoft.com/LinqToXmlTransform/2007`), то дочерний элемент не копируется в новое дерево.</span><span class="sxs-lookup"><span data-stu-id="9e54c-122">There is a special rule: If a child node of the new element is in a different namespace, a namespace that is made up for this purpose (in this example, the namespace is `http://www.microsoft.com/LinqToXmlTransform/2007`), then that child element is not copied to the new tree.</span></span> <span data-ttu-id="9e54c-123">Вместо этого, если пространство имен представляет собой упомянутое выше специальное пространство имен, а локальным именем элемента является `ApplyTransforms`, последовательно производится итерация по дочерним узлам элемента в исходном дереве и копирование их в новое дерево (за исключением того, что обозначенные заметками дочерние элементы преобразуются сами согласно этим правилам).</span><span class="sxs-lookup"><span data-stu-id="9e54c-123">Instead, if the namespace is the above mentioned special namespace, and the local name of the element is `ApplyTransforms`, then the child nodes of the element in the source tree are iterated, and copied to the new tree (with the exception that annotated child elements are themselves transformed according to these rules).</span></span>  
  
- <span data-ttu-id="9e54c-124">Это в какой-то мере аналогично спецификации преобразований в XSL.</span><span class="sxs-lookup"><span data-stu-id="9e54c-124">This is somewhat analogous to the specification of transforms in XSL.</span></span> <span data-ttu-id="9e54c-125">Запрос, выбирающий набор узлов, аналогичен выражению XPath для шаблона.</span><span class="sxs-lookup"><span data-stu-id="9e54c-125">The query that selects a set of nodes is analogous to the XPath expression for a template.</span></span> <span data-ttu-id="9e54c-126">Код создания нового элемента <xref:System.Xml.Linq.XElement>, сохраняемого в виде заметки, аналогичен конструктору последовательности в XSL, а элемент `ApplyTransforms` по своему назначению аналогичен элементу `xsl:apply-templates` в XSL.</span><span class="sxs-lookup"><span data-stu-id="9e54c-126">The code to create the new <xref:System.Xml.Linq.XElement> that is saved as an annotation is analogous to the sequence constructor in XSL, and the `ApplyTransforms` element is analogous in function to the `xsl:apply-templates` element in XSL.</span></span>  
  
- <span data-ttu-id="9e54c-127">Одним из преимуществ данного подхода является то, что запросы при формировании всегда создаются применительно к неизмененному исходному дереву.</span><span class="sxs-lookup"><span data-stu-id="9e54c-127">One advantage to taking this approach - as you formulate queries, you are always writing queries on the unmodified source tree.</span></span> <span data-ttu-id="9e54c-128">Можно не беспокоиться о том, как изменения в дереве повлияют на формируемые запросы.</span><span class="sxs-lookup"><span data-stu-id="9e54c-128">You need not worry about how modifications to the tree affect the queries that you are writing.</span></span>  
  
## <a name="transforming-a-tree"></a><span data-ttu-id="9e54c-129">Преобразование дерева</span><span class="sxs-lookup"><span data-stu-id="9e54c-129">Transforming a Tree</span></span>  
 <span data-ttu-id="9e54c-130">В этом первом примере переименовываются все узлы `Paragraph` в `para`.</span><span class="sxs-lookup"><span data-stu-id="9e54c-130">This first example renames all `Paragraph` nodes to `para`.</span></span>  
  
```csharp  
XNamespace xf = "http://www.microsoft.com/LinqToXmlTransform/2007";  
XName at = xf + "ApplyTransforms";  
  
XElement root = XElement.Parse(@"  
<Root>  
    <Paragraph>This is a sentence with <b>bold</b> and <i>italic</i> text.</Paragraph>  
    <Paragraph>More text.</Paragraph>  
</Root>");  
  
// replace Paragraph with para  
foreach (var el in root.Descendants("Paragraph"))  
    el.AddAnnotation(  
        new XElement("para",  
            // same idea as xsl:apply-templates  
            new XElement(xf + "ApplyTransforms")  
        )  
    );  
  
// The XForm method, shown later in this topic, accomplishes the transform  
XElement newRoot = XForm(root);  
  
Console.WriteLine(newRoot);  
```  
  
 <span data-ttu-id="9e54c-131">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="9e54c-131">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <para>This is a sentence with <b>bold</b> and <i>italic</i> text.</para>  
  <para>More text.</para>  
</Root>  
```  
  
## <a name="a-more-complicated-transform"></a><span data-ttu-id="9e54c-132">Более сложное преобразование</span><span class="sxs-lookup"><span data-stu-id="9e54c-132">A More Complicated Transform</span></span>  
 <span data-ttu-id="9e54c-133">В следующем примере выполняется запрос к дереву и вычисляются среднее арифметическое и сумма элементов `Data`, а затем происходит их добавление в дерево в виде новых элементов.</span><span class="sxs-lookup"><span data-stu-id="9e54c-133">The following example queries the tree and calculates the average and sum of the `Data` elements, and adds them as new elements to the tree.</span></span>  
  
```csharp  
XNamespace xf = "http://www.microsoft.com/LinqToXmlTransform/2007";  
XName at = xf + "ApplyTransforms";  
  
XElement data = new XElement("Root",  
    new XElement("Data", 20),  
    new XElement("Data", 10),  
    new XElement("Data", 3)  
);  
  
// while adding annotations, you can query the source tree all you want,  
// as the tree is not mutated while annotating.
var avg = data.Elements("Data").Select(z => (Decimal)z).Average();
data.AddAnnotation(  
    new XElement("Root",  
        new XElement(xf + "ApplyTransforms"),  
        new XElement("Average", $"{avg:F4}"),
        new XElement("Sum",  
            data  
            .Elements("Data")  
            .Select(z => (int)z)  
            .Sum()  
        )  
    )  
);  
  
Console.WriteLine("Before Transform");  
Console.WriteLine("----------------");  
Console.WriteLine(data);  
Console.WriteLine();  
Console.WriteLine();  
  
// The XForm method, shown later in this topic, accomplishes the transform  
XElement newData = XForm(data);  
  
Console.WriteLine("After Transform");  
Console.WriteLine("----------------");  
Console.WriteLine(newData);  
```  
  
 <span data-ttu-id="9e54c-134">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="9e54c-134">This example produces the following output:</span></span>  
  
```output  
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
  
## <a name="effecting-the-transform"></a><span data-ttu-id="9e54c-135">Влияние на преобразование</span><span class="sxs-lookup"><span data-stu-id="9e54c-135">Effecting the Transform</span></span>  
 <span data-ttu-id="9e54c-136">Небольшая функция `XForm` создает новое преобразованное дерево из исходного дерева, обозначенного заметками.</span><span class="sxs-lookup"><span data-stu-id="9e54c-136">A small function, `XForm`, creates a new transformed tree from the original, annotated tree.</span></span>  
  
- <span data-ttu-id="9e54c-137">Псевдокод для функции достаточно прост:</span><span class="sxs-lookup"><span data-stu-id="9e54c-137">The pseudo code for the function is quite simple:</span></span>  
  
```text  
The function takes an XElement as an argument and returns an XElement.
If an element has an XElement annotation, then  
    Return a new XElement  
        The name of the new XElement is the annotation element's name.  
        All attributes are copied from the annotation to the new node.  
        All child nodes are copied from the annotation, with the  
            exception that the special node xf:ApplyTransforms is  
            recognized, and the source element's child nodes are  
            iterated. If the source child node is not an XElement, it  
            is copied to the new tree. If the source child is an  
            XElement, then it is transformed by calling this function  
            recursively.  
If an element is not annotated  
    Return a new XElement  
        The name of the new XElement is the source element's name  
        All attributes are copied from the source element to the  
            destination's element.  
        All child nodes are copied from the source element.  
        If the source child node is not an XElement, it is copied to  
            the new tree. If the source child is an XElement, then it  
            is transformed by calling this function recursively.  
```  
  
 <span data-ttu-id="9e54c-138">Далее приводится реализация этой функции:</span><span class="sxs-lookup"><span data-stu-id="9e54c-138">Following is the implementation of this function:</span></span>  
  
```csharp  
// Build a transformed XML tree per the annotations  
static XElement XForm(XElement source)  
{  
    XNamespace xf = "http://www.microsoft.com/LinqToXmlTransform/2007";  
    XName at = xf + "ApplyTransforms";  
  
    if (source.Annotation<XElement>() != null)  
    {  
        XElement anno = source.Annotation<XElement>();  
        return new XElement(anno.Name,  
            anno.Attributes(),  
            anno  
            .Nodes()  
            .Select(  
                (XNode n) =>  
                {  
                    XElement annoEl = n as XElement;  
                    if (annoEl != null)  
                    {  
                        if (annoEl.Name == at)  
                            return (object)(  
                                source.Nodes()  
                                .Select(  
                                    (XNode n2) =>  
                                    {  
                                        XElement e2 = n2 as XElement;  
                                        if (e2 == null)  
                                            return n2;  
                                        else  
                                            return XForm(e2);  
                                    }  
                                )  
                            );  
                        else  
                            return n;  
                    }  
                    else  
                        return n;  
                }  
            )  
        );  
    }  
    else  
    {  
        return new XElement(source.Name,  
            source.Attributes(),  
            source  
                .Nodes()  
                .Select(n =>  
                {  
                    XElement el = n as XElement;  
                    if (el == null)  
                        return n;  
                    else  
                        return XForm(el);  
                }  
                )  
        );  
    }  
}
```  
  
## <a name="complete-example"></a><span data-ttu-id="9e54c-139">Полный пример</span><span class="sxs-lookup"><span data-stu-id="9e54c-139">Complete Example</span></span>  
 <span data-ttu-id="9e54c-140">Следующий код является полным примером, включающим функцию `XForm`.</span><span class="sxs-lookup"><span data-stu-id="9e54c-140">The following code is a complete example that includes the `XForm` function.</span></span> <span data-ttu-id="9e54c-141">Он включает несколько типичных вариантов использования преобразования данного типа:</span><span class="sxs-lookup"><span data-stu-id="9e54c-141">It includes a few of the typical uses of this type of transform:</span></span>  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.Xml;  
using System.Xml.Linq;  
  
class Program  
{  
    static XNamespace xf = "http://www.microsoft.com/LinqToXmlTransform/2007";  
    static XName at = xf + "ApplyTransforms";  
  
    // Build a transformed XML tree per the annotations  
    static XElement XForm(XElement source)  
    {  
        if (source.Annotation<XElement>() != null)  
        {  
            XElement anno = source.Annotation<XElement>();  
            return new XElement(anno.Name,  
                anno.Attributes(),  
                anno  
                .Nodes()  
                .Select(  
                    (XNode n) =>  
                    {  
                        XElement annoEl = n as XElement;  
                        if (annoEl != null)  
                        {  
                            if (annoEl.Name == at)  
                                return (object)(  
                                    source.Nodes()  
                                    .Select(  
                                        (XNode n2) =>  
                                        {  
                                            XElement e2 = n2 as XElement;  
                                            if (e2 == null)  
                                                return n2;  
                                            else  
                                                return XForm(e2);  
                                        }  
                                    )  
                                );  
                            else  
                                return n;  
                        }  
                        else  
                            return n;  
                    }  
                )  
            );  
        }  
        else  
        {  
            return new XElement(source.Name,  
                source.Attributes(),  
                source  
                    .Nodes()  
                    .Select(n =>  
                    {  
                        XElement el = n as XElement;  
                        if (el == null)  
                            return n;  
                        else  
                            return XForm(el);  
                    }  
                    )  
            );  
        }  
    }  
  
    static void Main(string[] args)  
    {  
        XElement root = new XElement("Root",  
            new XComment("A comment"),  
            new XAttribute("Att1", 123),  
            new XElement("Child", 1),  
            new XElement("Child", 2),  
            new XElement("Other",  
                new XElement("GC", 3),  
                new XElement("GC", 4)  
            ),  
            XElement.Parse(  
              "<SomeMixedContent>This is <i>an</i> element that " +  
              "<b>has</b> some mixed content</SomeMixedContent>"),  
            new XElement("AnUnchangedElement", 42)  
        );  
  
        // each of the following serves the same semantic purpose as  
        // XSLT templates and sequence constructors  
  
        // replace Child with NewChild  
        foreach (var el in root.Elements("Child"))  
            el.AddAnnotation(new XElement("NewChild", (string)el));  
  
        // replace first GC with GrandChild, add an attribute  
        foreach (var el in root.Descendants("GC").Take(1))  
            el.AddAnnotation(  
                new XElement("GrandChild",  
                    new XAttribute("ANewAttribute", 999),  
                    (string)el  
                )  
            );  
  
        // replace Other with NewOther, add new child elements around original content  
        foreach (var el in root.Elements("Other"))  
            el.AddAnnotation(  
                new XElement("NewOther",  
                    new XElement("MyNewChild", 1),  
                    // same idea as xsl:apply-templates  
                    new XElement(xf + "ApplyTransforms"),  
                    new XElement("ChildThatComesAfter")  
                )  
            );  
  
        // change name of element that has mixed content  
        root.Descendants("SomeMixedContent").First().AddAnnotation(  
            new XElement("MixedContent",  
                new XElement(xf + "ApplyTransforms")  
            )  
        );  
  
        // replace <b> with <Bold>  
        foreach (var el in root.Descendants("b"))  
            el.AddAnnotation(  
                new XElement("Bold",  
                    new XElement(xf + "ApplyTransforms")  
                )  
            );  
  
        // replace <i> with <Italic>  
        foreach (var el in root.Descendants("i"))  
            el.AddAnnotation(  
                new XElement("Italic",  
                    new XElement(xf + "ApplyTransforms")  
                )  
            );  
  
        Console.WriteLine("Before Transform");  
        Console.WriteLine("----------------");  
        Console.WriteLine(root);  
        Console.WriteLine();  
        Console.WriteLine();  
        XElement newRoot = XForm(root);  
  
        Console.WriteLine("After Transform");  
        Console.WriteLine("----------------");  
        Console.WriteLine(newRoot);  
    }  
}  
```  
  
 <span data-ttu-id="9e54c-142">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="9e54c-142">This example produces the following output:</span></span>  
  
```output  
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
  