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
ms.openlocfilehash: 91369392f33f2a86a7a4cb5ffb3faa668c113348
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965402"
---
# <a name="xml-comment-literal-visual-basic"></a><span data-ttu-id="67e39-102">XML-литерал комментариев (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67e39-102">XML Comment Literal (Visual Basic)</span></span>
<span data-ttu-id="67e39-103">Литерал, представляющий <xref:System.Xml.Linq.XComment> объект.</span><span class="sxs-lookup"><span data-stu-id="67e39-103">A literal representing an <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67e39-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="67e39-104">Syntax</span></span>  
  
```xml  
<!-- content -->  
```  
  
## <a name="parts"></a><span data-ttu-id="67e39-105">Части</span><span class="sxs-lookup"><span data-stu-id="67e39-105">Parts</span></span>  
  
|<span data-ttu-id="67e39-106">Термин</span><span class="sxs-lookup"><span data-stu-id="67e39-106">Term</span></span>|<span data-ttu-id="67e39-107">Определение</span><span class="sxs-lookup"><span data-stu-id="67e39-107">Definition</span></span>|  
|---|---|  
|`<!--`|<span data-ttu-id="67e39-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="67e39-108">Required.</span></span> <span data-ttu-id="67e39-109">Обозначает начало XML-комментария.</span><span class="sxs-lookup"><span data-stu-id="67e39-109">Denotes the start of the XML comment.</span></span>|  
|`content`|<span data-ttu-id="67e39-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="67e39-110">Required.</span></span> <span data-ttu-id="67e39-111">Текст, отображаемый в XML-комментарии.</span><span class="sxs-lookup"><span data-stu-id="67e39-111">Text to appear in the XML comment.</span></span> <span data-ttu-id="67e39-112">Не может содержать последовательность из двух дефисов (--) или заканчиваться дефисом, рядом с закрывающим тегом.</span><span class="sxs-lookup"><span data-stu-id="67e39-112">Cannot contain a series of two hyphens (--) or end with a hyphen adjacent to the closing tag.</span></span>|  
|`-->`|<span data-ttu-id="67e39-113">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="67e39-113">Required.</span></span> <span data-ttu-id="67e39-114">Обозначает конец XML-комментария.</span><span class="sxs-lookup"><span data-stu-id="67e39-114">Denotes the end of the XML comment.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="67e39-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="67e39-115">Return Value</span></span>  
 <span data-ttu-id="67e39-116">Объект <xref:System.Xml.Linq.XComment>.</span><span class="sxs-lookup"><span data-stu-id="67e39-116">An <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67e39-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="67e39-117">Remarks</span></span>  
 <span data-ttu-id="67e39-118">Литералы XML-комментариев не содержат содержимого документа; они содержат сведения о документе.</span><span class="sxs-lookup"><span data-stu-id="67e39-118">XML comment literals do not contain document content; they contain information about the document.</span></span> <span data-ttu-id="67e39-119">Раздел комментария XML заканчивается последовательностью "-->".</span><span class="sxs-lookup"><span data-stu-id="67e39-119">The XML comment section ends with the sequence "-->".</span></span> <span data-ttu-id="67e39-120">Это подразумевает следующие моменты:</span><span class="sxs-lookup"><span data-stu-id="67e39-120">This implies the following points:</span></span>  
  
- <span data-ttu-id="67e39-121">Нельзя использовать внедренное выражение в литерале XML-комментария, так как разделители внедренных выражений являются допустимым содержимым XML-комментариев.</span><span class="sxs-lookup"><span data-stu-id="67e39-121">You cannot use an embedded expression in an XML comment literal because the embedded expression delimiters are valid XML comment content.</span></span>  
  
- <span data-ttu-id="67e39-122">Разделы комментариев XML не могут быть вложенными `content` , поскольку не могут содержать значение "-->".</span><span class="sxs-lookup"><span data-stu-id="67e39-122">XML comment sections cannot be nested, because `content` cannot contain the value "-->".</span></span>  
  
 <span data-ttu-id="67e39-123">Литерал комментария XML можно назначить переменной или включить в литерал XML-элемента.</span><span class="sxs-lookup"><span data-stu-id="67e39-123">You can assign an XML comment literal to a variable, or you can include it in an XML element literal.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="67e39-124">XML-литерал может охватывать несколько строк без использования символов продолжения строки.</span><span class="sxs-lookup"><span data-stu-id="67e39-124">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="67e39-125">Эта функция позволяет копировать содержимое из XML-документа и вставлять его непосредственно в Visual Basic программу.</span><span class="sxs-lookup"><span data-stu-id="67e39-125">This feature enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="67e39-126">Компилятор Visual Basic преобразует литерал XML-комментария в вызов <xref:System.Xml.Linq.XComment.%23ctor%2A> конструктора.</span><span class="sxs-lookup"><span data-stu-id="67e39-126">The Visual Basic compiler converts the XML comment literal to a call to the <xref:System.Xml.Linq.XComment.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67e39-127">Пример</span><span class="sxs-lookup"><span data-stu-id="67e39-127">Example</span></span>  
 <span data-ttu-id="67e39-128">В следующем примере создается XML-комментарий, содержащий текст "это комментарий".</span><span class="sxs-lookup"><span data-stu-id="67e39-128">The following example creates an XML comment that contains the text "This is a comment".</span></span>  
  
 [!code-vb[VbXMLSamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="67e39-129">См. также</span><span class="sxs-lookup"><span data-stu-id="67e39-129">See also</span></span>

- <xref:System.Xml.Linq.XComment>
- [<span data-ttu-id="67e39-130">XML-литерал элемента</span><span class="sxs-lookup"><span data-stu-id="67e39-130">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="67e39-131">XML-литералы</span><span class="sxs-lookup"><span data-stu-id="67e39-131">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="67e39-132">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="67e39-132">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
