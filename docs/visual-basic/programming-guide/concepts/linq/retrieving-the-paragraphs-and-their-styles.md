---
title: "Извлечение абзацев и стилей (Visual Basic) | Документы Microsoft"
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
ms.assetid: d9ed2238-d38e-4ad4-b88b-db7859df9bde
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d21ea826c8263ff391d4174ad1a7ebb173bb54d9
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017


---
# <a name="retrieving-the-paragraphs-and-their-styles-visual-basic"></a><span data-ttu-id="dd6c5-102">Извлечение абзацев и стилей (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd6c5-102">Retrieving the Paragraphs and Their Styles (Visual Basic)</span></span>
<span data-ttu-id="dd6c5-103">В этом примере составляется запрос, при котором получаются узлы абзацев из документа WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="dd6c5-103">In this example, we write a query that retrieves the paragraph nodes from a WordprocessingML document.</span></span> <span data-ttu-id="dd6c5-104">Также идентифицируется стиль каждого абзаца.</span><span class="sxs-lookup"><span data-stu-id="dd6c5-104">It also identifies the style of each paragraph.</span></span>  
  
 <span data-ttu-id="dd6c5-105">Этот запрос строится на основе запроса в предыдущем примере [поиск стиля абзаца по умолчанию (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/finding-the-default-paragraph-style.md), который получает стиль по умолчанию из списка стилей.</span><span class="sxs-lookup"><span data-stu-id="dd6c5-105">This query builds on the query in the previous example, [Finding the Default Paragraph Style (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/finding-the-default-paragraph-style.md), which retrieves the default style from the list of styles.</span></span> <span data-ttu-id="dd6c5-106">Эти сведения требуются для того, чтобы запрос мог идентифицировать стиль абзацев, для которых явно не установлен стиль.</span><span class="sxs-lookup"><span data-stu-id="dd6c5-106">This information is required so that the query can identify the style of paragraphs that do not have a style explicitly set.</span></span> <span data-ttu-id="dd6c5-107">Стили абзацев устанавливаются при помощи элемента `w:pPr`. Если абзац не содержит этот элемент, выполняется форматирование стилем по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dd6c5-107">Paragraph styles are set through the `w:pPr` element; if a paragraph does not contain this element, it is formatted with the default style.</span></span>  
  
 <span data-ttu-id="dd6c5-108">В этом разделе объясняется значение некоторых фрагментов запроса, после чего запрос показывается в составе целостного рабочего примера.</span><span class="sxs-lookup"><span data-stu-id="dd6c5-108">This topic explains the significance of some pieces of the query, then shows the query as part of a complete, working example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd6c5-109">Пример</span><span class="sxs-lookup"><span data-stu-id="dd6c5-109">Example</span></span>  
 <span data-ttu-id="dd6c5-110">Источник этого запроса по получению всех абзацев документа и их стилей таков:</span><span class="sxs-lookup"><span data-stu-id="dd6c5-110">The source of the query to retrieve all the paragraphs in a document and their styles is as follows:</span></span>  
  
```vb  
xDoc.Root.<w:body>...<w:p>  
```  
  
 <span data-ttu-id="dd6c5-111">Это выражение напоминает источник запроса в предыдущем примере [поиск стиля абзаца по умолчанию (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/finding-the-default-paragraph-style.md).</span><span class="sxs-lookup"><span data-stu-id="dd6c5-111">This expression is similar to the source of the query in the previous example, [Finding the Default Paragraph Style (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/finding-the-default-paragraph-style.md).</span></span> <span data-ttu-id="dd6c5-112">Основное различие заключается в том, что он использует <xref:System.Xml.Linq.XContainer.Descendants%2A>оси вместо <xref:System.Xml.Linq.XContainer.Elements%2A>оси.</xref:System.Xml.Linq.XContainer.Elements%2A> </xref:System.Xml.Linq.XContainer.Descendants%2A></span><span class="sxs-lookup"><span data-stu-id="dd6c5-112">The main difference is that it uses the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis instead of the <xref:System.Xml.Linq.XContainer.Elements%2A> axis.</span></span> <span data-ttu-id="dd6c5-113">Запрос использует <xref:System.Xml.Linq.XContainer.Descendants%2A>оси так, как в документах, имеются разделы, абзацы не будут прямыми потомками элемента текста; вместо этого будут находиться на два уровня вниз по иерархии.</xref:System.Xml.Linq.XContainer.Descendants%2A></span><span class="sxs-lookup"><span data-stu-id="dd6c5-113">The query uses the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis because in documents that have sections, the paragraphs will not be the direct children of the body element; rather, the paragraphs will be two levels down in the hierarchy.</span></span> <span data-ttu-id="dd6c5-114">С помощью <xref:System.Xml.Linq.XContainer.Descendants%2A>оси, этот код будет работать вне зависимости от того, является ли используются разделы.</xref:System.Xml.Linq.XContainer.Descendants%2A></span><span class="sxs-lookup"><span data-stu-id="dd6c5-114">By using the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis, the code will work of whether or not the document uses sections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd6c5-115">Пример</span><span class="sxs-lookup"><span data-stu-id="dd6c5-115">Example</span></span>  
 <span data-ttu-id="dd6c5-116">В этом разделе используется предложение `Let`, чтобы определить элемент, содержащий узел стиля.</span><span class="sxs-lookup"><span data-stu-id="dd6c5-116">The query uses a `Let` clause to determine the element that contains the style node.</span></span> <span data-ttu-id="dd6c5-117">Если элемент не найден, то `styleNode` устанавливается в значение `Nothing`:</span><span class="sxs-lookup"><span data-stu-id="dd6c5-117">If there is no element, then `styleNode` is set to `Nothing`:</span></span>  
  
```vb  
Let styleNode As XElement = para.<w:pPr>.<w:pStyle>.FirstOrDefault()  
```  
  
 <span data-ttu-id="dd6c5-118">`Let` Сначала использует предложение <xref:System.Xml.Linq.XContainer.Elements%2A>оси, чтобы найти все элементы с именем `pPr`, затем использует <xref:System.Xml.Linq.Extensions.Elements%2A>метод расширения, чтобы найти все дочерние элементы с именем `pStyle`и затем использует <xref:System.Linq.Enumerable.FirstOrDefault%2A>стандартного оператора запроса для преобразования коллекции в одноэлементный.</xref:System.Linq.Enumerable.FirstOrDefault%2A> </xref:System.Xml.Linq.Extensions.Elements%2A> </xref:System.Xml.Linq.XContainer.Elements%2A></span><span class="sxs-lookup"><span data-stu-id="dd6c5-118">The `Let` clause first uses the <xref:System.Xml.Linq.XContainer.Elements%2A> axis to find all elements named `pPr`, then uses the <xref:System.Xml.Linq.Extensions.Elements%2A> extension method to find all child elements named `pStyle`, and finally uses the <xref:System.Linq.Enumerable.FirstOrDefault%2A> standard query operator to convert the collection to a singleton.</span></span> <span data-ttu-id="dd6c5-119">Если коллекция пуста, `styleNode` устанавливается в значение `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="dd6c5-119">If the collection is empty, `styleNode` is set to `Nothing`.</span></span> <span data-ttu-id="dd6c5-120">Это выражение полезно для поиска потомков узла `pStyle`.</span><span class="sxs-lookup"><span data-stu-id="dd6c5-120">This is a useful idiom to look for the `pStyle` descendant node.</span></span> <span data-ttu-id="dd6c5-121">Обратите внимание, что, если дочерний узел `pPr` не существует, код продолжает работать, а не выводит исключение. Вместо этого узел `styleNode` устанавливается в значение `Nothing`, что именно и требуется для предложения `Let`.</span><span class="sxs-lookup"><span data-stu-id="dd6c5-121">Note that if the `pPr` child node does not exist, the code does nor fail by throwing an exception; instead, `styleNode` is set to `Nothing`, which is the desired behavior of this `Let` clause.</span></span>  
  
 <span data-ttu-id="dd6c5-122">В этом запросе выполняется проецирование коллекции анонимного типа с двумя членами, `StyleName` и `ParagraphNode`.</span><span class="sxs-lookup"><span data-stu-id="dd6c5-122">The query projects a collection of an anonymous type with two members, `StyleName` and `ParagraphNode`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd6c5-123">Пример</span><span class="sxs-lookup"><span data-stu-id="dd6c5-123">Example</span></span>  
 <span data-ttu-id="dd6c5-124">В данном примере обрабатывается документ WordprocessingML, из которого извлекаются узлы абзацев.</span><span class="sxs-lookup"><span data-stu-id="dd6c5-124">This example processes a WordprocessingML document, retrieving the paragraph nodes from a WordprocessingML document.</span></span> <span data-ttu-id="dd6c5-125">Также идентифицируется стиль каждого абзаца.</span><span class="sxs-lookup"><span data-stu-id="dd6c5-125">It also identifies the style of each paragraph.</span></span> <span data-ttu-id="dd6c5-126">Этот пример основан на предыдущих примерах данного учебника.</span><span class="sxs-lookup"><span data-stu-id="dd6c5-126">This example builds on the previous examples in this tutorial.</span></span> <span data-ttu-id="dd6c5-127">Новый запрос выявляется в комментариях в нижеприведенном коде.</span><span class="sxs-lookup"><span data-stu-id="dd6c5-127">The new query is called out in comments in the code below.</span></span>  
  
 <span data-ttu-id="dd6c5-128">Можно найти инструкции по созданию исходного документа для данного примера в [создания источника Office Open XML-документа (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="dd6c5-128">You can find instructions for creating the source document for this example in [Creating the Source Office Open XML Document (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span></span>  
  
 <span data-ttu-id="dd6c5-129">В этом примере используются классы, находящиеся в сборке WindowsBase.</span><span class="sxs-lookup"><span data-stu-id="dd6c5-129">This example uses classes found in the WindowsBase assembly.</span></span> <span data-ttu-id="dd6c5-130">Используются типы из <xref:System.IO.Packaging?displayProperty=fullName>имен.</xref:System.IO.Packaging?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="dd6c5-130">It uses types in the <xref:System.IO.Packaging?displayProperty=fullName> namespace.</span></span>  
  
```vb  
Imports <xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main">  
  
Module Module1  
    Private Function GetStyleOfParagraph(ByVal styleNode As XElement, ByVal defaultStyle As String) As String  
        If (styleNode Is Nothing) Then  
            Return defaultStyle  
        Else  
            Return styleNode.@w:val  
        End If  
    End Function  
  
    Sub Main()  
        Dim fileName = "SampleDoc.docx"  
  
        Dim documentRelationshipType = "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument"  
        Dim stylesRelationshipType = "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles"  
        Dim wordmlNamespace = "http://schemas.openxmlformats.org/wordprocessingml/2006/main"  
  
        Dim xDoc As XDocument = Nothing  
        Dim styleDoc As XDocument = Nothing  
        Using wdPackage As Package = Package.Open(fileName, FileMode.Open, FileAccess.Read)  
            Dim docPackageRelationship As PackageRelationship = wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault()  
            If (docPackageRelationship IsNot Nothing) Then  
                Dim documentUri As Uri = PackUriHelper.ResolvePartUri(New Uri("/", UriKind.Relative), docPackageRelationship.TargetUri)  
                Dim documentPart As PackagePart = wdPackage.GetPart(documentUri)  
  
                '  Load the document XML in the part into an XDocument instance.  
                xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()))  
  
                '  Find the styles part. There will only be one.  
                Dim styleRelation As PackageRelationship = documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault()  
                If (styleRelation IsNot Nothing) Then  
                    Dim styleUri As Uri = PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri)  
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
  
        ' Following is the new query that finds all paragraphs in the  
        ' document and their styles.  
        Dim paragraphs = _  
            From para In xDoc.Root.<w:body>...<w:p> _  
        Let styleNode As XElement = para.<w:pPr>.<w:pStyle>.FirstOrDefault() _  
        Select New With { _  
            .ParagraphNode = para, _  
            .StyleName = GetStyleOfParagraph(styleNode, defaultStyle) _  
        }  
  
        For Each p In paragraphs  
            Console.WriteLine("StyleName:{0}", p.StyleName)  
        Next  
  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="dd6c5-131">В этом примере выводятся следующие выходные данные при применении к документу, описанному в [создания источника Office Open XML-документа (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="dd6c5-131">This example produces the following output when applied to the document described in [Creating the Source Office Open XML Document (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span></span>  
  
```  
StyleName:Heading1  
StyleName:Normal  
StyleName:Normal  
StyleName:Normal  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Normal  
StyleName:Normal  
StyleName:Normal  
StyleName:Code  
```  
  
## <a name="next-steps"></a><span data-ttu-id="dd6c5-132">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="dd6c5-132">Next Steps</span></span>  
 <span data-ttu-id="dd6c5-133">В следующем разделе [извлечение текста абзацев (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/retrieving-the-text-of-the-paragraphs.md), вы создадите запрос на извлечение текста абзацев.</span><span class="sxs-lookup"><span data-stu-id="dd6c5-133">In the next topic, [Retrieving the Text of the Paragraphs (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/retrieving-the-text-of-the-paragraphs.md), you'll create a query to retrieve the text of paragraphs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd6c5-134">См. также</span><span class="sxs-lookup"><span data-stu-id="dd6c5-134">See Also</span></span>  
 [<span data-ttu-id="dd6c5-135">Учебное руководство: Управление содержимым в документе WordprocessingML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd6c5-135">Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
