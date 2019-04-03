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
ms.openlocfilehash: ee269ca5cf9635fec35165d1ea65d6a6483cadef
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58828607"
---
# <a name="xml-cdata-literal-visual-basic"></a><span data-ttu-id="9e65e-102">Литеральное представление XML-раздела CDATA (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9e65e-102">XML CDATA Literal (Visual Basic)</span></span>
<span data-ttu-id="9e65e-103">Объект литерал, представляющий <xref:System.Xml.Linq.XCData> объекта.</span><span class="sxs-lookup"><span data-stu-id="9e65e-103">A literal representing an <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e65e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9e65e-104">Syntax</span></span>  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a><span data-ttu-id="9e65e-105">Части</span><span class="sxs-lookup"><span data-stu-id="9e65e-105">Parts</span></span>  
 `<![CDATA[`  
 <span data-ttu-id="9e65e-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="9e65e-106">Required.</span></span> <span data-ttu-id="9e65e-107">Обозначает начало раздела XML CDATA.</span><span class="sxs-lookup"><span data-stu-id="9e65e-107">Denotes the start of the XML CDATA section.</span></span>  
  
 `content`  
 <span data-ttu-id="9e65e-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="9e65e-108">Required.</span></span> <span data-ttu-id="9e65e-109">Текстовое содержимое в XML-раздела CDATA.</span><span class="sxs-lookup"><span data-stu-id="9e65e-109">Text content to appear in the XML CDATA section.</span></span>  
  
 `]]>`  
 <span data-ttu-id="9e65e-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="9e65e-110">Required.</span></span> <span data-ttu-id="9e65e-111">Обозначает конец раздела.</span><span class="sxs-lookup"><span data-stu-id="9e65e-111">Denotes the end of the section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9e65e-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9e65e-112">Return Value</span></span>  
 <span data-ttu-id="9e65e-113">Объект <xref:System.Xml.Linq.XCData>.</span><span class="sxs-lookup"><span data-stu-id="9e65e-113">An <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e65e-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="9e65e-114">Remarks</span></span>  
 <span data-ttu-id="9e65e-115">Разделы XML CDATA содержит необработанный текст, который должен быть включено, но не синтаксический анализ, XML, он содержится.</span><span class="sxs-lookup"><span data-stu-id="9e65e-115">XML CDATA sections contain raw text that should be included, but not parsed, with the XML that contains it.</span></span> <span data-ttu-id="9e65e-116">Раздел XML CDATA может содержать любой текст.</span><span class="sxs-lookup"><span data-stu-id="9e65e-116">A XML CDATA section can contain any text.</span></span> <span data-ttu-id="9e65e-117">Это включает в себя зарезервированные символы XML.</span><span class="sxs-lookup"><span data-stu-id="9e65e-117">This includes reserved XML characters.</span></span> <span data-ttu-id="9e65e-118">Раздел XML CDATA заканчивается последовательность «]] >».</span><span class="sxs-lookup"><span data-stu-id="9e65e-118">The XML CDATA section ends with the sequence "]]>".</span></span> <span data-ttu-id="9e65e-119">Это подразумевает следующее:</span><span class="sxs-lookup"><span data-stu-id="9e65e-119">This implies the following points:</span></span>  
  
-   <span data-ttu-id="9e65e-120">Нельзя использовать внедренное выражение в представлении XML CDATA, поскольку разделители внедренного выражения являются допустимым содержимым XML CDATA.</span><span class="sxs-lookup"><span data-stu-id="9e65e-120">You cannot use an embedded expression in an XML CDATA literal because the embedded expression delimiters are valid XML CDATA content.</span></span>  
  
-   <span data-ttu-id="9e65e-121">Разделы XML CDATA не могут быть вложенными, так как `content` не может содержать значение «]] >».</span><span class="sxs-lookup"><span data-stu-id="9e65e-121">XML CDATA sections cannot be nested, because `content` cannot contain the value "]]>".</span></span>  
  
 <span data-ttu-id="9e65e-122">Можно присвоить переменной в представлении XML CDATA или включить его в литерале XML-элемента.</span><span class="sxs-lookup"><span data-stu-id="9e65e-122">You can assign an XML CDATA literal to a variable, or include it in an XML element literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e65e-123">XML-литерал может занимать несколько строк, но не использует символы продолжения строки.</span><span class="sxs-lookup"><span data-stu-id="9e65e-123">An XML literal can span multiple lines but does not use line continuation characters.</span></span> <span data-ttu-id="9e65e-124">Это позволяет скопировать содержимое из XML-документа и вставьте его непосредственно в программу Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9e65e-124">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="9e65e-125">Компилятор Visual Basic литерала CDATA XML преобразуется в вызов <xref:System.Xml.Linq.XCData.%23ctor%2A> конструктор.</span><span class="sxs-lookup"><span data-stu-id="9e65e-125">The Visual Basic compiler converts the XML CDATA literal to a call to the <xref:System.Xml.Linq.XCData.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e65e-126">Пример</span><span class="sxs-lookup"><span data-stu-id="9e65e-126">Example</span></span>  
 <span data-ttu-id="9e65e-127">В следующем примере создается раздел CDATA, содержащий текст «может содержать литерал \<XML > теги».</span><span class="sxs-lookup"><span data-stu-id="9e65e-127">The following example creates a CDATA section that contains the text "Can contain literal \<XML> tags".</span></span>  
  
 [!code-vb[VbXMLSamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="9e65e-128">См. также</span><span class="sxs-lookup"><span data-stu-id="9e65e-128">See also</span></span>

- <xref:System.Xml.Linq.XCData>
- [<span data-ttu-id="9e65e-129">XML-литерал элемента</span><span class="sxs-lookup"><span data-stu-id="9e65e-129">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="9e65e-130">XML-литералы</span><span class="sxs-lookup"><span data-stu-id="9e65e-130">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="9e65e-131">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9e65e-131">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
