---
title: Практическое руководство. Проецирование нового типа (LINQ to XML) (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 8cfb24f5-89b2-4cfb-b85d-e7963f8f1845
ms.openlocfilehash: a94180705674c8aee3ce45607f89fdbba1c873b7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58834664"
---
# <a name="how-to-project-a-new-type-linq-to-xml-visual-basic"></a><span data-ttu-id="fc276-102">Практическое руководство. Проецирование нового типа (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc276-102">How to: Project a New Type (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="fc276-103">В других примерах данного раздела показаны запросы, возвращающие результаты в виде значений <xref:System.Collections.Generic.IEnumerable%601> типа <xref:System.Xml.Linq.XElement>, значений <xref:System.Collections.Generic.IEnumerable%601> типа `string` и значений <xref:System.Collections.Generic.IEnumerable%601> типа `int`.</span><span class="sxs-lookup"><span data-stu-id="fc276-103">Other examples in this section have shown queries that return results as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601> of `string`, and <xref:System.Collections.Generic.IEnumerable%601> of `int`.</span></span> <span data-ttu-id="fc276-104">Это наиболее распространенные типы результатов, но подходят не для всех сценариев.</span><span class="sxs-lookup"><span data-stu-id="fc276-104">These are common result types, but they are not appropriate for every scenario.</span></span> <span data-ttu-id="fc276-105">Во многих случаях требуется, чтобы запросы возвращали <xref:System.Collections.Generic.IEnumerable%601> какого-то другого типа.</span><span class="sxs-lookup"><span data-stu-id="fc276-105">In many cases you will want your queries to return an <xref:System.Collections.Generic.IEnumerable%601> of some other type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc276-106">Пример</span><span class="sxs-lookup"><span data-stu-id="fc276-106">Example</span></span>  
 <span data-ttu-id="fc276-107">В данном примере показано, как создавать экземпляры объектов в предложении `Select`.</span><span class="sxs-lookup"><span data-stu-id="fc276-107">This example shows how to instantiate objects in the `Select` clause.</span></span> <span data-ttu-id="fc276-108">Сначала в коде определяется новый класс с помощью конструктора, а затем модифицируется инструкция `Select`, чтобы это выражение представляло новый экземпляр нового класса.</span><span class="sxs-lookup"><span data-stu-id="fc276-108">The code first defines a new class with a constructor, and then modifies the `Select` statement so that the expression is a new instance of the new class.</span></span>  
  
 <span data-ttu-id="fc276-109">В этом примере используется следующий XML-документ: [Пример XML-файла. Типичный заказ на покупку (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="fc276-109">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span>  
  
```vb  
Public Class NameQty  
    Public name As String  
    Public qty As Integer  
    Public Sub New(ByVal n As String, ByVal q As Integer)  
        name = n  
        qty = q  
    End Sub  
End Class  
  
Public Class Program  
    Shared Sub Main()  
        Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
  
        Dim nqList As IEnumerable(Of NameQty) = _  
            From n In po...<Item> _  
            Select New NameQty( _  
                n.<ProductName>.Value, CInt(n.<Quantity>.Value))  
  
        For Each n As NameQty In nqList  
            Console.WriteLine(n.name & ":" & n.qty)  
        Next  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="fc276-110">В данном примере используется метод `M:System.Xml.Linq.XElement.Element`, представленный в разделе [Практическое руководство. Извлечение одного дочернего элемента (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="fc276-110">This example uses the `M:System.Xml.Linq.XElement.Element` method that was introduced in the topic [How to: Retrieve a Single Child Element (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md).</span></span> <span data-ttu-id="fc276-111">В нем также используется приведение для получения значений элементов, возвращаемых методом `M:System.Xml.Linq.XElement.Element`.</span><span class="sxs-lookup"><span data-stu-id="fc276-111">It also uses casts to retrieve the values of the elements that are returned by the `M:System.Xml.Linq.XElement.Element` method.</span></span>  
  
 <span data-ttu-id="fc276-112">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="fc276-112">This example produces the following output:</span></span>  
  
```  
Lawnmower:1  
Baby Monitor:2  
```  
  
## <a name="see-also"></a><span data-ttu-id="fc276-113">См. также</span><span class="sxs-lookup"><span data-stu-id="fc276-113">See also</span></span>

- [<span data-ttu-id="fc276-114">Проекции и преобразования (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc276-114">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)
