---
title: Форма документов WordprocessingML (C#)
ms.date: 07/20/2015
ms.assetid: 3791b5e0-c502-469b-bb75-a7bf6fdd0a94
ms.openlocfilehash: aeb047f23f60ba6951950a85a6e2ef57fcbd9dda
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2018
ms.locfileid: "44211389"
---
# <a name="shape-of-wordprocessingml-documents-c"></a><span data-ttu-id="79731-102">Форма документов WordprocessingML (C#)</span><span class="sxs-lookup"><span data-stu-id="79731-102">Shape of WordprocessingML Documents (C#)</span></span>
<span data-ttu-id="79731-103">Этот раздел позволяет ознакомиться с формой XML документов WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="79731-103">This topic introduces the XML shape of a WordprocessingML document.</span></span>  
  
## <a name="microsoft-office-formats"></a><span data-ttu-id="79731-104">Форматы Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="79731-104">Microsoft Office Formats</span></span>  
 <span data-ttu-id="79731-105">Собственным форматом файлов для выпуска 2007 системы Microsoft Office является Office Open XML (который обычно называют Open XML).</span><span class="sxs-lookup"><span data-stu-id="79731-105">The native file format for the 2007 Microsoft Office system is Office Open XML (commonly called Open XML).</span></span> <span data-ttu-id="79731-106">Open XML - это формат на основе XML, определенный стандартом Ecma, который в настоящее время проходит стандартизацию в организации ISO-IEC.</span><span class="sxs-lookup"><span data-stu-id="79731-106">Open XML is an XML-based format that an Ecma standard and is currently going through the ISO-IEC standards process.</span></span> <span data-ttu-id="79731-107">Язык разметки для файлов обработки текста в системе Open XML называется WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="79731-107">The markup language for word processing files within Open XML is called WordprocessingML.</span></span> <span data-ttu-id="79731-108">В этом учебнике в качестве входных данных для примеров используются исходные файлы WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="79731-108">This tutorial uses WordprocessingML source files as input for the examples.</span></span>  
  
 <span data-ttu-id="79731-109">При использовании Microsoft Office 2003 документы можно сохранять в формате Office Open XML, если установлен пакет обеспечения совместимости Microsoft Office Compatibility Pack для форматов Word, Excel и PowerPoint 2007.</span><span class="sxs-lookup"><span data-stu-id="79731-109">If you are using Microsoft Office 2003, you can save documents in the Office Open XML format if you have installed the Microsoft Office Compatibility Pack for Word, Excel, and PowerPoint 2007 File Formats.</span></span>  
  
## <a name="the-shape-of-wordprocessingml-documents"></a><span data-ttu-id="79731-110">Форма документов WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="79731-110">The Shape of WordprocessingML Documents</span></span>  
 <span data-ttu-id="79731-111">Прежде всего необходимо понять, какую форму имеют документы WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="79731-111">The first thing to understand is the shape of WordprocessingML documents.</span></span> <span data-ttu-id="79731-112">Документ WordprocessingML содержит элемент body (с именем `w:body`), который включает абзацы документа.</span><span class="sxs-lookup"><span data-stu-id="79731-112">A WordprocessingML document contains a body element (named `w:body`) that contains the paragraphs of the document.</span></span> <span data-ttu-id="79731-113">Каждый абзац содержит один или несколько текстовых периодов (с именем `w:r`).</span><span class="sxs-lookup"><span data-stu-id="79731-113">Each paragraph contains one or more text runs (named `w:r`).</span></span> <span data-ttu-id="79731-114">Каждый текстовый период содержит один или несколько текстовых фрагментов (с именем `w:t`).</span><span class="sxs-lookup"><span data-stu-id="79731-114">Each text run contains one or more text pieces (named `w:t`).</span></span>  
  
 <span data-ttu-id="79731-115">Ниже приведен очень простой документ WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="79731-115">The following is a very simple WordprocessingML document:</span></span>  
  
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
  
 <span data-ttu-id="79731-116">В этом документе два абзаца.</span><span class="sxs-lookup"><span data-stu-id="79731-116">This document contains two paragraphs.</span></span> <span data-ttu-id="79731-117">Оба они содержат по одному текстовому периоду, каждый включает один текстовый фрагмент.</span><span class="sxs-lookup"><span data-stu-id="79731-117">They both contain a single text run, and each text run contains a single text piece.</span></span>  
  
 <span data-ttu-id="79731-118">Самый простой способ просмотра содержимого документа WordprocessingML в форме XML состоит в создании документа Microsoft Word, сохранении этого документа и запуске следующей программы, выводящей код XML на консоль.</span><span class="sxs-lookup"><span data-stu-id="79731-118">The easiest way to see the contents of a WordprocessingML document in XML form is to create one using Microsoft Word, save it, and then run the following program that prints the XML to the console.</span></span>  
  
 <span data-ttu-id="79731-119">В этом примере используются классы, находящиеся в сборке WindowsBase.</span><span class="sxs-lookup"><span data-stu-id="79731-119">This example uses classes found in the WindowsBase assembly.</span></span> <span data-ttu-id="79731-120">Используются типы из пространства имен <xref:System.IO.Packaging?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="79731-120">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
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
  
## <a name="external-resources"></a><span data-ttu-id="79731-121">Внешние ресурсы</span><span class="sxs-lookup"><span data-stu-id="79731-121">External Resources</span></span>  
 [<span data-ttu-id="79731-122">Знакомство с форматами файлов Office (2007) Open XML</span><span class="sxs-lookup"><span data-stu-id="79731-122">Introducing the Office (2007) Open XML File Formats</span></span>](https://msdn.microsoft.com/library/ms406049.aspx)  
 <span data-ttu-id="79731-123">[Общие сведения о WordprocessingML](https://msdn.microsoft.com/library/aa212812(office.11).aspx)</span><span class="sxs-lookup"><span data-stu-id="79731-123">[Overview of WordprocessingML](https://msdn.microsoft.com/library/aa212812(office.11).aspx)</span></span>  
 [<span data-ttu-id="79731-124">Структура файла WordProcessingML</span><span class="sxs-lookup"><span data-stu-id="79731-124">Anatomy of a WordProcessingML File</span></span>](http://officeopenxml.com/anatomyofOOXML.php)  
 [<span data-ttu-id="79731-125">Общие сведения о WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="79731-125">Introduction to WordprocessingML</span></span>](http://ericwhite.com/blog/introduction-to-wordprocessingml-series/)  
 [<span data-ttu-id="79731-126">Office 2003: страница загрузки ссылочных схем XML</span><span class="sxs-lookup"><span data-stu-id="79731-126">Office 2003: XML Reference Schemas Download page</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=101)  
  
## <a name="see-also"></a><span data-ttu-id="79731-127">См. также</span><span class="sxs-lookup"><span data-stu-id="79731-127">See Also</span></span>

- [<span data-ttu-id="79731-128">Учебник. Управление содержимым в документе WordprocessingML (C#)</span><span class="sxs-lookup"><span data-stu-id="79731-128">Tutorial: Manipulating Content in a WordprocessingML Document (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
