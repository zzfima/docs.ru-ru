---
title: Свойство дочерней оси XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyChildAxis
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 89a59d00-985e-4f5c-b59f-29b47bad11cb
ms.openlocfilehash: 8f8283e7ed09e657a20addab0b203b3d99420d3a
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58838818"
---
# <a name="xml-child-axis-property-visual-basic"></a><span data-ttu-id="fcae0-102">Свойство дочерней оси XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fcae0-102">XML Child Axis Property (Visual Basic)</span></span>
<span data-ttu-id="fcae0-103">Предоставляет доступ к дочерним элементам одного из следующих: объекта <xref:System.Xml.Linq.XElement>, объекта <xref:System.Xml.Linq.XDocument>, коллекции объектов <xref:System.Xml.Linq.XElement> или коллекции объектов <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="fcae0-103">Provides access to the children of one of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcae0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fcae0-104">Syntax</span></span>  
  
```  
object.<child>  
```  
  
## <a name="parts"></a><span data-ttu-id="fcae0-105">Части</span><span class="sxs-lookup"><span data-stu-id="fcae0-105">Parts</span></span>  
  
|<span data-ttu-id="fcae0-106">Термин</span><span class="sxs-lookup"><span data-stu-id="fcae0-106">Term</span></span>|<span data-ttu-id="fcae0-107">Определение</span><span class="sxs-lookup"><span data-stu-id="fcae0-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="fcae0-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="fcae0-108">Required.</span></span> <span data-ttu-id="fcae0-109">Объект <xref:System.Xml.Linq.XElement>, объект <xref:System.Xml.Linq.XDocument>, коллекция объектов <xref:System.Xml.Linq.XElement> или коллекция объектов <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="fcae0-109">An <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>|  
|<span data-ttu-id="fcae0-110">.<</span><span class="sxs-lookup"><span data-stu-id="fcae0-110">.<</span></span>|<span data-ttu-id="fcae0-111">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="fcae0-111">Required.</span></span> <span data-ttu-id="fcae0-112">Обозначает начало свойства дочерней оси.</span><span class="sxs-lookup"><span data-stu-id="fcae0-112">Denotes the start of a child axis property.</span></span>|  
|`child`|<span data-ttu-id="fcae0-113">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="fcae0-113">Required.</span></span> <span data-ttu-id="fcae0-114">Имя дочерних узлов для доступа к формы [`prefix:]name`.</span><span class="sxs-lookup"><span data-stu-id="fcae0-114">Name of the child nodes to access, of the form [`prefix:]name`.</span></span><br /><br /> <span data-ttu-id="fcae0-115">-   `Prefix` -Необязательно.</span><span class="sxs-lookup"><span data-stu-id="fcae0-115">-   `Prefix` - Optional.</span></span> <span data-ttu-id="fcae0-116">Префикс пространства имен XML для дочернего узла.</span><span class="sxs-lookup"><span data-stu-id="fcae0-116">XML namespace prefix for the child node.</span></span> <span data-ttu-id="fcae0-117">Должно быть глобальным пространством имен XML, определенным с помощью оператора `Imports`.</span><span class="sxs-lookup"><span data-stu-id="fcae0-117">Must be a global XML namespace defined with an `Imports` statement.</span></span><br /><span data-ttu-id="fcae0-118">-   `Name` -Required.</span><span class="sxs-lookup"><span data-stu-id="fcae0-118">-   `Name` - Required.</span></span> <span data-ttu-id="fcae0-119">Имя локального дочернего узла.</span><span class="sxs-lookup"><span data-stu-id="fcae0-119">Local child node name.</span></span> <span data-ttu-id="fcae0-120">См. в разделе [имена объявленных элементов и атрибутов](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="fcae0-120">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
|>|<span data-ttu-id="fcae0-121">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="fcae0-121">Required.</span></span> <span data-ttu-id="fcae0-122">Обозначает конец свойства дочерней оси.</span><span class="sxs-lookup"><span data-stu-id="fcae0-122">Denotes the end of a child axis property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="fcae0-123">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fcae0-123">Return Value</span></span>  
 <span data-ttu-id="fcae0-124">Коллекция объектов <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="fcae0-124">A collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fcae0-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="fcae0-125">Remarks</span></span>  
 <span data-ttu-id="fcae0-126">Свойство дочерней оси XML можно использовать для доступа к дочерним узлам по имени из объекта <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument> или из коллекции объектов <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="fcae0-126">You can use an XML child axis property to access child nodes by name from an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object, or from a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="fcae0-127">Используйте XML-свойство `Value` для доступа к значению первого дочернего узла в возвращаемой коллекции.</span><span class="sxs-lookup"><span data-stu-id="fcae0-127">Use the XML `Value` property to access the value of the first child node in the returned collection.</span></span> <span data-ttu-id="fcae0-128">Дополнительные сведения см. в разделе [свойство значения XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="fcae0-128">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
 <span data-ttu-id="fcae0-129">Компилятор Visual Basic преобразует свойства дочерней оси для вызовов <xref:System.Xml.Linq.XContainer.Elements%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="fcae0-129">The Visual Basic compiler converts child axis properties to calls to the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="fcae0-130">Пространства имен XML</span><span class="sxs-lookup"><span data-stu-id="fcae0-130">XML Namespaces</span></span>  
 <span data-ttu-id="fcae0-131">Имя в свойстве дочерней оси может использовать только префиксы пространства имен XML, объявленные глобально с помощью метода `Imports`.</span><span class="sxs-lookup"><span data-stu-id="fcae0-131">The name in a child axis property can use only XML namespace prefixes declared globally with the `Imports` statement.</span></span> <span data-ttu-id="fcae0-132">В нем нельзя использовать префиксы пространства имен XML, объявленные локально с помощью литералов XML-элемента.</span><span class="sxs-lookup"><span data-stu-id="fcae0-132">It cannot use XML namespace prefixes declared locally within XML element literals.</span></span> <span data-ttu-id="fcae0-133">Дополнительные сведения см. в разделе [оператор Imports (пространство имен XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="fcae0-133">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fcae0-134">Пример</span><span class="sxs-lookup"><span data-stu-id="fcae0-134">Example</span></span>  
 <span data-ttu-id="fcae0-135">В следующем примере показано, как получить доступ к дочерним узлам `phone` из объекта `contact`.</span><span class="sxs-lookup"><span data-stu-id="fcae0-135">The following example shows how to access the child nodes named `phone` from the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#17)]  
  
 <span data-ttu-id="fcae0-136">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="fcae0-136">This code displays the following text:</span></span>  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="fcae0-137">Пример</span><span class="sxs-lookup"><span data-stu-id="fcae0-137">Example</span></span>  
 <span data-ttu-id="fcae0-138">В следующем примере показано, как получить доступ к дочерним узлам с именем `phone` из коллекции, возвращенной свойством дочерней оси `contact` объекта `contacts`.</span><span class="sxs-lookup"><span data-stu-id="fcae0-138">The following example shows how to access the child nodes named `phone` from the collection returned by the `contact` child axis property of the `contacts` object.</span></span>  
  
 [!code-vb[VbXMLSamples#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#18)]  
  
 <span data-ttu-id="fcae0-139">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="fcae0-139">This code displays the following text:</span></span>  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="fcae0-140">Пример</span><span class="sxs-lookup"><span data-stu-id="fcae0-140">Example</span></span>  
 <span data-ttu-id="fcae0-141">В следующем примере `ns` объявляется как префикс пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="fcae0-141">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="fcae0-142">Затем префикс пространства имен используется для создания литерала XML и доступа к первому дочернему узлу с полным именем `ns:name`.</span><span class="sxs-lookup"><span data-stu-id="fcae0-142">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name `ns:name`.</span></span>  
  
 [!code-vb[VbXMLSamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples8.vb#19)]  
  
 <span data-ttu-id="fcae0-143">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="fcae0-143">This code displays the following text:</span></span>  
  
 `Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="fcae0-144">См. также</span><span class="sxs-lookup"><span data-stu-id="fcae0-144">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="fcae0-145">Свойства оси XML</span><span class="sxs-lookup"><span data-stu-id="fcae0-145">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="fcae0-146">XML-литералы</span><span class="sxs-lookup"><span data-stu-id="fcae0-146">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="fcae0-147">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fcae0-147">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="fcae0-148">Имена объявленных элементов и атрибутов XML</span><span class="sxs-lookup"><span data-stu-id="fcae0-148">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
