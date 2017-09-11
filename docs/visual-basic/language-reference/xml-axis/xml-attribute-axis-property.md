---
title: "Свойство оси атрибута XML (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyAttributeAxis
dev_langs:
- VB
helpviewer_keywords:
- attribute axis property [Visual Basic]
- Visual Basic code, accessing XML
- XML attribute axis property [Visual Basic]
- XML axis [Visual Basic], attribute
- XML [Visual Basic], accessing
ms.assetid: 7a4777e1-0618-4de9-9510-fb9ace2bf4db
caps.latest.revision: 23
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
ms.openlocfilehash: a3c327f4448287bcf6c45b9b6e26a1ef9ba13c16
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="xml-attribute-axis-property-visual-basic"></a><span data-ttu-id="488bc-102">Свойство оси атрибута XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="488bc-102">XML Attribute Axis Property (Visual Basic)</span></span>
<span data-ttu-id="488bc-103">Предоставляет доступ к значению атрибута <xref:System.Xml.Linq.XElement>объекта или на первый элемент в коллекции <xref:System.Xml.Linq.XElement>объектов.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="488bc-103">Provides access to the value of an attribute for an <xref:System.Xml.Linq.XElement> object or to the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="488bc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="488bc-104">Syntax</span></span>  
  
```  
  
      object.@attribute  
-or-  
object.@<attribute>  
```  
  
## <a name="parts"></a><span data-ttu-id="488bc-105">Части</span><span class="sxs-lookup"><span data-stu-id="488bc-105">Parts</span></span>  
 `object`  
 <span data-ttu-id="488bc-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="488bc-106">Required.</span></span> <span data-ttu-id="488bc-107"><xref:System.Xml.Linq.XElement>Объект или коллекцию <xref:System.Xml.Linq.XElement>объектов.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="488bc-107">An <xref:System.Xml.Linq.XElement> object or a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="488bc-108">.@</span><span class="sxs-lookup"><span data-stu-id="488bc-108">.@</span></span>  
 <span data-ttu-id="488bc-109">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="488bc-109">Required.</span></span> <span data-ttu-id="488bc-110">Обозначает начало свойства оси атрибута.</span><span class="sxs-lookup"><span data-stu-id="488bc-110">Denotes the start of an attribute axis property.</span></span>  
  
 <  
 <span data-ttu-id="488bc-111">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="488bc-111">Optional.</span></span> <span data-ttu-id="488bc-112">Обозначает начало имени атрибута при `attribute` не является допустимым идентификатором в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="488bc-112">Denotes the beginning of the name of the attribute when `attribute` is not a valid identifier in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
 `attribute`  
 <span data-ttu-id="488bc-113">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="488bc-113">Required.</span></span> <span data-ttu-id="488bc-114">Имя атрибута для доступа, формы [`prefix`:]`name`.</span><span class="sxs-lookup"><span data-stu-id="488bc-114">Name of the attribute to access, of the form [`prefix`:]`name`.</span></span>  
  
|<span data-ttu-id="488bc-115">Отделение</span><span class="sxs-lookup"><span data-stu-id="488bc-115">Part</span></span>|<span data-ttu-id="488bc-116">Описание</span><span class="sxs-lookup"><span data-stu-id="488bc-116">Description</span></span>|  
|----------|-----------------|  
|`prefix`|<span data-ttu-id="488bc-117">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="488bc-117">Optional.</span></span> <span data-ttu-id="488bc-118">Префикс пространства имен XML для атрибута.</span><span class="sxs-lookup"><span data-stu-id="488bc-118">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="488bc-119">Должно быть глобальным пространством имен XML, определенным с помощью оператора `Imports`.</span><span class="sxs-lookup"><span data-stu-id="488bc-119">Must be a global XML namespace defined with an `Imports` statement.</span></span>|  
|`name`|<span data-ttu-id="488bc-120">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="488bc-120">Required.</span></span> <span data-ttu-id="488bc-121">Имя локального атрибута.</span><span class="sxs-lookup"><span data-stu-id="488bc-121">Local attribute name.</span></span> <span data-ttu-id="488bc-122">В разделе [имена элементов и атрибутов XML, объявленные](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="488bc-122">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
  
 \>  
 <span data-ttu-id="488bc-123">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="488bc-123">Optional.</span></span> <span data-ttu-id="488bc-124">Обозначает конец имени атрибута при `attribute` не является допустимым идентификатором в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="488bc-124">Denotes the end of the name of the attribute when `attribute` is not a valid identifier in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="488bc-125">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="488bc-125">Return Value</span></span>  
 <span data-ttu-id="488bc-126">Строка, содержащая значение `attribute`.</span><span class="sxs-lookup"><span data-stu-id="488bc-126">A string that contains the value of `attribute`.</span></span> <span data-ttu-id="488bc-127">Если имя атрибута не существует, `Nothing` возвращается.</span><span class="sxs-lookup"><span data-stu-id="488bc-127">If the attribute name does not exist, `Nothing` is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="488bc-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="488bc-128">Remarks</span></span>  
 <span data-ttu-id="488bc-129">Свойство оси атрибута XML можно использовать для доступа к значению атрибута по имени из <xref:System.Xml.Linq.XElement>объектов или из первого элемента в коллекции <xref:System.Xml.Linq.XElement>объектов.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="488bc-129">You can use an XML attribute axis property to access the value of an attribute by name from an <xref:System.Xml.Linq.XElement> object or from the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="488bc-130">Можно извлечь значение атрибута по имени или добавить новый атрибут в элемент, указав новое имя, начинающееся с идентификатора @.</span><span class="sxs-lookup"><span data-stu-id="488bc-130">You can retrieve an attribute value by name, or add a new attribute to an element by specifying a new name preceded by the @ identifier.</span></span>  
  
 <span data-ttu-id="488bc-131">При ссылке на XML-атрибутов с помощью идентификатора @, значение атрибута возвращается в виде строки, и необходимо явно указать <xref:System.Xml.Linq.XAttribute.Value%2A>свойство.</xref:System.Xml.Linq.XAttribute.Value%2A></span><span class="sxs-lookup"><span data-stu-id="488bc-131">When you refer to an XML attribute using the @ identifier, the attribute value is returned as a string and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span>  
  
 <span data-ttu-id="488bc-132">Правила именования для XML-атрибутов отличаются от правила именования для [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="488bc-132">The naming rules for XML attributes differ from the naming rules for [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] identifiers.</span></span> <span data-ttu-id="488bc-133">Чтобы получить доступ к XML-атрибут с именем, которое не является допустимым идентификатором Visual Basic, заключите имя в угловые скобки (\< и настроек).</span><span class="sxs-lookup"><span data-stu-id="488bc-133">To access an XML attribute that has a name that is not a valid Visual Basic identifier, enclose the name in angle brackets (\< and >).</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="488bc-134">Пространства имен XML</span><span class="sxs-lookup"><span data-stu-id="488bc-134">XML Namespaces</span></span>  
 <span data-ttu-id="488bc-135">Имя в свойстве атрибута оси может использовать только префиксы пространства имен XML, объявленные глобально с помощью `Imports` инструкции.</span><span class="sxs-lookup"><span data-stu-id="488bc-135">The name in an attribute axis property can use only XML namespace prefixes declared globally by using the `Imports` statement.</span></span> <span data-ttu-id="488bc-136">В нем нельзя использовать префиксы пространства имен XML, объявленные локально с помощью литералов XML-элемента.</span><span class="sxs-lookup"><span data-stu-id="488bc-136">It cannot use XML namespace prefixes declared locally within XML element literals.</span></span> <span data-ttu-id="488bc-137">Дополнительные сведения см. в разделе [оператор Imports (пространство имен XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="488bc-137">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="488bc-138">Пример</span><span class="sxs-lookup"><span data-stu-id="488bc-138">Example</span></span>  
 <span data-ttu-id="488bc-139">В следующем примере показано получение значений атрибутов XML с именем `type` из коллекции XML-элементов, которые называются `phone`.</span><span class="sxs-lookup"><span data-stu-id="488bc-139">The following example shows how to get the values of the XML attributes named `type` from a collection of XML elements that are named `phone`.</span></span>  
  
 <span data-ttu-id="488bc-140">[!code-vb[VbXMLSamples&#12;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="488bc-140">[!code-vb[VbXMLSamples#12](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_1.vb)]</span></span>  
  
 <span data-ttu-id="488bc-141">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="488bc-141">This code displays the following text:</span></span>  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a><span data-ttu-id="488bc-142">Пример</span><span class="sxs-lookup"><span data-stu-id="488bc-142">Example</span></span>  
 <span data-ttu-id="488bc-143">Приведенный ниже показано, как создать атрибуты для элемента XML как декларативно, как часть XML и динамически путем добавления атрибута к экземпляру <xref:System.Xml.Linq.XElement>объекта.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="488bc-143">The following example shows how to create attributes for an XML element both declaratively, as part of the XML, and dynamically by adding an attribute to an instance of an <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="488bc-144">`type` Атрибут создается декларативно и `owne`r атрибут создается динамически.</span><span class="sxs-lookup"><span data-stu-id="488bc-144">The `type` attribute is created declaratively and the `owne`r attribute is created dynamically.</span></span>  
  
 <span data-ttu-id="488bc-145">[!code-vb[VbXMLSamples&#44;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="488bc-145">[!code-vb[VbXMLSamples#44](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_2.vb)]</span></span>  
  
 <span data-ttu-id="488bc-146">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="488bc-146">This code displays the following text:</span></span>  
  
```  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a><span data-ttu-id="488bc-147">Пример</span><span class="sxs-lookup"><span data-stu-id="488bc-147">Example</span></span>  
 <span data-ttu-id="488bc-148">В следующем примере используется синтаксис угловых скобок, чтобы получить значение атрибута XML с именем `number-type`, который не является допустимым идентификатором в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="488bc-148">The following example uses the angle bracket syntax to get the value of the XML attribute named `number-type`, which is not a valid identifier in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
 <span data-ttu-id="488bc-149">[!code-vb[VbXMLSamples&#13;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="488bc-149">[!code-vb[VbXMLSamples#13](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_3.vb)]</span></span>  
  
 <span data-ttu-id="488bc-150">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="488bc-150">This code displays the following text:</span></span>  
  
 `Phone type: work`  
  
## <a name="example"></a><span data-ttu-id="488bc-151">Пример</span><span class="sxs-lookup"><span data-stu-id="488bc-151">Example</span></span>  
 <span data-ttu-id="488bc-152">В следующем примере `ns` объявляется как префикс пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="488bc-152">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="488bc-153">Затем используется префикс пространства имен для создания литерала XML и доступа к первому дочернему узлу с полным именем «`ns:name`».</span><span class="sxs-lookup"><span data-stu-id="488bc-153">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name "`ns:name`".</span></span>  
  
 <span data-ttu-id="488bc-154">[!code-vb[VbXMLSamples&#14;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="488bc-154">[!code-vb[VbXMLSamples#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_4.vb)]</span></span>  
  
 <span data-ttu-id="488bc-155">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="488bc-155">This code displays the following text:</span></span>  
  
 `Phone type: home`  
  
## <a name="see-also"></a><span data-ttu-id="488bc-156">См. также</span><span class="sxs-lookup"><span data-stu-id="488bc-156">See Also</span></span>  
 <span data-ttu-id="488bc-157"><xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="488bc-157"><xref:System.Xml.Linq.XElement></span></span>   
<span data-ttu-id="488bc-158"> [Свойства оси XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md) </span><span class="sxs-lookup"><span data-stu-id="488bc-158"> [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md) </span></span>  
<span data-ttu-id="488bc-159"> [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md) </span><span class="sxs-lookup"><span data-stu-id="488bc-159"> [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md) </span></span>  
<span data-ttu-id="488bc-160"> [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="488bc-160"> [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="488bc-161"> [Имена объявленных элементов и атрибутов XML](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)</span><span class="sxs-lookup"><span data-stu-id="488bc-161"> [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)</span></span>
