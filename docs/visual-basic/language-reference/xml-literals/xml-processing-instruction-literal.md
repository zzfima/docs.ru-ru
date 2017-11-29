---
title: "Литерал инструкции обработки XML (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.XmlLiteralProcessingInstruction
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9ce0f2d0dff80072beefdb4f84643ea28e2cf165
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="xml-processing-instruction-literal-visual-basic"></a><span data-ttu-id="61f5c-102">Литерал инструкции обработки XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="61f5c-102">XML Processing Instruction Literal (Visual Basic)</span></span>
<span data-ttu-id="61f5c-103">Объект литерал, представляющий <xref:System.Xml.Linq.XProcessingInstruction> объекта.</span><span class="sxs-lookup"><span data-stu-id="61f5c-103">A literal representing an <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61f5c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="61f5c-104">Syntax</span></span>  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a><span data-ttu-id="61f5c-105">Части</span><span class="sxs-lookup"><span data-stu-id="61f5c-105">Parts</span></span>  
 `<?`  
 <span data-ttu-id="61f5c-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="61f5c-106">Required.</span></span> <span data-ttu-id="61f5c-107">Обозначает начало литерала инструкции обработки XML.</span><span class="sxs-lookup"><span data-stu-id="61f5c-107">Denotes the start of the XML processing instruction literal.</span></span>  
  
 `piName`  
 <span data-ttu-id="61f5c-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="61f5c-108">Required.</span></span> <span data-ttu-id="61f5c-109">Имя, указывающее, какое приложение инструкции обработки.</span><span class="sxs-lookup"><span data-stu-id="61f5c-109">Name indicating which application the processing instruction targets.</span></span> <span data-ttu-id="61f5c-110">Не может начинаться с «xml» или «XML».</span><span class="sxs-lookup"><span data-stu-id="61f5c-110">Cannot begin with "xml" or "XML".</span></span>  
  
 `piData`  
 <span data-ttu-id="61f5c-111">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="61f5c-111">Optional.</span></span> <span data-ttu-id="61f5c-112">Строка, указывающая, как приложение распространяется `piName` должен обрабатывать XML-документ.</span><span class="sxs-lookup"><span data-stu-id="61f5c-112">String indicating how the application targeted by `piName` should process the XML document.</span></span>  
  
 `?>`  
 <span data-ttu-id="61f5c-113">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="61f5c-113">Required.</span></span> <span data-ttu-id="61f5c-114">Обозначает конец инструкции обработки.</span><span class="sxs-lookup"><span data-stu-id="61f5c-114">Denotes the end of the processing instruction.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="61f5c-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="61f5c-115">Return Value</span></span>  
 <span data-ttu-id="61f5c-116">Объект <xref:System.Xml.Linq.XProcessingInstruction>.</span><span class="sxs-lookup"><span data-stu-id="61f5c-116">An <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61f5c-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="61f5c-117">Remarks</span></span>  
 <span data-ttu-id="61f5c-118">XML литералы инструкции обработки указывают, как приложения должны обрабатывать XML-документа.</span><span class="sxs-lookup"><span data-stu-id="61f5c-118">XML processing instruction literals indicate how applications should process an XML document.</span></span> <span data-ttu-id="61f5c-119">Когда приложение загружает XML-документ, приложение может проверить инструкции обработки XML, чтобы определить способ обработки документа.</span><span class="sxs-lookup"><span data-stu-id="61f5c-119">When an application loads an XML document, the application can check the XML processing instructions to determine how to process the document.</span></span> <span data-ttu-id="61f5c-120">Приложение интерпретирует значение `piName` и `piData`.</span><span class="sxs-lookup"><span data-stu-id="61f5c-120">The application interprets the meaning of `piName` and `piData`.</span></span>  
  
 <span data-ttu-id="61f5c-121">XML-литерала документа использует синтаксис, аналогичный синтаксису инструкции по обработке XML.</span><span class="sxs-lookup"><span data-stu-id="61f5c-121">The XML document literal uses syntax that is similar to that of the XML processing instruction.</span></span> <span data-ttu-id="61f5c-122">Дополнительные сведения см. в разделе [литерала документа XML](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).</span><span class="sxs-lookup"><span data-stu-id="61f5c-122">For more information, see [XML Document Literal](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="61f5c-123">`piName` Элемент не может начинаться со строки «xml» или «XML», так как спецификации XML 1.0 резервирует эти идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="61f5c-123">The `piName` element cannot begin with the strings "xml" or "XML", because the XML 1.0 specification reserves those identifiers.</span></span>  
  
 <span data-ttu-id="61f5c-124">Можно назначить литерал инструкции обработки XML переменной или включить ее в литерал XML-документа.</span><span class="sxs-lookup"><span data-stu-id="61f5c-124">You can assign an XML processing instruction literal to a variable or include it in an XML document literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="61f5c-125">XML-литерал может занимать несколько строк без использования символа продолжения строки.</span><span class="sxs-lookup"><span data-stu-id="61f5c-125">An XML literal can span multiple lines without needing line continuation characters.</span></span> <span data-ttu-id="61f5c-126">Это позволяет скопировать содержимое из XML-документа и вставьте его непосредственно в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] программы.</span><span class="sxs-lookup"><span data-stu-id="61f5c-126">This enables you to copy content from an XML document and paste it directly into a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] program.</span></span>  
  
 <span data-ttu-id="61f5c-127">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Компилятор преобразует литерала инструкции обработки XML вызов <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> конструктор.</span><span class="sxs-lookup"><span data-stu-id="61f5c-127">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler converts the XML processing instruction literal to a call to the <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61f5c-128">Пример</span><span class="sxs-lookup"><span data-stu-id="61f5c-128">Example</span></span>  
 <span data-ttu-id="61f5c-129">В следующем примере создается определение таблицы стилей для XML-документ инструкцию по обработке.</span><span class="sxs-lookup"><span data-stu-id="61f5c-129">The following example creates a processing instruction identifying a style-sheet for an XML document.</span></span>  
  
 [!code-vb[VbXMLSamples#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-processing-instruction-literal_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="61f5c-130">См. также</span><span class="sxs-lookup"><span data-stu-id="61f5c-130">See Also</span></span>  
 <xref:System.Xml.Linq.XProcessingInstruction>  
 [<span data-ttu-id="61f5c-131">XML-литерал документа</span><span class="sxs-lookup"><span data-stu-id="61f5c-131">XML Document Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)  
 [<span data-ttu-id="61f5c-132">XML-литералы</span><span class="sxs-lookup"><span data-stu-id="61f5c-132">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="61f5c-133">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="61f5c-133">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
