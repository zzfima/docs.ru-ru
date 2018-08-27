---
title: Практическое руководство. Преобразование XML с помощью LINQ (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], transforming
- LINQ to XML [Visual Basic], transforming XML
ms.assetid: 815687f4-0bc2-4c0b-adc6-d78744aa356f
ms.openlocfilehash: 94ad5180c7921a5ace09f9161de5f275475e46d4
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2018
ms.locfileid: "42924913"
---
# <a name="how-to-transform-xml-by-using-linq-visual-basic"></a>Практическое руководство. Преобразование XML с помощью LINQ (Visual Basic)
[XML-литералов](../../../../visual-basic/language-reference/xml-literals/index.md) упрощают чтение данных XML из одного источника и преобразовать его в новый формат XML. Можно воспользоваться преимуществами запросов LINQ для получения содержимого для преобразования или изменять содержимое существующего документа в новый формат XML.  
  
 Пример в этом разделе преобразует содержимое из исходного документа XML в HTML для просмотра в браузере.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-transform-an-xml-document"></a>Для преобразования XML-документа  
  
1.  В Visual Studio создайте новый проект Visual Basic в **консольное приложение** шаблона проекта.  
  
2.  Дважды щелкните файл Module1.vb, созданный в проекте, чтобы изменить код Visual Basic. Добавьте следующий код, чтобы `Sub Main` из `Module1` модуля. Этот код создает XML-документа источника <xref:System.Xml.Linq.XDocument> объекта.  
  
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
  
     [Практическое: загрузить XML из файла, строки или Stream](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md).  
  
3.  После кода, чтобы создать исходный XML-документ, добавьте следующий код для извлечения всех \<книги > элементы из объекта и преобразования их в документ HTML. Список \<книги > элементов создается с помощью запроса LINQ, который возвращает коллекцию <xref:System.Xml.Linq.XElement> объектов, содержащих преобразованные данные HTML. Внедренные выражения можно использовать для размещения значений из исходного документа в новый формат XML.  
  
     Результирующий HTML-документ записывается в файл с помощью <xref:System.Xml.Linq.XElement.Save%2A> метод.  
  
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
  
4.  После `Sub Main` из `Module1`, добавьте новый метод (`Sub`) для преобразования \<описание > узел в указанном формате HTML. Этот метод вызывается в коде на предыдущем шаге и используется для сохранения формат \<описание > элементы.  
  
     Этот метод заменяет вложенные элементы \<описание > элементом HTML. `ReplaceWith` Метод используется для сохранения расположения вложенных элементов. Преобразованное содержимое \<описание > элемент включен в абзаце HTML (\<p >) элемента. <xref:System.Xml.Linq.XContainer.Nodes%2A> Свойство используется для получения преобразованного содержимого \<описание > элемента. Это гарантирует, что вложенные элементы включены в преобразованное содержимое.  
  
     Добавьте следующий код после `Sub Main` из `Module1`.  
  
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
  
5.  Сохраните изменения.  
  
6.  Нажмите клавишу F5 для выполнения кода. Полученный сохраненный документ будет выглядеть следующим образом:  
  
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
  
## <a name="see-also"></a>См. также  
 [XML-литералы](../../../../visual-basic/language-reference/xml-literals/index.md)  
 [Работа с XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [Практическое руководство. Загрузка XML-кода из файла, строки или потока](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
