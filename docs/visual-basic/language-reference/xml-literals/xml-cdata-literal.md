---
title: Литеральное представление XML-раздела CDATA (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralCdata
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
ms.openlocfilehash: 01a505130d566ec88a6d87e5e9ad525e449d7298
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981248"
---
# <a name="xml-cdata-literal-visual-basic"></a><span data-ttu-id="ebb09-102">Литеральное представление XML-раздела CDATA (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ebb09-102">XML CDATA Literal (Visual Basic)</span></span>
<span data-ttu-id="ebb09-103">Объект литерал, представляющий <xref:System.Xml.Linq.XCData> объекта.</span><span class="sxs-lookup"><span data-stu-id="ebb09-103">A literal representing an <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebb09-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ebb09-104">Syntax</span></span>  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a><span data-ttu-id="ebb09-105">Части</span><span class="sxs-lookup"><span data-stu-id="ebb09-105">Parts</span></span>  
 `<![CDATA[`  
 <span data-ttu-id="ebb09-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="ebb09-106">Required.</span></span> <span data-ttu-id="ebb09-107">Обозначает начало раздела XML CDATA.</span><span class="sxs-lookup"><span data-stu-id="ebb09-107">Denotes the start of the XML CDATA section.</span></span>  
  
 `content`  
 <span data-ttu-id="ebb09-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="ebb09-108">Required.</span></span> <span data-ttu-id="ebb09-109">Текстовое содержимое в XML-раздела CDATA.</span><span class="sxs-lookup"><span data-stu-id="ebb09-109">Text content to appear in the XML CDATA section.</span></span>  
  
 `]]>`  
 <span data-ttu-id="ebb09-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="ebb09-110">Required.</span></span> <span data-ttu-id="ebb09-111">Обозначает конец раздела.</span><span class="sxs-lookup"><span data-stu-id="ebb09-111">Denotes the end of the section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ebb09-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ebb09-112">Return Value</span></span>  
 <span data-ttu-id="ebb09-113">Объект <xref:System.Xml.Linq.XCData>.</span><span class="sxs-lookup"><span data-stu-id="ebb09-113">An <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ebb09-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="ebb09-114">Remarks</span></span>  
 <span data-ttu-id="ebb09-115">Разделы XML CDATA содержит необработанный текст, который должен быть включено, но не синтаксический анализ, XML, он содержится.</span><span class="sxs-lookup"><span data-stu-id="ebb09-115">XML CDATA sections contain raw text that should be included, but not parsed, with the XML that contains it.</span></span> <span data-ttu-id="ebb09-116">Раздел XML CDATA может содержать любой текст.</span><span class="sxs-lookup"><span data-stu-id="ebb09-116">A XML CDATA section can contain any text.</span></span> <span data-ttu-id="ebb09-117">Это включает в себя зарезервированные символы XML.</span><span class="sxs-lookup"><span data-stu-id="ebb09-117">This includes reserved XML characters.</span></span> <span data-ttu-id="ebb09-118">Раздел XML CDATA заканчивается последовательность «]] >».</span><span class="sxs-lookup"><span data-stu-id="ebb09-118">The XML CDATA section ends with the sequence "]]>".</span></span> <span data-ttu-id="ebb09-119">Это подразумевает следующее:</span><span class="sxs-lookup"><span data-stu-id="ebb09-119">This implies the following points:</span></span>  
  
-   <span data-ttu-id="ebb09-120">Нельзя использовать внедренное выражение в представлении XML CDATA, поскольку разделители внедренного выражения являются допустимым содержимым XML CDATA.</span><span class="sxs-lookup"><span data-stu-id="ebb09-120">You cannot use an embedded expression in an XML CDATA literal because the embedded expression delimiters are valid XML CDATA content.</span></span>  
  
-   <span data-ttu-id="ebb09-121">Разделы XML CDATA не могут быть вложенными, так как `content` не может содержать значение «]] >».</span><span class="sxs-lookup"><span data-stu-id="ebb09-121">XML CDATA sections cannot be nested, because `content` cannot contain the value "]]>".</span></span>  
  
 <span data-ttu-id="ebb09-122">Можно присвоить переменной в представлении XML CDATA или включить его в литерале XML-элемента.</span><span class="sxs-lookup"><span data-stu-id="ebb09-122">You can assign an XML CDATA literal to a variable, or include it in an XML element literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ebb09-123">XML-литерал может занимать несколько строк, но не использует символы продолжения строки.</span><span class="sxs-lookup"><span data-stu-id="ebb09-123">An XML literal can span multiple lines but does not use line continuation characters.</span></span> <span data-ttu-id="ebb09-124">Это позволяет скопировать содержимое из XML-документа и вставьте его непосредственно в программу Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ebb09-124">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="ebb09-125">Компилятор Visual Basic литерала CDATA XML преобразуется в вызов <xref:System.Xml.Linq.XCData.%23ctor%2A> конструктор.</span><span class="sxs-lookup"><span data-stu-id="ebb09-125">The Visual Basic compiler converts the XML CDATA literal to a call to the <xref:System.Xml.Linq.XCData.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ebb09-126">Пример</span><span class="sxs-lookup"><span data-stu-id="ebb09-126">Example</span></span>  
 <span data-ttu-id="ebb09-127">В следующем примере создается раздел CDATA, содержащий текст «может содержать литерал \<XML > теги».</span><span class="sxs-lookup"><span data-stu-id="ebb09-127">The following example creates a CDATA section that contains the text "Can contain literal \<XML> tags".</span></span>  
  
 [!code-vb[VbXMLSamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="ebb09-128">См. также</span><span class="sxs-lookup"><span data-stu-id="ebb09-128">See also</span></span>
- <xref:System.Xml.Linq.XCData>
- [<span data-ttu-id="ebb09-129">XML-литерал элемента</span><span class="sxs-lookup"><span data-stu-id="ebb09-129">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="ebb09-130">XML-литералы</span><span class="sxs-lookup"><span data-stu-id="ebb09-130">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="ebb09-131">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ebb09-131">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
