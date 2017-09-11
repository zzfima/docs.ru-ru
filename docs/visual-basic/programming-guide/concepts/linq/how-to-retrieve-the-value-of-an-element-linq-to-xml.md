---
title: "Практическое руководство: извлечение значений элемента (LINQ to XML) (Visual Basic) | Документы Microsoft"
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
ms.assetid: 76b9b2a5-b3ba-49da-ba74-82100e1bd21c
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: be5eebc382f83819fd978554f830b6ba12227902
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017


---
# <a name="how-to-retrieve-the-value-of-an-element-linq-to-xml-visual-basic"></a><span data-ttu-id="e8ec4-102">Практическое руководство: извлечение значений элемента (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e8ec4-102">How to: Retrieve the Value of an Element (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="e8ec4-103">В этом разделе показано получение значений элементов.</span><span class="sxs-lookup"><span data-stu-id="e8ec4-103">This topic shows how to get the value of elements.</span></span> <span data-ttu-id="e8ec4-104">Это можно сделать двумя основными способами.</span><span class="sxs-lookup"><span data-stu-id="e8ec4-104">There are two main ways to do this.</span></span> <span data-ttu-id="e8ec4-105">Один способ состоит в приведении <xref:System.Xml.Linq.XElement>или <xref:System.Xml.Linq.XAttribute>в требуемый тип.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="e8ec4-105">One way is to cast an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XAttribute> to the desired type.</span></span> <span data-ttu-id="e8ec4-106">Оператор явного преобразования, который преобразует содержимое элемента или атрибута в указанный тип и присваивает полученное значение указанной переменной.</span><span class="sxs-lookup"><span data-stu-id="e8ec4-106">The explicit conversion operator then converts the contents of the element or attribute to the specified type and assigns it to your variable.</span></span> <span data-ttu-id="e8ec4-107">Кроме того, можно использовать <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName>свойства или <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName>свойство.</xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName> </xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="e8ec4-107">Alternatively, you can use the <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName> property or the <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName> property.</span></span>  
  
 <span data-ttu-id="e8ec4-108">С помощью Visual Basic лучшим подходом является использование <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName>свойство.</xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="e8ec4-108">With Visual Basic, the best approach is to use the <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8ec4-109">Пример</span><span class="sxs-lookup"><span data-stu-id="e8ec4-109">Example</span></span>  
 <span data-ttu-id="e8ec4-110">Чтобы получить значение элемента, нужно просто привести <xref:System.Xml.Linq.XElement>объекта к желаемому типу.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="e8ec4-110">To retrieve the value of an element, you just cast the <xref:System.Xml.Linq.XElement> object to your desired type.</span></span> <span data-ttu-id="e8ec4-111">Всегда можно привести элемент к строке следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e8ec4-111">You can always cast an element to a string, as follows:</span></span>  
  
```vb  
Dim e As XElement = <StringElement>abcde</StringElement>  
Console.WriteLine(e)  
Console.WriteLine("Value of e:" & e.Value)  
```  
  
 <span data-ttu-id="e8ec4-112">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="e8ec4-112">This example produces the following output:</span></span>  
  
```  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a><span data-ttu-id="e8ec4-113">Пример</span><span class="sxs-lookup"><span data-stu-id="e8ec4-113">Example</span></span>  
 <span data-ttu-id="e8ec4-114">Также можно приводить элементы к типам, отличным от строковых.</span><span class="sxs-lookup"><span data-stu-id="e8ec4-114">You can also cast elements to types other than string.</span></span> <span data-ttu-id="e8ec4-115">Например, если имеется элемент, содержащий целое число, его можно привести к типу `int`, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="e8ec4-115">For example, if you have an element that contains an integer, you can cast it to `int`, as shown in the following code:</span></span>  
  
```vb  
Dim e As XElement = <Age>44</Age>  
Console.WriteLine(e)  
Console.WriteLine("Value of e:" & CInt(e))  
```  
  
 <span data-ttu-id="e8ec4-116">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="e8ec4-116">This example produces the following output:</span></span>  
  
```  
<Age>44</Age>  
Value of e:44  
```  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="e8ec4-117">provides explicit cast operators for the following data types: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`, and `GUID?`.</span><span class="sxs-lookup"><span data-stu-id="e8ec4-117"> provides explicit cast operators for the following data types: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`, and `GUID?`.</span></span>  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="e8ec4-118">предоставляет аналогичные операторы приведения для <xref:System.Xml.Linq.XAttribute>объектов.</xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="e8ec4-118"> provides the same cast operators for <xref:System.Xml.Linq.XAttribute> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8ec4-119">Пример</span><span class="sxs-lookup"><span data-stu-id="e8ec4-119">Example</span></span>  
 <span data-ttu-id="e8ec4-120">Можно использовать <xref:System.Xml.Linq.XElement.Value%2A>свойство для извлечения содержимого элемента:</xref:System.Xml.Linq.XElement.Value%2A></span><span class="sxs-lookup"><span data-stu-id="e8ec4-120">You can use the <xref:System.Xml.Linq.XElement.Value%2A> property to retrieve the contents of an element:</span></span>  
  
```vb  
Dim e As XElement = <StringElement>abcde</StringElement>  
Console.WriteLine(e)  
Console.WriteLine("Value of e:" & e.Value)  
```  
  
 <span data-ttu-id="e8ec4-121">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="e8ec4-121">This example produces the following output:</span></span>  
  
```  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a><span data-ttu-id="e8ec4-122">Пример</span><span class="sxs-lookup"><span data-stu-id="e8ec4-122">Example</span></span>  
 <span data-ttu-id="e8ec4-123">Иногда осуществляются попытки получить значение элемента, в отношении которого неизвестно, существует ли он.</span><span class="sxs-lookup"><span data-stu-id="e8ec4-123">Sometimes you try to retrieve the value of an element even though you are not sure it exists.</span></span> <span data-ttu-id="e8ec4-124">В этом случае при назначении элемент привести тип nullable (либо `string` или одного из таких типов в [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)]), если элемент не существует, то переменной просто присваивается значение `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="e8ec4-124">In this case, when you assign the casted element to a nullable type (either `string` or one of the nullable types in the [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)]), if the element does not exist the assigned variable is just set to `Nothing`.</span></span> <span data-ttu-id="e8ec4-125">В следующем коде показано, что если элемент может существовать или не существовать, проще использовать приведение типа, а не использовать <xref:System.Xml.Linq.XElement.Value%2A>свойство.</xref:System.Xml.Linq.XElement.Value%2A></span><span class="sxs-lookup"><span data-stu-id="e8ec4-125">The following code shows that when the element might or might not exist, it is easier to use casting than to use the <xref:System.Xml.Linq.XElement.Value%2A> property.</span></span>  
  
```vb  
Dim root As XElement = <Root>  
                           <Child1>child 1 content</Child1>  
                           <Child2>2</Child2>  
                       </Root>  
  
' The following assignments show why it is easier to use  
' casting when the element might or might not exist.  
  
Dim c1 As String = CStr(root.Element("Child1"))  
Console.WriteLine("c1:{0}", IIf(c1 Is Nothing, "element does not exist", c1))  
  
Dim c2 As Nullable(Of Integer) = CType(root.Element("Child2"), Nullable(Of Integer))  
Console.WriteLine("c2:{0}", IIf(Not (c2.HasValue), "element does not exist", c2.ToString()))  
  
Dim c3 As String = CStr(root.Element("Child3"))  
Console.WriteLine("c3:{0}", IIf(c3 Is Nothing, "element does not exist", c3))  
  
Dim c4 As Nullable(Of Integer) = CType(root.Element("Child4"), Nullable(Of Integer))  
Console.WriteLine("c4:{0}", IIf(Not (c4.HasValue), "element does not exist", c4.ToString()))  
  
Console.WriteLine()  
  
' The following assignments show the required code when using  
' the Value property when the attribute might or might not exist.  
' Notice that this is more difficult than the casting approach.  
  
Dim e1 As XElement = root.Element("Child1")  
Dim v1 As String  
If (e1 Is Nothing) Then  
    v1 = Nothing  
Else  
    v1 = e1.Value  
End If  
Console.WriteLine("v1:{0}", IIf(v1 Is Nothing, "element does not exist", v1))  
  
Dim e2 As XElement = root.Element("Child2")  
Dim v2 As Nullable(Of Integer)  
If (e2 Is Nothing) Then  
    v2 = Nothing  
Else  
    v2 = e2.Value  
End If  
Console.WriteLine("v2:{0}", IIf(Not (v2.HasValue), "element does not exist", v2))  
  
Dim e3 As XElement = root.Element("Child3")  
Dim v3 As String  
If (e3 Is Nothing) Then  
    v3 = Nothing  
Else  
    v3 = e3.Value  
End If  
Console.WriteLine("v3:{0}", IIf(v3 Is Nothing, "element does not exist", v3))  
  
Dim e4 As XElement = root.Element("Child4")  
Dim v4 As Nullable(Of Integer)  
If (e4 Is Nothing) Then  
    v4 = Nothing  
Else  
    v4 = e4.Value  
End If  
Console.WriteLine("v4:{0}", IIf(Not (v4.HasValue), "element does not exist", v4))  
```  
  
 <span data-ttu-id="e8ec4-126">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="e8ec4-126">This code produces the following output:</span></span>  
  
```  
c1:child 1 content  
c2:2  
c3:element does not exist  
c4:element does not exist  
  
v1:child 1 content  
v2:2  
v3:element does not exist  
v4:element does not exist  
```  
  
 <span data-ttu-id="e8ec4-127">Как правило, использование приведения для получения содержимого элементов и атрибутов позволяет создавать более простой код.</span><span class="sxs-lookup"><span data-stu-id="e8ec4-127">In general, you can write simpler code when using casting to retrieve the contents of elements and attributes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8ec4-128">См. также</span><span class="sxs-lookup"><span data-stu-id="e8ec4-128">See Also</span></span>  
 [<span data-ttu-id="e8ec4-129">Оси LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e8ec4-129">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
