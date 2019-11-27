---
title: Практическое руководство. Загрузка XML-кода из файла, строки или потока
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
ms.openlocfilehash: 7a2a0513a066ae8ea8a70f7a5ae340ab29de7d25
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330961"
---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a>Практическое руководство. Загрузка XML-кода из файла, строки или потока (Visual Basic)

Можно создать [XML-литералы](../../../../visual-basic/language-reference/xml-literals/index.md) и заполнить их содержимым из внешнего источника, например файла, строки или потока, с помощью нескольких методов. Эти методы показаны в следующих примерах.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-load-xml-from-a-file"></a>Загрузка XML из файла

Для заполнения XML-литерала, например <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument> объекта из файла, используйте метод `Load`. Этот метод может принимать в качестве входных данных путь к файлу, поток текста или поток XML.

В следующем примере кода показано использование метода <xref:System.Xml.Linq.XDocument.Load%28System.String%29> для заполнения <xref:System.Xml.Linq.XDocument> объекта XML из текстового файла.

[!code-vb[VbXMLSamples#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#43)]

## <a name="to-load-xml-from-a-string"></a>Загрузка XML из строки

Для заполнения XML-литерала, например <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument> объекта из строки, можно использовать метод `Parse`.

В следующем примере кода показано использование метода <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> для заполнения <xref:System.Xml.Linq.XDocument> объекта XML из строки.

[!code-vb[VbXMLSamples#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#47)]

## <a name="to-load-xml-from-a-stream"></a>Загрузка XML из потока

Чтобы заполнить литерал XML, например <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument> объект из потока, можно использовать метод `Load` или метод <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>.

В следующем примере кода показано использование метода <xref:System.Xml.Linq.XNode.ReadFrom%2A> для заполнения <xref:System.Xml.Linq.XDocument> объекта XML из потока XML.

[!code-vb[VbXMLSamples#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#46)]

## <a name="see-also"></a>См. также

- <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>
- [XML-литералы](../../../../visual-basic/language-reference/xml-literals/index.md)
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [Работа с XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
