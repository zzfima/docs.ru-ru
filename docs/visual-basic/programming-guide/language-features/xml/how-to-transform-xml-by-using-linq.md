---
title: "Практическое руководство: преобразование XML с помощью LINQ (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- XML [Visual Basic], transforming
- LINQ to XML [Visual Basic], transforming XML
ms.assetid: 815687f4-0bc2-4c0b-adc6-d78744aa356f
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: 12b5bfd059d219a5cb0087e763688d01a75b0533
ms.contentlocale: ru-ru
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-transform-xml-by-using-linq-visual-basic"></a><span data-ttu-id="f6a54-102">Практическое руководство. Преобразование XML с помощью LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f6a54-102">How to: Transform XML by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="f6a54-103">[XML-литералы](../../../../visual-basic/language-reference/xml-literals/index.md) упрощают чтение данных XML из одного источника и преобразование их к новому формату XML.</span><span class="sxs-lookup"><span data-stu-id="f6a54-103">[XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md) make it easy to read XML from one source and transform it to a new XML format.</span></span> <span data-ttu-id="f6a54-104">Можно воспользоваться преимуществами запросов LINQ для получения содержимого для преобразования или изменять содержимое существующего документа к новому формату XML.</span><span class="sxs-lookup"><span data-stu-id="f6a54-104">You can take advantage of LINQ queries to retrieve the content to transform, or change content in an existing document to a new XML format.</span></span>  
  
 <span data-ttu-id="f6a54-105">Пример в этом разделе преобразует содержимое из исходного документа XML к HTML для просмотра в обозревателе.</span><span class="sxs-lookup"><span data-stu-id="f6a54-105">The example in this topic transforms content from an XML source document to HTML to be viewed in a browser.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-transform-an-xml-document"></a><span data-ttu-id="f6a54-106">Для преобразования XML-документа</span><span class="sxs-lookup"><span data-stu-id="f6a54-106">To transform an XML document</span></span>  
  
1.  <span data-ttu-id="f6a54-107">В Visual Studio создайте новый проект Visual Basic в **консольное приложение** шаблона проекта.</span><span class="sxs-lookup"><span data-stu-id="f6a54-107">In Visual Studio, create a new Visual Basic project in the **Console Application** project template.</span></span>  
  
2.  <span data-ttu-id="f6a54-108">Дважды щелкните файл Module1.vb, созданный в проекте, чтобы изменить код Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f6a54-108">Double-click the Module1.vb file created in the project to modify the Visual Basic code.</span></span> <span data-ttu-id="f6a54-109">Добавьте следующий код в `Sub Main` из `Module1` модуля.</span><span class="sxs-lookup"><span data-stu-id="f6a54-109">Add the following code to the `Sub Main` of the `Module1` module.</span></span> <span data-ttu-id="f6a54-110">Этот код создает исходный XML-документ как <xref:System.Xml.Linq.XDocument>объект.</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="f6a54-110">This code creates the source XML document as an <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
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
  
     <span data-ttu-id="f6a54-111">[Практическое руководство: загрузка XML из файла, строки или потока](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md).</span><span class="sxs-lookup"><span data-stu-id="f6a54-111">[How to: Load XML from a File, String, or Stream](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md).</span></span>  
  
3.  <span data-ttu-id="f6a54-112">После кода, чтобы создать исходный XML-документ, добавьте следующий код для извлечения всех \<книги настроек элементы из объекта и преобразования их в документ HTML.</span><span class="sxs-lookup"><span data-stu-id="f6a54-112">After the code to create the source XML document, add the following code to retrieve all the \<Book> elements from the object and transform them into an HTML document.</span></span> <span data-ttu-id="f6a54-113">Список \<книги настроек элементов создается с помощью запроса LINQ, который возвращает коллекцию <xref:System.Xml.Linq.XElement>объектов, содержащих преобразованные данные HTML.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="f6a54-113">The list of \<Book> elements is created by using a LINQ query that returns a collection of <xref:System.Xml.Linq.XElement> objects that contain the transformed HTML.</span></span> <span data-ttu-id="f6a54-114">Можно использовать внедренные выражения для размещения значений из документа-источника в новый формат XML.</span><span class="sxs-lookup"><span data-stu-id="f6a54-114">You can use embedded expressions to put the values from the source document in the new XML format.</span></span>  
  
     <span data-ttu-id="f6a54-115">Результирующий HTML-документ записывается в файл с помощью <xref:System.Xml.Linq.XElement.Save%2A>метод.</xref:System.Xml.Linq.XElement.Save%2A></span><span class="sxs-lookup"><span data-stu-id="f6a54-115">The resulting HTML document is written to a file by using the <xref:System.Xml.Linq.XElement.Save%2A> method.</span></span>  
  
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
  
4.  <span data-ttu-id="f6a54-116">После `Sub Main` из `Module1`, добавьте новый метод (`Sub`) для преобразования \<описание настроек узла в указанном формате HTML.</span><span class="sxs-lookup"><span data-stu-id="f6a54-116">After `Sub Main` of `Module1`, add a new method (`Sub`) to transform a \<Description> node into the specified HTML format.</span></span> <span data-ttu-id="f6a54-117">Этот метод вызывается кодом на предыдущем шаге и используется для сохранения формат \<описание настроек элементов.</span><span class="sxs-lookup"><span data-stu-id="f6a54-117">This method is called by the code in the previous step and is used to preserve the format of the \<Description> elements.</span></span>  
  
     <span data-ttu-id="f6a54-118">Этот метод заменяет вложенные элементы \<описание настроек элементом HTML.</span><span class="sxs-lookup"><span data-stu-id="f6a54-118">This method replaces sub-elements of the \<Description> element with HTML.</span></span> <span data-ttu-id="f6a54-119">`ReplaceWith` Метод используется для сохранения расположения вложенных элементов.</span><span class="sxs-lookup"><span data-stu-id="f6a54-119">The `ReplaceWith` method is used to preserve the location of the sub-elements.</span></span> <span data-ttu-id="f6a54-120">Преобразованное содержимое \<описание настроек элемент включен в абзаца HTML (\<p настроек) элемент.</span><span class="sxs-lookup"><span data-stu-id="f6a54-120">The transformed content of the \<Description> element is included in an HTML paragraph (\<p>) element.</span></span> <span data-ttu-id="f6a54-121"><xref:System.Xml.Linq.XContainer.Nodes%2A>Свойство используется для извлечения преобразованного содержимого \<описание настроек элемент.</xref:System.Xml.Linq.XContainer.Nodes%2A></span><span class="sxs-lookup"><span data-stu-id="f6a54-121">The <xref:System.Xml.Linq.XContainer.Nodes%2A> property is used to retrieve the transformed content of the \<Description> element.</span></span> <span data-ttu-id="f6a54-122">Это гарантирует, что вложенные элементы включены в преобразованное содержимое.</span><span class="sxs-lookup"><span data-stu-id="f6a54-122">This ensures that sub-elements are included in the transformed content.</span></span>  
  
     <span data-ttu-id="f6a54-123">Добавьте следующий код после `Sub Main` из `Module1`.</span><span class="sxs-lookup"><span data-stu-id="f6a54-123">Add the following code after `Sub Main` of `Module1`.</span></span>  
  
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
  
5.  <span data-ttu-id="f6a54-124">Сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="f6a54-124">Save your changes.</span></span>  
  
6.  <span data-ttu-id="f6a54-125">Нажмите клавишу F5 для запуска кода.</span><span class="sxs-lookup"><span data-stu-id="f6a54-125">Press F5 to run the code.</span></span> <span data-ttu-id="f6a54-126">Полученный сохраненный документ будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f6a54-126">The resulting saved document will resemble the following:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f6a54-127">См. также</span><span class="sxs-lookup"><span data-stu-id="f6a54-127">See Also</span></span>  
 <span data-ttu-id="f6a54-128">[XML-литералы](../../../../visual-basic/language-reference/xml-literals/index.md) </span><span class="sxs-lookup"><span data-stu-id="f6a54-128">[XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md) </span></span>  
<span data-ttu-id="f6a54-129"> [Обработка XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="f6a54-129"> [Manipulating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md) </span></span>  
<span data-ttu-id="f6a54-130"> [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) </span><span class="sxs-lookup"><span data-stu-id="f6a54-130"> [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) </span></span>  
<span data-ttu-id="f6a54-131"> [Практическое руководство: загрузка XML из файла, строки или потока](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md) </span><span class="sxs-lookup"><span data-stu-id="f6a54-131"> [How to: Load XML from a File, String, or Stream](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md) </span></span>  
<span data-ttu-id="f6a54-132"> [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="f6a54-132"> [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="f6a54-133"> [Введение в LINQ в Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span><span class="sxs-lookup"><span data-stu-id="f6a54-133"> [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>

