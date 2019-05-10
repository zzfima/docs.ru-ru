---
title: Поиск стиля абзаца по умолчанию (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 9d094a4a-ec8c-41b0-b7ab-a3deb2a01d45
ms.openlocfilehash: f874033b9a070b951d27f37aae36f738ab1fd222
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64618379"
---
# <a name="finding-the-default-paragraph-style-visual-basic"></a><span data-ttu-id="c48d4-102">Поиск стиля абзаца по умолчанию (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c48d4-102">Finding the Default Paragraph Style (Visual Basic)</span></span>
<span data-ttu-id="c48d4-103">Первая задача в учебнике "Обработка информации в документе WordprocessingML" заключается в поиске стиля абзацев по умолчанию в документе.</span><span class="sxs-lookup"><span data-stu-id="c48d4-103">The first task in the Manipulating Information in a WordprocessingML Document tutorial is to find the default style of paragraphs in the document.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c48d4-104">Пример</span><span class="sxs-lookup"><span data-stu-id="c48d4-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="c48d4-105">Описание</span><span class="sxs-lookup"><span data-stu-id="c48d4-105">Description</span></span>  
 <span data-ttu-id="c48d4-106">В следующем примере открывается документ Office Open XML WordprocessingML, осуществляется поиск секций с документом и стилями в пакете, а затем выполняется запрос, который находит имя стиля по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c48d4-106">The following example opens an Office Open XML WordprocessingML document, finds the document and style parts of the package, and then executes a query that finds the default style name.</span></span> <span data-ttu-id="c48d4-107">Сведения о пакетах документа Office Open XML и частях, из которых они состоят, см. в разделе [сведения об Office Open XML документов WordprocessingML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md).</span><span class="sxs-lookup"><span data-stu-id="c48d4-107">For information about Office Open XML document packages, and the parts they consist of, see [Details of Office Open XML WordprocessingML Documents (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md).</span></span>  
  
 <span data-ttu-id="c48d4-108">Этот запрос находит узел с именем `w:style`, который имеет атрибут `w:type` со значением «paragraph», а также имеет атрибут `w:default` со значением «1».</span><span class="sxs-lookup"><span data-stu-id="c48d4-108">The query finds a node named `w:style` that has an attribute named `w:type` with a value of "paragraph", and also has an attribute named `w:default` with a value of "1".</span></span> <span data-ttu-id="c48d4-109">Так как XML-узел с этими атрибутами будет только один, запрос использует оператор <xref:System.Linq.Enumerable.First%2A?displayProperty=nameWithType>, чтобы преобразовать коллекцию в один элемент.</span><span class="sxs-lookup"><span data-stu-id="c48d4-109">Because there will be only one XML node with these attributes, the query uses the <xref:System.Linq.Enumerable.First%2A?displayProperty=nameWithType> operator to convert a collection to a singleton.</span></span> <span data-ttu-id="c48d4-110">Затем он возвращает значение атрибута `w:styleId`.</span><span class="sxs-lookup"><span data-stu-id="c48d4-110">It then gets the value of the attribute with the name `w:styleId`.</span></span>  
  
 <span data-ttu-id="c48d4-111">В этом примере используются классы из сборки WindowsBase.</span><span class="sxs-lookup"><span data-stu-id="c48d4-111">This example uses classes from the WindowsBase assembly.</span></span> <span data-ttu-id="c48d4-112">Используются типы из пространства имен <xref:System.IO.Packaging?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c48d4-112">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
### <a name="code"></a><span data-ttu-id="c48d4-113">Код</span><span class="sxs-lookup"><span data-stu-id="c48d4-113">Code</span></span>  
  
```vb  
Imports <xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main">  
  
Module Module1  
  
    Sub Main()  
  
        Const fileName As String = "SampleDoc.docx"  
  
        Const documentRelationshipType As String = _  
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument"  
        Const stylesRelationshipType As String = _  
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles"  
  
        Dim xDoc As XDocument = Nothing  
        Dim styleDoc As XDocument = Nothing  
  
        Using wdPackage As Package = Package.Open(fileName, FileMode.Open, FileAccess.Read)  
            Dim docPackageRelationship As PackageRelationship = _  
              wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault()  
            If docPackageRelationship IsNot Nothing Then  
                Dim documentUri As Uri = PackUriHelper.ResolvePartUri(New Uri("/", UriKind.Relative), _  
                  docPackageRelationship.TargetUri)  
                Dim documentPart As PackagePart = wdPackage.GetPart(documentUri)  
  
                ' Load the document XML in the part into an XDocument instance.  
                xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()))  
  
                ' Find the styles part. There will only be one.  
                Dim styleRelation As PackageRelationship = _  
                  documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault()  
                If styleRelation IsNot Nothing Then  
                    Dim styleUri As Uri = _  
                      PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri)  
                    Dim stylePart As PackagePart = wdPackage.GetPart(styleUri)  
  
                    ' Load the style XML in the part into an XDocument instance.  
                    styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()))  
                End If  
            End If  
        End Using  
  
        ' The following query finds all the paragraphs that have the default style.  
        Dim defParas As IEnumerable(Of XElement) = _  
            From style In styleDoc.Root.<w:style> _  
            Where style.@w:type.Equals("paragraph") And _  
                   style.@w:default.Equals("1") _  
            Select style  
        ' Then find the style of the first.  
        Dim defaultStyle As String = defParas.First().@w:styleId  
  
        Console.WriteLine("The default style is: " & defaultStyle)  
    End Sub  
End Module  
```  
  
### <a name="comments"></a><span data-ttu-id="c48d4-114">Комментарии</span><span class="sxs-lookup"><span data-stu-id="c48d4-114">Comments</span></span>  
 <span data-ttu-id="c48d4-115">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="c48d4-115">This example produces the following output:</span></span>  
  
```  
The default style is: Normal  
```  
  
## <a name="next-steps"></a><span data-ttu-id="c48d4-116">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="c48d4-116">Next Steps</span></span>  
 <span data-ttu-id="c48d4-117">В следующем примере будет создан похожий запрос, который ищет все абзацы в документе и их стили:</span><span class="sxs-lookup"><span data-stu-id="c48d4-117">In the next example, you'll create a similar query that finds all the paragraphs in a document and their styles:</span></span>  
  
- [<span data-ttu-id="c48d4-118">Извлечение абзацев и стилей (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c48d4-118">Retrieving the Paragraphs and Their Styles (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/retrieving-the-paragraphs-and-their-styles.md)  
  
## <a name="see-also"></a><span data-ttu-id="c48d4-119">См. также</span><span class="sxs-lookup"><span data-stu-id="c48d4-119">See also</span></span>

- [<span data-ttu-id="c48d4-120">Учебник. Управление содержимым в документе WordprocessingML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c48d4-120">Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
