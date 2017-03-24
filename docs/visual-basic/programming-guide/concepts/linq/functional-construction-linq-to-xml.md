---
title: "Функциональное построение (LINQ to XML) (Visual Basic) | Документы Microsoft"
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
ms.assetid: feac4273-39ab-43ae-bab7-4059c807a785
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9fa8cb3c97a1e23a863296c828c82b240e9ab5db
ms.lasthandoff: 03/13/2017

---
# <a name="functional-construction-linq-to-xml-visual-basic"></a>Функциональное построение (LINQ to XML) (Visual Basic)
[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]предоставляет эффективный способ создания элементов XML, который называется *функциональное построение*. Функциональное построение — это возможность создать XML-дерево одной инструкцией.  
  
 Существует несколько основных функций интерфейса программирования [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], обеспечивающих функциональное построение.  
  
-   <xref:System.Xml.Linq.XElement>Конструктор принимает различные типы аргументов для содержимого.</xref:System.Xml.Linq.XElement> Например, можно передать другой <xref:System.Xml.Linq.XElement>объекта, который станет дочерним элементом.</xref:System.Xml.Linq.XElement> Можно передать <xref:System.Xml.Linq.XAttribute>объекта, который станет атрибутом элемента.</xref:System.Xml.Linq.XAttribute> Можно также передать любой другой тип объекта, который будет преобразован в строку и станет текстовым содержимым элемента.  
  
-   <xref:System.Xml.Linq.XElement>Конструктор принимает `params` массив типа <xref:System.Object>, так что можно передать любое количество объектов в конструктор.</xref:System.Object> </xref:System.Xml.Linq.XElement> Это позволяет создавать элементы со сложным содержимым.  
  
-   Если объект реализует интерфейс <xref:System.Collections.Generic.IEnumerable%601>, коллекция в этом объекте перечисляется и добавляются все элементы в коллекции.</xref:System.Collections.Generic.IEnumerable%601> Если коллекция содержит <xref:System.Xml.Linq.XElement>или <xref:System.Xml.Linq.XAttribute>объектов, каждый элемент в коллекцию добавляется отдельно.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement> Это важно, так как позволяет передавать результаты [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] запрос в конструктор.  
  
 Ниже представлен пример такого кода.  
  
 Эти функции позволяют создавать код с помощью XML-литералов для создания XML-дерева, а также написать код, использующий результаты [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] запросов при создании XML-дерева:  
  
```vb  
Dim srcTree As XElement = _  
    <Root>  
        <Element>1</Element>  
        <Element>2</Element>  
        <Element>3</Element>  
        <Element>4</Element>  
        <Element>5</Element>  
    </Root>  
Dim xmlTree As XElement = _  
    <Root>  
        <Child>1</Child>  
        <Child>2</Child>  
        <%= From el In srcTree.Elements() _  
            Where CInt(el) > 2 _  
            Select el %>  
    </Root>  
Console.WriteLine(xmlTree)  
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
 [Создание деревьев XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
