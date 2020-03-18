---
title: Извлечение текста абзацев (C#)
ms.date: 07/20/2015
ms.assetid: 127d635e-e559-408f-90c8-2bb621ca50ac
ms.openlocfilehash: 7c47420045def3fe973169e01143646c0f60a8eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79168249"
---
# <a name="retrieving-the-text-of-the-paragraphs-c"></a><span data-ttu-id="fe23d-102">Извлечение текста абзацев (C#)</span><span class="sxs-lookup"><span data-stu-id="fe23d-102">Retrieving the Text of the Paragraphs (C#)</span></span>
<span data-ttu-id="fe23d-103">Этот пример основан на предыдущем примере [Извлечение абзацев и стилей (C#)](./retrieving-the-paragraphs-and-their-styles.md).</span><span class="sxs-lookup"><span data-stu-id="fe23d-103">This example builds on the previous example, [Retrieving the Paragraphs and Their Styles (C#)](./retrieving-the-paragraphs-and-their-styles.md).</span></span> <span data-ttu-id="fe23d-104">В этом примере текст каждого абзаца получается в строку.</span><span class="sxs-lookup"><span data-stu-id="fe23d-104">This new example retrieves the text of each paragraph as a string.</span></span>  
  
 <span data-ttu-id="fe23d-105">Чтобы получить текст, в этом примере добавляется дополнительный запрос, который последовательно проходит по коллекции анонимных типов и проецирует новую коллекцию анонимного типа с добавлением нового члена, `Text`.</span><span class="sxs-lookup"><span data-stu-id="fe23d-105">To retrieve the text, this example adds an additional query that iterates through the collection of anonymous types and projects a new collection of an anonymous type with the addition of a new member, `Text`.</span></span> <span data-ttu-id="fe23d-106">Он использует стандартный оператор запроса <xref:System.Linq.Enumerable.Aggregate%2A>, чтобы объединить несколько строк в одну.</span><span class="sxs-lookup"><span data-stu-id="fe23d-106">It uses the <xref:System.Linq.Enumerable.Aggregate%2A> standard query operator to concatenate multiple strings into one string.</span></span>  
  
 <span data-ttu-id="fe23d-107">Этот способ (т. е. сначала проецирование в коллекцию анонимного типа, затем использование этой коллекции для проекции в новую коллекцию анонимного типа) широко распространен и полезен.</span><span class="sxs-lookup"><span data-stu-id="fe23d-107">This technique (that is, first projecting to a collection of an anonymous type, then using this collection to project to a new collection of an anonymous type) is a common and useful idiom.</span></span> <span data-ttu-id="fe23d-108">Этот запрос не удалось бы создать без создания проекции к первому анонимному типу.</span><span class="sxs-lookup"><span data-stu-id="fe23d-108">This query could have been written without projecting to the first anonymous type.</span></span> <span data-ttu-id="fe23d-109">Однако из-за применения неспешных вычислений это не требует много дополнительных вычислительных мощностей.</span><span class="sxs-lookup"><span data-stu-id="fe23d-109">However, because of lazy evaluation, doing so does not use much additional processing power.</span></span> <span data-ttu-id="fe23d-110">Происходит создание большего количества кратковременных объектов в куче, однако производительность при этом снижается незначительно.</span><span class="sxs-lookup"><span data-stu-id="fe23d-110">The idiom creates more short lived objects on the heap, but this does not substantially degrade performance.</span></span>  
  
 <span data-ttu-id="fe23d-111">Конечно, было бы возможным создать единичный запрос, который содержит функциональные возможности получать абзацы, стиль и текст каждого абзаца.</span><span class="sxs-lookup"><span data-stu-id="fe23d-111">Of course, it would be possible to write a single query that contains the functionality to retrieve the paragraphs, the style of each paragraph, and the text of each paragraph.</span></span> <span data-ttu-id="fe23d-112">Однако часто полезно разбить более сложный запрос на несколько запросов, поскольку при этом результирующий код выглядит более модульным и легким для поддержки.</span><span class="sxs-lookup"><span data-stu-id="fe23d-112">However, it often is useful to break up a more complicated query into multiple queries because the resulting code is more modular and easier to maintain.</span></span> <span data-ttu-id="fe23d-113">Более того, если потребуется повторно использовать часть запроса, будет легче выполнить оптимизацию кода.</span><span class="sxs-lookup"><span data-stu-id="fe23d-113">Furthermore, if you need to reuse a portion of the query, it is easier to refactor if the queries are written in this manner.</span></span>  
  
 <span data-ttu-id="fe23d-114">Эти связанные в цепочку запросы используют модель обработки, подробно рассматриваемую в разделе [Учебник. Объединение запросов в цепочки (C#)](deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="fe23d-114">These queries, which are chained together, use the processing model that is examined in detail in the topic [Tutorial: Chaining Queries Together (C#)](deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe23d-115">Пример</span><span class="sxs-lookup"><span data-stu-id="fe23d-115">Example</span></span>  
 <span data-ttu-id="fe23d-116">В этом примере выполняется обработка документа WordprocessingML, определение узла элемента, имени стиля и текста каждого абзаца.</span><span class="sxs-lookup"><span data-stu-id="fe23d-116">This example processes a WordprocessingML document, determining the element node, the style name, and the text of each paragraph.</span></span> <span data-ttu-id="fe23d-117">Этот пример основан на предыдущих примерах данного учебника.</span><span class="sxs-lookup"><span data-stu-id="fe23d-117">This example builds on the previous examples in this tutorial.</span></span> <span data-ttu-id="fe23d-118">Новый запрос выявляется в комментариях в нижеприведенном коде.</span><span class="sxs-lookup"><span data-stu-id="fe23d-118">The new query is called out in comments in the code below.</span></span>  
  
 <span data-ttu-id="fe23d-119">Инструкции по созданию исходного документа для этого примера см. в разделе [Создание исходного документа в формате Office Open XML (C#)](./creating-the-source-office-open-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="fe23d-119">For instructions for creating the source document for this example, see [Creating the Source Office Open XML Document (C#)](./creating-the-source-office-open-xml-document.md).</span></span>  
  
 <span data-ttu-id="fe23d-120">В этом примере используются классы из сборки WindowsBase.</span><span class="sxs-lookup"><span data-stu-id="fe23d-120">This example uses classes from the WindowsBase assembly.</span></span> <span data-ttu-id="fe23d-121">Используются типы из пространства имен <xref:System.IO.Packaging?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fe23d-121">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
```csharp  
const string fileName = "SampleDoc.docx";  
  
const string documentRelationshipType =  
  "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument";  
const string stylesRelationshipType =  
  "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles";  
const string wordmlNamespace =  
  "http://schemas.openxmlformats.org/wordprocessingml/2006/main";  
XNamespace w = wordmlNamespace;  
  
XDocument xDoc = null;  
XDocument styleDoc = null;  
  
using (Package wdPackage = Package.Open(fileName, FileMode.Open, FileAccess.Read))  
{  
    PackageRelationship docPackageRelationship =  
      wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault();  
    if (docPackageRelationship != null)  
    {  
        Uri documentUri = PackUriHelper.ResolvePartUri(new Uri("/", UriKind.Relative),  
          docPackageRelationship.TargetUri);  
        PackagePart documentPart = wdPackage.GetPart(documentUri);  
  
        //  Load the document XML in the part into an XDocument instance.  
        xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()));  
  
        //  Find the styles part. There will only be one.  
        PackageRelationship styleRelation =  
          documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault();  
        if (styleRelation != null)  
        {  
            Uri styleUri = PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri);  
            PackagePart stylePart = wdPackage.GetPart(styleUri);  
  
            //  Load the style XML in the part into an XDocument instance.  
            styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()));  
        }  
    }  
}  
  
string defaultStyle =
    (string)(  
        from style in styleDoc.Root.Elements(w + "style")  
        where (string)style.Attribute(w + "type") == "paragraph"&&  
              (string)style.Attribute(w + "default") == "1"  
              select style  
    ).First().Attribute(w + "styleId");  
  
// Find all paragraphs in the document.  
var paragraphs =  
    from para in xDoc  
                 .Root  
                 .Element(w + "body")  
                 .Descendants(w + "p")  
    let styleNode = para  
                    .Elements(w + "pPr")  
                    .Elements(w + "pStyle")  
                    .FirstOrDefault()  
    select new  
    {  
        ParagraphNode = para,  
        StyleName = styleNode != null ?  
            (string)styleNode.Attribute(w + "val") :  
            defaultStyle  
    };  
  
// Following is the new query that retrieves the text of  
// each paragraph.  
var paraWithText =  
    from para in paragraphs  
    select new  
    {  
        ParagraphNode = para.ParagraphNode,  
        StyleName = para.StyleName,  
        Text = para  
               .ParagraphNode  
               .Elements(w + "r")  
               .Elements(w + "t")  
               .Aggregate(  
                   new StringBuilder(),  
                   (s, i) => s.Append((string)i),  
                   s => s.ToString()  
               )  
    };  
  
foreach (var p in paraWithText)  
    Console.WriteLine("StyleName:{0} >{1}<", p.StyleName, p.Text);  
```  
  
 <span data-ttu-id="fe23d-122">Этот пример выводит следующие результаты, будучи примененным к документу, описанному в разделе [Создание исходного документа в формате Office Open XML (C#)](./creating-the-source-office-open-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="fe23d-122">This example produces the following output when applied to the document described in [Creating the Source Office Open XML Document (C#)](./creating-the-source-office-open-xml-document.md).</span></span>  
  
```output  
StyleName:Heading1 >Parsing WordprocessingML with LINQ to XML<  
StyleName:Normal ><  
StyleName:Normal >The following example prints to the console.<  
StyleName:Normal ><  
StyleName:Code >using System;<  
StyleName:Code ><  
StyleName:Code >class Program {<  
StyleName:Code >    public static void (string[] args) {<  
StyleName:Code >        Console.WriteLine("Hello World");<  
StyleName:Code >    }<  
StyleName:Code >}<  
StyleName:Normal ><  
StyleName:Normal >This example produces the following output:<  
StyleName:Normal ><  
StyleName:Code >Hello World<  
```  
  
## <a name="next-steps"></a><span data-ttu-id="fe23d-123">Next Steps</span><span class="sxs-lookup"><span data-stu-id="fe23d-123">Next Steps</span></span>  
 <span data-ttu-id="fe23d-124">В следующем примере показано, как использовать метод расширений вместо <xref:System.Linq.Enumerable.Aggregate%2A>, чтобы объединить несколько строк в одну.</span><span class="sxs-lookup"><span data-stu-id="fe23d-124">The next example shows how to use an extension method, instead of <xref:System.Linq.Enumerable.Aggregate%2A>, to concatenate multiple strings into a single string.</span></span>  
  
- [<span data-ttu-id="fe23d-125">Рефакторинг с использованием метода расширения (C#)</span><span class="sxs-lookup"><span data-stu-id="fe23d-125">Refactoring Using an Extension Method (C#)</span></span>](./refactoring-using-an-extension-method.md)  
  
## <a name="see-also"></a><span data-ttu-id="fe23d-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="fe23d-126">See also</span></span>

- [<span data-ttu-id="fe23d-127">Учебник. Управление содержимым в документе WordprocessingML (C#)</span><span class="sxs-lookup"><span data-stu-id="fe23d-127">Tutorial: Manipulating Content in a WordprocessingML Document (C#)</span></span>](shape-of-wordprocessingml-documents.md)
- [<span data-ttu-id="fe23d-128">Отложенное выполнение и отложенное вычисление в LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="fe23d-128">Deferred Execution and Lazy Evaluation in LINQ to XML (C#)</span></span>](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
