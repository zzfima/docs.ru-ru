---
title: Общие сведения о классе XAttribute
ms.date: 07/20/2015
ms.assetid: 7781580a-9583-4a1b-ae1e-91c5936eb0b1
ms.openlocfilehash: 00aeeec3f251ecd1d21a313290326b3ba49d63d3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349328"
---
# <a name="xattribute-class-overview-visual-basic"></a>Общие сведения о классе XAttribute (Visual Basic)
Атрибуты - это пары «имя-значение», ассоциированные с элементом. Класс <xref:System.Xml.Linq.XAttribute> представляет XML-атрибуты.  
  
## <a name="overview"></a>Обзор  
 Работа с атрибутами [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] аналогична работе с элементами. Они имеют аналогичные конструкторы. Аналогичны и методы, используемые для получения их коллекций. По своему виду выражение запроса [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] для коллекции атрибутов весьма напоминает выражение запроса [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] для коллекции элементов.  
  
 Порядок, в котором атрибуты добавлялись к элементу, сохраняется. Иначе говоря, при просмотре атрибутов они отображаются в том же порядке, в каком были добавлены.  
  
## <a name="the-xattribute-constructor"></a>Конструктор XAttribute  
 Чаще всего используется следующий конструктор класса <xref:System.Xml.Linq.XAttribute>.  
  
|Конструктор|Описание|  
|-----------------|-----------------|  
|`XAttribute(XName name, object content)`|Создает объект <xref:System.Xml.Linq.XAttribute>. Аргумент `name` указывает имя атрибута; `content` указывает содержимое атрибута.|  
  
### <a name="creating-an-element-with-an-attribute"></a>Создание элемента с атрибутом  
 В следующем коде показан элемент, содержащий атрибут с использованием литералов XML в Visual Basic:  
  
```vb  
Dim phone As XElement = <Phone Type="Home">555-555-5555</Phone>  
Console.WriteLine(phone)  
```  
  
 В этом примере выводятся следующие данные:  
  
```xml  
<Phone Type="Home">555-555-5555</Phone>  
```  
  
### <a name="functional-construction-of-attributes"></a>Функциональное построение атрибутов  
 Объекты <xref:System.Xml.Linq.XAttribute> можно создавать в процессе создания объектов <xref:System.Xml.Linq.XElement> следующим образом:  
  
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
 Между атрибутами и элементами имеются существенные различия. Объекты <xref:System.Xml.Linq.XAttribute> не являются узлами в дереве XML. Они представляют собой пары «имя-значение», ассоциированные с элементом XML. В отличие от модели DOM, это более точно отражает структуру XML. Хотя объекты <xref:System.Xml.Linq.XAttribute> фактически не являются узлами XML-дерева, работа с объектами <xref:System.Xml.Linq.XAttribute> весьма напоминает работу с объектами <xref:System.Xml.Linq.XElement>.  
  
 Это различие имеет первостепенную важность только для разработчиков, создающих коды, которые взаимодействуют с XML-деревьями на уровне узлов. Для многих разработчиков это различие не имеет значения.  
  
## <a name="see-also"></a>См. также:

- [Общие сведения о программировании LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
