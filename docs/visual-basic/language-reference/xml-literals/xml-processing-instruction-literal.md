---
title: "Литерал инструкции (Visual Basic) обработки XML | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralProcessingInstruction
dev_langs:
- VB
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
caps.latest.revision: 19
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
ms.openlocfilehash: 2ae976530ed3028677a1fef39db92265591df530
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="xml-processing-instruction-literal-visual-basic"></a><span data-ttu-id="47766-102">Литерал инструкции обработки XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="47766-102">XML Processing Instruction Literal (Visual Basic)</span></span>
<span data-ttu-id="47766-103">Литерал представляет <xref:System.Xml.Linq.XProcessingInstruction>объекта.</xref:System.Xml.Linq.XProcessingInstruction></span><span class="sxs-lookup"><span data-stu-id="47766-103">A literal representing an <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47766-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="47766-104">Syntax</span></span>  
  
```  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a><span data-ttu-id="47766-105">Части</span><span class="sxs-lookup"><span data-stu-id="47766-105">Parts</span></span>  
 `<?`  
 <span data-ttu-id="47766-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="47766-106">Required.</span></span> <span data-ttu-id="47766-107">Обозначает начало литерал инструкции обработки XML.</span><span class="sxs-lookup"><span data-stu-id="47766-107">Denotes the start of the XML processing instruction literal.</span></span>  
  
 `piName`  
 <span data-ttu-id="47766-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="47766-108">Required.</span></span> <span data-ttu-id="47766-109">Имя, указывающее целевое приложение инструкции обработки.</span><span class="sxs-lookup"><span data-stu-id="47766-109">Name indicating which application the processing instruction targets.</span></span> <span data-ttu-id="47766-110">Не может начинаться с «xml» или «XML».</span><span class="sxs-lookup"><span data-stu-id="47766-110">Cannot begin with "xml" or "XML".</span></span>  
  
 `piData`  
 <span data-ttu-id="47766-111">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="47766-111">Optional.</span></span> <span data-ttu-id="47766-112">Строка, указывающая, как приложение мишенью `piName` должен обрабатывать XML-документ.</span><span class="sxs-lookup"><span data-stu-id="47766-112">String indicating how the application targeted by `piName` should process the XML document.</span></span>  
  
 `?>`  
 <span data-ttu-id="47766-113">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="47766-113">Required.</span></span> <span data-ttu-id="47766-114">Обозначает конец инструкции обработки.</span><span class="sxs-lookup"><span data-stu-id="47766-114">Denotes the end of the processing instruction.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="47766-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="47766-115">Return Value</span></span>  
 <span data-ttu-id="47766-116"><xref:System.Xml.Linq.XProcessingInstruction>Объект.</xref:System.Xml.Linq.XProcessingInstruction></span><span class="sxs-lookup"><span data-stu-id="47766-116">An <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47766-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="47766-117">Remarks</span></span>  
 <span data-ttu-id="47766-118">XML литералы инструкции обработки указывают, как приложения должны обрабатывать XML-документ.</span><span class="sxs-lookup"><span data-stu-id="47766-118">XML processing instruction literals indicate how applications should process an XML document.</span></span> <span data-ttu-id="47766-119">Когда приложение загружает XML-документ, оно может проверить инструкции обработки XML для определения способа обработки документа.</span><span class="sxs-lookup"><span data-stu-id="47766-119">When an application loads an XML document, the application can check the XML processing instructions to determine how to process the document.</span></span> <span data-ttu-id="47766-120">Приложение интерпретирует значение `piName` и `piData`.</span><span class="sxs-lookup"><span data-stu-id="47766-120">The application interprets the meaning of `piName` and `piData`.</span></span>  
  
 <span data-ttu-id="47766-121">Литерал XML-документа использует синтаксис, аналогичный, инструкции по обработке XML.</span><span class="sxs-lookup"><span data-stu-id="47766-121">The XML document literal uses syntax that is similar to that of the XML processing instruction.</span></span> <span data-ttu-id="47766-122">Дополнительные сведения см. в разделе [литерала XML документ](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).</span><span class="sxs-lookup"><span data-stu-id="47766-122">For more information, see [XML Document Literal](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47766-123">`piName` Элемент не может начинаться со строки «xml» или «XML», поскольку спецификация XML 1.0 резервирует эти идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="47766-123">The `piName` element cannot begin with the strings "xml" or "XML", because the XML 1.0 specification reserves those identifiers.</span></span>  
  
 <span data-ttu-id="47766-124">Можно назначить литерал инструкции обработки XML переменной или включить ее в литерал XML-документа.</span><span class="sxs-lookup"><span data-stu-id="47766-124">You can assign an XML processing instruction literal to a variable or include it in an XML document literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47766-125">XML-литерал может занимать несколько строк без использования символа продолжения строки.</span><span class="sxs-lookup"><span data-stu-id="47766-125">An XML literal can span multiple lines without needing line continuation characters.</span></span> <span data-ttu-id="47766-126">Это позволяет скопировать содержимое из XML-документа и вставьте его непосредственно в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] программы.</span><span class="sxs-lookup"><span data-stu-id="47766-126">This enables you to copy content from an XML document and paste it directly into a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] program.</span></span>  
  
 <span data-ttu-id="47766-127">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Компилятор преобразует литерал инструкции обработки XML вызов <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A>конструктор.</xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A></span><span class="sxs-lookup"><span data-stu-id="47766-127">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler converts the XML processing instruction literal to a call to the <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47766-128">Пример</span><span class="sxs-lookup"><span data-stu-id="47766-128">Example</span></span>  
 <span data-ttu-id="47766-129">В следующем примере создается инструкцию обработки, определяющая таблицу стилей для XML-документа.</span><span class="sxs-lookup"><span data-stu-id="47766-129">The following example creates a processing instruction identifying a style-sheet for an XML document.</span></span>  
  
 <span data-ttu-id="47766-130">[!code-vb[VbXMLSamples&#28;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-processing-instruction-literal_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="47766-130">[!code-vb[VbXMLSamples#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-processing-instruction-literal_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47766-131">См. также</span><span class="sxs-lookup"><span data-stu-id="47766-131">See Also</span></span>  
 <span data-ttu-id="47766-132"><xref:System.Xml.Linq.XProcessingInstruction></xref:System.Xml.Linq.XProcessingInstruction></span><span class="sxs-lookup"><span data-stu-id="47766-132"><xref:System.Xml.Linq.XProcessingInstruction></span></span>   
<span data-ttu-id="47766-133"> [XML-литерал документа](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md) </span><span class="sxs-lookup"><span data-stu-id="47766-133"> [XML Document Literal](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md) </span></span>  
<span data-ttu-id="47766-134"> [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md) </span><span class="sxs-lookup"><span data-stu-id="47766-134"> [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md) </span></span>  
<span data-ttu-id="47766-135"> [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)</span><span class="sxs-lookup"><span data-stu-id="47766-135"> [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)</span></span>
