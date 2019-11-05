---
title: Практическое руководство. Создание дерева из XmlReader (C#)
ms.date: 07/20/2015
ms.assetid: 60951c9c-7087-406c-b5bb-c60e58609b21
ms.openlocfilehash: a0cff596e0a6d50aefab3645a99beec3277d05ec
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73418314"
---
# <a name="how-to-create-a-tree-from-an-xmlreader-c"></a>Практическое руководство. Создание дерева из XmlReader (C#)
В этом разделе рассказывается, как создать XML-дерево непосредственно из <xref:System.Xml.XmlReader>. Чтобы создать <xref:System.Xml.Linq.XElement> на основе <xref:System.Xml.XmlReader>, необходимо указать для модуля <xref:System.Xml.XmlReader> узел элемента. Модуль <xref:System.Xml.XmlReader> пропускает комментарии и инструкции по обработке, но если для <xref:System.Xml.XmlReader> будет указан текстовый узел, то выдается ошибка. Чтобы избежать подобных ошибок, всегда задавайте для <xref:System.Xml.XmlReader> элемент, прежде чем приступать к созданию XML-дерева на основе <xref:System.Xml.XmlReader>.  
  
## <a name="example"></a>Пример  
 В этом примере используется следующий XML-документ: [Пример XML-файла. Книги (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).  
  
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

- [Анализ XML (C#)](how-to-parse-a-string.md)
