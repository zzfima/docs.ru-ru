---
title: "Встроенные выражения в XML (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.XmlEmbeddedExpression"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "встроенные выражения [Visual Basic]"
  - "LINQ to XML [Visual Basic], встроенные выражения"
  - "XML-литералы [Visual Basic], встроенные выражения"
ms.assetid: bf2eb779-b751-4b7c-854f-9f2161482352
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Встроенные выражения в XML (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Встроенные выражения позволяют создать XML\-литералы, содержащие выражения, которые вычисляются во время выполнения.  Синтаксис для встроенных выражений следующий: `<%=` `expression` `%>`, который совпадает с синтаксисом, используемым в [!INCLUDE[vstecasp](../../../../csharp/language-reference/preprocessor-directives/includes/vstecasp-md.md)].  
  
 Например, можно создать XML\-литерал, объединяющий встроенные выражения с содержимым текста.  
  
 [!code-vb[VbXMLSamples#27](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/embedded-expressions-in-_1.vb)]  
  
 Если `isbnNumber` содержит целое число 12345, а `modifiedDate` содержит дату "05.03.2006", то при выполнении этого кода значение `book` будет:  
  
```  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## Расположение и проверка встроенных выражений  
 Встроенные выражения могут располагаться только на определенных местах внутри текстовых XML выражений.  Расположение выражения определяет типы значений, которые могут возвращать выражения, и порядок обработки ключевого слова `Nothing`.  В следующей таблице предоставлены разрешенные расположения и типы встроенных выражений.  
  
||||  
|-|-|-|  
|Расположение в литерале|Тип выражения|Обработка `Nothing`|  
|Имя XML\-элемента|<xref:System.Xml.Linq.XName>|Ошибка|  
|Содержимое XML\-элемента|Элемент `Object` или массив элементов `Object`|Игнорируется|  
|Имя атрибута XML\-элемента|<xref:System.Xml.Linq.XName>|Ошибка, если значение атрибута не является также `Nothing`|  
|Значение атрибута XML\-элемента|`Object`|Объявление атрибута игнорируется|  
|Атрибут XML\-элемента|Объект класса <xref:System.Xml.Linq.XAttribute> или коллекция объектов <xref:System.Xml.Linq.XAttribute>|Игнорируется|  
|Корневой элемент XML\-документа|Объект класса <xref:System.Xml.Linq.XElement> или коллекция из одного объекта класса <xref:System.Xml.Linq.XElement> и произвольного числа объектов класса <xref:System.Xml.Linq.XProcessingInstruction> и <xref:System.Xml.Linq.XComment>|Игнорируется|  
  
-   Пример встроенного выражения в имени XML\-элемента:  
  
     [!code-vb[VbXMLSamples#32](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/embedded-expressions-in-_2.vb)]  
  
-   Пример встроенного выражения в содержимом XML\-элемента:  
  
     [!code-vb[VbXMLSamples#33](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/embedded-expressions-in-_3.vb)]  
  
-   Пример встроенного выражения в имени атрибута XML\-элемента:  
  
     [!code-vb[VbXMLSamples#34](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/embedded-expressions-in-_4.vb)]  
  
-   Пример встроенного выражения в значении атрибута XML\-элемента:  
  
     [!code-vb[VbXMLSamples#35](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/embedded-expressions-in-_5.vb)]  
  
-   Пример встроенного выражения в атрибуте XML\-элемента:  
  
     [!code-vb[VbXMLSamples#36](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/embedded-expressions-in-_6.vb)]  
  
-   Пример встроенного выражения в корневом элементе XML\-документа:  
  
     [!code-vb[VbXMLSamples#37](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/embedded-expressions-in-_7.vb)]  
  
 Если разрешено использование ключевого слова `Option Strict`, то компилятор проверяет, можно ли расширить тип каждого встроенного выражения до требуемого типа.  Единственным исключением является корневой элемент XML\-документа, который проверяется при выполнении кода.  Если выполнить компиляцию без ключевого слова `Option Strict`, то можно внедрить выражения типа `Object`, и их тип будет проверяться во время выполнения.  
  
 В местах, где содержимое является необязательным, встроенные выражения, содержащие `Nothing`, игнорируются.  Это означает, что перед использованием XML\-литерала можно не проверять содержимое элемента, значения атрибутов и элементы массива, которые не содержат значения `Nothing`.  Необходимые значения, такие как имена элементов и атрибутов, не могут быть `Nothing`.  
  
 Дополнительные сведения об использовании встроенного выражения в литерале определенного типа см. в разделе [XML\-литерал документа](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [Литеральное представление XML\-элемента](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## Правила обзора данных  
 Компилятор преобразует каждый XML\-литерал в вызов конструктора для соответствующего типа литерала.  Компилятор преобразует каждый XML\-литерал в вызов конструктора для соответствующего типа литерала.  Это означает, что все элементы программирования [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], доступные для XML\-литерала, также доступны для его встроенных выражений.  
  
 В XML\-литерале можно использовать префиксы пространства имен XML, объявляемые с помощью инструкции `Imports`.  Можно объявить новый префикс пространства имен XML или переопределить существующий XML\-префикс в элементе с помощью атрибута `xmlns`.  Новое пространство имен является доступным для дочерних узлов таких элементов, но не для XML\-литералов во встроенных выражениях.  
  
> [!NOTE]
>  При объявлении префикса пространства имен XML с помощью атрибута пространства имен `xmlns` значение атрибута должно быть константной строкой.  В этом смысле, использование атрибута `xmlns` аналогично использованию инструкции `Imports` для объявления пространства имен XML.  Встроенные выражения нельзя использовать для указания значения пространства имен XML.  
  
## См. также  
 [Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [XML\-литерал документа](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)   
 [Литеральное представление XML\-элемента](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Оператор Imports \(пространство имен .NET и тип\)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [Общие сведения об XML\-литералах](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)