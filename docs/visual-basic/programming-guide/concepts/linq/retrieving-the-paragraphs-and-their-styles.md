---
title: Извлечение абзацев и стилей (Visual Basic)
ms.date: 07/20/2015
ms.assetid: d9ed2238-d38e-4ad4-b88b-db7859df9bde
ms.openlocfilehash: a726c3b609d778d8d91be61091a3627ec1358dfc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54716030"
---
# <a name="retrieving-the-paragraphs-and-their-styles-visual-basic"></a>Извлечение абзацев и стилей (Visual Basic)
В этом примере составляется запрос, при котором получаются узлы абзацев из документа WordprocessingML. Также идентифицируется стиль каждого абзаца.  
  
 Этот запрос основан на запросе из предыдущего примера, [поиск стиля абзаца по умолчанию (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/finding-the-default-paragraph-style.md), который получает стиль по умолчанию из списка стилей. Эти сведения требуются для того, чтобы запрос мог идентифицировать стиль абзацев, для которых явно не установлен стиль. Стили абзацев устанавливаются при помощи элемента `w:pPr`. Если абзац не содержит этот элемент, выполняется форматирование стилем по умолчанию.  
  
 В этом разделе объясняется значение некоторых фрагментов запроса, после чего запрос показывается в составе целостного рабочего примера.  
  
## <a name="example"></a>Пример  
 Источник этого запроса по получению всех абзацев документа и их стилей таков:  
  
```vb  
xDoc.Root.<w:body>...<w:p>  
```  
  
 Это выражение напоминает источник запроса в предыдущем примере [поиск стиля абзаца по умолчанию (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/finding-the-default-paragraph-style.md). Основная разница в том, что здесь используется ось <xref:System.Xml.Linq.XContainer.Descendants%2A> вместо оси <xref:System.Xml.Linq.XContainer.Elements%2A>. В запросе используется ось <xref:System.Xml.Linq.XContainer.Descendants%2A>, поскольку в документах, в которых имеются разделы, абзацы не будут прямыми потомками элемента текста, а будут находиться на два уровня ниже в иерархии. За счет использования оси <xref:System.Xml.Linq.XContainer.Descendants%2A> этот код будет работать вне зависимости от того, используются разделы или нет.  
  
## <a name="example"></a>Пример  
 В этом разделе используется предложение `Let`, чтобы определить элемент, содержащий узел стиля. Если элемент не найден, то `styleNode` устанавливается в значение `Nothing`:  
  
```vb  
Let styleNode As XElement = para.<w:pPr>.<w:pStyle>.FirstOrDefault()  
```  
  
 Предложение `Let` сначала использует ось <xref:System.Xml.Linq.XContainer.Elements%2A> для поиска всех элементов с названием `pPr`, затем использует метод расширений <xref:System.Xml.Linq.Extensions.Elements%2A> для поиска всех дочерних элементов с названием `pStyle` и затем использует стандартный оператор запросов <xref:System.Linq.Enumerable.FirstOrDefault%2A> для объединения коллекции в одно целое. Если коллекция пуста, `styleNode` устанавливается в значение `Nothing`. Это выражение полезно для поиска потомков узла `pStyle`. Обратите внимание, что, если дочерний узел `pPr` не существует, код продолжает работать, а не выводит исключение. Вместо этого узел `styleNode` устанавливается в значение `Nothing`, что именно и требуется для предложения `Let`.  
  
 В этом запросе выполняется проецирование коллекции анонимного типа с двумя членами, `StyleName` и `ParagraphNode`.  
  
## <a name="example"></a>Пример  
 В данном примере обрабатывается документ WordprocessingML, из которого извлекаются узлы абзацев. Также идентифицируется стиль каждого абзаца. Этот пример основан на предыдущих примерах данного учебника. Новый запрос выявляется в комментариях в нижеприведенном коде.  
  
 Вы найдете инструкции по созданию исходного документа для этого примера в [создания источника Office Open XML-документа (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).  
  
 В этом примере используются классы, находящиеся в сборке WindowsBase. Используются типы из пространства имен <xref:System.IO.Packaging?displayProperty=nameWithType>.  
  
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
  
 Этот пример выводит следующие результаты, будучи примененным к документу, описанному в [создания источника Office Open XML-документа (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).  
  
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
  
## <a name="next-steps"></a>Следующие шаги  
 В следующем разделе [извлечение текста абзацев (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/retrieving-the-text-of-the-paragraphs.md), вы создадите запрос на извлечение текста абзацев.  
  
## <a name="see-also"></a>См. также
- [Учебник. Управление содержимым в документе WordprocessingML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
