---
title: XML-литерал комментариев (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralComment
helpviewer_keywords:
- comment literal [Visual Basic]
- XML comments, adding [Visual Basic]
- XML comment literal [Visual Basic]
- XML literals [Visual Basic], comment
ms.assetid: 634c1cee-5e01-48d0-88d7-2dd55e4a9e52
ms.openlocfilehash: 149bbac6d301a9c2f166d05698e3780171126cb3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58827280"
---
# <a name="xml-comment-literal-visual-basic"></a><span data-ttu-id="5cb08-102">XML-литерал комментариев (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5cb08-102">XML Comment Literal (Visual Basic)</span></span>
<span data-ttu-id="5cb08-103">Объект литерал, представляющий <xref:System.Xml.Linq.XComment> объекта.</span><span class="sxs-lookup"><span data-stu-id="5cb08-103">A literal representing an <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cb08-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5cb08-104">Syntax</span></span>  
  
```xml  
<!-- content -->  
```  
  
## <a name="parts"></a><span data-ttu-id="5cb08-105">Части</span><span class="sxs-lookup"><span data-stu-id="5cb08-105">Parts</span></span>  
  
|<span data-ttu-id="5cb08-106">Термин</span><span class="sxs-lookup"><span data-stu-id="5cb08-106">Term</span></span>|<span data-ttu-id="5cb08-107">Определение</span><span class="sxs-lookup"><span data-stu-id="5cb08-107">Definition</span></span>|  
|---|---|  
|`<!--`|<span data-ttu-id="5cb08-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="5cb08-108">Required.</span></span> <span data-ttu-id="5cb08-109">Обозначает начало комментария XML.</span><span class="sxs-lookup"><span data-stu-id="5cb08-109">Denotes the start of the XML comment.</span></span>|  
|`content`|<span data-ttu-id="5cb08-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="5cb08-110">Required.</span></span> <span data-ttu-id="5cb08-111">Текст, появляющийся в комментарии XML.</span><span class="sxs-lookup"><span data-stu-id="5cb08-111">Text to appear in the XML comment.</span></span> <span data-ttu-id="5cb08-112">Не может содержать ряд два дефиса (-) или заканчиваться дефисом рядом закрывающий тег.</span><span class="sxs-lookup"><span data-stu-id="5cb08-112">Cannot contain a series of two hyphens (--) or end with a hyphen adjacent to the closing tag.</span></span>|  
|`-->`|<span data-ttu-id="5cb08-113">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="5cb08-113">Required.</span></span> <span data-ttu-id="5cb08-114">Обозначает конец комментария XML.</span><span class="sxs-lookup"><span data-stu-id="5cb08-114">Denotes the end of the XML comment.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="5cb08-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5cb08-115">Return Value</span></span>  
 <span data-ttu-id="5cb08-116">Объект <xref:System.Xml.Linq.XComment>.</span><span class="sxs-lookup"><span data-stu-id="5cb08-116">An <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5cb08-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="5cb08-117">Remarks</span></span>  
 <span data-ttu-id="5cb08-118">XML-литералы комментариев не содержат содержимого документа; они содержат сведения о документе.</span><span class="sxs-lookup"><span data-stu-id="5cb08-118">XML comment literals do not contain document content; they contain information about the document.</span></span> <span data-ttu-id="5cb08-119">Раздел комментариев XML заканчивается последовательность «-->».</span><span class="sxs-lookup"><span data-stu-id="5cb08-119">The XML comment section ends with the sequence "-->".</span></span> <span data-ttu-id="5cb08-120">Это подразумевает следующее:</span><span class="sxs-lookup"><span data-stu-id="5cb08-120">This implies the following points:</span></span>  
  
-   <span data-ttu-id="5cb08-121">Нельзя использовать внедренное выражение в XML-литерал комментария, поскольку разделители внедренного выражения представляют допустимое содержимое комментария XML.</span><span class="sxs-lookup"><span data-stu-id="5cb08-121">You cannot use an embedded expression in an XML comment literal because the embedded expression delimiters are valid XML comment content.</span></span>  
  
-   <span data-ttu-id="5cb08-122">Разделы комментария XML не могут быть вложенными, так как `content` не может содержать значение «-->».</span><span class="sxs-lookup"><span data-stu-id="5cb08-122">XML comment sections cannot be nested, because `content` cannot contain the value "-->".</span></span>  
  
 <span data-ttu-id="5cb08-123">XML-литерал комментария можно присвоить переменной, или ее можно включить в литерале XML-элемента.</span><span class="sxs-lookup"><span data-stu-id="5cb08-123">You can assign an XML comment literal to a variable, or you can include it in an XML element literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5cb08-124">XML-литерал может занимать несколько строк без использования символа продолжения строки.</span><span class="sxs-lookup"><span data-stu-id="5cb08-124">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="5cb08-125">Эта функция позволяет скопировать содержимое из XML-документа и вставьте его непосредственно в программу Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5cb08-125">This feature enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="5cb08-126">Компилятор Visual Basic преобразует XML-литерал комментария в вызов <xref:System.Xml.Linq.XComment.%23ctor%2A> конструктор.</span><span class="sxs-lookup"><span data-stu-id="5cb08-126">The Visual Basic compiler converts the XML comment literal to a call to the <xref:System.Xml.Linq.XComment.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5cb08-127">Пример</span><span class="sxs-lookup"><span data-stu-id="5cb08-127">Example</span></span>  
 <span data-ttu-id="5cb08-128">В следующем примере создается XML-комментарий, содержащий текст «Это комментарий».</span><span class="sxs-lookup"><span data-stu-id="5cb08-128">The following example creates an XML comment that contains the text "This is a comment".</span></span>  
  
 [!code-vb[VbXMLSamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="5cb08-129">См. также</span><span class="sxs-lookup"><span data-stu-id="5cb08-129">See also</span></span>

- <xref:System.Xml.Linq.XComment>
- [<span data-ttu-id="5cb08-130">XML-литерал элемента</span><span class="sxs-lookup"><span data-stu-id="5cb08-130">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="5cb08-131">XML-литералы</span><span class="sxs-lookup"><span data-stu-id="5cb08-131">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="5cb08-132">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5cb08-132">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
