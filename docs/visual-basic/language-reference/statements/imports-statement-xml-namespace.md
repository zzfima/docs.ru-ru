---
title: Оператор Imports — пространство имен XML
ms.date: 07/20/2015
f1_keywords:
- vb.ImportsXmlns
helpviewer_keywords:
- XML namespace [Visual Basic], importing
- imports [Visual Basic]
- Imports statement [Visual Basic]
- namespaces [Visual Basic], importing
ms.assetid: 1f4d50a6-08c7-4c2e-8206-ccae35fcd1b4
ms.openlocfilehash: 52864e4d1c8183b6243025e72368d23627049c84
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351053"
---
# <a name="imports-statement-xml-namespace"></a><span data-ttu-id="67b8a-102">Оператор Imports (пространство имен XML)</span><span class="sxs-lookup"><span data-stu-id="67b8a-102">Imports Statement (XML Namespace)</span></span>

<span data-ttu-id="67b8a-103">Импортирует префиксы пространства имен XML для использования в XML-литералах и свойствах осей XML.</span><span class="sxs-lookup"><span data-stu-id="67b8a-103">Imports XML namespace prefixes for use in XML literals and XML axis properties.</span></span>

## <a name="syntax"></a><span data-ttu-id="67b8a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="67b8a-104">Syntax</span></span>

```vb
Imports <xmlns:xmlNamespacePrefix = "xmlNamespaceName">
```

## <a name="parts"></a><span data-ttu-id="67b8a-105">Части</span><span class="sxs-lookup"><span data-stu-id="67b8a-105">Parts</span></span>

`xmlNamespacePrefix`  
<span data-ttu-id="67b8a-106">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="67b8a-106">Optional.</span></span> <span data-ttu-id="67b8a-107">Строка, с помощью которой XML-элементы и атрибуты могут ссылаться на `xmlNamespaceName`.</span><span class="sxs-lookup"><span data-stu-id="67b8a-107">The string by which XML elements and attributes can refer to `xmlNamespaceName`.</span></span> <span data-ttu-id="67b8a-108">Если `xmlNamespacePrefix` не указан, импортированное пространство имен XML является пространством имен XML по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="67b8a-108">If no `xmlNamespacePrefix` is supplied, the imported XML namespace is the default XML namespace.</span></span> <span data-ttu-id="67b8a-109">Должен быть допустимым идентификатором XML.</span><span class="sxs-lookup"><span data-stu-id="67b8a-109">Must be a valid XML identifier.</span></span> <span data-ttu-id="67b8a-110">Дополнительные сведения см. в разделе [Имена объявленных XML-элементов и атрибутов](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="67b8a-110">For more information, see [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>

`xmlNamespaceName`  
<span data-ttu-id="67b8a-111">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="67b8a-111">Required.</span></span> <span data-ttu-id="67b8a-112">Строка, идентифицирующая импортируемое пространство имен XML.</span><span class="sxs-lookup"><span data-stu-id="67b8a-112">The string identifying the XML namespace being imported.</span></span>

## <a name="remarks"></a><span data-ttu-id="67b8a-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="67b8a-113">Remarks</span></span>

<span data-ttu-id="67b8a-114">Можно использовать инструкцию `Imports` для определения глобальных пространств имен XML, которые можно использовать с XML-литералами и свойствами осей XML, или как параметры, передаваемые оператору `GetXmlNamespace`.</span><span class="sxs-lookup"><span data-stu-id="67b8a-114">You can use the `Imports` statement to define global XML namespaces that you can use with XML literals and XML axis properties, or as parameters passed to the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="67b8a-115">(Сведения об использовании оператора `Imports` для импорта псевдонима, который можно использовать при использовании имен типов в коде, см. в разделе [оператор Imports (пространство имен .NET и тип)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).) Синтаксис объявления пространства имен XML с помощью оператора `Imports` идентичен синтаксису, используемому в XML.</span><span class="sxs-lookup"><span data-stu-id="67b8a-115">(For information about using the `Imports` statement to import an alias that can be used where type names are used in your code, see [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).) The syntax for declaring an XML namespace by using the `Imports` statement is identical to the syntax used in XML.</span></span> <span data-ttu-id="67b8a-116">Таким образом, можно скопировать объявление пространства имен из XML-файла и использовать его в инструкции `Imports`.</span><span class="sxs-lookup"><span data-stu-id="67b8a-116">Therefore, you can copy a namespace declaration from an XML file and use it in an `Imports` statement.</span></span>

<span data-ttu-id="67b8a-117">Префиксы пространства имен XML полезны, если требуется многократно создавать XML-элементы из одного и того же пространства имен.</span><span class="sxs-lookup"><span data-stu-id="67b8a-117">XML namespace prefixes are useful when you want to repeatedly create XML elements that are from the same namespace.</span></span> <span data-ttu-id="67b8a-118">Префикс пространства имен XML, объявленный с помощью оператора `Imports`, является глобальным в том смысле, что он доступен для всего кода в файле.</span><span class="sxs-lookup"><span data-stu-id="67b8a-118">The XML namespace prefix declared with the `Imports` statement is global in the sense that it is available to all code in the file.</span></span> <span data-ttu-id="67b8a-119">Его можно использовать при создании литералов XML-элементов и при доступе к свойствам осей XML.</span><span class="sxs-lookup"><span data-stu-id="67b8a-119">You can use it when you create XML element literals and when you access XML axis properties.</span></span> <span data-ttu-id="67b8a-120">Дополнительные сведения см. в разделе [литерал XML-элемента](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) и [Свойства оси XML](../../../visual-basic/language-reference/xml-axis/index.md).</span><span class="sxs-lookup"><span data-stu-id="67b8a-120">For more information, see [XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) and [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/index.md).</span></span>

<span data-ttu-id="67b8a-121">Если определено глобальное пространство имен XML без префикса пространства имен (например, `Imports <xmlns="http://SomeNameSpace>"`), это пространство имен считается пространством имен XML по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="67b8a-121">If you define a global XML namespace without a namespace prefix (for example, `Imports <xmlns="http://SomeNameSpace>"`), that namespace is considered the default XML namespace.</span></span> <span data-ttu-id="67b8a-122">Пространство имен XML по умолчанию используется для любых литералов XML-элементов или свойств оси атрибутов XML, которые явно не задают пространство имен.</span><span class="sxs-lookup"><span data-stu-id="67b8a-122">The default XML namespace is used for any XML element literals or XML attribute axis properties that do not explicitly specify a namespace.</span></span> <span data-ttu-id="67b8a-123">Пространство имен по умолчанию также используется, если указанное пространство имен представляет собой пустое пространство имен (то есть `xmlns=""`).</span><span class="sxs-lookup"><span data-stu-id="67b8a-123">The default namespace is also used if the specified namespace is the empty namespace (that is, `xmlns=""`).</span></span> <span data-ttu-id="67b8a-124">Пространство имен XML по умолчанию не применяется к атрибутам XML в XML-литералах или к свойствам оси атрибутов XML, не имеющим пространства имен.</span><span class="sxs-lookup"><span data-stu-id="67b8a-124">The default XML namespace does not apply to XML attributes in XML literals or to XML attribute axis properties that do not have a namespace.</span></span>

<span data-ttu-id="67b8a-125">Пространства имен XML, определенные в XML-литерале, которые называются *локальными пространствами имен XML*, имеют приоритет над пространствами имен XML, которые определены инструкцией `Imports` как глобальные.</span><span class="sxs-lookup"><span data-stu-id="67b8a-125">XML namespaces that are defined in an XML literal, which are called *local XML namespaces*, take precedence over XML namespaces that are defined by the `Imports` statement as global.</span></span> <span data-ttu-id="67b8a-126">Пространства имен XML, определенные оператором `Imports`, имеют приоритет над пространствами имен XML, импортированными для проекта Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="67b8a-126">XML namespaces that are defined by the `Imports` statement take precedence over XML namespaces imported for a Visual Basic project.</span></span> <span data-ttu-id="67b8a-127">Если XML-литерал определяет пространство имен XML, это локальное пространство имен не применяется к внедренным выражениям.</span><span class="sxs-lookup"><span data-stu-id="67b8a-127">If an XML literal defines an XML namespace, that local namespace does not apply to embedded expressions.</span></span>

<span data-ttu-id="67b8a-128">Глобальные пространства имен XML следуют тем же правилам области и определения, что и .NET Framework пространства имен.</span><span class="sxs-lookup"><span data-stu-id="67b8a-128">Global XML namespaces follow the same scoping and definition rules as .NET Framework namespaces.</span></span> <span data-ttu-id="67b8a-129">В результате можно включить инструкцию `Imports`, чтобы определить глобальное пространство имен XML в любом месте, где можно импортировать пространство имен .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="67b8a-129">As a result, you can include an `Imports` statement to define a global XML namespace anywhere you can import a .NET Framework namespace.</span></span> <span data-ttu-id="67b8a-130">Сюда входят файлы кода и импортированные пространства имен на уровне проекта.</span><span class="sxs-lookup"><span data-stu-id="67b8a-130">This includes both code files and project-level imported namespaces.</span></span> <span data-ttu-id="67b8a-131">Сведения об импортированных пространствах имен на уровне проекта см. в разделе [Страница "ссылки" в конструкторе проектов (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="67b8a-131">For information about project-level imported namespaces, see [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span>

<span data-ttu-id="67b8a-132">Каждый исходный файл может содержать любое количество инструкций `Imports`.</span><span class="sxs-lookup"><span data-stu-id="67b8a-132">Each source file can contain any number of `Imports` statements.</span></span> <span data-ttu-id="67b8a-133">Они должны следовать объявлениям параметров, таким как оператор `Option Strict`, и должны предшествовать объявлениям элементов программирования, таким как `Module` или операторы `Class`.</span><span class="sxs-lookup"><span data-stu-id="67b8a-133">These must follow option declarations, such as the `Option Strict` statement, and they must precede programming element declarations, such as `Module` or `Class` statements.</span></span>

## <a name="example"></a><span data-ttu-id="67b8a-134">Пример</span><span class="sxs-lookup"><span data-stu-id="67b8a-134">Example</span></span>

<span data-ttu-id="67b8a-135">В следующем примере выполняется импорт пространства имен XML по умолчанию и пространства имен XML, определенного префиксом `ns`.</span><span class="sxs-lookup"><span data-stu-id="67b8a-135">The following example imports a default XML namespace and an XML namespace identified with the prefix `ns`.</span></span> <span data-ttu-id="67b8a-136">Затем он создает литералы XML, которые используют оба пространства имен.</span><span class="sxs-lookup"><span data-stu-id="67b8a-136">It then creates XML literals that use both namespaces.</span></span>

[!code-vb[VbXMLSamples#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/Module1.vb#45)]

<span data-ttu-id="67b8a-137">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="67b8a-137">This code displays the following text:</span></span>

```xml
<ns:outer xmlns="http://DefaultNamespace"
          xmlns:ns="http://NewNamespace">
  <ns:innerElement></ns:innerElement>
  <siblingElement></siblingElement>
  <innerElement />
</ns:outer>
```

## <a name="example"></a><span data-ttu-id="67b8a-138">Пример</span><span class="sxs-lookup"><span data-stu-id="67b8a-138">Example</span></span>

<span data-ttu-id="67b8a-139">В следующем примере выполняется импорт префикса пространства имен XML `ns`.</span><span class="sxs-lookup"><span data-stu-id="67b8a-139">The following example imports the XML namespace prefix `ns`.</span></span> <span data-ttu-id="67b8a-140">Затем он создает XML-литерал, использующий префикс пространства имен, и отображает окончательную форму элемента.</span><span class="sxs-lookup"><span data-stu-id="67b8a-140">It then creates an XML literal that uses the namespace prefix and displays the element's final form.</span></span>

[!code-vb[VbXMLSamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples10.vb#22)]

<span data-ttu-id="67b8a-141">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="67b8a-141">This code displays the following text:</span></span>

```xml
<ns:outer xmlns:ns="http://SomeNamespace">
  <ns:middle xmlns:ns="http://NewNamespace">
    <ns:inner1 />
    <inner2 xmlns="http://SomeNamespace" />
  </ns:middle>
</ns:outer>
```

<span data-ttu-id="67b8a-142">Обратите внимание, что компилятор преобразует префикс пространства имен XML из глобального префикса в локальное определение префикса.</span><span class="sxs-lookup"><span data-stu-id="67b8a-142">Notice that the compiler converted the XML namespace prefix from a global prefix to a local prefix definition.</span></span>

## <a name="example"></a><span data-ttu-id="67b8a-143">Пример</span><span class="sxs-lookup"><span data-stu-id="67b8a-143">Example</span></span>

<span data-ttu-id="67b8a-144">В следующем примере выполняется импорт префикса пространства имен XML `ns`.</span><span class="sxs-lookup"><span data-stu-id="67b8a-144">The following example imports the XML namespace prefix `ns`.</span></span> <span data-ttu-id="67b8a-145">Затем префикс пространства имен используется для создания литерала XML и доступа к первому дочернему узлу с полным именем `ns:name`.</span><span class="sxs-lookup"><span data-stu-id="67b8a-145">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name `ns:name`.</span></span>

[!code-vb[VbXMLSamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples8.vb#19)]

<span data-ttu-id="67b8a-146">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="67b8a-146">This code displays the following text:</span></span>

`Patrick Hines`

## <a name="see-also"></a><span data-ttu-id="67b8a-147">См. также</span><span class="sxs-lookup"><span data-stu-id="67b8a-147">See also</span></span>

- [<span data-ttu-id="67b8a-148">XML-литерал элемента</span><span class="sxs-lookup"><span data-stu-id="67b8a-148">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="67b8a-149">Свойства оси XML</span><span class="sxs-lookup"><span data-stu-id="67b8a-149">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="67b8a-150">Имена объявленных элементов и атрибутов XML</span><span class="sxs-lookup"><span data-stu-id="67b8a-150">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [<span data-ttu-id="67b8a-151">Оператор GetXmlNamespace</span><span class="sxs-lookup"><span data-stu-id="67b8a-151">GetXmlNamespace Operator</span></span>](../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)
