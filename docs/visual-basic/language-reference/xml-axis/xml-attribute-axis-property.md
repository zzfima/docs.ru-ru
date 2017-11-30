---
title: "Свойство оси атрибута XML (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.XmlPropertyAttributeAxis
helpviewer_keywords:
- attribute axis property [Visual Basic]
- Visual Basic code, accessing XML
- XML attribute axis property [Visual Basic]
- XML axis [Visual Basic], attribute
- XML [Visual Basic], accessing
ms.assetid: 7a4777e1-0618-4de9-9510-fb9ace2bf4db
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a286c70f57128d0406b3a300610fea5e1c44b32d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="xml-attribute-axis-property-visual-basic"></a><span data-ttu-id="96c27-102">Свойство оси атрибута XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="96c27-102">XML Attribute Axis Property (Visual Basic)</span></span>
<span data-ttu-id="96c27-103">Предоставляет доступ к значению атрибута для <xref:System.Xml.Linq.XElement> объекта или первый элемент в коллекцию <xref:System.Xml.Linq.XElement> объектов.</span><span class="sxs-lookup"><span data-stu-id="96c27-103">Provides access to the value of an attribute for an <xref:System.Xml.Linq.XElement> object or to the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96c27-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="96c27-104">Syntax</span></span>  
  
```  
      object.@attribute  
-or-  
object.@<attribute>  
```  
  
## <a name="parts"></a><span data-ttu-id="96c27-105">Части</span><span class="sxs-lookup"><span data-stu-id="96c27-105">Parts</span></span>  
 `object`  
 <span data-ttu-id="96c27-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="96c27-106">Required.</span></span> <span data-ttu-id="96c27-107"><xref:System.Xml.Linq.XElement> Объект или коллекцию <xref:System.Xml.Linq.XElement> объектов.</span><span class="sxs-lookup"><span data-stu-id="96c27-107">An <xref:System.Xml.Linq.XElement> object or a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="96c27-108">.@</span><span class="sxs-lookup"><span data-stu-id="96c27-108">.@</span></span>  
 <span data-ttu-id="96c27-109">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="96c27-109">Required.</span></span> <span data-ttu-id="96c27-110">Обозначает начало свойства оси атрибута.</span><span class="sxs-lookup"><span data-stu-id="96c27-110">Denotes the start of an attribute axis property.</span></span>  
  
 <  
 <span data-ttu-id="96c27-111">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="96c27-111">Optional.</span></span> <span data-ttu-id="96c27-112">Обозначает начало имени атрибута при `attribute` не является допустимым идентификатором в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96c27-112">Denotes the beginning of the name of the attribute when `attribute` is not a valid identifier in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
 `attribute`  
 <span data-ttu-id="96c27-113">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="96c27-113">Required.</span></span> <span data-ttu-id="96c27-114">Имя атрибута для доступа к формы [`prefix`:]`name`.</span><span class="sxs-lookup"><span data-stu-id="96c27-114">Name of the attribute to access, of the form [`prefix`:]`name`.</span></span>  
  
|<span data-ttu-id="96c27-115">Отделение</span><span class="sxs-lookup"><span data-stu-id="96c27-115">Part</span></span>|<span data-ttu-id="96c27-116">Описание</span><span class="sxs-lookup"><span data-stu-id="96c27-116">Description</span></span>|  
|----------|-----------------|  
|`prefix`|<span data-ttu-id="96c27-117">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="96c27-117">Optional.</span></span> <span data-ttu-id="96c27-118">Префикс пространства имен XML для атрибута.</span><span class="sxs-lookup"><span data-stu-id="96c27-118">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="96c27-119">Должно быть глобальным пространством имен XML, определенным с помощью оператора `Imports`.</span><span class="sxs-lookup"><span data-stu-id="96c27-119">Must be a global XML namespace defined with an `Imports` statement.</span></span>|  
|`name`|<span data-ttu-id="96c27-120">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="96c27-120">Required.</span></span> <span data-ttu-id="96c27-121">Имя локального атрибута.</span><span class="sxs-lookup"><span data-stu-id="96c27-121">Local attribute name.</span></span> <span data-ttu-id="96c27-122">В разделе [имена объявленных элементов и атрибутов](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="96c27-122">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
  
 \>  
 <span data-ttu-id="96c27-123">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="96c27-123">Optional.</span></span> <span data-ttu-id="96c27-124">Обозначает конец имени атрибута при `attribute` не является допустимым идентификатором в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96c27-124">Denotes the end of the name of the attribute when `attribute` is not a valid identifier in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="96c27-125">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="96c27-125">Return Value</span></span>  
 <span data-ttu-id="96c27-126">Строка, содержащая значение `attribute`.</span><span class="sxs-lookup"><span data-stu-id="96c27-126">A string that contains the value of `attribute`.</span></span> <span data-ttu-id="96c27-127">Если имя атрибута не существует, `Nothing` возвращается.</span><span class="sxs-lookup"><span data-stu-id="96c27-127">If the attribute name does not exist, `Nothing` is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96c27-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="96c27-128">Remarks</span></span>  
 <span data-ttu-id="96c27-129">Свойство оси атрибута XML можно использовать для доступа к значению атрибута по имени из <xref:System.Xml.Linq.XElement> объекта или с первого элемента в коллекции <xref:System.Xml.Linq.XElement> объектов.</span><span class="sxs-lookup"><span data-stu-id="96c27-129">You can use an XML attribute axis property to access the value of an attribute by name from an <xref:System.Xml.Linq.XElement> object or from the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="96c27-130">Можно извлечь значение атрибута по имени или добавить новый атрибут в элемент, указав новое имя, начинающееся с идентификатора @.</span><span class="sxs-lookup"><span data-stu-id="96c27-130">You can retrieve an attribute value by name, or add a new attribute to an element by specifying a new name preceded by the @ identifier.</span></span>  
  
 <span data-ttu-id="96c27-131">При ссылке на XML-атрибутов с помощью идентификатора @, значение атрибута возвращается в виде строки, и необходимо явно указать <xref:System.Xml.Linq.XAttribute.Value%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="96c27-131">When you refer to an XML attribute using the @ identifier, the attribute value is returned as a string and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span>  
  
 <span data-ttu-id="96c27-132">Правила именования для XML-атрибутов отличаются от правила именования для [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="96c27-132">The naming rules for XML attributes differ from the naming rules for [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] identifiers.</span></span> <span data-ttu-id="96c27-133">Чтобы получить доступ к XML-атрибут, который имеет имя, которое не является допустимым идентификатором Visual Basic, заключите имя в угловые скобки (\< и >).</span><span class="sxs-lookup"><span data-stu-id="96c27-133">To access an XML attribute that has a name that is not a valid Visual Basic identifier, enclose the name in angle brackets (\< and >).</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="96c27-134">Пространства имен XML</span><span class="sxs-lookup"><span data-stu-id="96c27-134">XML Namespaces</span></span>  
 <span data-ttu-id="96c27-135">Имя в свойство оси атрибута можно использовать только префиксы пространства имен XML, объявленные глобально с помощью `Imports` инструкции.</span><span class="sxs-lookup"><span data-stu-id="96c27-135">The name in an attribute axis property can use only XML namespace prefixes declared globally by using the `Imports` statement.</span></span> <span data-ttu-id="96c27-136">В нем нельзя использовать префиксы пространства имен XML, объявленные локально с помощью литералов XML-элемента.</span><span class="sxs-lookup"><span data-stu-id="96c27-136">It cannot use XML namespace prefixes declared locally within XML element literals.</span></span> <span data-ttu-id="96c27-137">Дополнительные сведения см. в разделе [оператор Imports (пространство имен XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="96c27-137">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="96c27-138">Пример</span><span class="sxs-lookup"><span data-stu-id="96c27-138">Example</span></span>  
 <span data-ttu-id="96c27-139">Следующий пример показывает способ получения значений атрибутов XML с именем `type` из коллекции XML-элементов, которые именуются `phone`.</span><span class="sxs-lookup"><span data-stu-id="96c27-139">The following example shows how to get the values of the XML attributes named `type` from a collection of XML elements that are named `phone`.</span></span>  
  
 [!code-vb[VbXMLSamples#12](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_1.vb)]  
  
 <span data-ttu-id="96c27-140">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="96c27-140">This code displays the following text:</span></span>  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a><span data-ttu-id="96c27-141">Пример</span><span class="sxs-lookup"><span data-stu-id="96c27-141">Example</span></span>  
 <span data-ttu-id="96c27-142">Приведенный ниже показано, как создать атрибуты для XML-элемента как декларативно как часть XML и динамически путем добавления атрибута в экземпляр <xref:System.Xml.Linq.XElement> объекта.</span><span class="sxs-lookup"><span data-stu-id="96c27-142">The following example shows how to create attributes for an XML element both declaratively, as part of the XML, and dynamically by adding an attribute to an instance of an <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="96c27-143">`type` Атрибут создается декларативно и `owner` динамически создать атрибут.</span><span class="sxs-lookup"><span data-stu-id="96c27-143">The `type` attribute is created declaratively and the `owner` attribute is created dynamically.</span></span>  
  
 [!code-vb[VbXMLSamples#44](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_2.vb)]  
  
 <span data-ttu-id="96c27-144">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="96c27-144">This code displays the following text:</span></span>  
  
```xml  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a><span data-ttu-id="96c27-145">Пример</span><span class="sxs-lookup"><span data-stu-id="96c27-145">Example</span></span>  
 <span data-ttu-id="96c27-146">В следующем примере используется синтаксис угловых скобок, необходимо получить значение атрибута XML с именем `number-type`, который не является допустимым идентификатором в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96c27-146">The following example uses the angle bracket syntax to get the value of the XML attribute named `number-type`, which is not a valid identifier in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
 [!code-vb[VbXMLSamples#13](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_3.vb)]  
  
 <span data-ttu-id="96c27-147">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="96c27-147">This code displays the following text:</span></span>  
  
 `Phone type: work`  
  
## <a name="example"></a><span data-ttu-id="96c27-148">Пример</span><span class="sxs-lookup"><span data-stu-id="96c27-148">Example</span></span>  
 <span data-ttu-id="96c27-149">В следующем примере `ns` объявляется как префикс пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="96c27-149">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="96c27-150">Затем используется префикс пространства имен для создания литерала XML и доступа к первым дочерним узлом с помощью полного имени «`ns:name`».</span><span class="sxs-lookup"><span data-stu-id="96c27-150">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name "`ns:name`".</span></span>  
  
 [!code-vb[VbXMLSamples#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_4.vb)]  
  
 <span data-ttu-id="96c27-151">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="96c27-151">This code displays the following text:</span></span>  
  
 `Phone type: home`  
  
## <a name="see-also"></a><span data-ttu-id="96c27-152">См. также</span><span class="sxs-lookup"><span data-stu-id="96c27-152">See Also</span></span>  
 <xref:System.Xml.Linq.XElement>  
 [<span data-ttu-id="96c27-153">Свойства оси XML</span><span class="sxs-lookup"><span data-stu-id="96c27-153">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [<span data-ttu-id="96c27-154">XML-литералы</span><span class="sxs-lookup"><span data-stu-id="96c27-154">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="96c27-155">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="96c27-155">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="96c27-156">Имена объявленных элементов и атрибутов XML</span><span class="sxs-lookup"><span data-stu-id="96c27-156">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
