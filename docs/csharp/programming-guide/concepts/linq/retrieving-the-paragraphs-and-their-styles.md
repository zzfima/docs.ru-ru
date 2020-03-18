---
title: Извлечение абзацев и стилей (C#)
ms.date: 07/20/2015
ms.assetid: c2f767f8-57b1-4b4b-af04-89ffb1f7067d
ms.openlocfilehash: 47127b6f1d6bfaa0d8d93333882a0d0b59f1bae6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79168301"
---
# <a name="retrieving-the-paragraphs-and-their-styles-c"></a><span data-ttu-id="36516-102">Извлечение абзацев и стилей (C#)</span><span class="sxs-lookup"><span data-stu-id="36516-102">Retrieving the Paragraphs and Their Styles (C#)</span></span>
<span data-ttu-id="36516-103">В этом примере составляется запрос, при котором получаются узлы абзацев из документа WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="36516-103">In this example, we write a query that retrieves the paragraph nodes from a WordprocessingML document.</span></span> <span data-ttu-id="36516-104">Также идентифицируется стиль каждого абзаца.</span><span class="sxs-lookup"><span data-stu-id="36516-104">It also identifies the style of each paragraph.</span></span>  
  
 <span data-ttu-id="36516-105">Этот запрос основан на запросе из предыдущего примера — [Поиск стиля абзаца по умолчанию (C#)](./finding-the-default-paragraph-style.md), который получает стиль по умолчанию из списка стилей.</span><span class="sxs-lookup"><span data-stu-id="36516-105">This query builds on the query in the previous example, [Finding the Default Paragraph Style (C#)](./finding-the-default-paragraph-style.md), which retrieves the default style from the list of styles.</span></span> <span data-ttu-id="36516-106">Эти сведения требуются для того, чтобы запрос мог идентифицировать стиль абзацев, для которых явно не установлен стиль.</span><span class="sxs-lookup"><span data-stu-id="36516-106">This information is required so that the query can identify the style of paragraphs that do not have a style explicitly set.</span></span> <span data-ttu-id="36516-107">Стили абзацев устанавливаются при помощи элемента `w:pPr`. Если абзац не содержит этот элемент, выполняется форматирование стилем по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="36516-107">Paragraph styles are set through the `w:pPr` element; if a paragraph does not contain this element, it is formatted with the default style.</span></span>  
  
 <span data-ttu-id="36516-108">В этом разделе объясняется значение некоторых фрагментов запроса, после чего запрос показывается в составе целостного рабочего примера.</span><span class="sxs-lookup"><span data-stu-id="36516-108">This topic explains the significance of some pieces of the query, then shows the query as part of a complete, working example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36516-109">Пример</span><span class="sxs-lookup"><span data-stu-id="36516-109">Example</span></span>  
 <span data-ttu-id="36516-110">Источник этого запроса по получению всех абзацев документа и их стилей таков:</span><span class="sxs-lookup"><span data-stu-id="36516-110">The source of the query to retrieve all the paragraphs in a document and their styles is as follows:</span></span>  
  
```csharp  
xDoc.Root.Element(w + "body").Descendants(w + "p")  
```  
  
 <span data-ttu-id="36516-111">Это выражение напоминает источник запроса предыдущего примера — [Поиск стиля абзаца по умолчанию (C#)](./finding-the-default-paragraph-style.md).</span><span class="sxs-lookup"><span data-stu-id="36516-111">This expression is similar to the source of the query in the previous example, [Finding the Default Paragraph Style (C#)](./finding-the-default-paragraph-style.md).</span></span> <span data-ttu-id="36516-112">Основная разница в том, что здесь используется ось <xref:System.Xml.Linq.XContainer.Descendants%2A> вместо оси <xref:System.Xml.Linq.XContainer.Elements%2A>.</span><span class="sxs-lookup"><span data-stu-id="36516-112">The main difference is that it uses the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis instead of the <xref:System.Xml.Linq.XContainer.Elements%2A> axis.</span></span> <span data-ttu-id="36516-113">В запросе используется ось <xref:System.Xml.Linq.XContainer.Descendants%2A>, поскольку в документах, в которых имеются разделы, абзацы не будут прямыми потомками элемента текста, а будут находиться на два уровня ниже в иерархии.</span><span class="sxs-lookup"><span data-stu-id="36516-113">The query uses the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis because in documents that have sections, the paragraphs will not be the direct children of the body element; rather, the paragraphs will be two levels down in the hierarchy.</span></span> <span data-ttu-id="36516-114">За счет использования оси <xref:System.Xml.Linq.XContainer.Descendants%2A> этот код будет работать вне зависимости от того, используются разделы или нет.</span><span class="sxs-lookup"><span data-stu-id="36516-114">By using the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis, the code will work of whether or not the document uses sections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36516-115">Пример</span><span class="sxs-lookup"><span data-stu-id="36516-115">Example</span></span>  
 <span data-ttu-id="36516-116">В этом разделе используется предложение `let`, чтобы определить элемент, содержащий узел стиля.</span><span class="sxs-lookup"><span data-stu-id="36516-116">The query uses a `let` clause to determine the element that contains the style node.</span></span> <span data-ttu-id="36516-117">Если элемент не найден, то `styleNode` устанавливается в значение `null`:</span><span class="sxs-lookup"><span data-stu-id="36516-117">If there is no element, then `styleNode` is set to `null`:</span></span>  
  
```csharp  
let styleNode = para.Elements(w + "pPr").Elements(w + "pStyle").FirstOrDefault()  
```  
  
 <span data-ttu-id="36516-118">Предложение `let` сначала использует ось <xref:System.Xml.Linq.XContainer.Elements%2A> для поиска всех элементов с названием `pPr`, затем использует метод расширений <xref:System.Xml.Linq.Extensions.Elements%2A> для поиска всех дочерних элементов с названием `pStyle` и затем использует стандартный оператор запросов <xref:System.Linq.Enumerable.FirstOrDefault%2A> для объединения коллекции в одно целое.</span><span class="sxs-lookup"><span data-stu-id="36516-118">The `let` clause first uses the <xref:System.Xml.Linq.XContainer.Elements%2A> axis to find all elements named `pPr`, then uses the <xref:System.Xml.Linq.Extensions.Elements%2A> extension method to find all child elements named `pStyle`, and finally uses the <xref:System.Linq.Enumerable.FirstOrDefault%2A> standard query operator to convert the collection to a singleton.</span></span> <span data-ttu-id="36516-119">Если коллекция пуста, `styleNode` устанавливается в значение `null`.</span><span class="sxs-lookup"><span data-stu-id="36516-119">If the collection is empty, `styleNode` is set to `null`.</span></span> <span data-ttu-id="36516-120">Это выражение полезно для поиска потомков узла `pStyle`.</span><span class="sxs-lookup"><span data-stu-id="36516-120">This is a useful idiom to look for the `pStyle` descendant node.</span></span> <span data-ttu-id="36516-121">Обратите внимание, что, если дочерний узел `pPr` не существует, код продолжает работать, а не выводит исключение. Вместо этого узел `styleNode` устанавливается в значение `null`, что именно и требуется для предложения `let`.</span><span class="sxs-lookup"><span data-stu-id="36516-121">Note that if the `pPr` child node does not exist, the code does nor fail by throwing an exception; instead, `styleNode` is set to `null`, which is the desired behavior of this `let` clause.</span></span>  
  
 <span data-ttu-id="36516-122">В этом запросе выполняется проецирование коллекции анонимного типа с двумя членами, `StyleName` и `ParagraphNode`.</span><span class="sxs-lookup"><span data-stu-id="36516-122">The query projects a collection of an anonymous type with two members, `StyleName` and `ParagraphNode`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36516-123">Пример</span><span class="sxs-lookup"><span data-stu-id="36516-123">Example</span></span>  
 <span data-ttu-id="36516-124">В данном примере обрабатывается документ WordprocessingML, из которого извлекаются узлы абзацев.</span><span class="sxs-lookup"><span data-stu-id="36516-124">This example processes a WordprocessingML document, retrieving the paragraph nodes from a WordprocessingML document.</span></span> <span data-ttu-id="36516-125">Также идентифицируется стиль каждого абзаца.</span><span class="sxs-lookup"><span data-stu-id="36516-125">It also identifies the style of each paragraph.</span></span> <span data-ttu-id="36516-126">Этот пример основан на предыдущих примерах данного учебника.</span><span class="sxs-lookup"><span data-stu-id="36516-126">This example builds on the previous examples in this tutorial.</span></span> <span data-ttu-id="36516-127">Новый запрос выявляется в комментариях в нижеприведенном коде.</span><span class="sxs-lookup"><span data-stu-id="36516-127">The new query is called out in comments in the code below.</span></span>  
  
 <span data-ttu-id="36516-128">Инструкции по созданию исходного документа для данного примера можно найти в разделе [Создание исходного документа в формате Office Open XML (C#)](./creating-the-source-office-open-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="36516-128">You can find instructions for creating the source document for this example in [Creating the Source Office Open XML Document (C#)](./creating-the-source-office-open-xml-document.md).</span></span>  
  
 <span data-ttu-id="36516-129">В этом примере используются классы, находящиеся в сборке WindowsBase.</span><span class="sxs-lookup"><span data-stu-id="36516-129">This example uses classes found in the WindowsBase assembly.</span></span> <span data-ttu-id="36516-130">Используются типы из пространства имен <xref:System.IO.Packaging?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="36516-130">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
```csharp  
const string fileName = "SampleDoc.docx";  
  
const string documentRelationshipType = "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument";  
const string stylesRelationshipType = "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles";  
const string wordmlNamespace = "http://schemas.openxmlformats.org/wordprocessingml/2006/main";  
XNamespace w = wordmlNamespace;  
  
XDocument xDoc = null;  
XDocument styleDoc = null;  
  
using (Package wdPackage = Package.Open(fileName, FileMode.Open, FileAccess.Read))  
{  
    PackageRelationship docPackageRelationship = wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault();  
    if (docPackageRelationship != null)  
    {  
        Uri documentUri = PackUriHelper.ResolvePartUri(new Uri("/", UriKind.Relative), docPackageRelationship.TargetUri);  
        PackagePart documentPart = wdPackage.GetPart(documentUri);  
  
        //  Load the document XML in the part into an XDocument instance.  
        xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()));  
  
        //  Find the styles part. There will only be one.  
        PackageRelationship styleRelation = documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault();  
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
  
// Following is the new query that finds all paragraphs in the  
// document and their styles.  
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
  
foreach (var p in paragraphs)  
    Console.WriteLine("StyleName:{0}", p.StyleName);  
```  
  
 <span data-ttu-id="36516-131">Этот пример выводит следующие результаты, будучи примененным к документу, описанному в разделе [Создание исходного документа в формате Office Open XML (C#)](./creating-the-source-office-open-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="36516-131">This example produces the following output when applied to the document described in [Creating the Source Office Open XML Document (C#)](./creating-the-source-office-open-xml-document.md).</span></span>  
  
```output  
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
  
## <a name="next-steps"></a><span data-ttu-id="36516-132">Next Steps</span><span class="sxs-lookup"><span data-stu-id="36516-132">Next Steps</span></span>  
 <span data-ttu-id="36516-133">В следующем разделе [Извлечение текста абзацев (C#)](./retrieving-the-text-of-the-paragraphs.md) вы создадите запрос для извлечение текста абзацев.</span><span class="sxs-lookup"><span data-stu-id="36516-133">In the next topic, [Retrieving the Text of the Paragraphs (C#)](./retrieving-the-text-of-the-paragraphs.md), you'll create a query to retrieve the text of paragraphs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36516-134">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="36516-134">See also</span></span>

- [<span data-ttu-id="36516-135">Учебник. Управление содержимым в документе WordprocessingML (C#)</span><span class="sxs-lookup"><span data-stu-id="36516-135">Tutorial: Manipulating Content in a WordprocessingML Document (C#)</span></span>](./shape-of-wordprocessingml-documents.md)
