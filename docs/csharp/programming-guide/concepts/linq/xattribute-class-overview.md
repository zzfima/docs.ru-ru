---
title: "Общие сведения о классе XAttribute (C#) | Документы Майкрософт"
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
ms.assetid: 5a630f24-f9ad-400e-831e-c14ebfc9e142
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e1b461158fed20ea5824d89ec455abb667d3fef2
ms.lasthandoff: 03/13/2017

---
# <a name="xattribute-class-overview-c"></a>Общие сведения о классе XAttribute (C#)
Атрибуты - это пары «имя-значение», ассоциированные с элементом. Класс <xref:System.Xml.Linq.XAttribute> представляет атрибуты XML.  
  
## <a name="overview"></a>Обзор  
 Работа с атрибутами [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] аналогична работе с элементами. Они имеют аналогичные конструкторы. Аналогичны и методы, используемые для получения их коллекций. По своему виду выражение запроса [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] для коллекции атрибутов весьма напоминает выражение запроса [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] для коллекции элементов.  
  
 Порядок, в котором атрибуты добавлялись к элементу, сохраняется. Иначе говоря, при просмотре атрибутов они отображаются в том же порядке, в каком были добавлены.  
  
## <a name="the-xattribute-constructor"></a>Конструктор XAttribute  
 Чаще всего используется следующий конструктор класса <xref:System.Xml.Linq.XAttribute>:  
  
|Конструктор|Описание|  
|-----------------|-----------------|  
|`XAttribute(XName name, object content)`|Создает объект <xref:System.Xml.Linq.XAttribute>. Аргумент `name` указывает имя атрибута; `content` указывает содержимое атрибута.|  
  
### <a name="creating-an-element-with-an-attribute"></a>Создание элемента с атрибутом  
 Следующий код иллюстрирует типичную задачу создания элемента, содержащего атрибут:  
  
```csharp  
XElement phone = new XElement("Phone",  
    new XAttribute("Type", "Home"),  
    "555-555-5555");  
Console.WriteLine(phone);  
```  
  
 В этом примере выводятся следующие данные:  
  
```xml  
<Phone Type="Home">555-555-5555</Phone>  
```  
  
### <a name="functional-construction-of-attributes"></a>Функциональное построение атрибутов  
 Объекты <xref:System.Xml.Linq.XAttribute> можно создавать в процессе создания объектов <xref:System.Xml.Linq.XElement> следующим образом:  
  
```csharp  
XElement c = new XElement("Customers",  
    new XElement("Customer",  
        new XElement("Name", "John Doe"),  
        new XElement("PhoneNumbers",  
            new XElement("Phone",  
                new XAttribute("type", "home"),  
                "555-555-5555"),  
            new XElement("Phone",  
                new XAttribute("type", "work"),  
                "666-666-6666")  
        )  
    )  
);  
Console.WriteLine(c);  
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
 Между атрибутами и элементами имеются существенные различия. Объекты <xref:System.Xml.Linq.XAttribute> не являются узлами в дереве XML. Они представляют собой пары «имя-значение», ассоциированные с элементом XML. В отличие от модели DOM, это более точно отражает структуру XML. Хотя объекты <xref:System.Xml.Linq.XAttribute> фактически не являются узлами дерева XML, работа с объектами <xref:System.Xml.Linq.XAttribute> весьма напоминает работу с объектами <xref:System.Xml.Linq.XElement>.  
  
 Это различие имеет первостепенную важность только для разработчиков, создающих коды, которые взаимодействуют с XML-деревьями на уровне узлов. Для многих разработчиков это различие не имеет значения.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о программировании LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
