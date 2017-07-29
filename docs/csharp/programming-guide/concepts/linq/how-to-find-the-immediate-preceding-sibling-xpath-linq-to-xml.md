---
title: "Практическое руководство. Поиск ближайшего предшествующего элемента того же уровня (XPath-LINQ to XML) (C#)"
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
ms.assetid: 74c06201-0b1b-4b5e-b3ac-0092980614e6
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 033cadcf8d2e87301c8eef9c77b6fcf691c4e040
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-find-the-immediate-preceding-sibling-xpath-linq-to-xml-c"></a>Практическое руководство. Поиск ближайшего предшествующего элемента того же уровня (XPath-LINQ to XML) (C#)
Иногда требуется найти ближайший предшествующий одноуровневый элемент узла. Из-за разности в семантике позиционных предикатов для осей предшествующих одноуровневых элементов в XPath и в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] это сравнение является одним из наиболее интересных.  
  
## <a name="example"></a>Пример  
 В этом примере в запросе [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] оператор <xref:System.Linq.Enumerable.Last%2A> используется для обнаружения последнего узла в коллекции, возвращенной методом <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>. В отличие от этого, в выражении XPath для обнаружения ближайшего предшествующего элемента используется предикат со значением 1.  
  
```csharp  
XElement root = XElement.Parse(  
    @"<Root>  
    <Child1/>  
    <Child2/>  
    <Child3/>  
    <Child4/>  
</Root>");  
XElement child4 = root.Element("Child4");  
  
// LINQ to XML query  
XElement el1 =  
    child4  
    .ElementsBeforeSelf()  
    .Last();  
  
// XPath expression  
XElement el2 =  
    ((IEnumerable)child4  
                 .XPathEvaluate("preceding-sibling::*[1]"))  
                 .Cast<XElement>()  
                 .First();  
  
if (el1 == el2)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(el1);  
```  
  
 В этом примере выводятся следующие данные:  
  
```  
Results are identical  
<Child3 />  
```  
  
## <a name="see-also"></a>См. также  
 [LINQ to XML для пользователей XPath (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)

