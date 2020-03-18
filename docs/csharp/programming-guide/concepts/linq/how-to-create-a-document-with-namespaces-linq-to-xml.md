---
title: Практическое руководство. Создание документа с пространствами имен (C#) (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 37e63c57-f86d-47ac-88a7-2c2d107def30
ms.openlocfilehash: 429b0b0b41f2201b983f931e469b25ff406b91ac
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141332"
---
# <a name="how-to-create-a-document-with-namespaces-c-linq-to-xml"></a>Практическое руководство. Создание документа с пространствами имен (C#) (LINQ to XML)
В этом разделе описано, как создавать документы с пространствами имен.  
  
## <a name="example"></a>Пример  
 Чтобы создать элемент или атрибут, находящийся в пространстве имен, необходимо сначала объявить и инициализировать объект <xref:System.Xml.Linq.XNamespace>. Затем следует использовать перегруженный оператор сложения для объединения пространства имен с локальным именем, выраженным строкой.  
  
 В следующем примере создается документ с одним пространством имен. По умолчанию [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] сериализует документ с использованием пространства имен по умолчанию.  
  
```csharp  
// Create an XML tree in a namespace.  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = new XElement(aw + "Root",  
    new XElement(aw + "Child", "child content")  
);  
Console.WriteLine(root);  
```  
  
 В этом примере выводятся следующие данные:  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child>child content</Child>  
</Root>  
```  
  
## <a name="example"></a>Пример  
 В следующем примере создается документ с одним пространством имен. Он также создает атрибут, который объявляет пространство имен с префиксом пространства имен. Создать атрибут, объявляющий пространство имен с префиксом, можно, указав имя атрибута в качестве префикса пространства имен и поместив его в пространство имен <xref:System.Xml.Linq.XNamespace.Xmlns%2A>. Значение этого атрибута представляет собой URI пространства имен.  
  
```csharp  
// Create an XML tree in a namespace, with a specified prefix  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com"),  
    new XElement(aw + "Child", "child content")  
);  
Console.WriteLine(root);  
```  
  
 В этом примере выводятся следующие данные:  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Child>child content</aw:Child>  
</aw:Root>  
```  
  
## <a name="example"></a>Пример  
 Следующий пример иллюстрирует создание документа, содержащего два пространства имен. Одно из них - пространство имен по умолчанию. Другое - пространство имен с префиксом.  
  
 При включении атрибутов пространств имен в корневой элемент пространства имен сериализуются, поэтому `http://www.adventure-works.com` становится пространством имен по умолчанию, а `www.fourthcoffee.com` сериализуется с префиксом "fc". Чтобы создать атрибут, объявляющий применяемое по умолчанию пространство имен, необходимо создать атрибут с именем «xmlns» без пространства имен. Значение этого атрибута является используемым по умолчанию идентификатором URI пространства имен.  
  
```csharp  
// The http://www.adventure-works.com namespace is forced to be the default namespace.  
XNamespace aw = "http://www.adventure-works.com";  
XNamespace fc = "www.fourthcoffee.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute("xmlns", "http://www.adventure-works.com"),  
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
<Root xmlns="http://www.adventure-works.com" xmlns:fc="www.fourthcoffee.com">  
  <fc:Child>  
    <DifferentChild>other content</DifferentChild>  
  </fc:Child>  
  <Child2>c2 content</Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</Root>  
```  
  
## <a name="example"></a>Пример  
 В этом примере создается документ, который содержит два пространства имен с префиксами.  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XNamespace fc = "www.fourthcoffee.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute(XNamespace.Xmlns + "aw", aw.NamespaceName),  
    new XAttribute(XNamespace.Xmlns + "fc", fc.NamespaceName),  
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
  
## <a name="example"></a>Пример  
 Другой метод получения того же результата состоит в использовании развернутых имен вместо объявления и создания объекта <xref:System.Xml.Linq.XNamespace>.  
  
 Этот подход влияет на производительность. Всякий раз при передаче [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] строки, содержащей развернутое имя, система [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] должна проанализировать это имя, обнаружить атомизированное пространство имен и атомарное имя. Этот процесс требует затрат процессорного времени. Если производительность является важным фактором, целесообразнее объявить и использовать объект <xref:System.Xml.Linq.XNamespace> явным образом.  
  
 Если производительность важна, дополнительные сведения см. в разделе [Предварительная атомизация объектов XName (LINQ to XML) (C#)](./pre-atomization-of-xname-objects-linq-to-xml.md).  
  
```csharp  
// Create an XML tree in a namespace, with a specified prefix  
XElement root = new XElement("{http://www.adventure-works.com}Root",  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com"),  
    new XElement("{http://www.adventure-works.com}Child", "child content")  
);  
Console.WriteLine(root);  
```  
  
 В этом примере выводятся следующие данные:  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Child>child content</aw:Child>  
</aw:Root>  
```  
  
## <a name="see-also"></a>См. также раздел

- [Обзор пространств имен (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md)
