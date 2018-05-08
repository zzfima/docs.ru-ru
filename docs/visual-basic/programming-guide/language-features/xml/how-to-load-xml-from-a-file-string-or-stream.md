---
title: Практическое руководство. Загрузка XML-кода из файла, строки или потока (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
ms.openlocfilehash: 241f6552e46d7689b42a409ba44bc747984773ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a>Практическое руководство. Загрузка XML-кода из файла, строки или потока (Visual Basic)
Можно создать [XML-литералы](../../../../visual-basic/language-reference/xml-literals/index.md) и заполнить их содержимое из внешнего источника, например файла, строки или потока с помощью нескольких методов. В следующих примерах показаны эти методы.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-load-xml-from-a-file"></a>Чтобы загрузить XML из файла  
  
-   Для заполнения XML-литерал, например <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument> объекта из файла, используйте `Load` метод. Этот метод можно использовать в качестве входа путь к файлу, текстовый поток или XML-поток.  
  
     В следующем примере кода показано использование <xref:System.Xml.Linq.XDocument.Load%28System.String%29> метод для заполнения <xref:System.Xml.Linq.XDocument> объекта с XML из текстового файла.  
  
     [!code-vb[VbXMLSamples#43](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_1.vb)]  
  
### <a name="to-load-xml-from-a-string"></a>Чтобы загрузить XML из строки  
  
-   Для заполнения XML-литерал, например <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument> объекта из строки, можно использовать `Parse` метода.  
  
     В следующем примере кода показано использование <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> метод для заполнения <xref:System.Xml.Linq.XDocument> объекта с XML из строки.  
  
     [!code-vb[VbXMLSamples#47](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_2.vb)]  
  
### <a name="to-load-xml-from-a-stream"></a>Чтобы загрузить XML из потока  
  
-   Для заполнения XML-литерал, например <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument> объекта из потока, можно использовать `Load` метода или <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> метод.  
  
 В следующем примере кода показано использование <xref:System.Xml.Linq.XNode.ReadFrom%2A> метод для заполнения <xref:System.Xml.Linq.XDocument> объект с XML из XML-потока.  
  
 [!code-vb[VbXMLSamples#46](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_3.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>  
 [XML-литералы](../../../../visual-basic/language-reference/xml-literals/index.md)  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [Работа с XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
