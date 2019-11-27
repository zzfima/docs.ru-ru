---
title: XML-литерал документа
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralDocument
helpviewer_keywords:
- XML document literal [Visual Basic]
- XML literals [Visual Basic], document
- XML documents [Visual Basic], creating
- document literal [Visual Basic]
ms.assetid: f7bbee56-0911-41de-b907-96f20450137b
ms.openlocfilehash: db77cccd26c87e271d6db45ce514ab6dabbc53e3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349387"
---
# <a name="xml-document-literal-visual-basic"></a><span data-ttu-id="bb324-102">XML-литерал документа (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bb324-102">XML Document Literal (Visual Basic)</span></span>
<span data-ttu-id="bb324-103">Литерал, представляющий объект <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="bb324-103">A literal representing an <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb324-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bb324-104">Syntax</span></span>  
  
```xml  
<?xml version="1.0" [encoding="encoding"] [standalone="standalone"] ?>  
[ piCommentList ]  
rootElement  
[ piCommentList ]  
```  
  
## <a name="parts"></a><span data-ttu-id="bb324-105">Части</span><span class="sxs-lookup"><span data-stu-id="bb324-105">Parts</span></span>  
  
|<span data-ttu-id="bb324-106">Термин</span><span class="sxs-lookup"><span data-stu-id="bb324-106">Term</span></span>|<span data-ttu-id="bb324-107">Определение</span><span class="sxs-lookup"><span data-stu-id="bb324-107">Definition</span></span>|  
|---|---|  
|`encoding`|<span data-ttu-id="bb324-108">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="bb324-108">Optional.</span></span> <span data-ttu-id="bb324-109">Литеральный текст, объявляющий кодировку, используемую в документе.</span><span class="sxs-lookup"><span data-stu-id="bb324-109">Literal text declaring which encoding the document uses.</span></span>|  
|`standalone`|<span data-ttu-id="bb324-110">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="bb324-110">Optional.</span></span> <span data-ttu-id="bb324-111">Текст литерала.</span><span class="sxs-lookup"><span data-stu-id="bb324-111">Literal text.</span></span> <span data-ttu-id="bb324-112">Значение должно быть "Yes" или "No".</span><span class="sxs-lookup"><span data-stu-id="bb324-112">Must be "yes" or "no".</span></span>|  
|`piCommentList`|<span data-ttu-id="bb324-113">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="bb324-113">Optional.</span></span> <span data-ttu-id="bb324-114">Список инструкций по обработке XML и XML-комментариев.</span><span class="sxs-lookup"><span data-stu-id="bb324-114">List of XML processing instructions and XML comments.</span></span> <span data-ttu-id="bb324-115">Принимает следующий формат:</span><span class="sxs-lookup"><span data-stu-id="bb324-115">Takes the following format:</span></span><br /><br /> <span data-ttu-id="bb324-116">`piComment [` `piComment` `... ]`</span><span class="sxs-lookup"><span data-stu-id="bb324-116">`piComment [` `piComment` `... ]`</span></span><br /><br /> <span data-ttu-id="bb324-117">Каждый `piComment` может быть одним из следующих:</span><span class="sxs-lookup"><span data-stu-id="bb324-117">Each `piComment` can be one of the following:</span></span><br /><br /> <span data-ttu-id="bb324-118">-   [литерал инструкции обработки XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span><span class="sxs-lookup"><span data-stu-id="bb324-118">-   [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span><br /><span data-ttu-id="bb324-119">-   [литерал XML-комментария](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span><span class="sxs-lookup"><span data-stu-id="bb324-119">-   [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>|  
|`rootElement`|<span data-ttu-id="bb324-120">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="bb324-120">Required.</span></span> <span data-ttu-id="bb324-121">Корневой элемент документа.</span><span class="sxs-lookup"><span data-stu-id="bb324-121">Root element of the document.</span></span> <span data-ttu-id="bb324-122">Формат может быть одним из следующих:</span><span class="sxs-lookup"><span data-stu-id="bb324-122">The format is one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="bb324-123">[Литерал XML-элемента](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="bb324-123">[XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span></li><li><span data-ttu-id="bb324-124">Внедренное выражение формы `<%=` `elementExp` `%>`.</span><span class="sxs-lookup"><span data-stu-id="bb324-124">Embedded expression of the form `<%=` `elementExp` `%>`.</span></span> <span data-ttu-id="bb324-125">`elementExp` возвращает одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="bb324-125">The `elementExp` returns one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="bb324-126">Объект <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="bb324-126">An <xref:System.Xml.Linq.XElement> object.</span></span></li><li><span data-ttu-id="bb324-127">Коллекция, содержащая один объект <xref:System.Xml.Linq.XElement> и любое количество <xref:System.Xml.Linq.XProcessingInstruction> и <xref:System.Xml.Linq.XComment> объектов.</span><span class="sxs-lookup"><span data-stu-id="bb324-127">A collection that contains one <xref:System.Xml.Linq.XElement> object and any number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects.</span></span></li></ul></li></ul><br /> <span data-ttu-id="bb324-128">Дополнительные сведения см. [в разделе внедренные выражения в XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="bb324-128">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="bb324-129">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bb324-129">Return Value</span></span>  
 <span data-ttu-id="bb324-130">Объект <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="bb324-130">An <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb324-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="bb324-131">Remarks</span></span>  
 <span data-ttu-id="bb324-132">Литерал XML-документа определяется XML-объявлением в начале литерала.</span><span class="sxs-lookup"><span data-stu-id="bb324-132">An XML document literal is identified by the XML declaration at the start of the literal.</span></span> <span data-ttu-id="bb324-133">Хотя каждый литерал XML-документа должен иметь ровно один корневой XML-элемент, он может иметь любое количество инструкций по обработке XML и XML-комментариев.</span><span class="sxs-lookup"><span data-stu-id="bb324-133">Although each XML document literal must have exactly one root XML element, it can have any number of XML processing instructions and XML comments.</span></span>  
  
 <span data-ttu-id="bb324-134">Литерал XML-документа не может присутствовать в элементе XML.</span><span class="sxs-lookup"><span data-stu-id="bb324-134">An XML document literal cannot appear in an XML element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bb324-135">XML-литерал может охватывать несколько строк без использования символов продолжения строки.</span><span class="sxs-lookup"><span data-stu-id="bb324-135">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="bb324-136">Это позволяет копировать содержимое из XML-документа и вставлять его непосредственно в Visual Basic программу.</span><span class="sxs-lookup"><span data-stu-id="bb324-136">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="bb324-137">Компилятор Visual Basic преобразует литерал XML-документа в вызовы конструкторов <xref:System.Xml.Linq.XDocument.%23ctor%2A> и <xref:System.Xml.Linq.XDeclaration.%23ctor%2A>.</span><span class="sxs-lookup"><span data-stu-id="bb324-137">The Visual Basic compiler converts the XML document literal into calls to the <xref:System.Xml.Linq.XDocument.%23ctor%2A> and <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> constructors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb324-138">Пример</span><span class="sxs-lookup"><span data-stu-id="bb324-138">Example</span></span>  
 <span data-ttu-id="bb324-139">В следующем примере создается XML-документ с XML-объявлением, инструкцией по обработке, комментарием и элементом, содержащим другой элемент.</span><span class="sxs-lookup"><span data-stu-id="bb324-139">The following example creates an XML document that has an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
 [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="bb324-140">См. также</span><span class="sxs-lookup"><span data-stu-id="bb324-140">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- <xref:System.Xml.Linq.XProcessingInstruction>
- <xref:System.Xml.Linq.XComment>
- <xref:System.Xml.Linq.XDocument>
- [<span data-ttu-id="bb324-141">XML-литерал инструкции обработки</span><span class="sxs-lookup"><span data-stu-id="bb324-141">XML Processing Instruction Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)
- [<span data-ttu-id="bb324-142">XML-литерал комментария</span><span class="sxs-lookup"><span data-stu-id="bb324-142">XML Comment Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)
- [<span data-ttu-id="bb324-143">XML-литерал элемента</span><span class="sxs-lookup"><span data-stu-id="bb324-143">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="bb324-144">XML-литералы</span><span class="sxs-lookup"><span data-stu-id="bb324-144">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="bb324-145">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bb324-145">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="bb324-146">Встроенные выражения в XML</span><span class="sxs-lookup"><span data-stu-id="bb324-146">Embedded Expressions in XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
