---
title: "Сериализация с помощью объявления XML (C#) | Документы Майкрософт"
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
ms.assetid: c237fa4a-a042-40fd-886f-17b54c66bb75
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
ms.openlocfilehash: 5c0389630c7fc4b8aa394974b7e42cce2a5101a4
ms.lasthandoff: 03/13/2017

---
# <a name="serializing-with-an-xml-declaration-c"></a>Сериализация с помощью объявления XML (C#)
В этом разделе описывается, как указывать, должна ли при сериализации формироваться XML-декларация.  
  
## <a name="xml-declaration-generation"></a>Формирование XML-декларации  
 При сериализации в <xref:System.IO.File> или <xref:System.IO.TextWriter> с помощью метода <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName> или метода <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName> формируется объявление XML. При сериализации в <xref:System.Xml.XmlWriter> параметры модуля записи (заданные в объекте <xref:System.Xml.XmlWriterSettings>) определяют, будет ли сформировано объявление XML.  
  
 При сериализации в строку при помощи метода `ToString` итоговый XML-документ не будет содержать XML-декларацию.  
  
### <a name="serializing-with-an-xml-declaration"></a>Сериализация с использованием декларации XML  
 В приведенном ниже примере создается объект <xref:System.Xml.Linq.XElement>, документ сохраняется в файл, а затем файл выводится в консоль.  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child", "child content")  
);  
root.Save("Root.xml");  
string str = File.ReadAllText("Root.xml");  
Console.WriteLine(str);  
```  
  
 В этом примере выводятся следующие данные:  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Root>  
  <Child>child content</Child>  
</Root>  
```  
  
### <a name="serializing-without-an-xml-declaration"></a>Сериализация без XML-декларации  
 В приведенном ниже примере демонстрируется, как сохранить <xref:System.Xml.Linq.XElement> в <xref:System.Xml.XmlWriter>.  
  
```csharp  
StringBuilder sb = new StringBuilder();  
XmlWriterSettings xws = new XmlWriterSettings();  
xws.OmitXmlDeclaration = true;  
  
using (XmlWriter xw = XmlWriter.Create(sb, xws)) {  
    XElement root = new XElement("Root",  
        new XElement("Child", "child content")  
    );  
    root.Save(xw);  
}  
Console.WriteLine(sb.ToString());  
```  
  
 В этом примере выводятся следующие данные:  
  
```xml  
<Root><Child>child content</Child></Root>  
```  
  
## <a name="see-also"></a>См. также  
 [Сериализация XML-деревьев (C#)](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md)
