---
title: Функциональное построение (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 57a82bcf-de03-4f1c-a0c8-9a76e989d542
ms.openlocfilehash: c837660adf9c62c8f4304b92d37f732795c981c9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="functional-construction-linq-to-xml-c"></a>Функциональное построение (LINQ to XML) (C#)
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] предоставляет эффективный способ создания XML-элементов, который называется *функциональным построением*. Функциональное построение — это возможность создать XML-дерево одной инструкцией.  
  
 Существует несколько основных функций интерфейса программирования [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], обеспечивающих функциональное построение.  
  
-   Конструктор <xref:System.Xml.Linq.XElement> принимает различные типы аргументов для содержимого. Например, можно передать еще один объект <xref:System.Xml.Linq.XElement>, который станет дочерним элементом. Можно передать объект <xref:System.Xml.Linq.XAttribute>, который станет атрибутом элемента. Можно также передать любой другой тип объекта, который будет преобразован в строку и станет текстовым содержимым элемента.  
  
-   Конструктор <xref:System.Xml.Linq.XElement> принимает массив `params` типа <xref:System.Object>, так что этому конструктору можно передать любое количество объектов. Это позволяет создавать элементы со сложным содержимым.  
  
-   Если объект реализует интерфейс <xref:System.Collections.Generic.IEnumerable%601>, коллекция в этом объекте перечисляется и добавляются все элементы коллекции. Если коллекция содержит объекты <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XAttribute>, каждый ее элемент добавляется отдельно. Это важно, так как позволяет передавать результаты запроса [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] конструктору.  
  
 Эти возможности позволяют использовать код для создания XML-деревьев. Ниже представлен пример такого кода.  
  
```csharp  
XElement contacts =  
    new XElement("Contacts",  
        new XElement("Contact",  
            new XElement("Name", "Patrick Hines"),  
            new XElement("Phone", "206-555-0144"),  
            new XElement("Address",  
                new XElement("Street1", "123 Main St"),  
                new XElement("City", "Mercer Island"),  
                new XElement("State", "WA"),  
                new XElement("Postal", "68042")  
            )  
        )  
    );  
```  
  
 Эти возможности позволяют также написать код, в котором используются результаты запросов [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] при создании дерева XML, как показано ниже.  
  
```csharp  
XElement srcTree = new XElement("Root",  
    new XElement("Element", 1),  
    new XElement("Element", 2),  
    new XElement("Element", 3),  
    new XElement("Element", 4),  
    new XElement("Element", 5)  
);  
XElement xmlTree = new XElement("Root",  
    new XElement("Child", 1),  
    new XElement("Child", 2),  
    from el in srcTree.Elements()  
    where (int)el > 2  
    select el  
);  
Console.WriteLine(xmlTree);  
```  
  
 В этом примере выводятся следующие данные:  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  
## <a name="see-also"></a>См. также  
 [Создание деревьев XML (C#)](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md)
