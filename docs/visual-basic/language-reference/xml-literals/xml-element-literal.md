---
title: Литеральное представление XML-элемента (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralElement
helpviewer_keywords:
- XML element literal [Visual Basic]
- element literal [Visual Basic]
- XML literals [Visual Basic], element
ms.assetid: 95039642-7893-48b7-b23f-45a6c55d8f67
ms.openlocfilehash: 54ad162a1a720a1645a3b413e6518d2ccfd37bbe
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54595920"
---
# <a name="xml-element-literal-visual-basic"></a>Литеральное представление XML-элемента (Visual Basic)

Литералом, представляющим <xref:System.Xml.Linq.XElement> объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<name [ attributeList ] />  
-or-  
<name [ attributeList ] > [ elementContents ] </[ name ]>  
```  
  
## <a name="parts"></a>Части  
  
-   `<`  
  
     Обязательный. Откроется начальный тег элемента.  
  
-   `name`  
  
     Обязательный. Имя элемента. Одно из следующих имеет следующий формат:  
  
    -   Литеральный текст для имени элемента формы `[ePrefix:]eName`, где:  
  
        |Отделение|Описание:|  
        |---|---|  
        |`ePrefix`|Необязательный параметр. Префикс пространства имен XML для элемента. Должно быть глобальным пространством имен XML, который определен с помощью `Imports` инструкции в файле или на уровне проекта или локальное пространство имен XML, который определен в этом элементе или родительском элементе.|  
        |`eName`|Обязательный. Имя элемента. Одно из следующих имеет следующий формат:<br /><br /> -Литеральный текст. См. в разделе [имена объявленных элементов и атрибутов](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).<br />-Внедренные выражения вида `<%= eNameExp %>`. Тип `eNameExp` должно быть `String` или типом, который неявно преобразуется к типу <xref:System.Xml.Linq.XName>.|  
  
    -   Внедренные выражения вида `<%= nameExp %>`. Тип `nameExp` должно быть `String` или неявно преобразовываться в тип <xref:System.Xml.Linq.XName>. Внедренное выражение не допускается в закрывающий тег элемента.  
  
-   `attributeList`  
  
     Необязательный параметр. Список атрибутов, объявленных в литерале.  
  
     `attribute [ attribute ... ]`  
  
     Каждый `attribute` имеет одно из следующих вариантов синтаксиса:  
  
    -   Назначение формы атрибутов `[aPrefix:]aName=aValue`, где:  
  
        |Отделение|Описание|  
        |---|---|  
        |`aPrefix`|Необязательный параметр. Префикс пространства имен XML для атрибута. Должно быть глобальным пространством имен XML, который определен с помощью `Imports` инструкции или локальное пространство имен XML, который определен в этом элементе или родительском элементе.|  
        |`aName`|Обязательный. Имя атрибута. Одно из следующих имеет следующий формат:<br /><br /> -Литеральный текст. См. в разделе [имена объявленных элементов и атрибутов](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).<br />-Внедренные выражения вида `<%= aNameExp %>`. Тип `aNameExp` должно быть `String` или типом, который неявно преобразуется к типу <xref:System.Xml.Linq.XName>.|  
        |`aValue`|Необязательный параметр. Значение атрибута. Одно из следующих имеет следующий формат:<br /><br /> -Литеральный текст, заключенный в кавычки.<br />-Внедренные выражения вида `<%= aValueExp %>`. Допустим любой тип.|  
  
    -   Внедренные выражения вида `<%= aExp %>`.  
  
-   `/>`  
  
     Необязательный параметр. Указывает, что элемент является пустым элементом, без содержимого.  
  
-   `>`  
  
     Обязательный. Завершает начиная или пустым тегом элемента.  
  
-   `elementContents`  
  
     Необязательный параметр. Содержимое элемента.  
  
     `content [ content ... ]`  
  
     Каждый `content` может принимать одно из следующих:  
  
    -   Литеральный текст. Все пробелы в `elementContents` становится значимыми, если любой текст.  
  
    -   Внедренные выражения вида `<%= contentExp %>`.  
  
    -   Литерала элемента XML.  
  
    -   XML-литерал комментария. См. в разделе [XML-литерал комментария](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).  
  
    -   Литерал инструкции обработки XML. См. в разделе [литерал инструкции обработки XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).  
  
    -   Литерал CDATA XML. См. в разделе [XML-литерале CDATA](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).  
  
-   `</[name]>`  
  
     Необязательный параметр. Представляет закрывающий тег для элемента. Необязательный `name` параметра не допускается, если она является результатом встроенного выражения.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект <xref:System.Xml.Linq.XElement>.  
  
## <a name="remarks"></a>Примечания  
 Синтаксис элемента XML можно использовать для создания <xref:System.Xml.Linq.XElement> объектов в коде.  
  
> [!NOTE]
>  XML-литерал может занимать несколько строк без использования символа продолжения строки. Эта функция позволяет скопировать содержимое из XML-документа и вставьте его непосредственно в программу Visual Basic.  
  
 Встроенные выражения формы `<%= exp %>` позволяют добавить динамические сведения в литерале XML-элемента. Дополнительные сведения см. в разделе [встроенные выражения в XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
 Компилятор Visual Basic преобразует литерала XML-элемента в вызовы <xref:System.Xml.Linq.XElement.%23ctor%2A> конструктор и, при необходимости, <xref:System.Xml.Linq.XAttribute.%23ctor%2A> конструктор.  
  
## <a name="xml-namespaces"></a>Пространства имен XML  
 Префиксы пространства имен XML полезны в тех случаях, когда необходимо создать XML-литералов с элементами одного пространства имен много раз в коде. Можно использовать глобальные префиксы пространства имен XML, которые определяются с помощью `Imports` инструкции или локальные префиксы, которые определяются с помощью `xmlns:xmlPrefix="xmlNamespace"` синтаксис атрибута. Дополнительные сведения см. в разделе [оператор Imports (пространство имен XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
 В соответствии с правилами обзора данных для пространств имен XML локальные префиксы имеют приоритет над глобальные префиксы. Тем не менее, если XML-литерал определяет пространство имен XML, что пространство имен недоступно для выражения, которые встречаются во внедренном выражении. Внедренное выражение доступен только глобальным пространством имен XML.  
  
 Компилятор Visual Basic преобразует каждый глобального пространства имен XML, который используется XML-литерала в одно определение Локальное пространство имен в созданном коде. Глобальные пространства имен XML, которые не используются не отображаются в созданном коде.  
  
## <a name="example"></a>Пример  
 Приведенный ниже показано, как создать простой XML-элемент, который имеет два вложенных пустых элементов.  
  
 [!code-vb[VbXMLSamples#20](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_1.vb)]  
  
 В примере отображается следующий текст. Обратите внимание на то, что литерал сохраняет структуру пустых элементов.  
  
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
 В следующем примере `ns` объявляется как префикс пространства имен XML. Затем используется префикс пространства имен для создания литерала XML и отображает окончательной форме этого элемента.  
  
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
  
 Обратите внимание на то, что компилятор преобразует префикса глобального пространства имен XML в определении префикса пространства имен XML. \<Ns:middle > элемент переопределяет префикс пространства имен XML для \<ns:inner1 > элемента. Тем не менее \<ns:inner2 > элемент использует пространство имен, определенное `Imports` инструкции.  
  
## <a name="see-also"></a>См. также
- <xref:System.Xml.Linq.XElement>
- [Имена объявленных элементов и атрибутов XML](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [XML-литерал комментария](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)
- [XML-литерал CDATA](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)
- [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md)
- [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Встроенные выражения в XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [Оператор Imports (пространство имен XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
