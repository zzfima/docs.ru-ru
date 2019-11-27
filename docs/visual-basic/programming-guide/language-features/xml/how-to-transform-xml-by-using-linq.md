---
title: Практическое руководство. Преобразование XML с помощью LINQ
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], transforming
- LINQ to XML [Visual Basic], transforming XML
ms.assetid: 815687f4-0bc2-4c0b-adc6-d78744aa356f
ms.openlocfilehash: a531b189074ac7bdd1c02935368c408ff506a6f1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353651"
---
# <a name="how-to-transform-xml-by-using-linq-visual-basic"></a>Практическое руководство. Преобразование XML с помощью LINQ (Visual Basic)

[XML-литералы](../../../../visual-basic/language-reference/xml-literals/index.md) позволяют легко считывать XML-код из одного источника и преобразовывать его в новый формат XML. Можно использовать запросы LINQ для получения содержимого для преобразования или изменения содержимого существующего документа в новый формат XML.

Пример в этом разделе преобразует содержимое из исходного документа XML в HTML для просмотра в браузере.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

### <a name="to-transform-an-xml-document"></a>Преобразование XML-документа

1. В Visual Studio создайте новый проект Visual Basic в шаблоне проекта **консольное приложение** .

2. Дважды щелкните файл Module1. vb, созданный в проекте, чтобы изменить код Visual Basic. Добавьте следующий код в `Sub Main` модуля `Module1`. Этот код создает исходный XML-документ как объект <xref:System.Xml.Linq.XDocument>.

    ```vb
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

     [Как загрузить XML из файла, строки или потока](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md).

3. После создания исходного XML-документа добавьте следующий код, чтобы извлечь все элементы \<Book > из объекта и преобразовать их в HTML-документ. Список элементов \<Book > создается с помощью запроса LINQ, возвращающего коллекцию объектов <xref:System.Xml.Linq.XElement>, содержащих преобразованный HTML. Внедренные выражения можно использовать для размещения значений из исходного документа в новом XML-формате.

     Полученный HTML-документ записывается в файл с помощью метода <xref:System.Xml.Linq.XElement.Save%2A>.

    ```vb
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

4. После `Sub Main` `Module1`добавьте новый метод (`Sub`) для преобразования \<описания > узла в указанный формат HTML. Этот метод вызывается кодом на предыдущем шаге и используется для сохранения формата \<Description > элементов.

     Этот метод заменяет вложенные элементы \<Description > элемента HTML. Метод `ReplaceWith` используется для сохранения расположения вложенных элементов. Преобразованное содержимое элемента \<Description > включено в элемент HTML-Абзац (\<p >). Свойство <xref:System.Xml.Linq.XContainer.Nodes%2A> используется для получения преобразованного содержимого элемента \<Description >. Это гарантирует, что вложенные элементы будут включены в преобразованное содержимое.

     Добавьте следующий код после `Sub Main` `Module1`.

    ```vb
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

5. Сохраните изменения.

6. Нажмите клавишу F5, чтобы выполнить код. Полученный сохраненный документ будет выглядеть следующим образом:

    ```html
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

## <a name="see-also"></a>См. также

- [XML-литералы](../../../../visual-basic/language-reference/xml-literals/index.md)
- [Работа с XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [Практическое руководство. Загрузка XML-кода из файла, строки или потока](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
