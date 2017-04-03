---
title: "Обслуживание пар &quot;имя-значение&quot; (C#) | Документы Майкрософт"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 7b04b0f1-af64-42eb-8737-83f8861b5915
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: fda5e083584a57245a83bdf8c09d31e7ffdb2d5a
ms.lasthandoff: 03/13/2017


---
# <a name="maintaining-namevalue-pairs-c"></a>Обслуживание пар "имя-значение" (C#)
Множеству приложений приходится сохранять данные, которые лучше всего хранить в виде пар «имя-значение». Эти данные могут представлять сведения о конфигурации или глобальные параметры. [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] содержит несколько методов, которые облегчают хранение пар «имя-значение». Можно либо оставить информацию в виде атрибутов, либо в виде набора дочерних элементов.  
  
 Одно из отличий между хранением информации в виде атрибутов и в виде дочерних элементов состоит в том, что атрибуты имеют ограничение в том, что для элемента может быть только один атрибут с данным именем. Это ограничение не относится к дочерним элементам.  
  
## <a name="setattributevalue-and-setelementvalue"></a>Методы SetAttributeValue и SetElementValue  
 Хранение пар имен и значений упрощают методы <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> и <xref:System.Xml.Linq.XElement.SetElementValue%2A>. Эти два метода имеют похожую семантику.  
  
 Метод <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> позволяет добавлять, изменять и удалять атрибуты элемента.  
  
-   При вызове метода <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> с несуществующим именем атрибута этот метод создаст новый атрибут и добавит его в указанный элемент.  
  
-   При вызове метода <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> с существующим именем атрибута и с указанным содержимым содержимое данного атрибута замещается указанным содержимым.  
  
-   При вызове метода <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> с существующим именем атрибута и с указанием значения NULL в качестве содержимого атрибут удаляется из своего родителя.  
  
 Метод <xref:System.Xml.Linq.XElement.SetElementValue%2A> позволяет добавлять, изменять и удалять дочерние элементы элемента.  
  
-   При вызове метода <xref:System.Xml.Linq.XElement.SetElementValue%2A> с несуществующим именем дочернего элемента этот метод создаст новый элемент и добавляет его в указанный элемент.  
  
-   При вызове метода <xref:System.Xml.Linq.XElement.SetElementValue%2A> с существующим именем элемента и с указанным содержимым содержимое данного элемента замещается указанным содержимым.  
  
-   При вызове метода <xref:System.Xml.Linq.XElement.SetElementValue%2A> с существующим именем элемента и с указанием значения NULL в качестве содержимого элемент удаляется из его родителя.  
  
## <a name="example"></a>Пример  
 Следующий пример показывает, как создать элемент без атрибутов. Затем с помощью метода <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> в нем создается и ведется список пар имен и значений.  
  
```csharp  
// Create an element with no content.  
XElement root = new XElement("Root");  
  
// Add a number of name/value pairs as attributes.  
root.SetAttributeValue("Top", 22);  
root.SetAttributeValue("Left", 20);  
root.SetAttributeValue("Bottom", 122);  
root.SetAttributeValue("Right", 300);  
root.SetAttributeValue("DefaultColor", "Color.Red");  
Console.WriteLine(root);  
  
// Replace the value of Top.  
root.SetAttributeValue("Top", 10);  
Console.WriteLine(root);  
  
// Remove DefaultColor.  
root.SetAttributeValue("DefaultColor", null);  
Console.WriteLine(root);  
```  
  
 В этом примере выводятся следующие данные:  
  
```  
<Root Top="22" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" />  
```  
  
## <a name="example"></a>Пример  
 Следующий пример показывает, как создать элемент без дочерних элементов. Затем с помощью метода <xref:System.Xml.Linq.XElement.SetElementValue%2A> в нем создается и ведется список пар имен и значений.  
  
```csharp  
// Create an element with no content.  
XElement root = new XElement("Root");  
  
// Add a number of name/value pairs as elements.  
root.SetElementValue("Top", 22);  
root.SetElementValue("Left", 20);  
root.SetElementValue("Bottom", 122);  
root.SetElementValue("Right", 300);  
root.SetElementValue("DefaultColor", "Color.Red");  
Console.WriteLine(root);  
Console.WriteLine("----");  
  
// Replace the value of Top.  
root.SetElementValue("Top", 10);  
Console.WriteLine(root);  
Console.WriteLine("----");  
  
// Remove DefaultColor.  
root.SetElementValue("DefaultColor", null);  
Console.WriteLine(root);  
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
 <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>   
 <xref:System.Xml.Linq.XElement.SetElementValue%2A>   
 [Изменение деревьев XML (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
