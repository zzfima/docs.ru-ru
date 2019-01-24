---
title: Как выполнить Проверка с использованием XSD (LINQ to XML) (Visual Basic)
ms.date: 07/20/2015
ms.assetid: a0fe88d4-4e77-49e7-90de-8953feeccc21
ms.openlocfilehash: 9e4250ac1da4b25ce3f1644b38ff0e71693ecc57
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54691220"
---
# <a name="how-to-validate-using-xsd-linq-to-xml-visual-basic"></a><span data-ttu-id="1a8e4-102">Как выполнить Проверка с использованием XSD (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1a8e4-102">How to: Validate Using XSD (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="1a8e4-103">Пространство имен <xref:System.Xml.Schema> содержит методы расширения, облегчающие проверку правильности XML-дерева по XSD-файлу.</span><span class="sxs-lookup"><span data-stu-id="1a8e4-103">The <xref:System.Xml.Schema> namespace contains extension methods that make it easy to validate an XML tree against an XML Schema Definition Language (XSD) file.</span></span> <span data-ttu-id="1a8e4-104">Дополнительные сведения см. в документации метода <xref:System.Xml.Schema.Extensions.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="1a8e4-104">For more information, see the <xref:System.Xml.Schema.Extensions.Validate%2A> method documentation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a8e4-105">Пример</span><span class="sxs-lookup"><span data-stu-id="1a8e4-105">Example</span></span>  
 <span data-ttu-id="1a8e4-106">В следующем примере создается набор схем <xref:System.Xml.Schema.XmlSchemaSet>, затем с его помощью проводится проверка правильности двух объектов <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="1a8e4-106">The following example creates an <xref:System.Xml.Schema.XmlSchemaSet>, then validates two <xref:System.Xml.Linq.XDocument> objects against the schema set.</span></span> <span data-ttu-id="1a8e4-107">Правильность одного документа подтверждается, а второго - нет.</span><span class="sxs-lookup"><span data-stu-id="1a8e4-107">One of the documents is valid, the other is not.</span></span>  
  
```vb  
Dim errors As Boolean = False  
  
Private Sub XSDErrors(ByVal o As Object, ByVal e As ValidationEventArgs)  
    Console.WriteLine("{0}", e.Message)  
    errors = True  
End Sub  
  
Sub Main()  
    Dim xsdMarkup As XElement = _  
        <xsd:schema xmlns:xsd='http://www.w3.org/2001/XMLSchema'>  
            <xsd:element name='Root'>  
                <xsd:complexType>  
                    <xsd:sequence>  
                        <xsd:element name='Child1' minOccurs='1' maxOccurs='1'/>  
                        <xsd:element name='Child2' minOccurs='1' maxOccurs='1'/>  
                    </xsd:sequence>  
                </xsd:complexType>  
            </xsd:element>  
        </xsd:schema>  
    Dim schemas As XmlSchemaSet = New XmlSchemaSet()  
    schemas.Add("", xsdMarkup.CreateReader)  
  
    Dim doc1 As XDocument = _  
        <?xml version='1.0'?>  
        <Root>  
            <Child1>content1</Child1>  
            <Child2>content1</Child2>  
        </Root>  
  
    Dim doc2 As XDocument = _  
        <?xml version='1.0'?>  
        <Root>  
            <Child1>content1</Child1>  
            <Child3>content1</Child3>  
        </Root>  
  
    Console.WriteLine("Validating doc1")  
    errors = False  
    doc1.Validate(schemas, AddressOf XSDErrors)  
    Console.WriteLine("doc1 {0}", IIf(errors = True, "did not validate", "validated"))  
  
    Console.WriteLine()  
    Console.WriteLine("Validating doc2")  
    errors = False  
    doc2.Validate(schemas, AddressOf XSDErrors)  
    Console.WriteLine("doc2 {0}", IIf(errors = True, "did not validate", "validated"))  
End Sub  
```  
  
 <span data-ttu-id="1a8e4-108">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="1a8e4-108">This example produces the following output:</span></span>  
  
```  
Validating doc1  
doc1 validated  
  
Validating doc2  
The element 'Root' has invalid child element 'Child3'. List of possible elements expected: 'Child2'.  
doc2 did not validate  
```  
  
## <a name="example"></a><span data-ttu-id="1a8e4-109">Пример</span><span class="sxs-lookup"><span data-stu-id="1a8e4-109">Example</span></span>  
 <span data-ttu-id="1a8e4-110">В следующем примере проверяется, что XML-документ из [пример XML-файла: Клиенты и заказы (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md) является правильным согласно схеме из [пример XSD-файла: Клиенты и заказы](../../../../visual-basic/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders.md).</span><span class="sxs-lookup"><span data-stu-id="1a8e4-110">The following example validates that the XML document from [Sample XML File: Customers and Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md) is valid per the schema from [Sample XSD File: Customers and Orders](../../../../visual-basic/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders.md).</span></span> <span data-ttu-id="1a8e4-111">Затем в исходный XML-документ вносятся изменения.</span><span class="sxs-lookup"><span data-stu-id="1a8e4-111">It then modifies the source XML document.</span></span> <span data-ttu-id="1a8e4-112">Изменяется атрибут `CustomerID` первого клиента.</span><span class="sxs-lookup"><span data-stu-id="1a8e4-112">It changes the `CustomerID` attribute on the first customer.</span></span> <span data-ttu-id="1a8e4-113">После этого изменения заказы ссылаются на несуществующего клиента, поэтому XML-документ больше не должен пройти проверку правильности.</span><span class="sxs-lookup"><span data-stu-id="1a8e4-113">After the change, orders will then refer to a customer that does not exist, so the XML document will no longer validate.</span></span>  
  
 <span data-ttu-id="1a8e4-114">В этом примере используется следующий XML-документ: [Пример XML-файла: Клиенты и заказы (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="1a8e4-114">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="1a8e4-115">В этом примере используется следующая XSD-схема: [Образец XSD-файла: Клиенты и заказы](../../../../visual-basic/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders.md).</span><span class="sxs-lookup"><span data-stu-id="1a8e4-115">This example uses the following XSD schema: [Sample XSD File: Customers and Orders](../../../../visual-basic/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders.md).</span></span>  
  
```vb  
Dim errors As Boolean = False  
  
Private Sub XSDErrors(ByVal o As Object, ByVal e As ValidationEventArgs)  
    Console.WriteLine("{0}", e.Message)  
    errors = True  
End Sub  
  
Sub Main()  
    Dim schemas As XmlSchemaSet = New XmlSchemaSet()  
    schemas.Add("", "CustomersOrders.xsd")  
  
    Console.WriteLine("Attempting to validate")  
    Dim custOrdDoc As XDocument = XDocument.Load("CustomersOrders.xml")  
    errors = False  
    custOrdDoc.Validate(schemas, AddressOf XSDErrors)  
    Console.WriteLine("custOrdDoc {0}", IIf(errors, "did not validate", "validated"))  
  
    Console.WriteLine()  
    ' Modify the source document so that it will not validate.  
    custOrdDoc.<Root>.<Orders>.<Order>.<CustomerID>(0).Value = "AAAAA"  
    Console.WriteLine("Attempting to validate after modification")  
    errors = False  
    custOrdDoc.Validate(schemas, AddressOf XSDErrors)  
    Console.WriteLine("custOrdDoc {0}", IIf(errors, "did not validate", "validated"))  
End Sub  
```  
  
 <span data-ttu-id="1a8e4-116">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="1a8e4-116">This example produces the following output:</span></span>  
  
```  
Attempting to validate  
custOrdDoc validated  
  
Attempting to validate after modification  
The key sequence 'AAAAA' in Keyref fails to refer to some key.  
custOrdDoc did not validate  
```  
  
## <a name="see-also"></a><span data-ttu-id="1a8e4-117">См. также</span><span class="sxs-lookup"><span data-stu-id="1a8e4-117">See also</span></span>
- <xref:System.Xml.Schema.Extensions.Validate%2A>
- [<span data-ttu-id="1a8e4-118">Создание деревьев XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1a8e4-118">Creating XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
