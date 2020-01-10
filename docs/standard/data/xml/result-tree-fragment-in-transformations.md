---
title: Фрагмент дерева результатов в преобразованиях
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: df363480-ba02-4233-9ddf-8434e421c4f1
ms.openlocfilehash: 33d66b0a835be8bacab76ef9295ce8158385d8d1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710262"
---
# <a name="result-tree-fragment-in-transformations"></a><span data-ttu-id="97fec-102">Фрагмент дерева результатов в преобразованиях</span><span class="sxs-lookup"><span data-stu-id="97fec-102">Result Tree Fragment in Transformations</span></span>

> [!NOTE]
> <span data-ttu-id="97fec-103">Класс <xref:System.Xml.Xsl.XslTransform> явлется устаревшим в версии .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="97fec-103">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the .NET Framework 2.0.</span></span> <span data-ttu-id="97fec-104">Можно выполнять XSLT-преобразование, используя класс <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="97fec-104">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="97fec-105">См. дополнительные сведения об [использовании класса XslCompiledTransform](using-the-xslcompiledtransform-class.md) и [миграции из класса XslTransform](migrating-from-the-xsltransform-class.md).</span><span class="sxs-lookup"><span data-stu-id="97fec-105">See [Using the XslCompiledTransform Class](using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](migrating-from-the-xsltransform-class.md) for more information.</span></span>

 <span data-ttu-id="97fec-106">Фрагменты результирующего дерева представляют собой особый тип набора узлов.</span><span class="sxs-lookup"><span data-stu-id="97fec-106">Result tree fragments, also known as result tree fragments, are nothing more than a special type of node set.</span></span> <span data-ttu-id="97fec-107">С ними можно выполнять любое действие, которое можно выполнять с набором узлов.</span><span class="sxs-lookup"><span data-stu-id="97fec-107">You can perform any function on them that can be performed on a node set.</span></span> <span data-ttu-id="97fec-108">Также можно преобразовать фрагмент результирующего дерева в набор узлов с помощью функции `node-set()` и далее использовать его в любом месте, где можно использовать набор узлов.</span><span class="sxs-lookup"><span data-stu-id="97fec-108">Or, you can also convert a result tree fragment to a node set using the `node-set()` function and subsequently use it any place that a node set can be used.</span></span>

 <span data-ttu-id="97fec-109">Фрагмент результирующего дерева создается в результате применения элемента `<xsl:variable>` или `<xsl:param>` особым образом в таблице стилей.</span><span class="sxs-lookup"><span data-stu-id="97fec-109">A result tree fragment is created as a result of using an `<xsl:variable>` or `<xsl:param>` element in a specific manner in a style sheet.</span></span> <span data-ttu-id="97fec-110">Для элементов `variable` и `parameter` используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="97fec-110">The syntax for the `variable` and `parameter` elements is as follows:</span></span>

```xml
<xsl:param name=Qname select= XPath Expression >
    template body
</xsl:param>

<xsl:variable name=Qname select=XPath Expression >
    template body
</xsl:variable>
```

<span data-ttu-id="97fec-111">Для элемента `parameter` существует несколько способов задания значения для полного имени (`Qname`).</span><span class="sxs-lookup"><span data-stu-id="97fec-111">For the `parameter` element, the value is assigned to the qualified name (`Qname`) in several ways.</span></span> <span data-ttu-id="97fec-112">Можно назначить значение по умолчанию для параметра, возвратив содержимое из выражения XPath в атрибуте `select` или присвоив ему содержимое текста шаблона.</span><span class="sxs-lookup"><span data-stu-id="97fec-112">You can assign a default value to the parameter by returning content from the XML Path Language (XPath) expression in the `select` attribute, or by assigning it the contents of the template body.</span></span>

<span data-ttu-id="97fec-113">Для элемента `variable` также существует несколько способов задания значения.</span><span class="sxs-lookup"><span data-stu-id="97fec-113">For the `variable` element, the value is also assigned in several ways.</span></span> <span data-ttu-id="97fec-114">Можно задать его, возвратив содержимое из выражения XPath в атрибуте `select` или присвоив ему содержимое текста шаблона.</span><span class="sxs-lookup"><span data-stu-id="97fec-114">You can assign it by returning content from the XPath expression in the `select` attribute, or by assigning it the contents of the template body.</span></span>

<span data-ttu-id="97fec-115">Если значение для элемента `parameter` или `variable` присваивается с помощью выражения XPath, будет возвращен один из четырех основных типов XPath: логический, строковый, числовой или набор узлов.</span><span class="sxs-lookup"><span data-stu-id="97fec-115">For both the `parameter` and `variable` elements, if a value is assigned by the XPath expression, then one of the four basic XPath types will be returned: Boolean, string, number, or node set.</span></span> <span data-ttu-id="97fec-116">Если значение задается с помощью непустого текста шаблона, то возвращается тип данных, который отличается от типов данных XPath и представляет собой фрагмент результирующего дерева.</span><span class="sxs-lookup"><span data-stu-id="97fec-116">When the value is given by using a non-empty template body, then a non-XPath data type is returned, and that will be a result tree fragment.</span></span>

<span data-ttu-id="97fec-117">Если переменная привязана к фрагменту результирующего дерева, а не к одному из четырех основных типов данных XPath, то это единственный случай, когда запрос XPath возвращает тип, отличный от четырех типов объектов XPath.</span><span class="sxs-lookup"><span data-stu-id="97fec-117">When a variable is bound to a result tree fragment instead of one of the four basic XPath data types, this is the only time that an XPath query returns a type that is not one of the four XPath object types.</span></span> <span data-ttu-id="97fec-118">Фрагменты результирующего дерева и аспекты их работы описаны в [спецификации консорциума W3C](https://www.w3.org/TR/xslt-10/), в разделах с [11.1 Result Tree Fragments](https://www.w3.org/TR/xslt-10/#section-Result-Tree-Fragments) (Фрагменты результирующего дерева) по [11.6 Passing Parameters to Templates](https://www.w3.org/TR/xslt-10/#section-Passing-Parameters-to-Templates) (Передача параметров в шаблоны).</span><span class="sxs-lookup"><span data-stu-id="97fec-118">Result tree fragments and their behavior are discussed in the [World Wide Web Consortium (W3C) specification](https://www.w3.org/TR/xslt-10/), [section 11.1 Result Tree Fragments](https://www.w3.org/TR/xslt-10/#section-Result-Tree-Fragments) through [section 11.6 Passing Parameters to Templates](https://www.w3.org/TR/xslt-10/#section-Passing-Parameters-to-Templates).</span></span> <span data-ttu-id="97fec-119">Кроме того, в разделе [1 Introduction](https://www.w3.org/TR/xslt-10/#section-Introduction) (Введение) описано, каким образом шаблоны могут содержать элементы из пространства имен XSLT, которые возвращают или создают фрагменты результирующего дерева.</span><span class="sxs-lookup"><span data-stu-id="97fec-119">Also, [section 1 Introduction](https://www.w3.org/TR/xslt-10/#section-Introduction) discusses how templates can contain elements from the XSLT namespace that return or create result tree fragments.</span></span>

<span data-ttu-id="97fec-120">Сам по себе фрагмент результирующего дерева представляет собой набор узлов с единственным корневым узлом.</span><span class="sxs-lookup"><span data-stu-id="97fec-120">A result tree fragment, in concept, behaves like a node set with nothing more than a single root node.</span></span> <span data-ttu-id="97fec-121">Однако остальные возвращаемые узлы являются дочерними.</span><span class="sxs-lookup"><span data-stu-id="97fec-121">However, the rest of the nodes returned are child nodes.</span></span> <span data-ttu-id="97fec-122">Чтобы отобразить дочерние узлы программным образом, скопируйте фрагмент результирующего дерева в результирующее дерево с помощью элемента `<xsl:copy-of>`.</span><span class="sxs-lookup"><span data-stu-id="97fec-122">To programmatically see the child nodes, copy the result tree fragment to the result tree using the `<xsl:copy-of>` element.</span></span> <span data-ttu-id="97fec-123">Во время выполнения элемента copy-of все дочерние узлы также последовательно копируются в результирующее дерево.</span><span class="sxs-lookup"><span data-stu-id="97fec-123">When the copy-of is performed, all the child nodes are also copied to the result tree in sequence.</span></span> <span data-ttu-id="97fec-124">До использования элемента `copy` или `copy-of` фрагмент результирующего дерева не является частью результирующего дерева или выходных данных преобразования.</span><span class="sxs-lookup"><span data-stu-id="97fec-124">Until a `copy` or `copy-of` is used, a result tree fragment is not part of the result tree or the output from the transformation.</span></span>

<span data-ttu-id="97fec-125">Чтобы пройти по возвращаемым узлам фрагмента результирующего дерева используется объект <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="97fec-125">To iterate over the returned nodes of a result tree fragment, an <xref:System.Xml.XPath.XPathNavigator> is used.</span></span> <span data-ttu-id="97fec-126">В следующем образце кода показано, как создать фрагмент результирующего дерева в таблице стилей путем вызова функции с параметром `fragment`, содержащим XML-данные.</span><span class="sxs-lookup"><span data-stu-id="97fec-126">The following code sample shows how to create a result tree fragment within a style sheet by calling the function with a parameter `fragment`, which contains XML.</span></span>

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

<span data-ttu-id="97fec-127">Далее представлен еще один образец, показывающий переменную в формате RTF и, соответственно, тип фрагмента результирующего дерева, который не преобразуется в набор узлов.</span><span class="sxs-lookup"><span data-stu-id="97fec-127">Here is another sample showing a variable, which is in Rich Text Format (RTF), and hence, a type of result tree fragment, that is not converted to a node set.</span></span> <span data-ttu-id="97fec-128">Вместо этого он передается в функцию скрипта, а для перемещения по узлам используется объект <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="97fec-128">Instead, it is passed to a script function, and the <xref:System.Xml.XPath.XPathNavigator> is used to navigate over the nodes.</span></span>

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

<span data-ttu-id="97fec-129">Результат преобразования любого XML-кода с этой таблицей стилей показан в следующих выходных данных.</span><span class="sxs-lookup"><span data-stu-id="97fec-129">The result of transforming any XML with this style sheet is shown in the following output.</span></span>

## <a name="output"></a><span data-ttu-id="97fec-130">Вывод</span><span class="sxs-lookup"><span data-stu-id="97fec-130">Output</span></span>

```xml
<first_book xmlns:user="urn:books">Book1</first_book>
```

<span data-ttu-id="97fec-131">Как упоминалось выше, функция `node-set` позволяет преобразовать фрагмент результирующего дерева в набор узлов.</span><span class="sxs-lookup"><span data-stu-id="97fec-131">As stated above, the `node-set` function enables you to convert a result tree fragment into a node set.</span></span> <span data-ttu-id="97fec-132">Результирующий узел всегда содержит один узел, который является корневым узлом дерева.</span><span class="sxs-lookup"><span data-stu-id="97fec-132">The resulting node always contains a single node that is the root node of the tree.</span></span> <span data-ttu-id="97fec-133">Если преобразовать фрагмент результирующего дерева в набор узлов, его можно будет использовать везде, где используется обычный набор узлов, например в инструкции for-each или в значении атрибута `select`.</span><span class="sxs-lookup"><span data-stu-id="97fec-133">If you convert a result tree fragment to a node set, then you can use it anywhere a regular node set is used, such as in a for-each statement or in the value of a `select` attribute.</span></span> <span data-ttu-id="97fec-134">В следующих строках кода показано преобразование фрагмента в набор узлов и его использование в качестве набора узлов:</span><span class="sxs-lookup"><span data-stu-id="97fec-134">The following lines of code show the fragment being converted to a node set and used as a node set:</span></span>

`<xsl:for-each select="msxsl:node-set($node-fragment)">`

`<xsl:value-of select="user:func(msxsl:node-set($node-fragment))"/>`

<span data-ttu-id="97fec-135">После преобразования фрагмента в набор узлов для перемещения по нему уже не нужно использовать объект <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="97fec-135">When a fragment is converted to a node set, you no longer use the <xref:System.Xml.XPath.XPathNavigator> to navigate over it.</span></span> <span data-ttu-id="97fec-136">Вместо него для набора узлов используется объект <xref:System.Xml.XPath.XPathNodeIterator>.</span><span class="sxs-lookup"><span data-stu-id="97fec-136">For a node set, you use the <xref:System.Xml.XPath.XPathNodeIterator> instead.</span></span>

<span data-ttu-id="97fec-137">В следующем примере `$var` - переменная, представляющая собой дерево узлов в таблице стилей.</span><span class="sxs-lookup"><span data-stu-id="97fec-137">In the following example, `$var` is a variable that is a node tree in the style sheet.</span></span> <span data-ttu-id="97fec-138">Инструкция for-each в сочетании с функцией `node-set` позволяет проходить по дереву, рассматривая его как набор узлов.</span><span class="sxs-lookup"><span data-stu-id="97fec-138">The for-each statement, combined with the `node-set` function, allows the user to iterate over this tree as a node set.</span></span>

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

<span data-ttu-id="97fec-139">Далее приведен еще один пример переменной формата RTF, имеющей тип фрагмента результирующего дерева, которая преобразуется в набор узлов, а затем передается функции скрипта как объект XPathNodeIterator.</span><span class="sxs-lookup"><span data-stu-id="97fec-139">Here is another example of a variable that is in RTF, and hence of type result tree fragment, that is converted to a node set before being passed to a script function as XPathNodeIterator.</span></span>

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

<span data-ttu-id="97fec-140">Далее приведен результат преобразования XML-кода с этой таблицей стилей:</span><span class="sxs-lookup"><span data-stu-id="97fec-140">The following is the result of transforming XML with this style sheet:</span></span>

```xml
<books xmlns:user="urn:books">Book1Book2Book3Book4</books>
```

## <a name="see-also"></a><span data-ttu-id="97fec-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="97fec-141">See also</span></span>

- <xref:System.Xml.XPath.XPathNodeIterator>
- [<span data-ttu-id="97fec-142">XSLT-преобразования с помощью класса XslTransform</span><span class="sxs-lookup"><span data-stu-id="97fec-142">XSLT Transformations with the XslTransform Class</span></span>](xslt-transformations-with-the-xsltransform-class.md)
- [<span data-ttu-id="97fec-143">Реализация классом XslTransform XSLT-процессора</span><span class="sxs-lookup"><span data-stu-id="97fec-143">XslTransform Class Implements the XSLT Processor</span></span>](xsltransform-class-implements-the-xslt-processor.md)
