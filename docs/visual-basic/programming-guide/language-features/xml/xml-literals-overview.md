---
title: "Общие сведения об XML-литералах (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "объявление XML-литералов [Visual Basic]"
  - "LINQ to XML [Visual Basic], XML-литералы"
  - "литералы [Visual Basic], XML"
  - "XML-литералы [Visual Basic], сведения о XML-литералах"
ms.assetid: 37987c15-4ab8-471b-bd45-399816bfb57f
caps.latest.revision: 27
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 27
---
# Общие сведения об XML-литералах (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

*Литерал XML* позволяет внедрять XML непосредственно в код [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]. Синтаксис литерала XML представляет объекты [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)] и подобен синтаксису XML 1.0. Это упрощает программное создание XML\-элементов и документов, так как код имеет такую же структуру, как окончательный XML.  
  
 При компиляции [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] превращает литералы XML в объекты [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)].  [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)] предоставляет простую объектную модель создания и управления XML. Эта модель хорошо интегрируется с [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext-md.md)].  Дополнительные сведения см. в разделе <xref:System.Xml.Linq.XElement>.  
  
 Можно внедрить выражение [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] в литерал XML.  Во время выполнения приложение создает объект [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)] для каждого литерала, включая значения внедренных выражений.  Это позволяет указывать динамическое содержимое в литералах XML.  Дополнительные сведения см. в разделе [Встроенные выражения в XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
 Дополнительные сведения о различиях между синтаксисом литералов XML и синтаксисом XML 1.0 см. в разделе [XML\-литералы и спецификация XML 1.0](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md).  
  
## Простые литералы  
 Можно создать объект [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)] в коде [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], введя или вставив корректный XML.  Литерал XML\-элемента возвращает объект <xref:System.Xml.Linq.XElement>.  Дополнительные сведения см. в разделах [Литеральное представление XML\-элемента](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) и [XML\-литералы и спецификация XML 1.0](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md).  В следующем примере создается XML\-элемент, который имеет несколько дочерних элементов.  
  
 [!code-vb[VbXMLSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_1.vb)]  
  
 Можно создать XML\-документ, запустив литерал XML с `<?xml version="1.0"?>`, как показано в следующем примере.  Литерал XML\-документа возвращает объект <xref:System.Xml.Linq.XDocument>.  Дополнительные сведения см. в разделе [XML\-литерал документа](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).  
  
 [!code-vb[VbXMLSamples#6](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_2.vb)]  
  
> [!NOTE]
>  Синтаксис XML\-литерала в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] не идентичен синтаксису спецификации XML 1.0.  Дополнительные сведения см. в разделе [XML\-литералы и спецификация XML 1.0](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md).  
  
## Продолжение строки  
 XML\-литерал может занимать несколько строк без использования символа продолжения строки \(последовательность пробел\-символ подчеркивания\-возврат каретки\).  Это упрощает сравнение XML\-литералов в коде с помощью XML\-документов.  
  
 Компилятор рассматривает символы продолжения строки как часть XML\-литерала.  Поэтому следует использовать последовательность \(пробел\-символ подчеркивания\-возврат каретки\), только если она принадлежит к объекту [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)].  
  
 Тем не менее, символы продолжения строки все\-таки нужны при наличии многострочного выражения во внедренном выражении.  Дополнительные сведения см. в разделе [Встроенные выражения в XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
## Внедрение запросов в XML\-литералы  
 Можно использовать запрос во внедренном выражении.  При этом элементы, возвращенные запросом, добавляются к XML\-элементу.  Это позволяет добавлять в XML\-литерал динамическое содержимое, такое как результат пользовательского запроса.  
  
 Например, следующий код использует внедренный запрос для создания XML\-элементов из членов массива `phoneNumbers2` и добавления их затем как дочерних узлов `contact2`.  
  
 [!code-vb[VbXMLSamples#7](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_3.vb)]  
  
## Создание компилятором объектов из XML\-литералов  
 Компилятор [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] преобразует литералы XML в вызовы эквивалентных конструкторов [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)] для создания объекта [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)].  Например, компилятор [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] преобразует следующий пример кода в вызов конструктора <xref:System.Xml.Linq.XProcessingInstruction> для инструкции XML\-версии, вызовы конструктора <xref:System.Xml.Linq.XElement> для элементов `<contact>`, `<name>` и `<phone>`, и вызовы конструктора <xref:System.Xml.Linq.XAttribute> для атрибута `type`.  В частности, при атрибутах из следующего примера компилятор [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] вызовет конструктор <xref:System.Xml.Linq.XAttribute.%23ctor%28System.Xml.Linq.XName%2CSystem.Object%29> дважды.  Первому передаст значение `type` в качестве параметра `name` и значение `home` в качестве параметра `value`.  Второму также передаст значение `type` в качестве параметра `name`, но в качестве параметра `value` будет значение `work`.  
  
 [!code-vb[VbXMLSamples#6](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_2.vb)]  
  
## См. также  
 <xref:System.Xml.Linq.XElement>   
 [Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Встроенные выражения в XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)   
 [XML\-литерал документа](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)   
 [Литеральное представление XML\-элемента](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [XML\-литералы](../../../../visual-basic/language-reference/xml-literals/index.md)