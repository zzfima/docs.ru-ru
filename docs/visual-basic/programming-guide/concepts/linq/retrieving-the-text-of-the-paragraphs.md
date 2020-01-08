---
title: Извлечение текста абзацев
ms.date: 07/20/2015
ms.assetid: 095fa0d9-7b1b-4cbb-9c13-e2c9d8923d31
ms.openlocfilehash: 0f53eec44e0b11a6c23c7afb4892e4d5d876d6d6
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75341591"
---
# <a name="retrieving-the-text-of-the-paragraphs-visual-basic"></a><span data-ttu-id="7ff44-102">Получение текста абзацев (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7ff44-102">Retrieving the Text of the Paragraphs (Visual Basic)</span></span>
<span data-ttu-id="7ff44-103">Этот пример строится на предыдущем примере, [получая абзацы и их стили (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/retrieving-the-paragraphs-and-their-styles.md).</span><span class="sxs-lookup"><span data-stu-id="7ff44-103">This example builds on the previous example, [Retrieving the Paragraphs and Their Styles (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/retrieving-the-paragraphs-and-their-styles.md).</span></span> <span data-ttu-id="7ff44-104">В этом примере текст каждого абзаца получается в строку.</span><span class="sxs-lookup"><span data-stu-id="7ff44-104">This new example retrieves the text of each paragraph as a string.</span></span>  
  
 <span data-ttu-id="7ff44-105">Чтобы получить текст, в этом примере добавляется дополнительный запрос, который последовательно проходит по коллекции анонимных типов и проецирует новую коллекцию анонимного типа с добавлением нового члена, `Text`.</span><span class="sxs-lookup"><span data-stu-id="7ff44-105">To retrieve the text, this example adds an additional query that iterates through the collection of anonymous types and projects a new collection of an anonymous type with the addition of a new member, `Text`.</span></span> <span data-ttu-id="7ff44-106">Он использует стандартный оператор запроса <xref:System.Linq.Enumerable.Aggregate%2A>, чтобы объединить несколько строк в одну.</span><span class="sxs-lookup"><span data-stu-id="7ff44-106">It uses the <xref:System.Linq.Enumerable.Aggregate%2A> standard query operator to concatenate multiple strings into one string.</span></span>  
  
 <span data-ttu-id="7ff44-107">Этот способ (т. е. сначала проецирование в коллекцию анонимного типа, затем использование этой коллекции для проекции в новую коллекцию анонимного типа) широко распространен и полезен.</span><span class="sxs-lookup"><span data-stu-id="7ff44-107">This technique (that is, first projecting to a collection of an anonymous type, then using this collection to project to a new collection of an anonymous type) is a common and useful idiom.</span></span> <span data-ttu-id="7ff44-108">Этот запрос не удалось бы создать без создания проекции к первому анонимному типу.</span><span class="sxs-lookup"><span data-stu-id="7ff44-108">This query could have been written without projecting to the first anonymous type.</span></span> <span data-ttu-id="7ff44-109">Однако из-за применения неспешных вычислений это не требует много дополнительных вычислительных мощностей.</span><span class="sxs-lookup"><span data-stu-id="7ff44-109">However, because of lazy evaluation, doing so does not use much additional processing power.</span></span> <span data-ttu-id="7ff44-110">Происходит создание большего количества кратковременных объектов в куче, однако производительность при этом снижается незначительно.</span><span class="sxs-lookup"><span data-stu-id="7ff44-110">The idiom creates more short lived objects on the heap, but this does not substantially degrade performance.</span></span>  
  
 <span data-ttu-id="7ff44-111">Конечно, было бы возможным создать единичный запрос, который содержит функциональные возможности получать абзацы, стиль и текст каждого абзаца.</span><span class="sxs-lookup"><span data-stu-id="7ff44-111">Of course, it would be possible to write a single query that contains the functionality to retrieve the paragraphs, the style of each paragraph, and the text of each paragraph.</span></span> <span data-ttu-id="7ff44-112">Однако часто полезно разбить более сложный запрос на несколько запросов, поскольку при этом результирующий код выглядит более модульным и легким для поддержки.</span><span class="sxs-lookup"><span data-stu-id="7ff44-112">However, it often is useful to break up a more complicated query into multiple queries because the resulting code is more modular and easier to maintain.</span></span> <span data-ttu-id="7ff44-113">Более того, если потребуется повторно использовать часть запроса, будет легче выполнить оптимизацию кода.</span><span class="sxs-lookup"><span data-stu-id="7ff44-113">Furthermore, if you need to reuse a portion of the query, it is easier to refactor if the queries are written in this manner.</span></span>  
  
 <span data-ttu-id="7ff44-114">Эти запросы, Объединенные в цепочку, используют модель обработки, подробно рассмотренную в разделе [учебник. отложенное выполнение (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-deferred-execution.md).</span><span class="sxs-lookup"><span data-stu-id="7ff44-114">These queries, which are chained together, use the processing model that is examined in detail in the topic [Tutorial: Deferred Execution (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-deferred-execution.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ff44-115">Пример</span><span class="sxs-lookup"><span data-stu-id="7ff44-115">Example</span></span>  
 <span data-ttu-id="7ff44-116">В этом примере выполняется обработка документа WordprocessingML, определение узла элемента, имени стиля и текста каждого абзаца.</span><span class="sxs-lookup"><span data-stu-id="7ff44-116">This example processes a WordprocessingML document, determining the element node, the style name, and the text of each paragraph.</span></span> <span data-ttu-id="7ff44-117">Этот пример основан на предыдущих примерах данного учебника.</span><span class="sxs-lookup"><span data-stu-id="7ff44-117">This example builds on the previous examples in this tutorial.</span></span> <span data-ttu-id="7ff44-118">Новый запрос выявляется в комментариях в нижеприведенном коде.</span><span class="sxs-lookup"><span data-stu-id="7ff44-118">The new query is called out in comments in the code below.</span></span>  
  
 <span data-ttu-id="7ff44-119">Инструкции по созданию исходного документа для этого примера см. в разделе [Создание исходного документа Office Open XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="7ff44-119">For instructions for creating the source document for this example, see [Creating the Source Office Open XML Document (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span></span>  
  
 <span data-ttu-id="7ff44-120">В этом примере используются классы из сборки WindowsBase.</span><span class="sxs-lookup"><span data-stu-id="7ff44-120">This example uses classes from the WindowsBase assembly.</span></span> <span data-ttu-id="7ff44-121">Используются типы из пространства имен <xref:System.IO.Packaging?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7ff44-121">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
```vb  
Imports <xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main">  
  
Module Module1  
    ' Following function is required because Visual Basic does not support short circuit evaluation  
    Private Function GetStyleOfParagraph(ByVal styleNode As XElement, _  
                                         ByVal defaultStyle As String) As String  
        If (styleNode Is Nothing) Then  
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
                If (styleRelation IsNot Nothing) Then  
                    Dim styleUri As Uri = _  
                      PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri)  
                    Dim stylePart As PackagePart = wdPackage.GetPart(styleUri)  
  
                    '  Load the style XML in the part into an XDocument instance.  
                    styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()))  
                End If  
            End If  
        End Using  
  
        Dim defaultStyle As String = _  
            ( _  
                From style In styleDoc.Root.<w:style> _  
                Where style.@w:type = "paragraph" And _  
                      style.@w:default = "1" _  
                Select style _  
            ).First().@w:styleId  
  
        ' Find all paragraphs in the document.  
        Dim paragraphs = _  
            From para In xDoc.Root.<w:body>...<w:p> _  
        Let styleNode As XElement = para.<w:pPr>.<w:pStyle>.FirstOrDefault _  
        Select New With { _  
            .ParagraphNode = para, _  
            .StyleName = GetStyleOfParagraph(styleNode, defaultStyle) _  
        }  
  
        ' Following is the new query that retrieves the text of  
        ' each paragraph.  
        Dim paraWithText = _  
            From para In paragraphs _  
            Select New With { _  
                .ParagraphNode = para.ParagraphNode, _  
                .StyleName = para.StyleName, _  
                .Text = para.ParagraphNode.<w:r>.<w:t> _  
                    .Aggregate(New StringBuilder(), _  
                               Function(s As StringBuilder, i As String) s.Append(CStr(i)), _  
                               Function(s As StringBuilder) s.ToString) _  
            }  
  
        For Each p In paraWithText  
            Console.WriteLine("StyleName:{0} >{1}<", p.StyleName, p.Text)  
        Next  
  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="7ff44-122">В этом примере при применении к документу, описанному в разделе [Создание исходного документа Office Open XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md), выводится следующий результат.</span><span class="sxs-lookup"><span data-stu-id="7ff44-122">This example produces the following output when applied to the document described in [Creating the Source Office Open XML Document (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span></span>  
  
```console  
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
  
## <a name="next-steps"></a><span data-ttu-id="7ff44-123">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="7ff44-123">Next Steps</span></span>  
 <span data-ttu-id="7ff44-124">В следующем примере показано, как использовать метод расширений вместо <xref:System.Linq.Enumerable.Aggregate%2A>, чтобы объединить несколько строк в одну.</span><span class="sxs-lookup"><span data-stu-id="7ff44-124">The next example shows how to use an extension method, instead of <xref:System.Linq.Enumerable.Aggregate%2A>, to concatenate multiple strings into a single string.</span></span>  
  
- [<span data-ttu-id="7ff44-125">Рефакторинг с помощью метода расширения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7ff44-125">Refactoring Using an Extension Method (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/refactoring-using-an-extension-method.md)  
  
## <a name="see-also"></a><span data-ttu-id="7ff44-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="7ff44-126">See also</span></span>

- [<span data-ttu-id="7ff44-127">Руководство. Управление содержимым в документе WordprocessingML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7ff44-127">Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
- [<span data-ttu-id="7ff44-128">Отложенное выполнение и отложенное вычисление в LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7ff44-128">Deferred Execution and Lazy Evaluation in LINQ to XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
