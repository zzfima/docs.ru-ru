---
title: "Извлечение абзацев и стилей (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: c2f767f8-57b1-4b4b-af04-89ffb1f7067d
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: db420c0aca9edadb8009556ebf476f196ee7641a
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="retrieving-the-paragraphs-and-their-styles-c"></a>Извлечение абзацев и стилей (C#)
В этом примере составляется запрос, при котором получаются узлы абзацев из документа WordprocessingML. Также идентифицируется стиль каждого абзаца.  
  
 Этот запрос основан на запросе из предыдущего примера — [Поиск стиля абзаца по умолчанию (C#)](../../../../csharp/programming-guide/concepts/linq/finding-the-default-paragraph-style.md), который получает стиль по умолчанию из списка стилей. Эти сведения требуются для того, чтобы запрос мог идентифицировать стиль абзацев, для которых явно не установлен стиль. Стили абзацев устанавливаются при помощи элемента `w:pPr`. Если абзац не содержит этот элемент, выполняется форматирование стилем по умолчанию.  
  
 В этом разделе объясняется значение некоторых фрагментов запроса, после чего запрос показывается в составе целостного рабочего примера.  
  
## <a name="example"></a>Пример  
 Источник этого запроса по получению всех абзацев документа и их стилей таков:  
  
```csharp  
xDoc.Root.Element(w + "body").Descendants(w + "p")  
```  
  
 Это выражение напоминает источник запроса предыдущего примера — [Поиск стиля абзаца по умолчанию (C#)](../../../../csharp/programming-guide/concepts/linq/finding-the-default-paragraph-style.md). Основная разница в том, что здесь используется ось <xref:System.Xml.Linq.XContainer.Descendants%2A> вместо оси <xref:System.Xml.Linq.XContainer.Elements%2A>. В запросе используется ось <xref:System.Xml.Linq.XContainer.Descendants%2A>, поскольку в документах, в которых имеются разделы, абзацы не будут прямыми потомками элемента текста, а будут находиться на два уровня ниже в иерархии. За счет использования оси <xref:System.Xml.Linq.XContainer.Descendants%2A> этот код будет работать вне зависимости от того, используются разделы или нет.  
  
## <a name="example"></a>Пример  
 В этом разделе используется предложение `let`, чтобы определить элемент, содержащий узел стиля. Если элемент не найден, то `styleNode` устанавливается в значение `null`:  
  
```csharp  
let styleNode = para.Elements(w + "pPr").Elements(w + "pStyle").FirstOrDefault()  
```  
  
 Предложение `let` сначала использует ось <xref:System.Xml.Linq.XContainer.Elements%2A> для поиска всех элементов с названием `pPr`, затем использует метод расширений <xref:System.Xml.Linq.Extensions.Elements%2A> для поиска всех дочерних элементов с названием `pStyle` и затем использует стандартный оператор запросов <xref:System.Linq.Enumerable.FirstOrDefault%2A> для объединения коллекции в одно целое. Если коллекция пуста, `styleNode` устанавливается в значение `null`. Это выражение полезно для поиска потомков узла `pStyle`. Обратите внимание, что, если дочерний узел `pPr` не существует, код продолжает работать, а не выводит исключение. Вместо этого узел `styleNode` устанавливается в значение `null`, что именно и требуется для предложения `let`.  
  
 В этом запросе выполняется проецирование коллекции анонимного типа с двумя членами, `StyleName` и `ParagraphNode`.  
  
## <a name="example"></a>Пример  
 В данном примере обрабатывается документ WordprocessingML, из которого извлекаются узлы абзацев. Также идентифицируется стиль каждого абзаца. Этот пример основан на предыдущих примерах данного учебника. Новый запрос выявляется в комментариях в нижеприведенном коде.  
  
 Инструкции по созданию исходного документа для данного примера можно найти в разделе [Создание исходного документа в формате Office Open XML (C#)](../../../../csharp/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).  
  
 В этом примере используются классы, находящиеся в сборке WindowsBase. Используются типы из пространства имен <xref:System.IO.Packaging?displayProperty=fullName>.  
  
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
  
 Этот пример выводит следующие результаты, будучи примененным к документу, описанному в разделе [Создание исходного документа в формате Office Open XML (C#)](../../../../csharp/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).  
  
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
  
## <a name="next-steps"></a>Дальнейшие действия  
 В следующем разделе [Извлечение текста абзацев (C#)](../../../../csharp/programming-guide/concepts/linq/retrieving-the-text-of-the-paragraphs.md) вы создадите запрос для извлечение текста абзацев.  
  
## <a name="see-also"></a>См. также  
 [Учебник. Управление содержимым в документе WordprocessingML (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)

