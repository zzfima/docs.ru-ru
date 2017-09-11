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
- vb.XmlPropertyDescendantsAxis
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML descendant axis property [Visual Basic]
- descendant axis property [Visual Baisc]
- XML axis [Visual Basic], descendant
- XML [Visual Basic], accessing
ms.assetid: a178f85b-5d54-438f-8479-40b62af6fe76
caps.latest.revision: 14
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
ms.openlocfilehash: e84a8bb989ebbed57595ebf93cef620027a04328
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="xml-descendant-axis-property-visual-basic"></a><span data-ttu-id="415d8-102">Свойство дочерней оси XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="415d8-102">XML Descendant Axis Property (Visual Basic)</span></span>
<span data-ttu-id="415d8-103">Предоставляет доступ к потомкам из следующих: <xref:System.Xml.Linq.XElement>объекта <xref:System.Xml.Linq.XDocument>объекта, набор <xref:System.Xml.Linq.XElement>объекты или коллекции <xref:System.Xml.Linq.XDocument>объектов.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="415d8-103">Provides access to the descendants of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="415d8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="415d8-104">Syntax</span></span>  
  
```  
  
object...<descendant>  
```  
  
## <a name="parts"></a><span data-ttu-id="415d8-105">Части</span><span class="sxs-lookup"><span data-stu-id="415d8-105">Parts</span></span>  
 `object`  
 <span data-ttu-id="415d8-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="415d8-106">Required.</span></span> <span data-ttu-id="415d8-107"><xref:System.Xml.Linq.XElement>Объекта <xref:System.Xml.Linq.XDocument>объекта, набор <xref:System.Xml.Linq.XElement>объекты или коллекции <xref:System.Xml.Linq.XDocument>объектов.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="415d8-107">An <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>  
  
 <span data-ttu-id="415d8-108">...<</span><span class="sxs-lookup"><span data-stu-id="415d8-108">...<</span></span>  
 <span data-ttu-id="415d8-109">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="415d8-109">Required.</span></span> <span data-ttu-id="415d8-110">Обозначает начало свойства оси-потомка.</span><span class="sxs-lookup"><span data-stu-id="415d8-110">Denotes the start of a descendant axis property.</span></span>  
  
 `descendant`  
 <span data-ttu-id="415d8-111">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="415d8-111">Required.</span></span> <span data-ttu-id="415d8-112">Имя узлов-потомков для доступа, формы [`prefix``:`]`name`.</span><span class="sxs-lookup"><span data-stu-id="415d8-112">Name of the descendant nodes to access, of the form [`prefix``:`]`name`.</span></span>  
  
|<span data-ttu-id="415d8-113">Отделение</span><span class="sxs-lookup"><span data-stu-id="415d8-113">Part</span></span>|<span data-ttu-id="415d8-114">Описание</span><span class="sxs-lookup"><span data-stu-id="415d8-114">Description</span></span>|  
|----------|-----------------|  
|`prefix`|<span data-ttu-id="415d8-115">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="415d8-115">Optional.</span></span> <span data-ttu-id="415d8-116">Префикс пространства имен XML для дочернего узла.</span><span class="sxs-lookup"><span data-stu-id="415d8-116">XML namespace prefix for the descendant node.</span></span> <span data-ttu-id="415d8-117">Должно быть глобальное пространство имен XML, который определен с помощью `Imports` инструкции.</span><span class="sxs-lookup"><span data-stu-id="415d8-117">Must be a global XML namespace that is defined by using an `Imports` statement.</span></span>|  
|`name`|<span data-ttu-id="415d8-118">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="415d8-118">Required.</span></span> <span data-ttu-id="415d8-119">Локальное имя узлов-потомков.</span><span class="sxs-lookup"><span data-stu-id="415d8-119">Local name of the descendant node.</span></span> <span data-ttu-id="415d8-120">В разделе [имена элементов и атрибутов XML, объявленные](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="415d8-120">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
  
 \>  
 <span data-ttu-id="415d8-121">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="415d8-121">Required.</span></span> <span data-ttu-id="415d8-122">Обозначает конец свойства дочерней оси.</span><span class="sxs-lookup"><span data-stu-id="415d8-122">Denotes the end of a descendant axis property.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="415d8-123">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="415d8-123">Return Value</span></span>  
 <span data-ttu-id="415d8-124">Коллекция <xref:System.Xml.Linq.XElement>объектов.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="415d8-124">A collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="415d8-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="415d8-125">Remarks</span></span>  
 <span data-ttu-id="415d8-126">Свойство дочерней оси XML можно использовать для доступа к узлов-потомков по имени из <xref:System.Xml.Linq.XElement>или <xref:System.Xml.Linq.XDocument>объект, или из коллекции <xref:System.Xml.Linq.XElement>или <xref:System.Xml.Linq.XDocument>объектов.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="415d8-126">You can use an XML descendant axis property to access descendant nodes by name from an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object, or from a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="415d8-127">Используйте XML `Value` свойства для доступа к значению первого дочернего узла в возвращаемой коллекции.</span><span class="sxs-lookup"><span data-stu-id="415d8-127">Use the XML `Value` property to access the value of the first descendant node in the returned collection.</span></span> <span data-ttu-id="415d8-128">Дополнительные сведения см. в разделе [свойство значения XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="415d8-128">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
 <span data-ttu-id="415d8-129">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Компилятор преобразует свойства оси-потомка в вызовы <xref:System.Xml.Linq.XContainer.Descendants%2A>метод.</xref:System.Xml.Linq.XContainer.Descendants%2A></span><span class="sxs-lookup"><span data-stu-id="415d8-129">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler converts descendant axis properties into calls to the <xref:System.Xml.Linq.XContainer.Descendants%2A> method.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="415d8-130">Пространства имен XML</span><span class="sxs-lookup"><span data-stu-id="415d8-130">XML Namespaces</span></span>  
 <span data-ttu-id="415d8-131">Имя в свойстве дочерней оси может использовать только Пространства имен, объявленных глобально с `Imports` инструкции.</span><span class="sxs-lookup"><span data-stu-id="415d8-131">The name in a descendant axis property can use only XML namespaces declared globally with the `Imports` statement.</span></span> <span data-ttu-id="415d8-132">Он не может использовать пространства имен XML, объявленные локально с помощью литералов XML-элемента.</span><span class="sxs-lookup"><span data-stu-id="415d8-132">It cannot use XML namespaces declared locally within XML element literals.</span></span> <span data-ttu-id="415d8-133">Дополнительные сведения см. в разделе [оператор Imports (пространство имен XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="415d8-133">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="415d8-134">Пример</span><span class="sxs-lookup"><span data-stu-id="415d8-134">Example</span></span>  
 <span data-ttu-id="415d8-135">В следующем примере показано, как для доступа к значению первого дочернего узла с именем `name` и значения всех узлов-потомков с именем `phone` из `contacts` объекта.</span><span class="sxs-lookup"><span data-stu-id="415d8-135">The following example shows how to access the value of the first descendant node named `name` and the values of all descendant nodes named `phone` from the `contacts` object.</span></span>  
  
 <span data-ttu-id="415d8-136">[!code-vb[VbXMLSamples&#25;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="415d8-136">[!code-vb[VbXMLSamples#25](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_1.vb)]</span></span>  
  
 <span data-ttu-id="415d8-137">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="415d8-137">This code displays the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="415d8-138">Пример</span><span class="sxs-lookup"><span data-stu-id="415d8-138">Example</span></span>  
 <span data-ttu-id="415d8-139">В следующем примере `ns` объявляется как префикс пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="415d8-139">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="415d8-140">Затем используется префикс пространства имен для создания литерала XML и доступа к значению первого дочернего узла с помощью полного имени `ns:name`.</span><span class="sxs-lookup"><span data-stu-id="415d8-140">It then uses the prefix of the namespace to create an XML literal and access the value of the first child node with the qualified name `ns:name`.</span></span>  
  
 <span data-ttu-id="415d8-141">[!code-vb[VbXMLSamples&#26;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="415d8-141">[!code-vb[VbXMLSamples#26](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_2.vb)]</span></span>  
  
 <span data-ttu-id="415d8-142">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="415d8-142">This code displays the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="415d8-143">См. также</span><span class="sxs-lookup"><span data-stu-id="415d8-143">See Also</span></span>  
 <span data-ttu-id="415d8-144"><xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="415d8-144"><xref:System.Xml.Linq.XElement></span></span>   
<span data-ttu-id="415d8-145"> [Свойства оси XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md) </span><span class="sxs-lookup"><span data-stu-id="415d8-145"> [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md) </span></span>  
<span data-ttu-id="415d8-146"> [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md) </span><span class="sxs-lookup"><span data-stu-id="415d8-146"> [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md) </span></span>  
<span data-ttu-id="415d8-147"> [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="415d8-147"> [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="415d8-148"> [Имена объявленных элементов и атрибутов XML](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)</span><span class="sxs-lookup"><span data-stu-id="415d8-148"> [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)</span></span>
