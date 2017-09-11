---
title: "Литеральное представление XML-раздела CDATA (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralCdata
dev_langs:
- VB
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
caps.latest.revision: 16
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
ms.openlocfilehash: 6bf12a5dd5b24b0a915cb15f41cb8947c33e94b0
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="xml-cdata-literal-visual-basic"></a><span data-ttu-id="75ab6-102">Литеральное представление XML-раздела CDATA (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75ab6-102">XML CDATA Literal (Visual Basic)</span></span>
<span data-ttu-id="75ab6-103">Литерал представляет <xref:System.Xml.Linq.XCData>объекта.</xref:System.Xml.Linq.XCData></span><span class="sxs-lookup"><span data-stu-id="75ab6-103">A literal representing an <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75ab6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="75ab6-104">Syntax</span></span>  
  
```  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a><span data-ttu-id="75ab6-105">Части</span><span class="sxs-lookup"><span data-stu-id="75ab6-105">Parts</span></span>  
 `<![CDATA[`  
 <span data-ttu-id="75ab6-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="75ab6-106">Required.</span></span> <span data-ttu-id="75ab6-107">Обозначает начало раздела XML CDATA.</span><span class="sxs-lookup"><span data-stu-id="75ab6-107">Denotes the start of the XML CDATA section.</span></span>  
  
 `content`  
 <span data-ttu-id="75ab6-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="75ab6-108">Required.</span></span> <span data-ttu-id="75ab6-109">Текст содержимого для отображения в разделе XML CDATA.</span><span class="sxs-lookup"><span data-stu-id="75ab6-109">Text content to appear in the XML CDATA section.</span></span>  
  
 `]]>`  
 <span data-ttu-id="75ab6-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="75ab6-110">Required.</span></span> <span data-ttu-id="75ab6-111">Обозначает конец раздела.</span><span class="sxs-lookup"><span data-stu-id="75ab6-111">Denotes the end of the section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="75ab6-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="75ab6-112">Return Value</span></span>  
 <span data-ttu-id="75ab6-113"><xref:System.Xml.Linq.XCData>Объект.</xref:System.Xml.Linq.XCData></span><span class="sxs-lookup"><span data-stu-id="75ab6-113">An <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75ab6-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="75ab6-114">Remarks</span></span>  
 <span data-ttu-id="75ab6-115">Разделы XML CDATA содержит необработанный текст, который должен быть включено, но не проанализировать XML, который его содержит.</span><span class="sxs-lookup"><span data-stu-id="75ab6-115">XML CDATA sections contain raw text that should be included, but not parsed, with the XML that contains it.</span></span> <span data-ttu-id="75ab6-116">Раздел XML CDATA может содержать любой текст.</span><span class="sxs-lookup"><span data-stu-id="75ab6-116">A XML CDATA section can contain any text.</span></span> <span data-ttu-id="75ab6-117">Это включает в себя зарезервированные символы XML.</span><span class="sxs-lookup"><span data-stu-id="75ab6-117">This includes reserved XML characters.</span></span> <span data-ttu-id="75ab6-118">Раздел XML CDATA заканчивается последовательностью «]] настроек».</span><span class="sxs-lookup"><span data-stu-id="75ab6-118">The XML CDATA section ends with the sequence "]]>".</span></span> <span data-ttu-id="75ab6-119">Это подразумевает следующее:</span><span class="sxs-lookup"><span data-stu-id="75ab6-119">This implies the following points:</span></span>  
  
-   <span data-ttu-id="75ab6-120">Нельзя использовать внедренные выражения в литеральном представлении XML CDATA, поскольку разделители внедренного выражения являются допустимым содержимым XML CDATA.</span><span class="sxs-lookup"><span data-stu-id="75ab6-120">You cannot use an embedded expression in an XML CDATA literal because the embedded expression delimiters are valid XML CDATA content.</span></span>  
  
-   <span data-ttu-id="75ab6-121">Разделы XML CDATA не может быть вложенными, поскольку `content` не может содержать значение «]] настроек».</span><span class="sxs-lookup"><span data-stu-id="75ab6-121">XML CDATA sections cannot be nested, because `content` cannot contain the value "]]>".</span></span>  
  
 <span data-ttu-id="75ab6-122">Можно присвоить Литеральное представление CDATA XML переменной или включить ее в литерал XML-элемента.</span><span class="sxs-lookup"><span data-stu-id="75ab6-122">You can assign an XML CDATA literal to a variable, or include it in an XML element literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="75ab6-123">XML-литерал может занимать несколько строк, но не использует символы продолжения строки.</span><span class="sxs-lookup"><span data-stu-id="75ab6-123">An XML literal can span multiple lines but does not use line continuation characters.</span></span> <span data-ttu-id="75ab6-124">Это позволяет скопировать содержимое из XML-документа и вставьте его непосредственно в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] программы.</span><span class="sxs-lookup"><span data-stu-id="75ab6-124">This enables you to copy content from an XML document and paste it directly into a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] program.</span></span>  
  
 <span data-ttu-id="75ab6-125">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Компилятор преобразует XML-раздела CDATA литерала для вызова <xref:System.Xml.Linq.XCData.%23ctor%2A>конструктор.</xref:System.Xml.Linq.XCData.%23ctor%2A></span><span class="sxs-lookup"><span data-stu-id="75ab6-125">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler converts the XML CDATA literal to a call to the <xref:System.Xml.Linq.XCData.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75ab6-126">Пример</span><span class="sxs-lookup"><span data-stu-id="75ab6-126">Example</span></span>  
 <span data-ttu-id="75ab6-127">В следующем примере создается раздел CDATA, содержащий текст» может содержать литеральное \<XML настроек тегов».</span><span class="sxs-lookup"><span data-stu-id="75ab6-127">The following example creates a CDATA section that contains the text "Can contain literal \<XML> tags".</span></span>  
  
 <span data-ttu-id="75ab6-128">[!code-vb[VbXMLSamples&#23;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-cdata-literal_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="75ab6-128">[!code-vb[VbXMLSamples#23](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-cdata-literal_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75ab6-129">См. также</span><span class="sxs-lookup"><span data-stu-id="75ab6-129">See Also</span></span>  
 <span data-ttu-id="75ab6-130"><xref:System.Xml.Linq.XCData></xref:System.Xml.Linq.XCData></span><span class="sxs-lookup"><span data-stu-id="75ab6-130"><xref:System.Xml.Linq.XCData></span></span>   
<span data-ttu-id="75ab6-131"> [Литеральное представление XML элемента](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span><span class="sxs-lookup"><span data-stu-id="75ab6-131"> [XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span></span>  
<span data-ttu-id="75ab6-132"> [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md) </span><span class="sxs-lookup"><span data-stu-id="75ab6-132"> [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md) </span></span>  
<span data-ttu-id="75ab6-133"> [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)</span><span class="sxs-lookup"><span data-stu-id="75ab6-133"> [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)</span></span>
