---
title: Встроенные выражения в XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlEmbeddedExpression
helpviewer_keywords:
- embedded expressions [Visual Basic]
- LINQ to XML [Visual Basic], embedded expressions
- XML literals [Visual Basic], embedded expressions
ms.assetid: bf2eb779-b751-4b7c-854f-9f2161482352
ms.openlocfilehash: f99735df2512fd4b1477bab9126e18f5afbbfa8c
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932933"
---
# <a name="embedded-expressions-in-xml-visual-basic"></a>Встроенные выражения в XML (Visual Basic)
Внедренные выражения позволяют создавать XML-литералов, которые содержат выражения, которые вычисляются во время выполнения. Для внедренного выражения используется синтаксис `<%=` `expression` `%>`, которая используется, и как синтаксис, используемый в [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)].  
  
 Например созданием XML-элемент литерала, объединяющий встроенные выражения с содержимым текста.  
  
 [!code-vb[VbXMLSamples#27](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_1.vb)]  
  
 Если `isbnNumber` содержит целое число 12345 и `modifiedDate` содержит дату 3/5/2006, при выполнении этого кода значение `book` является:  
  
```xml  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## <a name="embedded-expression-location-and-validation"></a>Расположение внедренного выражения и проверка  
 Внедренные выражения может присутствовать только в определенных местах внутри выражения литералов XML. Расположение выражения определяет типы выражения значений, которые могут возвращать и как `Nothing` обрабатывается. Следующая таблица описывает допустимые расположения и типы встроенных выражений.  
  
|Расположение в литерале|Тип выражения|Обработка `Nothing`|  
|---|---|---|  
|Имя XML-элемента|<xref:System.Xml.Linq.XName>|Error|  
|Содержимое XML-элемента|`Object` или массив `Object`|Не учитывается|  
|Имя атрибута XML-элемента|<xref:System.Xml.Linq.XName>|Ошибка, если также не является значение атрибута `Nothing`|  
|Значение атрибута XML-элемент|`Object`|Объявление атрибута игнорируется|  
|Атрибут XML-элемента|<xref:System.Xml.Linq.XAttribute> или коллекции <xref:System.Xml.Linq.XAttribute>|Не учитывается|  
|Корневой элемент документа XML|<xref:System.Xml.Linq.XElement> или набор из одного элемента <xref:System.Xml.Linq.XElement> объекта и произвольное число <xref:System.Xml.Linq.XProcessingInstruction> и <xref:System.Xml.Linq.XComment> объектов|Не учитывается|  
  
-   Пример встроенного выражения в имя элемента XML.  
  
     [!code-vb[VbXMLSamples#32](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_2.vb)]  
  
-   Пример встроенного выражения в содержимом элемента XML.  
  
     [!code-vb[VbXMLSamples#33](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_3.vb)]  
  
-   Пример встроенного выражения в имя атрибута элемента XML.  
  
     [!code-vb[VbXMLSamples#34](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_4.vb)]  
  
-   Пример встроенного выражения в значении атрибута элемента XML.  
  
     [!code-vb[VbXMLSamples#35](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_5.vb)]  
  
-   Пример встроенного выражения в атрибуте XML-элемента.  
  
     [!code-vb[VbXMLSamples#36](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_6.vb)]  
  
-   Пример встроенного выражения в корневого элемента документа XML.  
  
     [!code-vb[VbXMLSamples#37](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_7.vb)]  
  
 При включении `Option Strict`, компилятор проверяет, что тип каждого внедренного выражения можно расширить до требуемого типа. Единственное исключение — для корневого элемента документа XML, который проверяется при выполнении кода. Если компиляция выполняется без `Option Strict`, можно внедрить выражения типа `Object` и их тип будет проверяться во время выполнения.  
  
 В местах, где содержимое является необязательным встроенные выражения, содержащие `Nothing` игнорируются. Это означает, что нет необходимости проверять содержимое элемента, значения атрибутов и элементы массива не являются `Nothing` прежде чем использовать XML-литерала. Необходимые значения, такие как имена элементов и атрибутов, не могут быть `Nothing`.  
  
 Дополнительные сведения об использовании внедренное выражение в литерале определенного типа см. в разделе [литерала документа XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [литерала элемента XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="scoping-rules"></a>Правила области видимости  
 Компилятор преобразует каждый XML-литерал в вызов конструктора для соответствующего типа литерала. Текстовое содержимое и встроенные выражения в XML-литерала, передаются как аргументы в конструктор. Это означает, что все доступные для XML-литерала элементы программирования Visual Basic, также доступны для его встроенных выражений.  
  
 В XML-литерал, можно использовать пространство имен XML, объявленные префиксы с `Imports` инструкции. Можно объявить новый префикс пространства имен XML, или переопределить существующий префикс пространства имен XML в элементе с помощью `xmlns` атрибута. Новое пространство имен доступно на дочерние узлы данного элемента, но не к XML-литералов в внедренные выражения.  
  
> [!NOTE]
>  При объявлении префикса пространства имен XML с помощью `xmlns` атрибут пространства имен, значение атрибута должно быть строковой константы. Таким образом, с помощью `xmlns` атрибут аналогична использованию `Imports` инструкцию для объявления пространства имен XML. Нельзя использовать внедренное выражение для указания значения пространства имен XML.  
  
## <a name="see-also"></a>См. также  
 [Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [XML-литерал документа](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)  
 [XML-литерал элемента](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [Оператор Imports (пространство имен и тип .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [Общие сведения об XML-литералах](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)
