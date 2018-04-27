---
title: Литеральное представление XML-раздела CDATA (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralCdata
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e8dfc091409e060e20970b0b6d6bc19b4fc2aeea
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="xml-cdata-literal-visual-basic"></a><span data-ttu-id="d687c-102">Литеральное представление XML-раздела CDATA (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d687c-102">XML CDATA Literal (Visual Basic)</span></span>
<span data-ttu-id="d687c-103">Объект литерал, представляющий <xref:System.Xml.Linq.XCData> объекта.</span><span class="sxs-lookup"><span data-stu-id="d687c-103">A literal representing an <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d687c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d687c-104">Syntax</span></span>  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a><span data-ttu-id="d687c-105">Части</span><span class="sxs-lookup"><span data-stu-id="d687c-105">Parts</span></span>  
 `<![CDATA[`  
 <span data-ttu-id="d687c-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="d687c-106">Required.</span></span> <span data-ttu-id="d687c-107">Обозначает начало раздела XML CDATA.</span><span class="sxs-lookup"><span data-stu-id="d687c-107">Denotes the start of the XML CDATA section.</span></span>  
  
 `content`  
 <span data-ttu-id="d687c-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="d687c-108">Required.</span></span> <span data-ttu-id="d687c-109">Текст содержимого для отображения в разделе XML CDATA.</span><span class="sxs-lookup"><span data-stu-id="d687c-109">Text content to appear in the XML CDATA section.</span></span>  
  
 `]]>`  
 <span data-ttu-id="d687c-110">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="d687c-110">Required.</span></span> <span data-ttu-id="d687c-111">Обозначает конец раздела.</span><span class="sxs-lookup"><span data-stu-id="d687c-111">Denotes the end of the section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d687c-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d687c-112">Return Value</span></span>  
 <span data-ttu-id="d687c-113">Объект <xref:System.Xml.Linq.XCData>.</span><span class="sxs-lookup"><span data-stu-id="d687c-113">An <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d687c-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="d687c-114">Remarks</span></span>  
 <span data-ttu-id="d687c-115">Разделы XML CDATA содержит необработанный текст, который должны быть включены, но не синтаксического анализа XML, он содержит.</span><span class="sxs-lookup"><span data-stu-id="d687c-115">XML CDATA sections contain raw text that should be included, but not parsed, with the XML that contains it.</span></span> <span data-ttu-id="d687c-116">Раздел XML CDATA может содержать любой текст.</span><span class="sxs-lookup"><span data-stu-id="d687c-116">A XML CDATA section can contain any text.</span></span> <span data-ttu-id="d687c-117">Это включает в себя зарезервированные символы XML.</span><span class="sxs-lookup"><span data-stu-id="d687c-117">This includes reserved XML characters.</span></span> <span data-ttu-id="d687c-118">Раздел XML CDATA заканчивается последовательностью «]] >».</span><span class="sxs-lookup"><span data-stu-id="d687c-118">The XML CDATA section ends with the sequence "]]>".</span></span> <span data-ttu-id="d687c-119">Это подразумевает следующее:</span><span class="sxs-lookup"><span data-stu-id="d687c-119">This implies the following points:</span></span>  
  
-   <span data-ttu-id="d687c-120">Нельзя использовать внедренное выражение в представлении XML CDATA, поскольку разделители внедренного выражения являются допустимым содержимым XML CDATA.</span><span class="sxs-lookup"><span data-stu-id="d687c-120">You cannot use an embedded expression in an XML CDATA literal because the embedded expression delimiters are valid XML CDATA content.</span></span>  
  
-   <span data-ttu-id="d687c-121">Разделы XML CDATA не может быть вложенными, поскольку `content` не может содержать значение «]] >».</span><span class="sxs-lookup"><span data-stu-id="d687c-121">XML CDATA sections cannot be nested, because `content` cannot contain the value "]]>".</span></span>  
  
 <span data-ttu-id="d687c-122">Можно присвоить переменной литеральное представление CDATA XML или включить ее в литерале XML-элемента.</span><span class="sxs-lookup"><span data-stu-id="d687c-122">You can assign an XML CDATA literal to a variable, or include it in an XML element literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d687c-123">XML-литерал может занимать несколько строк, но не использует символы продолжения строки.</span><span class="sxs-lookup"><span data-stu-id="d687c-123">An XML literal can span multiple lines but does not use line continuation characters.</span></span> <span data-ttu-id="d687c-124">Это позволяет скопировать содержимое из XML-документа и вставьте его непосредственно в программу Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d687c-124">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="d687c-125">Компилятор Visual Basic литерала CDATA XML преобразуется в вызов <xref:System.Xml.Linq.XCData.%23ctor%2A> конструктор.</span><span class="sxs-lookup"><span data-stu-id="d687c-125">The Visual Basic compiler converts the XML CDATA literal to a call to the <xref:System.Xml.Linq.XCData.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d687c-126">Пример</span><span class="sxs-lookup"><span data-stu-id="d687c-126">Example</span></span>  
 <span data-ttu-id="d687c-127">В следующем примере создается раздел CDATA, содержащий текст «может содержать литеральное \<XML > теги».</span><span class="sxs-lookup"><span data-stu-id="d687c-127">The following example creates a CDATA section that contains the text "Can contain literal \<XML> tags".</span></span>  
  
 [!code-vb[VbXMLSamples#23](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-cdata-literal_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d687c-128">См. также</span><span class="sxs-lookup"><span data-stu-id="d687c-128">See Also</span></span>  
 <xref:System.Xml.Linq.XCData>  
 [<span data-ttu-id="d687c-129">XML-литерал элемента</span><span class="sxs-lookup"><span data-stu-id="d687c-129">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [<span data-ttu-id="d687c-130">XML-литералы</span><span class="sxs-lookup"><span data-stu-id="d687c-130">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="d687c-131">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d687c-131">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
