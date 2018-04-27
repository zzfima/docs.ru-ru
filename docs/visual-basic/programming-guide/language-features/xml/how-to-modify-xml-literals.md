---
title: Практическое руководство. Изменение XML-литералов (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML axis [Visual Basic], Value
- XML literals [Visual Basic]
- XML literals [Visual Basic], modifying
ms.assetid: 4e864522-a37a-43a2-8236-af80277c5482
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 230cf17fec8356b8f16ea2118b0bda0589ecd04a
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-modify-xml-literals-visual-basic"></a>Практическое руководство. Изменение XML-литералов (Visual Basic)
Visual Basic предоставляет удобный способ изменения XML-литералов. Можно добавить или удалить элементы и атрибуты, и также можно заменить существующий элемент новым элементом XML. Здесь приведены несколько примеров того, как изменить существующий XML-литерала.  
  
### <a name="to-modify-the-value-of-an-xml-literal"></a>Чтобы изменить значение XML-литерала  
  
1.  Чтобы изменить значение XML-литерала, получите ссылку на XML-литерал и задайте `Value` свойство нужное значение.  
  
     В следующем примере кода показано, как значение всех \<цена > элементов в XML-документа.  
  
     [!code-vb[VbXmlSamples2#4](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_1.vb)]  
  
     Ниже показан образец XML-источника и изменение XML из этого примера кода.  
  
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
    >  `Value` Свойство ссылается на первый XML-элемент в коллекции. Если имеется более одного элемента с тем же именем в коллекцию, задание `Value` свойство влияет только на первый элемент в коллекции.  
  
### <a name="to-add-an-attribute-to-an-xml-literal"></a>Чтобы добавить атрибут в XML-литерала  
  
1.  Чтобы добавить атрибут в XML-литерал, сначала получите ссылку на XML-литерал. Затем можно добавить атрибут, добавив новое свойство оси атрибута XML. Также можно добавить новый <xref:System.Xml.Linq.XAttribute> объекта для XML-литерала с помощью <xref:System.Xml.Linq.XContainer.Add%2A> метод. В следующем примере показано, как параметры.  
  
     [!code-vb[VbXmlSamples2#5](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_2.vb)]  
  
     Ниже показан образец XML-источника и изменение XML из этого примера кода.  
  
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
  
     Дополнительные сведения о свойствах атрибутов оси XML см. в разделе [свойство оси атрибута XML](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md).  
  
### <a name="to-add-an-element-to-an-xml-literal"></a>Чтобы добавить элемент в XML-литерала  
  
1.  Чтобы добавить элемент в XML-литерал, сначала получите ссылку на XML-литерал. Затем можно добавить новый <xref:System.Xml.Linq.XElement> объектов как последний дочерний элемент элемента с помощью <xref:System.Xml.Linq.XContainer.Add%2A> метод. Можно добавить новый <xref:System.Xml.Linq.XElement> объект как первый дочерний элемент с помощью <xref:System.Xml.Linq.XContainer.AddFirst%2A> метод.  
  
     Чтобы добавить новый элемент в определенное место относительно других вложенных элементов, сначала получите ссылку на смежные вложенный элемент. Затем можно добавить новый <xref:System.Xml.Linq.XElement> объекта перед соседними вложенными элементами с помощью <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> метод. Также можно добавить новый <xref:System.Xml.Linq.XElement> объекта после соседними вложенными элементами с помощью <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> метод.  
  
     В следующем примере показано примеры каждого из этих методов.  
  
     [!code-vb[VbXmlSamples2#6](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_3.vb)]  
  
     Ниже показан образец XML-источника и изменение XML из этого примера кода.  
  
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
  
### <a name="to-remove-an-element-or-attribute-from-an-xml-literal"></a>Чтобы удалить элемент или атрибут из XML-литерала  
  
1.  Чтобы удалить элемент или атрибут из XML-литерала, получите ссылку на элемент или атрибут и вызовите `Remove` метода, как показано в следующем примере.  
  
     [!code-vb[VbXmlSamples2#7](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_4.vb)]  
  
     Ниже показан образец XML-источника и изменение XML из этого примера кода.  
  
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
      </Book></Catalog>  
    ```  
  
     Чтобы удалить все элементы или атрибуты из XML-литерала, получите ссылку на XML-литерал и вызовите <xref:System.Xml.Linq.XElement.RemoveAll%2A> метод.  
  
### <a name="to-modify-an-xml-literal"></a>Для изменения XML-литерала  
  
1.  Чтобы изменить имя элемента XML, необходимо сначала получите ссылку на элемент. Затем можно создать новый <xref:System.Xml.Linq.XElement> объект, имеющий новое имя и передать этот <xref:System.Xml.Linq.XElement> объект <xref:System.Xml.Linq.XNode.ReplaceWith%2A> метод существующего <xref:System.Xml.Linq.XElement> объекта.  
  
     Если элемент, который вы заменяете имеет вложенные элементы, которые должны быть сохранены, задайте значение нового <xref:System.Xml.Linq.XElement> объект <xref:System.Xml.Linq.XContainer.Nodes%2A> свойства существующего элемента. Это будет присвоено значение нового элемента внутренний XML существующего элемента. В противном случае можно задать значение в новом элементе `Value` свойства существующего элемента.  
  
     В следующем примере кода заменяет все \<описание > элементы с \<абстрактный > элемент. Содержимое \<описание > элемент сохраняется в новом \<абстрактный > элемента с помощью <xref:System.Xml.Linq.XContainer.Nodes%2A> свойство \<описание > <xref:System.Xml.Linq.XElement> объекта.  
  
     [!code-vb[VbXmlSamples2#8](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_5.vb)]  
  
     Ниже показан образец XML-источника и изменение XML из этого примера кода.  
  
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
 [Работа с XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [Практическое руководство. Загрузка XML-кода из файла, строки или потока](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
