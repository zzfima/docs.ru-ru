---
title: "Расширение модели DOM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: b5489c96-4afd-439a-a25d-fc82eb4a148d
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 06cac8d76b17f3ef32931ea21d0556085f05d7b1
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="extending-the-dom"></a><span data-ttu-id="f53a6-102">Расширение модели DOM</span><span class="sxs-lookup"><span data-stu-id="f53a6-102">Extending the DOM</span></span>
<span data-ttu-id="f53a6-103">Платформа Microsoft .NET Framework включает базовый набор классов, обеспечивающих реализацию модели DOM.</span><span class="sxs-lookup"><span data-stu-id="f53a6-103">The Microsoft .NET Framework includes a base set of classes that provides an implementation of the XML Document Object Model (DOM).</span></span> <span data-ttu-id="f53a6-104">Объект <xref:System.Xml.XmlNode> и его производные классы предоставляют методы и свойства, позволяющие переходить по содержимому и структуре XML-документа, запрашивать и изменять это содержимое и структуру.</span><span class="sxs-lookup"><span data-stu-id="f53a6-104">The <xref:System.Xml.XmlNode>, and its derived classes, provides methods and properties that allow you to navigate, query, and modify the content and structure of an XML document.</span></span>  
  
 <span data-ttu-id="f53a6-105">Если содержимое XML загружается в память с помощью модели DOM, созданные узлы содержат такие сведения, как имя узла, тип узла и так далее.</span><span class="sxs-lookup"><span data-stu-id="f53a6-105">When XML content is loaded into memory using the DOM, the nodes created contain information such as node name, node type, and so on.</span></span> <span data-ttu-id="f53a6-106">Могут быть случаи, когда необходимы конкретные данные об узле, которые не предоставляют базовые классы.</span><span class="sxs-lookup"><span data-stu-id="f53a6-106">There may be occasions where you require specific node information that the base classes do not provide.</span></span> <span data-ttu-id="f53a6-107">Например, может потребоваться узнать номер строки и позицию узла.</span><span class="sxs-lookup"><span data-stu-id="f53a6-107">For example, you may want to see the line number and position of the node.</span></span> <span data-ttu-id="f53a6-108">В этом случае можно произвести новые классы из существующих классов DOM, создав для них дополнительные возможности.</span><span class="sxs-lookup"><span data-stu-id="f53a6-108">In this case, you can derive new classes from the existing DOM classes and add additional functionality.</span></span>  
  
 <span data-ttu-id="f53a6-109">Есть две общие рекомендации для создания новых классов из существующих.</span><span class="sxs-lookup"><span data-stu-id="f53a6-109">There are two general guidelines when deriving new classes:</span></span>  
  
-   <span data-ttu-id="f53a6-110">Рекомендуется никогда не создавать производных классов от класса <xref:System.Xml.XmlNode>.</span><span class="sxs-lookup"><span data-stu-id="f53a6-110">It is recommended that you never derive from the <xref:System.Xml.XmlNode> class.</span></span> <span data-ttu-id="f53a6-111">Вместо этого рекомендуется наследовать классы от класса, соответствующего типу интересующего вас узла.</span><span class="sxs-lookup"><span data-stu-id="f53a6-111">Instead, it is recommended that you derive classes from the class corresponding to the node type that you are interested in.</span></span> <span data-ttu-id="f53a6-112">Например, если необходимо возвращать дополнительную информацию об узлах атрибутов, можно унаследовать класс <xref:System.Xml.XmlAttribute>.</span><span class="sxs-lookup"><span data-stu-id="f53a6-112">For example, if you want to return additional information on attribute nodes, you can derive from the <xref:System.Xml.XmlAttribute> class.</span></span>  
  
-   <span data-ttu-id="f53a6-113">За исключением методов создания узлов, при переопределении функции рекомендуется всегда вызывать базовую версию функции, а затем добавлять дополнительную обработку.</span><span class="sxs-lookup"><span data-stu-id="f53a6-113">Except for the node creation methods, it is recommended that when overriding a function, you should always call the base version of the function and then add any additional processing.</span></span>  
  
## <a name="creating-your-own-node-instances"></a><span data-ttu-id="f53a6-114">Создание собственных экземпляров узлов</span><span class="sxs-lookup"><span data-stu-id="f53a6-114">Creating Your Own Node Instances</span></span>  
 <span data-ttu-id="f53a6-115">Класс <xref:System.Xml.XmlDocument> содержит методы создания узлов.</span><span class="sxs-lookup"><span data-stu-id="f53a6-115">The <xref:System.Xml.XmlDocument> class contains node creation methods.</span></span> <span data-ttu-id="f53a6-116">Эти методы вызываются для создания узлов при загрузке XML-файла.</span><span class="sxs-lookup"><span data-stu-id="f53a6-116">When an XML file is loaded, these methods are called to create the nodes.</span></span> <span data-ttu-id="f53a6-117">Эти методы можно переопределять, чтобы собственные экземпляры узлов создавались при загрузке документа.</span><span class="sxs-lookup"><span data-stu-id="f53a6-117">You can override these methods so that your node instances are created when a document is loaded.</span></span> <span data-ttu-id="f53a6-118">Например, при расширении класса <xref:System.Xml.XmlElement> был бы унаследован класс <xref:System.Xml.XmlDocument> и переопределен метод <xref:System.Xml.XmlDocument.CreateElement%2A>.</span><span class="sxs-lookup"><span data-stu-id="f53a6-118">For example, if you have extended the <xref:System.Xml.XmlElement> class, you would inherit the <xref:System.Xml.XmlDocument> class and override the <xref:System.Xml.XmlDocument.CreateElement%2A> method.</span></span>  
  
 <span data-ttu-id="f53a6-119">В следующем примере показано, как переопределить метод <xref:System.Xml.XmlDocument.CreateElement%2A>, чтобы возвратить собственную реализацию класса <xref:System.Xml.XmlElement>.</span><span class="sxs-lookup"><span data-stu-id="f53a6-119">The following example shows how to override the <xref:System.Xml.XmlDocument.CreateElement%2A> method to return your implementation of the <xref:System.Xml.XmlElement> class.</span></span>  
  
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
class LineInfoDocument : XmlDocument {  
  public override XmlElement CreateElement(string prefix, string localname, string nsURI) {  
  LineInfoElement elem = new LineInfoElement(prefix, localname, nsURI, this);  
  return elem;  
  }  
```  
  
## <a name="extending-a-class"></a><span data-ttu-id="f53a6-120">Расширение класса</span><span class="sxs-lookup"><span data-stu-id="f53a6-120">Extending a Class</span></span>  
 <span data-ttu-id="f53a6-121">Чтобы расширить класс, необходимо создать собственный класс на основе одного из существующих классов модели DOM.</span><span class="sxs-lookup"><span data-stu-id="f53a6-121">To extend a class, derive your class from one of the existing DOM classes.</span></span> <span data-ttu-id="f53a6-122">После этого можно будет переопределить любые виртуальные методы или свойства в базовом классе или добавить собственные.</span><span class="sxs-lookup"><span data-stu-id="f53a6-122">You can then override any of the virtual methods or properties in the base class, or add your own.</span></span>  
  
 <span data-ttu-id="f53a6-123">В следующем примере создается новый класс, который реализует класс <xref:System.Xml.XmlElement> и интерфейс <xref:System.Xml.IXmlLineInfo>.</span><span class="sxs-lookup"><span data-stu-id="f53a6-123">In the following example, a new class is created, which implements the <xref:System.Xml.XmlElement> class and the <xref:System.Xml.IXmlLineInfo> interface.</span></span> <span data-ttu-id="f53a6-124">Определяются дополнительные методы и свойства, позволяющие пользователям получать сведения о строке.</span><span class="sxs-lookup"><span data-stu-id="f53a6-124">Additional methods and properties are defined which allows users to gather line information.</span></span>  
  
```vb  
Class LineInfoElement  
   Inherits XmlElement  
   Implements IXmlLineInfo  
   Private lineNumber As Integer = 0  
   Private linePosition As Integer = 0  
  
   Friend Sub New(prefix As String, localname As String, nsURI As String, doc As XmlDocument)  
      MyBase.New(prefix, localname, nsURI, doc)  
      CType(doc, LineInfoDocument).IncrementElementCount()  
   End Sub 'New  
  
   Public Sub SetLineInfo(linenum As Integer, linepos As Integer)  
      lineNumber = linenum  
      linePosition = linepos  
   End Sub 'SetLineInfo  
  
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
   End Function 'HasLineInfo  
End Class 'LineInfoElement ' End LineInfoElement class.  
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
  
### <a name="example"></a><span data-ttu-id="f53a6-125">Пример</span><span class="sxs-lookup"><span data-stu-id="f53a6-125">Example</span></span>  
 <span data-ttu-id="f53a6-126">Следующий пример считает количество элементов в XML-документе.</span><span class="sxs-lookup"><span data-stu-id="f53a6-126">The following example counts the number of elements in an XML document.</span></span>  
  
```vb  
Imports System  
Imports System.Xml  
Imports System.IO  
  
 _  
  
Class LineInfoDocument  
   Inherits XmlDocument  
  
   Private elementCount As Integer  
  
   Friend Sub New()  
      elementCount = 0  
   End Sub 'New  
  
   Public Overrides Function CreateElement(prefix As String, localname As String, nsURI As String) As XmlElement  
      Dim elem As New LineInfoElement(prefix, localname, nsURI, Me)  
      Return elem  
   End Function 'CreateElement  
  
   Public Sub IncrementElementCount()  
      elementCount += 1  
   End Sub 'IncrementElementCount  
  
   Public Function GetCount() As Integer  
      Return elementCount  
   End Function 'GetCount  
End Class 'LineInfoDocument  
 _ 'End LineInfoDocument class.  
  
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
   End Sub 'Main   
End Class 'Test  
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
  
##### <a name="input"></a><span data-ttu-id="f53a6-127">Входные данные</span><span class="sxs-lookup"><span data-stu-id="f53a6-127">Input</span></span>  
 <span data-ttu-id="f53a6-128">book.xml</span><span class="sxs-lookup"><span data-stu-id="f53a6-128">book.xml</span></span>  
  
```xml  
<!--sample XML fragment-->  
<book genre='novel' ISBN='1-861001-57-5' misc='sale-item'>  
  <title>The Handmaid's Tale</title>  
  <price>14.95</price>  
</book>  
```  
  
##### <a name="output"></a><span data-ttu-id="f53a6-129">Вывод</span><span class="sxs-lookup"><span data-stu-id="f53a6-129">Output</span></span>  
  
```  
Number of elements in book.xml: 3  
```  
  
 <span data-ttu-id="f53a6-130">Пример, показывающий, как расширять классы модели XML DOM (System.Xml), см. в www.gotdotnet.com/userfiles/XMLDom/extendDOM.zip.</span><span class="sxs-lookup"><span data-stu-id="f53a6-130">For an example showing how to extend the XML DOM classes (System.Xml), see www.gotdotnet.com/userfiles/XMLDom/extendDOM.zip.</span></span>  
  
## <a name="node-event-handler"></a><span data-ttu-id="f53a6-131">Обработчик события узла</span><span class="sxs-lookup"><span data-stu-id="f53a6-131">Node Event Handler</span></span>  
 <span data-ttu-id="f53a6-132">Реализация модели DOM в платформе .NET Framework также имеет систему событий, которая позволяет принимать и обрабатывать события при изменении узлов в XML-документе.</span><span class="sxs-lookup"><span data-stu-id="f53a6-132">The .NET Framework implementation of the DOM also includes an event system that enables you to receive and handle events when nodes in an XML document change.</span></span> <span data-ttu-id="f53a6-133">При помощи классов <xref:System.Xml.XmlNodeChangedEventHandler> и <xref:System.Xml.XmlNodeChangedEventArgs> можно отслеживать события `NodeChanged`, `NodeChanging`, `NodeInserted`, `NodeInserting`, `NodeRemoved` и `NodeRemoving`.</span><span class="sxs-lookup"><span data-stu-id="f53a6-133">Using the <xref:System.Xml.XmlNodeChangedEventHandler> and <xref:System.Xml.XmlNodeChangedEventArgs> classes, you can capture `NodeChanged`, `NodeChanging`, `NodeInserted`, `NodeInserting`, `NodeRemoved`, and `NodeRemoving` events.</span></span>  
  
 <span data-ttu-id="f53a6-134">В производных классах процесс обработки событий протекает точно так же, как в исходных классах модели DOM.</span><span class="sxs-lookup"><span data-stu-id="f53a6-134">The event-handling process works exactly the same in derived classes as it would in the original DOM classes.</span></span>  
  
 <span data-ttu-id="f53a6-135">Дополнительные сведения об обработке событий узлов см. в руководствах по [событиям ](../../../../docs/standard/events/index.md) и <xref:System.Xml.XmlNodeChangedEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="f53a6-135">For more information regarding node event handling, see [Events](../../../../docs/standard/events/index.md) and <xref:System.Xml.XmlNodeChangedEventHandler>.</span></span>  
  
## <a name="default-attributes-and-the-createelement-method"></a><span data-ttu-id="f53a6-136">Атрибуты по умолчанию и метод CreateElement</span><span class="sxs-lookup"><span data-stu-id="f53a6-136">Default Attributes and the CreateElement Method</span></span>  
 <span data-ttu-id="f53a6-137">При переопределении метода <xref:System.Xml.XmlDocument.CreateElement%2A> в производном классе, если во время изменения документа создаются новые элементы, атрибуты по умолчанию не добавляются.</span><span class="sxs-lookup"><span data-stu-id="f53a6-137">If you are overriding the <xref:System.Xml.XmlDocument.CreateElement%2A> method in a derived class, default attributes are not added when you are creating new elements while editing the document.</span></span> <span data-ttu-id="f53a6-138">Это верно только при выполнении изменений.</span><span class="sxs-lookup"><span data-stu-id="f53a6-138">This is only an issue while editing.</span></span> <span data-ttu-id="f53a6-139">Так как метод <xref:System.Xml.XmlDocument.CreateElement%2A> отвечает за добавление атрибутов по умолчанию в класс <xref:System.Xml.XmlDocument>, необходимо запрограммировать эту функциональность в методе <xref:System.Xml.XmlDocument.CreateElement%2A>.</span><span class="sxs-lookup"><span data-stu-id="f53a6-139">Because the <xref:System.Xml.XmlDocument.CreateElement%2A> method is responsible for adding default attributes to an <xref:System.Xml.XmlDocument>, you must code this functionality in the <xref:System.Xml.XmlDocument.CreateElement%2A> method.</span></span> <span data-ttu-id="f53a6-140">При загрузке объекта <xref:System.Xml.XmlDocument>, который содержит атрибуты по умолчанию, они будут обработаны правильно.</span><span class="sxs-lookup"><span data-stu-id="f53a6-140">If you are loading an <xref:System.Xml.XmlDocument> that includes default attributes, they will be handled correctly.</span></span> <span data-ttu-id="f53a6-141">См. дополнительные сведения по [созданию атрибутов для элементов в модели DOM](../../../../docs/standard/data/xml/creating-new-attributes-for-elements-in-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="f53a6-141">For more information on default attributes, see [Creating New Attributes for Elements in the DOM](../../../../docs/standard/data/xml/creating-new-attributes-for-elements-in-the-dom.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f53a6-142">См. также</span><span class="sxs-lookup"><span data-stu-id="f53a6-142">See Also</span></span>  
 [<span data-ttu-id="f53a6-143">Модель объектов документов XML (DOM)</span><span class="sxs-lookup"><span data-stu-id="f53a6-143">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
