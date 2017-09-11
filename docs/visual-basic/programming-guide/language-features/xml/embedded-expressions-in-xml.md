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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d24a49f2fa6fd66fe6e4c7724bd4298d65fb7a59
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="embedded-expressions-in-xml-visual-basic"></a><span data-ttu-id="5a74e-102">Встроенные выражения в XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a74e-102">Embedded Expressions in XML (Visual Basic)</span></span>
<span data-ttu-id="5a74e-103">Внедренные выражения позволяют создать XML-литералы, содержащие выражения, которые вычисляются во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="5a74e-103">Embedded expressions enable you to create XML literals that contain expressions that are evaluated at run time.</span></span> <span data-ttu-id="5a74e-104">Синтаксис для встроенных выражений `<%=` `expression` `%>`, который одинаков как синтаксис, используемый в [!INCLUDE[vstecasp](../../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a74e-104">The syntax for an embedded expression is `<%=` `expression` `%>`, which is the same as the syntax used in [!INCLUDE[vstecasp](../../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)].</span></span>  
  
 <span data-ttu-id="5a74e-105">Например созданием XML-элемента литерал, объединяющий встроенные выражения с содержимым текста.</span><span class="sxs-lookup"><span data-stu-id="5a74e-105">For example, you can create an XML element literal, combining embedded expressions with literal text content.</span></span>  
  
 <span data-ttu-id="5a74e-106">[!code-vb[VbXMLSamples&#27;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="5a74e-106">[!code-vb[VbXMLSamples#27](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_1.vb)]</span></span>  
  
 <span data-ttu-id="5a74e-107">Если `isbnNumber` содержит целое число 12345 и `modifiedDate` содержит дату 3/5/2006, при выполнении этого кода значение `book` является:</span><span class="sxs-lookup"><span data-stu-id="5a74e-107">If `isbnNumber` contains the integer 12345 and `modifiedDate` contains the date 3/5/2006, when this code executes, the value of `book` is:</span></span>  
  
```  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## <a name="embedded-expression-location-and-validation"></a><span data-ttu-id="5a74e-108">Расположение встроенного выражения и проверка</span><span class="sxs-lookup"><span data-stu-id="5a74e-108">Embedded Expression Location and Validation</span></span>  
 <span data-ttu-id="5a74e-109">Встроенные выражения могут располагаться только на определенных местах внутри текстовых XML выражений.</span><span class="sxs-lookup"><span data-stu-id="5a74e-109">Embedded expressions can appear only at certain locations within XML literal expressions.</span></span> <span data-ttu-id="5a74e-110">Расположение выражения определяет типы выражения значений, которые могут возвращать и как `Nothing` обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5a74e-110">The expression location controls which types the expression can return and how `Nothing` is handled.</span></span> <span data-ttu-id="5a74e-111">В следующей таблице описаны разрешенные расположения и типы встроенных выражений.</span><span class="sxs-lookup"><span data-stu-id="5a74e-111">The following table describes the allowed locations and types of embedded expressions.</span></span>  
  
|<span data-ttu-id="5a74e-112">Расположение в литерале</span><span class="sxs-lookup"><span data-stu-id="5a74e-112">Location in literal</span></span>|<span data-ttu-id="5a74e-113">Тип выражения</span><span class="sxs-lookup"><span data-stu-id="5a74e-113">Type of expression</span></span>|<span data-ttu-id="5a74e-114">Обработка`Nothing`</span><span class="sxs-lookup"><span data-stu-id="5a74e-114">Handling of `Nothing`</span></span>|  
|---|---|---|  
|<span data-ttu-id="5a74e-115">Имя XML-элемента</span><span class="sxs-lookup"><span data-stu-id="5a74e-115">XML element name</span></span>|<span data-ttu-id="5a74e-116"><xref:System.Xml.Linq.XName></xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="5a74e-116"><xref:System.Xml.Linq.XName></span></span>|<span data-ttu-id="5a74e-117">Ошибка</span><span class="sxs-lookup"><span data-stu-id="5a74e-117">Error</span></span>|  
|<span data-ttu-id="5a74e-118">Содержимое XML-элемента</span><span class="sxs-lookup"><span data-stu-id="5a74e-118">XML element content</span></span>|<span data-ttu-id="5a74e-119">`Object`или массив`Object`</span><span class="sxs-lookup"><span data-stu-id="5a74e-119">`Object` or array of `Object`</span></span>|<span data-ttu-id="5a74e-120">Не учитывается</span><span class="sxs-lookup"><span data-stu-id="5a74e-120">Ignored</span></span>|  
|<span data-ttu-id="5a74e-121">Имя атрибута элемента XML</span><span class="sxs-lookup"><span data-stu-id="5a74e-121">XML element attribute name</span></span>|<span data-ttu-id="5a74e-122"><xref:System.Xml.Linq.XName></xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="5a74e-122"><xref:System.Xml.Linq.XName></span></span>|<span data-ttu-id="5a74e-123">Ошибка, если значение атрибута не является также`Nothing`</span><span class="sxs-lookup"><span data-stu-id="5a74e-123">Error, unless the attribute value is also `Nothing`</span></span>|  
|<span data-ttu-id="5a74e-124">Значение атрибута элемента XML</span><span class="sxs-lookup"><span data-stu-id="5a74e-124">XML element attribute value</span></span>|`Object`|<span data-ttu-id="5a74e-125">Объявление атрибута игнорируется</span><span class="sxs-lookup"><span data-stu-id="5a74e-125">Attribute declaration ignored</span></span>|  
|<span data-ttu-id="5a74e-126">Атрибут XML-элемента</span><span class="sxs-lookup"><span data-stu-id="5a74e-126">XML element attribute</span></span>|<span data-ttu-id="5a74e-127"><xref:System.Xml.Linq.XAttribute>или коллекции<xref:System.Xml.Linq.XAttribute></xref:System.Xml.Linq.XAttribute></xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="5a74e-127"><xref:System.Xml.Linq.XAttribute> or a collection of <xref:System.Xml.Linq.XAttribute></span></span>|<span data-ttu-id="5a74e-128">Не учитывается</span><span class="sxs-lookup"><span data-stu-id="5a74e-128">Ignored</span></span>|  
|<span data-ttu-id="5a74e-129">Корневой элемент документа XML</span><span class="sxs-lookup"><span data-stu-id="5a74e-129">XML document root element</span></span>|<span data-ttu-id="5a74e-130"><xref:System.Xml.Linq.XElement>или коллекцию одного <xref:System.Xml.Linq.XElement>объекта и произвольное число <xref:System.Xml.Linq.XProcessingInstruction>и <xref:System.Xml.Linq.XComment>объектов</xref:System.Xml.Linq.XComment> </xref:System.Xml.Linq.XProcessingInstruction> </xref:System.Xml.Linq.XElement></xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="5a74e-130"><xref:System.Xml.Linq.XElement> or a collection of one <xref:System.Xml.Linq.XElement> object and an arbitrary number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects</span></span>|<span data-ttu-id="5a74e-131">Не учитывается</span><span class="sxs-lookup"><span data-stu-id="5a74e-131">Ignored</span></span>|  
  
-   <span data-ttu-id="5a74e-132">Пример встроенного выражения в имени элемента XML.</span><span class="sxs-lookup"><span data-stu-id="5a74e-132">Example of an embedded expression in an XML element name:</span></span>  
  
     <span data-ttu-id="5a74e-133">[!code-vb[VbXMLSamples&#32;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="5a74e-133">[!code-vb[VbXMLSamples#32](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_2.vb)]</span></span>  
  
-   <span data-ttu-id="5a74e-134">Пример встроенного выражения в содержимом XML-элемента.</span><span class="sxs-lookup"><span data-stu-id="5a74e-134">Example of an embedded expression in the content of an XML element:</span></span>  
  
     <span data-ttu-id="5a74e-135">[!code-vb[VbXMLSamples&#33;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="5a74e-135">[!code-vb[VbXMLSamples#33](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_3.vb)]</span></span>  
  
-   <span data-ttu-id="5a74e-136">Пример встроенного выражения в имени атрибута элемента XML.</span><span class="sxs-lookup"><span data-stu-id="5a74e-136">Example of an embedded expression in an XML element attribute name:</span></span>  
  
     <span data-ttu-id="5a74e-137">[!code-vb[VbXMLSamples&#34;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="5a74e-137">[!code-vb[VbXMLSamples#34](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_4.vb)]</span></span>  
  
-   <span data-ttu-id="5a74e-138">Пример встроенного выражения в значении атрибута элемента XML.</span><span class="sxs-lookup"><span data-stu-id="5a74e-138">Example of an embedded expression in an XML element attribute value:</span></span>  
  
     <span data-ttu-id="5a74e-139">[!code-vb[VbXMLSamples&#35;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="5a74e-139">[!code-vb[VbXMLSamples#35](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_5.vb)]</span></span>  
  
-   <span data-ttu-id="5a74e-140">Пример встроенного выражения в атрибуте XML-элемента.</span><span class="sxs-lookup"><span data-stu-id="5a74e-140">Example of an embedded expression in an XML element attribute:</span></span>  
  
     <span data-ttu-id="5a74e-141">[!code-vb[VbXMLSamples&#36;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="5a74e-141">[!code-vb[VbXMLSamples#36](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_6.vb)]</span></span>  
  
-   <span data-ttu-id="5a74e-142">Пример встроенного выражения в корневом элементе документа XML.</span><span class="sxs-lookup"><span data-stu-id="5a74e-142">Example of an embedded expression in an XML document root element:</span></span>  
  
     <span data-ttu-id="5a74e-143">[!code-vb[VbXMLSamples&#37;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="5a74e-143">[!code-vb[VbXMLSamples#37](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_7.vb)]</span></span>  
  
 <span data-ttu-id="5a74e-144">При включении `Option Strict`, компилятор проверяет, что тип каждого встроенного выражения может быть расширен до нужного типа.</span><span class="sxs-lookup"><span data-stu-id="5a74e-144">If you enable `Option Strict`, the compiler checks that the type of each embedded expression widens to the required type.</span></span> <span data-ttu-id="5a74e-145">Единственное исключение — для корневого элемента XML-документа, который проверяется при выполнении кода.</span><span class="sxs-lookup"><span data-stu-id="5a74e-145">The only exception is for the root element of an XML document, which is verified when the code runs.</span></span> <span data-ttu-id="5a74e-146">Если компиляция выполняется без `Option Strict`, то можно внедрить выражения типа `Object` и их тип будет проверяться во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="5a74e-146">If you compile without `Option Strict`, you can embed expressions of type `Object` and their type is verified at run time.</span></span>  
  
 <span data-ttu-id="5a74e-147">В местах, где содержимое является необязательным встроенные выражения, содержащие `Nothing` игнорируются.</span><span class="sxs-lookup"><span data-stu-id="5a74e-147">In locations where content is optional, embedded expressions that contain `Nothing` are ignored.</span></span> <span data-ttu-id="5a74e-148">Это означает, нет необходимости проверять содержимое элемента, значения атрибутов и элементы массива не `Nothing` прежде чем использовать XML-литерал.</span><span class="sxs-lookup"><span data-stu-id="5a74e-148">This means you do not have to check that element content, attribute values, and array elements are not `Nothing` before you use an XML literal.</span></span> <span data-ttu-id="5a74e-149">Необходимые значения, такие как имена элементов и атрибутов, не может быть `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="5a74e-149">Required values, such as element and attribute names, cannot be `Nothing`.</span></span>  
  
 <span data-ttu-id="5a74e-150">Дополнительные сведения об использовании встроенного выражения в литерале определенного типа см. в разделе [литерала документа XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [литерала XML элемент](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="5a74e-150">For more information about using an embedded expression in a particular type of literal, see [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="scoping-rules"></a><span data-ttu-id="5a74e-151">Правила области видимости</span><span class="sxs-lookup"><span data-stu-id="5a74e-151">Scoping Rules</span></span>  
 <span data-ttu-id="5a74e-152">Компилятор преобразует каждый XML-литерал в вызов конструктора для соответствующего типа литерала.</span><span class="sxs-lookup"><span data-stu-id="5a74e-152">The compiler converts each XML literal into a constructor call for the appropriate literal type.</span></span> <span data-ttu-id="5a74e-153">Текстовое содержимое и встроенные выражения в XML-литерале передаются как аргументы в конструктор.</span><span class="sxs-lookup"><span data-stu-id="5a74e-153">The literal content and embedded expressions in an XML literal are passed as arguments to the constructor.</span></span> <span data-ttu-id="5a74e-154">Это означает, что все [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] элементы программирования на XML-литерал также доступны для его встроенных выражений.</span><span class="sxs-lookup"><span data-stu-id="5a74e-154">This means that all [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] programming elements available to an XML literal are also available to its embedded expressions.</span></span>  
  
 <span data-ttu-id="5a74e-155">В XML-литерал можно использовать пространство имен XML, объявленные префиксы с `Imports` инструкции.</span><span class="sxs-lookup"><span data-stu-id="5a74e-155">Within an XML literal, you can access the XML namespace prefixes declared with the `Imports` statement.</span></span> <span data-ttu-id="5a74e-156">Можно объявить новый префикс пространства имен XML или переопределить существующий XML префикс в элементе с помощью `xmlns` атрибута.</span><span class="sxs-lookup"><span data-stu-id="5a74e-156">You can declare a new XML namespace prefix, or shadow an existing XML namespace prefix, in an element by using the `xmlns` attribute.</span></span> <span data-ttu-id="5a74e-157">Новое пространство имен доступно дочерние узлы этого элемента, но не XML-литералов во встроенных выражениях.</span><span class="sxs-lookup"><span data-stu-id="5a74e-157">The new namespace is available to the child nodes of that element, but not to XML literals in embedded expressions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5a74e-158">При объявлении префикса пространства имен XML с помощью `xmlns` пространства имен атрибута, значение атрибута должно быть строковой константы.</span><span class="sxs-lookup"><span data-stu-id="5a74e-158">When you declare an XML namespace prefix by using the `xmlns` namespace attribute, the attribute value must be a constant string.</span></span> <span data-ttu-id="5a74e-159">Таким образом, с помощью `xmlns` атрибут аналогично использованию `Imports` инструкции для объявления пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="5a74e-159">In this regard, using the `xmlns` attribute is like using the `Imports` statement to declare an XML namespace.</span></span> <span data-ttu-id="5a74e-160">Нельзя использовать внедренное выражение для указания значения пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="5a74e-160">You cannot use an embedded expression to specify the XML namespace value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a74e-161">См. также</span><span class="sxs-lookup"><span data-stu-id="5a74e-161">See Also</span></span>  
 <span data-ttu-id="5a74e-162">[Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="5a74e-162">[Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="5a74e-163"> [XML-литерал документа](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md) </span><span class="sxs-lookup"><span data-stu-id="5a74e-163"> [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md) </span></span>  
<span data-ttu-id="5a74e-164"> [Литеральное представление XML элемента](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span><span class="sxs-lookup"><span data-stu-id="5a74e-164"> [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span></span>  
<span data-ttu-id="5a74e-165"> [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) </span><span class="sxs-lookup"><span data-stu-id="5a74e-165"> [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) </span></span>  
<span data-ttu-id="5a74e-166"> [Оператор Imports (пространство имен .NET и тип)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) </span><span class="sxs-lookup"><span data-stu-id="5a74e-166"> [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) </span></span>  
<span data-ttu-id="5a74e-167"> [Общие сведения об XML-литералах](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)</span><span class="sxs-lookup"><span data-stu-id="5a74e-167"> [XML Literals Overview](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)</span></span>
