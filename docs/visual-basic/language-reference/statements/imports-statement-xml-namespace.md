---
title: Оператор - Imports пространство имен XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ImportsXmlns
helpviewer_keywords:
- XML namespace [Visual Basic], importing
- imports [Visual Basic]
- Imports statement [Visual Basic]
- namespaces [Visual Basic], importing
ms.assetid: 1f4d50a6-08c7-4c2e-8206-ccae35fcd1b4
ms.openlocfilehash: 51b63a11fd2987d82f9a7599b39d15856a0abb1d
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/25/2018
ms.locfileid: "39243832"
---
# <a name="imports-statement-xml-namespace"></a><span data-ttu-id="dbdbb-102">Оператор Imports (пространство имен XML)</span><span class="sxs-lookup"><span data-stu-id="dbdbb-102">Imports Statement (XML Namespace)</span></span>
<span data-ttu-id="dbdbb-103">Импортирует префиксы пространства имен XML для использования в XML-литералы и свойства оси XML.</span><span class="sxs-lookup"><span data-stu-id="dbdbb-103">Imports XML namespace prefixes for use in XML literals and XML axis properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbdbb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dbdbb-104">Syntax</span></span>  
  
```  
Imports <xmlns:xmlNamespacePrefix = "xmlNamespaceName">  
```  
  
## <a name="parts"></a><span data-ttu-id="dbdbb-105">Части</span><span class="sxs-lookup"><span data-stu-id="dbdbb-105">Parts</span></span>  
 `xmlNamespacePrefix`  
 <span data-ttu-id="dbdbb-106">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="dbdbb-106">Optional.</span></span> <span data-ttu-id="dbdbb-107">Строка, по котором XML элементы и атрибуты можно обращаться к `xmlNamespaceName`.</span><span class="sxs-lookup"><span data-stu-id="dbdbb-107">The string by which XML elements and attributes can refer to `xmlNamespaceName`.</span></span> <span data-ttu-id="dbdbb-108">Если нет `xmlNamespacePrefix` будет указано, импортируемое пространство имен XML — это пространство имен XML по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dbdbb-108">If no `xmlNamespacePrefix` is supplied, the imported XML namespace is the default XML namespace.</span></span> <span data-ttu-id="dbdbb-109">Должен быть допустимым идентификатором XML.</span><span class="sxs-lookup"><span data-stu-id="dbdbb-109">Must be a valid XML identifier.</span></span> <span data-ttu-id="dbdbb-110">Дополнительные сведения см. в разделе [имена объявленных элементов XML и атрибутов](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="dbdbb-110">For more information, see [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>  
  
 `xmlNamespaceName`  
 <span data-ttu-id="dbdbb-111">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="dbdbb-111">Required.</span></span> <span data-ttu-id="dbdbb-112">Строка, идентифицирующая импортируемого пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="dbdbb-112">The string identifying the XML namespace being imported.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dbdbb-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="dbdbb-113">Remarks</span></span>  
 <span data-ttu-id="dbdbb-114">Можно использовать `Imports` инструкции для определения глобальных пространств имен XML, который можно использовать с XML-литералы и свойства оси XML, или в качестве параметров, переданных `GetXmlNamespace` оператор.</span><span class="sxs-lookup"><span data-stu-id="dbdbb-114">You can use the `Imports` statement to define global XML namespaces that you can use with XML literals and XML axis properties, or as parameters passed to the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="dbdbb-115">(Дополнительные сведения об использовании `Imports` инструкцию, чтобы импортировать псевдоним, который может использоваться где имена типов используются в коде, см. в разделе [оператор Imports (пространство имен .NET и тип)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).) Синтаксис объявления пространства имен XML с помощью `Imports` инструкция идентична синтаксисе, используемом в XML.</span><span class="sxs-lookup"><span data-stu-id="dbdbb-115">(For information about using the `Imports` statement to import an alias that can be used where type names are used in your code, see [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).) The syntax for declaring an XML namespace by using the `Imports` statement is identical to the syntax used in XML.</span></span> <span data-ttu-id="dbdbb-116">Таким образом, можно скопировать объявление пространства имен из файла XML и использовать его в `Imports` инструкции.</span><span class="sxs-lookup"><span data-stu-id="dbdbb-116">Therefore, you can copy a namespace declaration from an XML file and use it in an `Imports` statement.</span></span>  
  
 <span data-ttu-id="dbdbb-117">Префиксы пространства имен XML полезны в тех случаях, когда вы хотите повторно создать XML-элементах из одного пространства имен.</span><span class="sxs-lookup"><span data-stu-id="dbdbb-117">XML namespace prefixes are useful when you want to repeatedly create XML elements that are from the same namespace.</span></span> <span data-ttu-id="dbdbb-118">Префикс пространства имен XML объявлен с `Imports` инструкция является глобальным в том смысле, что он доступен на весь код в файле.</span><span class="sxs-lookup"><span data-stu-id="dbdbb-118">The XML namespace prefix declared with the `Imports` statement is global in the sense that it is available to all code in the file.</span></span> <span data-ttu-id="dbdbb-119">Его можно использовать при создании литералов XML-элемента и при доступе к свойства оси XML.</span><span class="sxs-lookup"><span data-stu-id="dbdbb-119">You can use it when you create XML element literals and when you access XML axis properties.</span></span> <span data-ttu-id="dbdbb-120">Дополнительные сведения см. в разделе [литерала элемента XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) и [свойства оси XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md).</span><span class="sxs-lookup"><span data-stu-id="dbdbb-120">For more information, see [XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) and [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md).</span></span>  
  
 <span data-ttu-id="dbdbb-121">Если можно определить глобальное пространство имен XML без префикса пространства имен (например, `Imports <xmlns="http://SomeNameSpace>"`), это пространство имен считается пространство имен XML по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dbdbb-121">If you define a global XML namespace without a namespace prefix (for example, `Imports <xmlns="http://SomeNameSpace>"`), that namespace is considered the default XML namespace.</span></span> <span data-ttu-id="dbdbb-122">Для любого элемента XML-литералов или свойств оси атрибута XML пространство имен явно не указано, используется пространство имен XML по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dbdbb-122">The default XML namespace is used for any XML element literals or XML attribute axis properties that do not explicitly specify a namespace.</span></span> <span data-ttu-id="dbdbb-123">Пространство имен по умолчанию используется также в том случае, если указанное пространство имен является пустое пространство имен (то есть `xmlns=""`).</span><span class="sxs-lookup"><span data-stu-id="dbdbb-123">The default namespace is also used if the specified namespace is the empty namespace (that is, `xmlns=""`).</span></span> <span data-ttu-id="dbdbb-124">Пространство имен XML по умолчанию не применяется к атрибутам XML в XML-литералов или свойств оси атрибута XML, у которых нет пространства имен.</span><span class="sxs-lookup"><span data-stu-id="dbdbb-124">The default XML namespace does not apply to XML attributes in XML literals or to XML attribute axis properties that do not have a namespace.</span></span>  
  
 <span data-ttu-id="dbdbb-125">Пространства имен XML, определенные в XML-литерал, которые называются *локального пространства имен XML*, имеют приоритет над пространств имен XML, которые определяются `Imports` инструкцию как глобальный.</span><span class="sxs-lookup"><span data-stu-id="dbdbb-125">XML namespaces that are defined in an XML literal, which are called *local XML namespaces*, take precedence over XML namespaces that are defined by the `Imports` statement as global.</span></span> <span data-ttu-id="dbdbb-126">Пространства имен XML, которые определяются `Imports` инструкции имеют приоритет над пространства имен XML, импортированные в проекте Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="dbdbb-126">XML namespaces that are defined by the `Imports` statement take precedence over XML namespaces imported for a Visual Basic project.</span></span> <span data-ttu-id="dbdbb-127">Если XML-литерал определяет пространство имен XML, то Локальное пространство имен не применяется к внедренные выражения.</span><span class="sxs-lookup"><span data-stu-id="dbdbb-127">If an XML literal defines an XML namespace, that local namespace does not apply to embedded expressions.</span></span>  
  
 <span data-ttu-id="dbdbb-128">Глобальные пространства имен XML, выполните те же правила области видимости и определения пространства имен .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dbdbb-128">Global XML namespaces follow the same scoping and definition rules as .NET Framework namespaces.</span></span> <span data-ttu-id="dbdbb-129">Таким образом, можно включить `Imports` инструкции для определения глобального пространства имен XML в любом месте, вы можете импортировать пространство имен .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dbdbb-129">As a result, you can include an `Imports` statement to define a global XML namespace anywhere you can import a .NET Framework namespace.</span></span> <span data-ttu-id="dbdbb-130">Сюда входят файлы кода и импортированных пространств имен уровня проекта.</span><span class="sxs-lookup"><span data-stu-id="dbdbb-130">This includes both code files and project-level imported namespaces.</span></span> <span data-ttu-id="dbdbb-131">Сведения о пространствах имен уровня проекта, см. в разделе [страница "ссылки", конструктор проектов (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="dbdbb-131">For information about project-level imported namespaces, see [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="dbdbb-132">Каждый исходный файл может содержать любое количество `Imports` инструкций.</span><span class="sxs-lookup"><span data-stu-id="dbdbb-132">Each source file can contain any number of `Imports` statements.</span></span> <span data-ttu-id="dbdbb-133">Они должны следовать за параметром объявления, такие как `Option Strict` инструкции и они должны указываться до объявлений элементов программирования, таких как `Module` или `Class` инструкций.</span><span class="sxs-lookup"><span data-stu-id="dbdbb-133">These must follow option declarations, such as the `Option Strict` statement, and they must precede programming element declarations, such as `Module` or `Class` statements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dbdbb-134">Пример</span><span class="sxs-lookup"><span data-stu-id="dbdbb-134">Example</span></span>  
 <span data-ttu-id="dbdbb-135">В следующем примере импортируется в пространство имен XML по умолчанию и идентифицировать с помощью префикса пространства имен XML `ns`.</span><span class="sxs-lookup"><span data-stu-id="dbdbb-135">The following example imports a default XML namespace and an XML namespace identified with the prefix `ns`.</span></span> <span data-ttu-id="dbdbb-136">Затем он создает XML-литералов, использующих обоих пространствах имен.</span><span class="sxs-lookup"><span data-stu-id="dbdbb-136">It then creates XML literals that use both namespaces.</span></span>  
  
 [!code-vb[VbXMLSamples#45](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_1.vb)]  
  
 <span data-ttu-id="dbdbb-137">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="dbdbb-137">This code displays the following text:</span></span>  
  
```xml  
<ns:outer xmlns="http://DefaultNamespace"   
          xmlns:ns="http://NewNamespace">  
  <ns:innerElement></ns:innerElement>  
  <siblingElement></siblingElement>  
  <innerElement />  
</ns:outer>  
```  
  
## <a name="example"></a><span data-ttu-id="dbdbb-138">Пример</span><span class="sxs-lookup"><span data-stu-id="dbdbb-138">Example</span></span>  
 <span data-ttu-id="dbdbb-139">В следующем примере выполняется импорт префикс пространства имен XML `ns`.</span><span class="sxs-lookup"><span data-stu-id="dbdbb-139">The following example imports the XML namespace prefix `ns`.</span></span> <span data-ttu-id="dbdbb-140">Затем он создает XML-литерала, использует префикс пространства имен и отображает окончательной форме этого элемента.</span><span class="sxs-lookup"><span data-stu-id="dbdbb-140">It then creates an XML literal that uses the namespace prefix and displays the element's final form.</span></span>  
  
 [!code-vb[VbXMLSamples#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_2.vb)]  
  
 <span data-ttu-id="dbdbb-141">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="dbdbb-141">This code displays the following text:</span></span>  
  
```xml  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 <span data-ttu-id="dbdbb-142">Обратите внимание на то, что компилятор преобразует префикс пространства имен XML из глобального префикса определение локального префикса.</span><span class="sxs-lookup"><span data-stu-id="dbdbb-142">Notice that the compiler converted the XML namespace prefix from a global prefix to a local prefix definition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dbdbb-143">Пример</span><span class="sxs-lookup"><span data-stu-id="dbdbb-143">Example</span></span>  
 <span data-ttu-id="dbdbb-144">В следующем примере выполняется импорт префикс пространства имен XML `ns`.</span><span class="sxs-lookup"><span data-stu-id="dbdbb-144">The following example imports the XML namespace prefix `ns`.</span></span> <span data-ttu-id="dbdbb-145">Затем префикс пространства имен используется для создания литерала XML и доступа к первому дочернему узлу с полным именем `ns:name`.</span><span class="sxs-lookup"><span data-stu-id="dbdbb-145">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name `ns:name`.</span></span>  
  
 [!code-vb[VbXMLSamples#19](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_3.vb)]  
  
 <span data-ttu-id="dbdbb-146">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="dbdbb-146">This code displays the following text:</span></span>  
  
 `Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="dbdbb-147">См. также</span><span class="sxs-lookup"><span data-stu-id="dbdbb-147">See Also</span></span>  
 [<span data-ttu-id="dbdbb-148">XML-литерал элемента</span><span class="sxs-lookup"><span data-stu-id="dbdbb-148">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [<span data-ttu-id="dbdbb-149">Свойства оси XML</span><span class="sxs-lookup"><span data-stu-id="dbdbb-149">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [<span data-ttu-id="dbdbb-150">Имена объявленных элементов и атрибутов XML</span><span class="sxs-lookup"><span data-stu-id="dbdbb-150">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)  
 [<span data-ttu-id="dbdbb-151">Оператор GetXmlNamespace</span><span class="sxs-lookup"><span data-stu-id="dbdbb-151">GetXmlNamespace Operator</span></span>](../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)
