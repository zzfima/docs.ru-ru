---
title: XML Attribute Axis Property
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyAttributeAxis
helpviewer_keywords:
- attribute axis property [Visual Basic]
- Visual Basic code, accessing XML
- XML attribute axis property [Visual Basic]
- XML axis [Visual Basic], attribute
- XML [Visual Basic], accessing
ms.assetid: 7a4777e1-0618-4de9-9510-fb9ace2bf4db
ms.openlocfilehash: 109c4b45a5e3ed4e3e4db49687df5cb127a5e0c6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352673"
---
# <a name="xml-attribute-axis-property-visual-basic"></a><span data-ttu-id="e75d7-102">Свойство оси атрибута XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e75d7-102">XML Attribute Axis Property (Visual Basic)</span></span>
<span data-ttu-id="e75d7-103">Предоставляет доступ к значению атрибута для <xref:System.Xml.Linq.XElement> объекта или к первому элементу в коллекции объектов <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="e75d7-103">Provides access to the value of an attribute for an <xref:System.Xml.Linq.XElement> object or to the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e75d7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e75d7-104">Syntax</span></span>  
  
```vb  
object.@attribute  
' -or-  
object.@<attribute>  
```  
  
## <a name="parts"></a><span data-ttu-id="e75d7-105">Части</span><span class="sxs-lookup"><span data-stu-id="e75d7-105">Parts</span></span>  
 `object`  
 <span data-ttu-id="e75d7-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="e75d7-106">Required.</span></span> <span data-ttu-id="e75d7-107">Объект <xref:System.Xml.Linq.XElement> или коллекция объектов <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="e75d7-107">An <xref:System.Xml.Linq.XElement> object or a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="e75d7-108">.@</span><span class="sxs-lookup"><span data-stu-id="e75d7-108">.@</span></span>  
 <span data-ttu-id="e75d7-109">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="e75d7-109">Required.</span></span> <span data-ttu-id="e75d7-110">Обозначает начало свойства оси атрибута.</span><span class="sxs-lookup"><span data-stu-id="e75d7-110">Denotes the start of an attribute axis property.</span></span>  
  
 <  
 <span data-ttu-id="e75d7-111">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="e75d7-111">Optional.</span></span> <span data-ttu-id="e75d7-112">Обозначает начало имени атрибута, если `attribute` не является допустимым идентификатором в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e75d7-112">Denotes the beginning of the name of the attribute when `attribute` is not a valid identifier in Visual Basic.</span></span>  
  
 `attribute`  
 <span data-ttu-id="e75d7-113">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="e75d7-113">Required.</span></span> <span data-ttu-id="e75d7-114">Имя атрибута, к которому осуществляется доступ, в форме [`prefix`:]`name`.</span><span class="sxs-lookup"><span data-stu-id="e75d7-114">Name of the attribute to access, of the form [`prefix`:]`name`.</span></span>  
  
|<span data-ttu-id="e75d7-115">Отделение</span><span class="sxs-lookup"><span data-stu-id="e75d7-115">Part</span></span>|<span data-ttu-id="e75d7-116">Описание</span><span class="sxs-lookup"><span data-stu-id="e75d7-116">Description</span></span>|  
|----------|-----------------|  
|`prefix`|<span data-ttu-id="e75d7-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="e75d7-117">Optional.</span></span> <span data-ttu-id="e75d7-118">Префикс пространства имен XML для атрибута.</span><span class="sxs-lookup"><span data-stu-id="e75d7-118">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="e75d7-119">Должно быть глобальным пространством имен XML, определенным с помощью оператора `Imports`.</span><span class="sxs-lookup"><span data-stu-id="e75d7-119">Must be a global XML namespace defined with an `Imports` statement.</span></span>|  
|`name`|<span data-ttu-id="e75d7-120">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="e75d7-120">Required.</span></span> <span data-ttu-id="e75d7-121">Имя локального атрибута.</span><span class="sxs-lookup"><span data-stu-id="e75d7-121">Local attribute name.</span></span> <span data-ttu-id="e75d7-122">См. [Имена объявленных XML-элементов и атрибутов](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="e75d7-122">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
  
 \>  
 <span data-ttu-id="e75d7-123">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="e75d7-123">Optional.</span></span> <span data-ttu-id="e75d7-124">Обозначает конец имени атрибута, если `attribute` не является допустимым идентификатором в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e75d7-124">Denotes the end of the name of the attribute when `attribute` is not a valid identifier in Visual Basic.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e75d7-125">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e75d7-125">Return Value</span></span>  
 <span data-ttu-id="e75d7-126">Строка, содержащая значение `attribute`.</span><span class="sxs-lookup"><span data-stu-id="e75d7-126">A string that contains the value of `attribute`.</span></span> <span data-ttu-id="e75d7-127">Если имя атрибута не существует, возвращается `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="e75d7-127">If the attribute name does not exist, `Nothing` is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e75d7-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="e75d7-128">Remarks</span></span>  
 <span data-ttu-id="e75d7-129">Свойство оси атрибутов XML можно использовать для доступа к значению атрибута по имени из <xref:System.Xml.Linq.XElement> объекта или из первого элемента в коллекции объектов <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="e75d7-129">You can use an XML attribute axis property to access the value of an attribute by name from an <xref:System.Xml.Linq.XElement> object or from the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="e75d7-130">Можно получить значение атрибута по имени или добавить новый атрибут к элементу, указав новое имя перед идентификатором @.</span><span class="sxs-lookup"><span data-stu-id="e75d7-130">You can retrieve an attribute value by name, or add a new attribute to an element by specifying a new name preceded by the @ identifier.</span></span>  
  
 <span data-ttu-id="e75d7-131">При ссылке на XML-атрибут, используя идентификатор @, значение атрибута возвращается в виде строки и не требуется явно указывать свойство <xref:System.Xml.Linq.XAttribute.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="e75d7-131">When you refer to an XML attribute using the @ identifier, the attribute value is returned as a string and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span>  
  
 <span data-ttu-id="e75d7-132">Правила именования для XML-атрибутов отличаются от правил именования для Visual Basic идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="e75d7-132">The naming rules for XML attributes differ from the naming rules for Visual Basic identifiers.</span></span> <span data-ttu-id="e75d7-133">Чтобы получить доступ к XML-атрибуту, имя которого не является допустимым Visual Basic идентификатором, заключите имя в угловые скобки (\< и >).</span><span class="sxs-lookup"><span data-stu-id="e75d7-133">To access an XML attribute that has a name that is not a valid Visual Basic identifier, enclose the name in angle brackets (\< and >).</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="e75d7-134">Пространства имен XML</span><span class="sxs-lookup"><span data-stu-id="e75d7-134">XML Namespaces</span></span>  
 <span data-ttu-id="e75d7-135">Имя в свойстве оси атрибута может использовать только префиксы пространства имен XML, объявленные глобально с помощью инструкции `Imports`.</span><span class="sxs-lookup"><span data-stu-id="e75d7-135">The name in an attribute axis property can use only XML namespace prefixes declared globally by using the `Imports` statement.</span></span> <span data-ttu-id="e75d7-136">В нем нельзя использовать префиксы пространства имен XML, объявленные локально с помощью литералов XML-элемента.</span><span class="sxs-lookup"><span data-stu-id="e75d7-136">It cannot use XML namespace prefixes declared locally within XML element literals.</span></span> <span data-ttu-id="e75d7-137">Дополнительные сведения см. в разделе [оператор Imports (пространство имен XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="e75d7-137">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e75d7-138">Пример</span><span class="sxs-lookup"><span data-stu-id="e75d7-138">Example</span></span>  
 <span data-ttu-id="e75d7-139">В следующем примере показано, как получить значения XML-атрибутов с именем `type` из коллекции XML-элементов с именами `phone`.</span><span class="sxs-lookup"><span data-stu-id="e75d7-139">The following example shows how to get the values of the XML attributes named `type` from a collection of XML elements that are named `phone`.</span></span>  
  
 [!code-vb[VbXMLSamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#12)]  
  
 <span data-ttu-id="e75d7-140">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="e75d7-140">This code displays the following text:</span></span>  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a><span data-ttu-id="e75d7-141">Пример</span><span class="sxs-lookup"><span data-stu-id="e75d7-141">Example</span></span>  
 <span data-ttu-id="e75d7-142">В следующем примере показано, как создать атрибуты для XML-элемента декларативно, как часть XML, и динамически, добавив атрибут к экземпляру объекта <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="e75d7-142">The following example shows how to create attributes for an XML element both declaratively, as part of the XML, and dynamically by adding an attribute to an instance of an <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="e75d7-143">Атрибут `type` создается декларативно, а атрибут `owner` создается динамически.</span><span class="sxs-lookup"><span data-stu-id="e75d7-143">The `type` attribute is created declaratively and the `owner` attribute is created dynamically.</span></span>  
  
 [!code-vb[VbXMLSamples#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#44)]  
  
 <span data-ttu-id="e75d7-144">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="e75d7-144">This code displays the following text:</span></span>  
  
```xml  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a><span data-ttu-id="e75d7-145">Пример</span><span class="sxs-lookup"><span data-stu-id="e75d7-145">Example</span></span>  
 <span data-ttu-id="e75d7-146">В следующем примере используется синтаксис угловой скобки для получения значения XML-атрибута с именем `number-type`, который не является допустимым идентификатором в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e75d7-146">The following example uses the angle bracket syntax to get the value of the XML attribute named `number-type`, which is not a valid identifier in Visual Basic.</span></span>  
  
 [!code-vb[VbXMLSamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#13)]  
  
 <span data-ttu-id="e75d7-147">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="e75d7-147">This code displays the following text:</span></span>  
  
 `Phone type: work`  
  
## <a name="example"></a><span data-ttu-id="e75d7-148">Пример</span><span class="sxs-lookup"><span data-stu-id="e75d7-148">Example</span></span>  
 <span data-ttu-id="e75d7-149">В следующем примере `ns` объявляется как префикс пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="e75d7-149">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="e75d7-150">Затем он использует префикс пространства имен для создания XML-литерала и доступа к первому дочернему узлу с полным именем "`ns:name`".</span><span class="sxs-lookup"><span data-stu-id="e75d7-150">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name "`ns:name`".</span></span>  
  
 [!code-vb[VbXMLSamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples6.vb#14)]  
  
 <span data-ttu-id="e75d7-151">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="e75d7-151">This code displays the following text:</span></span>  
  
 `Phone type: home`  
  
## <a name="see-also"></a><span data-ttu-id="e75d7-152">См. также</span><span class="sxs-lookup"><span data-stu-id="e75d7-152">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="e75d7-153">Свойства оси XML</span><span class="sxs-lookup"><span data-stu-id="e75d7-153">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="e75d7-154">XML-литералы</span><span class="sxs-lookup"><span data-stu-id="e75d7-154">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="e75d7-155">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e75d7-155">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="e75d7-156">Имена объявленных элементов и атрибутов XML</span><span class="sxs-lookup"><span data-stu-id="e75d7-156">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
