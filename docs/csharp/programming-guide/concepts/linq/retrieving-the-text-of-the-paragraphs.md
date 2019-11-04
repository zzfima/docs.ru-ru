---
title: Извлечение текста абзацев (C#)
ms.date: 07/20/2015
ms.assetid: 127d635e-e559-408f-90c8-2bb621ca50ac
ms.openlocfilehash: cedca9df84ee687a9e304cde0015b46d07956364
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423330"
---
# <a name="retrieving-the-text-of-the-paragraphs-c"></a>Извлечение текста абзацев (C#)
Этот пример основан на предыдущем примере [Извлечение абзацев и стилей (C#)](./retrieving-the-paragraphs-and-their-styles.md). В этом примере текст каждого абзаца получается в строку.  
  
 Чтобы получить текст, в этом примере добавляется дополнительный запрос, который последовательно проходит по коллекции анонимных типов и проецирует новую коллекцию анонимного типа с добавлением нового члена, `Text`. Он использует стандартный оператор запроса <xref:System.Linq.Enumerable.Aggregate%2A>, чтобы объединить несколько строк в одну.  
  
 Этот способ (т. е. сначала проецирование в коллекцию анонимного типа, затем использование этой коллекции для проекции в новую коллекцию анонимного типа) широко распространен и полезен. Этот запрос не удалось бы создать без создания проекции к первому анонимному типу. Однако из-за применения неспешных вычислений это не требует много дополнительных вычислительных мощностей. Происходит создание большего количества кратковременных объектов в куче, однако производительность при этом снижается незначительно.  
  
 Конечно, было бы возможным создать единичный запрос, который содержит функциональные возможности получать абзацы, стиль и текст каждого абзаца. Однако часто полезно разбить более сложный запрос на несколько запросов, поскольку при этом результирующий код выглядит более модульным и легким для поддержки. Более того, если потребуется повторно использовать часть запроса, будет легче выполнить оптимизацию кода.  
  
 Эти связанные в цепочку запросы используют модель обработки, подробно рассматриваемую в разделе [Учебник. Объединение запросов в цепочки (C#)](deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).  
  
## <a name="example"></a>Пример  
 В этом примере выполняется обработка документа WordprocessingML, определение узла элемента, имени стиля и текста каждого абзаца. Этот пример основан на предыдущих примерах данного учебника. Новый запрос выявляется в комментариях в нижеприведенном коде.  
  
 Инструкции по созданию исходного документа для этого примера см. в разделе [Создание исходного документа в формате Office Open XML (C#)](./creating-the-source-office-open-xml-document.md).  
  
 В этом примере используются классы из сборки WindowsBase. Используются типы из пространства имен <xref:System.IO.Packaging?displayProperty=nameWithType>.  
  
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
  
 Этот пример выводит следующие результаты, будучи примененным к документу, описанному в разделе [Создание исходного документа в формате Office Open XML (C#)](./creating-the-source-office-open-xml-document.md).  
  
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
  
## <a name="next-steps"></a>Следующие шаги  
 В следующем примере показано, как использовать метод расширений вместо <xref:System.Linq.Enumerable.Aggregate%2A>, чтобы объединить несколько строк в одну.  
  
- [Рефакторинг с использованием метода расширения (C#)](./refactoring-using-an-extension-method.md)  
  
## <a name="see-also"></a>См. также

- [Учебник. Обработка содержимого документа WordprocessingML (C#)](shape-of-wordprocessingml-documents.md)
- [Отложенное выполнение и отложенное вычисление в LINQ to XML (C#)](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
