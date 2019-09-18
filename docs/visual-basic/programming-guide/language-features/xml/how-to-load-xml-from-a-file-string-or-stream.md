---
title: Практическое руководство. Загрузка XML из файла, строки или потока (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
ms.openlocfilehash: ba88ae19abc216a318d6c2069ab0846d5db8a346
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71054166"
---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a>Практическое руководство. Загрузка XML из файла, строки или потока (Visual Basic)

Можно создать [XML-литералы](../../../../visual-basic/language-reference/xml-literals/index.md) и заполнить их содержимым из внешнего источника, например файла, строки или потока, с помощью нескольких методов. Эти методы показаны в следующих примерах.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-load-xml-from-a-file"></a>Загрузка XML из файла

Чтобы заполнить XML-литерал, например <xref:System.Xml.Linq.XElement> объект или <xref:System.Xml.Linq.XDocument> , из файла, используйте `Load` метод. Этот метод может принимать в качестве входных данных путь к файлу, поток текста или поток XML.

В следующем примере кода показано использование <xref:System.Xml.Linq.XDocument.Load%28System.String%29> метода для заполнения <xref:System.Xml.Linq.XDocument> объекта XML из текстового файла.

[!code-vb[VbXMLSamples#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#43)]

## <a name="to-load-xml-from-a-string"></a>Загрузка XML из строки

Для заполнения XML-литерала <xref:System.Xml.Linq.XElement> `Parse` , такого как объект <xref:System.Xml.Linq.XDocument> или, из строки можно использовать метод.

В следующем примере кода показано использование <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> метода для заполнения <xref:System.Xml.Linq.XDocument> объекта XML из строки.

[!code-vb[VbXMLSamples#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#47)]

## <a name="to-load-xml-from-a-stream"></a>Загрузка XML из потока

Для заполнения XML- <xref:System.Xml.Linq.XElement> литерала `Load` , такого как объект <xref:System.Xml.Linq.XDocument> или, из потока можно <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> использовать метод или.

В следующем примере кода показано использование <xref:System.Xml.Linq.XNode.ReadFrom%2A> метода для заполнения <xref:System.Xml.Linq.XDocument> объекта XML-потоком из XML-потока.

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
