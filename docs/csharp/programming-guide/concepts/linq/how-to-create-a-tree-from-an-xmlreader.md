---
title: "Практическое руководство. Создание дерева из XmlReader (C#) | Документы Майкрософт"
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
ms.assetid: 60951c9c-7087-406c-b5bb-c60e58609b21
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
ms.openlocfilehash: d94b2238f6908a29efeb2465c1c11babc54a3704
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-a-tree-from-an-xmlreader-c"></a>Практическое руководство. Создание дерева из XmlReader (C#)
В этом разделе рассказывается, как создать XML-дерево непосредственно из <xref:System.Xml.XmlReader>. Для создания <xref:System.Xml.Linq.XElement> из <xref:System.Xml.XmlReader> необходимо разместить <xref:System.Xml.XmlReader> в узле элемента. Модуль <xref:System.Xml.XmlReader> пропускает комментарии и инструкции по обработке, но если <xref:System.Xml.XmlReader> размещен в текстовом узле, выдается ошибка. Чтобы избежать подобных ошибок, всегда задавайте для <xref:System.Xml.XmlReader> элемент, прежде чем приступать к созданию XML-дерева из <xref:System.Xml.XmlReader>.  
  
## <a name="example"></a>Пример  
 В этом примере используется следующий XML-документ: [Пример XML-файла. Книги (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).  
  
 Следующий код создает объект `T:System.Xml.XmlReader`, а затем читает узлы, пока не найдет узел первого элемента. Затем он загружает объект <xref:System.Xml.Linq.XElement>.  
  
```csharp  
XmlReader r = XmlReader.Create("books.xml");  
while (r.NodeType != XmlNodeType.Element)  
    r.Read();  
XElement e = XElement.Load(r);  
Console.WriteLine(e);  
```  
  
 В этом примере выводятся следующие данные:  
  
```xml  
<Catalog>  
   <Book id="bk101">  
      <Author>Garghentini, Davide</Author>  
      <Title>XML Developer's Guide</Title>  
      <Genre>Computer</Genre>  
      <Price>44.95</Price>  
      <PublishDate>2000-10-01</PublishDate>  
      <Description>An in-depth look at creating applications   
      with XML.</Description>  
   </Book>  
   <Book id="bk102">  
      <Author>Garcia, Debra</Author>  
      <Title>Midnight Rain</Title>  
      <Genre>Fantasy</Genre>  
      <Price>5.95</Price>  
      <PublishDate>2000-12-16</PublishDate>  
      <Description>A former architect battles corporate zombies,   
      an evil sorceress, and her own childhood to become queen   
      of the world.</Description>  
   </Book>  
</Catalog>  
```  
  
## <a name="see-also"></a>См. также  
 [Анализ XML (C#)](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md)
