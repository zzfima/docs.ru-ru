---
title: "Практическое руководство. Изменение XML-литералов (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "оси XML [Visual Basic], Значение"
  - "XML-литералы [Visual Basic]"
  - "XML-литералы [Visual Basic], изменение"
ms.assetid: 4e864522-a37a-43a2-8236-af80277c5482
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Практическое руководство. Изменение XML-литералов (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] предоставляет удобный способ изменения XML\-литералов.  Можно добавлять и удалять элементы и атрибуты, а также заменять существующие элементы новыми XML\-элементами.  В этом разделе приведены несколько примеров по изменению существующих XML\-литералов.  
  
### Изменение значение XML\-литерала  
  
1.  Чтобы изменить значение XML\-литерала, получите ссылку на XML\-литерал и задайте свойству `Value` нужное значение.  
  
     В следующем примере кода обновляется значение всех элементов \<Price\> в XML\-документе.  
  
     [!code-vb[VbXmlSamples2#4](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/visualbasic/VbXmlSamples2/Module2.vb#4)]  
  
     В следующем примере показан образец XML\-источника и изменение XML из кода этого примера.  
  
    ```  
    Source XML:  
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
  
    Modified XML:  
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
    >  Свойство `Value` ссылается на первый XML\-элемент в коллекции.  Если в коллекции имеется более одного элемента с одинаковыми именами, задание свойства `Value` влияет только первый элемент в коллекции.  
  
### Добавление атрибута к XML\-литералу  
  
1.  Чтобы добавить атрибут к XML\-литералу, сначала получите ссылку на XML\-литерал.  После этого можно добавить атрибут, добавив новое свойство оси атрибута XML.  К XML\-литералу можно также добавить новый объект <xref:System.Xml.Linq.XAttribute>, воспользовавшись методом <xref:System.Xml.Linq.XContainer.Add%2A>.  В следующем примере показаны обе возможности.  
  
     [!code-vb[VbXmlSamples2#5](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/visualbasic/VbXmlSamples2/Module2.vb#5)]  
  
     В следующем примере показан образец XML\-источника и изменение XML из кода этого примера.  
  
    ```  
    Source XML:  
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
  
    Modified XML:  
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
  
     Дополнительные сведения о свойствах атрибутов оси XML см. в разделе [Свойство оси атрибута XML](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md).  
  
### Добавление элемента к XML\-литералу  
  
1.  Чтобы добавить элемент к XML\-литералу, сначала получите ссылку на XML\-литерал.  После этого можно добавить новый объект <xref:System.Xml.Linq.XElement> как последний вложенный элемент с помощью метода <xref:System.Xml.Linq.XContainer.Add%2A>.  Можно добавить новый объект <xref:System.Xml.Linq.XElement> как первый вложенный элемент с помощью метода <xref:System.Xml.Linq.XContainer.AddFirst%2A>.  
  
     Чтобы добавить новый элемент в определенное место относительно других вложенных элементов, сначала получите ссылку на соседний вложенный элемент.  После этого можно добавить новый объект <xref:System.Xml.Linq.XElement> перед соседними вложенными элементами с помощью метода <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>.  Также можно добавить новый объект <xref:System.Xml.Linq.XElement> перед соседними вложенными элементами с помощью метода <xref:System.Xml.Linq.XNode.AddAfterSelf%2A>.  
  
     В следующем примере показаны примеры использования каждого из этих методов.  
  
     [!code-vb[VbXmlSamples2#6](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/visualbasic/VbXmlSamples2/Module2.vb#6)]  
  
     В следующем примере показан образец XML\-источника и изменение XML из кода этого примера.  
  
    ```  
    Source XML:  
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
  
    Modified XML:  
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
  
### Удаление элемента или атрибута из XML\-литерала  
  
1.  Чтобы удалить элемент или атрибут из XML\-литерала, получите ссылку на элемент или атрибут и вызовите метод `Remove`, как показано в следующем примере.  
  
     [!code-vb[VbXmlSamples2#7](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/visualbasic/VbXmlSamples2/Module2.vb#7)]  
  
     В следующем примере показан образец XML\-источника и изменение XML из кода этого примера.  
  
    ```  
    Source XML:  
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
  
    Modified XML:  
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
      </Book> </Catalog>  
    ```  
  
     Чтобы удалить все элементы или атрибуты из XML\-литерала, получите ссылку на XML\-литерал и вызовите метод <xref:System.Xml.Linq.XElement.RemoveAll%2A>.  
  
### Изменение XML\-литерал  
  
1.  Чтобы изменить имя XML\-элемента, сначала получите ссылку на элемент.  Затем можно создать новый объект <xref:System.Xml.Linq.XElement>, имеющий новое имя, и передать этот объект <xref:System.Xml.Linq.XElement> в метод <xref:System.Xml.Linq.XNode.ReplaceWith%2A> существующего объекта <xref:System.Xml.Linq.XElement>.  
  
     Если заменяемый элемент имеет вложенные элементы, которые должны быть сохранены, задайте значение нового объекта <xref:System.Xml.Linq.XElement> по значению свойства <xref:System.Xml.Linq.XContainer.Nodes%2A> существующего элемента.  При этом значение нового элемента будет равно внутреннему XML\-содержимому существующего элемента.  В противном случае в качестве значения нового элемента можно задать свойство `Value` существующего элемента.  
  
     В следующем примере все элементы \<Description\> заменяются элементами \<Abstract\>.  Содержимое элемента \<Description\> сохраняется в новом элементе \<Abstract\> с помощью свойства <xref:System.Xml.Linq.XContainer.Nodes%2A> объекта <xref:System.Xml.Linq.XElement>.  
  
     [!code-vb[VbXmlSamples2#8](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/visualbasic/VbXmlSamples2/Module2.vb#8)]  
  
     В следующем примере показан образец XML\-источника и изменение XML из кода этого примера.  
  
    ```  
    Source XML:  
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
  
    Modified XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <MSRP>44.95</MSRP>     <Abstract>  
          An in-depth look at creating applications  
          with <technology>XML</technology>. For   
          <audience>beginners</audience> or   
          <audience>advanced</audience> developers.  
        </Abstract>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <MSRP>45.95</MSRP>     <Abstract>  
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
  
## См. также  
 [Обработка XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)   
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)   
 [Практическое руководство. Загрузка XML\-кода из файла, строки или потока](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)   
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Знакомство с LINQ в Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)