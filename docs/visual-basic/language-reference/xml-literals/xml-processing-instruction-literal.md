---
title: Литерал инструкции обработки XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralProcessingInstruction
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
ms.openlocfilehash: cb9ad1d687203dff497e4cd451933a8bbbdf4bf6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491237"
---
# <a name="xml-processing-instruction-literal-visual-basic"></a><span data-ttu-id="d1769-102">Литерал инструкции обработки XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d1769-102">XML Processing Instruction Literal (Visual Basic)</span></span>
<span data-ttu-id="d1769-103">Объект литерал, представляющий <xref:System.Xml.Linq.XProcessingInstruction> объекта.</span><span class="sxs-lookup"><span data-stu-id="d1769-103">A literal representing an <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1769-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d1769-104">Syntax</span></span>  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a><span data-ttu-id="d1769-105">Части</span><span class="sxs-lookup"><span data-stu-id="d1769-105">Parts</span></span>  
 `<?`  
 <span data-ttu-id="d1769-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="d1769-106">Required.</span></span> <span data-ttu-id="d1769-107">Обозначает начало литерала инструкции обработки XML.</span><span class="sxs-lookup"><span data-stu-id="d1769-107">Denotes the start of the XML processing instruction literal.</span></span>  
  
 `piName`  
 <span data-ttu-id="d1769-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="d1769-108">Required.</span></span> <span data-ttu-id="d1769-109">Имя, указывающее, какое приложение инструкции обработки.</span><span class="sxs-lookup"><span data-stu-id="d1769-109">Name indicating which application the processing instruction targets.</span></span> <span data-ttu-id="d1769-110">Не может начинаться с «xml» или «XML».</span><span class="sxs-lookup"><span data-stu-id="d1769-110">Cannot begin with "xml" or "XML".</span></span>  
  
 `piData`  
 <span data-ttu-id="d1769-111">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="d1769-111">Optional.</span></span> <span data-ttu-id="d1769-112">Строка, указывающая, каким образом приложение мишенью `piName` должен обрабатывать XML-документа.</span><span class="sxs-lookup"><span data-stu-id="d1769-112">String indicating how the application targeted by `piName` should process the XML document.</span></span>  
  
 `?>`  
 <span data-ttu-id="d1769-113">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="d1769-113">Required.</span></span> <span data-ttu-id="d1769-114">Обозначает конец инструкции обработки.</span><span class="sxs-lookup"><span data-stu-id="d1769-114">Denotes the end of the processing instruction.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d1769-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d1769-115">Return Value</span></span>  
 <span data-ttu-id="d1769-116">Объект <xref:System.Xml.Linq.XProcessingInstruction>.</span><span class="sxs-lookup"><span data-stu-id="d1769-116">An <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1769-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="d1769-117">Remarks</span></span>  
 <span data-ttu-id="d1769-118">Литералы инструкции обработки XML указывают, как приложения должны обрабатывать XML-документа.</span><span class="sxs-lookup"><span data-stu-id="d1769-118">XML processing instruction literals indicate how applications should process an XML document.</span></span> <span data-ttu-id="d1769-119">Когда приложение загружает XML-документ, приложение может проверять инструкции по обработке XML, чтобы определить способ обработки документа.</span><span class="sxs-lookup"><span data-stu-id="d1769-119">When an application loads an XML document, the application can check the XML processing instructions to determine how to process the document.</span></span> <span data-ttu-id="d1769-120">Приложение интерпретирует значение `piName` и `piData`.</span><span class="sxs-lookup"><span data-stu-id="d1769-120">The application interprets the meaning of `piName` and `piData`.</span></span>  
  
 <span data-ttu-id="d1769-121">XML-литерала документа использует синтаксис, который аналогичен инструкции по обработке XML.</span><span class="sxs-lookup"><span data-stu-id="d1769-121">The XML document literal uses syntax that is similar to that of the XML processing instruction.</span></span> <span data-ttu-id="d1769-122">Дополнительные сведения см. в разделе [литерала документа XML](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).</span><span class="sxs-lookup"><span data-stu-id="d1769-122">For more information, see [XML Document Literal](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d1769-123">`piName` Элемент не может начинаться с строки «xml» или «XML», поскольку в спецификации XML 1.0 резервирует эти идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="d1769-123">The `piName` element cannot begin with the strings "xml" or "XML", because the XML 1.0 specification reserves those identifiers.</span></span>  
  
 <span data-ttu-id="d1769-124">Можно присвоить переменной литерала инструкции обработки XML или включить в литерал XML-документа.</span><span class="sxs-lookup"><span data-stu-id="d1769-124">You can assign an XML processing instruction literal to a variable or include it in an XML document literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d1769-125">XML-литерал может занимать несколько строк без необходимости символы продолжения строки.</span><span class="sxs-lookup"><span data-stu-id="d1769-125">An XML literal can span multiple lines without needing line continuation characters.</span></span> <span data-ttu-id="d1769-126">Это позволяет скопировать содержимое из XML-документа и вставьте его непосредственно в программу Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d1769-126">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="d1769-127">Компилятор Visual Basic литерала инструкции обработки XML преобразуется в вызов <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> конструктор.</span><span class="sxs-lookup"><span data-stu-id="d1769-127">The Visual Basic compiler converts the XML processing instruction literal to a call to the <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1769-128">Пример</span><span class="sxs-lookup"><span data-stu-id="d1769-128">Example</span></span>  
 <span data-ttu-id="d1769-129">В следующем примере создается инструкция по обработке, определяющая таблицу стилей для XML-документа.</span><span class="sxs-lookup"><span data-stu-id="d1769-129">The following example creates a processing instruction identifying a style-sheet for an XML document.</span></span>  
  
 [!code-vb[VbXMLSamples#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-processing-instruction-literal_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d1769-130">См. также</span><span class="sxs-lookup"><span data-stu-id="d1769-130">See also</span></span>
- <xref:System.Xml.Linq.XProcessingInstruction>
- [<span data-ttu-id="d1769-131">XML-литерал документа</span><span class="sxs-lookup"><span data-stu-id="d1769-131">XML Document Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [<span data-ttu-id="d1769-132">XML-литералы</span><span class="sxs-lookup"><span data-stu-id="d1769-132">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="d1769-133">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d1769-133">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
