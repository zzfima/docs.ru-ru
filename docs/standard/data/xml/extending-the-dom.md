---
title: Расширение модели DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: b5489c96-4afd-439a-a25d-fc82eb4a148d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3224250b08a780b87b9b7f96547830b0563daadf
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351936"
---
# <a name="extending-the-dom"></a><span data-ttu-id="dac75-102">Расширение модели DOM</span><span class="sxs-lookup"><span data-stu-id="dac75-102">Extending the DOM</span></span>

<span data-ttu-id="dac75-103">Платформа Microsoft .NET Framework включает базовый набор классов, обеспечивающих реализацию модели DOM.</span><span class="sxs-lookup"><span data-stu-id="dac75-103">The Microsoft .NET Framework includes a base set of classes that provides an implementation of the XML Document Object Model (DOM).</span></span> <span data-ttu-id="dac75-104">Объект <xref:System.Xml.XmlNode> и его производные классы предоставляют методы и свойства, позволяющие переходить по содержимому и структуре XML-документа, запрашивать и изменять это содержимое и структуру.</span><span class="sxs-lookup"><span data-stu-id="dac75-104">The <xref:System.Xml.XmlNode>, and its derived classes, provides methods and properties that allow you to navigate, query, and modify the content and structure of an XML document.</span></span>

<span data-ttu-id="dac75-105">Если содержимое XML загружается в память с помощью модели DOM, созданные узлы содержат такие сведения, как имя узла, тип узла и так далее.</span><span class="sxs-lookup"><span data-stu-id="dac75-105">When XML content is loaded into memory using the DOM, the nodes created contain information such as node name, node type, and so on.</span></span> <span data-ttu-id="dac75-106">Могут быть случаи, когда необходимы конкретные данные об узле, которые не предоставляют базовые классы.</span><span class="sxs-lookup"><span data-stu-id="dac75-106">There may be occasions where you require specific node information that the base classes do not provide.</span></span> <span data-ttu-id="dac75-107">Например, может потребоваться узнать номер строки и позицию узла.</span><span class="sxs-lookup"><span data-stu-id="dac75-107">For example, you may want to see the line number and position of the node.</span></span> <span data-ttu-id="dac75-108">В этом случае можно произвести новые классы из существующих классов DOM, создав для них дополнительные возможности.</span><span class="sxs-lookup"><span data-stu-id="dac75-108">In this case, you can derive new classes from the existing DOM classes and add additional functionality.</span></span>

<span data-ttu-id="dac75-109">Есть две общие рекомендации для создания новых классов из существующих.</span><span class="sxs-lookup"><span data-stu-id="dac75-109">There are two general guidelines when deriving new classes:</span></span>

- <span data-ttu-id="dac75-110">Рекомендуется никогда не создавать производных классов от класса <xref:System.Xml.XmlNode>.</span><span class="sxs-lookup"><span data-stu-id="dac75-110">It is recommended that you never derive from the <xref:System.Xml.XmlNode> class.</span></span> <span data-ttu-id="dac75-111">Вместо этого рекомендуется наследовать классы от класса, соответствующего типу интересующего вас узла.</span><span class="sxs-lookup"><span data-stu-id="dac75-111">Instead, it is recommended that you derive classes from the class corresponding to the node type that you are interested in.</span></span> <span data-ttu-id="dac75-112">Например, если необходимо возвращать дополнительную информацию об узлах атрибутов, можно унаследовать класс <xref:System.Xml.XmlAttribute>.</span><span class="sxs-lookup"><span data-stu-id="dac75-112">For example, if you want to return additional information on attribute nodes, you can derive from the <xref:System.Xml.XmlAttribute> class.</span></span>

- <span data-ttu-id="dac75-113">За исключением методов создания узлов, при переопределении функции рекомендуется всегда вызывать базовую версию функции, а затем добавлять дополнительную обработку.</span><span class="sxs-lookup"><span data-stu-id="dac75-113">Except for the node creation methods, it is recommended that when overriding a function, you should always call the base version of the function and then add any additional processing.</span></span>

## <a name="creating-your-own-node-instances"></a><span data-ttu-id="dac75-114">Создание собственных экземпляров узлов</span><span class="sxs-lookup"><span data-stu-id="dac75-114">Creating Your Own Node Instances</span></span>

<span data-ttu-id="dac75-115">Класс <xref:System.Xml.XmlDocument> содержит методы создания узлов.</span><span class="sxs-lookup"><span data-stu-id="dac75-115">The <xref:System.Xml.XmlDocument> class contains node creation methods.</span></span> <span data-ttu-id="dac75-116">Эти методы вызываются для создания узлов при загрузке XML-файла.</span><span class="sxs-lookup"><span data-stu-id="dac75-116">When an XML file is loaded, these methods are called to create the nodes.</span></span> <span data-ttu-id="dac75-117">Эти методы можно переопределять, чтобы собственные экземпляры узлов создавались при загрузке документа.</span><span class="sxs-lookup"><span data-stu-id="dac75-117">You can override these methods so that your node instances are created when a document is loaded.</span></span> <span data-ttu-id="dac75-118">Например, при расширении класса <xref:System.Xml.XmlElement> был бы унаследован класс <xref:System.Xml.XmlDocument> и переопределен метод <xref:System.Xml.XmlDocument.CreateElement%2A>.</span><span class="sxs-lookup"><span data-stu-id="dac75-118">For example, if you have extended the <xref:System.Xml.XmlElement> class, you would inherit the <xref:System.Xml.XmlDocument> class and override the <xref:System.Xml.XmlDocument.CreateElement%2A> method.</span></span>

<span data-ttu-id="dac75-119">В следующем примере показано, как переопределить метод <xref:System.Xml.XmlDocument.CreateElement%2A>, чтобы возвратить собственную реализацию класса <xref:System.Xml.XmlElement>.</span><span class="sxs-lookup"><span data-stu-id="dac75-119">The following example shows how to override the <xref:System.Xml.XmlDocument.CreateElement%2A> method to return your implementation of the <xref:System.Xml.XmlElement> class.</span></span>

```vb
Class LineInfoDocument
    Inherits XmlDocument
        Public Overrides Function CreateElement(prefix As String, localname As String, nsURI As String) As XmlElement
        Dim elem As New LineInfoElement(prefix, localname, nsURI, Me)
        Return elem
    End Function 'CreateElement
End Class 'LineInfoDocument
```

```csharp
class LineInfoDocument : XmlDocument 
{
    public override XmlElement CreateElement(string prefix, string localname, string nsURI) 
    {
        LineInfoElement elem = new LineInfoElement(prefix, localname, nsURI, this);
        return elem;
    }
}
```

## <a name="extending-a-class"></a><span data-ttu-id="dac75-120">Расширение класса</span><span class="sxs-lookup"><span data-stu-id="dac75-120">Extending a Class</span></span>

<span data-ttu-id="dac75-121">Чтобы расширить класс, необходимо создать собственный класс на основе одного из существующих классов модели DOM.</span><span class="sxs-lookup"><span data-stu-id="dac75-121">To extend a class, derive your class from one of the existing DOM classes.</span></span> <span data-ttu-id="dac75-122">После этого можно будет переопределить любые виртуальные методы или свойства в базовом классе или добавить собственные.</span><span class="sxs-lookup"><span data-stu-id="dac75-122">You can then override any of the virtual methods or properties in the base class, or add your own.</span></span>

<span data-ttu-id="dac75-123">В следующем примере создается новый класс, который реализует класс <xref:System.Xml.XmlElement> и интерфейс <xref:System.Xml.IXmlLineInfo>.</span><span class="sxs-lookup"><span data-stu-id="dac75-123">In the following example, a new class is created, which implements the <xref:System.Xml.XmlElement> class and the <xref:System.Xml.IXmlLineInfo> interface.</span></span> <span data-ttu-id="dac75-124">Определяются дополнительные методы и свойства, позволяющие пользователям получать сведения о строке.</span><span class="sxs-lookup"><span data-stu-id="dac75-124">Additional methods and properties are defined which allows users to gather line information.</span></span>

```vb
Class LineInfoElement
   Inherits XmlElement
   Implements IXmlLineInfo
   Private lineNumber As Integer = 0
   Private linePosition As Integer = 0

   Friend Sub New(prefix As String, localname As String, nsURI As String, doc As XmlDocument)
      MyBase.New(prefix, localname, nsURI, doc)
      CType(doc, LineInfoDocument).IncrementElementCount()
   End Sub

   Public Sub SetLineInfo(linenum As Integer, linepos As Integer)
      lineNumber = linenum
      linePosition = linepos
   End Sub

   Public ReadOnly Property LineNumber() As Integer
      Get
         Return lineNumber
      End Get
   End Property

   Public ReadOnly Property LinePosition() As Integer
      Get
         Return linePosition
      End Get
   End Property

   Public Function HasLineInfo() As Boolean
      Return True
   End Function
End Class ' End LineInfoElement class.
```

```csharp
class LineInfoElement : XmlElement, IXmlLineInfo {
   int lineNumber = 0;
   int linePosition = 0;
   internal LineInfoElement( string prefix, string localname, string nsURI, XmlDocument doc ) : base( prefix, localname, nsURI, doc ) {
       ( (LineInfoDocument)doc ).IncrementElementCount();
  }
  public void SetLineInfo( int linenum, int linepos ) {
      lineNumber = linenum;
      linePosition = linepos;
  }
  public int LineNumber {
     get {
       return lineNumber;
     }
  }
  public int LinePosition {
      get {
        return linePosition;
      }
  }
  public bool HasLineInfo() {
    return true;
  }
} // End LineInfoElement class.
```

### <a name="example"></a><span data-ttu-id="dac75-125">Пример</span><span class="sxs-lookup"><span data-stu-id="dac75-125">Example</span></span>

<span data-ttu-id="dac75-126">Следующий пример считает количество элементов в XML-документе:</span><span class="sxs-lookup"><span data-stu-id="dac75-126">The following example counts the number of elements in an XML document:</span></span>

```vb
Imports System.Xml
Imports System.IO

Class LineInfoDocument
   Inherits XmlDocument

   Private elementCount As Integer

   Friend Sub New()
      elementCount = 0
   End Sub

   Public Overrides Function CreateElement(prefix As String, localname As String, nsURI As String) As XmlElement
      Dim elem As New LineInfoElement(prefix, localname, nsURI, Me)
      Return elem
   End Function

   Public Sub IncrementElementCount()
      elementCount += 1
   End Sub

   Public Function GetCount() As Integer
      Return elementCount
   End Function
End Class 'End LineInfoDocument class.

Class LineInfoElement
   Inherits XmlElement

   Friend Sub New(prefix As String, localname As String, nsURI As String, doc As XmlDocument)
      MyBase.New(prefix, localname, nsURI, doc)
      CType(doc, LineInfoDocument).IncrementElementCount()
   End Sub 'New
End Class 'LineInfoElement
 _ 'End LineInfoElement class.

Public Class Test

   Private filename As [String] = "book.xml"

   Public Shared Sub Main()

      Dim doc As New LineInfoDocument()
      doc.Load(filename)
      Console.WriteLine("Number of elements in {0}: {1}", filename, doc.GetCount())
   End Sub
End Class
```

```csharp
using System;
using System.Xml;
using System.IO;

class LineInfoDocument : XmlDocument {

  int elementCount;
  internal LineInfoDocument():base() {
    elementCount = 0;
  }

  public override XmlElement CreateElement( string prefix, string localname, string nsURI) {
    LineInfoElement elem = new LineInfoElement(prefix, localname, nsURI, this );
    return elem;
  }

  public void IncrementElementCount() {
     elementCount++;
  }

  public int GetCount() {
     return elementCount;
  }
} // End LineInfoDocument class.

class LineInfoElement:XmlElement {

    internal LineInfoElement( string prefix, string localname, string nsURI, XmlDocument doc ):base( prefix,localname,nsURI, doc ){
      ((LineInfoDocument)doc).IncrementElementCount();
    }
} // End LineInfoElement class.

public class Test {

  const String filename = "book.xml";
  public static void Main() {

     LineInfoDocument doc =new LineInfoDocument();
     doc.Load(filename);
     Console.WriteLine("Number of elements in {0}: {1}", filename, doc.GetCount());

  }
}
```

#### <a name="input"></a><span data-ttu-id="dac75-127">Ввод</span><span class="sxs-lookup"><span data-stu-id="dac75-127">Input</span></span>

<span data-ttu-id="dac75-128">book.xml</span><span class="sxs-lookup"><span data-stu-id="dac75-128">book.xml</span></span>

```xml
<!--sample XML fragment-->
<book genre='novel' ISBN='1-861001-57-5' misc='sale-item'>
  <title>The Handmaid's Tale</title>
  <price>14.95</price>
</book>
```

#### <a name="output"></a><span data-ttu-id="dac75-129">Вывод</span><span class="sxs-lookup"><span data-stu-id="dac75-129">Output</span></span>

```console
Number of elements in book.xml: 3
```

## <a name="node-event-handler"></a><span data-ttu-id="dac75-130">Обработчик события узла</span><span class="sxs-lookup"><span data-stu-id="dac75-130">Node Event Handler</span></span>

<span data-ttu-id="dac75-131">Реализация модели DOM в платформе .NET Framework также имеет систему событий, которая позволяет принимать и обрабатывать события при изменении узлов в XML-документе.</span><span class="sxs-lookup"><span data-stu-id="dac75-131">The .NET Framework implementation of the DOM also includes an event system that enables you to receive and handle events when nodes in an XML document change.</span></span> <span data-ttu-id="dac75-132">При помощи классов <xref:System.Xml.XmlNodeChangedEventHandler> и <xref:System.Xml.XmlNodeChangedEventArgs> можно отслеживать события `NodeChanged`, `NodeChanging`, `NodeInserted`, `NodeInserting`, `NodeRemoved` и `NodeRemoving`.</span><span class="sxs-lookup"><span data-stu-id="dac75-132">Using the <xref:System.Xml.XmlNodeChangedEventHandler> and <xref:System.Xml.XmlNodeChangedEventArgs> classes, you can capture `NodeChanged`, `NodeChanging`, `NodeInserted`, `NodeInserting`, `NodeRemoved`, and `NodeRemoving` events.</span></span>

<span data-ttu-id="dac75-133">В производных классах процесс обработки событий протекает точно так же, как в исходных классах модели DOM.</span><span class="sxs-lookup"><span data-stu-id="dac75-133">The event-handling process works exactly the same in derived classes as it would in the original DOM classes.</span></span>

<span data-ttu-id="dac75-134">Дополнительные сведения об обработке событий узлов см. в руководствах по [событиям ](../../../../docs/standard/events/index.md) и <xref:System.Xml.XmlNodeChangedEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="dac75-134">For more information regarding node event handling, see [Events](../../../../docs/standard/events/index.md) and <xref:System.Xml.XmlNodeChangedEventHandler>.</span></span>

## <a name="default-attributes-and-the-createelement-method"></a><span data-ttu-id="dac75-135">Атрибуты по умолчанию и метод CreateElement</span><span class="sxs-lookup"><span data-stu-id="dac75-135">Default Attributes and the CreateElement Method</span></span>

<span data-ttu-id="dac75-136">При переопределении метода <xref:System.Xml.XmlDocument.CreateElement%2A> в производном классе, если во время изменения документа создаются новые элементы, атрибуты по умолчанию не добавляются.</span><span class="sxs-lookup"><span data-stu-id="dac75-136">If you are overriding the <xref:System.Xml.XmlDocument.CreateElement%2A> method in a derived class, default attributes are not added when you are creating new elements while editing the document.</span></span> <span data-ttu-id="dac75-137">Это верно только при выполнении изменений.</span><span class="sxs-lookup"><span data-stu-id="dac75-137">This is only an issue while editing.</span></span> <span data-ttu-id="dac75-138">Так как метод <xref:System.Xml.XmlDocument.CreateElement%2A> отвечает за добавление атрибутов по умолчанию в класс <xref:System.Xml.XmlDocument>, необходимо запрограммировать эту функциональность в методе <xref:System.Xml.XmlDocument.CreateElement%2A>.</span><span class="sxs-lookup"><span data-stu-id="dac75-138">Because the <xref:System.Xml.XmlDocument.CreateElement%2A> method is responsible for adding default attributes to an <xref:System.Xml.XmlDocument>, you must code this functionality in the <xref:System.Xml.XmlDocument.CreateElement%2A> method.</span></span> <span data-ttu-id="dac75-139">При загрузке объекта <xref:System.Xml.XmlDocument>, который содержит атрибуты по умолчанию, они будут обработаны правильно.</span><span class="sxs-lookup"><span data-stu-id="dac75-139">If you are loading an <xref:System.Xml.XmlDocument> that includes default attributes, they will be handled correctly.</span></span> <span data-ttu-id="dac75-140">См. дополнительные сведения по [созданию атрибутов для элементов в модели DOM](creating-new-attributes-for-elements-in-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="dac75-140">For more information on default attributes, see [Creating New Attributes for Elements in the DOM](creating-new-attributes-for-elements-in-the-dom.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dac75-141">См. также</span><span class="sxs-lookup"><span data-stu-id="dac75-141">See also</span></span>

- [<span data-ttu-id="dac75-142">Модель объектов документов XML (DOM)</span><span class="sxs-lookup"><span data-stu-id="dac75-142">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
