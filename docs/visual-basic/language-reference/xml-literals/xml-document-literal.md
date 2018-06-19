---
title: XML-литерал документа (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralDocument
helpviewer_keywords:
- XML document literal [Visual Basic]
- XML literals [Visual Basic], document
- XML documents [Visual Basic], creating
- document literal [Visual Basic]
ms.assetid: f7bbee56-0911-41de-b907-96f20450137b
ms.openlocfilehash: bd2ecfb93cfcdb7cf9c115f9a44ac47dd74c4b53
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604358"
---
# <a name="xml-document-literal-visual-basic"></a><span data-ttu-id="f9c16-102">XML-литерал документа (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f9c16-102">XML Document Literal (Visual Basic)</span></span>
<span data-ttu-id="f9c16-103">Объект литерал, представляющий <xref:System.Xml.Linq.XDocument> объекта.</span><span class="sxs-lookup"><span data-stu-id="f9c16-103">A literal representing an <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9c16-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f9c16-104">Syntax</span></span>  
  
```xml  
<?xml version="1.0" [encoding="encoding"] [standalone="standalone"] ?>  
[ piCommentList ]  
rootElement  
[ piCommentList ]  
```  
  
## <a name="parts"></a><span data-ttu-id="f9c16-105">Части</span><span class="sxs-lookup"><span data-stu-id="f9c16-105">Parts</span></span>  
  
|<span data-ttu-id="f9c16-106">Термин</span><span class="sxs-lookup"><span data-stu-id="f9c16-106">Term</span></span>|<span data-ttu-id="f9c16-107">Определение</span><span class="sxs-lookup"><span data-stu-id="f9c16-107">Definition</span></span>|  
|---|---|  
|`encoding`|<span data-ttu-id="f9c16-108">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="f9c16-108">Optional.</span></span> <span data-ttu-id="f9c16-109">Использует литеральный текст определения кодировки документа.</span><span class="sxs-lookup"><span data-stu-id="f9c16-109">Literal text declaring which encoding the document uses.</span></span>|  
|`standalone`|<span data-ttu-id="f9c16-110">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="f9c16-110">Optional.</span></span> <span data-ttu-id="f9c16-111">Литеральный текст.</span><span class="sxs-lookup"><span data-stu-id="f9c16-111">Literal text.</span></span> <span data-ttu-id="f9c16-112">Должен быть «yes» или «no».</span><span class="sxs-lookup"><span data-stu-id="f9c16-112">Must be "yes" or "no".</span></span>|  
|`piCommentList`|<span data-ttu-id="f9c16-113">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="f9c16-113">Optional.</span></span> <span data-ttu-id="f9c16-114">Список инструкций по обработке XML и XML-комментариев.</span><span class="sxs-lookup"><span data-stu-id="f9c16-114">List of XML processing instructions and XML comments.</span></span> <span data-ttu-id="f9c16-115">Имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="f9c16-115">Takes the following format:</span></span><br /><br /> <span data-ttu-id="f9c16-116">`piComment [` `piComment` `... ]`</span><span class="sxs-lookup"><span data-stu-id="f9c16-116">`piComment [` `piComment` `... ]`</span></span><br /><br /> <span data-ttu-id="f9c16-117">Каждый `piComment` может принимать одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="f9c16-117">Each `piComment` can be one of the following:</span></span><br /><br /> <span data-ttu-id="f9c16-118">-   [Литерал инструкции обработки XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span><span class="sxs-lookup"><span data-stu-id="f9c16-118">-   [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span><br /><span data-ttu-id="f9c16-119">-   [XML-литерал комментария](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span><span class="sxs-lookup"><span data-stu-id="f9c16-119">-   [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>|  
|`rootElement`|<span data-ttu-id="f9c16-120">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="f9c16-120">Required.</span></span> <span data-ttu-id="f9c16-121">Корневой элемент документа.</span><span class="sxs-lookup"><span data-stu-id="f9c16-121">Root element of the document.</span></span> <span data-ttu-id="f9c16-122">Имеет одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="f9c16-122">The format is one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="f9c16-123">[Элемент XML-литерала](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="f9c16-123">[XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span></li><li><span data-ttu-id="f9c16-124">Встроенные выражения формы `<%=` `elementExp` `%>`.</span><span class="sxs-lookup"><span data-stu-id="f9c16-124">Embedded expression of the form `<%=` `elementExp` `%>`.</span></span> <span data-ttu-id="f9c16-125">`elementExp` Возвращает одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="f9c16-125">The `elementExp` returns one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="f9c16-126">Объект <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="f9c16-126">An <xref:System.Xml.Linq.XElement> object.</span></span></li><li><span data-ttu-id="f9c16-127">Коллекция, содержащая один <xref:System.Xml.Linq.XElement> объектов и любое количество <xref:System.Xml.Linq.XProcessingInstruction> и <xref:System.Xml.Linq.XComment> объектов.</span><span class="sxs-lookup"><span data-stu-id="f9c16-127">A collection that contains one <xref:System.Xml.Linq.XElement> object and any number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects.</span></span></li></ul></li></ul><br /> <span data-ttu-id="f9c16-128">Дополнительные сведения см. в разделе [встроенные выражения в XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="f9c16-128">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="f9c16-129">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f9c16-129">Return Value</span></span>  
 <span data-ttu-id="f9c16-130">Объект <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="f9c16-130">An <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9c16-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="f9c16-131">Remarks</span></span>  
 <span data-ttu-id="f9c16-132">Литерал XML-документа определяется по XML-декларация в начале литерала.</span><span class="sxs-lookup"><span data-stu-id="f9c16-132">An XML document literal is identified by the XML declaration at the start of the literal.</span></span> <span data-ttu-id="f9c16-133">Несмотря на то, что каждый XML-литерала документа должен иметь ровно один корневой элемент XML, он может иметь любое количество инструкций по обработке XML и XML-комментариев.</span><span class="sxs-lookup"><span data-stu-id="f9c16-133">Although each XML document literal must have exactly one root XML element, it can have any number of XML processing instructions and XML comments.</span></span>  
  
 <span data-ttu-id="f9c16-134">Литерал XML-документа не может присутствовать в XML-элемента.</span><span class="sxs-lookup"><span data-stu-id="f9c16-134">An XML document literal cannot appear in an XML element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f9c16-135">XML-литерал может занимать несколько строк без использования символа продолжения строки.</span><span class="sxs-lookup"><span data-stu-id="f9c16-135">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="f9c16-136">Это позволяет скопировать содержимое из XML-документа и вставьте его непосредственно в программу Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f9c16-136">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="f9c16-137">Компилятор Visual Basic преобразует XML-литерала документа в вызовы <xref:System.Xml.Linq.XDocument.%23ctor%2A> и <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> конструкторы.</span><span class="sxs-lookup"><span data-stu-id="f9c16-137">The Visual Basic compiler converts the XML document literal into calls to the <xref:System.Xml.Linq.XDocument.%23ctor%2A> and <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> constructors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9c16-138">Пример</span><span class="sxs-lookup"><span data-stu-id="f9c16-138">Example</span></span>  
 <span data-ttu-id="f9c16-139">В следующем примере создается XML-документ с XML-декларация, инструкции по обработке, комментарий и элемент, содержащий другой элемент.</span><span class="sxs-lookup"><span data-stu-id="f9c16-139">The following example creates an XML document that has an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
 [!code-vb[VbXMLSamples#30](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-document-literal_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="f9c16-140">См. также</span><span class="sxs-lookup"><span data-stu-id="f9c16-140">See Also</span></span>  
 <xref:System.Xml.Linq.XElement>  
 <xref:System.Xml.Linq.XProcessingInstruction>  
 <xref:System.Xml.Linq.XComment>  
 <xref:System.Xml.Linq.XDocument>  
 [<span data-ttu-id="f9c16-141">XML-литерал инструкции обработки</span><span class="sxs-lookup"><span data-stu-id="f9c16-141">XML Processing Instruction Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)  
 [<span data-ttu-id="f9c16-142">XML-литерал комментария</span><span class="sxs-lookup"><span data-stu-id="f9c16-142">XML Comment Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)  
 [<span data-ttu-id="f9c16-143">XML-литерал элемента</span><span class="sxs-lookup"><span data-stu-id="f9c16-143">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [<span data-ttu-id="f9c16-144">XML-литералы</span><span class="sxs-lookup"><span data-stu-id="f9c16-144">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="f9c16-145">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f9c16-145">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="f9c16-146">Встроенные выражения в XML</span><span class="sxs-lookup"><span data-stu-id="f9c16-146">Embedded Expressions in XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
