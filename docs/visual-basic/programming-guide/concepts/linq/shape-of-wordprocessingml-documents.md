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
  
 В этом примере используются классы, находящиеся в сборке WindowsBase. Используются типы из пространства имен <xref:System.IO.Packaging?displayProperty=nameWithType>.  
  
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
 [Знакомство с форматами файлов Office (2007) Open XML](https://docs.microsoft.com/previous-versions/office/developer/office-2007/aa338205(v=office.12))  
  
 [Общие сведения о WordprocessingML](https://docs.microsoft.com/previous-versions/office/developer/office-2003/aa212812(v=office.11))  
  
 [Office 2003: страница загрузки ссылочных схем XML](https://go.microsoft.com/fwlink/?LinkId=98095)  
  
## <a name="see-also"></a>См. также:

- [Руководство. Управление содержимым в документе WordprocessingML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
