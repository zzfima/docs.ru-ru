---
title: Допустимое содержимое объектов XElement и XDocument3
ms.date: 07/20/2015
ms.assetid: 0d253586-2b97-459f-b1a7-f30f38f3ed9f
ms.openlocfilehash: 1ad5b18e3bbc2143a56f9c8e7b34354761b4e42f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "69590932"
---
# <a name="valid-content-of-xelement-and-xdocument-objects"></a><span data-ttu-id="0d1b1-102">Допустимое содержимое объектов XElement и XDocument</span><span class="sxs-lookup"><span data-stu-id="0d1b1-102">Valid Content of XElement and XDocument Objects</span></span>
<span data-ttu-id="0d1b1-103">В этом разделе описываются допустимые аргументы, которые можно передавать конструкторам, а также методы, которые можно использовать для добавления содержимого в элементы и документы.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-103">This topic describes the valid arguments that can be passed to constructors and methods that you use to add content to elements and documents.</span></span>  
  
## <a name="valid-content"></a><span data-ttu-id="0d1b1-104">Допустимое содержимое</span><span class="sxs-lookup"><span data-stu-id="0d1b1-104">Valid Content</span></span>  
 <span data-ttu-id="0d1b1-105">Возвращаемые запросами данные часто выражаются с помощью коллекций <xref:System.Collections.Generic.IEnumerable%601> элементов <xref:System.Xml.Linq.XElement> или с помощью коллекций <xref:System.Collections.Generic.IEnumerable%601> атрибутов <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-105">Queries often evaluate to <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement> or <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XAttribute>.</span></span> <span data-ttu-id="0d1b1-106">Можно передавать коллекции объектов <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XAttribute> в конструктор <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-106">You can pass collections of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects to the <xref:System.Xml.Linq.XElement> constructor.</span></span> <span data-ttu-id="0d1b1-107">Таким образом, передавать результаты запроса методам и конструкторам, используемым для заполнения XML-деревьев, удобно в виде содержимого.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-107">Therefore, it is convenient to pass the results of a query as content into methods and constructors that you use to populate XML trees.</span></span>  
  
 <span data-ttu-id="0d1b1-108">При добавлении простого содержимого этому методу могут передаваться различные типы.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-108">When adding simple content, various types can be passed to this method.</span></span> <span data-ttu-id="0d1b1-109">Допустимые типы:</span><span class="sxs-lookup"><span data-stu-id="0d1b1-109">Valid types include the following:</span></span>  
  
- <xref:System.String>  
  
- <xref:System.Double>  
  
- <xref:System.Single>  
  
- <xref:System.Decimal>  
  
- <xref:System.Boolean>  
  
- <xref:System.DateTime>  
  
- <xref:System.TimeSpan>  
  
- <xref:System.DateTimeOffset>  
  
- <span data-ttu-id="0d1b1-110">Любой тип, реализующий `Object.ToString`.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-110">Any type that implements `Object.ToString`.</span></span>  
  
- <span data-ttu-id="0d1b1-111">Любой тип, реализующий <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-111">Any type that implements <xref:System.Collections.Generic.IEnumerable%601>.</span></span>  
  
 <span data-ttu-id="0d1b1-112">При добавлении сложного содержимого этому методу могут передаваться различные типы:</span><span class="sxs-lookup"><span data-stu-id="0d1b1-112">When adding complex content, various types can be passed to this method:</span></span>  
  
- <xref:System.Xml.Linq.XObject>  
  
- <xref:System.Xml.Linq.XNode>  
  
- <xref:System.Xml.Linq.XAttribute>  
  
- <span data-ttu-id="0d1b1-113">Любой тип, реализующий объект <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-113">Any type that implements <xref:System.Collections.Generic.IEnumerable%601></span></span>  
  
 <span data-ttu-id="0d1b1-114">Если объект реализует интерфейс <xref:System.Collections.Generic.IEnumerable%601>, коллекция в этом объекте перечисляется и добавляются все элементы коллекции.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-114">If an object implements <xref:System.Collections.Generic.IEnumerable%601>, the collection in the object is enumerated, and all items in the collection are added.</span></span> <span data-ttu-id="0d1b1-115">Если коллекция содержит объекты <xref:System.Xml.Linq.XNode> или <xref:System.Xml.Linq.XAttribute>, каждый ее элемент добавляется отдельно.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-115">If the collection contains <xref:System.Xml.Linq.XNode> or <xref:System.Xml.Linq.XAttribute> objects, each item in the collection is added separately.</span></span> <span data-ttu-id="0d1b1-116">Если коллекция содержит текст (или объекты, преобразованные в текст), текст в коллекции объединяется и добавляется в виде единого текстового узла.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-116">If the collection contains text (or objects that are converted to text), the text in the collection is concatenated and added as a single text node.</span></span>  
  
 <span data-ttu-id="0d1b1-117">Если содержимое имеет значение `null`, ничего не добавляется.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-117">If content is `null`, nothing is added.</span></span> <span data-ttu-id="0d1b1-118">При передаче коллекции ее элементы могут иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-118">When passing a collection items in the collection can be `null`.</span></span> <span data-ttu-id="0d1b1-119">Элементы коллекции со значением `null` не влияют на дерево.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-119">A `null` item in the collection has no effect on the tree.</span></span>  
  
 <span data-ttu-id="0d1b1-120">Добавленный атрибут должен иметь уникальное имя внутри содержащего его элемента.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-120">An added attribute must have a unique name within its containing element.</span></span>  
  
 <span data-ttu-id="0d1b1-121">Если при добавлении объектов <xref:System.Xml.Linq.XNode> или <xref:System.Xml.Linq.XAttribute> новое содержимое не имеет родителя, то эти объекты просто добавляются к XML-дереву.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-121">When adding <xref:System.Xml.Linq.XNode> or <xref:System.Xml.Linq.XAttribute> objects, if the new content has no parent, then the objects are simply attached to the XML tree.</span></span> <span data-ttu-id="0d1b1-122">Если же новое содержимое уже имеет родителя и является частью другого XML-дерева, тогда это содержимое клонируется, а вновь созданный клон присоединяется к XML-дереву.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-122">If the new content already is parented and is part of another XML tree, then the new content is cloned, and the newly cloned content is attached to the XML tree.</span></span>  
  
## <a name="valid-content-for-documents"></a><span data-ttu-id="0d1b1-123">Допустимое содержимое для документов</span><span class="sxs-lookup"><span data-stu-id="0d1b1-123">Valid Content for Documents</span></span>  
 <span data-ttu-id="0d1b1-124">Атрибуты и простое содержимое не могут быть добавлены к документу.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-124">Attributes and simple content cannot be added to a document.</span></span>  
  
 <span data-ttu-id="0d1b1-125">Ситуации, когда необходимо создавать документ <xref:System.Xml.Linq.XDocument>, встречаются нечасто.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-125">There are not many scenarios that require you to create an <xref:System.Xml.Linq.XDocument>.</span></span> <span data-ttu-id="0d1b1-126">Вместо этого обычно имеется возможность создавать XML-деревья с корневым узлом <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-126">Instead, you can usually create your XML trees with an <xref:System.Xml.Linq.XElement> root node.</span></span> <span data-ttu-id="0d1b1-127">Если отсутствуют конкретные требования по созданию документа (вызванные, например, необходимостью создания инструкций по обработке и комментариев на верхнем уровне или необходимостью поддержки типов документов), часто бывает удобнее всего в качестве корневого узла использовать <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-127">Unless you have a specific requirement to create a document (for example, because you have to create processing instructions and comments at the top level, or you have to support document types), it is often more convenient to use <xref:System.Xml.Linq.XElement> as your root node.</span></span>  
  
 <span data-ttu-id="0d1b1-128">К допустимому содержимому для документа относится следующее:</span><span class="sxs-lookup"><span data-stu-id="0d1b1-128">Valid content for a document includes the following:</span></span>  
  
- <span data-ttu-id="0d1b1-129">Ноль или один объект <xref:System.Xml.Linq.XDocumentType>.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-129">Zero or one <xref:System.Xml.Linq.XDocumentType> objects.</span></span> <span data-ttu-id="0d1b1-130">Типы документов должны указываться до элемента.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-130">The document types must come before the element.</span></span>  
  
- <span data-ttu-id="0d1b1-131">Ноль или один элемент.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-131">Zero or one element.</span></span>  
  
- <span data-ttu-id="0d1b1-132">Ноль или более комментариев.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-132">Zero or more comments.</span></span>  
  
- <span data-ttu-id="0d1b1-133">Ноль или более инструкций по обработке.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-133">Zero or more processing instructions.</span></span>  
  
- <span data-ttu-id="0d1b1-134">Ноль или более текстовых узлов, содержащих только пробел.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-134">Zero or more text nodes that contain only white space.</span></span>  
  
## <a name="constructors-and-functions-that-allow-adding-content"></a><span data-ttu-id="0d1b1-135">Конструкторы и функции, допускающие добавление содержимого</span><span class="sxs-lookup"><span data-stu-id="0d1b1-135">Constructors and Functions that Allow Adding Content</span></span>  
 <span data-ttu-id="0d1b1-136">Следующие методы позволяют добавлять дочернее содержимое к элементу <xref:System.Xml.Linq.XElement> или к документу <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-136">The following methods allow you to add child content to an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XDocument>:</span></span>  
  
|<span data-ttu-id="0d1b1-137">Метод</span><span class="sxs-lookup"><span data-stu-id="0d1b1-137">Method</span></span>|<span data-ttu-id="0d1b1-138">Описание:</span><span class="sxs-lookup"><span data-stu-id="0d1b1-138">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.%23ctor%2A>|<span data-ttu-id="0d1b1-139">Создает элемент <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-139">Constructs an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<xref:System.Xml.Linq.XDocument.%23ctor%2A>|<span data-ttu-id="0d1b1-140">Создает документ <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-140">Constructs a <xref:System.Xml.Linq.XDocument>.</span></span>|  
|<xref:System.Xml.Linq.XContainer.Add%2A>|<span data-ttu-id="0d1b1-141">Добавляет к концу дочернего содержимого элемента <xref:System.Xml.Linq.XElement> или документа <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-141">Adds to the end of the child content of the <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>.</span></span>|  
|<xref:System.Xml.Linq.XNode.AddAfterSelf%2A>|<span data-ttu-id="0d1b1-142">Добавляет содержимое после <xref:System.Xml.Linq.XNode>.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-142">Adds content after the <xref:System.Xml.Linq.XNode>.</span></span>|  
|<xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>|<span data-ttu-id="0d1b1-143">Добавляет содержимое перед <xref:System.Xml.Linq.XNode>.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-143">Adds content before the <xref:System.Xml.Linq.XNode>.</span></span>|  
|<xref:System.Xml.Linq.XContainer.AddFirst%2A>|<span data-ttu-id="0d1b1-144">Добавляет содержимое в начале дочернего содержимого <xref:System.Xml.Linq.XContainer>.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-144">Adds content at the beginning of the child content of the <xref:System.Xml.Linq.XContainer>.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A>|<span data-ttu-id="0d1b1-145">Заменяет все содержимое (дочерние узлы и атрибуты) элемента <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-145">Replaces all content (child nodes and attributes) of an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A>|<span data-ttu-id="0d1b1-146">Заменяет атрибуты элемента <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-146">Replaces the attributes of an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A>|<span data-ttu-id="0d1b1-147">Заменяет дочерние узлы новым содержимым.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-147">Replaces the children nodes with new content.</span></span>|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A>|<span data-ttu-id="0d1b1-148">Заменяет узел новым содержимым.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-148">Replaces a node with new content.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0d1b1-149">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0d1b1-149">See also</span></span>

- [<span data-ttu-id="0d1b1-150">Создание деревьев XML (C#)</span><span class="sxs-lookup"><span data-stu-id="0d1b1-150">Creating XML Trees (C#)</span></span>](./linq-to-xml-overview.md)
