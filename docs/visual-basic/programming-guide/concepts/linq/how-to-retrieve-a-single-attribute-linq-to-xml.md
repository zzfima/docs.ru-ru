---
title: "Практическое руководство: получение одного атрибута (LINQ to XML) (Visual Basic) | Документы Microsoft"
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
ms.assetid: 11b938d7-c011-4048-900e-8b9183c41c94
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 7b4242e051c6171c51c6ace12798e54ae7374e02
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017


---
# <a name="how-to-retrieve-a-single-attribute-linq-to-xml-visual-basic"></a><span data-ttu-id="2419a-102">Практическое руководство: получение одного атрибута (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2419a-102">How to: Retrieve a Single Attribute (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="2419a-103">В этом разделе приведены объяснения способа получения одного атрибута элемента при условии, что название атрибута известно.</span><span class="sxs-lookup"><span data-stu-id="2419a-103">This topic explains how to retrieve a single attribute of an element, given the attribute name.</span></span> <span data-ttu-id="2419a-104">Это полезно для составления выражений запросов, при которых требуется найти элемент с определенным атрибутом.</span><span class="sxs-lookup"><span data-stu-id="2419a-104">This is useful for writing query expressions where you want to find an element that has a particular attribute.</span></span>  
  
 <span data-ttu-id="2419a-105"><xref:System.Xml.Linq.XElement.Attribute%2A>Метод <xref:System.Xml.Linq.XElement>возвращает <xref:System.Xml.Linq.XAttribute>с указанным именем.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement.Attribute%2A></span><span class="sxs-lookup"><span data-stu-id="2419a-105">The <xref:System.Xml.Linq.XElement.Attribute%2A> method of the <xref:System.Xml.Linq.XElement> class returns the <xref:System.Xml.Linq.XAttribute> with the specified name.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2419a-106">Пример</span><span class="sxs-lookup"><span data-stu-id="2419a-106">Example</span></span>  
 <span data-ttu-id="2419a-107">В следующем примере используется <xref:System.Xml.Linq.XElement.Attribute%2A>метод.</xref:System.Xml.Linq.XElement.Attribute%2A></span><span class="sxs-lookup"><span data-stu-id="2419a-107">The following example uses the <xref:System.Xml.Linq.XElement.Attribute%2A> method.</span></span>  
  
```vb  
Dim cust As XElement = <PhoneNumbers>  
                           <Phone type="home">555-555-5555</Phone>  
                           <Phone type="work">555-555-6666</Phone>  
                       </PhoneNumbers>  
Dim elList = From el In cust...<Phone>  
For Each e As XElement In elList  
    Console.WriteLine(e.@type)  
Next  
```  
  
 <span data-ttu-id="2419a-108">В этом примере выполняется поиск всех потомков в дереве с названием `Phone`, затем атрибута с названием `type`.</span><span class="sxs-lookup"><span data-stu-id="2419a-108">This example finds all the descendants in the tree named `Phone`, and then finds the attribute named `type`.</span></span>  
  
 <span data-ttu-id="2419a-109">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="2419a-109">This code produces the following output:</span></span>  
  
```  
home  
work  
```  
  
## <a name="example"></a><span data-ttu-id="2419a-110">Пример</span><span class="sxs-lookup"><span data-stu-id="2419a-110">Example</span></span>  
 <span data-ttu-id="2419a-111">Если вы хотите получить значение атрибута, можно его, так же, как при работе с <xref:System.Xml.Linq.XElement>объектов.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="2419a-111">If you want to retrieve the value of the attribute, you can cast it, just as you do for with <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="2419a-112">В следующем примере это показано.</span><span class="sxs-lookup"><span data-stu-id="2419a-112">The following example demonstrates this.</span></span>  
  
```vb  
Dim cust As XElement = <PhoneNumbers>  
                           <Phone type="home">555-555-5555</Phone>  
                           <Phone type="work">555-555-6666</Phone>  
                       </PhoneNumbers>  
Dim elList As IEnumerable(Of XElement) = _  
    From el In cust...<Phone> _  
    Select el  
For Each el As XElement In elList  
    Console.WriteLine(el.@type)  
Next  
```  
  
 <span data-ttu-id="2419a-113">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="2419a-113">This code produces the following output:</span></span>  
  
```  
home  
work  
```  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="2419a-114">provides explicit cast operators for the <xref:System.Xml.Linq.XAttribute> class to `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`, and `GUID?`.</xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="2419a-114"> provides explicit cast operators for the <xref:System.Xml.Linq.XAttribute> class to `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`, and `GUID?`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2419a-115">Пример</span><span class="sxs-lookup"><span data-stu-id="2419a-115">Example</span></span>  
 <span data-ttu-id="2419a-116">Следующий пример демонстрирует тот же код атрибута, что и в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="2419a-116">The following example shows the same code for an attribute that is in a namespace.</span></span> <span data-ttu-id="2419a-117">Дополнительные сведения см. в разделе [работа с пространствами имен XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="2419a-117">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim cust As XElement = _  
            <aw:PhoneNumbers>  
                <aw:Phone aw:type="home">555-555-5555</aw:Phone>  
                <aw:Phone aw:type="work">555-555-6666</aw:Phone>  
            </aw:PhoneNumbers>  
        Dim elList As IEnumerable(Of XElement) = _  
            From el In cust...<aw:Phone> _  
            Select el  
        For Each el As XElement In elList  
            Console.WriteLine(el.@aw:type)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="2419a-118">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="2419a-118">This code produces the following output:</span></span>  
  
```  
home  
work  
```  
  
## <a name="see-also"></a><span data-ttu-id="2419a-119">См. также</span><span class="sxs-lookup"><span data-stu-id="2419a-119">See Also</span></span>  
 [<span data-ttu-id="2419a-120">Оси LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2419a-120">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
