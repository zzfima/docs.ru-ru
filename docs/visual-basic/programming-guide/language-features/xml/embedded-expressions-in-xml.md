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
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="embedded-expressions-in-xml-visual-basic"></a><span data-ttu-id="d64b1-102">Встроенные выражения в XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d64b1-102">Embedded Expressions in XML (Visual Basic)</span></span>
<span data-ttu-id="d64b1-103">Внедренные выражения позволяют создать XML-литералы, которые содержат выражения, оцениваемые во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="d64b1-103">Embedded expressions enable you to create XML literals that contain expressions that are evaluated at run time.</span></span> <span data-ttu-id="d64b1-104">Для внедренного выражения используется синтаксис `<%=` `expression` `%>`, который рассматривается как синтаксис, используемый в [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d64b1-104">The syntax for an embedded expression is `<%=` `expression` `%>`, which is the same as the syntax used in [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)].</span></span>  
  
 <span data-ttu-id="d64b1-105">Например созданием XML-элемента литерал, объединяющий встроенные выражения с содержимым текста.</span><span class="sxs-lookup"><span data-stu-id="d64b1-105">For example, you can create an XML element literal, combining embedded expressions with literal text content.</span></span>  
  
 [!code-vb[VbXMLSamples#27](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_1.vb)]  
  
 <span data-ttu-id="d64b1-106">Если `isbnNumber` содержит целое число 12345 и `modifiedDate` содержит дату 3/5/2006, при выполнении этого кода значение `book` является:</span><span class="sxs-lookup"><span data-stu-id="d64b1-106">If `isbnNumber` contains the integer 12345 and `modifiedDate` contains the date 3/5/2006, when this code executes, the value of `book` is:</span></span>  
  
```xml  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## <a name="embedded-expression-location-and-validation"></a><span data-ttu-id="d64b1-107">Внедренное выражение расположение и проверка</span><span class="sxs-lookup"><span data-stu-id="d64b1-107">Embedded Expression Location and Validation</span></span>  
 <span data-ttu-id="d64b1-108">Встроенные выражения могут располагаться только на определенных местах внутри выражения литералов XML.</span><span class="sxs-lookup"><span data-stu-id="d64b1-108">Embedded expressions can appear only at certain locations within XML literal expressions.</span></span> <span data-ttu-id="d64b1-109">Расположение выражения определяет типы выражения значений, которые могут возвращать и как `Nothing` обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="d64b1-109">The expression location controls which types the expression can return and how `Nothing` is handled.</span></span> <span data-ttu-id="d64b1-110">В следующей таблице описаны допустимые расположения и типы внедренных выражений.</span><span class="sxs-lookup"><span data-stu-id="d64b1-110">The following table describes the allowed locations and types of embedded expressions.</span></span>  
  
|<span data-ttu-id="d64b1-111">Расположение в литерале</span><span class="sxs-lookup"><span data-stu-id="d64b1-111">Location in literal</span></span>|<span data-ttu-id="d64b1-112">Тип выражения</span><span class="sxs-lookup"><span data-stu-id="d64b1-112">Type of expression</span></span>|<span data-ttu-id="d64b1-113">Обработка `Nothing`</span><span class="sxs-lookup"><span data-stu-id="d64b1-113">Handling of `Nothing`</span></span>|  
|---|---|---|  
|<span data-ttu-id="d64b1-114">Имя элемента XML</span><span class="sxs-lookup"><span data-stu-id="d64b1-114">XML element name</span></span>|<xref:System.Xml.Linq.XName>|<span data-ttu-id="d64b1-115">Error</span><span class="sxs-lookup"><span data-stu-id="d64b1-115">Error</span></span>|  
|<span data-ttu-id="d64b1-116">Содержимое XML-элемента</span><span class="sxs-lookup"><span data-stu-id="d64b1-116">XML element content</span></span>|<span data-ttu-id="d64b1-117">`Object` или массив `Object`</span><span class="sxs-lookup"><span data-stu-id="d64b1-117">`Object` or array of `Object`</span></span>|<span data-ttu-id="d64b1-118">Не учитывается</span><span class="sxs-lookup"><span data-stu-id="d64b1-118">Ignored</span></span>|  
|<span data-ttu-id="d64b1-119">Имя атрибута XML-элемента</span><span class="sxs-lookup"><span data-stu-id="d64b1-119">XML element attribute name</span></span>|<xref:System.Xml.Linq.XName>|<span data-ttu-id="d64b1-120">Ошибка, если значение атрибута не является также `Nothing`</span><span class="sxs-lookup"><span data-stu-id="d64b1-120">Error, unless the attribute value is also `Nothing`</span></span>|  
|<span data-ttu-id="d64b1-121">Значение атрибута элемента XML</span><span class="sxs-lookup"><span data-stu-id="d64b1-121">XML element attribute value</span></span>|`Object`|<span data-ttu-id="d64b1-122">Объявление атрибута игнорируется</span><span class="sxs-lookup"><span data-stu-id="d64b1-122">Attribute declaration ignored</span></span>|  
|<span data-ttu-id="d64b1-123">Атрибут XML-элемента</span><span class="sxs-lookup"><span data-stu-id="d64b1-123">XML element attribute</span></span>|<span data-ttu-id="d64b1-124"><xref:System.Xml.Linq.XAttribute> или коллекции <xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="d64b1-124"><xref:System.Xml.Linq.XAttribute> or a collection of <xref:System.Xml.Linq.XAttribute></span></span>|<span data-ttu-id="d64b1-125">Не учитывается</span><span class="sxs-lookup"><span data-stu-id="d64b1-125">Ignored</span></span>|  
|<span data-ttu-id="d64b1-126">Корневой элемент документа XML</span><span class="sxs-lookup"><span data-stu-id="d64b1-126">XML document root element</span></span>|<span data-ttu-id="d64b1-127"><xref:System.Xml.Linq.XElement> или коллекция из одного элемента <xref:System.Xml.Linq.XElement> объекта и произвольное число <xref:System.Xml.Linq.XProcessingInstruction> и <xref:System.Xml.Linq.XComment> объектов</span><span class="sxs-lookup"><span data-stu-id="d64b1-127"><xref:System.Xml.Linq.XElement> or a collection of one <xref:System.Xml.Linq.XElement> object and an arbitrary number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects</span></span>|<span data-ttu-id="d64b1-128">Не учитывается</span><span class="sxs-lookup"><span data-stu-id="d64b1-128">Ignored</span></span>|  
  
-   <span data-ttu-id="d64b1-129">Пример встроенного выражения в имя элемента XML.</span><span class="sxs-lookup"><span data-stu-id="d64b1-129">Example of an embedded expression in an XML element name:</span></span>  
  
     [!code-vb[VbXMLSamples#32](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_2.vb)]  
  
-   <span data-ttu-id="d64b1-130">Пример встроенного выражения в содержимом элемента XML.</span><span class="sxs-lookup"><span data-stu-id="d64b1-130">Example of an embedded expression in the content of an XML element:</span></span>  
  
     [!code-vb[VbXMLSamples#33](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_3.vb)]  
  
-   <span data-ttu-id="d64b1-131">Пример встроенного выражения в имени атрибута элемента XML.</span><span class="sxs-lookup"><span data-stu-id="d64b1-131">Example of an embedded expression in an XML element attribute name:</span></span>  
  
     [!code-vb[VbXMLSamples#34](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_4.vb)]  
  
-   <span data-ttu-id="d64b1-132">Пример встроенного выражения в значении атрибута элемента XML.</span><span class="sxs-lookup"><span data-stu-id="d64b1-132">Example of an embedded expression in an XML element attribute value:</span></span>  
  
     [!code-vb[VbXMLSamples#35](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_5.vb)]  
  
-   <span data-ttu-id="d64b1-133">Пример встроенного выражения в атрибуте XML-элемента.</span><span class="sxs-lookup"><span data-stu-id="d64b1-133">Example of an embedded expression in an XML element attribute:</span></span>  
  
     [!code-vb[VbXMLSamples#36](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_6.vb)]  
  
-   <span data-ttu-id="d64b1-134">Пример встроенного выражения в корневом элементе документа XML.</span><span class="sxs-lookup"><span data-stu-id="d64b1-134">Example of an embedded expression in an XML document root element:</span></span>  
  
     [!code-vb[VbXMLSamples#37](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_7.vb)]  
  
 <span data-ttu-id="d64b1-135">При включении `Option Strict`, компилятор проверяет, что тип каждого встроенного выражения может быть расширен в требуемый тип.</span><span class="sxs-lookup"><span data-stu-id="d64b1-135">If you enable `Option Strict`, the compiler checks that the type of each embedded expression widens to the required type.</span></span> <span data-ttu-id="d64b1-136">Единственное исключение — для корневого элемента XML-документа, который проверяется при выполнении кода.</span><span class="sxs-lookup"><span data-stu-id="d64b1-136">The only exception is for the root element of an XML document, which is verified when the code runs.</span></span> <span data-ttu-id="d64b1-137">Если компиляция выполняется без `Option Strict`, можно внедрить выражения типа `Object` и их тип будет проверяться во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="d64b1-137">If you compile without `Option Strict`, you can embed expressions of type `Object` and their type is verified at run time.</span></span>  
  
 <span data-ttu-id="d64b1-138">В местах, где содержимое является необязательным встроенные выражения, содержащие `Nothing` игнорируются.</span><span class="sxs-lookup"><span data-stu-id="d64b1-138">In locations where content is optional, embedded expressions that contain `Nothing` are ignored.</span></span> <span data-ttu-id="d64b1-139">Это означает, вам не нужно проверять содержимое элемента, значения атрибутов и элементы массива не `Nothing` перед использованием XML-литерала.</span><span class="sxs-lookup"><span data-stu-id="d64b1-139">This means you do not have to check that element content, attribute values, and array elements are not `Nothing` before you use an XML literal.</span></span> <span data-ttu-id="d64b1-140">Необходимые значения, такие как имена элементов и атрибутов, не могут быть `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="d64b1-140">Required values, such as element and attribute names, cannot be `Nothing`.</span></span>  
  
 <span data-ttu-id="d64b1-141">Дополнительные сведения об использовании внедренное выражение в литерале определенного типа см. в разделе [литерала документа XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [литерала элемента XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="d64b1-141">For more information about using an embedded expression in a particular type of literal, see [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="scoping-rules"></a><span data-ttu-id="d64b1-142">Правила области видимости</span><span class="sxs-lookup"><span data-stu-id="d64b1-142">Scoping Rules</span></span>  
 <span data-ttu-id="d64b1-143">Компилятор преобразует каждый XML-литерал в вызов конструктора для соответствующего типа литерала.</span><span class="sxs-lookup"><span data-stu-id="d64b1-143">The compiler converts each XML literal into a constructor call for the appropriate literal type.</span></span> <span data-ttu-id="d64b1-144">Текстовое содержимое и встроенные выражения в XML-литерал, передаются как аргументы в конструктор.</span><span class="sxs-lookup"><span data-stu-id="d64b1-144">The literal content and embedded expressions in an XML literal are passed as arguments to the constructor.</span></span> <span data-ttu-id="d64b1-145">Это означает, что все доступные для XML-литерала элементы программирования Visual Basic, также доступны для его встроенных выражений.</span><span class="sxs-lookup"><span data-stu-id="d64b1-145">This means that all Visual Basic programming elements available to an XML literal are also available to its embedded expressions.</span></span>  
  
 <span data-ttu-id="d64b1-146">В XML-литерал можно использовать пространство имен XML, объявленные префиксы с `Imports` инструкции.</span><span class="sxs-lookup"><span data-stu-id="d64b1-146">Within an XML literal, you can access the XML namespace prefixes declared with the `Imports` statement.</span></span> <span data-ttu-id="d64b1-147">Можно объявить новый префикс пространства имен XML, или переопределить существующий XML-префиксом в элементе с помощью `xmlns` атрибута.</span><span class="sxs-lookup"><span data-stu-id="d64b1-147">You can declare a new XML namespace prefix, or shadow an existing XML namespace prefix, in an element by using the `xmlns` attribute.</span></span> <span data-ttu-id="d64b1-148">Новое пространство имен доступно потомков этого элемента, но не XML-литералов в внедренные выражения.</span><span class="sxs-lookup"><span data-stu-id="d64b1-148">The new namespace is available to the child nodes of that element, but not to XML literals in embedded expressions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d64b1-149">При объявлении префикса пространства имен XML с помощью `xmlns` атрибут пространства имен, значение атрибута должно быть строковой константы.</span><span class="sxs-lookup"><span data-stu-id="d64b1-149">When you declare an XML namespace prefix by using the `xmlns` namespace attribute, the attribute value must be a constant string.</span></span> <span data-ttu-id="d64b1-150">Таким образом, с помощью `xmlns` аналогично использованию атрибута `Imports` инструкции для объявления пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="d64b1-150">In this regard, using the `xmlns` attribute is like using the `Imports` statement to declare an XML namespace.</span></span> <span data-ttu-id="d64b1-151">Не удается использовать внедренное выражение для указания значения пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="d64b1-151">You cannot use an embedded expression to specify the XML namespace value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d64b1-152">См. также</span><span class="sxs-lookup"><span data-stu-id="d64b1-152">See Also</span></span>  
 [<span data-ttu-id="d64b1-153">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d64b1-153">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="d64b1-154">XML-литерал документа</span><span class="sxs-lookup"><span data-stu-id="d64b1-154">XML Document Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)  
 [<span data-ttu-id="d64b1-155">XML-литерал элемента</span><span class="sxs-lookup"><span data-stu-id="d64b1-155">XML Element Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [<span data-ttu-id="d64b1-156">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="d64b1-156">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="d64b1-157">Оператор Imports (пространство имен и тип .NET)</span><span class="sxs-lookup"><span data-stu-id="d64b1-157">Imports Statement (.NET Namespace and Type)</span></span>](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [<span data-ttu-id="d64b1-158">Общие сведения об XML-литералах</span><span class="sxs-lookup"><span data-stu-id="d64b1-158">XML Literals Overview</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)
