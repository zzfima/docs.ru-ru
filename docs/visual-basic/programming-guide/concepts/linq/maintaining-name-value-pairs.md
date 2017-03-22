---
title: "Обслуживание пар &quot;имя значение&quot; (Visual Basic) | Документы Microsoft"
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
ms.assetid: 57ac2072-d9f5-432b-84f0-a889c62fd813
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 54db297ecd39e37492dcf8bb4de4f64476662670
ms.lasthandoff: 03/13/2017


---
# <a name="maintaining-namevalue-pairs-visual-basic"></a>Обслуживание пар имя значение (Visual Basic)
Множеству приложений приходится сохранять данные, которые лучше всего хранить в виде пар «имя-значение». Эти данные могут представлять сведения о конфигурации или глобальные параметры. [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] содержит несколько методов, которые облегчают хранение пар «имя-значение». Можно либо оставить информацию в виде атрибутов, либо в виде набора дочерних элементов.  
  
 Одно из отличий между хранением информации в виде атрибутов и в виде дочерних элементов состоит в том, что атрибуты имеют ограничение в том, что для элемента может быть только один атрибут с данным именем. Это ограничение не относится к дочерним элементам.  
  
## <a name="setattributevalue-and-setelementvalue"></a>Методы SetAttributeValue и SetElementValue  
 Два метода, которые облегчают хранение имя значение пары <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>и <xref:System.Xml.Linq.XElement.SetElementValue%2A>.</xref:System.Xml.Linq.XElement.SetElementValue%2A> </xref:System.Xml.Linq.XElement.SetAttributeValue%2A> Эти два метода имеют похожую семантику.  
  
 <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>можно добавить, изменить или удалить атрибуты элемента.</xref:System.Xml.Linq.XElement.SetAttributeValue%2A>  
  
-   При вызове метода <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>с имя атрибута, который не существует, этот метод создаст новый атрибут и добавляет его в указанный элемент.</xref:System.Xml.Linq.XElement.SetAttributeValue%2A>  
  
-   При вызове метода <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>с именем существующего атрибута и с указанным содержимого, содержимое атрибута замещается указанным содержимым.</xref:System.Xml.Linq.XElement.SetAttributeValue%2A>  
  
-   При вызове метода <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>с существующим именем атрибута и с указанием значения null для содержимого, атрибут удаляется из родительского.</xref:System.Xml.Linq.XElement.SetAttributeValue%2A>  
  
 <xref:System.Xml.Linq.XElement.SetElementValue%2A>можно добавлять, изменять или удалять дочерние элементы данного элемента.</xref:System.Xml.Linq.XElement.SetElementValue%2A>  
  
-   При вызове метода <xref:System.Xml.Linq.XElement.SetElementValue%2A>с именем дочерний элемент, который не существует, этот метод создает новый элемент и добавляет его в указанный элемент.</xref:System.Xml.Linq.XElement.SetElementValue%2A>  
  
-   При вызове метода <xref:System.Xml.Linq.XElement.SetElementValue%2A>с именем существующего элемента и с указанным содержимым, содержимое элемента, заменяются с указанным содержимым.</xref:System.Xml.Linq.XElement.SetElementValue%2A>  
  
-   При вызове метода <xref:System.Xml.Linq.XElement.SetElementValue%2A>с именем существующего элемента и задать значение null для содержимого, элемент удаляется из своего родителя.</xref:System.Xml.Linq.XElement.SetElementValue%2A>  
  
## <a name="example"></a>Пример  
 Следующий пример показывает, как создать элемент без атрибутов. Затем он использует <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>метод для создания и поддержания списка пар имя значение.</xref:System.Xml.Linq.XElement.SetAttributeValue%2A>  
  
```vb  
' Create an element with no content.  
Dim root As XElement = <Root/>  
  
' Add a number of name/value pairs as attributes.  
root.SetAttributeValue("Top", 22)  
root.SetAttributeValue("Left", 20)  
root.SetAttributeValue("Bottom", 122)  
root.SetAttributeValue("Right", 300)  
root.SetAttributeValue("DefaultColor", "Color.Red")  
Console.WriteLine(root)  
  
' Replace the value of Top.  
root.SetAttributeValue("Top", 10)  
Console.WriteLine(root)  
  
' Remove DefaultColor.  
root.SetAttributeValue("DefaultColor", Nothing)  
Console.WriteLine(root)  
```  
  
 В этом примере выводятся следующие данные:  
  
```  
<Root Top="22" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" />  
```  
  
## <a name="example"></a>Пример  
 Следующий пример показывает, как создать элемент без дочерних элементов. Затем он использует <xref:System.Xml.Linq.XElement.SetElementValue%2A>метод для создания и поддержания списка пар имя значение.</xref:System.Xml.Linq.XElement.SetElementValue%2A>  
  
```vb  
' Create an element with no content.  
Dim root As XElement = <Root/>  
  
' Add a number of name/value pairs as elements.  
root.SetElementValue("Top", 22)  
root.SetElementValue("Left", 20)  
root.SetElementValue("Bottom", 122)  
root.SetElementValue("Right", 300)  
root.SetElementValue("DefaultColor", "Color.Red")  
Console.WriteLine(root)  
Console.WriteLine("----")  
  
' Replace the value of Top.  
root.SetElementValue("Top", 10)  
Console.WriteLine(root)  
Console.WriteLine("----")  
  
' Remove DefaultColor.  
root.SetElementValue("DefaultColor", Nothing)  
Console.WriteLine(root)  
  
```  
  
 В этом примере выводятся следующие данные:  
  
```  
<Root>  
  <Top>22</Top>  
  <Left>20</Left>  
  <Bottom>122</Bottom>  
  <Right>300</Right>  
  <DefaultColor>Color.Red</DefaultColor>  
</Root>  
----  
<Root>  
  <Top>10</Top>  
  <Left>20</Left>  
  <Bottom>122</Bottom>  
  <Right>300</Right>  
  <DefaultColor>Color.Red</DefaultColor>  
</Root>  
----  
<Root>  
  <Top>10</Top>  
  <Left>20</Left>  
  <Bottom>122</Bottom>  
  <Right>300</Right>  
</Root>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Xml.Linq.XElement.SetAttributeValue%2A></xref:System.Xml.Linq.XElement.SetAttributeValue%2A>   
 <xref:System.Xml.Linq.XElement.SetElementValue%2A></xref:System.Xml.Linq.XElement.SetElementValue%2A>   
 [Изменение деревьев XML (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
