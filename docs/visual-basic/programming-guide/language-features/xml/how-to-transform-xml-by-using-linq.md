---
title: "Практическое руководство. Преобразование XML с помощью LINQ (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "LINQ to XML [Visual Basic], преобразование XML"
  - "XML [Visual Basic], преобразование"
ms.assetid: 815687f4-0bc2-4c0b-adc6-d78744aa356f
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Преобразование XML с помощью LINQ (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

[XML\-литералы](../../../../visual-basic/language-reference/xml-literals/index.md) упрощают чтение данных XML из одного источника и преобразование их к новому формату XML.  Можно воспользоваться преимуществами LINQ запросов для извлечения содержимого, которое требуется преобразовать, или преобразовывать содержимое существующего документа к новому формату XML.  
  
 Пример в этом разделе преобразует содержимое из исходного документа XML к HTML для просмотра в браузере.  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### Для преобразования XML\-документа  
  
1.  В Visual Studio создайте новый проект Visual Basic по шаблону **Console Application**.  
  
2.  Дважды щелкните по файлу Module1.vb в проекте, в котором требуется изменить код Visual Basic.  Добавьте следующий код в `Sub Main` модуля `Module1`.  Этот код создает исходный XML\-документ в виде объекта <xref:System.Xml.Linq.XDocument>.  
  
    ```vb#  
    Dim catalog =   
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
              Get the expert insights, practical code samples,   
              and best practices you need   
              to advance your expertise with <technology>Visual   
              Basic .NET</technology>.   
              Learn how to create faster, more reliable applications  
              based on professional,   
              pragmatic guidance by today's top <audience>developers</audience>.  
            </Description>  
          </Book>  
        </Catalog>  
    ```  
  
     [Практическое руководство. Загрузка XML\-кода из файла, строки или потока](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md).  
  
3.  После того, как код создаст исходный XML документ, добавьте следующий код для извлечения всех элементов \<Book\> из объекта и преобразования их к HTML документу.  Список, содержащий элементы \<Book\>, был создан с помощью LINQ запроса, возвращающего набор объектов <xref:System.Xml.Linq.XElement>, содержащих преобразованные данные HTML.  Можно использовать внедренные выражения для размещения значений из документа\-источника в новом XML\-формате.  
  
     Результирующий HTML\-документ записывается в файл с помощью метода <xref:System.Xml.Linq.XElement.Save%2A>.  
  
    ```vb#  
    Dim htmlOutput =   
      <html>  
        <body>  
          <%= From book In catalog.<Catalog>.<Book>   
              Select <div>  
                       <h1><%= book.<Title>.Value %></h1>  
                       <h3><%= "By " & book.<Author>.Value %></h3>  
                        <h3><%= "Price = " & book.<Price>.Value %></h3>  
                        <h2>Description</h2>  
                        <%= TransformDescription(book.<Description>(0)) %>  
                        <hr/>  
                      </div> %>  
        </body>  
      </html>  
  
    htmlOutput.Save("BookDescription.html")  
    ```  
  
4.  После `Sub Main` `Module1`, добавьте новый метод \(`Sub`\) для преобразования узла \<Description\> в указанный HTML формат.  Этот метод вызывается кодом на предыдущем шаге и используется для сохранения формата \<Description\> элементов.  
  
     Этот метод заменяет вложенные элементы \<Description\> элементом HTML.  Метод `ReplaceWith` используется для сохранения расположения вложенных элементов.  Преобразованное содержимое элемента \<Description\> включается в элемент абзаца HTML \(\<p\>\).  Свойство <xref:System.Xml.Linq.XContainer.Nodes%2A> используется для извлечения преобразованного содержимого \<Description\> элемента.  Это гарантирует, что вложенные элементы включены в преобразованное содержимое.  
  
     Добавьте следующий код сразу после `Sub Main` `Module1`.  
  
    ```vb#  
    Public Function TransformDescription(ByVal desc As XElement) As XElement  
  
      ' Replace <technology> elements with <b>.  
      Dim content = (From element In desc...<technology>).ToList()  
  
      If content.Count > 0 Then  
        For i = 0 To content.Count - 1  
          content(i).ReplaceWith(<b><%= content(i).Value %></b>)  
        Next  
      End If  
  
      ' Replace <audience> elements with <i>.  
      content = (From element In desc...<audience>).ToList()  
  
      If content.Count > 0 Then  
        For i = 0 To content.Count - 1  
          content(i).ReplaceWith(<i><%= content(i).Value %></i>)  
        Next  
      End If  
  
      ' Return the updated contents of the <Description> element.  
      Return <p><%= desc.Nodes %></p>  
    End Function  
    ```  
  
5.  Сохраните изменения.  
  
6.  Нажмите клавишу F5 для запуска кода.  Полученный сохраненный документ будет выглядеть следующим образом:  
  
    ```  
    <?xml version="1.0"?>  
    <html>  
      <body>  
        <div>  
          <h1>XML Developer's Guide</h1>  
          <h3>By Garghentini, Davide</h3>  
          <h3>Price = 44.95</h3>  
          <h2>Description</h2>  
          <p>  
            An in-depth look at creating applications  
            with <b>XML</b>. For   
            <i>beginners</i> or   
            <i>advanced</i> developers.  
          </p>  
          <hr />  
        </div>  
        <div>  
          <h1>Developing Applications with Visual Basic .NET</h1>  
          <h3>By Spencer, Phil</h3>  
          <h3>Price = 45.95</h3>  
          <h2>Description</h2>  
          <p>  
            Get the expert insights, practical code   
            samples, and best practices you need   
            to advance your expertise with <b>Visual   
            Basic .NET</b>. Learn how to create faster,  
            more reliable applications based on  
            professional, pragmatic guidance by today's   
            top <i>developers</i>.  
          </p>  
          <hr />  
        </div>  
      </body>  
    </html>  
    ```  
  
## См. также  
 [XML\-литералы](../../../../visual-basic/language-reference/xml-literals/index.md)   
 [Обработка XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)   
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)   
 [Практическое руководство. Загрузка XML\-кода из файла, строки или потока](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)   
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Знакомство с LINQ в Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)