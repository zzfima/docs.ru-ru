---
title: Практическое руководство. Изменение XML-литералов
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], Value
- XML literals [Visual Basic]
- XML literals [Visual Basic], modifying
ms.assetid: 4e864522-a37a-43a2-8236-af80277c5482
ms.openlocfilehash: 99ec35addcb9fc8d886c9151cde87227b5113eb9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330859"
---
# <a name="how-to-modify-xml-literals-visual-basic"></a>Практическое руководство. Изменение XML-литералов (Visual Basic)

Visual Basic предоставляет удобные способы изменения XML-литералов. Можно добавлять или удалять элементы и атрибуты. Кроме того, можно заменить существующий элемент новым XML-элементом. В этом разделе приводится несколько примеров изменения существующего XML-литерала.

### <a name="to-modify-the-value-of-an-xml-literal"></a>Изменение значения XML-литерала

1. Чтобы изменить значение XML-литерала, получите ссылку на XML-литерал и задайте для свойства `Value` нужное значение.

    В следующем примере кода обновляется значение всех элементов \<Price > в XML-документе.

    [!code-vb[VbXmlSamples2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#4)]

    Ниже приведен пример исходного XML и измененный XML-код из этого примера кода.

    Исходный XML-код:

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk331">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
      </Book>
    </Catalog>
    ```

    Измененный XML:

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>47.20</Price>
      </Book>
      <Book id="bk331">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>48.25</Price>
      </Book>
    </Catalog>
    ```

    > [!NOTE]
    > Свойство `Value` ссылается на первый элемент XML в коллекции. Если в коллекции имеется несколько элементов с одинаковым именем, установка свойства `Value` влияет только на первый элемент в коллекции.

### <a name="to-add-an-attribute-to-an-xml-literal"></a>Добавление атрибута к XML-литералу

1. Чтобы добавить атрибут к XML-литералу, сначала получите ссылку на XML-литерал. Затем можно добавить атрибут, добавив новое свойство оси атрибутов XML. Можно также добавить новый объект <xref:System.Xml.Linq.XAttribute> в XML-литерал с помощью метода <xref:System.Xml.Linq.XContainer.Add%2A>. В следующем примере показаны оба варианта.

    [!code-vb[VbXmlSamples2#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#5)]

    Ниже приведен пример исходного XML и измененный XML-код из этого примера кода.

    Исходный XML-код:

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101" >
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk331">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
      </Book>
    </Catalog>
    ```

    Измененный XML:

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101" genre="Computer" editorEmail="someone@example.com">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk331" genre="Computer" editorEmail="someone@example.com">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
      </Book>
    </Catalog>
    ```

    Дополнительные сведения о свойствах осей атрибутов XML см. в разделе [свойство оси атрибутов XML](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md).

### <a name="to-add-an-element-to-an-xml-literal"></a>Добавление элемента в XML-литерал

1. Чтобы добавить элемент в XML-литерал, сначала получите ссылку на XML-литерал. Затем можно добавить новый объект <xref:System.Xml.Linq.XElement> как последний вложенный элемент элемента с помощью метода <xref:System.Xml.Linq.XContainer.Add%2A>. Новый объект <xref:System.Xml.Linq.XElement> можно добавить в качестве первого вложенного элемента с помощью метода <xref:System.Xml.Linq.XContainer.AddFirst%2A>.

    Чтобы добавить новый элемент в определенном месте относительно других вложенных элементов, сначала получите ссылку на смежный вложенный элемент. Затем можно добавить новый объект <xref:System.Xml.Linq.XElement> перед соседним вложенным элементом с помощью метода <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>. Можно также добавить новый объект <xref:System.Xml.Linq.XElement> после соседнего вложенного элемента с помощью метода <xref:System.Xml.Linq.XNode.AddAfterSelf%2A>.

    В следующем примере показаны примеры каждого из этих методов.

    [!code-vb[VbXmlSamples2#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#6)]

    Ниже приведен пример исходного XML и измененный XML-код из этого примера кода.

    Исходный XML-код:

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101" >
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk331">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
      </Book>
    </Catalog>
    ```

    Измененный XML:

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101" >
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk000"></Book>
      <Book id="bk331">
        <Publisher>Microsoft Press</Publisher>
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
        <PublishDate>2005-2-14</PublishDate>
      </Book>
      <Book id="bk999"></Book>
    </Catalog>
    ```

### <a name="to-remove-an-element-or-attribute-from-an-xml-literal"></a>Удаление элемента или атрибута из XML-литерала

1. Чтобы удалить элемент или атрибут из XML-литерала, получите ссылку на элемент или атрибут и вызовите метод `Remove`, как показано в следующем примере.

    [!code-vb[VbXmlSamples2#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#7)]

    Ниже приведен пример исходного XML и измененный XML-код из этого примера кода.

    Исходный XML-код:

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101" genre="Computer" editorEmail="someone@example.com">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk000"></Book>
      <Book id="bk331" genre="Computer" editorEmail="someone@example.com">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
      </Book>
      <Book id="bk999"></Book>
    </Catalog>
    ```

    Измененный XML:

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101" editorEmail="someone@example.com">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk000"></Book>
      <Book id="bk331" editorEmail="someone@example.com">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
      </Book></Catalog>
    ```

    Чтобы удалить все элементы или атрибуты из XML-литерала, получите ссылку на XML-литерал и вызовите метод <xref:System.Xml.Linq.XElement.RemoveAll%2A>.

### <a name="to-modify-an-xml-literal"></a>Изменение XML-литерала

1. Чтобы изменить имя XML-элемента, сначала получите ссылку на элемент. Затем можно создать новый объект <xref:System.Xml.Linq.XElement> с новым именем и передать новый объект <xref:System.Xml.Linq.XElement> методу <xref:System.Xml.Linq.XNode.ReplaceWith%2A> существующего объекта <xref:System.Xml.Linq.XElement>.

    Если заменяемый элемент содержит вложенные элементы, которые должны быть сохранены, установите значение нового объекта <xref:System.Xml.Linq.XElement> в свойство <xref:System.Xml.Linq.XContainer.Nodes%2A> существующего элемента. При этом значение нового элемента будет присвоено внутреннему XML существующего элемента. В противном случае можно присвоить значение нового элемента свойству `Value` существующего элемента.

    Следующий пример кода заменяет все \<Description > элементами \<абстрактный элемент >. Содержимое элемента \<Description > сохраняется в новом \<абстрактном элементе > с помощью свойства <xref:System.Xml.Linq.XContainer.Nodes%2A> объекта \<Description > <xref:System.Xml.Linq.XElement>.

    [!code-vb[VbXmlSamples2#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#8)]

    Ниже приведен пример исходного XML и измененный XML-код из этого примера кода.

    Исходный XML-код:

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
        <Description>
          An in-depth look at creating applications
          with <technology>XML</technology>. For
          <audience>beginners</audience> or
          <audience>advanced</audience> developers.
        </Description>
      </Book>
      <Book id="bk331">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
        <Description>
          Get the expert insights, practical code samples, and best
          practices you need to advance your expertise with
          <technology>Visual Basic .NET</technology>.
          Learn how to create faster, more reliable applications
          based on professional, pragmatic guidance by today's top
          <audience>developers</audience>.
        </Description>
      </Book>
    </Catalog>
    ```

    Измененный XML:

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <MSRP>44.95</MSRP>    <Abstract>
          An in-depth look at creating applications
          with <technology>XML</technology>. For
          <audience>beginners</audience> or
          <audience>advanced</audience> developers.
        </Abstract>
      </Book>
      <Book id="bk331">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <MSRP>45.95</MSRP>    <Abstract>
          Get the expert insights, practical code samples, and best
          practices you need to advance your expertise with
          <technology>Visual Basic .NET</technology>.
          Learn how to create faster, more reliable applications
          based on professional, pragmatic guidance by today's top
          <audience>developers</audience>.
        </Abstract>
      </Book>
    </Catalog>
    ```

## <a name="see-also"></a>См. также

- [Работа с XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [Практическое руководство. Загрузка XML-кода из файла, строки или потока](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
