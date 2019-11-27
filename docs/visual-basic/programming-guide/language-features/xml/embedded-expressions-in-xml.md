---
title: Встроенные выражения в XML
ms.date: 07/20/2015
f1_keywords:
- vb.XmlEmbeddedExpression
helpviewer_keywords:
- embedded expressions [Visual Basic]
- LINQ to XML [Visual Basic], embedded expressions
- XML literals [Visual Basic], embedded expressions
ms.assetid: bf2eb779-b751-4b7c-854f-9f2161482352
ms.openlocfilehash: 0cdb960160457108ddf18c554dae5f5993269833
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74332350"
---
# <a name="embedded-expressions-in-xml-visual-basic"></a>Встроенные выражения в XML (Visual Basic)
Внедренные выражения позволяют создавать XML-литералы, содержащие выражения, вычисляемые во время выполнения. Синтаксис для внедренного выражения `<%=` `expression` `%>`, который совпадает с синтаксисом, используемым в ASP.NET.  
  
 Например, можно создать литерал XML-элемента, объединяющий внедренные выражения с текстовым содержимым.  
  
 [!code-vb[VbXMLSamples#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#27)]  
  
 Если `isbnNumber` содержит целое число 12345, а `modifiedDate` содержит дату 3/5/2006, при выполнении этого кода значение `book` равно:  
  
```xml  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## <a name="embedded-expression-location-and-validation"></a>Расположение и проверка внедренных выражений  
 Встроенные выражения могут использоваться только в определенных местах в выражениях литералов XML. Расположение выражения определяет, какие типы могут возвращать выражение и как обрабатываются `Nothing`. В следующей таблице описаны допустимые расположения и типы внедренных выражений.  
  
|Расположение в литерале|Тип выражения|Обработка `Nothing`|  
|---|---|---|  
|Имя XML-элемента|<xref:System.Xml.Linq.XName>|Ошибка|  
|Содержимое XML-элемента|`Object` или массив `Object`|Не учитывается|  
|Имя атрибута XML-элемента|<xref:System.Xml.Linq.XName>|Ошибка, если значение атрибута также не `Nothing`|  
|Значение атрибута XML-элемента|`Object`|Объявление атрибута пропущено|  
|Атрибут XML-элемента|<xref:System.Xml.Linq.XAttribute> или коллекция <xref:System.Xml.Linq.XAttribute>|Не учитывается|  
|Корневой элемент XML-документа|<xref:System.Xml.Linq.XElement> или коллекция из одного <xref:System.Xml.Linq.XElement> объекта и произвольного числа <xref:System.Xml.Linq.XProcessingInstruction> и объектов <xref:System.Xml.Linq.XComment>|Не учитывается|  
  
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
  
 Если включить `Option Strict`, компилятор проверяет, что тип каждого внедренного выражения расширяется до требуемого типа. Единственным исключением является корневой элемент XML-документа, который проверяется при выполнении кода. При компиляции без `Option Strict`можно внедрять выражения типа `Object` и их тип проверяется во время выполнения.  
  
 В расположениях, где содержимое является необязательным, внедренные выражения, содержащие `Nothing`, игнорируются. Это означает, что не нужно проверять, что содержимое элемента, значения атрибутов и элементы массива не `Nothing`, прежде чем использовать XML-литерал. Обязательные значения, такие как имена элементов и атрибутов, не могут быть `Nothing`.  
  
 Дополнительные сведения об использовании внедренных выражений в определенном типе литерала см. в разделе [литерал XML-документа](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [литерал XML-элемента](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="scoping-rules"></a>Правила области видимости  
 Компилятор преобразует каждый XML-литерал в вызов конструктора для соответствующего типа литерала. Литеральное содержимое и внедренные выражения в XML-литерале передаются в качестве аргументов в конструктор. Это означает, что все элементы программирования Visual Basic, доступные для XML-литерала, также доступны для внедренных выражений.  
  
 В XML-литерале можно получить доступ к префиксам пространства имен XML, объявленным с помощью оператора `Imports`. Можно объявить новый префикс пространства имен XML или затенить существующий префикс пространства имен XML в элементе с помощью атрибута `xmlns`. Новое пространство имен доступно для дочерних узлов этого элемента, но не для XML-литералов во внедренных выражениях.  
  
> [!NOTE]
> При объявлении префикса пространства имен XML с помощью атрибута `xmlns` Namespace значение атрибута должно быть строковой константой. В этом отношении использование атрибута `xmlns` аналогично использованию оператора `Imports` для объявления пространства имен XML. Нельзя использовать внедренное выражение для указания значения пространства имен XML.  
  
## <a name="see-also"></a>См. также

- [Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [XML-литерал документа](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [XML-литерал элемента](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Оператор Imports (пространство имен и тип .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Общие сведения об XML-литералах](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)
