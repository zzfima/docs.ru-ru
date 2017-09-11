---
title: "Оператор Imports (пространство имен XML) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ImportsXmlns
dev_langs:
- VB
helpviewer_keywords:
- XML namespace [Visual Basic], importing
- imports [Visual Basic]
- Imports statement [Visual Basic]
- namespaces [Visual Basic], importing
ms.assetid: 1f4d50a6-08c7-4c2e-8206-ccae35fcd1b4
caps.latest.revision: 18
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
ms.sourcegitcommit: a32f50ce8a92fa22d9627a1510a4b3ec1087364e
ms.openlocfilehash: 66ac2bd947328dab9df812709525b43fb27145ac
ms.contentlocale: ru-ru
ms.lasthandoff: 06/01/2017

---
# <a name="imports-statement-xml-namespace"></a><span data-ttu-id="fad45-102">Оператор Imports (пространство имен XML)</span><span class="sxs-lookup"><span data-stu-id="fad45-102">Imports Statement (XML Namespace)</span></span>
<span data-ttu-id="fad45-103">Импортирует префиксы пространства имен XML для использования в XML-литералы и свойства оси XML.</span><span class="sxs-lookup"><span data-stu-id="fad45-103">Imports XML namespace prefixes for use in XML literals and XML axis properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fad45-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fad45-104">Syntax</span></span>  
  
```  
Imports <xmlns:xmlNamespacePrefix = "xmlNamespaceName">  
```  
  
## <a name="parts"></a><span data-ttu-id="fad45-105">Части</span><span class="sxs-lookup"><span data-stu-id="fad45-105">Parts</span></span>  
 `xmlNamespacePrefix`  
 <span data-ttu-id="fad45-106">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="fad45-106">Optional.</span></span> <span data-ttu-id="fad45-107">Строка, по которой XML элементы и атрибуты можно обращаться к `xmlNamespaceName`.</span><span class="sxs-lookup"><span data-stu-id="fad45-107">The string by which XML elements and attributes can refer to `xmlNamespaceName`.</span></span> <span data-ttu-id="fad45-108">Если не `xmlNamespacePrefix` будет указано, импортируемое пространство имен XML — пространство имен XML по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fad45-108">If no `xmlNamespacePrefix` is supplied, the imported XML namespace is the default XML namespace.</span></span> <span data-ttu-id="fad45-109">Должен быть допустимым идентификатором XML.</span><span class="sxs-lookup"><span data-stu-id="fad45-109">Must be a valid XML identifier.</span></span> <span data-ttu-id="fad45-110">Дополнительные сведения см. в разделе [имена объявленных элементов XML и атрибутов](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="fad45-110">For more information, see [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>  
  
 `xmlNamespaceName`  
 <span data-ttu-id="fad45-111">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="fad45-111">Required.</span></span> <span data-ttu-id="fad45-112">Строка, определяющая импортируемого пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="fad45-112">The string identifying the XML namespace being imported.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fad45-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="fad45-113">Remarks</span></span>  
 <span data-ttu-id="fad45-114">Можно использовать `Imports` инструкции для определения глобального пространства имен XML, который можно использовать с XML-литералы и свойства оси XML, а также параметры, передаваемые `GetXmlNamespace` оператор.</span><span class="sxs-lookup"><span data-stu-id="fad45-114">You can use the `Imports` statement to define global XML namespaces that you can use with XML literals and XML axis properties, or as parameters passed to the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="fad45-115">(Дополнительные сведения об использовании `Imports` statement, чтобы импортировать псевдоним, который можно использовать, где используются имена типов в коде, в разделе [оператор Imports (пространство имен .NET и тип)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).) Синтаксис объявления пространства имен XML с помощью `Imports` инструкции идентичен синтаксису, используемому в формате XML.</span><span class="sxs-lookup"><span data-stu-id="fad45-115">(For information about using the `Imports` statement to import an alias that can be used where type names are used in your code, see [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).) The syntax for declaring an XML namespace by using the `Imports` statement is identical to the syntax used in XML.</span></span> <span data-ttu-id="fad45-116">Таким образом, можно скопировать объявление пространства имен из XML-файла и использовать его в `Imports` инструкции.</span><span class="sxs-lookup"><span data-stu-id="fad45-116">Therefore, you can copy a namespace declaration from an XML file and use it in an `Imports` statement.</span></span>  
  
 <span data-ttu-id="fad45-117">Префиксы пространства имен XML полезны, когда требуется повторно создать элементы XML, которые находятся в том же пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="fad45-117">XML namespace prefixes are useful when you want to repeatedly create XML elements that are from the same namespace.</span></span> <span data-ttu-id="fad45-118">Префикс пространства имен XML, объявленные с `Imports` инструкция является глобальным в том смысле, что он доступен всему коду в файле.</span><span class="sxs-lookup"><span data-stu-id="fad45-118">The XML namespace prefix declared with the `Imports` statement is global in the sense that it is available to all code in the file.</span></span> <span data-ttu-id="fad45-119">Его можно использовать при создании литералов XML-элемента и при доступе к свойствам осей XML.</span><span class="sxs-lookup"><span data-stu-id="fad45-119">You can use it when you create XML element literals and when you access XML axis properties.</span></span> <span data-ttu-id="fad45-120">Дополнительные сведения см. в разделе [литерала XML элемент](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) и [свойства оси XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md).</span><span class="sxs-lookup"><span data-stu-id="fad45-120">For more information, see [XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) and [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md).</span></span>  
  
 <span data-ttu-id="fad45-121">Если можно определить глобальное пространство имен XML без префикса пространства имен (например, `Imports <xmlns="http://SomeNameSpace>"`), такое пространство рассматривается как пространство имен XML по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fad45-121">If you define a global XML namespace without a namespace prefix (for example, `Imports <xmlns="http://SomeNameSpace>"`), that namespace is considered the default XML namespace.</span></span> <span data-ttu-id="fad45-122">Пространство имен XML по умолчанию используется для любого элемента XML-литералов или свойств оси атрибута XML, которых явно не указано пространство имен.</span><span class="sxs-lookup"><span data-stu-id="fad45-122">The default XML namespace is used for any XML element literals or XML attribute axis properties that do not explicitly specify a namespace.</span></span> <span data-ttu-id="fad45-123">Пространство имен по умолчанию также используется, если указанного пространства имен является пустое пространство имен (то есть, `xmlns=""`).</span><span class="sxs-lookup"><span data-stu-id="fad45-123">The default namespace is also used if the specified namespace is the empty namespace (that is, `xmlns=""`).</span></span> <span data-ttu-id="fad45-124">Пространство имен XML по умолчанию не применяется для атрибутов XML в XML-литералов или свойства оси атрибута XML, у которых нет пространства имен.</span><span class="sxs-lookup"><span data-stu-id="fad45-124">The default XML namespace does not apply to XML attributes in XML literals or to XML attribute axis properties that do not have a namespace.</span></span>  
  
 <span data-ttu-id="fad45-125">Пространства имен XML, определенные в XML-литерал, который называются *локальными пространствами имен XML*, имеют приоритет над пространствами имен XML, определяются `Imports` инструкции в качестве глобальных.</span><span class="sxs-lookup"><span data-stu-id="fad45-125">XML namespaces that are defined in an XML literal, which are called *local XML namespaces*, take precedence over XML namespaces that are defined by the `Imports` statement as global.</span></span> <span data-ttu-id="fad45-126">Пространства имен XML, который определен с `Imports` инструкции имеют приоритет над пространствами имен XML, импортированные для проекта Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="fad45-126">XML namespaces that are defined by the `Imports` statement take precedence over XML namespaces imported for a Visual Basic project.</span></span> <span data-ttu-id="fad45-127">Если XML-литерал определяет пространство имен XML, то Локальное пространство имен неприменимо к внедренные выражения.</span><span class="sxs-lookup"><span data-stu-id="fad45-127">If an XML literal defines an XML namespace, that local namespace does not apply to embedded expressions.</span></span>  
  
 <span data-ttu-id="fad45-128">Глобальные пространства имен XML, выполните те же правила области видимости и определения пространства имен .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fad45-128">Global XML namespaces follow the same scoping and definition rules as .NET Framework namespaces.</span></span> <span data-ttu-id="fad45-129">В результате можно включить `Imports` инструкции для определения глобального пространства имен XML в любом месте можно импортировать пространство имен .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fad45-129">As a result, you can include an `Imports` statement to define a global XML namespace anywhere you can import a .NET Framework namespace.</span></span> <span data-ttu-id="fad45-130">Это включает файлы кода и импортированные пространства имен на уровне проекта.</span><span class="sxs-lookup"><span data-stu-id="fad45-130">This includes both code files and project-level imported namespaces.</span></span> <span data-ttu-id="fad45-131">Сведения о пространствах имен уровня проекта см. в разделе [страница "ссылки" в конструкторе проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="fad45-131">For information about project-level imported namespaces, see [References Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="fad45-132">Каждый исходный файл может содержать любое количество `Imports` инструкции.</span><span class="sxs-lookup"><span data-stu-id="fad45-132">Each source file can contain any number of `Imports` statements.</span></span> <span data-ttu-id="fad45-133">Они должны следовать за параметром объявления, такие как `Option Strict` инструкции и они должны предшествовать объявления элементов программирования, таких как `Module` или `Class` инструкции.</span><span class="sxs-lookup"><span data-stu-id="fad45-133">These must follow option declarations, such as the `Option Strict` statement, and they must precede programming element declarations, such as `Module` or `Class` statements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fad45-134">Пример</span><span class="sxs-lookup"><span data-stu-id="fad45-134">Example</span></span>  
 <span data-ttu-id="fad45-135">В следующем примере импортируется пространство имен XML по умолчанию и определить префикс пространства имен XML `ns`.</span><span class="sxs-lookup"><span data-stu-id="fad45-135">The following example imports a default XML namespace and an XML namespace identified with the prefix `ns`.</span></span> <span data-ttu-id="fad45-136">Затем он создает XML-литералы, использующие оба пространства имен.</span><span class="sxs-lookup"><span data-stu-id="fad45-136">It then creates XML literals that use both namespaces.</span></span>  
  
 <span data-ttu-id="fad45-137">[!code-vb[VbXMLSamples&#45;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="fad45-137">[!code-vb[VbXMLSamples#45](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_1.vb)]</span></span>  
  
 <span data-ttu-id="fad45-138">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="fad45-138">This code displays the following text:</span></span>  
  
```xml  
<ns:outer xmlns="http://DefaultNamespace"   
          xmlns:ns="http://NewNamespace">  
  <ns:innerElement></ns:innerElement>  
  <siblingElement></siblingElement>  
  <innerElement />  
</ns:outer>  
```  
  
## <a name="example"></a><span data-ttu-id="fad45-139">Пример</span><span class="sxs-lookup"><span data-stu-id="fad45-139">Example</span></span>  
 <span data-ttu-id="fad45-140">В следующем примере импортируется префикс пространства имен XML `ns`.</span><span class="sxs-lookup"><span data-stu-id="fad45-140">The following example imports the XML namespace prefix `ns`.</span></span> <span data-ttu-id="fad45-141">Затем он создает XML-литерал, использует префикс пространства имен и отображается конечная форма элемента.</span><span class="sxs-lookup"><span data-stu-id="fad45-141">It then creates an XML literal that uses the namespace prefix and displays the element's final form.</span></span>  
  
 <span data-ttu-id="fad45-142">[!code-vb[VbXMLSamples&#22;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="fad45-142">[!code-vb[VbXMLSamples#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_2.vb)]</span></span>  
  
 <span data-ttu-id="fad45-143">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="fad45-143">This code displays the following text:</span></span>  
  
```xml  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 <span data-ttu-id="fad45-144">Обратите внимание, что компилятор преобразует префикс пространства имен XML из глобального префикса в определение локального префикса.</span><span class="sxs-lookup"><span data-stu-id="fad45-144">Notice that the compiler converted the XML namespace prefix from a global prefix to a local prefix definition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fad45-145">Пример</span><span class="sxs-lookup"><span data-stu-id="fad45-145">Example</span></span>  
 <span data-ttu-id="fad45-146">В следующем примере импортируется префикс пространства имен XML `ns`.</span><span class="sxs-lookup"><span data-stu-id="fad45-146">The following example imports the XML namespace prefix `ns`.</span></span> <span data-ttu-id="fad45-147">Затем префикс пространства имен используется для создания литерала XML и доступа к первому дочернему узлу с полным именем `ns:name`.</span><span class="sxs-lookup"><span data-stu-id="fad45-147">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name `ns:name`.</span></span>  
  
 <span data-ttu-id="fad45-148">[!code-vb[VbXMLSamples&19;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="fad45-148">[!code-vb[VbXMLSamples#19](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_3.vb)]</span></span>  
  
 <span data-ttu-id="fad45-149">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="fad45-149">This code displays the following text:</span></span>  
  
 `Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="fad45-150">См. также</span><span class="sxs-lookup"><span data-stu-id="fad45-150">See Also</span></span>  
 <span data-ttu-id="fad45-151">[Литеральное представление XML элемента](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span><span class="sxs-lookup"><span data-stu-id="fad45-151">[XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span></span>  
<span data-ttu-id="fad45-152"> [Свойства оси XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md) </span><span class="sxs-lookup"><span data-stu-id="fad45-152"> [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md) </span></span>  
<span data-ttu-id="fad45-153"> [Имена объявленных элементов и атрибутов](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md) </span><span class="sxs-lookup"><span data-stu-id="fad45-153"> [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md) </span></span>  
<span data-ttu-id="fad45-154"> [Оператор GetXmlNamespace](../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)</span><span class="sxs-lookup"><span data-stu-id="fad45-154"> [GetXmlNamespace Operator](../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)</span></span>
