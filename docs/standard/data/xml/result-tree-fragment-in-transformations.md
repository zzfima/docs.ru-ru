---
title: Фрагмент дерева результатов в преобразованиях
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: df363480-ba02-4233-9ddf-8434e421c4f1
ms.openlocfilehash: e454c1194e8c280042857f106e22d0d0509417e3
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156365"
---
# <a name="result-tree-fragment-in-transformations"></a>Фрагмент дерева результатов в преобразованиях

> [!NOTE]
> Класс <xref:System.Xml.Xsl.XslTransform> явлется устаревшим в версии .NET Framework 2.0. Можно выполнять XSLT-преобразование, используя класс <xref:System.Xml.Xsl.XslCompiledTransform>. См. дополнительные сведения об [использовании класса XslCompiledTransform](using-the-xslcompiledtransform-class.md) и [миграции из класса XslTransform](migrating-from-the-xsltransform-class.md).

 Фрагменты результирующего дерева представляют собой особый тип набора узлов. С ними можно выполнять любое действие, которое можно выполнять с набором узлов. Также можно преобразовать фрагмент результирующего дерева в набор узлов с помощью функции `node-set()` и далее использовать его в любом месте, где можно использовать набор узлов.

 Фрагмент результирующего дерева создается в результате применения элемента `<xsl:variable>` или `<xsl:param>` особым образом в таблице стилей. Для элементов `variable` и `parameter` используется следующий синтаксис:

```xml
<xsl:param name=Qname select= XPath Expression >
    template body
</xsl:param>

<xsl:variable name=Qname select=XPath Expression >
    template body
</xsl:variable>
```

Для элемента `parameter` существует несколько способов задания значения для полного имени (`Qname`). Можно назначить значение по умолчанию для параметра, возвратив содержимое из выражения XPath в атрибуте `select` или присвоив ему содержимое текста шаблона.

Для элемента `variable` также существует несколько способов задания значения. Можно задать его, возвратив содержимое из выражения XPath в атрибуте `select` или присвоив ему содержимое текста шаблона.

Если значение для элемента `parameter` или `variable` присваивается с помощью выражения XPath, будет возвращен один из четырех основных типов XPath: логический, строковый, числовой или набор узлов. Если значение задается с помощью непустого текста шаблона, то возвращается тип данных, который отличается от типов данных XPath и представляет собой фрагмент результирующего дерева.

Если переменная привязана к фрагменту результирующего дерева, а не к одному из четырех основных типов данных XPath, то это единственный случай, когда запрос XPath возвращает тип, отличный от четырех типов объектов XPath. Фрагменты результирующего дерева и аспекты их работы описаны в [спецификации консорциума W3C](https://www.w3.org/TR/xslt-10/), в разделах с [11.1 Result Tree Fragments](https://www.w3.org/TR/xslt-10/#section-Result-Tree-Fragments) (Фрагменты результирующего дерева) по [11.6 Passing Parameters to Templates](https://www.w3.org/TR/xslt-10/#section-Passing-Parameters-to-Templates) (Передача параметров в шаблоны). Кроме того, в разделе [1 Introduction](https://www.w3.org/TR/xslt-10/#section-Introduction) (Введение) описано, каким образом шаблоны могут содержать элементы из пространства имен XSLT, которые возвращают или создают фрагменты результирующего дерева.

Сам по себе фрагмент результирующего дерева представляет собой набор узлов с единственным корневым узлом. Однако остальные возвращаемые узлы являются дочерними. Чтобы отобразить дочерние узлы программным образом, скопируйте фрагмент результирующего дерева в результирующее дерево с помощью элемента `<xsl:copy-of>`. Во время выполнения элемента copy-of все дочерние узлы также последовательно копируются в результирующее дерево. До использования элемента `copy` или `copy-of` фрагмент результирующего дерева не является частью результирующего дерева или выходных данных преобразования.

Чтобы пройти по возвращаемым узлам фрагмента результирующего дерева используется объект <xref:System.Xml.XPath.XPathNavigator>. В следующем образце кода показано, как создать фрагмент результирующего дерева в таблице стилей путем вызова функции с параметром `fragment`, содержащим XML-данные.

```xml
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform"
                xmlns:msxsl="urn:schemas-microsoft-com:xslt"
                xmlns:user="http://www.adventure-works.com"
                version="1.0">
    <xsl:var name="fragment">
        <node1>
            <node2/>
        </node1>
    <xsl:var>

  <msxsl:script language="C#" implements-prefix="user">
    function NodeFragment(XPathNavigator nav)
    {
      if (nav.HasSelection == false)
        XPathNavigator.MoveToNext();
      return;
    }
  </msxsl:script>

    <xsl:template match="/">
            <xsl:value-of select="user:NodeFragment(msxml:node-set($fragment))"/>
    </xsl:template>
</xsl:stylesheet>
```

Далее представлен еще один образец, показывающий переменную в формате RTF и, соответственно, тип фрагмента результирующего дерева, который не преобразуется в набор узлов. Вместо этого он передается в функцию скрипта, а для перемещения по узлам используется объект <xref:System.Xml.XPath.XPathNavigator>.

```xml
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform"
        xmlns:msxsl="urn:schemas-microsoft-com:xslt"
        xmlns:user="urn:books"
        exclude-result-prefixes="msxsl">

<xsl:output method="xml" indent="yes" omit-xml-declaration="yes"/>

<xsl:variable name="node-fragment">
    <book>Book1</book>
    <book>Book2</book>
    <book>Book3</book>
    <book>Book4</book>
</xsl:variable>

<msxsl:script implements-prefix="user" language="c#">

<![CDATA[
    string func(XPathNavigator nav)
    {
        bool b = nav.MoveToFirstChild();
        if (b)
            return nav.Value;
        else
            return "Does not exist";
    }

]]>

</msxsl:script>

<xsl:template match="/">
    <first_book>
        <xsl:value-of select="user:func($node-fragment)"/>
    </first_book>
</xsl:template>

</xsl:stylesheet>
```

Результат преобразования любого XML-кода с этой таблицей стилей показан в следующих выходных данных.

## <a name="output"></a>Выходные данные

```xml
<first_book xmlns:user="urn:books">Book1</first_book>
```

Как упоминалось выше, функция `node-set` позволяет преобразовать фрагмент результирующего дерева в набор узлов. Результирующий узел всегда содержит один узел, который является корневым узлом дерева. Если преобразовать фрагмент результирующего дерева в набор узлов, его можно будет использовать везде, где используется обычный набор узлов, например в инструкции for-each или в значении атрибута `select`. В следующих строках кода показано преобразование фрагмента в набор узлов и его использование в качестве набора узлов:

`<xsl:for-each select="msxsl:node-set($node-fragment)">`

`<xsl:value-of select="user:func(msxsl:node-set($node-fragment))"/>`

После преобразования фрагмента в набор узлов для перемещения по нему уже не нужно использовать объект <xref:System.Xml.XPath.XPathNavigator>. Вместо него для набора узлов используется объект <xref:System.Xml.XPath.XPathNodeIterator>.

В следующем примере `$var` - переменная, представляющая собой дерево узлов в таблице стилей. Инструкция for-each в сочетании с функцией `node-set` позволяет проходить по дереву, рассматривая его как набор узлов.

```xml
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform"
                xmlns:msxsl="urn:schemas-microsoft-com:xslt"
                xmlns:user="http://www.adventure-works.com"
                version="1.0">
    <xsl:variable name="states">
        <node1>AL</node1>
        <node1>CA</node1>
        <node1>CO</node1>
        <node1>WA</node1>
    </xsl:variable>

    <xsl:template match="/">
            <xsl:for-each select="msxsl:node-set($states)"/>
    </xsl:template>
</xsl:stylesheet>
```

Далее приведен еще один пример переменной формата RTF, имеющей тип фрагмента результирующего дерева, которая преобразуется в набор узлов, а затем передается функции скрипта как объект XPathNodeIterator.

```xml
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform"
        xmlns:msxsl="urn:schemas-microsoft-com:xslt"
        xmlns:user="urn:books"
        exclude-result-prefixes="msxsl">

<xsl:output method="xml" indent="yes" omit-xml-declaration="yes"/>

<xsl:variable name="node-fragment">
    <book>Book1</book>
    <book>Book2</book>
    <book>Book3</book>
    <book>Book4</book>
</xsl:variable>

<msxsl:script implements-prefix="user" language="c#">

<![CDATA[
    string func(XPathNodeIterator it)
    {
        it.MoveNext();
        return it.Current.Value;
        //it.Current returns XPathNavigator positioned on the current node
    }

]]>

</msxsl:script>
<xsl:template match="/">
    <books>
        <xsl:value-of select="user:func(msxsl:node-set($node-fragment))"/>
    </books>
</xsl:template>

</xsl:stylesheet>
```

Далее приведен результат преобразования XML-кода с этой таблицей стилей:

```xml
<books xmlns:user="urn:books">Book1Book2Book3Book4</books>
```

## <a name="see-also"></a>См. также раздел

- <xref:System.Xml.XPath.XPathNodeIterator>
- [XSLT-преобразования с помощью класса XslTransform](xslt-transformations-with-the-xsltransform-class.md)
- [Реализация классом XslTransform XSLT-процессора](xsltransform-class-implements-the-xslt-processor.md)
