---
title: Практическое руководство. Создание запросов со сложной фильтрацией
ms.date: 07/20/2015
ms.assetid: bf286ffc-7990-4b00-a4eb-ee3d70129950
ms.openlocfilehash: 28e84b7785948e9d50c08438494b89c906ab8505
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344456"
---
# <a name="how-to-write-queries-with-complex-filtering-visual-basic"></a>Как писать запросы со сложной фильтрацией (Visual Basic)
Иногда возникает необходимость в написании запросов LINQ to XML с комплексной фильтрацией. Например, может потребоваться найти все элементы, имеющие дочерние элементы с определенным именем и значением. В этом разделе приводится пример написания запроса с комплексной фильтрацией.  
  
## <a name="example"></a>Пример  
 В этом примере показано, как найти все элементы `PurchaseOrder`, имеющие дочерний элемент `Address` с атрибутом `Type`, равным «Доставка», и дочерним элементом `State`, равным «NY». В нем используется вложенный запрос в предложении `Where`, а оператор `Any` возвращает значение `True`, если коллекция содержит элементы.  
  
 В этом примере используется следующий XML-документ: [Пример XML-файла. Несколько заказов на покупку (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).  
  
 Дополнительные сведения об операторе `Any` см. в разделе [операции квантификатора (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/quantifier-operations.md).  
  
```vb  
Dim root As XElement = XElement.Load("PurchaseOrders.xml")  
Dim purchaseOrders As IEnumerable(Of XElement) = _  
    From el In root.<PurchaseOrder> _  
    Where _  
        (From add In el.<Address> _  
        Where _  
             add.@Type = "Shipping" And _  
             add.<State>.Value = "NY" _  
        Select add) _  
    .Any() _  
    Select el  
For Each el As XElement In purchaseOrders  
    Console.WriteLine(el.@PurchaseOrderNumber)  
Next  
```  
  
 Этот код выводит следующие результаты:  
  
```console  
99505  
```  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует тот же запрос XML, что и в пространстве имен. Дополнительные сведения см. в разделе [Общие сведения о пространствах имен (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).  
  
 В этом примере используется следующий XML-документ: [Пример XML-файла. Несколько заказов на покупку в пространстве имен](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md).  
  
```vb  
Imports <xmlns:aw='http://www.adventure-works.com'>  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = XElement.Load("PurchaseOrdersInNamespace.xml")  
        Dim purchaseOrders As IEnumerable(Of XElement) = _  
            From el In root.<aw:PurchaseOrder> _  
            Where _  
                (From add In el.<aw:Address> _  
                Where _  
                     add.@aw:Type = "Shipping" And _  
                     add.<aw:State>.Value = "NY" _  
                Select add) _  
            .Any() _  
            Select el  
        For Each el As XElement In purchaseOrders  
            Console.WriteLine(el.@aw:PurchaseOrderNumber)  
        Next  
    End Sub  
End Module  
```  
  
 Этот код выводит следующие результаты:  
  
```console  
99505  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [Основные запросы (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
- [Свойство дочерней оси XML](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)
- [Свойство оси атрибута XML](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)
- [Свойство значения XML](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [Операции проекции (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md)
- [Операции квантификаторов (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/quantifier-operations.md)
