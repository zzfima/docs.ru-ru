---
title: "XML-литерал комментария (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralComment
dev_langs:
- VB
helpviewer_keywords:
- comment literal [Visual Basic]
- XML comments, adding [Visual Basic]
- XML comment literal [Visual Basic]
- XML literals [Visual Basic], comment
ms.assetid: 634c1cee-5e01-48d0-88d7-2dd55e4a9e52
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
ms.openlocfilehash: ab896399b664c658710c24d9799218ff3d81aecc
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="xml-comment-literal-visual-basic"></a><span data-ttu-id="06739-102">XML-литерал комментариев (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="06739-102">XML Comment Literal (Visual Basic)</span></span>
<span data-ttu-id="06739-103">Литерал представляет <xref:System.Xml.Linq.XComment>объекта.</xref:System.Xml.Linq.XComment></span><span class="sxs-lookup"><span data-stu-id="06739-103">A literal representing an <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06739-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="06739-104">Syntax</span></span>  
  
```  
<!-- content -->  
```  
  
## <a name="parts"></a><span data-ttu-id="06739-105">Части</span><span class="sxs-lookup"><span data-stu-id="06739-105">Parts</span></span>  
  
|<span data-ttu-id="06739-106">Термин</span><span class="sxs-lookup"><span data-stu-id="06739-106">Term</span></span>|<span data-ttu-id="06739-107">Определение</span><span class="sxs-lookup"><span data-stu-id="06739-107">Definition</span></span>|  
|---|---|  
|`<!--`|<span data-ttu-id="06739-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="06739-108">Required.</span></span> <span data-ttu-id="06739-109">Обозначает начало комментария XML.</span><span class="sxs-lookup"><span data-stu-id="06739-109">Denotes the start of the XML comment.</span></span>|  
|`content`|<span data-ttu-id="06739-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="06739-110">Required.</span></span> <span data-ttu-id="06739-111">Текст для отображения в XML-комментарий.</span><span class="sxs-lookup"><span data-stu-id="06739-111">Text to appear in the XML comment.</span></span> <span data-ttu-id="06739-112">Не может содержать ряд двух дефисов (--) или заканчиваться дефисом рядом с закрывающим тегом.</span><span class="sxs-lookup"><span data-stu-id="06739-112">Cannot contain a series of two hyphens (--) or end with a hyphen adjacent to the closing tag.</span></span>|  
|`-->`|<span data-ttu-id="06739-113">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="06739-113">Required.</span></span> <span data-ttu-id="06739-114">Обозначает конец комментария XML.</span><span class="sxs-lookup"><span data-stu-id="06739-114">Denotes the end of the XML comment.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="06739-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="06739-115">Return Value</span></span>  
 <span data-ttu-id="06739-116"><xref:System.Xml.Linq.XComment>Объект.</xref:System.Xml.Linq.XComment></span><span class="sxs-lookup"><span data-stu-id="06739-116">An <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06739-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="06739-117">Remarks</span></span>  
 <span data-ttu-id="06739-118">XML-литералы комментариев не содержат содержимое документа; они содержат сведения о документе.</span><span class="sxs-lookup"><span data-stu-id="06739-118">XML comment literals do not contain document content; they contain information about the document.</span></span> <span data-ttu-id="06739-119">Раздел комментария XML заканчивается последовательностью «-->».</span><span class="sxs-lookup"><span data-stu-id="06739-119">The XML comment section ends with the sequence "-->".</span></span> <span data-ttu-id="06739-120">Это подразумевает следующее:</span><span class="sxs-lookup"><span data-stu-id="06739-120">This implies the following points:</span></span>  
  
-   <span data-ttu-id="06739-121">Нельзя использовать внедренное выражение в литерале комментария XML, поскольку разделители внедренного выражения являются допустимым содержимым комментария XML.</span><span class="sxs-lookup"><span data-stu-id="06739-121">You cannot use an embedded expression in an XML comment literal because the embedded expression delimiters are valid XML comment content.</span></span>  
  
-   <span data-ttu-id="06739-122">Разделы комментария XML не может быть вложенными, поскольку `content` не может содержать значение «-->».</span><span class="sxs-lookup"><span data-stu-id="06739-122">XML comment sections cannot be nested, because `content` cannot contain the value "-->".</span></span>  
  
 <span data-ttu-id="06739-123">XML-литерал комментария можно присвоить переменной, или его можно включить в литерал XML-элемента.</span><span class="sxs-lookup"><span data-stu-id="06739-123">You can assign an XML comment literal to a variable, or you can include it in an XML element literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="06739-124">XML-литерал может занимать несколько строк без использования символа продолжения строки.</span><span class="sxs-lookup"><span data-stu-id="06739-124">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="06739-125">Эта функция позволяет скопировать содержимое из XML-документа и вставьте его непосредственно в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] программы.</span><span class="sxs-lookup"><span data-stu-id="06739-125">This feature enables you to copy content from an XML document and paste it directly into a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] program.</span></span>  
  
 <span data-ttu-id="06739-126">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Компилятор преобразует XML-литерал комментария вызов <xref:System.Xml.Linq.XComment.%23ctor%2A>конструктор.</xref:System.Xml.Linq.XComment.%23ctor%2A></span><span class="sxs-lookup"><span data-stu-id="06739-126">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler converts the XML comment literal to a call to the <xref:System.Xml.Linq.XComment.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="06739-127">Пример</span><span class="sxs-lookup"><span data-stu-id="06739-127">Example</span></span>  
 <span data-ttu-id="06739-128">В следующем примере создается XML-комментарий с текстом «Это комментарий».</span><span class="sxs-lookup"><span data-stu-id="06739-128">The following example creates an XML comment that contains the text "This is a comment".</span></span>  
  
 <span data-ttu-id="06739-129">[!code-vb[VbXMLSamples №&9;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-comment-literal_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="06739-129">[!code-vb[VbXMLSamples#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-comment-literal_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06739-130">См. также</span><span class="sxs-lookup"><span data-stu-id="06739-130">See Also</span></span>  
 <span data-ttu-id="06739-131"><xref:System.Xml.Linq.XComment></xref:System.Xml.Linq.XComment></span><span class="sxs-lookup"><span data-stu-id="06739-131"><xref:System.Xml.Linq.XComment></span></span>   
<span data-ttu-id="06739-132"> [Литеральное представление XML элемента](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span><span class="sxs-lookup"><span data-stu-id="06739-132"> [XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span></span>  
<span data-ttu-id="06739-133"> [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md) </span><span class="sxs-lookup"><span data-stu-id="06739-133"> [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md) </span></span>  
<span data-ttu-id="06739-134"> [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)</span><span class="sxs-lookup"><span data-stu-id="06739-134"> [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)</span></span>
