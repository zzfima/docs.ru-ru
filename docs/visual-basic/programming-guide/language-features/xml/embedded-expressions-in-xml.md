---
title: "Встроенные выражения в XML (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vb.XmlEmbeddedExpression
dev_langs:
- VB
helpviewer_keywords:
- embedded expressions [Visual Basic]
- LINQ to XML [Visual Basic], embedded expressions
- XML literals [Visual Basic], embedded expressions
ms.assetid: bf2eb779-b751-4b7c-854f-9f2161482352
caps.latest.revision: 22
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
ms.openlocfilehash: e5cd40e55ec23de3ad1bb2f5f065762c893d9cb3
ms.lasthandoff: 03/13/2017

---
# <a name="embedded-expressions-in-xml-visual-basic"></a>Встроенные выражения в XML (Visual Basic)
Внедренные выражения позволяют создать XML-литералы, содержащие выражения, которые вычисляются во время выполнения. Синтаксис для встроенных выражений `<%=` `expression` `%>`, который одинаков как синтаксис, используемый в [!INCLUDE[vstecasp](../../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)].  
  
 Например созданием XML-элемента литерал, объединяющий встроенные выражения с содержимым текста.  
  
 [!code-vb[VbXMLSamples&#27;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_1.vb)]  
  
 Если `isbnNumber` содержит целое число 12345 и `modifiedDate` содержит дату 3/5/2006, при выполнении этого кода значение `book` является:  
  
```  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## <a name="embedded-expression-location-and-validation"></a>Расположение встроенного выражения и проверка  
 Встроенные выражения могут располагаться только на определенных местах внутри текстовых XML выражений. Расположение выражения определяет типы выражения значений, которые могут возвращать и как `Nothing` обрабатывается. В следующей таблице описаны разрешенные расположения и типы встроенных выражений.  
  
|Расположение в литерале|Тип выражения|Обработка`Nothing`|  
|---|---|---|  
|Имя XML-элемента|<xref:System.Xml.Linq.XName></xref:System.Xml.Linq.XName>|Ошибка|  
|Содержимое XML-элемента|`Object`или массив`Object`|Не учитывается|  
|Имя атрибута элемента XML|<xref:System.Xml.Linq.XName></xref:System.Xml.Linq.XName>|Ошибка, если значение атрибута не является также`Nothing`|  
|Значение атрибута элемента XML|`Object`|Объявление атрибута игнорируется|  
|Атрибут XML-элемента|<xref:System.Xml.Linq.XAttribute>или коллекции<xref:System.Xml.Linq.XAttribute></xref:System.Xml.Linq.XAttribute></xref:System.Xml.Linq.XAttribute>|Не учитывается|  
|Корневой элемент документа XML|<xref:System.Xml.Linq.XElement>или коллекцию одного <xref:System.Xml.Linq.XElement>объекта и произвольное число <xref:System.Xml.Linq.XProcessingInstruction>и <xref:System.Xml.Linq.XComment>объектов</xref:System.Xml.Linq.XComment> </xref:System.Xml.Linq.XProcessingInstruction> </xref:System.Xml.Linq.XElement></xref:System.Xml.Linq.XElement>|Не учитывается|  
  
-   Пример встроенного выражения в имени элемента XML.  
  
     [!code-vb[VbXMLSamples&#32;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_2.vb)]  
  
-   Пример встроенного выражения в содержимом XML-элемента.  
  
     [!code-vb[VbXMLSamples&#33;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_3.vb)]  
  
-   Пример встроенного выражения в имени атрибута элемента XML.  
  
     [!code-vb[VbXMLSamples&#34;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_4.vb)]  
  
-   Пример встроенного выражения в значении атрибута элемента XML.  
  
     [!code-vb[VbXMLSamples&#35;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_5.vb)]  
  
-   Пример встроенного выражения в атрибуте XML-элемента.  
  
     [!code-vb[VbXMLSamples&#36;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_6.vb)]  
  
-   Пример встроенного выражения в корневом элементе документа XML.  
  
     [!code-vb[VbXMLSamples&#37;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_7.vb)]  
  
 При включении `Option Strict`, компилятор проверяет, что тип каждого встроенного выражения может быть расширен до нужного типа. Единственное исключение — для корневого элемента XML-документа, который проверяется при выполнении кода. Если компиляция выполняется без `Option Strict`, то можно внедрить выражения типа `Object` и их тип будет проверяться во время выполнения.  
  
 В местах, где содержимое является необязательным встроенные выражения, содержащие `Nothing` игнорируются. Это означает, нет необходимости проверять содержимое элемента, значения атрибутов и элементы массива не `Nothing` прежде чем использовать XML-литерал. Необходимые значения, такие как имена элементов и атрибутов, не может быть `Nothing`.  
  
 Дополнительные сведения об использовании встроенного выражения в литерале определенного типа см. в разделе [литерала документа XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [литерала XML элемент](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="scoping-rules"></a>Правила области видимости  
 Компилятор преобразует каждый XML-литерал в вызов конструктора для соответствующего типа литерала. Текстовое содержимое и встроенные выражения в XML-литерале передаются как аргументы в конструктор. Это означает, что все [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] элементы программирования на XML-литерал также доступны для его встроенных выражений.  
  
 В XML-литерал можно использовать пространство имен XML, объявленные префиксы с `Imports` инструкции. Можно объявить новый префикс пространства имен XML или переопределить существующий XML префикс в элементе с помощью `xmlns` атрибута. Новое пространство имен доступно дочерние узлы этого элемента, но не XML-литералов во встроенных выражениях.  
  
> [!NOTE]
>  При объявлении префикса пространства имен XML с помощью `xmlns` пространства имен атрибута, значение атрибута должно быть строковой константы. Таким образом, с помощью `xmlns` атрибут аналогично использованию `Imports` инструкции для объявления пространства имен XML. Нельзя использовать внедренное выражение для указания значения пространства имен XML.  
  
## <a name="see-also"></a>См. также  
 [Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [XML-литерал документа](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)   
 [Литеральное представление XML элемента](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Оператор Imports (пространство имен .NET и тип)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [Общие сведения об XML-литералах](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)
