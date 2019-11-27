---
title: XML-литерал инструкции обработки
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralProcessingInstruction
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
ms.openlocfilehash: 3602a81feae9287a77d060bb46f10eefee4fc05d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347037"
---
# <a name="xml-processing-instruction-literal-visual-basic"></a><span data-ttu-id="a6226-102">Литерал инструкции обработки XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a6226-102">XML Processing Instruction Literal (Visual Basic)</span></span>
<span data-ttu-id="a6226-103">Литерал, представляющий объект <xref:System.Xml.Linq.XProcessingInstruction>.</span><span class="sxs-lookup"><span data-stu-id="a6226-103">A literal representing an <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6226-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a6226-104">Syntax</span></span>  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a><span data-ttu-id="a6226-105">Части</span><span class="sxs-lookup"><span data-stu-id="a6226-105">Parts</span></span>  
 `<?`  
 <span data-ttu-id="a6226-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="a6226-106">Required.</span></span> <span data-ttu-id="a6226-107">Обозначает начало литерала инструкции обработки XML.</span><span class="sxs-lookup"><span data-stu-id="a6226-107">Denotes the start of the XML processing instruction literal.</span></span>  
  
 `piName`  
 <span data-ttu-id="a6226-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="a6226-108">Required.</span></span> <span data-ttu-id="a6226-109">Имя, указывающее, какое приложение предназначено для инструкции по обработке.</span><span class="sxs-lookup"><span data-stu-id="a6226-109">Name indicating which application the processing instruction targets.</span></span> <span data-ttu-id="a6226-110">Не может начинаться с "XML" или "XML".</span><span class="sxs-lookup"><span data-stu-id="a6226-110">Cannot begin with "xml" or "XML".</span></span>  
  
 `piData`  
 <span data-ttu-id="a6226-111">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="a6226-111">Optional.</span></span> <span data-ttu-id="a6226-112">Строка, указывающая, как приложение, на которое нацелена `piName`, должно обрабатывать XML-документ.</span><span class="sxs-lookup"><span data-stu-id="a6226-112">String indicating how the application targeted by `piName` should process the XML document.</span></span>  
  
 `?>`  
 <span data-ttu-id="a6226-113">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="a6226-113">Required.</span></span> <span data-ttu-id="a6226-114">Обозначает конец инструкции по обработке.</span><span class="sxs-lookup"><span data-stu-id="a6226-114">Denotes the end of the processing instruction.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a6226-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a6226-115">Return Value</span></span>  
 <span data-ttu-id="a6226-116">Объект <xref:System.Xml.Linq.XProcessingInstruction>.</span><span class="sxs-lookup"><span data-stu-id="a6226-116">An <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6226-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="a6226-117">Remarks</span></span>  
 <span data-ttu-id="a6226-118">Литералы инструкций обработки XML указывают, как приложения должны обрабатывать XML-документ.</span><span class="sxs-lookup"><span data-stu-id="a6226-118">XML processing instruction literals indicate how applications should process an XML document.</span></span> <span data-ttu-id="a6226-119">Когда приложение загружает XML-документ, приложение может проверить инструкции по обработке XML, чтобы определить способ обработки документа.</span><span class="sxs-lookup"><span data-stu-id="a6226-119">When an application loads an XML document, the application can check the XML processing instructions to determine how to process the document.</span></span> <span data-ttu-id="a6226-120">Приложение интерпретирует значение `piName` и `piData`.</span><span class="sxs-lookup"><span data-stu-id="a6226-120">The application interprets the meaning of `piName` and `piData`.</span></span>  
  
 <span data-ttu-id="a6226-121">В литерале XML-документа используется синтаксис, схожий с инструкцией по обработке XML.</span><span class="sxs-lookup"><span data-stu-id="a6226-121">The XML document literal uses syntax that is similar to that of the XML processing instruction.</span></span> <span data-ttu-id="a6226-122">Дополнительные сведения см. в разделе [XML-литерал документа](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).</span><span class="sxs-lookup"><span data-stu-id="a6226-122">For more information, see [XML Document Literal](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a6226-123">Элемент `piName` не может начинаться со строк "XML" или "XML", поскольку спецификация XML 1,0 резервирует эти идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="a6226-123">The `piName` element cannot begin with the strings "xml" or "XML", because the XML 1.0 specification reserves those identifiers.</span></span>  
  
 <span data-ttu-id="a6226-124">Литерал инструкции обработки XML можно назначить переменной или включить в литерал XML-документа.</span><span class="sxs-lookup"><span data-stu-id="a6226-124">You can assign an XML processing instruction literal to a variable or include it in an XML document literal.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a6226-125">XML-литерал может охватывать несколько строк без символов продолжения строки.</span><span class="sxs-lookup"><span data-stu-id="a6226-125">An XML literal can span multiple lines without needing line continuation characters.</span></span> <span data-ttu-id="a6226-126">Это позволяет копировать содержимое из XML-документа и вставлять его непосредственно в Visual Basic программу.</span><span class="sxs-lookup"><span data-stu-id="a6226-126">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="a6226-127">Компилятор Visual Basic преобразует литерал инструкции обработки XML в вызов конструктора <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A>.</span><span class="sxs-lookup"><span data-stu-id="a6226-127">The Visual Basic compiler converts the XML processing instruction literal to a call to the <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6226-128">Пример</span><span class="sxs-lookup"><span data-stu-id="a6226-128">Example</span></span>  
 <span data-ttu-id="a6226-129">В следующем примере создается инструкция по обработке, определяющая таблицу стилей для XML-документа.</span><span class="sxs-lookup"><span data-stu-id="a6226-129">The following example creates a processing instruction identifying a style-sheet for an XML document.</span></span>  
  
 [!code-vb[VbXMLSamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="a6226-130">См. также</span><span class="sxs-lookup"><span data-stu-id="a6226-130">See also</span></span>

- <xref:System.Xml.Linq.XProcessingInstruction>
- [<span data-ttu-id="a6226-131">XML-литерал документа</span><span class="sxs-lookup"><span data-stu-id="a6226-131">XML Document Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [<span data-ttu-id="a6226-132">XML-литералы</span><span class="sxs-lookup"><span data-stu-id="a6226-132">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="a6226-133">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a6226-133">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
