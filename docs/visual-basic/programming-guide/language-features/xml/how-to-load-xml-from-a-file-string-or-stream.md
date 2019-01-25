---
title: Как выполнить Загрузить XML из файла, строки или Stream (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
ms.openlocfilehash: b660900c1ac29e40eeed36b1e07326dfbcf69ec8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54492745"
---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a>Как выполнить Загрузить XML из файла, строки или Stream (Visual Basic)
Можно создать [XML-литералов](../../../../visual-basic/language-reference/xml-literals/index.md) и заполнять их с содержимым из внешнего источника, например файла, строку или поток с помощью нескольких методов. Эти методы представлены в следующих примерах.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-load-xml-from-a-file"></a>Загрузить XML из файла  
  
-   Для заполнения XML-литерал, например <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument> объект из файла, используйте `Load` метод. Этот метод может принимать в качестве входных данных путь к файлу, текстовый поток или XML-поток.  
  
     В следующем примере кода показано использование <xref:System.Xml.Linq.XDocument.Load%28System.String%29> способ заполнения <xref:System.Xml.Linq.XDocument> объект с XML из текстового файла.  
  
     [!code-vb[VbXMLSamples#43](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_1.vb)]  
  
### <a name="to-load-xml-from-a-string"></a>Загрузить XML из строки  
  
-   Для заполнения XML-литерал, например <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument> объекта из строки, можно использовать `Parse` метод.  
  
     В следующем примере кода показано использование <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> способ заполнения <xref:System.Xml.Linq.XDocument> объект с XML из строки.  
  
     [!code-vb[VbXMLSamples#47](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_2.vb)]  
  
### <a name="to-load-xml-from-a-stream"></a>Загрузить XML из потока  
  
-   Для заполнения XML-литерал, например <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument> объекта из потока, можно использовать `Load` метод или <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> метод.  
  
 В следующем примере кода показано использование <xref:System.Xml.Linq.XNode.ReadFrom%2A> способ заполнения <xref:System.Xml.Linq.XDocument> объект с XML из XML-потока.  
  
 [!code-vb[VbXMLSamples#46](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_3.vb)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>
- [XML-литералы](../../../../visual-basic/language-reference/xml-literals/index.md)
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [Работа с XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
