---
title: Введение в XML-литералов в Visual Basic2
ms.date: 07/20/2015
ms.assetid: 94fc0e03-978e-4c08-ab6c-0dc3c1e64f10
ms.openlocfilehash: 68ba1e018d4ad9501532745a88090f0f756b5c17
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58841305"
---
# <a name="introduction-to-xml-literals-in-visual-basic"></a><span data-ttu-id="3c94e-102">Знакомство с литералами XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3c94e-102">Introduction to XML Literals in Visual Basic</span></span>
<span data-ttu-id="3c94e-103">Этот раздел содержит сведения о создании деревьев XML в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3c94e-103">This section provides information about creating XML trees in Visual Basic.</span></span>  
  
 <span data-ttu-id="3c94e-104">Сведения об использовании результатов запросов LINQ как содержимого XML-дерева см. в разделе [функциональное построение (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-construction-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="3c94e-104">For information about using the results of LINQ queries as the content for an XML tree, see [Functional Construction (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-construction-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="3c94e-105">Дополнительные сведения о XML-литералов в Visual Basic, см. в разделе [Общие сведения о LINQ to XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="3c94e-105">For more information on XML literals in Visual Basic, see [Overview of LINQ to XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md).</span></span>  
  
## <a name="creating-xml-trees"></a><span data-ttu-id="3c94e-106">Создание деревьев XML</span><span class="sxs-lookup"><span data-stu-id="3c94e-106">Creating XML Trees</span></span>  
 <span data-ttu-id="3c94e-107">В следующем примере показано, как создать объект <xref:System.Xml.Linq.XElement>. В этом случае дерево `contacts`:</span><span class="sxs-lookup"><span data-stu-id="3c94e-107">The following example shows how to create an <xref:System.Xml.Linq.XElement>, in this case `contacts`:</span></span>  
  
```vb  
Dim contacts As XElement = _  
    <Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone>206-555-0144</Phone>  
            <Address>  
                <Street1>123 Main St</Street1>  
                <City>Mercer Island</City>  
                <State>WA</State>  
                <Postal>68042</Postal>  
            </Address>  
        </Contact>  
    </Contacts>  
```  
  
### <a name="creating-an-xelement-with-simple-content"></a><span data-ttu-id="3c94e-108">Создание объекта XElement с простым содержимым</span><span class="sxs-lookup"><span data-stu-id="3c94e-108">Creating an XElement with Simple Content</span></span>  
 <span data-ttu-id="3c94e-109">Следующим образом можно создать объект <xref:System.Xml.Linq.XElement> с простым содержимым.</span><span class="sxs-lookup"><span data-stu-id="3c94e-109">You can create an <xref:System.Xml.Linq.XElement> that contains simple content, as follows:</span></span>  
  
```vb  
Dim n as XElement = <Customer>Adventure Works</Customer>  
Console.WriteLine(n)   
```  
  
 <span data-ttu-id="3c94e-110">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="3c94e-110">This example produces the following output:</span></span>  
  
```xml  
<Customer>Adventure Works</Customer>  
```  
  
### <a name="creating-an-empty-element"></a><span data-ttu-id="3c94e-111">Создание пустого элемента</span><span class="sxs-lookup"><span data-stu-id="3c94e-111">Creating an Empty Element</span></span>  
 <span data-ttu-id="3c94e-112">Следующим образом можно создать пустой объект <xref:System.Xml.Linq.XElement>:</span><span class="sxs-lookup"><span data-stu-id="3c94e-112">You can create an empty <xref:System.Xml.Linq.XElement>, as follows:</span></span>  
  
```vb  
Dim n As XElement = <Customer/>  
Console.WriteLine(n)  
```  
  
 <span data-ttu-id="3c94e-113">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="3c94e-113">This example produces the following output:</span></span>  
  
```xml  
<Customer />  
```  
  
### <a name="using-embedded-expressions"></a><span data-ttu-id="3c94e-114">Использование внедренных выражений</span><span class="sxs-lookup"><span data-stu-id="3c94e-114">Using Embedded Expressions</span></span>  
 <span data-ttu-id="3c94e-115">Важной характеристикой XML-литералов является использование внедренных выражений.</span><span class="sxs-lookup"><span data-stu-id="3c94e-115">An important feature of XML literals is that they allow embedded expressions.</span></span> <span data-ttu-id="3c94e-116">Внедренные выражения позволяют вычислять выражения и вставлять результаты вычисления в XML-дерево.</span><span class="sxs-lookup"><span data-stu-id="3c94e-116">Embedded expressions enable you to evaluate an expression and insert the results of the expression into the XML tree.</span></span> <span data-ttu-id="3c94e-117">Если результат выражения имеет тип объекта <xref:System.Xml.Linq.XElement>, элемент вставляется в дерево.</span><span class="sxs-lookup"><span data-stu-id="3c94e-117">If the expression evaluates to a type of <xref:System.Xml.Linq.XElement>, an element is inserted into the tree.</span></span> <span data-ttu-id="3c94e-118">Если результат выражения имеет тип объекта <xref:System.Xml.Linq.XAttribute>, атрибут вставляется в дерево.</span><span class="sxs-lookup"><span data-stu-id="3c94e-118">If the expression evaluates to a type of <xref:System.Xml.Linq.XAttribute>, an attribute is inserted into the tree.</span></span> <span data-ttu-id="3c94e-119">Элементы и атрибуты можно вставлять в дерево, только если они допустимы.</span><span class="sxs-lookup"><span data-stu-id="3c94e-119">You can insert elements and attributes into the tree only where they are valid.</span></span>  
  
 <span data-ttu-id="3c94e-120">Важно отметить, что только простое выражение может входить во внедренное выражение.</span><span class="sxs-lookup"><span data-stu-id="3c94e-120">It is important to note that only a single expression can go into an embedded expression.</span></span> <span data-ttu-id="3c94e-121">Можно внедрять несколько инструкций.</span><span class="sxs-lookup"><span data-stu-id="3c94e-121">You cannot embed multiple statements.</span></span> <span data-ttu-id="3c94e-122">Если выражение выходит за пределы одной строки, нужно использовать знак объединения строк.</span><span class="sxs-lookup"><span data-stu-id="3c94e-122">If an expression extends beyond a single line, you must use the line continuation character.</span></span>  
  
 <span data-ttu-id="3c94e-123">Если использовать внедренное выражение для добавления существующих узлов (включая элементы) и атрибутов в новое XML-дерево и если существующие узлы уже имеют родителей, узлы копируются.</span><span class="sxs-lookup"><span data-stu-id="3c94e-123">If you use an embedded expression to add existing nodes (including elements) and attributes to a new XML tree and if the existing nodes are already parented, the nodes are cloned.</span></span> <span data-ttu-id="3c94e-124">Скопированные узлы присоединяются к новому XML-дереву.</span><span class="sxs-lookup"><span data-stu-id="3c94e-124">The newly cloned nodes are attached to the new XML tree.</span></span> <span data-ttu-id="3c94e-125">Если существующие узлы не имеют родителей, узлы просто присоединяются к новому XML-дереву.</span><span class="sxs-lookup"><span data-stu-id="3c94e-125">If the existing nodes are not parented, the nodes are simply attached to the new XML tree.</span></span> <span data-ttu-id="3c94e-126">Это демонстрирует последний пример из данного раздела.</span><span class="sxs-lookup"><span data-stu-id="3c94e-126">The last example in this topic demonstrates this.</span></span>  
  
 <span data-ttu-id="3c94e-127">В следующем примере используется внедренное выражение для вставки элементов в дерево:</span><span class="sxs-lookup"><span data-stu-id="3c94e-127">The following example uses an embedded expression to insert an element into the tree:</span></span>  
  
```vb  
xmlTree1 As XElement = _  
    <Root>  
        <Child>Contents</Child>  
    </Root>  
Dim xmlTree2 As XElement = _  
    <Root>  
        <%= xmlTree1.<Child> %>  
    </Root>  
Console.WriteLine(xmlTree2)  
```  
  
 <span data-ttu-id="3c94e-128">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="3c94e-128">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child>Contents</Child>  
</Root>  
```  
  
### <a name="using-embedded-expressions-for-content"></a><span data-ttu-id="3c94e-129">Использование внедренных выражений в содержимом</span><span class="sxs-lookup"><span data-stu-id="3c94e-129">Using Embedded Expressions for Content</span></span>  
 <span data-ttu-id="3c94e-130">Можно использовать внедренное выражение для создания содержимого элемента:</span><span class="sxs-lookup"><span data-stu-id="3c94e-130">You can use an embedded expression to supply the content of an element:</span></span>  
  
```vb  
Dim str As String  
str = "Some content"  
Dim root As XElement = <Root><%= str %></Root>  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="3c94e-131">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="3c94e-131">This example produces the following output:</span></span>  
  
```xml  
<Root>Some content</Root>  
```  
  
### <a name="using-a-linq-query-in-an-embedded-expression"></a><span data-ttu-id="3c94e-132">Использование запросов LINQ во внедренном выражении</span><span class="sxs-lookup"><span data-stu-id="3c94e-132">Using a LINQ Query in an Embedded Expression</span></span>  
 <span data-ttu-id="3c94e-133">Можно использовать результаты запросов LINQ для создания содержимого элемента:</span><span class="sxs-lookup"><span data-stu-id="3c94e-133">You can use the results of a LINQ query for the content of an element:</span></span>  
  
```vb  
Dim arr As Integer() = {1, 2, 3}  
  
Dim n As XElement = _  
    <Root>  
        <%= From i In arr Select <Child><%= i %></Child> %>  
    </Root>  
  
Console.WriteLine(n)  
```  
  
 <span data-ttu-id="3c94e-134">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="3c94e-134">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Child>3</Child>  
</Root>  
```  
  
### <a name="using-embedded-expressions-for-node-names"></a><span data-ttu-id="3c94e-135">Использование внедренных выражений для создания имен узлов</span><span class="sxs-lookup"><span data-stu-id="3c94e-135">Using Embedded Expressions for Node Names</span></span>  
 <span data-ttu-id="3c94e-136">Можно также использовать внедренные выражения для вычисления имен атрибутов, значений атрибутов, имен элементов и значений элементов:</span><span class="sxs-lookup"><span data-stu-id="3c94e-136">You can also use embedded expressions to calculate attribute names, attribute values, element names, and element values:</span></span>  
  
```vb  
Dim eleName As String = "ele"  
Dim attName As String = "att"  
Dim attValue As String = "aValue"  
Dim eleValue As String = "eValue"  
Dim n As XElement = _  
    <Root <%= attName %>=<%= attValue %>>  
        <<%= eleName %>>  
            <%= eleValue %>  
        </>  
    </Root>  
Console.WriteLine(n)  
```  
  
 <span data-ttu-id="3c94e-137">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="3c94e-137">This example produces the following output:</span></span>  
  
```xml  
<Root att="aValue">  
  <ele>eValue</ele>  
</Root>  
```  
  
### <a name="cloning-vs-attaching"></a><span data-ttu-id="3c94e-138">Сравнение клонирования и присоединения</span><span class="sxs-lookup"><span data-stu-id="3c94e-138">Cloning vs. Attaching</span></span>  
 <span data-ttu-id="3c94e-139">Как уже было сказано, если использовать внедренное выражение для добавления существующих узлов (включая элементы) и атрибутов в новое XML-дерево и если существующие узлы уже имеют родителей, узлы копируются и присоединяются к новому XML-дереву.</span><span class="sxs-lookup"><span data-stu-id="3c94e-139">As mentioned earlier, if you use an embedded expression to add existing nodes (including elements) and attributes to a new XML tree, if the existing nodes are already parented, the nodes are cloned and the newly cloned nodes are attached to the new XML tree.</span></span> <span data-ttu-id="3c94e-140">Если существующие узлы не имеют родителей, узлы просто присоединяются к новому XML-дереву.</span><span class="sxs-lookup"><span data-stu-id="3c94e-140">If the existing nodes are not parented, they are simply attached to the new XML tree.</span></span>  
  
```vb  
' Create a tree with a child element.  
Dim xmlTree1 As XElement = _  
    <Root>  
        <Child1>1</Child1>  
    </Root>  
  
' Create an element that is not parented.  
Dim child2 As XElement = <Child2>2</Child2>  
  
' Create a tree and add Child1 and Child2 to it.  
Dim xmlTree2 As XElement = _  
    <Root>  
        <%= xmlTree1.<Child1>(0) %>  
        <%= child2 %>  
    </Root>  
  
' Compare Child1 identity.  
Console.WriteLine("Child1 was {0}", _  
    IIf(xmlTree1.Element("Child1") Is xmlTree2.Element("Child1"), _  
    "attached", "cloned"))  
  
' Compare Child2 identity.  
Console.WriteLine("Child2 was {0}", _  
    IIf(child2 Is xmlTree2.Element("Child2"), _  
    "attached", "cloned"))  
```  
  
 <span data-ttu-id="3c94e-141">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="3c94e-141">This example produces the following output:</span></span>  
  
```  
Child1 was cloned  
Child2 was attached  
```  
  
## <a name="see-also"></a><span data-ttu-id="3c94e-142">См. также</span><span class="sxs-lookup"><span data-stu-id="3c94e-142">See also</span></span>

- [<span data-ttu-id="3c94e-143">Создание деревьев XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3c94e-143">Creating XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
