---
title: "Общие сведения о классе XAttribute (Visual Basic) | Документы Microsoft"
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
ms.assetid: 7781580a-9583-4a1b-ae1e-91c5936eb0b1
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
ms.openlocfilehash: 1ce5f4be6006908b35057854f89432471fd9f06b
ms.lasthandoff: 03/13/2017

---
# <a name="xattribute-class-overview-visual-basic"></a>Общие сведения о классе XAttribute (Visual Basic)
Атрибуты - это пары «имя-значение», ассоциированные с элементом. <xref:System.Xml.Linq.XAttribute>Класс представляет XML-атрибуты.</xref:System.Xml.Linq.XAttribute>  
  
## <a name="overview"></a>Обзор  
 Работа с атрибутами [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] аналогична работе с элементами. Они имеют аналогичные конструкторы. Аналогичны и методы, используемые для получения их коллекций. Объект [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] выражение запроса для коллекции атрибутов очень похож на [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] выражение коллекции элементов запроса.  
  
 Порядок, в котором атрибуты добавлялись к элементу, сохраняется. Иначе говоря, при просмотре атрибутов они отображаются в том же порядке, в каком были добавлены.  
  
## <a name="the-xattribute-constructor"></a>Конструктор XAttribute  
 Следующий конструктор класса <xref:System.Xml.Linq.XAttribute>класс является тот, который будет использоваться чаще всего:</xref:System.Xml.Linq.XAttribute>  
  
|Конструктор|Описание|  
|-----------------|-----------------|  
|`XAttribute(XName name, object content)`|Создает <xref:System.Xml.Linq.XAttribute>объекта.</xref:System.Xml.Linq.XAttribute> Аргумент `name` указывает имя атрибута; `content` указывает содержимое атрибута.|  
  
### <a name="creating-an-element-with-an-attribute"></a>Создание элемента с атрибутом  
 Следующий код показывает элемент, содержащий атрибут с помощью XML-литералов в Visual Basic:  
  
```vb  
Dim phone As XElement = <Phone Type="Home">555-555-5555</Phone>  
Console.WriteLine(phone)  
```  
  
 В этом примере выводятся следующие данные:  
  
```xml  
<Phone Type="Home">555-555-5555</Phone>  
```  
  
### <a name="functional-construction-of-attributes"></a>Функциональное построение атрибутов  
 Можно создавать <xref:System.Xml.Linq.XAttribute>объекты в процессе создания <xref:System.Xml.Linq.XElement>объектов следующим образом:</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XAttribute>  
  
```vb  
Dim c As XElement = _  
    <Customers>  
        <Customer>  
            <Name>John Doe</Name>  
            <PhoneNumbers>  
                <Phone type="home">555-555-5555</Phone>  
                <Phone type="work">666-666-6666</Phone>  
            </PhoneNumbers>  
        </Customer>  
    </Customers>  
Console.WriteLine(c)  
```  
  
 В этом примере выводятся следующие данные:  
  
```xml  
<Customers>  
  <Customer>  
    <Name>John Doe</Name>  
    <PhoneNumbers>  
      <Phone type="home">555-555-5555</Phone>  
      <Phone type="work">666-666-6666</Phone>  
    </PhoneNumbers>  
  </Customer>  
</Customers>  
```  
  
### <a name="attributes-are-not-nodes"></a>Атрибуты не являются узлами  
 Между атрибутами и элементами имеются существенные различия. <xref:System.Xml.Linq.XAttribute>объекты не являются узлами XML-дерева.</xref:System.Xml.Linq.XAttribute> Они представляют собой пары «имя-значение», ассоциированные с элементом XML. В отличие от модели DOM, это более точно отражает структуру XML. Хотя <xref:System.Xml.Linq.XAttribute>объектов фактически не являются узлами XML-дерева, работа с <xref:System.Xml.Linq.XAttribute>объекты очень похожа на работу с <xref:System.Xml.Linq.XElement>объектов.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XAttribute>  
  
 Это различие имеет первостепенную важность только для разработчиков, создающих коды, которые взаимодействуют с XML-деревьями на уровне узлов. Для многих разработчиков это различие не имеет значения.  
  
## <a name="see-also"></a>См. также  
 [LINQ to XML обзор программирования (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
