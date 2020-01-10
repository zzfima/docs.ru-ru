---
title: Извлечение XML-данных с помощью XPathNavigator
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 095b0987-ee4b-4595-a160-da1c956ad576
ms.openlocfilehash: 627da3c8c45d007e677c4f92f4d5cd602d34ae84
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710860"
---
# <a name="extract-xml-data-using-xpathnavigator"></a><span data-ttu-id="68ba5-102">Извлечение XML-данных с помощью XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="68ba5-102">Extract XML Data Using XPathNavigator</span></span>
<span data-ttu-id="68ba5-103">В платформе Microsoft .NET Framework есть несколько способов представления XML-документа.</span><span class="sxs-lookup"><span data-stu-id="68ba5-103">There are several different ways to represent an XML document in the Microsoft .NET Framework.</span></span> <span data-ttu-id="68ba5-104">К ним относится использование класса <xref:System.String>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, <xref:System.Xml.XmlDocument> или <xref:System.Xml.XPath.XPathDocument>.</span><span class="sxs-lookup"><span data-stu-id="68ba5-104">This includes using a <xref:System.String>, or by using the <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, <xref:System.Xml.XmlDocument>, or <xref:System.Xml.XPath.XPathDocument> classes.</span></span> <span data-ttu-id="68ba5-105">Чтобы ускорить перемещение между различными представлениями XML-документа, в классе <xref:System.Xml.XPath.XPathNavigator> предусмотрено несколько методов и свойств для извлечения XML как объекта <xref:System.String>, <xref:System.Xml.XmlReader> или <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="68ba5-105">To facilitate moving between these different representations of an XML document, the <xref:System.Xml.XPath.XPathNavigator> class provides a number of methods and properties for extracting the XML as a <xref:System.String>, <xref:System.Xml.XmlReader> object or <xref:System.Xml.XmlWriter> object.</span></span>  
  
## <a name="convert-an-xpathnavigator-to-a-string"></a><span data-ttu-id="68ba5-106">Преобразование XPathNavigator в строку</span><span class="sxs-lookup"><span data-stu-id="68ba5-106">Convert an XPathNavigator to a String</span></span>  
 <span data-ttu-id="68ba5-107">Свойство <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> класса <xref:System.Xml.XPath.XPathNavigator> используется для получения разметки всего XML-документа или просто разметки одного узла и его дочерних узлов.</span><span class="sxs-lookup"><span data-stu-id="68ba5-107">The <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> property of the <xref:System.Xml.XPath.XPathNavigator> class is used to get the markup of the entire XML document or just the markup of a single node and its child nodes.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="68ba5-108">Свойство <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> получает разметку или просто дочерние узлы данного узла.</span><span class="sxs-lookup"><span data-stu-id="68ba5-108">The <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> property gets the markup of just the child nodes of a node.</span></span>  
  
 <span data-ttu-id="68ba5-109">В следующем примере кода показано, как сохранить целый XML-документ, содержащийся в объекте <xref:System.Xml.XPath.XPathNavigator> как <xref:System.String>, а также один узел и его дочерние узлы.</span><span class="sxs-lookup"><span data-stu-id="68ba5-109">The following code example shows how to save an entire XML document contained in an <xref:System.Xml.XPath.XPathNavigator> object as a <xref:System.String>, as well as a single node and its child nodes.</span></span>  
  
```vb  
Dim document As XPathDocument = New XPathDocument("input.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
' Save the entire input.xml document to a string.  
Dim xml As String = navigator.OuterXml  
  
' Now save the Root element and its child nodes to a string.  
navigator.MoveToChild(XPathNodeType.Element)  
Dim root As String = navigator.OuterXml  
```  
  
```csharp  
XPathDocument document = new XPathDocument("input.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
// Save the entire input.xml document to a string.  
string xml = navigator.OuterXml;  
  
// Now save the Root element and its child nodes to a string.  
navigator.MoveToChild(XPathNodeType.Element);  
string root = navigator.OuterXml;  
```  
  
## <a name="convert-an-xpathnavigator-to-an-xmlreader"></a><span data-ttu-id="68ba5-110">Преобразование XPathNavigator в XmlReader</span><span class="sxs-lookup"><span data-stu-id="68ba5-110">Convert an XPathNavigator to an XmlReader</span></span>  
 <span data-ttu-id="68ba5-111">Метод <xref:System.Xml.XPath.XPathNavigator.ReadSubtree%2A> используется для потоковой записи всего содержимого XML-документа или отдельного его узла с дочерними узлами в объект <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="68ba5-111">The <xref:System.Xml.XPath.XPathNavigator.ReadSubtree%2A> method is used to stream the entire contents of an XML document or just a single node and its child nodes to an <xref:System.Xml.XmlReader> object.</span></span>  
  
 <span data-ttu-id="68ba5-112">Когда объект <xref:System.Xml.XmlReader> создан с текущим узлом и дочерними узлами, свойство <xref:System.Xml.XmlReader> объекта <xref:System.Xml.XmlReader.ReadState%2A> имеет значение <xref:System.Xml.ReadState.Initial>.</span><span class="sxs-lookup"><span data-stu-id="68ba5-112">When the <xref:System.Xml.XmlReader> object is created with the current node and its child nodes, the <xref:System.Xml.XmlReader> object's <xref:System.Xml.XmlReader.ReadState%2A> property is set to <xref:System.Xml.ReadState.Initial>.</span></span> <span data-ttu-id="68ba5-113">Когда метод <xref:System.Xml.XmlReader> объекта <xref:System.Xml.XmlReader.Read%2A> вызывается в первый раз, <xref:System.Xml.XmlReader> перемещается в текущий узел <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="68ba5-113">When the <xref:System.Xml.XmlReader> object's <xref:System.Xml.XmlReader.Read%2A> method is called for the first time, the <xref:System.Xml.XmlReader> is moved to the current node of the <xref:System.Xml.XPath.XPathNavigator>.</span></span> <span data-ttu-id="68ba5-114">Новый объект <xref:System.Xml.XmlReader> продолжает считывание до тех пор, пока не будет достигнут конец XML-дерева.</span><span class="sxs-lookup"><span data-stu-id="68ba5-114">The new <xref:System.Xml.XmlReader> object continues to read until the end of the XML tree is reached.</span></span> <span data-ttu-id="68ba5-115">На этом этапе метод <xref:System.Xml.XmlReader.Read%2A> возвращает `false`, а свойство <xref:System.Xml.XmlReader> объекта <xref:System.Xml.XmlReader.ReadState%2A> имеет значение <xref:System.Xml.ReadState.EndOfFile>.</span><span class="sxs-lookup"><span data-stu-id="68ba5-115">At this point, the <xref:System.Xml.XmlReader.Read%2A> method returns `false` and the <xref:System.Xml.XmlReader> object's <xref:System.Xml.XmlReader.ReadState%2A> property is set to <xref:System.Xml.ReadState.EndOfFile>.</span></span>  
  
 <span data-ttu-id="68ba5-116">Позиция объекта <xref:System.Xml.XPath.XPathNavigator> не изменяется при создании или перемещении объекта <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="68ba5-116">The <xref:System.Xml.XPath.XPathNavigator> object's position is unchanged by the creation or movement of the <xref:System.Xml.XmlReader> object.</span></span> <span data-ttu-id="68ba5-117">Метод <xref:System.Xml.XPath.XPathNavigator.ReadSubtree%2A> допустим только при размещении на элементе или в корневом узле.</span><span class="sxs-lookup"><span data-stu-id="68ba5-117">The <xref:System.Xml.XPath.XPathNavigator.ReadSubtree%2A> method is only valid when positioned on an element or root node.</span></span>  
  
 <span data-ttu-id="68ba5-118">Следующий пример показывает, как получить объект <xref:System.Xml.XmlReader>, содержащий весь XML-документ в объекте <xref:System.Xml.XPath.XPathDocument>, так же как и для отдельного узла с дочерними узлами.</span><span class="sxs-lookup"><span data-stu-id="68ba5-118">The following example shows how to get an <xref:System.Xml.XmlReader> object containing the entire XML document in an <xref:System.Xml.XPath.XPathDocument> object as well as a single node and its child nodes.</span></span>  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
' Stream the entire XML document to the XmlReader.  
Dim xml As XmlReader = navigator.ReadSubtree()  
  
While xml.Read()  
    Console.WriteLine(xml.ReadInnerXml())  
End While  
  
xml.Close()  
  
' Stream the book element and its child nodes to the XmlReader.  
navigator.MoveToChild("bookstore", "")  
navigator.MoveToChild("book", "")  
  
Dim book As XmlReader = navigator.ReadSubtree()  
  
While book.Read()  
    Console.WriteLine(book.ReadInnerXml())  
End While  
  
book.Close()  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
// Stream the entire XML document to the XmlReader.  
XmlReader xml = navigator.ReadSubtree();  
  
while (xml.Read())  
{  
    Console.WriteLine(xml.ReadInnerXml());  
}  
  
xml.Close();  
  
// Stream the book element and its child nodes to the XmlReader.  
navigator.MoveToChild("bookstore", "");  
navigator.MoveToChild("book", "");  
  
XmlReader book = navigator.ReadSubtree();  
  
while (book.Read())  
{  
    Console.WriteLine(book.ReadInnerXml());  
}  
  
book.Close();  
```  
  
 <span data-ttu-id="68ba5-119">В примере в качестве входных данных используется файл `books.xml`.</span><span class="sxs-lookup"><span data-stu-id="68ba5-119">The example takes the `books.xml` file as input.</span></span>  
  
 [!code-xml[XPathXMLExamples#1](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/books.xml#1)]  
  
## <a name="converting-an-xpathnavigator-to-an-xmlwriter"></a><span data-ttu-id="68ba5-120">Преобразование XPathNavigator в XmlWriter</span><span class="sxs-lookup"><span data-stu-id="68ba5-120">Converting an XPathNavigator to an XmlWriter</span></span>  
 <span data-ttu-id="68ba5-121">Метод <xref:System.Xml.XPath.XPathNavigator.WriteSubtree%2A> используется для потоковой записи всего содержимого XML-документа или отдельного его узла с дочерними узлами в объект <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="68ba5-121">The <xref:System.Xml.XPath.XPathNavigator.WriteSubtree%2A> method is used to stream the entire contents of an XML document or just a single node and its child nodes to an <xref:System.Xml.XmlWriter> object.</span></span>  
  
 <span data-ttu-id="68ba5-122">Позиция объекта <xref:System.Xml.XPath.XPathNavigator> не изменяется при создании объекта <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="68ba5-122">The <xref:System.Xml.XPath.XPathNavigator> object's position is unchanged by the creation of the <xref:System.Xml.XmlWriter> object.</span></span>  
  
 <span data-ttu-id="68ba5-123">Следующий пример показывает, как получить объект <xref:System.Xml.XmlWriter>, содержащий весь XML-документ в объекте <xref:System.Xml.XPath.XPathDocument>, так же как и для отдельного узла с дочерними узлами.</span><span class="sxs-lookup"><span data-stu-id="68ba5-123">The following example shows how to get an <xref:System.Xml.XmlWriter> object containing the entire XML document in an <xref:System.Xml.XPath.XPathDocument> object as well as a single node and its child nodes.</span></span>  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
' Stream the entire XML document to the XmlWriter.  
Dim xml As XmlWriter = XmlWriter.Create("newbooks.xml")  
navigator.WriteSubtree(xml)  
xml.Close()  
  
' Stream the book element and its child nodes to the XmlWriter.  
navigator.MoveToChild("bookstore", "")  
navigator.MoveToChild("book", "")  
  
Dim book As XmlWriter = XmlWriter.Create("book.xml")  
navigator.WriteSubtree(book)  
book.Close()  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
// Stream the entire XML document to the XmlWriter.  
XmlWriter xml = XmlWriter.Create("newbooks.xml");  
navigator.WriteSubtree(xml);  
xml.Close();  
  
// Stream the book element and its child nodes to the XmlWriter.  
navigator.MoveToChild("bookstore", "");  
navigator.MoveToChild("book", "");  
  
XmlWriter book = XmlWriter.Create("book.xml");  
navigator.WriteSubtree(book);  
book.Close();  
```  
  
 <span data-ttu-id="68ba5-124">В данном примере в качестве входного файла используется указанный выше файл `books.xml`.</span><span class="sxs-lookup"><span data-stu-id="68ba5-124">The example takes the `books.xml` file found earlier in this topic as input.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68ba5-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="68ba5-125">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="68ba5-126">Обработка XML-данных с использованием модели данных XPath</span><span class="sxs-lookup"><span data-stu-id="68ba5-126">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="68ba5-127">Навигация в наборе узлов с помощью XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="68ba5-127">Node Set Navigation Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md)
- [<span data-ttu-id="68ba5-128">Навигация по узлам атрибутов и пространств имен с помощью XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="68ba5-128">Attribute and Namespace Node Navigation Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md)
- [<span data-ttu-id="68ba5-129">Доступ к XML-данным со строгой типизацией с помощью XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="68ba5-129">Accessing Strongly Typed XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-strongly-typed-xml-data-using-xpathnavigator.md)
