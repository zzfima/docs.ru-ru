---
title: "XML-литерал документа (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralDocument
dev_langs:
- VB
helpviewer_keywords:
- XML document literal [Visual Basic]
- XML literals [Visual Basic], document
- XML documents [Visual Basic], creating
- document literal [Visual Basic]
ms.assetid: f7bbee56-0911-41de-b907-96f20450137b
caps.latest.revision: 20
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
ms.openlocfilehash: 5e173c8bc89f61925c3e6127fb3cac61379aeffa
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="xml-document-literal-visual-basic"></a><span data-ttu-id="abf67-102">XML-литерал документа (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="abf67-102">XML Document Literal (Visual Basic)</span></span>
<span data-ttu-id="abf67-103">Литерал представляет <xref:System.Xml.Linq.XDocument>объекта.</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="abf67-103">A literal representing an <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abf67-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="abf67-104">Syntax</span></span>  
  
```  
<?xml version="1.0" [encoding="encoding"] [standalone="standalone"] ?>  
[ piCommentList ]  
rootElement  
[ piCommentList ]  
```  
  
## <a name="parts"></a><span data-ttu-id="abf67-105">Части</span><span class="sxs-lookup"><span data-stu-id="abf67-105">Parts</span></span>  
  
|<span data-ttu-id="abf67-106">Термин</span><span class="sxs-lookup"><span data-stu-id="abf67-106">Term</span></span>|<span data-ttu-id="abf67-107">Определение</span><span class="sxs-lookup"><span data-stu-id="abf67-107">Definition</span></span>|  
|---|---|  
|`encoding`|<span data-ttu-id="abf67-108">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="abf67-108">Optional.</span></span> <span data-ttu-id="abf67-109">Использует текст литерала для определения, какая кодировка документа.</span><span class="sxs-lookup"><span data-stu-id="abf67-109">Literal text declaring which encoding the document uses.</span></span>|  
|`standalone`|<span data-ttu-id="abf67-110">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="abf67-110">Optional.</span></span> <span data-ttu-id="abf67-111">Обычный текст.</span><span class="sxs-lookup"><span data-stu-id="abf67-111">Literal text.</span></span> <span data-ttu-id="abf67-112">Должно быть «Да» или «нет».</span><span class="sxs-lookup"><span data-stu-id="abf67-112">Must be "yes" or "no".</span></span>|  
|`piCommentList`|<span data-ttu-id="abf67-113">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="abf67-113">Optional.</span></span> <span data-ttu-id="abf67-114">Список инструкций по обработке XML и XML-комментариев.</span><span class="sxs-lookup"><span data-stu-id="abf67-114">List of XML processing instructions and XML comments.</span></span> <span data-ttu-id="abf67-115">Имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="abf67-115">Takes the following format:</span></span><br /><br /> <span data-ttu-id="abf67-116">`piComment [` `piComment` `... ]`</span><span class="sxs-lookup"><span data-stu-id="abf67-116">`piComment [` `piComment` `... ]`</span></span><br /><br /> <span data-ttu-id="abf67-117">Каждая `piComment`может принимать одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="abf67-117">Each `piComment`can be one of the following:</span></span><br /><br /><span data-ttu-id="abf67-118"> -   [Литерал инструкции обработки XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span><span class="sxs-lookup"><span data-stu-id="abf67-118"> -   [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span><br /><span data-ttu-id="abf67-119">-   [XML-литерал комментария](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span><span class="sxs-lookup"><span data-stu-id="abf67-119">-   [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>|  
|`rootElement`|<span data-ttu-id="abf67-120">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="abf67-120">Required.</span></span> <span data-ttu-id="abf67-121">Корневой элемент документа.</span><span class="sxs-lookup"><span data-stu-id="abf67-121">Root element of the document.</span></span> <span data-ttu-id="abf67-122">Формат является одним из следующих:</span><span class="sxs-lookup"><span data-stu-id="abf67-122">The format is one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="abf67-123">[XML-литерал элемента](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="abf67-123">[XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span></li><li><span data-ttu-id="abf67-124">Встроенные выражения в форме `<%=` `elementExp` `%>`.</span><span class="sxs-lookup"><span data-stu-id="abf67-124">Embedded expression of the form `<%=` `elementExp` `%>`.</span></span> <span data-ttu-id="abf67-125">`elementExp` Возвращает одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="abf67-125">The `elementExp` returns one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="abf67-126"><xref:System.Xml.Linq.XElement>Объект.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="abf67-126">An <xref:System.Xml.Linq.XElement> object.</span></span></li><li><span data-ttu-id="abf67-127">Коллекция, содержащая один <xref:System.Xml.Linq.XElement>объекта и любым количеством <xref:System.Xml.Linq.XProcessingInstruction>и <xref:System.Xml.Linq.XComment>объекты.</xref:System.Xml.Linq.XComment> </xref:System.Xml.Linq.XProcessingInstruction> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="abf67-127">A collection that contains one <xref:System.Xml.Linq.XElement> object and any number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects.</span></span></li></ul></li></ul><br /> <span data-ttu-id="abf67-128">Дополнительные сведения см. в разделе [встроенные выражения в XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="abf67-128">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="abf67-129">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="abf67-129">Return Value</span></span>  
 <span data-ttu-id="abf67-130"><xref:System.Xml.Linq.XDocument>Объект.</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="abf67-130">An <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="abf67-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="abf67-131">Remarks</span></span>  
 <span data-ttu-id="abf67-132">Литерал XML-документа определяется XML-декларация в начале литерала.</span><span class="sxs-lookup"><span data-stu-id="abf67-132">An XML document literal is identified by the XML declaration at the start of the literal.</span></span> <span data-ttu-id="abf67-133">Несмотря на то, что каждый литерал XML-документа должен иметь ровно один корневой элемент XML, он может иметь любое количество инструкций по обработке XML и XML-комментариев.</span><span class="sxs-lookup"><span data-stu-id="abf67-133">Although each XML document literal must have exactly one root XML element, it can have any number of XML processing instructions and XML comments.</span></span>  
  
 <span data-ttu-id="abf67-134">Литерал XML-документа не может присутствовать в XML-элемента.</span><span class="sxs-lookup"><span data-stu-id="abf67-134">An XML document literal cannot appear in an XML element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="abf67-135">XML-литерал может занимать несколько строк без использования символа продолжения строки.</span><span class="sxs-lookup"><span data-stu-id="abf67-135">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="abf67-136">Это позволяет скопировать содержимое из XML-документа и вставьте его непосредственно в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] программы.</span><span class="sxs-lookup"><span data-stu-id="abf67-136">This enables you to copy content from an XML document and paste it directly into a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] program.</span></span>  
  
 <span data-ttu-id="abf67-137">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Компилятор преобразует литерала XML-документа в вызовы <xref:System.Xml.Linq.XDocument.%23ctor%2A>и <xref:System.Xml.Linq.XDeclaration.%23ctor%2A>конструкторы.</xref:System.Xml.Linq.XDeclaration.%23ctor%2A> </xref:System.Xml.Linq.XDocument.%23ctor%2A></span><span class="sxs-lookup"><span data-stu-id="abf67-137">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler converts the XML document literal into calls to the <xref:System.Xml.Linq.XDocument.%23ctor%2A> and <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> constructors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="abf67-138">Пример</span><span class="sxs-lookup"><span data-stu-id="abf67-138">Example</span></span>  
 <span data-ttu-id="abf67-139">В следующем примере создается XML-документ, который содержит XML-декларация, инструкции по обработке, комментарий и элемент, содержащий другой элемент.</span><span class="sxs-lookup"><span data-stu-id="abf67-139">The following example creates an XML document that has an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
 <span data-ttu-id="abf67-140">[!code-vb[VbXMLSamples&#30;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-document-literal_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="abf67-140">[!code-vb[VbXMLSamples#30](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-document-literal_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abf67-141">См. также</span><span class="sxs-lookup"><span data-stu-id="abf67-141">See Also</span></span>  
 <span data-ttu-id="abf67-142"><xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="abf67-142"><xref:System.Xml.Linq.XElement></span></span>   
 <span data-ttu-id="abf67-143"><xref:System.Xml.Linq.XProcessingInstruction></xref:System.Xml.Linq.XProcessingInstruction></span><span class="sxs-lookup"><span data-stu-id="abf67-143"><xref:System.Xml.Linq.XProcessingInstruction></span></span>   
 <span data-ttu-id="abf67-144"><xref:System.Xml.Linq.XComment></xref:System.Xml.Linq.XComment></span><span class="sxs-lookup"><span data-stu-id="abf67-144"><xref:System.Xml.Linq.XComment></span></span>   
 <span data-ttu-id="abf67-145"><xref:System.Xml.Linq.XDocument></xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="abf67-145"><xref:System.Xml.Linq.XDocument></span></span>   
<span data-ttu-id="abf67-146"> [Литерал инструкции обработки XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md) </span><span class="sxs-lookup"><span data-stu-id="abf67-146"> [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md) </span></span>  
<span data-ttu-id="abf67-147"> [XML-литерал комментария](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md) </span><span class="sxs-lookup"><span data-stu-id="abf67-147"> [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md) </span></span>  
<span data-ttu-id="abf67-148"> [Литеральное представление XML элемента](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span><span class="sxs-lookup"><span data-stu-id="abf67-148"> [XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span></span>  
<span data-ttu-id="abf67-149"> [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md) </span><span class="sxs-lookup"><span data-stu-id="abf67-149"> [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md) </span></span>  
<span data-ttu-id="abf67-150"> [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="abf67-150"> [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="abf67-151"> [Встроенные выражения в XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)</span><span class="sxs-lookup"><span data-stu-id="abf67-151"> [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)</span></span>
