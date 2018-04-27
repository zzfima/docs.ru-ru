---
title: Свойство-индексатор расширения (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyExtensionIndexer
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6bcb19388a9449a76eed5689b12fb95c5a4fb8de
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="extension-indexer-property-visual-basic"></a><span data-ttu-id="e7d2f-102">Свойство-индексатор расширения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7d2f-102">Extension Indexer Property (Visual Basic)</span></span>
<span data-ttu-id="e7d2f-103">Обеспечивает доступ к отдельным элементам коллекции.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-103">Provides access to individual elements in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7d2f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e7d2f-104">Syntax</span></span>  
  
```  
object(index)  
```  
  
## <a name="parts"></a><span data-ttu-id="e7d2f-105">Части</span><span class="sxs-lookup"><span data-stu-id="e7d2f-105">Parts</span></span>  
  
|<span data-ttu-id="e7d2f-106">Термин</span><span class="sxs-lookup"><span data-stu-id="e7d2f-106">Term</span></span>|<span data-ttu-id="e7d2f-107">Определение</span><span class="sxs-lookup"><span data-stu-id="e7d2f-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="e7d2f-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-108">Required.</span></span> <span data-ttu-id="e7d2f-109">Запрашиваемой коллекции.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-109">A queryable collection.</span></span> <span data-ttu-id="e7d2f-110">То есть, коллекция, реализующая <xref:System.Collections.Generic.IEnumerable%601> или <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-110">That is, a collection that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>|  
|<span data-ttu-id="e7d2f-111">(</span><span class="sxs-lookup"><span data-stu-id="e7d2f-111">(</span></span>|<span data-ttu-id="e7d2f-112">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-112">Required.</span></span> <span data-ttu-id="e7d2f-113">Обозначает начало свойства индексатора.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-113">Denotes the start of the indexer property.</span></span>|  
|`index`|<span data-ttu-id="e7d2f-114">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-114">Required.</span></span> <span data-ttu-id="e7d2f-115">Целочисленное выражение, задающее позицию (с нуля) элемента коллекции.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-115">An integer expression that specifies the zero-based position of an element of the collection.</span></span>|  
|<span data-ttu-id="e7d2f-116">)</span><span class="sxs-lookup"><span data-stu-id="e7d2f-116">)</span></span>|<span data-ttu-id="e7d2f-117">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-117">Required.</span></span> <span data-ttu-id="e7d2f-118">Обозначает конец свойства индексатора.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-118">Denotes the end of the indexer property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="e7d2f-119">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e7d2f-119">Return Value</span></span>  
 <span data-ttu-id="e7d2f-120">Объект из указанного расположения в коллекции, или `Nothing` Если индекс вне допустимого диапазона.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-120">The object from the specified location in the collection, or `Nothing` if the index is out of range.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7d2f-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="e7d2f-121">Remarks</span></span>  
 <span data-ttu-id="e7d2f-122">Свойство-индексатор расширения можно использовать для доступа к отдельным элементам в коллекции.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-122">You can use the extension indexer property to access individual elements in a collection.</span></span> <span data-ttu-id="e7d2f-123">Это свойство индексатора обычно используется на выходе свойства оси XML.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-123">This indexer property is typically used on the output of XML axis properties.</span></span> <span data-ttu-id="e7d2f-124">Дочерние XML и свойства XML descendant axis возвращают коллекции <xref:System.Xml.Linq.XElement> объектов или значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-124">The XML child and XML descendent axis properties return collections of <xref:System.Xml.Linq.XElement> objects or an attribute value.</span></span>  
  
 <span data-ttu-id="e7d2f-125">Компилятор Visual Basic преобразует свойства индексатора расширения вызовы `ElementAtOrDefault` метод.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-125">The Visual Basic compiler converts extension indexer properties to calls to the `ElementAtOrDefault` method.</span></span> <span data-ttu-id="e7d2f-126">В отличие от индексатора массива `ElementAtOrDefault` возвращает `Nothing` Если индекс вне допустимого диапазона.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-126">Unlike an array indexer, the `ElementAtOrDefault` method returns `Nothing` if the index is out of range.</span></span> <span data-ttu-id="e7d2f-127">Это полезно в тех случаях, когда не удается легко определить число элементов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-127">This behavior is useful when you cannot easily determine the number of elements in a collection.</span></span>  
  
 <span data-ttu-id="e7d2f-128">Это свойство индексатора доступно как свойство расширения для коллекций, реализующих <xref:System.Collections.Generic.IEnumerable%601> или <xref:System.Linq.IQueryable%601>: оно используется только в том случае, если коллекция не имеет индексатора или свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-128">This indexer property is like an extension property for collections that implement <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>: it is used only if the collection does not have an indexer or a default property.</span></span>  
  
 <span data-ttu-id="e7d2f-129">Для доступа к значению первого элемента в коллекции <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XAttribute> объектов, которые можно использовать XML `Value` свойства.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-129">To access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, you can use the XML `Value` property.</span></span> <span data-ttu-id="e7d2f-130">Дополнительные сведения см. в разделе [свойство значения XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="e7d2f-130">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7d2f-131">Пример</span><span class="sxs-lookup"><span data-stu-id="e7d2f-131">Example</span></span>  
 <span data-ttu-id="e7d2f-132">Приведенный ниже показано, как использовать индексатор расширения для доступа к второй дочерний узел в коллекцию <xref:System.Xml.Linq.XElement> объектов.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-132">The following example shows how to use the extension indexer to access the second child node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="e7d2f-133">Доступ к коллекции с помощью свойства дочерней оси, который получает все дочерние элементы с именем `phone` в `contact` объекта.</span><span class="sxs-lookup"><span data-stu-id="e7d2f-133">The collection is accessed by using the child axis property, which gets all child elements named `phone` in the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#24](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/extension-indexer-property_1.vb)]  
  
 <span data-ttu-id="e7d2f-134">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="e7d2f-134">This code displays the following text:</span></span>  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a><span data-ttu-id="e7d2f-135">См. также</span><span class="sxs-lookup"><span data-stu-id="e7d2f-135">See Also</span></span>  
 <xref:System.Xml.Linq.XElement>  
 [<span data-ttu-id="e7d2f-136">Свойства оси XML</span><span class="sxs-lookup"><span data-stu-id="e7d2f-136">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [<span data-ttu-id="e7d2f-137">XML-литералы</span><span class="sxs-lookup"><span data-stu-id="e7d2f-137">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="e7d2f-138">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e7d2f-138">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="e7d2f-139">Свойство значения XML</span><span class="sxs-lookup"><span data-stu-id="e7d2f-139">XML Value Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
