---
title: "Общие сведения об XML-литералах (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML literals [Visual Basic], about XML literals
- declaring XML literals [Visual Basic]
- LINQ to XML [Visual Basic], XML literals
- literals [Visual Basic], XML
ms.assetid: 37987c15-4ab8-471b-bd45-399816bfb57f
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 59ce79995025692428263120f9c21c7baf5cf231
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="xml-literals-overview-visual-basic"></a>Общие сведения об XML-литералах (Visual Basic)
*XML-литерала* позволяет внедрять XML непосредственно в вашей [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] кода. Синтаксис XML представляет [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объектов, который напоминает синтаксис XML 1.0. Это упрощает программное создание XML-элементов и документов, так как код имеет такую же структуру, как последний XML.  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]Компилирует XML-литералы в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объектов. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]предоставляет простую объектную модель для создания и обработки XML и эта модель тесно интегрируется с [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]. Для получения дополнительной информации см. <xref:System.Xml.Linq.XElement>.  
  
 Можно внедрить [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] выражения в XML-литерал. Во время выполнения приложение создает [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объект для каждого литерала, включая значения внедренных выражений. Это позволяет указывать динамическое содержимое в литералах XML. Дополнительные сведения см. в разделе [встроенные выражения в XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
 Дополнительные сведения о различиях между синтаксис XML-литерала и синтаксис XML 1.0 см. в разделе [XML-литералы и спецификация XML 1.0](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md).  
  
## <a name="simple-literals"></a>Простые литералы  
 Можно создать [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объект в вашей [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] кода, введя или вставив корректный XML. Возвращает литерала элемента XML <xref:System.Xml.Linq.XElement> объекта. Дополнительные сведения см. в разделе [литерала элемента XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) и [XML-литералы и спецификация XML 1.0](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md). В следующем примере создается XML-элемент, который имеет несколько дочерних элементов.  
  
 [!code-vb[VbXMLSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_1.vb)]  
  
 Можно создать XML-документ, запустив литерал XML с `<?xml version="1.0"?>`, как показано в следующем примере. Возвращает XML-литерала документа <xref:System.Xml.Linq.XDocument> объекта. Дополнительные сведения см. в разделе [литерала документа XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).  
  
 [!code-vb[VbXMLSamples#6](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_2.vb)]  
  
> [!NOTE]
>  Синтаксис XML-литерала в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] не идентичен синтаксису спецификации XML 1.0. Дополнительные сведения см. в разделе [XML-литералы и спецификация XML 1.0](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md).  
  
## <a name="line-continuation"></a>Продолжение строки  
 XML-литерал может занимать несколько строк без использования символа продолжения строки (последовательность введите пространства подчеркивания). Это упрощает сравнение XML-литералов в коде с XML-документами.  
  
 Компилятор рассматривает символы продолжения строки как часть XML-литерала. Таким образом, последовательность введите пространства подчеркивания следует использовать только в том случае, если она принадлежит к [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объекта.  
  
 Однако следует соблюдать символы продолжения строки при наличии многострочного выражения во внедренном выражении. Дополнительные сведения см. в разделе [встроенные выражения в XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
## <a name="embedding-queries-in-xml-literals"></a>Встраивание запросов в XML-литералах  
 Можно использовать запрос во внедренном выражении. При этом элементы, возвращенные запросом добавляются в XML-элемент. Это позволяет добавлять в XML-литерал динамическое содержимое, например результат запроса пользователя.  
  
 Например, следующий код использует внедренный запрос для создания XML-элементов из членов `phoneNumbers2` массива и затем добавить эти элементы в качестве дочерних элементов `contact2`.  
  
 [!code-vb[VbXMLSamples#7](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_3.vb)]  
  
## <a name="how-the-compiler-creates-objects-from-xml-literals"></a>Как компилятор создает объекты из XML-литералы  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Компилятор преобразует XML-литералы в вызовы эквивалентных [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] конструкторы для построения [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объекта. Например [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] компилятор преобразует в следующем примере кода в вызов <xref:System.Xml.Linq.XProcessingInstruction> вызовы конструктора для инструкции XML-версии <xref:System.Xml.Linq.XElement> конструктор для `<contact>`, `<name>`и `<phone>`элементов, а также вызовы <xref:System.Xml.Linq.XAttribute> конструктор для `type` атрибута. В частности, учитывая атрибуты в следующем образце [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] компилятор будет вызывать <xref:System.Xml.Linq.XAttribute.%23ctor%28System.Xml.Linq.XName%2CSystem.Object%29> конструктора дважды. Первому передаст значение `type` для `name` параметра и значения `home` для `value` параметра. Второй также передает значение `type` для `name` параметр, но значение `work` для `value` параметра.  
  
 [!code-vb[VbXMLSamples#6](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_2.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Xml.Linq.XElement>  
 [Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [Встроенные выражения в XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)  
 [XML-литерал документа](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)  
 [XML-литерал элемента](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [XML-литералы](../../../../visual-basic/language-reference/xml-literals/index.md)
