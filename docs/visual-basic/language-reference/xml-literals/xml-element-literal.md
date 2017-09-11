---
title: "XML-литерал элемента (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralElement
dev_langs:
- VB
helpviewer_keywords:
- XML element literal [Visual Basic]
- element literal [Visual Basic]
- XML literals [Visual Basic], element
ms.assetid: 95039642-7893-48b7-b23f-45a6c55d8f67
caps.latest.revision: 32
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
ms.openlocfilehash: d5cf769a1e3f668652d1eb4551058deba38a8acf
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="xml-element-literal-visual-basic"></a><span data-ttu-id="16ef3-102">Литеральное представление XML-элемента (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="16ef3-102">XML Element Literal (Visual Basic)</span></span>
<span data-ttu-id="16ef3-103">Литерал, представляющий <xref:System.Xml.Linq.XElement>объекта.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="16ef3-103">A literal that represents an <xref:System.Xml.Linq.XElement> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16ef3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="16ef3-104">Syntax</span></span>  
  
```  
<name [ attributeList ] />  
-or-  
<name [ attributeList ] > [ elementContents ] </[ name ]>  
```  
  
## <a name="parts"></a><span data-ttu-id="16ef3-105">Части</span><span class="sxs-lookup"><span data-stu-id="16ef3-105">Parts</span></span>  
  
-   `<`  
  
     <span data-ttu-id="16ef3-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="16ef3-106">Required.</span></span> <span data-ttu-id="16ef3-107">Открывает начальный тег элемента.</span><span class="sxs-lookup"><span data-stu-id="16ef3-107">Opens the starting element tag.</span></span>  
  
-   `name`  
  
     <span data-ttu-id="16ef3-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="16ef3-108">Required.</span></span> <span data-ttu-id="16ef3-109">Имя элемента.</span><span class="sxs-lookup"><span data-stu-id="16ef3-109">Name of the element.</span></span> <span data-ttu-id="16ef3-110">Формат является одним из следующих:</span><span class="sxs-lookup"><span data-stu-id="16ef3-110">The format is one of the following:</span></span>  
  
    -   <span data-ttu-id="16ef3-111">Литеральный текст для имени элемента формы [`ePrefix``:`]`eName`, где:</span><span class="sxs-lookup"><span data-stu-id="16ef3-111">Literal text for the element name, of the form [`ePrefix``:`]`eName`, where:</span></span>  
  
        |<span data-ttu-id="16ef3-112">Отделение</span><span class="sxs-lookup"><span data-stu-id="16ef3-112">Part</span></span>|<span data-ttu-id="16ef3-113">Описание</span><span class="sxs-lookup"><span data-stu-id="16ef3-113">Description</span></span>|  
        |---|---|  
        |`ePrefix`|<span data-ttu-id="16ef3-114">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="16ef3-114">Optional.</span></span> <span data-ttu-id="16ef3-115">Префикс пространства имен XML для элемента.</span><span class="sxs-lookup"><span data-stu-id="16ef3-115">XML namespace prefix for the element.</span></span> <span data-ttu-id="16ef3-116">Должно быть глобальное пространство имен XML, который определен с `Imports` инструкции в файл или на уровне проекта или локальным пространством имен XML, который определен в этом элементе или родительском элементе.</span><span class="sxs-lookup"><span data-stu-id="16ef3-116">Must be a global XML namespace that is defined with an `Imports` statement in the file or at the project level, or a local XML namespace that is defined in this element or a parent element.</span></span>|  
        |`eName`|<span data-ttu-id="16ef3-117">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="16ef3-117">Required.</span></span> <span data-ttu-id="16ef3-118">Имя элемента.</span><span class="sxs-lookup"><span data-stu-id="16ef3-118">Name of the element.</span></span> <span data-ttu-id="16ef3-119">Формат является одним из следующих:</span><span class="sxs-lookup"><span data-stu-id="16ef3-119">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="16ef3-120">-Текста.</span><span class="sxs-lookup"><span data-stu-id="16ef3-120">-   Literal text.</span></span> <span data-ttu-id="16ef3-121">В разделе [имена элементов и атрибутов XML, объявленные](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="16ef3-121">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="16ef3-122">-Встроенного выражения формы `<%=` e`NameExp` `%>`.</span><span class="sxs-lookup"><span data-stu-id="16ef3-122">-   Embedded expression of the form `<%=` e`NameExp` `%>`.</span></span> <span data-ttu-id="16ef3-123">Тип `eNameExp` должно быть `String` или типа, который неявно преобразуется в <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="16ef3-123">The type of `eNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|  
  
    -   <span data-ttu-id="16ef3-124">Встроенные выражения в форме `<%=` `nameExp` `%>`.</span><span class="sxs-lookup"><span data-stu-id="16ef3-124">Embedded expression of the form `<%=` `nameExp` `%>`.</span></span> <span data-ttu-id="16ef3-125">Тип `nameExp` должно быть `String` или <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> неявное преобразование типа</span><span class="sxs-lookup"><span data-stu-id="16ef3-125">The type of `nameExp` must be `String` or a type implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span> <span data-ttu-id="16ef3-126">Внедренное выражение не допускается в закрывающий тег элемента.</span><span class="sxs-lookup"><span data-stu-id="16ef3-126">An embedded expression is not allowed in a closing tag of an element.</span></span>  
  
-   `attributeList`  
  
     <span data-ttu-id="16ef3-127">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="16ef3-127">Optional.</span></span> <span data-ttu-id="16ef3-128">Список атрибутов, объявленных в литерале.</span><span class="sxs-lookup"><span data-stu-id="16ef3-128">List of attributes declared in the literal.</span></span>  
  
     `attribute [ attribute ... ]`  
  
     <span data-ttu-id="16ef3-129">Каждый `attribute` имеет один из следующих вариантов синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="16ef3-129">Each `attribute` has one of the following syntaxes:</span></span>  
  
    -   <span data-ttu-id="16ef3-130">Назначение формы атрибутов [`aPrefix``:`]`aName``=``aValue`, где:</span><span class="sxs-lookup"><span data-stu-id="16ef3-130">Attribute assignment, of the form [`aPrefix``:`]`aName``=``aValue`, where:</span></span>  
  
        |<span data-ttu-id="16ef3-131">Отделение</span><span class="sxs-lookup"><span data-stu-id="16ef3-131">Part</span></span>|<span data-ttu-id="16ef3-132">Описание</span><span class="sxs-lookup"><span data-stu-id="16ef3-132">Description</span></span>|  
        |---|---|  
        |`aPrefix`|<span data-ttu-id="16ef3-133">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="16ef3-133">Optional.</span></span> <span data-ttu-id="16ef3-134">Префикс пространства имен XML для атрибута.</span><span class="sxs-lookup"><span data-stu-id="16ef3-134">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="16ef3-135">Должно быть глобальное пространство имен XML, который определен с `Imports` инструкции или локальным пространством имен XML, который определен в этом элементе или родительском элементе.</span><span class="sxs-lookup"><span data-stu-id="16ef3-135">Must be a global XML namespace that is defined with an `Imports` statement, or a local XML namespace that is defined in this element or a parent element.</span></span>|  
        |`aName`|<span data-ttu-id="16ef3-136">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="16ef3-136">Required.</span></span> <span data-ttu-id="16ef3-137">Имя атрибута.</span><span class="sxs-lookup"><span data-stu-id="16ef3-137">Name of the attribute.</span></span> <span data-ttu-id="16ef3-138">Формат является одним из следующих:</span><span class="sxs-lookup"><span data-stu-id="16ef3-138">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="16ef3-139">-Текста.</span><span class="sxs-lookup"><span data-stu-id="16ef3-139">-   Literal text.</span></span> <span data-ttu-id="16ef3-140">В разделе [имена элементов и атрибутов XML, объявленные](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="16ef3-140">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="16ef3-141">-Встроенного выражения формы `<%=` `aNameExp` `%>`.</span><span class="sxs-lookup"><span data-stu-id="16ef3-141">-   Embedded expression of the form `<%=` `aNameExp` `%>`.</span></span> <span data-ttu-id="16ef3-142">Тип `aNameExp` должно быть `String` или типа, который неявно преобразуется в <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="16ef3-142">The type of `aNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|  
        |`aValue`|<span data-ttu-id="16ef3-143">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="16ef3-143">Optional.</span></span> <span data-ttu-id="16ef3-144">Значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="16ef3-144">Value of the attribute.</span></span> <span data-ttu-id="16ef3-145">Формат является одним из следующих:</span><span class="sxs-lookup"><span data-stu-id="16ef3-145">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="16ef3-146">-Литеральный текст, заключенный в кавычки.</span><span class="sxs-lookup"><span data-stu-id="16ef3-146">-   Literal text, enclosed in quotation marks.</span></span><br /><span data-ttu-id="16ef3-147">-Встроенного выражения формы `<%=` `aValueExp` `%>`.</span><span class="sxs-lookup"><span data-stu-id="16ef3-147">-   Embedded expression of the form `<%=` `aValueExp` `%>`.</span></span> <span data-ttu-id="16ef3-148">Допустим любой тип.</span><span class="sxs-lookup"><span data-stu-id="16ef3-148">Any type is allowed.</span></span>|  
  
    -   <span data-ttu-id="16ef3-149">Встроенные выражения в форме `<%=` `aExp` `%>`.</span><span class="sxs-lookup"><span data-stu-id="16ef3-149">Embedded expression of the form `<%=` `aExp` `%>`.</span></span>  
  
-   `/>`  
  
     <span data-ttu-id="16ef3-150">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="16ef3-150">Optional.</span></span> <span data-ttu-id="16ef3-151">Указывает, что элемент является пустым элементом без содержимого.</span><span class="sxs-lookup"><span data-stu-id="16ef3-151">Indicates that the element is an empty element, without content.</span></span>  
  
-   `>`  
  
     <span data-ttu-id="16ef3-152">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="16ef3-152">Required.</span></span> <span data-ttu-id="16ef3-153">Завершает начальный или пустым тегом элемента.</span><span class="sxs-lookup"><span data-stu-id="16ef3-153">Ends the beginning or empty element tag.</span></span>  
  
-   `elementContents`  
  
     <span data-ttu-id="16ef3-154">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="16ef3-154">Optional.</span></span> <span data-ttu-id="16ef3-155">Содержимое элемента.</span><span class="sxs-lookup"><span data-stu-id="16ef3-155">Content of the element.</span></span>  
  
     `content [ content ... ]`  
  
     <span data-ttu-id="16ef3-156">Каждая `content` может принимать одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="16ef3-156">Each `content` can be one of the following:</span></span>  
  
    -   <span data-ttu-id="16ef3-157">Обычный текст.</span><span class="sxs-lookup"><span data-stu-id="16ef3-157">Literal text.</span></span> <span data-ttu-id="16ef3-158">Все пробелы в `elementContents` становится значимыми, если любой текст.</span><span class="sxs-lookup"><span data-stu-id="16ef3-158">All the white space in `elementContents` becomes significant if there is any literal text.</span></span>  
  
    -   <span data-ttu-id="16ef3-159">Встроенные выражения в форме `<%=` `contentExp` `%>`.</span><span class="sxs-lookup"><span data-stu-id="16ef3-159">Embedded expression of the form `<%=` `contentExp` `%>`.</span></span>  
  
    -   <span data-ttu-id="16ef3-160">XML-элемент литерала.</span><span class="sxs-lookup"><span data-stu-id="16ef3-160">XML element literal.</span></span>  
  
    -   <span data-ttu-id="16ef3-161">XML-литерал комментария.</span><span class="sxs-lookup"><span data-stu-id="16ef3-161">XML comment literal.</span></span> <span data-ttu-id="16ef3-162">В разделе [XML-литерал комментария](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span><span class="sxs-lookup"><span data-stu-id="16ef3-162">See [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>  
  
    -   <span data-ttu-id="16ef3-163">Литерал инструкции обработки XML.</span><span class="sxs-lookup"><span data-stu-id="16ef3-163">XML processing instruction literal.</span></span> <span data-ttu-id="16ef3-164">В разделе [литерал инструкции обработки XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span><span class="sxs-lookup"><span data-stu-id="16ef3-164">See [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span>  
  
    -   <span data-ttu-id="16ef3-165">Литеральное представление CDATA XML.</span><span class="sxs-lookup"><span data-stu-id="16ef3-165">XML CDATA literal.</span></span> <span data-ttu-id="16ef3-166">В разделе [XML CDATA-литерал](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).</span><span class="sxs-lookup"><span data-stu-id="16ef3-166">See [XML CDATA Literal](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).</span></span>  
  
-   <span data-ttu-id="16ef3-167">`</`[`name`]`>`</span><span class="sxs-lookup"><span data-stu-id="16ef3-167">`</`[`name`]`>`</span></span>  
  
     <span data-ttu-id="16ef3-168">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="16ef3-168">Optional.</span></span> <span data-ttu-id="16ef3-169">Представляет закрывающий тег для элемента.</span><span class="sxs-lookup"><span data-stu-id="16ef3-169">Represents the closing tag for the element.</span></span> <span data-ttu-id="16ef3-170">Необязательный `name` параметра недопустимо, если он является результатом встроенного выражения.</span><span class="sxs-lookup"><span data-stu-id="16ef3-170">The optional `name` parameter is not allowed when it is the result of an embedded expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="16ef3-171">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="16ef3-171">Return Value</span></span>  
 <span data-ttu-id="16ef3-172"><xref:System.Xml.Linq.XElement>Объект.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="16ef3-172">An <xref:System.Xml.Linq.XElement> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16ef3-173">Примечания</span><span class="sxs-lookup"><span data-stu-id="16ef3-173">Remarks</span></span>  
 <span data-ttu-id="16ef3-174">Синтаксис элемента XML можно использовать для создания <xref:System.Xml.Linq.XElement>объектов в коде.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="16ef3-174">You can use the XML element literal syntax to create <xref:System.Xml.Linq.XElement> objects in your code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="16ef3-175">XML-литерал может занимать несколько строк без использования символа продолжения строки.</span><span class="sxs-lookup"><span data-stu-id="16ef3-175">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="16ef3-176">Эта функция позволяет скопировать содержимое из XML-документа и вставьте его непосредственно в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] программы.</span><span class="sxs-lookup"><span data-stu-id="16ef3-176">This feature enables you to copy content from an XML document and paste it directly into a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] program.</span></span>  
  
 <span data-ttu-id="16ef3-177">Встроенные выражения формы `<%=` `exp` `%>` позволяют добавлять динамические данные литерала XML-элемента.</span><span class="sxs-lookup"><span data-stu-id="16ef3-177">Embedded expressions of the form `<%=` `exp` `%>` enable you to add dynamic information to an XML element literal.</span></span> <span data-ttu-id="16ef3-178">Дополнительные сведения см. в разделе [встроенные выражения в XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="16ef3-178">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>  
  
 <span data-ttu-id="16ef3-179">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Компилятор преобразует литералы XML-элементов в вызовы <xref:System.Xml.Linq.XElement.%23ctor%2A>конструктор и, при необходимости, <xref:System.Xml.Linq.XAttribute.%23ctor%2A>конструктор.</xref:System.Xml.Linq.XAttribute.%23ctor%2A> </xref:System.Xml.Linq.XElement.%23ctor%2A></span><span class="sxs-lookup"><span data-stu-id="16ef3-179">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler converts the XML element literal into calls to the <xref:System.Xml.Linq.XElement.%23ctor%2A> constructor and, if it is required, the <xref:System.Xml.Linq.XAttribute.%23ctor%2A> constructor.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="16ef3-180">Пространства имен XML</span><span class="sxs-lookup"><span data-stu-id="16ef3-180">XML Namespaces</span></span>  
 <span data-ttu-id="16ef3-181">Префиксы пространства имен XML полезны в тех случаях, когда необходимо создать XML-литералы с элементами одного пространства имен много раз в коде.</span><span class="sxs-lookup"><span data-stu-id="16ef3-181">XML namespace prefixes are useful when you have to create XML literals with elements from the same namespace many times in code.</span></span> <span data-ttu-id="16ef3-182">Можно использовать глобальные префиксы пространства имен XML, которые можно определить с помощью `Imports` инструкции или локальные префиксы, которые определяются с помощью `xmlns:``xmlPrefix`= «`xmlNamespace`» синтаксис атрибута.</span><span class="sxs-lookup"><span data-stu-id="16ef3-182">You can use global XML namespace prefixes, which you define by using the `Imports` statement, or local prefixes, which you define by using the `xmlns:``xmlPrefix`="`xmlNamespace`" attribute syntax.</span></span> <span data-ttu-id="16ef3-183">Дополнительные сведения см. в разделе [оператор Imports (пространство имен XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="16ef3-183">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
 <span data-ttu-id="16ef3-184">В соответствии с правилами обзора данных для пространства имен XML локальные префиксы имеют приоритет над глобальные префиксы.</span><span class="sxs-lookup"><span data-stu-id="16ef3-184">In accordance with the scoping rules for XML namespaces, local prefixes take precedence over global prefixes.</span></span> <span data-ttu-id="16ef3-185">Тем не менее, если XML-литерал определяет пространство имен XML, что пространство имен недоступно для выражений, отображаемых во внедренном выражении.</span><span class="sxs-lookup"><span data-stu-id="16ef3-185">However, if an XML literal defines an XML namespace, that namespace is not available to expressions that appear in an embedded expression.</span></span> <span data-ttu-id="16ef3-186">Вложенное выражение можно получить доступ к только глобального пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="16ef3-186">The embedded expression can access only the global XML namespace.</span></span>  
  
 <span data-ttu-id="16ef3-187">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Компилятор преобразует каждый глобального пространства имен XML, используется XML-литерал в одно определение Локальное пространство имен в созданном коде.</span><span class="sxs-lookup"><span data-stu-id="16ef3-187">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler converts each global XML namespace that is used by an XML literal into a one local namespace definition in the generated code.</span></span> <span data-ttu-id="16ef3-188">Глобальные пространства имен XML, которые не используются в созданном коде не отображаются.</span><span class="sxs-lookup"><span data-stu-id="16ef3-188">Global XML namespaces that are not used do not appear in the generated code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16ef3-189">Пример</span><span class="sxs-lookup"><span data-stu-id="16ef3-189">Example</span></span>  
 <span data-ttu-id="16ef3-190">В следующем примере демонстрируется создание простой XML-элемент, который имеет два вложенных пустых элемента.</span><span class="sxs-lookup"><span data-stu-id="16ef3-190">The following example shows how to create a simple XML element that has two nested empty elements.</span></span>  
  
 <span data-ttu-id="16ef3-191">[!code-vb[VbXMLSamples&20;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="16ef3-191">[!code-vb[VbXMLSamples#20](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_1.vb)]</span></span>  
  
 <span data-ttu-id="16ef3-192">В примере отображается следующий текст.</span><span class="sxs-lookup"><span data-stu-id="16ef3-192">The example displays the following text.</span></span> <span data-ttu-id="16ef3-193">Обратите внимание, что литерал сохраняет структуру пустых элементов.</span><span class="sxs-lookup"><span data-stu-id="16ef3-193">Notice that the literal preserves the structure of the empty elements.</span></span>  
  
```  
<outer>  
  <inner1></inner1>  
  <inner2 />  
</outer>  
```  
  
## <a name="example"></a><span data-ttu-id="16ef3-194">Пример</span><span class="sxs-lookup"><span data-stu-id="16ef3-194">Example</span></span>  
 <span data-ttu-id="16ef3-195">В следующем примере показано, как использовать внедренные выражения для имени элементу и создания атрибутов.</span><span class="sxs-lookup"><span data-stu-id="16ef3-195">The following example shows how to use embedded expressions to name an element and create attributes.</span></span>  
  
 <span data-ttu-id="16ef3-196">[!code-vb[VbXMLSamples&#21;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="16ef3-196">[!code-vb[VbXMLSamples#21](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_2.vb)]</span></span>  
  
 <span data-ttu-id="16ef3-197">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="16ef3-197">This code displays the following text:</span></span>  
  
```  
<book isbn="1234" author="My Author" year="1999" title="My Book" />  
```  
  
## <a name="example"></a><span data-ttu-id="16ef3-198">Пример</span><span class="sxs-lookup"><span data-stu-id="16ef3-198">Example</span></span>  
 <span data-ttu-id="16ef3-199">В следующем примере `ns` объявляется как префикс пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="16ef3-199">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="16ef3-200">Затем используется префикс пространства имен для создания литерала XML и отображается конечная форма элемента.</span><span class="sxs-lookup"><span data-stu-id="16ef3-200">It then uses the prefix of the namespace to create an XML literal and displays the element's final form.</span></span>  
  
 <span data-ttu-id="16ef3-201">[!code-vb[VbXMLSamples&#22;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="16ef3-201">[!code-vb[VbXMLSamples#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_3.vb)]</span></span>  
  
 <span data-ttu-id="16ef3-202">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="16ef3-202">This code displays the following text:</span></span>  
  
```  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 <span data-ttu-id="16ef3-203">Обратите внимание, что компилятор преобразовал префикс глобального пространства имен XML в определение префикса для пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="16ef3-203">Notice that the compiler converted the prefix of the global XML namespace into a prefix definition for the XML namespace.</span></span> <span data-ttu-id="16ef3-204">\<Ns:middle настроек элемент переопределяет префикс пространства имен XML для \<ns:inner1 настроек элемента.</span><span class="sxs-lookup"><span data-stu-id="16ef3-204">The \<ns:middle> element redefines the XML namespace prefix for the \<ns:inner1> element.</span></span> <span data-ttu-id="16ef3-205">Тем не менее \<ns:inner2 настроек элемент использует пространство имен, определяются `Imports` инструкции.</span><span class="sxs-lookup"><span data-stu-id="16ef3-205">However, the \<ns:inner2> element uses the namespace defined by the `Imports` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16ef3-206">См. также</span><span class="sxs-lookup"><span data-stu-id="16ef3-206">See Also</span></span>  
 <span data-ttu-id="16ef3-207"><xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="16ef3-207"><xref:System.Xml.Linq.XElement></span></span>   
<span data-ttu-id="16ef3-208"> [Имена объявленных элементов и атрибутов](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md) </span><span class="sxs-lookup"><span data-stu-id="16ef3-208"> [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md) </span></span>  
<span data-ttu-id="16ef3-209"> [XML-литерал комментария](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md) </span><span class="sxs-lookup"><span data-stu-id="16ef3-209"> [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md) </span></span>  
<span data-ttu-id="16ef3-210"> [Литерал XML-раздела CDATA](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md) </span><span class="sxs-lookup"><span data-stu-id="16ef3-210"> [XML CDATA Literal](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md) </span></span>  
<span data-ttu-id="16ef3-211"> [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md) </span><span class="sxs-lookup"><span data-stu-id="16ef3-211"> [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md) </span></span>  
<span data-ttu-id="16ef3-212"> [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="16ef3-212"> [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="16ef3-213"> [Встроенные выражения в XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md) </span><span class="sxs-lookup"><span data-stu-id="16ef3-213"> [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md) </span></span>  
<span data-ttu-id="16ef3-214"> [Оператор Imports (пространство имен XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)</span><span class="sxs-lookup"><span data-stu-id="16ef3-214"> [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)</span></span>
