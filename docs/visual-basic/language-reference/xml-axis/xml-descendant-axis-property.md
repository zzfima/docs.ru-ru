---
title: Свойство дочерней оси XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyDescendantsAxis
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML descendant axis property [Visual Basic]
- descendant axis property [Visual Baisc]
- XML axis [Visual Basic], descendant
- XML [Visual Basic], accessing
ms.assetid: a178f85b-5d54-438f-8479-40b62af6fe76
ms.openlocfilehash: 3b8d13e606f28896cae88162d572470e49af3739
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730286"
---
# <a name="xml-descendant-axis-property-visual-basic"></a><span data-ttu-id="b4f74-102">Свойство дочерней оси XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b4f74-102">XML Descendant Axis Property (Visual Basic)</span></span>
<span data-ttu-id="b4f74-103">Предоставляет доступ к потомкам из следующих: <xref:System.Xml.Linq.XElement> объекта, <xref:System.Xml.Linq.XDocument> объекта, коллекции <xref:System.Xml.Linq.XElement> объекты или коллекции <xref:System.Xml.Linq.XDocument> объектов.</span><span class="sxs-lookup"><span data-stu-id="b4f74-103">Provides access to the descendants of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4f74-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b4f74-104">Syntax</span></span>  
  
```  
object...<descendant>  
```  
  
## <a name="parts"></a><span data-ttu-id="b4f74-105">Части</span><span class="sxs-lookup"><span data-stu-id="b4f74-105">Parts</span></span>  
 `object`  
 <span data-ttu-id="b4f74-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="b4f74-106">Required.</span></span> <span data-ttu-id="b4f74-107">Объект <xref:System.Xml.Linq.XElement>, объект <xref:System.Xml.Linq.XDocument>, коллекция объектов <xref:System.Xml.Linq.XElement> или коллекция объектов <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="b4f74-107">An <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>  
  
 <span data-ttu-id="b4f74-108">...<</span><span class="sxs-lookup"><span data-stu-id="b4f74-108">...<</span></span>  
 <span data-ttu-id="b4f74-109">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="b4f74-109">Required.</span></span> <span data-ttu-id="b4f74-110">Обозначает начало свойства дочерней оси.</span><span class="sxs-lookup"><span data-stu-id="b4f74-110">Denotes the start of a descendant axis property.</span></span>  
  
 `descendant`  
 <span data-ttu-id="b4f74-111">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="b4f74-111">Required.</span></span> <span data-ttu-id="b4f74-112">Имя узлов-потомков, чтобы открыть окно, в формате [`prefix``:`]`name`.</span><span class="sxs-lookup"><span data-stu-id="b4f74-112">Name of the descendant nodes to access, of the form [`prefix``:`]`name`.</span></span>  
  
|<span data-ttu-id="b4f74-113">Отделение</span><span class="sxs-lookup"><span data-stu-id="b4f74-113">Part</span></span>|<span data-ttu-id="b4f74-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="b4f74-114">Description</span></span>|  
|----------|-----------------|  
|`prefix`|<span data-ttu-id="b4f74-115">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="b4f74-115">Optional.</span></span> <span data-ttu-id="b4f74-116">Префикс пространства имен XML для дочернего узла.</span><span class="sxs-lookup"><span data-stu-id="b4f74-116">XML namespace prefix for the descendant node.</span></span> <span data-ttu-id="b4f74-117">Должно быть глобальным пространством имен XML, который определен с помощью `Imports` инструкции.</span><span class="sxs-lookup"><span data-stu-id="b4f74-117">Must be a global XML namespace that is defined by using an `Imports` statement.</span></span>|  
|`name`|<span data-ttu-id="b4f74-118">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="b4f74-118">Required.</span></span> <span data-ttu-id="b4f74-119">Локальное имя узлов-потомков.</span><span class="sxs-lookup"><span data-stu-id="b4f74-119">Local name of the descendant node.</span></span> <span data-ttu-id="b4f74-120">См. в разделе [имена объявленных элементов и атрибутов](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="b4f74-120">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
  
 \>  
 <span data-ttu-id="b4f74-121">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="b4f74-121">Required.</span></span> <span data-ttu-id="b4f74-122">Обозначает конец свойства дочерней оси.</span><span class="sxs-lookup"><span data-stu-id="b4f74-122">Denotes the end of a descendant axis property.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b4f74-123">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b4f74-123">Return Value</span></span>  
 <span data-ttu-id="b4f74-124">Коллекция объектов <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="b4f74-124">A collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4f74-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="b4f74-125">Remarks</span></span>  
 <span data-ttu-id="b4f74-126">Свойство дочерней оси XML можно использовать для доступа к узлов-потомков по имени из <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument> объекта, или из коллекции <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument> объектов.</span><span class="sxs-lookup"><span data-stu-id="b4f74-126">You can use an XML descendant axis property to access descendant nodes by name from an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object, or from a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="b4f74-127">Используйте код XML `Value` свойство для доступа к значению первого дочернего узла в возвращаемой коллекции.</span><span class="sxs-lookup"><span data-stu-id="b4f74-127">Use the XML `Value` property to access the value of the first descendant node in the returned collection.</span></span> <span data-ttu-id="b4f74-128">Дополнительные сведения см. в разделе [свойство значения XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="b4f74-128">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
 <span data-ttu-id="b4f74-129">Компилятор Visual Basic преобразует свойства дочерней оси в вызовы <xref:System.Xml.Linq.XContainer.Descendants%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="b4f74-129">The Visual Basic compiler converts descendant axis properties into calls to the <xref:System.Xml.Linq.XContainer.Descendants%2A> method.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="b4f74-130">Пространства имен XML</span><span class="sxs-lookup"><span data-stu-id="b4f74-130">XML Namespaces</span></span>  
 <span data-ttu-id="b4f74-131">Имя в свойстве дочерней оси может использовать только пространства имен XML, объявленные глобально с помощью `Imports` инструкции.</span><span class="sxs-lookup"><span data-stu-id="b4f74-131">The name in a descendant axis property can use only XML namespaces declared globally with the `Imports` statement.</span></span> <span data-ttu-id="b4f74-132">Он не может использовать пространства имен XML, объявленные локально с помощью литералов XML-элемента.</span><span class="sxs-lookup"><span data-stu-id="b4f74-132">It cannot use XML namespaces declared locally within XML element literals.</span></span> <span data-ttu-id="b4f74-133">Дополнительные сведения см. в разделе [оператор Imports (пространство имен XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="b4f74-133">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4f74-134">Пример</span><span class="sxs-lookup"><span data-stu-id="b4f74-134">Example</span></span>  
 <span data-ttu-id="b4f74-135">В следующем примере показано, как получить доступ к значению первого дочернего узла с именем `name` и значения всех узлов-потомков с именем `phone` из `contacts` объекта.</span><span class="sxs-lookup"><span data-stu-id="b4f74-135">The following example shows how to access the value of the first descendant node named `name` and the values of all descendant nodes named `phone` from the `contacts` object.</span></span>  
  
 [!code-vb[VbXMLSamples#25](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_1.vb)]  
  
 <span data-ttu-id="b4f74-136">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="b4f74-136">This code displays the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="b4f74-137">Пример</span><span class="sxs-lookup"><span data-stu-id="b4f74-137">Example</span></span>  
 <span data-ttu-id="b4f74-138">В следующем примере `ns` объявляется как префикс пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="b4f74-138">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="b4f74-139">Затем используется префикс пространства имен для создания литерала XML и доступа к значению первого дочернего узла с полным именем `ns:name`.</span><span class="sxs-lookup"><span data-stu-id="b4f74-139">It then uses the prefix of the namespace to create an XML literal and access the value of the first child node with the qualified name `ns:name`.</span></span>  
  
 [!code-vb[VbXMLSamples#26](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_2.vb)]  
  
 <span data-ttu-id="b4f74-140">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="b4f74-140">This code displays the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="b4f74-141">См. также</span><span class="sxs-lookup"><span data-stu-id="b4f74-141">See also</span></span>
- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="b4f74-142">Свойства оси XML</span><span class="sxs-lookup"><span data-stu-id="b4f74-142">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="b4f74-143">XML-литералы</span><span class="sxs-lookup"><span data-stu-id="b4f74-143">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="b4f74-144">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b4f74-144">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="b4f74-145">Имена объявленных элементов и атрибутов XML</span><span class="sxs-lookup"><span data-stu-id="b4f74-145">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
