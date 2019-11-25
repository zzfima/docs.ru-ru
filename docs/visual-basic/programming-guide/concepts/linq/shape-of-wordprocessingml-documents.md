---
title: Форма документов WordprocessingML
ms.date: 07/20/2015
ms.assetid: 2dfb446b-5a07-4c00-9ab3-a74ba734ff3a
ms.openlocfilehash: 64e9ca280c000ba488bfc72248bd83e37474f043
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350607"
---
# <a name="shape-of-wordprocessingml-documents-visual-basic"></a><span data-ttu-id="80d05-102">Shape of WordprocessingML Documents (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="80d05-102">Shape of WordprocessingML Documents (Visual Basic)</span></span>
<span data-ttu-id="80d05-103">Этот раздел позволяет ознакомиться с формой XML документов WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="80d05-103">This topic introduces the XML shape of a WordprocessingML document.</span></span>  
  
## <a name="microsoft-office-formats"></a><span data-ttu-id="80d05-104">Форматы Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="80d05-104">Microsoft Office Formats</span></span>  
 <span data-ttu-id="80d05-105">Собственным форматом файлов для выпуска 2007 системы Microsoft Office является Office Open XML (который обычно называют Open XML).</span><span class="sxs-lookup"><span data-stu-id="80d05-105">The native file format for the 2007 Microsoft Office system is Office Open XML (commonly called Open XML).</span></span> <span data-ttu-id="80d05-106">Open XML - это формат на основе XML, определенный стандартом Ecma, который в настоящее время проходит стандартизацию в организации ISO-IEC.</span><span class="sxs-lookup"><span data-stu-id="80d05-106">Open XML is an XML-based format that an Ecma standard and is currently going through the ISO-IEC standards process.</span></span> <span data-ttu-id="80d05-107">Язык разметки для файлов обработки текста в системе Open XML называется WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="80d05-107">The markup language for word processing files within Open XML is called WordprocessingML.</span></span> <span data-ttu-id="80d05-108">В этом учебнике в качестве входных данных для примеров используются исходные файлы WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="80d05-108">This tutorial uses WordprocessingML source files as input for the examples.</span></span>  
  
 <span data-ttu-id="80d05-109">При использовании Microsoft Office 2003 документы можно сохранять в формате Office Open XML, если установлен пакет обеспечения совместимости Microsoft Office Compatibility Pack для форматов Word, Excel и PowerPoint 2007.</span><span class="sxs-lookup"><span data-stu-id="80d05-109">If you are using Microsoft Office 2003, you can save documents in the Office Open XML format if you have installed the Microsoft Office Compatibility Pack for Word, Excel, and PowerPoint 2007 File Formats.</span></span>  
  
## <a name="the-shape-of-wordprocessingml-documents"></a><span data-ttu-id="80d05-110">Форма документов WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="80d05-110">The Shape of WordprocessingML Documents</span></span>  
 <span data-ttu-id="80d05-111">Прежде всего необходимо понять, какую форму имеют документы WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="80d05-111">The first thing to understand is the shape of WordprocessingML documents.</span></span> <span data-ttu-id="80d05-112">Документ WordprocessingML содержит элемент body (с именем `w:body`), который включает абзацы документа.</span><span class="sxs-lookup"><span data-stu-id="80d05-112">A WordprocessingML document contains a body element (named `w:body`) that contains the paragraphs of the document.</span></span> <span data-ttu-id="80d05-113">Каждый абзац содержит один или несколько текстовых периодов (с именем `w:r`).</span><span class="sxs-lookup"><span data-stu-id="80d05-113">Each paragraph contains one or more text runs (named `w:r`).</span></span> <span data-ttu-id="80d05-114">Каждый текстовый период содержит один или несколько текстовых фрагментов (с именем `w:t`).</span><span class="sxs-lookup"><span data-stu-id="80d05-114">Each text run contains one or more text pieces (named `w:t`).</span></span>  
  
 <span data-ttu-id="80d05-115">Ниже приведен очень простой документ WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="80d05-115">The following is a very simple WordprocessingML document:</span></span>  
  
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
  
 <span data-ttu-id="80d05-116">В этом документе два абзаца.</span><span class="sxs-lookup"><span data-stu-id="80d05-116">This document contains two paragraphs.</span></span> <span data-ttu-id="80d05-117">Оба они содержат по одному текстовому периоду, каждый включает один текстовый фрагмент.</span><span class="sxs-lookup"><span data-stu-id="80d05-117">They both contain a single text run, and each text run contains a single text piece.</span></span>  
  
 <span data-ttu-id="80d05-118">Самый простой способ просмотра содержимого документа WordprocessingML в форме XML состоит в создании документа Microsoft Word, сохранении этого документа и запуске следующей программы, выводящей код XML на консоль.</span><span class="sxs-lookup"><span data-stu-id="80d05-118">The easiest way to see the contents of a WordprocessingML document in XML form is to create one using Microsoft Word, save it, and then run the following program that prints the XML to the console.</span></span>  
  
 <span data-ttu-id="80d05-119">В этом примере используются классы, находящиеся в сборке WindowsBase.</span><span class="sxs-lookup"><span data-stu-id="80d05-119">This example uses classes found in the WindowsBase assembly.</span></span> <span data-ttu-id="80d05-120">Используются типы из пространства имен <xref:System.IO.Packaging?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="80d05-120">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
```vb  
Imports <xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main">  
  
Module Module1  
    Sub Main()  
        Dim documentRelationshipType = _  
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument"  
  
        Using wdPackage As Package = _  
          Package.Open("SampleDoc.docx", _  
                       FileMode.Open, FileAccess.Read)  
            Dim docPackageRelationship As PackageRelationship = wdPackage _  
                .GetRelationshipsByType(documentRelationshipType).FirstOrDefault()  
            If (docPackageRelationship IsNot Nothing) Then  
                Dim documentUri As Uri = PackUriHelper.ResolvePartUri( _  
                            New Uri("/", UriKind.Relative), _  
                            docPackageRelationship.TargetUri)  
                Dim documentPart As PackagePart = wdPackage.GetPart(documentUri)  
  
                ' Get the officeDocument part from the package.  
                ' Load the XML in the part into an XDocument instance.  
                Dim xDoc As XDocument = _  
                    XDocument.Load(XmlReader.Create(documentPart.GetStream()))  
                Console.WriteLine(xDoc.Root)  
            End If  
        End Using  
    End Sub  
End Module  
```  
  
## <a name="external-resources"></a><span data-ttu-id="80d05-121">Внешние ресурсы</span><span class="sxs-lookup"><span data-stu-id="80d05-121">External Resources</span></span>  
 <span data-ttu-id="80d05-122">[Знакомство с форматами файлов Office (2007) Open XML](https://docs.microsoft.com/previous-versions/office/developer/office-2007/aa338205(v=office.12))</span><span class="sxs-lookup"><span data-stu-id="80d05-122">[Introducing the Office (2007) Open XML File Formats](https://docs.microsoft.com/previous-versions/office/developer/office-2007/aa338205(v=office.12))</span></span>  
  
 <span data-ttu-id="80d05-123">[Общие сведения о WordprocessingML](https://docs.microsoft.com/previous-versions/office/developer/office-2003/aa212812(v=office.11))</span><span class="sxs-lookup"><span data-stu-id="80d05-123">[Overview of WordprocessingML](https://docs.microsoft.com/previous-versions/office/developer/office-2003/aa212812(v=office.11))</span></span>  
  
 [<span data-ttu-id="80d05-124">Office 2003: страница загрузки ссылочных схем XML</span><span class="sxs-lookup"><span data-stu-id="80d05-124">Office 2003: XML Reference Schemas Download page</span></span>](https://go.microsoft.com/fwlink/?LinkId=98095)  
  
## <a name="see-also"></a><span data-ttu-id="80d05-125">См. также</span><span class="sxs-lookup"><span data-stu-id="80d05-125">See also</span></span>

- [<span data-ttu-id="80d05-126">Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="80d05-126">Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
