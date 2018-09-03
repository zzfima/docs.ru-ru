---
title: Практическое руководство. Управление префиксами пространств имен (C#) (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 64de5186-b81a-4ddd-8327-8693df59a01b
ms.openlocfilehash: af864139d56bd3ebb22cca6369b82539b9d007da
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43417375"
---
# <a name="how-to-control-namespace-prefixes-c-linq-to-xml"></a>Практическое руководство. Управление префиксами пространств имен (C#) (LINQ to XML)
В этом разделе описывается управление префиксами пространств имен при сериализации дерева XML.  
  
 Во многих ситуациях управлять префиксами пространств имен нет необходимости.  
  
 Однако некоторые средства программирования XML требуют, чтобы была возможность управления префиксами пространства имен. Например, при выполнении манипуляций с таблицами стилей XSLT или с документами XAML, которые содержат ссылающиеся на те или иные префиксы пространства имен внедренные выражения XPath, важно, чтобы документ сериализовался с этими конкретными префиксами.  
  
 Это основная причина, по которой необходимо управление префиксами пространства имен.  
  
 Кроме того, возможность управления префиксами пространства имен требуется в тех случаях, когда необходимо, чтобы пользователи редактировали XML-документы вручную и могли без труда вводить префиксы с клавиатуры. Пусть создается документ XSD. В соответствии с соглашениями по схемам при этом в качестве префиксов пространства имен схемы используются `xs` или `xsd`.  
  
 Для управления префиксами пространства имен нужно вставлять атрибуты, объявляющие пространства имен. В случае объявления пространств имен с теми или иными префиксами [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] попытается учитывать префиксы пространств имен при сериализации.  
  
 Создать атрибут, объявляющий пространство имен с префиксом, можно, указав для имени атрибута пространство имен <xref:System.Xml.Linq.XNamespace.Xmlns%2A>, а само имя атрибута в качестве префикса пространства имен. Значение атрибута представляет собой URI пространства имен.  
  
## <a name="example"></a>Пример  
 В этом примере объявляются два пространства имен. В нем указывается, что пространство имен `http://www.adventure-works.com` имеет префикс `aw`, а пространство имен `www.fourthcoffee.com` — префикс `fc`.  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XNamespace fc = "www.fourthcoffee.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com"),  
    new XAttribute(XNamespace.Xmlns + "fc", "www.fourthcoffee.com"),  
    new XElement(fc + "Child",  
        new XElement(aw + "DifferentChild", "other content")  
    ),  
    new XElement(aw + "Child2", "c2 content"),  
    new XElement(fc + "Child3", "c3 content")  
);  
Console.WriteLine(root);  
```  
  
 В этом примере выводятся следующие данные:  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com" xmlns:fc="www.fourthcoffee.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a>См. также  
 [Работа с пространствами имен XML (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)
