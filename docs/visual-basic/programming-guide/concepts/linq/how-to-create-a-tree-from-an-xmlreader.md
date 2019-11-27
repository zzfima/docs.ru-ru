---
title: Практическое руководство. Создание дерева из XmlReader
ms.date: 07/20/2015
ms.assetid: 6de683d8-177d-402b-b0de-d0539f1ce5d8
ms.openlocfilehash: 7d8d7f5b6389bef520e11fd2b7cc3e1c7e862e73
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353089"
---
# <a name="how-to-create-a-tree-from-an-xmlreader-visual-basic"></a>Как создать дерево из XmlReader (Visual Basic)

В этом разделе рассказывается, как создать XML-дерево непосредственно из <xref:System.Xml.XmlReader>. Чтобы создать <xref:System.Xml.Linq.XElement> на основе <xref:System.Xml.XmlReader>, необходимо указать для модуля <xref:System.Xml.XmlReader> узел элемента. Модуль <xref:System.Xml.XmlReader> пропускает комментарии и инструкции по обработке, но если для <xref:System.Xml.XmlReader> будет указан текстовый узел, то выдается ошибка. Чтобы избежать подобных ошибок, всегда задавайте для <xref:System.Xml.XmlReader> элемент, прежде чем приступать к созданию XML-дерева на основе <xref:System.Xml.XmlReader>.

## <a name="example"></a>Пример

В этом примере используется следующий XML-документ: [Пример XML-файла. Книги (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).

Следующий код создает объект `T:System.Xml.XmlReader`, а затем читает узлы, пока не найдет узел первого элемента. Затем он загружает объект <xref:System.Xml.Linq.XElement>.

```vb
Dim r As XmlReader = XmlReader.Create("books.xml")
Do While r.NodeType <> XmlNodeType.Element
    r.Read()
Loop
Dim e As XElement = XElement.Load(r)
Console.WriteLine(e)
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

- [Синтаксический анализ XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
