---
title: "Форма документов WordprocessingML (Visual Basic) | Документы Microsoft"
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
ms.assetid: 2dfb446b-5a07-4c00-9ab3-a74ba734ff3a
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e1982110ccf01f52ace20db6985d7329407357d8
ms.lasthandoff: 03/13/2017


---
# <a name="shape-of-wordprocessingml-documents-visual-basic"></a>Форма документов WordprocessingML (Visual Basic)
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
  
 В этом примере используются классы, находящиеся в сборке WindowsBase. Используются типы из <xref:System.IO.Packaging?displayProperty=fullName>имен.</xref:System.IO.Packaging?displayProperty=fullName>  
  
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
  
## <a name="external-resources"></a>Внешние ресурсы  
 [Знакомство с форматами файлов Office (2007) Open XML](http://go.microsoft.com/fwlink/?LinkId=98093)  
  
 [Общие сведения о WordprocessingML](http://go.microsoft.com/fwlink/?LinkId=98094)  
  
 [Office 2003: Страница загрузки ссылочных схем XML](http://go.microsoft.com/fwlink/?LinkId=98095)  
  
## <a name="see-also"></a>См. также  
 [Учебное руководство: Управление содержимым в документе WordprocessingML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
