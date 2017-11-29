---
title: "Литеральное представление XML-элемента (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.XmlLiteralElement
helpviewer_keywords:
- XML element literal [Visual Basic]
- element literal [Visual Basic]
- XML literals [Visual Basic], element
ms.assetid: 95039642-7893-48b7-b23f-45a6c55d8f67
caps.latest.revision: "32"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: de5825a6af1dd1b93c3c85651125cf817dc564f2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="xml-element-literal-visual-basic"></a>Литеральное представление XML-элемента (Visual Basic)

Литерал, представляющий <xref:System.Xml.Linq.XElement> объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<name [ attributeList ] />  
-or-  
<name [ attributeList ] > [ elementContents ] </[ name ]>  
```  
  
## <a name="parts"></a>Части  
  
-   `<`  
  
     Обязательный. Открывает начальный тег элемента.  
  
-   `name`  
  
     Обязательный. Имя элемента. Имеет одно из следующих:  
  
    -   Литеральный текст для имени элемента формы `[ePrefix:]eName`, где:  
  
        |Отделение|Описание|  
        |---|---|  
        |`ePrefix`|Необязательно. Префикс пространства имен XML для элемента. Должно быть глобальным пространством имен XML, который определен с `Imports` инструкции в файле или на уровне проекта или локальным пространством имен XML, определенные в этом элементе или родительском элементе.|  
        |`eName`|Обязательный. Имя элемента. Имеет одно из следующих:<br /><br /> -Текст. В разделе [имена объявленных элементов и атрибутов](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).<br />-Встроенные выражения формы `<%= eNameExp %>`. Тип `eNameExp` должно быть `String` или тип, который неявно преобразуется в <xref:System.Xml.Linq.XName>.|  
  
    -   Встроенные выражения формы `<%= nameExp %>`. Тип `nameExp` должно быть `String` или неявно преобразовываться в тип <xref:System.Xml.Linq.XName>. Внедренное выражение не допускается в закрывающего тега элемента.  
  
-   `attributeList`  
  
     Необязательно. Список атрибутов, объявленных в литерале.  
  
     `attribute [ attribute ... ]`  
  
     Каждый `attribute` имеет одно из следующих вариантов синтаксиса:  
  
    -   Атрибут назначения формы `[aPrefix:]aName=aValue`, где:  
  
        |Отделение|Описание|  
        |---|---|  
        |`aPrefix`|Необязательно. Префикс пространства имен XML для атрибута. Должно быть глобальным пространством имен XML, который определен с `Imports` инструкции или локальным пространством имен XML, определенные в этом элементе или родительском элементе.|  
        |`aName`|Обязательный. Имя атрибута. Имеет одно из следующих:<br /><br /> -Текст. В разделе [имена объявленных элементов и атрибутов](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).<br />-Встроенные выражения формы `<%= aNameExp %>`. Тип `aNameExp` должно быть `String` или тип, который неявно преобразуется в <xref:System.Xml.Linq.XName>.|  
        |`aValue`|Необязательно. Значение атрибута. Имеет одно из следующих:<br /><br /> -Литеральный текст, заключенный в кавычки.<br />-Встроенные выражения формы `<%= aValueExp %>`. Допустим любой тип.|  
  
    -   Встроенные выражения формы `<%= aExp %>`.  
  
-   `/>`  
  
     Необязательно. Указывает, что элемент является пустым элементом без содержимого.  
  
-   `>`  
  
     Обязательный. Завершает начальный или пустым тегом элемента.  
  
-   `elementContents`  
  
     Необязательно. Содержимое элемента.  
  
     `content [ content ... ]`  
  
     Каждый `content` может принимать одно из следующих действий:  
  
    -   Литеральный текст. Все пробелы в `elementContents` становится значимыми, если любой текст.  
  
    -   Встроенные выражения формы `<%= contentExp %>`.  
  
    -   Литерала элемента XML.  
  
    -   XML-литерал комментария. В разделе [XML-литерал комментария](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).  
  
    -   Литерал инструкции обработки XML. В разделе [литерал инструкции обработки XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).  
  
    -   Литерала CDATA XML. В разделе [XML-литерала CDATA](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).  
  
-   `</[name]>`  
  
     Необязательно. Представляет закрывающий тег для элемента. Необязательный `name` параметра не допускается, когда он является результатом встроенного выражения.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект <xref:System.Xml.Linq.XElement>.  
  
## <a name="remarks"></a>Примечания  
 Синтаксис элемента XML можно использовать для создания <xref:System.Xml.Linq.XElement> объектов в коде.  
  
> [!NOTE]
>  XML-литерал может занимать несколько строк без использования символа продолжения строки. Эта функция позволяет скопировать содержимое из XML-документа и вставьте его непосредственно в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] программы.  
  
 Встроенные выражения формы `<%= exp %>` позволяют добавлять динамические сведения для литерала XML-элемента. Дополнительные сведения см. в разделе [встроенные выражения в XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Компилятор преобразует литерала XML-элемента в вызовы <xref:System.Xml.Linq.XElement.%23ctor%2A> конструктора и, при необходимости, <xref:System.Xml.Linq.XAttribute.%23ctor%2A> конструктор.  
  
## <a name="xml-namespaces"></a>Пространства имен XML  
 Префиксы пространства имен XML полезны в тех случаях, когда необходимо создать XML-литералы с элементами одного пространства имен, сколько раз в коде. Можно использовать глобальные префиксы пространства имен XML, которые можно определить с помощью `Imports` инструкции или локальные префиксы, которые определяются с помощью `xmlns:xmlPrefix="xmlNamespace"` синтаксис атрибута. Дополнительные сведения см. в разделе [оператор Imports (пространство имен XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
 В соответствии с правилами обзора данных для пространства имен XML локальные префиксы имеют приоритет над глобальные префиксы. Тем не менее, если XML-литерал определяет пространство имен XML, что пространство имен недоступно для выражений, отображаемых во внедренном выражении. Внедренное выражение доступны только глобального пространства имен XML.  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Компилятор преобразует каждый глобального пространства имен XML, который используется XML-литерал в одно определение Локальное пространство имен в созданном коде. Глобальные пространства имен XML, которые не используются не отображаются в созданном коде.  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется создание простой XML-элемент, который имеет два вложенных элемента пустой.  
  
 [!code-vb[VbXMLSamples#20](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_1.vb)]  
  
 В примере отображается следующий текст. Обратите внимание, что литерал сохраняет структуру пустые элементы.  
  
```xml  
<outer>  
  <inner1></inner1>  
  <inner2 />  
</outer>  
```  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать внедренные выражения для имени элемента и создать атрибуты.  
  
 [!code-vb[VbXMLSamples#21](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_2.vb)]  
  
 Этот пример кода отображает следующий текст:  
  
```xml  
<book isbn="1234" author="My Author" year="1999" title="My Book" />  
```  
  
## <a name="example"></a>Пример  
 В следующем примере `ns` объявляется как префикс пространства имен XML. Затем используется префикс пространства имен для создания литерала XML и отображается конечная форма элемента.  
  
 [!code-vb[VbXMLSamples#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_3.vb)]  
  
 Этот пример кода отображает следующий текст:  
  
```xml  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 Обратите внимание, что компилятор преобразует префикс глобального пространства имен XML в определение префикса для пространства имен XML. \<Ns:middle > элемент переопределяет префикс пространства имен XML для \<ns:inner1 > элемент. Тем не менее \<ns:inner2 > элемент использует пространства имен, определенного в `Imports` инструкции.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Xml.Linq.XElement>  
 [Имена объявленных элементов и атрибутов XML](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)  
 [XML-литерал комментария](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)  
 [XML-литерал CDATA](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)  
 [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md)  
 [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [Встроенные выражения в XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)  
 [Оператор Imports (пространство имен XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
