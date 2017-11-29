---
title: "Свойство-индексатор расширения (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.XmlPropertyExtensionIndexer
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 99d14b6e54a59ffc904a9e786c22498d23ee8ab6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="extension-indexer-property-visual-basic"></a><span data-ttu-id="04681-102">Свойство-индексатор расширения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="04681-102">Extension Indexer Property (Visual Basic)</span></span>
<span data-ttu-id="04681-103">Обеспечивает доступ к отдельным элементам коллекции.</span><span class="sxs-lookup"><span data-stu-id="04681-103">Provides access to individual elements in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04681-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="04681-104">Syntax</span></span>  
  
```  
object(index)  
```  
  
## <a name="parts"></a><span data-ttu-id="04681-105">Части</span><span class="sxs-lookup"><span data-stu-id="04681-105">Parts</span></span>  
  
|<span data-ttu-id="04681-106">Термин</span><span class="sxs-lookup"><span data-stu-id="04681-106">Term</span></span>|<span data-ttu-id="04681-107">Определение</span><span class="sxs-lookup"><span data-stu-id="04681-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="04681-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="04681-108">Required.</span></span> <span data-ttu-id="04681-109">Запрашиваемой коллекции.</span><span class="sxs-lookup"><span data-stu-id="04681-109">A queryable collection.</span></span> <span data-ttu-id="04681-110">То есть, коллекция, реализующая <xref:System.Collections.Generic.IEnumerable%601> или <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="04681-110">That is, a collection that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>|  
|<span data-ttu-id="04681-111">(</span><span class="sxs-lookup"><span data-stu-id="04681-111">(</span></span>|<span data-ttu-id="04681-112">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="04681-112">Required.</span></span> <span data-ttu-id="04681-113">Обозначает начало свойства индексатора.</span><span class="sxs-lookup"><span data-stu-id="04681-113">Denotes the start of the indexer property.</span></span>|  
|`index`|<span data-ttu-id="04681-114">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="04681-114">Required.</span></span> <span data-ttu-id="04681-115">Целочисленное выражение, задающее позицию (с нуля) элемента коллекции.</span><span class="sxs-lookup"><span data-stu-id="04681-115">An integer expression that specifies the zero-based position of an element of the collection.</span></span>|  
|<span data-ttu-id="04681-116">)</span><span class="sxs-lookup"><span data-stu-id="04681-116">)</span></span>|<span data-ttu-id="04681-117">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="04681-117">Required.</span></span> <span data-ttu-id="04681-118">Обозначает конец свойства индексатора.</span><span class="sxs-lookup"><span data-stu-id="04681-118">Denotes the end of the indexer property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="04681-119">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="04681-119">Return Value</span></span>  
 <span data-ttu-id="04681-120">Объект из указанного расположения в коллекции, или `Nothing` Если индекс вне допустимого диапазона.</span><span class="sxs-lookup"><span data-stu-id="04681-120">The object from the specified location in the collection, or `Nothing` if the index is out of range.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04681-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="04681-121">Remarks</span></span>  
 <span data-ttu-id="04681-122">Свойство-индексатор расширения можно использовать для доступа к отдельным элементам в коллекции.</span><span class="sxs-lookup"><span data-stu-id="04681-122">You can use the extension indexer property to access individual elements in a collection.</span></span> <span data-ttu-id="04681-123">Это свойство индексатора обычно используется на выходе свойства оси XML.</span><span class="sxs-lookup"><span data-stu-id="04681-123">This indexer property is typically used on the output of XML axis properties.</span></span> <span data-ttu-id="04681-124">Дочерние XML и свойства XML descendant axis возвращают коллекции <xref:System.Xml.Linq.XElement> объектов или значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="04681-124">The XML child and XML descendent axis properties return collections of <xref:System.Xml.Linq.XElement> objects or an attribute value.</span></span>  
  
 <span data-ttu-id="04681-125">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Компилятор преобразует свойства индексатора расширения вызовы `ElementAtOrDefault` метод.</span><span class="sxs-lookup"><span data-stu-id="04681-125">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler converts extension indexer properties to calls to the `ElementAtOrDefault` method.</span></span> <span data-ttu-id="04681-126">В отличие от индексатора массива `ElementAtOrDefault` возвращает `Nothing` Если индекс вне допустимого диапазона.</span><span class="sxs-lookup"><span data-stu-id="04681-126">Unlike an array indexer, the `ElementAtOrDefault` method returns `Nothing` if the index is out of range.</span></span> <span data-ttu-id="04681-127">Это полезно в тех случаях, когда не удается легко определить число элементов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="04681-127">This behavior is useful when you cannot easily determine the number of elements in a collection.</span></span>  
  
 <span data-ttu-id="04681-128">Это свойство индексатора доступно как свойство расширения для коллекций, реализующих <xref:System.Collections.Generic.IEnumerable%601> или <xref:System.Linq.IQueryable%601>: оно используется только в том случае, если коллекция не имеет индексатора или свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="04681-128">This indexer property is like an extension property for collections that implement <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>: it is used only if the collection does not have an indexer or a default property.</span></span>  
  
 <span data-ttu-id="04681-129">Для доступа к значению первого элемента в коллекции <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XAttribute> объектов, которые можно использовать XML `Value` свойства.</span><span class="sxs-lookup"><span data-stu-id="04681-129">To access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, you can use the XML `Value` property.</span></span> <span data-ttu-id="04681-130">Дополнительные сведения см. в разделе [свойство значения XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="04681-130">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="04681-131">Пример</span><span class="sxs-lookup"><span data-stu-id="04681-131">Example</span></span>  
 <span data-ttu-id="04681-132">Приведенный ниже показано, как использовать индексатор расширения для доступа к второй дочерний узел в коллекцию <xref:System.Xml.Linq.XElement> объектов.</span><span class="sxs-lookup"><span data-stu-id="04681-132">The following example shows how to use the extension indexer to access the second child node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="04681-133">Доступ к коллекции с помощью свойства дочерней оси, который получает все дочерние элементы с именем `phone` в `contact` объекта.</span><span class="sxs-lookup"><span data-stu-id="04681-133">The collection is accessed by using the child axis property, which gets all child elements named `phone` in the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#24](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/extension-indexer-property_1.vb)]  
  
 <span data-ttu-id="04681-134">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="04681-134">This code displays the following text:</span></span>  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a><span data-ttu-id="04681-135">См. также</span><span class="sxs-lookup"><span data-stu-id="04681-135">See Also</span></span>  
 <xref:System.Xml.Linq.XElement>  
 [<span data-ttu-id="04681-136">Свойства оси XML</span><span class="sxs-lookup"><span data-stu-id="04681-136">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [<span data-ttu-id="04681-137">XML-литералы</span><span class="sxs-lookup"><span data-stu-id="04681-137">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="04681-138">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="04681-138">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="04681-139">Свойство значения XML</span><span class="sxs-lookup"><span data-stu-id="04681-139">XML Value Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
