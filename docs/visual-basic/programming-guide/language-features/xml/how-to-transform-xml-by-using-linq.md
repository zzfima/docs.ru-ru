---
title: "Практическое руководство. Преобразование XML с помощью LINQ (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML [Visual Basic], transforming
- LINQ to XML [Visual Basic], transforming XML
ms.assetid: 815687f4-0bc2-4c0b-adc6-d78744aa356f
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cf7c44598558b2c631ff3ef4c2ae0986a49ca2bd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-transform-xml-by-using-linq-visual-basic"></a><span data-ttu-id="4e23e-102">Практическое руководство. Преобразование XML с помощью LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e23e-102">How to: Transform XML by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="4e23e-103">[XML-литералы](../../../../visual-basic/language-reference/xml-literals/index.md) упрощают чтение данных XML из одного источника и преобразовать его в новый формат XML.</span><span class="sxs-lookup"><span data-stu-id="4e23e-103">[XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md) make it easy to read XML from one source and transform it to a new XML format.</span></span> <span data-ttu-id="4e23e-104">Можно воспользоваться преимуществами запросов LINQ для получения содержимого для преобразования или изменять содержимое существующего документа в новый формат XML.</span><span class="sxs-lookup"><span data-stu-id="4e23e-104">You can take advantage of LINQ queries to retrieve the content to transform, or change content in an existing document to a new XML format.</span></span>  
  
 <span data-ttu-id="4e23e-105">Пример в этом разделе преобразует содержимое из исходного документа XML в HTML для просмотра в браузере.</span><span class="sxs-lookup"><span data-stu-id="4e23e-105">The example in this topic transforms content from an XML source document to HTML to be viewed in a browser.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-transform-an-xml-document"></a><span data-ttu-id="4e23e-106">Для преобразования XML-документа</span><span class="sxs-lookup"><span data-stu-id="4e23e-106">To transform an XML document</span></span>  
  
1.  <span data-ttu-id="4e23e-107">В Visual Studio, создайте новый проект Visual Basic в **консольное приложение** шаблона проекта.</span><span class="sxs-lookup"><span data-stu-id="4e23e-107">In Visual Studio, create a new Visual Basic project in the **Console Application** project template.</span></span>  
  
2.  <span data-ttu-id="4e23e-108">Дважды щелкните файл Module1.vb, созданный в проекте, чтобы изменить код Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4e23e-108">Double-click the Module1.vb file created in the project to modify the Visual Basic code.</span></span> <span data-ttu-id="4e23e-109">Добавьте следующий код в `Sub Main` из `Module1` модуля.</span><span class="sxs-lookup"><span data-stu-id="4e23e-109">Add the following code to the `Sub Main` of the `Module1` module.</span></span> <span data-ttu-id="4e23e-110">Этот код создает исходный XML-документ как <xref:System.Xml.Linq.XDocument> объект.</span><span class="sxs-lookup"><span data-stu-id="4e23e-110">This code creates the source XML document as an <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
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
  
     <span data-ttu-id="4e23e-111">[Как: загрузить XML из файла, строки или потока](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md).</span><span class="sxs-lookup"><span data-stu-id="4e23e-111">[How to: Load XML from a File, String, or Stream](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md).</span></span>  
  
3.  <span data-ttu-id="4e23e-112">После кода для создания исходного XML-документа, добавьте следующий код для извлечения всех \<Book > элементы из объекта и преобразовать их в HTML-документе.</span><span class="sxs-lookup"><span data-stu-id="4e23e-112">After the code to create the source XML document, add the following code to retrieve all the \<Book> elements from the object and transform them into an HTML document.</span></span> <span data-ttu-id="4e23e-113">Список \<Book > элементов создается с помощью запроса LINQ, возвращающий коллекцию <xref:System.Xml.Linq.XElement> объектов, содержащих преобразованные данные HTML.</span><span class="sxs-lookup"><span data-stu-id="4e23e-113">The list of \<Book> elements is created by using a LINQ query that returns a collection of <xref:System.Xml.Linq.XElement> objects that contain the transformed HTML.</span></span> <span data-ttu-id="4e23e-114">Внедренные выражения можно использовать для размещения значений из исходного документа в новый формат XML.</span><span class="sxs-lookup"><span data-stu-id="4e23e-114">You can use embedded expressions to put the values from the source document in the new XML format.</span></span>  
  
     <span data-ttu-id="4e23e-115">Результирующий HTML-документ записывается в файл с помощью <xref:System.Xml.Linq.XElement.Save%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="4e23e-115">The resulting HTML document is written to a file by using the <xref:System.Xml.Linq.XElement.Save%2A> method.</span></span>  
  
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
  
4.  <span data-ttu-id="4e23e-116">После `Sub Main` из `Module1`, добавьте новый метод (`Sub`) для преобразования \<описание > узла в указанном формате HTML.</span><span class="sxs-lookup"><span data-stu-id="4e23e-116">After `Sub Main` of `Module1`, add a new method (`Sub`) to transform a \<Description> node into the specified HTML format.</span></span> <span data-ttu-id="4e23e-117">Этот метод вызывается кодом на предыдущем шаге и используется для сохранения формат \<описание > элементов.</span><span class="sxs-lookup"><span data-stu-id="4e23e-117">This method is called by the code in the previous step and is used to preserve the format of the \<Description> elements.</span></span>  
  
     <span data-ttu-id="4e23e-118">Этот метод заменяет вложенные элементы \<описание > элементом HTML.</span><span class="sxs-lookup"><span data-stu-id="4e23e-118">This method replaces sub-elements of the \<Description> element with HTML.</span></span> <span data-ttu-id="4e23e-119">`ReplaceWith` Метод используется для сохранения расположения вложенных элементов.</span><span class="sxs-lookup"><span data-stu-id="4e23e-119">The `ReplaceWith` method is used to preserve the location of the sub-elements.</span></span> <span data-ttu-id="4e23e-120">Преобразованное содержимое \<описание > элемент включен в абзаце HTML (\<p >) элемент.</span><span class="sxs-lookup"><span data-stu-id="4e23e-120">The transformed content of the \<Description> element is included in an HTML paragraph (\<p>) element.</span></span> <span data-ttu-id="4e23e-121"><xref:System.Xml.Linq.XContainer.Nodes%2A> Свойство используется для извлечения преобразованного содержимого \<описание > элемент.</span><span class="sxs-lookup"><span data-stu-id="4e23e-121">The <xref:System.Xml.Linq.XContainer.Nodes%2A> property is used to retrieve the transformed content of the \<Description> element.</span></span> <span data-ttu-id="4e23e-122">Это гарантирует, что вложенные элементы включены в преобразованное содержимое.</span><span class="sxs-lookup"><span data-stu-id="4e23e-122">This ensures that sub-elements are included in the transformed content.</span></span>  
  
     <span data-ttu-id="4e23e-123">Добавьте следующий код после `Sub Main` из `Module1`.</span><span class="sxs-lookup"><span data-stu-id="4e23e-123">Add the following code after `Sub Main` of `Module1`.</span></span>  
  
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
  
5.  <span data-ttu-id="4e23e-124">Сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="4e23e-124">Save your changes.</span></span>  
  
6.  <span data-ttu-id="4e23e-125">Нажмите клавишу F5 для запуска кода.</span><span class="sxs-lookup"><span data-stu-id="4e23e-125">Press F5 to run the code.</span></span> <span data-ttu-id="4e23e-126">Полученный сохраненный документ будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4e23e-126">The resulting saved document will resemble the following:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4e23e-127">См. также</span><span class="sxs-lookup"><span data-stu-id="4e23e-127">See Also</span></span>  
 [<span data-ttu-id="4e23e-128">XML-литералы</span><span class="sxs-lookup"><span data-stu-id="4e23e-128">XML Literals</span></span>](../../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="4e23e-129">Работа с XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4e23e-129">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 [<span data-ttu-id="4e23e-130">XML</span><span class="sxs-lookup"><span data-stu-id="4e23e-130">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [<span data-ttu-id="4e23e-131">Практическое руководство. Загрузка XML-кода из файла, строки или потока</span><span class="sxs-lookup"><span data-stu-id="4e23e-131">How to: Load XML from a File, String, or Stream</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)  
 [<span data-ttu-id="4e23e-132">LINQ</span><span class="sxs-lookup"><span data-stu-id="4e23e-132">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 <span data-ttu-id="4e23e-133">[Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e23e-133">[Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
