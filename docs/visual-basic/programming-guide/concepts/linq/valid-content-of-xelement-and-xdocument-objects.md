---
title: "Допустимое содержимое XElement и XDocument Objects2 | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 400bb692-478a-40b6-ac1b-4ccbb4cbbd02
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: ecdcd4c2c0ec61cf248c9e210d42abb750e0546b
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="valid-content-of-xelement-and-xdocument-objects"></a><span data-ttu-id="1240d-102">Допустимое содержимое объектов XElement и XDocument</span><span class="sxs-lookup"><span data-stu-id="1240d-102">Valid Content of XElement and XDocument Objects</span></span>
<span data-ttu-id="1240d-103">В этом разделе описываются допустимые аргументы, которые можно передавать конструкторам, а также методы, которые можно использовать для добавления содержимого в элементы и документы.</span><span class="sxs-lookup"><span data-stu-id="1240d-103">This topic describes the valid arguments that can be passed to constructors and methods that you use to add content to elements and documents.</span></span>  
  
## <a name="valid-content"></a><span data-ttu-id="1240d-104">Допустимое содержимое</span><span class="sxs-lookup"><span data-stu-id="1240d-104">Valid Content</span></span>  
 <span data-ttu-id="1240d-105">Запросы часто иметь <xref:System.Collections.Generic.IEnumerable%601>или <xref:System.Xml.Linq.XElement> <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Xml.Linq.XAttribute>.</xref:System.Xml.Linq.XAttribute> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="1240d-105">Queries often evaluate to <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement> or <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XAttribute>.</span></span> <span data-ttu-id="1240d-106">Можно передавать коллекции объектов <xref:System.Xml.Linq.XElement>или <xref:System.Xml.Linq.XAttribute>объектов <xref:System.Xml.Linq.XElement>конструктор.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="1240d-106">You can pass collections of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects to the <xref:System.Xml.Linq.XElement> constructor.</span></span> <span data-ttu-id="1240d-107">Таким образом, передавать результаты запроса методам и конструкторам, используемым для заполнения XML-деревьев, удобно в виде содержимого.</span><span class="sxs-lookup"><span data-stu-id="1240d-107">Therefore, it is convenient to pass the results of a query as content into methods and constructors that you use to populate XML trees.</span></span>  
  
 <span data-ttu-id="1240d-108">При добавлении простого содержимого этому методу могут передаваться различные типы.</span><span class="sxs-lookup"><span data-stu-id="1240d-108">When adding simple content, various types can be passed to this method.</span></span> <span data-ttu-id="1240d-109">Допустимые типы:</span><span class="sxs-lookup"><span data-stu-id="1240d-109">Valid types include the following:</span></span>  
  
-   <span data-ttu-id="1240d-110"><xref:System.String></xref:System.String></span><span class="sxs-lookup"><span data-stu-id="1240d-110"><xref:System.String></span></span>  
  
-   <span data-ttu-id="1240d-111"><xref:System.Double></xref:System.Double></span><span class="sxs-lookup"><span data-stu-id="1240d-111"><xref:System.Double></span></span>  
  
-   <span data-ttu-id="1240d-112"><xref:System.Single></xref:System.Single></span><span class="sxs-lookup"><span data-stu-id="1240d-112"><xref:System.Single></span></span>  
  
-   <span data-ttu-id="1240d-113"><xref:System.Decimal></xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="1240d-113"><xref:System.Decimal></span></span>  
  
-   <span data-ttu-id="1240d-114"><xref:System.Boolean></xref:System.Boolean></span><span class="sxs-lookup"><span data-stu-id="1240d-114"><xref:System.Boolean></span></span>  
  
-   <span data-ttu-id="1240d-115"><xref:System.DateTime></xref:System.DateTime></span><span class="sxs-lookup"><span data-stu-id="1240d-115"><xref:System.DateTime></span></span>  
  
-   <span data-ttu-id="1240d-116"><xref:System.TimeSpan></xref:System.TimeSpan></span><span class="sxs-lookup"><span data-stu-id="1240d-116"><xref:System.TimeSpan></span></span>  
  
-   <span data-ttu-id="1240d-117"><xref:System.DateTimeOffset></xref:System.DateTimeOffset></span><span class="sxs-lookup"><span data-stu-id="1240d-117"><xref:System.DateTimeOffset></span></span>  
  
-   <span data-ttu-id="1240d-118">Любой тип, реализующий `Object.ToString`.</span><span class="sxs-lookup"><span data-stu-id="1240d-118">Any type that implements `Object.ToString`.</span></span>  
  
-   <span data-ttu-id="1240d-119">Любой тип, реализующий <xref:System.Collections.Generic.IEnumerable%601>.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="1240d-119">Any type that implements <xref:System.Collections.Generic.IEnumerable%601>.</span></span>  
  
 <span data-ttu-id="1240d-120">При добавлении сложного содержимого этому методу могут передаваться различные типы:</span><span class="sxs-lookup"><span data-stu-id="1240d-120">When adding complex content, various types can be passed to this method:</span></span>  
  
-   <span data-ttu-id="1240d-121"><xref:System.Xml.Linq.XObject></xref:System.Xml.Linq.XObject></span><span class="sxs-lookup"><span data-stu-id="1240d-121"><xref:System.Xml.Linq.XObject></span></span>  
  
-   <span data-ttu-id="1240d-122"><xref:System.Xml.Linq.XNode></xref:System.Xml.Linq.XNode></span><span class="sxs-lookup"><span data-stu-id="1240d-122"><xref:System.Xml.Linq.XNode></span></span>  
  
-   <span data-ttu-id="1240d-123"><xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="1240d-123"><xref:System.Xml.Linq.XAttribute></span></span>  
  
-   <span data-ttu-id="1240d-124">Любой тип, реализующий<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="1240d-124">Any type that implements <xref:System.Collections.Generic.IEnumerable%601></span></span>  
  
 <span data-ttu-id="1240d-125">Если объект реализует интерфейс <xref:System.Collections.Generic.IEnumerable%601>, коллекция в этом объекте перечисляется и добавляются все элементы в коллекции.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="1240d-125">If an object implements <xref:System.Collections.Generic.IEnumerable%601>, the collection in the object is enumerated, and all items in the collection are added.</span></span> <span data-ttu-id="1240d-126">Если коллекция содержит <xref:System.Xml.Linq.XNode>или <xref:System.Xml.Linq.XAttribute>объектов, каждый элемент в коллекцию добавляется отдельно.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XNode></span><span class="sxs-lookup"><span data-stu-id="1240d-126">If the collection contains <xref:System.Xml.Linq.XNode> or <xref:System.Xml.Linq.XAttribute> objects, each item in the collection is added separately.</span></span> <span data-ttu-id="1240d-127">Если коллекция содержит текст (или объекты, преобразованные в текст), текст в коллекции объединяется и добавляется в виде единого текстового узла.</span><span class="sxs-lookup"><span data-stu-id="1240d-127">If the collection contains text (or objects that are converted to text), the text in the collection is concatenated and added as a single text node.</span></span>  
  
 <span data-ttu-id="1240d-128">Если содержимое имеет значение `null`, ничего не добавляется.</span><span class="sxs-lookup"><span data-stu-id="1240d-128">If content is `null`, nothing is added.</span></span> <span data-ttu-id="1240d-129">При передаче коллекции ее элементы могут иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="1240d-129">When passing a collection items in the collection can be `null`.</span></span> <span data-ttu-id="1240d-130">Элементы коллекции со значением `null` не влияют на дерево.</span><span class="sxs-lookup"><span data-stu-id="1240d-130">A `null` item in the collection has no effect on the tree.</span></span>  
  
 <span data-ttu-id="1240d-131">Добавленный атрибут должен иметь уникальное имя внутри содержащего его элемента.</span><span class="sxs-lookup"><span data-stu-id="1240d-131">An added attribute must have a unique name within its containing element.</span></span>  
  
 <span data-ttu-id="1240d-132">При добавлении <xref:System.Xml.Linq.XNode>или <xref:System.Xml.Linq.XAttribute>объектов, если новое содержимое не имеет родителя, то объекты просто добавляются к XML-дереву.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XNode></span><span class="sxs-lookup"><span data-stu-id="1240d-132">When adding <xref:System.Xml.Linq.XNode> or <xref:System.Xml.Linq.XAttribute> objects, if the new content has no parent, then the objects are simply attached to the XML tree.</span></span> <span data-ttu-id="1240d-133">Если же новое содержимое уже имеет родителя и является частью другого XML-дерева, тогда это содержимое клонируется, а вновь созданный клон присоединяется к XML-дереву.</span><span class="sxs-lookup"><span data-stu-id="1240d-133">If the new content already is parented and is part of another XML tree, then the new content is cloned, and the newly cloned content is attached to the XML tree.</span></span>  
  
## <a name="valid-content-for-documents"></a><span data-ttu-id="1240d-134">Допустимое содержимое для документов</span><span class="sxs-lookup"><span data-stu-id="1240d-134">Valid Content for Documents</span></span>  
 <span data-ttu-id="1240d-135">Атрибуты и простое содержимое не могут быть добавлены к документу.</span><span class="sxs-lookup"><span data-stu-id="1240d-135">Attributes and simple content cannot be added to a document.</span></span>  
  
 <span data-ttu-id="1240d-136">Не существует множество сценариев, которые требуют создания <xref:System.Xml.Linq.XDocument>.</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="1240d-136">There are not many scenarios that require you to create an <xref:System.Xml.Linq.XDocument>.</span></span> <span data-ttu-id="1240d-137">Вместо этого обычно имеется возможность создавать XML-деревья с <xref:System.Xml.Linq.XElement>корневого узла.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="1240d-137">Instead, you can usually create your XML trees with an <xref:System.Xml.Linq.XElement> root node.</span></span> <span data-ttu-id="1240d-138">Если отсутствуют конкретные требования для создания документа (например, если необходимо создать инструкции по обработке и комментарии на верхнем уровне или необходимостью поддержки типов документов), часто бывает удобно использовать <xref:System.Xml.Linq.XElement>в качестве корневого узла.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="1240d-138">Unless you have a specific requirement to create a document (for example, because you have to create processing instructions and comments at the top level, or you have to support document types), it is often more convenient to use <xref:System.Xml.Linq.XElement> as your root node.</span></span>  
  
 <span data-ttu-id="1240d-139">К допустимому содержимому для документа относится следующее:</span><span class="sxs-lookup"><span data-stu-id="1240d-139">Valid content for a document includes the following:</span></span>  
  
-   <span data-ttu-id="1240d-140">Ноль или один <xref:System.Xml.Linq.XDocumentType>объектов.</xref:System.Xml.Linq.XDocumentType></span><span class="sxs-lookup"><span data-stu-id="1240d-140">Zero or one <xref:System.Xml.Linq.XDocumentType> objects.</span></span> <span data-ttu-id="1240d-141">Типы документов должны указываться до элемента.</span><span class="sxs-lookup"><span data-stu-id="1240d-141">The document types must come before the element.</span></span>  
  
-   <span data-ttu-id="1240d-142">Ноль или один элемент.</span><span class="sxs-lookup"><span data-stu-id="1240d-142">Zero or one element.</span></span>  
  
-   <span data-ttu-id="1240d-143">Ноль или более комментариев.</span><span class="sxs-lookup"><span data-stu-id="1240d-143">Zero or more comments.</span></span>  
  
-   <span data-ttu-id="1240d-144">Ноль или более инструкций по обработке.</span><span class="sxs-lookup"><span data-stu-id="1240d-144">Zero or more processing instructions.</span></span>  
  
-   <span data-ttu-id="1240d-145">Ноль или более текстовых узлов, содержащих только пробел.</span><span class="sxs-lookup"><span data-stu-id="1240d-145">Zero or more text nodes that contain only white space.</span></span>  
  
## <a name="constructors-and-functions-that-allow-adding-content"></a><span data-ttu-id="1240d-146">Конструкторы и функции, допускающие добавление содержимого</span><span class="sxs-lookup"><span data-stu-id="1240d-146">Constructors and Functions that Allow Adding Content</span></span>  
 <span data-ttu-id="1240d-147">Следующие методы позволяют добавлять дочернее содержимое <xref:System.Xml.Linq.XElement>или <xref:System.Xml.Linq.XDocument>:</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="1240d-147">The following methods allow you to add child content to an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XDocument>:</span></span>  
  
|<span data-ttu-id="1240d-148">Метод</span><span class="sxs-lookup"><span data-stu-id="1240d-148">Method</span></span>|<span data-ttu-id="1240d-149">Описание</span><span class="sxs-lookup"><span data-stu-id="1240d-149">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="1240d-150"><xref:System.Xml.Linq.XElement.%23ctor%2A></xref:System.Xml.Linq.XElement.%23ctor%2A></span><span class="sxs-lookup"><span data-stu-id="1240d-150"><xref:System.Xml.Linq.XElement.%23ctor%2A></span></span>|<span data-ttu-id="1240d-151">Создает <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="1240d-151">Constructs an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<span data-ttu-id="1240d-152"><xref:System.Xml.Linq.XDocument.%23ctor%2A></xref:System.Xml.Linq.XDocument.%23ctor%2A></span><span class="sxs-lookup"><span data-stu-id="1240d-152"><xref:System.Xml.Linq.XDocument.%23ctor%2A></span></span>|<span data-ttu-id="1240d-153">Создает <xref:System.Xml.Linq.XDocument>.</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="1240d-153">Constructs a <xref:System.Xml.Linq.XDocument>.</span></span>|  
|<span data-ttu-id="1240d-154"><xref:System.Xml.Linq.XContainer.Add%2A></xref:System.Xml.Linq.XContainer.Add%2A></span><span class="sxs-lookup"><span data-stu-id="1240d-154"><xref:System.Xml.Linq.XContainer.Add%2A></span></span>|<span data-ttu-id="1240d-155">Добавляет к концу дочернего содержимого <xref:System.Xml.Linq.XElement>или <xref:System.Xml.Linq.XDocument>.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="1240d-155">Adds to the end of the child content of the <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>.</span></span>|  
|<span data-ttu-id="1240d-156"><xref:System.Xml.Linq.XNode.AddAfterSelf%2A></xref:System.Xml.Linq.XNode.AddAfterSelf%2A></span><span class="sxs-lookup"><span data-stu-id="1240d-156"><xref:System.Xml.Linq.XNode.AddAfterSelf%2A></span></span>|<span data-ttu-id="1240d-157">Добавляет содержимое после <xref:System.Xml.Linq.XNode>.</xref:System.Xml.Linq.XNode></span><span class="sxs-lookup"><span data-stu-id="1240d-157">Adds content after the <xref:System.Xml.Linq.XNode>.</span></span>|  
|<span data-ttu-id="1240d-158"><xref:System.Xml.Linq.XNode.AddBeforeSelf%2A></xref:System.Xml.Linq.XNode.AddBeforeSelf%2A></span><span class="sxs-lookup"><span data-stu-id="1240d-158"><xref:System.Xml.Linq.XNode.AddBeforeSelf%2A></span></span>|<span data-ttu-id="1240d-159">Добавляет содержимое перед <xref:System.Xml.Linq.XNode>.</xref:System.Xml.Linq.XNode></span><span class="sxs-lookup"><span data-stu-id="1240d-159">Adds content before the <xref:System.Xml.Linq.XNode>.</span></span>|  
|<span data-ttu-id="1240d-160"><xref:System.Xml.Linq.XContainer.AddFirst%2A></xref:System.Xml.Linq.XContainer.AddFirst%2A></span><span class="sxs-lookup"><span data-stu-id="1240d-160"><xref:System.Xml.Linq.XContainer.AddFirst%2A></span></span>|<span data-ttu-id="1240d-161">Добавляет содержимое в начале дочернего содержимого <xref:System.Xml.Linq.XContainer>.</xref:System.Xml.Linq.XContainer></span><span class="sxs-lookup"><span data-stu-id="1240d-161">Adds content at the beginning of the child content of the <xref:System.Xml.Linq.XContainer>.</span></span>|  
|<span data-ttu-id="1240d-162"><xref:System.Xml.Linq.XElement.ReplaceAll%2A></xref:System.Xml.Linq.XElement.ReplaceAll%2A></span><span class="sxs-lookup"><span data-stu-id="1240d-162"><xref:System.Xml.Linq.XElement.ReplaceAll%2A></span></span>|<span data-ttu-id="1240d-163">Заменяет все содержимое (дочерние узлы и атрибуты) <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="1240d-163">Replaces all content (child nodes and attributes) of an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<span data-ttu-id="1240d-164"><xref:System.Xml.Linq.XElement.ReplaceAttributes%2A></xref:System.Xml.Linq.XElement.ReplaceAttributes%2A></span><span class="sxs-lookup"><span data-stu-id="1240d-164"><xref:System.Xml.Linq.XElement.ReplaceAttributes%2A></span></span>|<span data-ttu-id="1240d-165">Заменяет атрибуты <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="1240d-165">Replaces the attributes of an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<span data-ttu-id="1240d-166"><xref:System.Xml.Linq.XContainer.ReplaceNodes%2A></xref:System.Xml.Linq.XContainer.ReplaceNodes%2A></span><span class="sxs-lookup"><span data-stu-id="1240d-166"><xref:System.Xml.Linq.XContainer.ReplaceNodes%2A></span></span>|<span data-ttu-id="1240d-167">Заменяет дочерние узлы новым содержимым.</span><span class="sxs-lookup"><span data-stu-id="1240d-167">Replaces the children nodes with new content.</span></span>|  
|<span data-ttu-id="1240d-168"><xref:System.Xml.Linq.XNode.ReplaceWith%2A></xref:System.Xml.Linq.XNode.ReplaceWith%2A></span><span class="sxs-lookup"><span data-stu-id="1240d-168"><xref:System.Xml.Linq.XNode.ReplaceWith%2A></span></span>|<span data-ttu-id="1240d-169">Заменяет узел новым содержимым.</span><span class="sxs-lookup"><span data-stu-id="1240d-169">Replaces a node with new content.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1240d-170">См. также</span><span class="sxs-lookup"><span data-stu-id="1240d-170">See Also</span></span>  
 [<span data-ttu-id="1240d-171">Создание деревьев XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1240d-171">Creating XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
