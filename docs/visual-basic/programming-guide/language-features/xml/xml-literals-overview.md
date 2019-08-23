---
title: Общие сведения об XML-литералах (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], about XML literals
- declaring XML literals [Visual Basic]
- LINQ to XML [Visual Basic], XML literals
- literals [Visual Basic], XML
ms.assetid: 37987c15-4ab8-471b-bd45-399816bfb57f
ms.openlocfilehash: 4024f4ad2b2aa8cb1897e83d87a7a00b1ba25e67
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964707"
---
# <a name="xml-literals-overview-visual-basic"></a>Общие сведения об XML-литералах (Visual Basic)
*XML-литерал* позволяет внедрять XML непосредственно в код Visual Basic. Синтаксис XML-литерала [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] представляет объекты, и он аналогичен синтаксису XML 1,0. Это упрощает создание XML-элементов и документов программным способом, так как код имеет ту же структуру, что и окончательный XML.  
  
 Visual Basic компилирует XML-литералы в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объекты. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]предоставляет простую объектную модель для создания XML-кода и управления им, и эта модель хорошо [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]интегрируется с. Дополнительные сведения см. в разделе <xref:System.Xml.Linq.XElement>.  
  
 Выражение Visual Basic можно внедрить в XML-литерал. Во время выполнения приложение создает [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объект для каждого литерала, включая значения внедренных выражений. Это позволяет указать динамическое содержимое в XML-литерале. Дополнительные сведения см. [в разделе внедренные выражения в XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
 Дополнительные сведения о различиях между синтаксисом XML-литерала и синтаксисом XML 1,0 см. [в разделе XML-литералы и спецификация xml 1,0](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md).  
  
## <a name="simple-literals"></a>Простые литералы  
 Вы можете создать [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объект в коде Visual Basic, введя или вставляя в допустимый XML. Литерал XML-элемента возвращает <xref:System.Xml.Linq.XElement> объект. Дополнительные сведения см. в статьях [литералы XML-элементов](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) и [XML-литералы и спецификация XML 1,0](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md). В следующем примере создается XML-элемент с несколькими дочерними элементами.  
  
 [!code-vb[VbXMLSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
 Можно создать XML-документ, запустив XML-литерал с `<?xml version="1.0"?>`помощью, как показано в следующем примере. Литерал XML-документа возвращает <xref:System.Xml.Linq.XDocument> объект. Дополнительные сведения см. в разделе [XML-литерал документа](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).  
  
 [!code-vb[VbXMLSamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#6)]  
  
> [!NOTE]
> Синтаксис XML-литерала в Visual Basic не идентичен синтаксису в спецификации XML 1,0. Дополнительные сведения см. [в разделе XML-литералы и спецификация xml 1,0](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md).  
  
## <a name="line-continuation"></a>Продолжение строки  
 XML-литерал может охватывать несколько строк без использования символов продолжения строки (последовательность пробел-символ подчеркивания-Enter). Это упрощает сравнение XML-литералов в коде с XML-документами.  
  
 Компилятор рассматривает символы продолжения строки как часть XML-литерала. Поэтому следует использовать последовательность пробел-подчеркивания-Enter, только если она принадлежит [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объекту.  
  
 Однако при наличии многострочного выражения во внедренном выражении нужны символы продолжения строки. Дополнительные сведения см. [в разделе внедренные выражения в XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
## <a name="embedding-queries-in-xml-literals"></a>Встраивание запросов в XML-литералы  
 Запрос можно использовать во внедренном выражении. При этом элементы, возвращаемые запросом, добавляются в XML-элемент. Это позволяет добавлять динамическое содержимое, например результат выполнения запроса пользователя, в XML-литерал.  
  
 Например, следующий код использует внедренный запрос для создания XML-элементов из членов `phoneNumbers2` массива, а затем добавляет эти элементы в качестве `contact2`дочерних элементов.  
  
 [!code-vb[VbXMLSamples#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#7)]  
  
## <a name="how-the-compiler-creates-objects-from-xml-literals"></a>Как компилятор создает объекты из XML-литералов  
 Компилятор Visual Basic преобразует литералы XML в вызовы эквивалентных [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] конструкторов для построения [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объекта. Например, компилятор Visual Basic преобразует следующий пример кода в вызов <xref:System.Xml.Linq.XProcessingInstruction> конструктора для инструкции версии XML, вызывает <xref:System.Xml.Linq.XElement> конструктор для `<contact>`, и `<phone>` `<name>` элементы и вызовы к <xref:System.Xml.Linq.XAttribute> конструктору `type` для атрибута. В частности, при наличии атрибутов, приведенных в следующем примере, компилятор Visual Basic будет <xref:System.Xml.Linq.XAttribute.%23ctor%28System.Xml.Linq.XName%2CSystem.Object%29> вызывать конструктор дважды. Первый `type` передаст значение `name` для параметра `home`изначение для параметра.`value` `type` Вторая также передает значение `name` для параметра, `value` а значение `work` для параметра.  
  
 [!code-vb[VbXMLSamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#6)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Xml.Linq.XElement>
- [Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Встроенные выражения в XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [XML-литерал документа](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [XML-литерал элемента](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [XML-литералы](../../../../visual-basic/language-reference/xml-literals/index.md)
