---
title: "Свойство дочерней оси XML (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyChildAxis
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 89a59d00-985e-4f5c-b59f-29b47bad11cb
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
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2ccdacdadf219b9c928558f07e0890be6471d40a
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="xml-child-axis-property-visual-basic"></a><span data-ttu-id="419ad-102">Свойство дочерней оси XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="419ad-102">XML Child Axis Property (Visual Basic)</span></span>
<span data-ttu-id="419ad-103">Предоставляет доступ к дочерним элементам одного из следующих действий: <xref:System.Xml.Linq.XElement>объекта <xref:System.Xml.Linq.XDocument>объекта, набор <xref:System.Xml.Linq.XElement>объекты или коллекции <xref:System.Xml.Linq.XDocument>объектов.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="419ad-103">Provides access to the children of one of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="419ad-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="419ad-104">Syntax</span></span>  
  
```  
  
object.<child>  
```  
  
## <a name="parts"></a><span data-ttu-id="419ad-105">Части</span><span class="sxs-lookup"><span data-stu-id="419ad-105">Parts</span></span>  
  
|<span data-ttu-id="419ad-106">Термин</span><span class="sxs-lookup"><span data-stu-id="419ad-106">Term</span></span>|<span data-ttu-id="419ad-107">Определение</span><span class="sxs-lookup"><span data-stu-id="419ad-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="419ad-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="419ad-108">Required.</span></span> <span data-ttu-id="419ad-109"><xref:System.Xml.Linq.XElement>Объекта <xref:System.Xml.Linq.XDocument>объекта, набор <xref:System.Xml.Linq.XElement>объекты или коллекции <xref:System.Xml.Linq.XDocument>объектов.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="419ad-109">An <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>|  
|<span data-ttu-id="419ad-110">.<</span><span class="sxs-lookup"><span data-stu-id="419ad-110">.<</span></span>|<span data-ttu-id="419ad-111">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="419ad-111">Required.</span></span> <span data-ttu-id="419ad-112">Обозначает начало свойства дочерней оси.</span><span class="sxs-lookup"><span data-stu-id="419ad-112">Denotes the start of a child axis property.</span></span>|  
|`child`|<span data-ttu-id="419ad-113">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="419ad-113">Required.</span></span> <span data-ttu-id="419ad-114">Имя дочерних узлов для доступа, формы [`prefix``:`]`name`.</span><span class="sxs-lookup"><span data-stu-id="419ad-114">Name of the child nodes to access, of the form [`prefix``:`]`name`.</span></span><br /><br /><span data-ttu-id="419ad-115"> -   `Prefix`— Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="419ad-115"> -   `Prefix` - Optional.</span></span> <span data-ttu-id="419ad-116">Префикс пространства имен XML для дочернего узла.</span><span class="sxs-lookup"><span data-stu-id="419ad-116">XML namespace prefix for the child node.</span></span> <span data-ttu-id="419ad-117">Должно быть глобальным пространством имен XML, определенным с помощью оператора `Imports`.</span><span class="sxs-lookup"><span data-stu-id="419ad-117">Must be a global XML namespace defined with an `Imports` statement.</span></span><br /><span data-ttu-id="419ad-118">-   `Name`— Обязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="419ad-118">-   `Name` - Required.</span></span> <span data-ttu-id="419ad-119">Имя локального дочернего узла.</span><span class="sxs-lookup"><span data-stu-id="419ad-119">Local child node name.</span></span> <span data-ttu-id="419ad-120">В разделе [имена элементов и атрибутов XML, объявленные](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="419ad-120">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
|>|<span data-ttu-id="419ad-121">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="419ad-121">Required.</span></span> <span data-ttu-id="419ad-122">Обозначает конец свойства дочерней оси.</span><span class="sxs-lookup"><span data-stu-id="419ad-122">Denotes the end of a child axis property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="419ad-123">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="419ad-123">Return Value</span></span>  
 <span data-ttu-id="419ad-124">Коллекция <xref:System.Xml.Linq.XElement>объектов.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="419ad-124">A collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="419ad-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="419ad-125">Remarks</span></span>  
 <span data-ttu-id="419ad-126">Свойство дочерней оси XML можно использовать для доступа к дочерние узлы по имени из <xref:System.Xml.Linq.XElement>или <xref:System.Xml.Linq.XDocument>объект, или из коллекции <xref:System.Xml.Linq.XElement>или <xref:System.Xml.Linq.XDocument>объектов.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="419ad-126">You can use an XML child axis property to access child nodes by name from an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object, or from a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="419ad-127">Используйте XML-свойство `Value` для доступа к значению первого дочернего узла в возвращаемой коллекции.</span><span class="sxs-lookup"><span data-stu-id="419ad-127">Use the XML `Value` property to access the value of the first child node in the returned collection.</span></span> <span data-ttu-id="419ad-128">Дополнительные сведения см. в разделе [свойство значения XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="419ad-128">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
 <span data-ttu-id="419ad-129">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Компилятор преобразует свойства дочерней оси вызовы <xref:System.Xml.Linq.XContainer.Elements%2A>метод.</xref:System.Xml.Linq.XContainer.Elements%2A></span><span class="sxs-lookup"><span data-stu-id="419ad-129">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler converts child axis properties to calls to the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="419ad-130">Пространства имен XML</span><span class="sxs-lookup"><span data-stu-id="419ad-130">XML Namespaces</span></span>  
 <span data-ttu-id="419ad-131">Имя в свойстве дочерней оси может использовать только префиксы пространства имен XML, объявленные глобально с помощью метода `Imports`.</span><span class="sxs-lookup"><span data-stu-id="419ad-131">The name in a child axis property can use only XML namespace prefixes declared globally with the `Imports` statement.</span></span> <span data-ttu-id="419ad-132">В нем нельзя использовать префиксы пространства имен XML, объявленные локально с помощью литералов XML-элемента.</span><span class="sxs-lookup"><span data-stu-id="419ad-132">It cannot use XML namespace prefixes declared locally within XML element literals.</span></span> <span data-ttu-id="419ad-133">Дополнительные сведения см. в разделе [оператор Imports (пространство имен XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="419ad-133">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="419ad-134">Пример</span><span class="sxs-lookup"><span data-stu-id="419ad-134">Example</span></span>  
 <span data-ttu-id="419ad-135">В следующем примере показано, как получить доступ к дочерним узлам `phone` из объекта `contact`.</span><span class="sxs-lookup"><span data-stu-id="419ad-135">The following example shows how to access the child nodes named `phone` from the `contact` object.</span></span>  
  
 <span data-ttu-id="419ad-136">[!code-vb[VbXMLSamples&17;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="419ad-136">[!code-vb[VbXMLSamples#17](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_1.vb)]</span></span>  
  
 <span data-ttu-id="419ad-137">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="419ad-137">This code displays the following text:</span></span>  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="419ad-138">Пример</span><span class="sxs-lookup"><span data-stu-id="419ad-138">Example</span></span>  
 <span data-ttu-id="419ad-139">В следующем примере показано, как получить доступ к дочерним узлам с именем `phone` из коллекции, возвращенной свойством дочерней оси `contact` объекта `contacts`.</span><span class="sxs-lookup"><span data-stu-id="419ad-139">The following example shows how to access the child nodes named `phone` from the collection returned by the `contact` child axis property of the `contacts` object.</span></span>  
  
 <span data-ttu-id="419ad-140">[!code-vb[VbXMLSamples&18;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="419ad-140">[!code-vb[VbXMLSamples#18](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_2.vb)]</span></span>  
  
 <span data-ttu-id="419ad-141">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="419ad-141">This code displays the following text:</span></span>  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="419ad-142">Пример</span><span class="sxs-lookup"><span data-stu-id="419ad-142">Example</span></span>  
 <span data-ttu-id="419ad-143">В следующем примере `ns` объявляется как префикс пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="419ad-143">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="419ad-144">Затем префикс пространства имен используется для создания литерала XML и доступа к первому дочернему узлу с полным именем `ns:name`.</span><span class="sxs-lookup"><span data-stu-id="419ad-144">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name `ns:name`.</span></span>  
  
 <span data-ttu-id="419ad-145">[!code-vb[VbXMLSamples&19;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="419ad-145">[!code-vb[VbXMLSamples#19](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_3.vb)]</span></span>  
  
 <span data-ttu-id="419ad-146">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="419ad-146">This code displays the following text:</span></span>  
  
 `Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="419ad-147">См. также</span><span class="sxs-lookup"><span data-stu-id="419ad-147">See Also</span></span>  
 <span data-ttu-id="419ad-148"><xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="419ad-148"><xref:System.Xml.Linq.XElement></span></span>   
<span data-ttu-id="419ad-149"> [Свойства оси XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md) </span><span class="sxs-lookup"><span data-stu-id="419ad-149"> [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md) </span></span>  
<span data-ttu-id="419ad-150"> [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md) </span><span class="sxs-lookup"><span data-stu-id="419ad-150"> [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md) </span></span>  
<span data-ttu-id="419ad-151"> [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="419ad-151"> [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="419ad-152"> [Имена объявленных элементов и атрибутов XML](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)</span><span class="sxs-lookup"><span data-stu-id="419ad-152"> [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)</span></span>
