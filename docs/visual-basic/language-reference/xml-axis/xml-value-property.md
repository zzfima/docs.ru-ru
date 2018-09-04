---
title: Свойство значения XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionValue
helpviewer_keywords:
- Value property [Visual Basic]
- Visual Basic code, accessing XML
- XML axis [Visual Basic], Value
- XML Value property [Visual Basic]
ms.assetid: 7ddd057a-a195-4e9b-ad8b-2ee0e615a20f
ms.openlocfilehash: 2b0719320db5843d5d010bfbd70e551646e3ded9
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43533395"
---
# <a name="xml-value-property-visual-basic"></a><span data-ttu-id="0efc7-102">Свойство значения XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0efc7-102">XML Value Property (Visual Basic)</span></span>
<span data-ttu-id="0efc7-103">Предоставляет доступ к значению первого элемента в коллекцию <xref:System.Xml.Linq.XElement> объектов.</span><span class="sxs-lookup"><span data-stu-id="0efc7-103">Provides access to the value of the first element of a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0efc7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0efc7-104">Syntax</span></span>  
  
```  
object.Value  
```  
  
## <a name="parts"></a><span data-ttu-id="0efc7-105">Части</span><span class="sxs-lookup"><span data-stu-id="0efc7-105">Parts</span></span>  
  
|<span data-ttu-id="0efc7-106">Термин</span><span class="sxs-lookup"><span data-stu-id="0efc7-106">Term</span></span>|<span data-ttu-id="0efc7-107">Определение</span><span class="sxs-lookup"><span data-stu-id="0efc7-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="0efc7-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="0efc7-108">Required.</span></span> <span data-ttu-id="0efc7-109">Коллекция объектов <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="0efc7-109">Collection of <xref:System.Xml.Linq.XElement> objects.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="0efc7-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0efc7-110">Return Value</span></span>  
 <span data-ttu-id="0efc7-111">Объект `String` , содержащий значение первого элемента коллекции, или `Nothing` если коллекция пуста.</span><span class="sxs-lookup"><span data-stu-id="0efc7-111">A `String` that contains the value of the first element of the collection, or `Nothing` if the collection is empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0efc7-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="0efc7-112">Remarks</span></span>  
 <span data-ttu-id="0efc7-113"><xref:System.Xml.Linq.XElement.Value%2A> Свойство позволяет легко получить доступ к значению первого элемента в коллекции <xref:System.Xml.Linq.XElement> объектов.</span><span class="sxs-lookup"><span data-stu-id="0efc7-113">The <xref:System.Xml.Linq.XElement.Value%2A> property makes it easy to access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="0efc7-114">Это свойство сначала проверяет, содержит ли коллекция хотя бы один объект.</span><span class="sxs-lookup"><span data-stu-id="0efc7-114">This property first checks whether the collection contains at least one object.</span></span> <span data-ttu-id="0efc7-115">Если коллекция пуста, это свойство возвращает `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="0efc7-115">If the collection is empty, this property returns `Nothing`.</span></span> <span data-ttu-id="0efc7-116">В противном случае это свойство возвращает значение <xref:System.Xml.Linq.XElement.Value%2A> свойства первого элемента в коллекции.</span><span class="sxs-lookup"><span data-stu-id="0efc7-116">Otherwise, this property returns the value of the <xref:System.Xml.Linq.XElement.Value%2A> property of the first element in the collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0efc7-117">При доступе к значение атрибута XML с помощью "\@" идентификатор, значение атрибута возвращается в виде `String` и вам не нужно явно указать <xref:System.Xml.Linq.XAttribute.Value%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="0efc7-117">When you access the value of an XML attribute using the '\@' identifier, the attribute value is returned as a `String` and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span>  
  
 <span data-ttu-id="0efc7-118">Для доступа к другим элементам в коллекции, можно использовать свойство-индексатор расширения XML.</span><span class="sxs-lookup"><span data-stu-id="0efc7-118">To access other elements in a collection, you can use the XML extension indexer property.</span></span> <span data-ttu-id="0efc7-119">Дополнительные сведения см. в разделе [свойство-индексатор расширения](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md).</span><span class="sxs-lookup"><span data-stu-id="0efc7-119">For more information, see [Extension Indexer Property](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md).</span></span>  
  
## <a name="inheritance"></a><span data-ttu-id="0efc7-120">Наследование</span><span class="sxs-lookup"><span data-stu-id="0efc7-120">Inheritance</span></span>  
 <span data-ttu-id="0efc7-121">Большинство пользователей не будет реализовать <xref:System.Collections.Generic.IEnumerable%601>и таким образом можно игнорировать в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="0efc7-121">Most users will not have to implement <xref:System.Collections.Generic.IEnumerable%601>, and can therefore ignore this section.</span></span>  
  
 <span data-ttu-id="0efc7-122"><xref:System.Xml.Linq.XElement.Value%2A> Свойство является свойством расширения для типов, реализующих `IEnumerable(Of XElement)`.</span><span class="sxs-lookup"><span data-stu-id="0efc7-122">The <xref:System.Xml.Linq.XElement.Value%2A> property is an extension property for types that implement `IEnumerable(Of XElement)`.</span></span> <span data-ttu-id="0efc7-123">Привязка этого свойства расширения имеет как привязка методов расширения: Если тип реализует один из интерфейсов и определяет свойство с именем «Value», это свойство имеет приоритет над свойством расширения.</span><span class="sxs-lookup"><span data-stu-id="0efc7-123">The binding of this extension property is like the binding of extension methods: if a type implements one of the interfaces and defines a property that has the name "Value", that property has precedence over the extension property.</span></span> <span data-ttu-id="0efc7-124">Другими словами, это <xref:System.Xml.Linq.XElement.Value%2A> свойство можно переопределить, определив новое свойство в класс, реализующий `IEnumerable(Of XElement)`.</span><span class="sxs-lookup"><span data-stu-id="0efc7-124">In other words, this <xref:System.Xml.Linq.XElement.Value%2A> property can be overridden by defining a new property in a class that implements `IEnumerable(Of XElement)`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0efc7-125">Пример</span><span class="sxs-lookup"><span data-stu-id="0efc7-125">Example</span></span>  
 <span data-ttu-id="0efc7-126">В следующем примере показано, как использовать <xref:System.Xml.Linq.XElement.Value%2A> свойство для доступа к первым узлом в коллекцию <xref:System.Xml.Linq.XElement> объектов.</span><span class="sxs-lookup"><span data-stu-id="0efc7-126">The following example shows how to use the <xref:System.Xml.Linq.XElement.Value%2A> property to access the first node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="0efc7-127">В примере используется свойство дочерней оси для получения коллекции всех дочерних узлов с именем `phone` , находящиеся в `contact` объекта.</span><span class="sxs-lookup"><span data-stu-id="0efc7-127">The example uses the child axis property to get the collection of all child nodes named `phone` that are in the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#15](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-value-property_1.vb)]  
  
 <span data-ttu-id="0efc7-128">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="0efc7-128">This code displays the following text:</span></span>  
  
 `Phone number: 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="0efc7-129">Пример</span><span class="sxs-lookup"><span data-stu-id="0efc7-129">Example</span></span>  
 <span data-ttu-id="0efc7-130">В следующем примере показано, как получить значение атрибута XML из коллекции <xref:System.Xml.Linq.XAttribute> объектов.</span><span class="sxs-lookup"><span data-stu-id="0efc7-130">The following example shows how to get the value of an XML attribute from a collection of <xref:System.Xml.Linq.XAttribute> objects.</span></span> <span data-ttu-id="0efc7-131">В примере используется свойство оси атрибута для отображения значения `type` атрибутов для всех `phone` элементов.</span><span class="sxs-lookup"><span data-stu-id="0efc7-131">The example uses the attribute axis property to display the value of the `type` attribute for all of the `phone` elements.</span></span>  
  
 [!code-vb[VbXMLSamples#16](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-value-property_2.vb)]  
  
 <span data-ttu-id="0efc7-132">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="0efc7-132">This code displays the following text:</span></span>  
  
 `home`  
  
 `work`  
  
## <a name="see-also"></a><span data-ttu-id="0efc7-133">См. также</span><span class="sxs-lookup"><span data-stu-id="0efc7-133">See Also</span></span>  
 <xref:System.Xml.Linq.XElement>  
 <xref:System.Collections.Generic.IEnumerable%601>  
 [<span data-ttu-id="0efc7-134">Свойства оси XML</span><span class="sxs-lookup"><span data-stu-id="0efc7-134">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)  
 [<span data-ttu-id="0efc7-135">XML-литералы</span><span class="sxs-lookup"><span data-stu-id="0efc7-135">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="0efc7-136">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0efc7-136">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="0efc7-137">Методы расширения</span><span class="sxs-lookup"><span data-stu-id="0efc7-137">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)  
 [<span data-ttu-id="0efc7-138">Свойство индексатора расширения</span><span class="sxs-lookup"><span data-stu-id="0efc7-138">Extension Indexer Property</span></span>](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)  
 [<span data-ttu-id="0efc7-139">Свойство дочерней оси XML</span><span class="sxs-lookup"><span data-stu-id="0efc7-139">XML Child Axis Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)  
 [<span data-ttu-id="0efc7-140">Свойство оси атрибута XML</span><span class="sxs-lookup"><span data-stu-id="0efc7-140">XML Attribute Axis Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)
