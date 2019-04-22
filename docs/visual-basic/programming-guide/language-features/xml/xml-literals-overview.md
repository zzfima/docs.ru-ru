---
title: Общие сведения об XML-литералах (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], about XML literals
- declaring XML literals [Visual Basic]
- LINQ to XML [Visual Basic], XML literals
- literals [Visual Basic], XML
ms.assetid: 37987c15-4ab8-471b-bd45-399816bfb57f
ms.openlocfilehash: a7b70669131ae35135088418e4b33b3ae289d322
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58839890"
---
# <a name="xml-literals-overview-visual-basic"></a>Общие сведения об XML-литералах (Visual Basic)
*XML-литерал* позволяет внедрять XML непосредственно в код Visual Basic. Синтаксис XML представляет [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объектов, который напоминает синтаксис XML 1.0. Это упрощает программное создание XML-элементов и документов, так как ваш код имеет такую же структуру, как последний XML.  
  
 Visual Basic компилирует литералы XML в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объектов. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] предоставляет простую объектную модель для создания и обработки XML и эта модель хорошо интегрируется с [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]. Дополнительные сведения см. в разделе <xref:System.Xml.Linq.XElement>.  
  
 Выражение Visual Basic можно внедрить в XML-литерал. Во время выполнения приложение создает [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объект для каждого литерала, включая значения внедренных выражений. Это позволяет указывать динамическое содержимое в XML-литерал. Дополнительные сведения см. в разделе [встроенные выражения в XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
 Дополнительные сведения о различиях между синтаксисом литералов XML и синтаксис XML 1.0, см. в разделе [XML-литералы и спецификация XML 1.0](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md).  
  
## <a name="simple-literals"></a>Простые литералы  
 Можно создать [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объекта в коде Visual Basic, введя или вставив в допустимый XML-код. Возвращает литерала элемента XML <xref:System.Xml.Linq.XElement> объекта. Дополнительные сведения см. в разделе [литерала элемента XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) и [XML-литералы и спецификация XML 1.0](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md). В следующем примере создается элемент XML, который имеет несколько дочерних элементов.  
  
 [!code-vb[VbXMLSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
 Можно создать XML-документ, запустив литерал XML с `<?xml version="1.0"?>`, как показано в следующем примере. Возвращает XML-литерала документа <xref:System.Xml.Linq.XDocument> объекта. Дополнительные сведения см. в разделе [литерала документа XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).  
  
 [!code-vb[VbXMLSamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#6)]  
  
> [!NOTE]
>  Синтаксис XML-литералов в Visual Basic не идентичен синтаксису спецификации XML 1.0. Дополнительные сведения см. в разделе [XML-литералы и спецификация XML 1.0](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md).  
  
## <a name="line-continuation"></a>Продолжение строки  
 XML-литерал может занимать несколько строк без использования символа продолжения строки (последовательность введите пространство-символ подчеркивания). Это упрощает сравнение XML-литералов в коде с помощью XML-документов.  
  
 Компилятор обрабатывает символы продолжения строки как часть XML-литерала. Таким образом, следует использовать последовательность введите пространство подчеркивания только в том случае, если она принадлежит к [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объекта.  
  
 Тем не менее вам нужен символы продолжения строки при наличии многострочного выражения во внедренном выражении. Дополнительные сведения см. в разделе [встроенные выражения в XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
## <a name="embedding-queries-in-xml-literals"></a>Внедрение запросов в XML-литералах  
 Можно использовать запрос во внедренном выражении. При этом элементы, возвращенные запросом добавляются в XML-элемент. Это позволяет добавить динамическое содержимое, например результат запроса пользователя, в XML-литерал.  
  
 Например, следующий код использует внедренный запрос для создания XML-элементов с членами `phoneNumbers2` массива, а затем добавьте эти элементы как дочерние элементы `contact2`.  
  
 [!code-vb[VbXMLSamples#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#7)]  
  
## <a name="how-the-compiler-creates-objects-from-xml-literals"></a>Как компилятор создает объекты из XML-литералов  
 Компилятор Visual Basic преобразует XML-литералы в вызовы в эквивалентную [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] конструкторы для построения [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объекта. Например, компилятор Visual Basic будет преобразовано в следующем примере кода в вызов <xref:System.Xml.Linq.XProcessingInstruction> вызывает конструктор для инструкции XML-версии, чтобы <xref:System.Xml.Linq.XElement> конструктор для `<contact>`, `<name>`, и `<phone>` элементы, а также вызовы <xref:System.Xml.Linq.XAttribute> конструктор для `type` атрибута. В частности, учитывая атрибуты в следующем примере, компилятор Visual Basic будет вызывать <xref:System.Xml.Linq.XAttribute.%23ctor%28System.Xml.Linq.XName%2CSystem.Object%29> конструктора дважды. Первый будут передавать значение `type` для `name` параметр и значение `home` для `value` параметра. Второй также передает значение `type` для `name` параметр, но значение `work` для `value` параметра.  
  
 [!code-vb[VbXMLSamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#6)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Xml.Linq.XElement>
- [Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Встроенные выражения в XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [XML-литерал документа](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [XML-литерал элемента](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [XML-литералы](../../../../visual-basic/language-reference/xml-literals/index.md)
