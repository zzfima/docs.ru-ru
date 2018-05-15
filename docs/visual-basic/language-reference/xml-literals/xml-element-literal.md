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
ms.openlocfilehash: 55d5d1410a65ea8c800bbd2b310907a6d6a61c61
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="xml-element-literal-visual-basic"></a><span data-ttu-id="79a3f-102">Литеральное представление XML-элемента (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="79a3f-102">XML Element Literal (Visual Basic)</span></span>

<span data-ttu-id="79a3f-103">Литерал, представляющий <xref:System.Xml.Linq.XElement> объекта.</span><span class="sxs-lookup"><span data-stu-id="79a3f-103">A literal that represents an <xref:System.Xml.Linq.XElement> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79a3f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="79a3f-104">Syntax</span></span>  
  
```xml  
<name [ attributeList ] />  
-or-  
<name [ attributeList ] > [ elementContents ] </[ name ]>  
```  
  
## <a name="parts"></a><span data-ttu-id="79a3f-105">Части</span><span class="sxs-lookup"><span data-stu-id="79a3f-105">Parts</span></span>  
  
-   `<`  
  
     <span data-ttu-id="79a3f-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="79a3f-106">Required.</span></span> <span data-ttu-id="79a3f-107">Открывает начальный тег элемента.</span><span class="sxs-lookup"><span data-stu-id="79a3f-107">Opens the starting element tag.</span></span>  
  
-   `name`  
  
     <span data-ttu-id="79a3f-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="79a3f-108">Required.</span></span> <span data-ttu-id="79a3f-109">Имя элемента.</span><span class="sxs-lookup"><span data-stu-id="79a3f-109">Name of the element.</span></span> <span data-ttu-id="79a3f-110">Имеет одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="79a3f-110">The format is one of the following:</span></span>  
  
    -   <span data-ttu-id="79a3f-111">Литеральный текст для имени элемента формы `[ePrefix:]eName`, где:</span><span class="sxs-lookup"><span data-stu-id="79a3f-111">Literal text for the element name, of the form `[ePrefix:]eName`, where:</span></span>  
  
        |<span data-ttu-id="79a3f-112">Отделение</span><span class="sxs-lookup"><span data-stu-id="79a3f-112">Part</span></span>|<span data-ttu-id="79a3f-113">Описание</span><span class="sxs-lookup"><span data-stu-id="79a3f-113">Description</span></span>|  
        |---|---|  
        |`ePrefix`|<span data-ttu-id="79a3f-114">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="79a3f-114">Optional.</span></span> <span data-ttu-id="79a3f-115">Префикс пространства имен XML для элемента.</span><span class="sxs-lookup"><span data-stu-id="79a3f-115">XML namespace prefix for the element.</span></span> <span data-ttu-id="79a3f-116">Должно быть глобальным пространством имен XML, который определен с `Imports` инструкции в файле или на уровне проекта или локальным пространством имен XML, определенные в этом элементе или родительском элементе.</span><span class="sxs-lookup"><span data-stu-id="79a3f-116">Must be a global XML namespace that is defined with an `Imports` statement in the file or at the project level, or a local XML namespace that is defined in this element or a parent element.</span></span>|  
        |`eName`|<span data-ttu-id="79a3f-117">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="79a3f-117">Required.</span></span> <span data-ttu-id="79a3f-118">Имя элемента.</span><span class="sxs-lookup"><span data-stu-id="79a3f-118">Name of the element.</span></span> <span data-ttu-id="79a3f-119">Имеет одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="79a3f-119">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="79a3f-120">-Текст.</span><span class="sxs-lookup"><span data-stu-id="79a3f-120">-   Literal text.</span></span> <span data-ttu-id="79a3f-121">В разделе [имена объявленных элементов и атрибутов](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="79a3f-121">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="79a3f-122">-Встроенные выражения формы `<%= eNameExp %>`.</span><span class="sxs-lookup"><span data-stu-id="79a3f-122">-   Embedded expression of the form `<%= eNameExp %>`.</span></span> <span data-ttu-id="79a3f-123">Тип `eNameExp` должно быть `String` или тип, который неявно преобразуется в <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="79a3f-123">The type of `eNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|  
  
    -   <span data-ttu-id="79a3f-124">Встроенные выражения формы `<%= nameExp %>`.</span><span class="sxs-lookup"><span data-stu-id="79a3f-124">Embedded expression of the form `<%= nameExp %>`.</span></span> <span data-ttu-id="79a3f-125">Тип `nameExp` должно быть `String` или неявно преобразовываться в тип <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="79a3f-125">The type of `nameExp` must be `String` or a type implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span> <span data-ttu-id="79a3f-126">Внедренное выражение не допускается в закрывающего тега элемента.</span><span class="sxs-lookup"><span data-stu-id="79a3f-126">An embedded expression is not allowed in a closing tag of an element.</span></span>  
  
-   `attributeList`  
  
     <span data-ttu-id="79a3f-127">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="79a3f-127">Optional.</span></span> <span data-ttu-id="79a3f-128">Список атрибутов, объявленных в литерале.</span><span class="sxs-lookup"><span data-stu-id="79a3f-128">List of attributes declared in the literal.</span></span>  
  
     `attribute [ attribute ... ]`  
  
     <span data-ttu-id="79a3f-129">Каждый `attribute` имеет одно из следующих вариантов синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="79a3f-129">Each `attribute` has one of the following syntaxes:</span></span>  
  
    -   <span data-ttu-id="79a3f-130">Атрибут назначения формы `[aPrefix:]aName=aValue`, где:</span><span class="sxs-lookup"><span data-stu-id="79a3f-130">Attribute assignment, of the form `[aPrefix:]aName=aValue`, where:</span></span>  
  
        |<span data-ttu-id="79a3f-131">Отделение</span><span class="sxs-lookup"><span data-stu-id="79a3f-131">Part</span></span>|<span data-ttu-id="79a3f-132">Описание</span><span class="sxs-lookup"><span data-stu-id="79a3f-132">Description</span></span>|  
        |---|---|  
        |`aPrefix`|<span data-ttu-id="79a3f-133">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="79a3f-133">Optional.</span></span> <span data-ttu-id="79a3f-134">Префикс пространства имен XML для атрибута.</span><span class="sxs-lookup"><span data-stu-id="79a3f-134">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="79a3f-135">Должно быть глобальным пространством имен XML, который определен с `Imports` инструкции или локальным пространством имен XML, определенные в этом элементе или родительском элементе.</span><span class="sxs-lookup"><span data-stu-id="79a3f-135">Must be a global XML namespace that is defined with an `Imports` statement, or a local XML namespace that is defined in this element or a parent element.</span></span>|  
        |`aName`|<span data-ttu-id="79a3f-136">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="79a3f-136">Required.</span></span> <span data-ttu-id="79a3f-137">Имя атрибута.</span><span class="sxs-lookup"><span data-stu-id="79a3f-137">Name of the attribute.</span></span> <span data-ttu-id="79a3f-138">Имеет одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="79a3f-138">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="79a3f-139">-Текст.</span><span class="sxs-lookup"><span data-stu-id="79a3f-139">-   Literal text.</span></span> <span data-ttu-id="79a3f-140">В разделе [имена объявленных элементов и атрибутов](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="79a3f-140">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="79a3f-141">-Встроенные выражения формы `<%= aNameExp %>`.</span><span class="sxs-lookup"><span data-stu-id="79a3f-141">-   Embedded expression of the form `<%= aNameExp %>`.</span></span> <span data-ttu-id="79a3f-142">Тип `aNameExp` должно быть `String` или тип, который неявно преобразуется в <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="79a3f-142">The type of `aNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|  
        |`aValue`|<span data-ttu-id="79a3f-143">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="79a3f-143">Optional.</span></span> <span data-ttu-id="79a3f-144">Значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="79a3f-144">Value of the attribute.</span></span> <span data-ttu-id="79a3f-145">Имеет одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="79a3f-145">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="79a3f-146">-Литеральный текст, заключенный в кавычки.</span><span class="sxs-lookup"><span data-stu-id="79a3f-146">-   Literal text, enclosed in quotation marks.</span></span><br /><span data-ttu-id="79a3f-147">-Встроенные выражения формы `<%= aValueExp %>`.</span><span class="sxs-lookup"><span data-stu-id="79a3f-147">-   Embedded expression of the form `<%= aValueExp %>`.</span></span> <span data-ttu-id="79a3f-148">Допустим любой тип.</span><span class="sxs-lookup"><span data-stu-id="79a3f-148">Any type is allowed.</span></span>|  
  
    -   <span data-ttu-id="79a3f-149">Встроенные выражения формы `<%= aExp %>`.</span><span class="sxs-lookup"><span data-stu-id="79a3f-149">Embedded expression of the form `<%= aExp %>`.</span></span>  
  
-   `/>`  
  
     <span data-ttu-id="79a3f-150">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="79a3f-150">Optional.</span></span> <span data-ttu-id="79a3f-151">Указывает, что элемент является пустым элементом без содержимого.</span><span class="sxs-lookup"><span data-stu-id="79a3f-151">Indicates that the element is an empty element, without content.</span></span>  
  
-   `>`  
  
     <span data-ttu-id="79a3f-152">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="79a3f-152">Required.</span></span> <span data-ttu-id="79a3f-153">Завершает начальный или пустым тегом элемента.</span><span class="sxs-lookup"><span data-stu-id="79a3f-153">Ends the beginning or empty element tag.</span></span>  
  
-   `elementContents`  
  
     <span data-ttu-id="79a3f-154">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="79a3f-154">Optional.</span></span> <span data-ttu-id="79a3f-155">Содержимое элемента.</span><span class="sxs-lookup"><span data-stu-id="79a3f-155">Content of the element.</span></span>  
  
     `content [ content ... ]`  
  
     <span data-ttu-id="79a3f-156">Каждый `content` может принимать одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="79a3f-156">Each `content` can be one of the following:</span></span>  
  
    -   <span data-ttu-id="79a3f-157">Литеральный текст.</span><span class="sxs-lookup"><span data-stu-id="79a3f-157">Literal text.</span></span> <span data-ttu-id="79a3f-158">Все пробелы в `elementContents` становится значимыми, если любой текст.</span><span class="sxs-lookup"><span data-stu-id="79a3f-158">All the white space in `elementContents` becomes significant if there is any literal text.</span></span>  
  
    -   <span data-ttu-id="79a3f-159">Встроенные выражения формы `<%= contentExp %>`.</span><span class="sxs-lookup"><span data-stu-id="79a3f-159">Embedded expression of the form `<%= contentExp %>`.</span></span>  
  
    -   <span data-ttu-id="79a3f-160">Литерала элемента XML.</span><span class="sxs-lookup"><span data-stu-id="79a3f-160">XML element literal.</span></span>  
  
    -   <span data-ttu-id="79a3f-161">XML-литерал комментария.</span><span class="sxs-lookup"><span data-stu-id="79a3f-161">XML comment literal.</span></span> <span data-ttu-id="79a3f-162">В разделе [XML-литерал комментария](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span><span class="sxs-lookup"><span data-stu-id="79a3f-162">See [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>  
  
    -   <span data-ttu-id="79a3f-163">Литерал инструкции обработки XML.</span><span class="sxs-lookup"><span data-stu-id="79a3f-163">XML processing instruction literal.</span></span> <span data-ttu-id="79a3f-164">В разделе [литерал инструкции обработки XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span><span class="sxs-lookup"><span data-stu-id="79a3f-164">See [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span>  
  
    -   <span data-ttu-id="79a3f-165">Литерала CDATA XML.</span><span class="sxs-lookup"><span data-stu-id="79a3f-165">XML CDATA literal.</span></span> <span data-ttu-id="79a3f-166">В разделе [XML-литерала CDATA](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).</span><span class="sxs-lookup"><span data-stu-id="79a3f-166">See [XML CDATA Literal](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).</span></span>  
  
-   `</[name]>`  
  
     <span data-ttu-id="79a3f-167">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="79a3f-167">Optional.</span></span> <span data-ttu-id="79a3f-168">Представляет закрывающий тег для элемента.</span><span class="sxs-lookup"><span data-stu-id="79a3f-168">Represents the closing tag for the element.</span></span> <span data-ttu-id="79a3f-169">Необязательный `name` параметра не допускается, когда он является результатом встроенного выражения.</span><span class="sxs-lookup"><span data-stu-id="79a3f-169">The optional `name` parameter is not allowed when it is the result of an embedded expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="79a3f-170">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="79a3f-170">Return Value</span></span>  
 <span data-ttu-id="79a3f-171">Объект <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="79a3f-171">An <xref:System.Xml.Linq.XElement> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79a3f-172">Примечания</span><span class="sxs-lookup"><span data-stu-id="79a3f-172">Remarks</span></span>  
 <span data-ttu-id="79a3f-173">Синтаксис элемента XML можно использовать для создания <xref:System.Xml.Linq.XElement> объектов в коде.</span><span class="sxs-lookup"><span data-stu-id="79a3f-173">You can use the XML element literal syntax to create <xref:System.Xml.Linq.XElement> objects in your code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="79a3f-174">XML-литерал может занимать несколько строк без использования символа продолжения строки.</span><span class="sxs-lookup"><span data-stu-id="79a3f-174">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="79a3f-175">Эта функция позволяет скопировать содержимое из XML-документа и вставьте его непосредственно в программу Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="79a3f-175">This feature enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="79a3f-176">Встроенные выражения формы `<%= exp %>` позволяют добавлять динамические сведения для литерала XML-элемента.</span><span class="sxs-lookup"><span data-stu-id="79a3f-176">Embedded expressions of the form `<%= exp %>` enable you to add dynamic information to an XML element literal.</span></span> <span data-ttu-id="79a3f-177">Дополнительные сведения см. в разделе [встроенные выражения в XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="79a3f-177">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>  
  
 <span data-ttu-id="79a3f-178">Компилятор Visual Basic преобразует литерала XML-элемента в вызовы <xref:System.Xml.Linq.XElement.%23ctor%2A> конструктора и, при необходимости, <xref:System.Xml.Linq.XAttribute.%23ctor%2A> конструктор.</span><span class="sxs-lookup"><span data-stu-id="79a3f-178">The Visual Basic compiler converts the XML element literal into calls to the <xref:System.Xml.Linq.XElement.%23ctor%2A> constructor and, if it is required, the <xref:System.Xml.Linq.XAttribute.%23ctor%2A> constructor.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="79a3f-179">Пространства имен XML</span><span class="sxs-lookup"><span data-stu-id="79a3f-179">XML Namespaces</span></span>  
 <span data-ttu-id="79a3f-180">Префиксы пространства имен XML полезны в тех случаях, когда необходимо создать XML-литералы с элементами одного пространства имен, сколько раз в коде.</span><span class="sxs-lookup"><span data-stu-id="79a3f-180">XML namespace prefixes are useful when you have to create XML literals with elements from the same namespace many times in code.</span></span> <span data-ttu-id="79a3f-181">Можно использовать глобальные префиксы пространства имен XML, которые можно определить с помощью `Imports` инструкции или локальные префиксы, которые определяются с помощью `xmlns:xmlPrefix="xmlNamespace"` синтаксис атрибута.</span><span class="sxs-lookup"><span data-stu-id="79a3f-181">You can use global XML namespace prefixes, which you define by using the `Imports` statement, or local prefixes, which you define by using the `xmlns:xmlPrefix="xmlNamespace"` attribute syntax.</span></span> <span data-ttu-id="79a3f-182">Дополнительные сведения см. в разделе [оператор Imports (пространство имен XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="79a3f-182">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
 <span data-ttu-id="79a3f-183">В соответствии с правилами обзора данных для пространства имен XML локальные префиксы имеют приоритет над глобальные префиксы.</span><span class="sxs-lookup"><span data-stu-id="79a3f-183">In accordance with the scoping rules for XML namespaces, local prefixes take precedence over global prefixes.</span></span> <span data-ttu-id="79a3f-184">Тем не менее, если XML-литерал определяет пространство имен XML, что пространство имен недоступно для выражений, отображаемых во внедренном выражении.</span><span class="sxs-lookup"><span data-stu-id="79a3f-184">However, if an XML literal defines an XML namespace, that namespace is not available to expressions that appear in an embedded expression.</span></span> <span data-ttu-id="79a3f-185">Внедренное выражение доступны только глобального пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="79a3f-185">The embedded expression can access only the global XML namespace.</span></span>  
  
 <span data-ttu-id="79a3f-186">Компилятор Visual Basic преобразует каждый глобального пространства имен XML, который используется XML-литерал в одно определение Локальное пространство имен в созданном коде.</span><span class="sxs-lookup"><span data-stu-id="79a3f-186">The Visual Basic compiler converts each global XML namespace that is used by an XML literal into a one local namespace definition in the generated code.</span></span> <span data-ttu-id="79a3f-187">Глобальные пространства имен XML, которые не используются не отображаются в созданном коде.</span><span class="sxs-lookup"><span data-stu-id="79a3f-187">Global XML namespaces that are not used do not appear in the generated code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79a3f-188">Пример</span><span class="sxs-lookup"><span data-stu-id="79a3f-188">Example</span></span>  
 <span data-ttu-id="79a3f-189">В следующем примере демонстрируется создание простой XML-элемент, который имеет два вложенных элемента пустой.</span><span class="sxs-lookup"><span data-stu-id="79a3f-189">The following example shows how to create a simple XML element that has two nested empty elements.</span></span>  
  
 [!code-vb[VbXMLSamples#20](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_1.vb)]  
  
 <span data-ttu-id="79a3f-190">В примере отображается следующий текст.</span><span class="sxs-lookup"><span data-stu-id="79a3f-190">The example displays the following text.</span></span> <span data-ttu-id="79a3f-191">Обратите внимание, что литерал сохраняет структуру пустые элементы.</span><span class="sxs-lookup"><span data-stu-id="79a3f-191">Notice that the literal preserves the structure of the empty elements.</span></span>  
  
```xml  
<outer>  
  <inner1></inner1>  
  <inner2 />  
</outer>  
```  
  
## <a name="example"></a><span data-ttu-id="79a3f-192">Пример</span><span class="sxs-lookup"><span data-stu-id="79a3f-192">Example</span></span>  
 <span data-ttu-id="79a3f-193">В следующем примере показано, как использовать внедренные выражения для имени элемента и создать атрибуты.</span><span class="sxs-lookup"><span data-stu-id="79a3f-193">The following example shows how to use embedded expressions to name an element and create attributes.</span></span>  
  
 [!code-vb[VbXMLSamples#21](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_2.vb)]  
  
 <span data-ttu-id="79a3f-194">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="79a3f-194">This code displays the following text:</span></span>  
  
```xml  
<book isbn="1234" author="My Author" year="1999" title="My Book" />  
```  
  
## <a name="example"></a><span data-ttu-id="79a3f-195">Пример</span><span class="sxs-lookup"><span data-stu-id="79a3f-195">Example</span></span>  
 <span data-ttu-id="79a3f-196">В следующем примере `ns` объявляется как префикс пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="79a3f-196">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="79a3f-197">Затем используется префикс пространства имен для создания литерала XML и отображается конечная форма элемента.</span><span class="sxs-lookup"><span data-stu-id="79a3f-197">It then uses the prefix of the namespace to create an XML literal and displays the element's final form.</span></span>  
  
 [!code-vb[VbXMLSamples#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_3.vb)]  
  
 <span data-ttu-id="79a3f-198">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="79a3f-198">This code displays the following text:</span></span>  
  
```xml  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 <span data-ttu-id="79a3f-199">Обратите внимание, что компилятор преобразует префикс глобального пространства имен XML в определение префикса для пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="79a3f-199">Notice that the compiler converted the prefix of the global XML namespace into a prefix definition for the XML namespace.</span></span> <span data-ttu-id="79a3f-200">\<Ns:middle > элемент переопределяет префикс пространства имен XML для \<ns:inner1 > элемент.</span><span class="sxs-lookup"><span data-stu-id="79a3f-200">The \<ns:middle> element redefines the XML namespace prefix for the \<ns:inner1> element.</span></span> <span data-ttu-id="79a3f-201">Тем не менее \<ns:inner2 > элемент использует пространства имен, определенного в `Imports` инструкции.</span><span class="sxs-lookup"><span data-stu-id="79a3f-201">However, the \<ns:inner2> element uses the namespace defined by the `Imports` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79a3f-202">См. также</span><span class="sxs-lookup"><span data-stu-id="79a3f-202">See Also</span></span>  
 <xref:System.Xml.Linq.XElement>  
 [<span data-ttu-id="79a3f-203">Имена объявленных элементов и атрибутов XML</span><span class="sxs-lookup"><span data-stu-id="79a3f-203">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)  
 [<span data-ttu-id="79a3f-204">XML-литерал комментария</span><span class="sxs-lookup"><span data-stu-id="79a3f-204">XML Comment Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)  
 [<span data-ttu-id="79a3f-205">XML-литерал CDATA</span><span class="sxs-lookup"><span data-stu-id="79a3f-205">XML CDATA Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)  
 [<span data-ttu-id="79a3f-206">XML-литералы</span><span class="sxs-lookup"><span data-stu-id="79a3f-206">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="79a3f-207">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="79a3f-207">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="79a3f-208">Встроенные выражения в XML</span><span class="sxs-lookup"><span data-stu-id="79a3f-208">Embedded Expressions in XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)  
 [<span data-ttu-id="79a3f-209">Оператор Imports (пространство имен XML)</span><span class="sxs-lookup"><span data-stu-id="79a3f-209">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
