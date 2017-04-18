---
title: "Общие сведения о литералах XML (Visual Basic) | Документы Microsoft"
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
helpviewer_keywords:
- XML literals [Visual Basic], about XML literals
- declaring XML literals [Visual Basic]
- LINQ to XML [Visual Basic], XML literals
- literals [Visual Basic], XML
ms.assetid: 37987c15-4ab8-471b-bd45-399816bfb57f
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 57d036910ba9e49385caca28de222a8a8e28ec56
ms.lasthandoff: 03/13/2017

---
# <a name="xml-literals-overview-visual-basic"></a>Общие сведения об XML-литералах (Visual Basic)
*XML-литерал* позволяет внедрять XML непосредственно в ваш [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] кода. Синтаксис литерала XML представляет [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] объектов, который напоминает синтаксис XML 1.0. Это упрощает программное создание XML-элементов и документов, так как ваш код имеет такую же структуру, как окончательный XML.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Компилирует литералы XML в [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] объектов. [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]предоставляет простую объектную модель для создания и управления XML и эта модель хорошо интегрируется с [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)]. Дополнительные сведения см. в разделе <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement>  
  
 Можно внедрить [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] выражения в XML-литерале. Во время выполнения приложение создает [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] объект для каждого литерала, включая значения внедренных выражений. Это позволяет указывать динамическое содержимое в литералах XML. Дополнительные сведения см. в разделе [встроенные выражения в XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
 Дополнительные сведения о различиях между синтаксисом литералов XML и синтаксисом XML 1.0 см. в разделе [XML-литералы и спецификация XML 1.0](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md).  
  
## <a name="simple-literals"></a>Простые литералы  
 Можно создать [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] объекта в своей [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] кода, введя или вставив корректный XML. Возвращает элемент XML литерала <xref:System.Xml.Linq.XElement>объекта.</xref:System.Xml.Linq.XElement> Дополнительные сведения см. в разделе [литерала XML элемент](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) и [XML-литералы и спецификация XML 1.0](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md). В следующем примере создается XML-элемента, который имеет несколько дочерних элементов.  
  
 [!code-vb[VbXMLSamples&#5;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_1.vb)]  
  
 Можно создать XML-документ, запустив литерал XML с `<?xml version="1.0"?>`, как показано в следующем примере. Возвращает литерал XML-документа <xref:System.Xml.Linq.XDocument>объекта.</xref:System.Xml.Linq.XDocument> Дополнительные сведения см. в разделе [литерала XML документ](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).  
  
 [!code-vb[VbXMLSamples №&6;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_2.vb)]  
  
> [!NOTE]
>  Синтаксис XML-литерала в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] не идентичен синтаксису спецификации XML 1.0. Дополнительные сведения см. в разделе [XML-литералы и спецификация XML 1.0](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md).  
  
## <a name="line-continuation"></a>Продолжение строки  
 XML-литерал может занимать несколько строк без использования символа продолжения строки (последовательность пространства введите символ подчеркивания). Это упрощает сравнение XML-литералов в коде с помощью XML-документов.  
  
 Компилятор рассматривает символы продолжения строки как часть XML-литерал. Таким образом, последовательность пространства введите символ подчеркивания следует использовать только в том случае, если она принадлежит к [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] объекта.  
  
 Однако следует соблюдать символы продолжения строки при наличии многострочного выражения во внедренном выражении. Дополнительные сведения см. в разделе [встроенные выражения в XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
## <a name="embedding-queries-in-xml-literals"></a>Внедрение запросов в XML-литералах  
 Можно использовать запрос во внедренном выражении. При этом элементы, возвращенные запросом добавляются в XML-элемент. Это позволяет добавить XML-литерал динамическое содержимое, например результат запроса пользователя.  
  
 Например, следующий код использует внедренный запрос для создания XML-элементов из членов `phoneNumbers2` массива и затем добавьте эти элементы в качестве дочерних элементов `contact2`.  
  
 [!code-vb[VbXMLSamples&#7;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_3.vb)]  
  
## <a name="how-the-compiler-creates-objects-from-xml-literals"></a>Как компилятор создает объекты из XML-литералов  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Компилятор преобразует XML-литералы в вызовы эквивалентных [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] конструкторы для создания [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] объекта. Например [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] компилятор преобразует в следующем примере кода в вызов <xref:System.Xml.Linq.XProcessingInstruction>вызывает конструктор для инструкции XML-версии <xref:System.Xml.Linq.XElement>конструктор для `<contact>`, `<name>`, и `<phone>` элементов и вызовы <xref:System.Xml.Linq.XAttribute>конструктор для `type` атрибут.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XProcessingInstruction> В частности, учитывая атрибуты в следующем примере [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] компилятор вызовет <xref:System.Xml.Linq.XAttribute.%23ctor%28System.Xml.Linq.XName%2CSystem.Object%29>конструктора дважды.</xref:System.Xml.Linq.XAttribute.%23ctor%28System.Xml.Linq.XName%2CSystem.Object%29> Первому передаст значение `type` для `name` параметра и значения `home` для `value` параметр. Второй также передает значение `type` для `name` параметр, но значение `work` для `value` параметр.  
  
 [!code-vb[VbXMLSamples №&6;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_2.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Xml.Linq.XElement>   
 [Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Встроенные выражения в XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)   
 [XML-литерал документа](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)   
 [Литеральное представление XML элемента](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [XML-литералы](../../../../visual-basic/language-reference/xml-literals/index.md)
