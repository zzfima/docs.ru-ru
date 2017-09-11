---
title: "Свойство-индексатор расширения (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyExtensionIndexer
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
caps.latest.revision: 22
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
ms.openlocfilehash: 71c16d3f1b93647154bdead4a85d1117b5f6c463
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="extension-indexer-property-visual-basic"></a><span data-ttu-id="62247-102">Свойство-индексатор расширения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="62247-102">Extension Indexer Property (Visual Basic)</span></span>
<span data-ttu-id="62247-103">Обеспечивает доступ к отдельным элементам коллекции.</span><span class="sxs-lookup"><span data-stu-id="62247-103">Provides access to individual elements in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62247-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="62247-104">Syntax</span></span>  
  
```  
  
object(index)  
```  
  
## <a name="parts"></a><span data-ttu-id="62247-105">Части</span><span class="sxs-lookup"><span data-stu-id="62247-105">Parts</span></span>  
  
|<span data-ttu-id="62247-106">Термин</span><span class="sxs-lookup"><span data-stu-id="62247-106">Term</span></span>|<span data-ttu-id="62247-107">Определение</span><span class="sxs-lookup"><span data-stu-id="62247-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="62247-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="62247-108">Required.</span></span> <span data-ttu-id="62247-109">Запрашиваемой коллекции.</span><span class="sxs-lookup"><span data-stu-id="62247-109">A queryable collection.</span></span> <span data-ttu-id="62247-110">То есть, коллекция, реализующая <xref:System.Collections.Generic.IEnumerable%601>или <xref:System.Linq.IQueryable%601>.</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="62247-110">That is, a collection that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>|  
|<span data-ttu-id="62247-111">(</span><span class="sxs-lookup"><span data-stu-id="62247-111">(</span></span>|<span data-ttu-id="62247-112">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="62247-112">Required.</span></span> <span data-ttu-id="62247-113">Обозначает начало свойства индексатора.</span><span class="sxs-lookup"><span data-stu-id="62247-113">Denotes the start of the indexer property.</span></span>|  
|`index`|<span data-ttu-id="62247-114">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="62247-114">Required.</span></span> <span data-ttu-id="62247-115">Целочисленное выражение, задающее позицию (с нуля) элемента коллекции.</span><span class="sxs-lookup"><span data-stu-id="62247-115">An integer expression that specifies the zero-based position of an element of the collection.</span></span>|  
|<span data-ttu-id="62247-116">)</span><span class="sxs-lookup"><span data-stu-id="62247-116">)</span></span>|<span data-ttu-id="62247-117">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="62247-117">Required.</span></span> <span data-ttu-id="62247-118">Обозначает конец свойства индексатора.</span><span class="sxs-lookup"><span data-stu-id="62247-118">Denotes the end of the indexer property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="62247-119">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="62247-119">Return Value</span></span>  
 <span data-ttu-id="62247-120">Объект из указанного расположения в коллекции, или `Nothing` Если индекс вне допустимого диапазона.</span><span class="sxs-lookup"><span data-stu-id="62247-120">The object from the specified location in the collection, or `Nothing` if the index is out of range.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62247-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="62247-121">Remarks</span></span>  
 <span data-ttu-id="62247-122">Свойство-индексатор расширения можно использовать для доступа к отдельным элементам в коллекции.</span><span class="sxs-lookup"><span data-stu-id="62247-122">You can use the extension indexer property to access individual elements in a collection.</span></span> <span data-ttu-id="62247-123">Это свойство индексатора обычно используется на выходе свойства оси XML.</span><span class="sxs-lookup"><span data-stu-id="62247-123">This indexer property is typically used on the output of XML axis properties.</span></span> <span data-ttu-id="62247-124">Дочерние XML и XML descendant axis свойства возвращают коллекции <xref:System.Xml.Linq.XElement>объектов или значение атрибута.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="62247-124">The XML child and XML descendent axis properties return collections of <xref:System.Xml.Linq.XElement> objects or an attribute value.</span></span>  
  
 <span data-ttu-id="62247-125">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Компилятор преобразует свойства индексатора расширения вызовы`ElementAtOrDefault` метод.</span><span class="sxs-lookup"><span data-stu-id="62247-125">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler converts extension indexer properties to calls to the`ElementAtOrDefault` method.</span></span> <span data-ttu-id="62247-126">В отличие от индексатора массива`ElementAtOrDefault` возвращает `Nothing` , если индекс выходит за пределы диапазона.</span><span class="sxs-lookup"><span data-stu-id="62247-126">Unlike an array indexer, the`ElementAtOrDefault` method returns `Nothing` if the index is out of range.</span></span> <span data-ttu-id="62247-127">Это полезно в тех случаях, когда не удается легко определить число элементов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="62247-127">This behavior is useful when you cannot easily determine the number of elements in a collection.</span></span>  
  
 <span data-ttu-id="62247-128">Это свойство индексатора доступно как свойство расширения для коллекций, реализующих <xref:System.Collections.Generic.IEnumerable%601>или <xref:System.Linq.IQueryable%601>: он используется только в том случае, если коллекция не имеет индексатора или свойство по умолчанию.</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="62247-128">This indexer property is like an extension property for collections that implement <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>: it is used only if the collection does not have an indexer or a default property.</span></span>  
  
 <span data-ttu-id="62247-129">Для доступа к значению первого элемента в коллекции <xref:System.Xml.Linq.XElement>или <xref:System.Xml.Linq.XAttribute>объектов, которые можно использовать XML `Value` свойства.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="62247-129">To access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, you can use the XML `Value` property.</span></span> <span data-ttu-id="62247-130">Дополнительные сведения см. в разделе [свойство значения XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="62247-130">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="62247-131">Пример</span><span class="sxs-lookup"><span data-stu-id="62247-131">Example</span></span>  
 <span data-ttu-id="62247-132">Следующий пример демонстрирует использование индексатора расширения для доступа к второй дочерний узел в коллекцию <xref:System.Xml.Linq.XElement>объектов.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="62247-132">The following example shows how to use the extension indexer to access the second child node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="62247-133">Эта коллекция доступна с помощью свойства дочерней оси, который получает все дочерние элементы с именем `phone` в `contact` объекта.</span><span class="sxs-lookup"><span data-stu-id="62247-133">The collection is accessed by using the child axis property, which gets all child elements named `phone` in the `contact` object.</span></span>  
  
 <span data-ttu-id="62247-134">[!code-vb[VbXMLSamples&#24;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/extension-indexer-property_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="62247-134">[!code-vb[VbXMLSamples#24](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/extension-indexer-property_1.vb)]</span></span>  
  
 <span data-ttu-id="62247-135">Этот пример кода отображает следующий текст:</span><span class="sxs-lookup"><span data-stu-id="62247-135">This code displays the following text:</span></span>  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a><span data-ttu-id="62247-136">См. также</span><span class="sxs-lookup"><span data-stu-id="62247-136">See Also</span></span>  
 <span data-ttu-id="62247-137"><xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="62247-137"><xref:System.Xml.Linq.XElement></span></span>   
<span data-ttu-id="62247-138"> [Свойства оси XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md) </span><span class="sxs-lookup"><span data-stu-id="62247-138"> [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md) </span></span>  
<span data-ttu-id="62247-139"> [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md) </span><span class="sxs-lookup"><span data-stu-id="62247-139"> [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md) </span></span>  
<span data-ttu-id="62247-140"> [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="62247-140"> [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="62247-141"> [Свойство значения XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)</span><span class="sxs-lookup"><span data-stu-id="62247-141"> [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)</span></span>
