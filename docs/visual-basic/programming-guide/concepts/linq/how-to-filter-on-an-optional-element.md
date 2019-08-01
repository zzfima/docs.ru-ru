---
title: Практическое руководство. Фильтрация по необязательному элементу (Visual Basic)
ms.date: 07/20/2015
ms.assetid: a74b76ad-6889-4185-a189-d6ef2c63841e
ms.openlocfilehash: 4de8c0b07eebc340a53785e6b932a66cb9d2fec9
ms.sourcegitcommit: eb9ff6f364cde6f11322e03800d8f5ce302f3c73
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2019
ms.locfileid: "68710418"
---
# <a name="how-to-filter-on-an-optional-element-visual-basic"></a>Практическое руководство. Фильтрация по необязательному элементу (Visual Basic)
Иногда необходимо выполнить фильтрацию элемента, даже если неизвестно, существует ли он в документе XML. Поиск должен быть выполнен, чтобы, если конкретный элемент не имеет дочернего узла, при фильтрации по этому элементу не возникло исключение null reference. В следующем примере элемент `Child5` не имеет дочернего узла `Type`, тем не менее запрос выполняется правильно.  
  
## <a name="example"></a>Пример  
 Этот пример использует метод расширений <xref:System.Xml.Linq.Extensions.Elements%2A>.  
  
```vb  
Dim root As XElement = _   
    <Root>  
        <Child1>  
            <Text>Child One Text</Text>  
            <Type Value="Yes"/>  
        </Child1>  
        <Child2>  
            <Text>Child Two Text</Text>  
            <Type Value="Yes"/>  
        </Child2>  
        <Child3>  
            <Text>Child Three Text</Text>  
            <Type Value="No"/>  
        </Child3>  
        <Child4>  
            <Text>Child Four Text</Text>  
            <Type Value="Yes"/>  
        </Child4>  
        <Child5>  
            <Text>Child Five Text</Text>  
        </Child5>  
    </Root>  
Dim cList As IEnumerable(Of String) = _  
    From typeElement In root.Elements().<Type> _  
    Where typeElement.@Value = "Yes" _  
    Select typeElement.Parent.<Text>.Value  
Dim str As String  
For Each str In cList  
    Console.WriteLine(str)  
Next  
```  
  
 Этот код выводит следующие результаты:  
  
```  
Child One Text  
Child Two Text  
Child Four Text  
```  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует тот же запрос XML, что и в пространстве имен. Дополнительные сведения см. в разделе [Общие сведения о пространствах имен (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).  
  
```vb  
Imports <xmlns='http://www.adatum.com'>  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root>  
                <Child1>  
                    <Text>Child One Text</Text>  
                    <Type Value="Yes"/>  
                </Child1>  
                <Child2>  
                    <Text>Child Two Text</Text>  
                    <Type Value="Yes"/>  
                </Child2>  
                <Child3>  
                    <Text>Child Three Text</Text>  
                    <Type Value="No"/>  
                </Child3>  
                <Child4>  
                    <Text>Child Four Text</Text>  
                    <Type Value="Yes"/>  
                </Child4>  
                <Child5>  
                    <Text>Child Five Text</Text>  
                </Child5>  
            </Root>  
        Dim cList As IEnumerable(Of String) = _  
            From typeElement In root.Elements().<Type> _  
            Where typeElement.@Value = "Yes" _  
            Select typeElement.Parent.<Text>.Value  
        Dim str As String  
        For Each str In cList  
            Console.WriteLine(str)  
        Next  
    End Sub  
End Module  
```  
  
 Этот код выводит следующие результаты:  
  
```  
Child One Text  
Child Two Text  
Child Four Text  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType>
- [Основные запросы (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
- [Свойство дочерней оси XML](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)
- [Свойство оси атрибута XML](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)
- [Свойство значения XML](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [Общие сведения о стандартных операторах запроса (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Операции проекции (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md)
