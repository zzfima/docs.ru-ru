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
ms.openlocfilehash: f58c1365e145166dfe122d455854d44526300a1e
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58814631"
---
# <a name="xml-document-literal-visual-basic"></a><span data-ttu-id="f5784-102">XML-литерал документа (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f5784-102">XML Document Literal (Visual Basic)</span></span>
<span data-ttu-id="f5784-103">Объект литерал, представляющий <xref:System.Xml.Linq.XDocument> объекта.</span><span class="sxs-lookup"><span data-stu-id="f5784-103">A literal representing an <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5784-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f5784-104">Syntax</span></span>  
  
```xml  
<?xml version="1.0" [encoding="encoding"] [standalone="standalone"] ?>  
[ piCommentList ]  
rootElement  
[ piCommentList ]  
```  
  
## <a name="parts"></a><span data-ttu-id="f5784-105">Части</span><span class="sxs-lookup"><span data-stu-id="f5784-105">Parts</span></span>  
  
|<span data-ttu-id="f5784-106">Термин</span><span class="sxs-lookup"><span data-stu-id="f5784-106">Term</span></span>|<span data-ttu-id="f5784-107">Определение</span><span class="sxs-lookup"><span data-stu-id="f5784-107">Definition</span></span>|  
|---|---|  
|`encoding`|<span data-ttu-id="f5784-108">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="f5784-108">Optional.</span></span> <span data-ttu-id="f5784-109">Использует литеральный текст, определения кодировки документа.</span><span class="sxs-lookup"><span data-stu-id="f5784-109">Literal text declaring which encoding the document uses.</span></span>|  
|`standalone`|<span data-ttu-id="f5784-110">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="f5784-110">Optional.</span></span> <span data-ttu-id="f5784-111">Литеральный текст.</span><span class="sxs-lookup"><span data-stu-id="f5784-111">Literal text.</span></span> <span data-ttu-id="f5784-112">Должен быть «yes» или «no».</span><span class="sxs-lookup"><span data-stu-id="f5784-112">Must be "yes" or "no".</span></span>|  
|`piCommentList`|<span data-ttu-id="f5784-113">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="f5784-113">Optional.</span></span> <span data-ttu-id="f5784-114">Список инструкции по обработке XML и XML-комментариев.</span><span class="sxs-lookup"><span data-stu-id="f5784-114">List of XML processing instructions and XML comments.</span></span> <span data-ttu-id="f5784-115">Имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="f5784-115">Takes the following format:</span></span><br /><br /> <span data-ttu-id="f5784-116">`piComment [` `piComment` `... ]`</span><span class="sxs-lookup"><span data-stu-id="f5784-116">`piComment [` `piComment` `... ]`</span></span><br /><br /> <span data-ttu-id="f5784-117">Каждый `piComment` может принимать одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="f5784-117">Each `piComment` can be one of the following:</span></span><br /><br /> <span data-ttu-id="f5784-118">-   [Литерал инструкции обработки XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span><span class="sxs-lookup"><span data-stu-id="f5784-118">-   [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span><br /><span data-ttu-id="f5784-119">-   [XML-литерал комментария](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span><span class="sxs-lookup"><span data-stu-id="f5784-119">-   [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>|  
|`rootElement`|<span data-ttu-id="f5784-120">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="f5784-120">Required.</span></span> <span data-ttu-id="f5784-121">Корневой элемент документа.</span><span class="sxs-lookup"><span data-stu-id="f5784-121">Root element of the document.</span></span> <span data-ttu-id="f5784-122">Одно из следующих имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="f5784-122">The format is one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="f5784-123">[XML-литерал элемента](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="f5784-123">[XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span></li><li><span data-ttu-id="f5784-124">Внедренные выражения вида `<%=` `elementExp` `%>`.</span><span class="sxs-lookup"><span data-stu-id="f5784-124">Embedded expression of the form `<%=` `elementExp` `%>`.</span></span> <span data-ttu-id="f5784-125">`elementExp` Возвращает одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="f5784-125">The `elementExp` returns one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="f5784-126">Объект <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="f5784-126">An <xref:System.Xml.Linq.XElement> object.</span></span></li><li><span data-ttu-id="f5784-127">Коллекция, содержащая один <xref:System.Xml.Linq.XElement> объекта и любое количество <xref:System.Xml.Linq.XProcessingInstruction> и <xref:System.Xml.Linq.XComment> объектов.</span><span class="sxs-lookup"><span data-stu-id="f5784-127">A collection that contains one <xref:System.Xml.Linq.XElement> object and any number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects.</span></span></li></ul></li></ul><br /> <span data-ttu-id="f5784-128">Дополнительные сведения см. в разделе [встроенные выражения в XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="f5784-128">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="f5784-129">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f5784-129">Return Value</span></span>  
 <span data-ttu-id="f5784-130">Объект <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="f5784-130">An <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5784-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="f5784-131">Remarks</span></span>  
 <span data-ttu-id="f5784-132">Литерала XML-документа определяется с помощью объявления XML в начале литерала.</span><span class="sxs-lookup"><span data-stu-id="f5784-132">An XML document literal is identified by the XML declaration at the start of the literal.</span></span> <span data-ttu-id="f5784-133">Несмотря на то, что каждый XML-литерала документа должен иметь ровно один корневой элемент XML, он может иметь любое количество инструкций по обработке XML и XML-комментариев.</span><span class="sxs-lookup"><span data-stu-id="f5784-133">Although each XML document literal must have exactly one root XML element, it can have any number of XML processing instructions and XML comments.</span></span>  
  
 <span data-ttu-id="f5784-134">Литерал XML-документа не может присутствовать в XML-элемента.</span><span class="sxs-lookup"><span data-stu-id="f5784-134">An XML document literal cannot appear in an XML element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f5784-135">XML-литерал может занимать несколько строк без использования символа продолжения строки.</span><span class="sxs-lookup"><span data-stu-id="f5784-135">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="f5784-136">Это позволяет скопировать содержимое из XML-документа и вставьте его непосредственно в программу Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f5784-136">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="f5784-137">Компилятор Visual Basic преобразует XML-литерала документа в вызовы <xref:System.Xml.Linq.XDocument.%23ctor%2A> и <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> конструкторы.</span><span class="sxs-lookup"><span data-stu-id="f5784-137">The Visual Basic compiler converts the XML document literal into calls to the <xref:System.Xml.Linq.XDocument.%23ctor%2A> and <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> constructors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5784-138">Пример</span><span class="sxs-lookup"><span data-stu-id="f5784-138">Example</span></span>  
 <span data-ttu-id="f5784-139">В следующем примере создается документ XML с XML-декларация, инструкции по обработке, комментарий и элемент, содержащий другой элемент.</span><span class="sxs-lookup"><span data-stu-id="f5784-139">The following example creates an XML document that has an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
 [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="f5784-140">См. также</span><span class="sxs-lookup"><span data-stu-id="f5784-140">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- <xref:System.Xml.Linq.XProcessingInstruction>
- <xref:System.Xml.Linq.XComment>
- <xref:System.Xml.Linq.XDocument>
- [<span data-ttu-id="f5784-141">XML-литерал инструкции обработки</span><span class="sxs-lookup"><span data-stu-id="f5784-141">XML Processing Instruction Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)
- [<span data-ttu-id="f5784-142">XML-литерал комментария</span><span class="sxs-lookup"><span data-stu-id="f5784-142">XML Comment Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)
- [<span data-ttu-id="f5784-143">XML-литерал элемента</span><span class="sxs-lookup"><span data-stu-id="f5784-143">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="f5784-144">XML-литералы</span><span class="sxs-lookup"><span data-stu-id="f5784-144">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="f5784-145">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f5784-145">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="f5784-146">Встроенные выражения в XML</span><span class="sxs-lookup"><span data-stu-id="f5784-146">Embedded Expressions in XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
