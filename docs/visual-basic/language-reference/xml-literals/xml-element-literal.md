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
ms.openlocfilehash: 3431ad32809e1f15eb8473d5af7660367cca04de
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64751955"
---
# <a name="xml-element-literal-visual-basic"></a><span data-ttu-id="388ef-102">Литеральное представление XML-элемента (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="388ef-102">XML Element Literal (Visual Basic)</span></span>

<span data-ttu-id="388ef-103">Литералом, представляющим <xref:System.Xml.Linq.XElement> объекта.</span><span class="sxs-lookup"><span data-stu-id="388ef-103">A literal that represents an <xref:System.Xml.Linq.XElement> object.</span></span>

## <a name="syntax"></a><span data-ttu-id="388ef-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="388ef-104">Syntax</span></span>

```xml
<name [ attributeList ] />
-or-
<name [ attributeList ] > [ elementContents ] </[ name ]>
```

## <a name="parts"></a><span data-ttu-id="388ef-105">Части</span><span class="sxs-lookup"><span data-stu-id="388ef-105">Parts</span></span>

- `<`

  <span data-ttu-id="388ef-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="388ef-106">Required.</span></span> <span data-ttu-id="388ef-107">Откроется начальный тег элемента.</span><span class="sxs-lookup"><span data-stu-id="388ef-107">Opens the starting element tag.</span></span>

- `name`

  <span data-ttu-id="388ef-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="388ef-108">Required.</span></span> <span data-ttu-id="388ef-109">Имя элемента.</span><span class="sxs-lookup"><span data-stu-id="388ef-109">Name of the element.</span></span> <span data-ttu-id="388ef-110">Одно из следующих имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="388ef-110">The format is one of the following:</span></span>

  - <span data-ttu-id="388ef-111">Литеральный текст для имени элемента формы `[ePrefix:]eName`, где:</span><span class="sxs-lookup"><span data-stu-id="388ef-111">Literal text for the element name, of the form `[ePrefix:]eName`, where:</span></span>

    |<span data-ttu-id="388ef-112">Отделение</span><span class="sxs-lookup"><span data-stu-id="388ef-112">Part</span></span>|<span data-ttu-id="388ef-113">Описание</span><span class="sxs-lookup"><span data-stu-id="388ef-113">Description</span></span>|
    |---|---|
    |`ePrefix`|<span data-ttu-id="388ef-114">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="388ef-114">Optional.</span></span> <span data-ttu-id="388ef-115">Префикс пространства имен XML для элемента.</span><span class="sxs-lookup"><span data-stu-id="388ef-115">XML namespace prefix for the element.</span></span> <span data-ttu-id="388ef-116">Должно быть глобальным пространством имен XML, который определен с помощью `Imports` инструкции в файле или на уровне проекта или локальное пространство имен XML, который определен в этом элементе или родительском элементе.</span><span class="sxs-lookup"><span data-stu-id="388ef-116">Must be a global XML namespace that is defined with an `Imports` statement in the file or at the project level, or a local XML namespace that is defined in this element or a parent element.</span></span>|
    |`eName`|<span data-ttu-id="388ef-117">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="388ef-117">Required.</span></span> <span data-ttu-id="388ef-118">Имя элемента.</span><span class="sxs-lookup"><span data-stu-id="388ef-118">Name of the element.</span></span> <span data-ttu-id="388ef-119">Одно из следующих имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="388ef-119">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="388ef-120">-Литеральный текст.</span><span class="sxs-lookup"><span data-stu-id="388ef-120">- Literal text.</span></span> <span data-ttu-id="388ef-121">См. в разделе [имена объявленных элементов и атрибутов](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="388ef-121">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="388ef-122">-Внедренные выражения вида `<%= eNameExp %>`.</span><span class="sxs-lookup"><span data-stu-id="388ef-122">- Embedded expression of the form `<%= eNameExp %>`.</span></span> <span data-ttu-id="388ef-123">Тип `eNameExp` должно быть `String` или типом, который неявно преобразуется к типу <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="388ef-123">The type of `eNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|

  - <span data-ttu-id="388ef-124">Внедренные выражения вида `<%= nameExp %>`.</span><span class="sxs-lookup"><span data-stu-id="388ef-124">Embedded expression of the form `<%= nameExp %>`.</span></span> <span data-ttu-id="388ef-125">Тип `nameExp` должно быть `String` или неявно преобразовываться в тип <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="388ef-125">The type of `nameExp` must be `String` or a type implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span> <span data-ttu-id="388ef-126">Внедренное выражение не допускается в закрывающий тег элемента.</span><span class="sxs-lookup"><span data-stu-id="388ef-126">An embedded expression is not allowed in a closing tag of an element.</span></span>

- `attributeList`

  <span data-ttu-id="388ef-127">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="388ef-127">Optional.</span></span> <span data-ttu-id="388ef-128">Список атрибутов, объявленных в литерале.</span><span class="sxs-lookup"><span data-stu-id="388ef-128">List of attributes declared in the literal.</span></span>

  `attribute [ attribute ... ]`

  <span data-ttu-id="388ef-129">Каждый `attribute` имеет одно из следующих вариантов синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="388ef-129">Each `attribute` has one of the following syntaxes:</span></span>

  - <span data-ttu-id="388ef-130">Назначение формы атрибутов `[aPrefix:]aName=aValue`, где:</span><span class="sxs-lookup"><span data-stu-id="388ef-130">Attribute assignment, of the form `[aPrefix:]aName=aValue`, where:</span></span>

    |<span data-ttu-id="388ef-131">Отделение</span><span class="sxs-lookup"><span data-stu-id="388ef-131">Part</span></span>|<span data-ttu-id="388ef-132">Описание</span><span class="sxs-lookup"><span data-stu-id="388ef-132">Description</span></span>|
    |---|---|
    |`aPrefix`|<span data-ttu-id="388ef-133">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="388ef-133">Optional.</span></span> <span data-ttu-id="388ef-134">Префикс пространства имен XML для атрибута.</span><span class="sxs-lookup"><span data-stu-id="388ef-134">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="388ef-135">Должно быть глобальным пространством имен XML, который определен с помощью `Imports` инструкции или локальное пространство имен XML, который определен в этом элементе или родительском элементе.</span><span class="sxs-lookup"><span data-stu-id="388ef-135">Must be a global XML namespace that is defined with an `Imports` statement, or a local XML namespace that is defined in this element or a parent element.</span></span>|
    |`aName`|<span data-ttu-id="388ef-136">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="388ef-136">Required.</span></span> <span data-ttu-id="388ef-137">Имя атрибута.</span><span class="sxs-lookup"><span data-stu-id="388ef-137">Name of the attribute.</span></span> <span data-ttu-id="388ef-138">Одно из следующих имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="388ef-138">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="388ef-139">-Литеральный текст.</span><span class="sxs-lookup"><span data-stu-id="388ef-139">- Literal text.</span></span> <span data-ttu-id="388ef-140">См. в разделе [имена объявленных элементов и атрибутов](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="388ef-140">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="388ef-141">-Внедренные выражения вида `<%= aNameExp %>`.</span><span class="sxs-lookup"><span data-stu-id="388ef-141">- Embedded expression of the form `<%= aNameExp %>`.</span></span> <span data-ttu-id="388ef-142">Тип `aNameExp` должно быть `String` или типом, который неявно преобразуется к типу <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="388ef-142">The type of `aNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|
    |`aValue`|<span data-ttu-id="388ef-143">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="388ef-143">Optional.</span></span> <span data-ttu-id="388ef-144">Значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="388ef-144">Value of the attribute.</span></span> <span data-ttu-id="388ef-145">Одно из следующих имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="388ef-145">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="388ef-146">-Литеральный текст, заключенный в кавычки.</span><span class="sxs-lookup"><span data-stu-id="388ef-146">- Literal text, enclosed in quotation marks.</span></span><br /><span data-ttu-id="388ef-147">-Внедренные выражения вида `<%= aValueExp %>`.</span><span class="sxs-lookup"><span data-stu-id="388ef-147">- Embedded expression of the form `<%= aValueExp %>`.</span></span> <span data-ttu-id="388ef-148">Допустим любой тип.</span><span class="sxs-lookup"><span data-stu-id="388ef-148">Any type is allowed.</span></span>|

  - <span data-ttu-id="388ef-149">Внедренные выражения вида `<%= aExp %>`.</span><span class="sxs-lookup"><span data-stu-id="388ef-149">Embedded expression of the form `<%= aExp %>`.</span></span>

- `/>`

  <span data-ttu-id="388ef-150">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="388ef-150">Optional.</span></span> <span data-ttu-id="388ef-151">Указывает, что элемент является пустым элементом, без содержимого.</span><span class="sxs-lookup"><span data-stu-id="388ef-151">Indicates that the element is an empty element, without content.</span></span>

- `>`

  <span data-ttu-id="388ef-152">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="388ef-152">Required.</span></span> <span data-ttu-id="388ef-153">Завершает начиная или пустым тегом элемента.</span><span class="sxs-lookup"><span data-stu-id="388ef-153">Ends the beginning or empty element tag.</span></span>

- `elementContents`

  <span data-ttu-id="388ef-154">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="388ef-154">Optional.</span></span> <span data-ttu-id="388ef-155">Содержимое элемента.</span><span class="sxs-lookup"><span data-stu-id="388ef-155">Content of the element.</span></span>

  `content [ content ... ]`

  <span data-ttu-id="388ef-156">Каждый `content` может принимать одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="388ef-156">Each `content` can be one of the following:</span></span>

  - <span data-ttu-id="388ef-157">Литеральный текст.</span><span class="sxs-lookup"><span data-stu-id="388ef-157">Literal text.</span></span> <span data-ttu-id="388ef-158">Все пробелы в `elementContents` становится значимыми, если любой текст.</span><span class="sxs-lookup"><span data-stu-id="388ef-158">All the white space in `elementContents` becomes significant if there is any literal text.</span></span>

  - <span data-ttu-id="388ef-159">Внедренные выражения вида `<%= contentExp %>`.</span><span class="sxs-lookup"><span data-stu-id="388ef-159">Embedded expression of the form `<%= contentExp %>`.</span></span>

  - <span data-ttu-id="388ef-160">Литерала элемента XML.</span><span class="sxs-lookup"><span data-stu-id="388ef-160">XML element literal.</span></span>

  - <span data-ttu-id="388ef-161">XML-литерал комментария.</span><span class="sxs-lookup"><span data-stu-id="388ef-161">XML comment literal.</span></span> <span data-ttu-id="388ef-162">См. в разделе [XML-литерал комментария](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span><span class="sxs-lookup"><span data-stu-id="388ef-162">See [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>

  - <span data-ttu-id="388ef-163">Литерал инструкции обработки XML.</span><span class="sxs-lookup"><span data-stu-id="388ef-163">XML processing instruction literal.</span></span> <span data-ttu-id="388ef-164">См. в разделе [литерал инструкции обработки XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span><span class="sxs-lookup"><span data-stu-id="388ef-164">See [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span>

  - <span data-ttu-id="388ef-165">Литерал CDATA XML.</span><span class="sxs-lookup"><span data-stu-id="388ef-165">XML CDATA literal.</span></span> <span data-ttu-id="388ef-166">См. в разделе [XML-литерале CDATA](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).</span><span class="sxs-lookup"><span data-stu-id="388ef-166">See [XML CDATA Literal](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).</span></span>

- `</[name]>`

  <span data-ttu-id="388ef-167">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="388ef-167">Optional.</span></span> <span data-ttu-id="388ef-168">Представляет закрывающий тег для элемента.</span><span class="sxs-lookup"><span data-stu-id="388ef-168">Represents the closing tag for the element.</span></span> <span data-ttu-id="388ef-169">Необязательный `name` параметра не допускается, если она является результатом встроенного выражения.</span><span class="sxs-lookup"><span data-stu-id="388ef-169">The optional `name` parameter is not allowed when it is the result of an embedded expression.</span></span>

## <a name="return-value"></a><span data-ttu-id="388ef-170">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="388ef-170">Return Value</span></span>

<span data-ttu-id="388ef-171">Объект <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="388ef-171">An <xref:System.Xml.Linq.XElement> object.</span></span>

## <a name="remarks"></a><span data-ttu-id="388ef-172">Примечания</span><span class="sxs-lookup"><span data-stu-id="388ef-172">Remarks</span></span>

<span data-ttu-id="388ef-173">Синтаксис элемента XML можно использовать для создания <xref:System.Xml.Linq.XElement> объектов в коде.</span><span class="sxs-lookup"><span data-stu-id="388ef-173">You can use the XML element literal syntax to create <xref:System.Xml.Linq.XElement> objects in your code.</span></span>

> [!NOTE]
> <span data-ttu-id="388ef-174">XML-литерал может занимать несколько строк без использования символа продолжения строки.</span><span class="sxs-lookup"><span data-stu-id="388ef-174">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="388ef-175">Эта функция позволяет скопировать содержимое из XML-документа и вставьте его непосредственно в программу Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="388ef-175">This feature enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>

<span data-ttu-id="388ef-176">Встроенные выражения формы `<%= exp %>` позволяют добавить динамические сведения в литерале XML-элемента.</span><span class="sxs-lookup"><span data-stu-id="388ef-176">Embedded expressions of the form `<%= exp %>` enable you to add dynamic information to an XML element literal.</span></span> <span data-ttu-id="388ef-177">Дополнительные сведения см. в разделе [встроенные выражения в XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="388ef-177">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>

<span data-ttu-id="388ef-178">Компилятор Visual Basic преобразует литерала XML-элемента в вызовы <xref:System.Xml.Linq.XElement.%23ctor%2A> конструктор и, при необходимости, <xref:System.Xml.Linq.XAttribute.%23ctor%2A> конструктор.</span><span class="sxs-lookup"><span data-stu-id="388ef-178">The Visual Basic compiler converts the XML element literal into calls to the <xref:System.Xml.Linq.XElement.%23ctor%2A> constructor and, if it is required, the <xref:System.Xml.Linq.XAttribute.%23ctor%2A> constructor.</span></span>

## <a name="xml-namespaces"></a><span data-ttu-id="388ef-179">Пространства имен XML</span><span class="sxs-lookup"><span data-stu-id="388ef-179">XML Namespaces</span></span>

<span data-ttu-id="388ef-180">Префиксы пространства имен XML полезны в тех случаях, когда необходимо создать XML-литералов с элементами одного пространства имен много раз в коде.</span><span class="sxs-lookup"><span data-stu-id="388ef-180">XML namespace prefixes are useful when you have to create XML literals with elements from the same namespace many times in code.</span></span> <span data-ttu-id="388ef-181">Можно использовать глобальные префиксы пространства имен XML, которые определяются с помощью `Imports` инструкции или локальные префиксы, которые определяются с помощью `xmlns:xmlPrefix="xmlNamespace"` синтаксис атрибута.</span><span class="sxs-lookup"><span data-stu-id="388ef-181">You can use global XML namespace prefixes, which you define by using the `Imports` statement, or local prefixes, which you define by using the `xmlns:xmlPrefix="xmlNamespace"` attribute syntax.</span></span> <span data-ttu-id="388ef-182">Дополнительные сведения см. в разделе [оператор Imports (пространство имен XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="388ef-182">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>

<span data-ttu-id="388ef-183">В соответствии с правилами обзора данных для пространств имен XML локальные префиксы имеют приоритет над глобальные префиксы.</span><span class="sxs-lookup"><span data-stu-id="388ef-183">In accordance with the scoping rules for XML namespaces, local prefixes take precedence over global prefixes.</span></span> <span data-ttu-id="388ef-184">Тем не менее, если XML-литерал определяет пространство имен XML, что пространство имен недоступно для выражения, которые встречаются во внедренном выражении.</span><span class="sxs-lookup"><span data-stu-id="388ef-184">However, if an XML literal defines an XML namespace, that namespace is not available to expressions that appear in an embedded expression.</span></span> <span data-ttu-id="388ef-185">Внедренное выражение доступен только глобальным пространством имен XML.</span><span class="sxs-lookup"><span data-stu-id="388ef-185">The embedded expression can access only the global XML namespace.</span></span>

<span data-ttu-id="388ef-186">Компилятор Visual Basic преобразует каждый глобального пространства имен XML, который используется XML-литерала в одно определение Локальное пространство имен в созданном коде.</span><span class="sxs-lookup"><span data-stu-id="388ef-186">The Visual Basic compiler converts each global XML namespace that is used by an XML literal into a one local namespace definition in the generated code.</span></span> <span data-ttu-id="388ef-187">Глобальные пространства имен XML, которые не используются не отображаются в созданном коде.</span><span class="sxs-lookup"><span data-stu-id="388ef-187">Global XML namespaces that are not used do not appear in the generated code.</span></span>

## <a name="example"></a><span data-ttu-id="388ef-188">Пример</span><span class="sxs-lookup"><span data-stu-id="388ef-188">Example</span></span>

<span data-ttu-id="388ef-189">Приведенный ниже показано, как создать простой XML-элемент, который имеет два вложенных пустых элементов.</span><span class="sxs-lookup"><span data-stu-id="388ef-189">The following example shows how to create a simple XML element that has two nested empty elements.</span></span>

[!code-vb[VbXMLSamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#20)]

<span data-ttu-id="388ef-190">В примере отображается следующий текст.</span><span class="sxs-lookup"><span data-stu-id="388ef-190">The example displays the following text.</span></span> <span data-ttu-id="388ef-191">Обратите внимание на то, что литерал сохраняет структуру пустых элементов.</span><span class="sxs-lookup"><span data-stu-id="388ef-191">Notice that the literal preserves the structure of the empty elements.</span></span>

```xml
<outer>
  <inner1></inner1>
  <inner2 />
</outer>
```

## <a name="example"></a><span data-ttu-id="388ef-192">Пример</span><span class="sxs-lookup"><span data-stu-id="388ef-192">Example</span></span>

<span data-ttu-id="388ef-193">В следующем примере показано, как использовать внедренные выражения для имени элемента и создать атрибуты.</span><span class="sxs-lookup"><span data-stu-id="388ef-193">The following example shows how to use embedded expressions to name an element and create attributes.</span></span>

[!code-vb[VbXMLSamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#21)]

<span data-ttu-id="388ef-194">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="388ef-194">This code displays the following text:</span></span>

```xml
<book isbn="1234" author="My Author" year="1999" title="My Book" />
```

## <a name="example"></a><span data-ttu-id="388ef-195">Пример</span><span class="sxs-lookup"><span data-stu-id="388ef-195">Example</span></span>

<span data-ttu-id="388ef-196">В следующем примере `ns` объявляется как префикс пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="388ef-196">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="388ef-197">Затем используется префикс пространства имен для создания литерала XML и отображает окончательной форме этого элемента.</span><span class="sxs-lookup"><span data-stu-id="388ef-197">It then uses the prefix of the namespace to create an XML literal and displays the element's final form.</span></span>

[!code-vb[VbXMLSamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples10.vb#22)]

<span data-ttu-id="388ef-198">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="388ef-198">This code displays the following text:</span></span>

```xml
<ns:outer xmlns:ns="http://SomeNamespace">
  <ns:middle xmlns:ns="http://NewNamespace">
    <ns:inner1 />
    <inner2 xmlns="http://SomeNamespace" />
  </ns:middle>
</ns:outer>
```

<span data-ttu-id="388ef-199">Обратите внимание на то, что компилятор преобразует префикса глобального пространства имен XML в определении префикса пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="388ef-199">Notice that the compiler converted the prefix of the global XML namespace into a prefix definition for the XML namespace.</span></span> <span data-ttu-id="388ef-200">\<Ns:middle > элемент переопределяет префикс пространства имен XML для \<ns:inner1 > элемента.</span><span class="sxs-lookup"><span data-stu-id="388ef-200">The \<ns:middle> element redefines the XML namespace prefix for the \<ns:inner1> element.</span></span> <span data-ttu-id="388ef-201">Тем не менее \<ns:inner2 > элемент использует пространство имен, определенное `Imports` инструкции.</span><span class="sxs-lookup"><span data-stu-id="388ef-201">However, the \<ns:inner2> element uses the namespace defined by the `Imports` statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="388ef-202">См. также</span><span class="sxs-lookup"><span data-stu-id="388ef-202">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="388ef-203">Имена объявленных элементов и атрибутов XML</span><span class="sxs-lookup"><span data-stu-id="388ef-203">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [<span data-ttu-id="388ef-204">XML-литерал комментария</span><span class="sxs-lookup"><span data-stu-id="388ef-204">XML Comment Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)
- [<span data-ttu-id="388ef-205">XML-литерал CDATA</span><span class="sxs-lookup"><span data-stu-id="388ef-205">XML CDATA Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)
- [<span data-ttu-id="388ef-206">XML-литералы</span><span class="sxs-lookup"><span data-stu-id="388ef-206">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="388ef-207">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="388ef-207">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="388ef-208">Встроенные выражения в XML</span><span class="sxs-lookup"><span data-stu-id="388ef-208">Embedded Expressions in XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [<span data-ttu-id="388ef-209">Оператор Imports (пространство имен XML)</span><span class="sxs-lookup"><span data-stu-id="388ef-209">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
