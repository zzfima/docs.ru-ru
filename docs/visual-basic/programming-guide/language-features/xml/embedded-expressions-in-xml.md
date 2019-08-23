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
ms.openlocfilehash: 525fa04db86a299d88e1612aac76d014f35124eb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69922620"
---
# <a name="embedded-expressions-in-xml-visual-basic"></a>Встроенные выражения в XML (Visual Basic)
Внедренные выражения позволяют создавать XML-литералы, содержащие выражения, вычисляемые во время выполнения. Синтаксис для внедренного выражения — `<%=` `expression` `%>`это то же, что и синтаксис, используемый в ASP.NET.  
  
 Например, можно создать литерал XML-элемента, объединяющий внедренные выражения с текстовым содержимым.  
  
 [!code-vb[VbXMLSamples#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#27)]  
  
 Если `isbnNumber` содержит целое число 12345 `modifiedDate` и содержит дату 3/5/2006, то при выполнении этого кода значение `book` равно:  
  
```xml  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## <a name="embedded-expression-location-and-validation"></a>Расположение и проверка внедренных выражений  
 Встроенные выражения могут использоваться только в определенных местах в выражениях литералов XML. Расположение выражения определяет, какие типы могут быть возвращены выражением `Nothing` и как обрабатывается. В следующей таблице описаны допустимые расположения и типы внедренных выражений.  
  
|Расположение в литерале|Тип выражения|Обработка`Nothing`|  
|---|---|---|  
|Имя XML-элемента|<xref:System.Xml.Linq.XName>|Error|  
|Содержимое XML-элемента|`Object`или массив`Object`|Не учитывается|  
|Имя атрибута XML-элемента|<xref:System.Xml.Linq.XName>|Ошибка, если значение атрибута также не равно`Nothing`|  
|Значение атрибута XML-элемента|`Object`|Объявление атрибута пропущено|  
|Атрибут XML-элемента|<xref:System.Xml.Linq.XAttribute>или коллекция<xref:System.Xml.Linq.XAttribute>|Не учитывается|  
|Корневой элемент XML-документа|<xref:System.Xml.Linq.XElement>или коллекция из одного <xref:System.Xml.Linq.XElement> объекта и произвольное <xref:System.Xml.Linq.XProcessingInstruction> число объектов и <xref:System.Xml.Linq.XComment>|Не учитывается|  
  
- Пример внедренного выражения в имени XML-элемента:  
  
     [!code-vb[VbXMLSamples#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#32)]  
  
- Пример внедренного выражения в содержимом XML-элемента:  
  
     [!code-vb[VbXMLSamples#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#33)]  
  
- Пример внедренного выражения в имени атрибута XML-элемента:  
  
     [!code-vb[VbXMLSamples#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#34)]  
  
- Пример внедренного выражения в значении атрибута XML-элемента:  
  
     [!code-vb[VbXMLSamples#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#35)]  
  
- Пример внедренного выражения в атрибуте XML-элемента:  
  
     [!code-vb[VbXMLSamples#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#36)]  
  
- Пример внедренного выражения в корневом элементе XML-документа:  
  
     [!code-vb[VbXMLSamples#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#37)]  
  
 Если включить `Option Strict`, компилятор проверяет, что тип каждого внедренного выражения расширяется до требуемого типа. Единственным исключением является корневой элемент XML-документа, который проверяется при выполнении кода. При компиляции без `Option Strict`можно внедрить выражения типа `Object` и их тип проверяется во время выполнения.  
  
 В расположениях, где содержимое является необязательным, внедренные выражения, содержащие `Nothing` , игнорируются. Это означает, что нет необходимости проверять содержимое элемента, значения атрибутов и элементы `Nothing` массива перед использованием XML-литерала. Обязательные значения, такие как имена элементов и атрибутов, не `Nothing`могут иметь значение.  
  
 Дополнительные сведения об использовании внедренных выражений в определенном типе литерала см. в разделе [литерал XML-документа](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [литерал XML-элемента](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="scoping-rules"></a>Правила области видимости  
 Компилятор преобразует каждый XML-литерал в вызов конструктора для соответствующего типа литерала. Литеральное содержимое и внедренные выражения в XML-литерале передаются в качестве аргументов в конструктор. Это означает, что все элементы программирования Visual Basic, доступные для XML-литерала, также доступны для внедренных выражений.  
  
 В XML-литерале можно получить доступ к префиксам пространства имен XML, объявленным с помощью `Imports` инструкции. Можно объявить новый префикс пространства имен XML или затенить существующий префикс пространства имен XML в элементе с помощью `xmlns` атрибута. Новое пространство имен доступно для дочерних узлов этого элемента, но не для XML-литералов во внедренных выражениях.  
  
> [!NOTE]
> При объявлении префикса пространства имен XML с помощью `xmlns` атрибута Namespace значение атрибута должно быть строковой константой. В этом отношении использование `xmlns` атрибута аналогично `Imports` использованию оператора для объявления пространства имен XML. Нельзя использовать внедренное выражение для указания значения пространства имен XML.  
  
## <a name="see-also"></a>См. также

- [Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [XML-литерал документа](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [XML-литерал элемента](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Оператор Imports (пространство имен и тип .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Общие сведения об XML-литералах](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)
