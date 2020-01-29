---
title: Форма документов WordprocessingML (C#)
ms.date: 07/20/2015
ms.assetid: 3791b5e0-c502-469b-bb75-a7bf6fdd0a94
ms.openlocfilehash: 58c028fed465f45fdcf8f63f2119eb8e8b201e32
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732672"
---
# <a name="shape-of-wordprocessingml-documents-c"></a>Форма документов WordprocessingML (C#)
Этот раздел позволяет ознакомиться с формой XML документов WordprocessingML.  
  
## <a name="microsoft-office-formats"></a>Форматы Microsoft Office  
 Собственным форматом файлов для выпуска 2007 системы Microsoft Office является Office Open XML (который обычно называют Open XML). Open XML - это формат на основе XML, определенный стандартом Ecma, который в настоящее время проходит стандартизацию в организации ISO-IEC. Язык разметки для файлов обработки текста в системе Open XML называется WordprocessingML. В этом учебнике в качестве входных данных для примеров используются исходные файлы WordprocessingML.  
  
 При использовании Microsoft Office 2003 документы можно сохранять в формате Office Open XML, если установлен пакет обеспечения совместимости Microsoft Office Compatibility Pack для форматов Word, Excel и PowerPoint 2007.  
  
## <a name="the-shape-of-wordprocessingml-documents"></a>Форма документов WordprocessingML  
 Прежде всего необходимо понять, какую форму имеют документы WordprocessingML. Документ WordprocessingML содержит элемент body (с именем `w:body`), который включает абзацы документа. Каждый абзац содержит один или несколько текстовых периодов (с именем `w:r`). Каждый текстовый период содержит один или несколько текстовых фрагментов (с именем `w:t`).  
  
 Ниже приведен очень простой документ WordprocessingML.  
  
```xml  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<w:document  
xmlns:ve="http://schemas.openxmlformats.org/markup-compatibility/2006"  
xmlns:o="urn:schemas-microsoft-com:office:office"  
xmlns:r="http://schemas.openxmlformats.org/officeDocument/2006/relationships"  
xmlns:m="http://schemas.openxmlformats.org/officeDocument/2006/math"  
xmlns:v="urn:schemas-microsoft-com:vml"  
xmlns:wp="http://schemas.openxmlformats.org/drawingml/2006/wordprocessingDrawing"  
xmlns:w10="urn:schemas-microsoft-com:office:word"  
xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main"  
xmlns:wne="http://schemas.microsoft.com/office/word/2006/wordml">  
  <w:body>  
    <w:p w:rsidR="00E22EB6"  
         w:rsidRDefault="00E22EB6">  
      <w:r>  
        <w:t>This is a paragraph.</w:t>  
      </w:r>  
    </w:p>  
    <w:p w:rsidR="00E22EB6"  
         w:rsidRDefault="00E22EB6">  
      <w:r>  
        <w:t>This is another paragraph.</w:t>  
      </w:r>  
    </w:p>  
  </w:body>  
</w:document>  
```  
  
 В этом документе два абзаца. Оба они содержат по одному текстовому периоду, каждый включает один текстовый фрагмент.  
  
 Самый простой способ просмотра содержимого документа WordprocessingML в форме XML состоит в создании документа Microsoft Word, сохранении этого документа и запуске следующей программы, выводящей код XML на консоль.  
  
 В этом примере используются классы, находящиеся в сборке WindowsBase. Используются типы из пространства имен <xref:System.IO.Packaging?displayProperty=nameWithType>.  
  
```csharp  
const string documentRelationshipType =  
  "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument";  
const string wordmlNamespace =  
  "http://schemas.openxmlformats.org/wordprocessingml/2006/main";  
XNamespace w = wordmlNamespace;  
  
using (Package wdPackage = Package.Open("SampleDoc.docx", FileMode.Open, FileAccess.Read))  
{  
    PackageRelationship relationship =  
        wdPackage  
        .GetRelationshipsByType(documentRelationshipType)  
        .FirstOrDefault();  
    if (relationship != null)  
    {  
        Uri documentUri =  
            PackUriHelper.ResolvePartUri(  
                new Uri("/", UriKind.Relative),  
                relationship.TargetUri);  
        PackagePart documentPart = wdPackage.GetPart(documentUri);  
  
        //  Get the officeDocument part from the package.  
        //  Load the XML in the part into an XDocument instance.  
        XDocument xdoc =  
            XDocument.Load(XmlReader.Create(documentPart.GetStream()));  
        Console.WriteLine(xdoc.Root);  
    }  
}  
```  
  
## <a name="external-resources"></a>Внешние ресурсы

- [Знакомство с форматами файлов Office (2007) Open XML](https://docs.microsoft.com/previous-versions/office/developer/office-2007/aa338205%28v=office.12%29)
- [Общие сведения о WordprocessingML](https://docs.microsoft.com/previous-versions/office/developer/office-2003/aa212812%28v=office.11%29)
- [Структура файла WordProcessingML](http://officeopenxml.com/anatomyofOOXML.php)
- [Общие сведения о WordprocessingML](https://ericwhite.com/blog/introduction-to-wordprocessingml-series/)

## <a name="see-also"></a>См. также

- [Учебник. Обработка содержимого документа WordprocessingML (C#)](./shape-of-wordprocessingml-documents.md)
