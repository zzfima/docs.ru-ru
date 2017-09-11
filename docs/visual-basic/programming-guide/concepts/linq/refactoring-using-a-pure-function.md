---
title: "Оптимизация кода с использованием чистой функции (Visual Basic) | Документы Microsoft"
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
ms.assetid: af0ea62f-4f57-4868-b624-a85524055935
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: cf797a3b2437a8191d3c5b9831ba51db687c4fd0
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017


---
# <a name="refactoring-using-a-pure-function-visual-basic"></a><span data-ttu-id="a1ea6-102">Оптимизация кода с использованием чистой функции (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a1ea6-102">Refactoring Using a Pure Function (Visual Basic)</span></span>
<span data-ttu-id="a1ea6-103">Следующий пример выполняет рефакторинг предыдущего примера [оптимизация кода с помощью метода расширения (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/refactoring-using-an-extension-method.md), чтобы использовать чистую функцию в этом примере кода для поиска текста абзаца перемещается в чисто статический метод `ParagraphText`.</span><span class="sxs-lookup"><span data-stu-id="a1ea6-103">The following example refactors the previous example, [Refactoring Using an Extension Method (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/refactoring-using-an-extension-method.md), to use a pure function In this example, the code to find the text of a paragraph is moved to the pure static method `ParagraphText`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1ea6-104">Пример</span><span class="sxs-lookup"><span data-stu-id="a1ea6-104">Example</span></span>  
 <span data-ttu-id="a1ea6-105">В данном примере обрабатывается документ WordprocessingML, из которого извлекаются узлы абзацев.</span><span class="sxs-lookup"><span data-stu-id="a1ea6-105">This example processes a WordprocessingML document, retrieving the paragraph nodes from a WordprocessingML document.</span></span> <span data-ttu-id="a1ea6-106">Также идентифицируется стиль каждого абзаца.</span><span class="sxs-lookup"><span data-stu-id="a1ea6-106">It also identifies the style of each paragraph.</span></span> <span data-ttu-id="a1ea6-107">Этот пример основан на предыдущих примерах данного учебника.</span><span class="sxs-lookup"><span data-stu-id="a1ea6-107">This example builds on the previous examples in this tutorial.</span></span> <span data-ttu-id="a1ea6-108">Оптимизированный код поясняется в комментариях кода ниже.</span><span class="sxs-lookup"><span data-stu-id="a1ea6-108">The refactored code is called out in comments in the code below.</span></span>  
  
 <span data-ttu-id="a1ea6-109">Инструкции по созданию исходного документа для данного примера см. в разделе [создания источника Office Open XML-документа (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="a1ea6-109">For instructions for creating the source document for this example, see [Creating the Source Office Open XML Document (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span></span>  
  
 <span data-ttu-id="a1ea6-110">В этом примере используются классы из сборки WindowsBase.</span><span class="sxs-lookup"><span data-stu-id="a1ea6-110">This example uses classes from the WindowsBase assembly.</span></span> <span data-ttu-id="a1ea6-111">Используются типы из <xref:System.IO.Packaging?displayProperty=fullName>имен.</xref:System.IO.Packaging?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a1ea6-111">It uses types in the <xref:System.IO.Packaging?displayProperty=fullName> namespace.</span></span>  
  
```vb  
Imports <xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main">  
Module Module1  
    <System.Runtime.CompilerServices.Extension()> _  
    Public Function StringConcatenate(ByVal source As IEnumerable(Of String)) As String  
        Dim sb = New StringBuilder()  
        For Each s In source  
            sb.Append(s)  
        Next  
        Return sb.ToString()  
    End Function  
  
    <System.Runtime.CompilerServices.Extension()> _  
    Public Function StringConcatenate(Of T)(ByVal source As IEnumerable(Of T), _  
    ByVal func As Func(Of T, String)) As String  
        Dim sb = New StringBuilder()  
        For Each item As T In source  
            sb.Append(func(item))  
        Next  
        Return sb.ToString()  
    End Function  
  
    <System.Runtime.CompilerServices.Extension()> _  
    Public Function StringConcatenate(Of T)(ByVal source As IEnumerable(Of T), _  
    ByVal separator As String) As String  
        Dim sb = New StringBuilder()  
        For Each s As T In source  
            sb.Append(s).Append(separator)  
        Next  
        Return sb.ToString()  
    End Function  
  
    <System.Runtime.CompilerServices.Extension()> _  
    Public Function StringConcatenate(Of T)(ByVal source As IEnumerable(Of T), _  
    ByVal func As Func(Of T, String), ByVal separator As String) As String  
        Dim sb = New StringBuilder()  
        For Each item As T In source  
            sb.Append(func(item)).Append(separator)  
        Next  
        Return sb.ToString()  
    End Function  
  
    ' This is a new method that assembles the paragraph text.  
    Public Function ParagraphText(ByVal e As XElement) As String  
        Dim w = e.Name.Namespace  
        Return (e.<w:r>.<w:t>).StringConcatenate(Function(element) CStr(element))  
    End Function  
  
    ' Following function is required because VB does not support short circuit evaluation  
    Private Function GetStyleOfParagraph(ByVal styleNode As XElement, _  
                                         ByVal defaultStyle As String) As String  
        If styleNode Is Nothing Then  
            Return defaultStyle  
        Else  
            Return styleNode.@w:val  
        End If  
    End Function  
  
    Sub Main()  
        Dim fileName = "SampleDoc.docx"  
  
        Dim documentRelationshipType = _  
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument"  
        Dim stylesRelationshipType = _  
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles"  
        Dim wordmlNamespace = _  
          "http://schemas.openxmlformats.org/wordprocessingml/2006/main"  
        Dim xDoc As XDocument = Nothing  
        Dim styleDoc As XDocument = Nothing  
  
        Using wdPackage As Package = Package.Open(fileName, FileMode.Open, FileAccess.Read)  
            Dim docPackageRelationship As PackageRelationship = _  
              wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault()  
            If (docPackageRelationship IsNot Nothing) Then  
                Dim documentUri As Uri = PackUriHelper.ResolvePartUri(New Uri("/", UriKind.Relative), _  
                  docPackageRelationship.TargetUri)  
                Dim documentPart As PackagePart = wdPackage.GetPart(documentUri)  
  
                '  Load the document XML in the part into an XDocument instance.  
                xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()))  
  
                '  Find the styles part. There will only be one.  
                Dim styleRelation As PackageRelationship = _  
                  documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault()  
                If styleRelation IsNot Nothing Then  
                    Dim styleUri As Uri = _  
                      PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri)  
                    Dim stylePart As PackagePart = wdPackage.GetPart(styleUri)  
  
                    '  Load the style XML in the part into an XDocument instance.  
                    styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()))  
                End If  
            End If  
        End Using  
  
        Dim defaultStyle = _  
            ( _  
                From style In styleDoc.Root.<w:style> _  
                Where style.@w:type = "paragraph" And _  
                      style.@w:default = "1" _  
                Select style _  
            ).First().@w:styleId  
  
        ' Find all paragraphs in the document.  
        Dim paragraphs = _  
            From para In xDoc.Root.<w:body>...<w:p> _  
        Let styleNode = para.<w:pPr>.<w:pStyle>.FirstOrDefault _  
        Select New With { _  
            .ParagraphNode = para, _  
            .StyleName = GetStyleOfParagraph(styleNode, defaultStyle) _  
        }  
  
        ' Retrieve the text of each paragraph.  
        Dim paraWithText = _  
            From para In paragraphs _  
            Select New With { _  
                .ParagraphNode = para.ParagraphNode, _  
                .StyleName = para.StyleName, _  
                .Text = ParagraphText(para.ParagraphNode) _  
            }  
  
        For Each p In paraWithText  
            Console.WriteLine("StyleName:{0} >{1}<", p.StyleName, p.Text)  
        Next  
    End Sub  
End Module   
```  
  
 <span data-ttu-id="a1ea6-112">В этом примере выводятся те же результаты, что и после оптимизации кода:</span><span class="sxs-lookup"><span data-stu-id="a1ea6-112">This example produces the same output as before the refactoring:</span></span>  
  
```  
StyleName:Heading1 >Parsing WordprocessingML with LINQ to XML<  
StyleName:Normal ><  
StyleName:Normal >The following example prints to the console.<  
StyleName:Normal ><  
StyleName:Code >Imports System<  
StyleName:Code ><  
StyleName:Code >Class Program<  
StyleName:Code >    Public Shared  Sub Main(ByVal args() As String)<  
StyleName:Code >        Console.WriteLine("Hello World")<  
StyleName:Code >   End Sub<  
StyleName:Code >End Class<  
StyleName:Normal ><  
StyleName:Normal >This example produces the following output:<  
StyleName:Normal ><  
StyleName:Code >Hello World<  
```  
  
### <a name="next-steps"></a><span data-ttu-id="a1ea6-113">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="a1ea6-113">Next Steps</span></span>  
 <span data-ttu-id="a1ea6-114">В следующем примере показано, как выполнить проекцию XML в другую форму:</span><span class="sxs-lookup"><span data-stu-id="a1ea6-114">The next example shows how to project XML into a different shape:</span></span>  
  
-   [<span data-ttu-id="a1ea6-115">Проецирование XML в другую форму (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a1ea6-115">Projecting XML in a Different Shape (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projecting-xml-in-a-different-shape.md)  
  
## <a name="see-also"></a><span data-ttu-id="a1ea6-116">См. также</span><span class="sxs-lookup"><span data-stu-id="a1ea6-116">See Also</span></span>  
 <span data-ttu-id="a1ea6-117">[Учебное руководство: Управление содержимым в документе WordprocessingML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) </span><span class="sxs-lookup"><span data-stu-id="a1ea6-117">[Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) </span></span>  
<span data-ttu-id="a1ea6-118"> [Оптимизация кода с помощью метода расширения (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/refactoring-using-an-extension-method.md) </span><span class="sxs-lookup"><span data-stu-id="a1ea6-118"> [Refactoring Using an Extension Method (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/refactoring-using-an-extension-method.md) </span></span>  
<span data-ttu-id="a1ea6-119"> [Рефакторинг в чистые функции (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/refactoring-into-pure-functions.md)</span><span class="sxs-lookup"><span data-stu-id="a1ea6-119"> [Refactoring Into Pure Functions (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/refactoring-into-pure-functions.md)</span></span>
