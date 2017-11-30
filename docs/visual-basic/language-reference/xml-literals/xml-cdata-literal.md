---
title: "Литеральное представление XML-раздела CDATA (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.XmlLiteralCdata
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 906fd2494dd952c08088b9b7e38dba4505780481
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="xml-cdata-literal-visual-basic"></a><span data-ttu-id="6827d-102">Литеральное представление XML-раздела CDATA (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6827d-102">XML CDATA Literal (Visual Basic)</span></span>
<span data-ttu-id="6827d-103">Объект литерал, представляющий <xref:System.Xml.Linq.XCData> объекта.</span><span class="sxs-lookup"><span data-stu-id="6827d-103">A literal representing an <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6827d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6827d-104">Syntax</span></span>  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a><span data-ttu-id="6827d-105">Части</span><span class="sxs-lookup"><span data-stu-id="6827d-105">Parts</span></span>  
 `<![CDATA[`  
 <span data-ttu-id="6827d-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="6827d-106">Required.</span></span> <span data-ttu-id="6827d-107">Обозначает начало раздела XML CDATA.</span><span class="sxs-lookup"><span data-stu-id="6827d-107">Denotes the start of the XML CDATA section.</span></span>  
  
 `content`  
 <span data-ttu-id="6827d-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="6827d-108">Required.</span></span> <span data-ttu-id="6827d-109">Текст содержимого для отображения в разделе XML CDATA.</span><span class="sxs-lookup"><span data-stu-id="6827d-109">Text content to appear in the XML CDATA section.</span></span>  
  
 `]]>`  
 <span data-ttu-id="6827d-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="6827d-110">Required.</span></span> <span data-ttu-id="6827d-111">Обозначает конец раздела.</span><span class="sxs-lookup"><span data-stu-id="6827d-111">Denotes the end of the section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6827d-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6827d-112">Return Value</span></span>  
 <span data-ttu-id="6827d-113">Объект <xref:System.Xml.Linq.XCData>.</span><span class="sxs-lookup"><span data-stu-id="6827d-113">An <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6827d-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="6827d-114">Remarks</span></span>  
 <span data-ttu-id="6827d-115">Разделы XML CDATA содержит необработанный текст, который должны быть включены, но не синтаксического анализа XML, он содержит.</span><span class="sxs-lookup"><span data-stu-id="6827d-115">XML CDATA sections contain raw text that should be included, but not parsed, with the XML that contains it.</span></span> <span data-ttu-id="6827d-116">Раздел XML CDATA может содержать любой текст.</span><span class="sxs-lookup"><span data-stu-id="6827d-116">A XML CDATA section can contain any text.</span></span> <span data-ttu-id="6827d-117">Это включает в себя зарезервированные символы XML.</span><span class="sxs-lookup"><span data-stu-id="6827d-117">This includes reserved XML characters.</span></span> <span data-ttu-id="6827d-118">Раздел XML CDATA заканчивается последовательностью «]] >».</span><span class="sxs-lookup"><span data-stu-id="6827d-118">The XML CDATA section ends with the sequence "]]>".</span></span> <span data-ttu-id="6827d-119">Это подразумевает следующее:</span><span class="sxs-lookup"><span data-stu-id="6827d-119">This implies the following points:</span></span>  
  
-   <span data-ttu-id="6827d-120">Нельзя использовать внедренное выражение в представлении XML CDATA, поскольку разделители внедренного выражения являются допустимым содержимым XML CDATA.</span><span class="sxs-lookup"><span data-stu-id="6827d-120">You cannot use an embedded expression in an XML CDATA literal because the embedded expression delimiters are valid XML CDATA content.</span></span>  
  
-   <span data-ttu-id="6827d-121">Разделы XML CDATA не может быть вложенными, поскольку `content` не может содержать значение «]] >».</span><span class="sxs-lookup"><span data-stu-id="6827d-121">XML CDATA sections cannot be nested, because `content` cannot contain the value "]]>".</span></span>  
  
 <span data-ttu-id="6827d-122">Можно присвоить переменной литеральное представление CDATA XML или включить ее в литерале XML-элемента.</span><span class="sxs-lookup"><span data-stu-id="6827d-122">You can assign an XML CDATA literal to a variable, or include it in an XML element literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6827d-123">XML-литерал может занимать несколько строк, но не использует символы продолжения строки.</span><span class="sxs-lookup"><span data-stu-id="6827d-123">An XML literal can span multiple lines but does not use line continuation characters.</span></span> <span data-ttu-id="6827d-124">Это позволяет скопировать содержимое из XML-документа и вставьте его непосредственно в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] программы.</span><span class="sxs-lookup"><span data-stu-id="6827d-124">This enables you to copy content from an XML document and paste it directly into a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] program.</span></span>  
  
 <span data-ttu-id="6827d-125">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Компилятор преобразует литерала CDATA XML вызов <xref:System.Xml.Linq.XCData.%23ctor%2A> конструктор.</span><span class="sxs-lookup"><span data-stu-id="6827d-125">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler converts the XML CDATA literal to a call to the <xref:System.Xml.Linq.XCData.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6827d-126">Пример</span><span class="sxs-lookup"><span data-stu-id="6827d-126">Example</span></span>  
 <span data-ttu-id="6827d-127">В следующем примере создается раздел CDATA, содержащий текст «может содержать литеральное \<XML > теги».</span><span class="sxs-lookup"><span data-stu-id="6827d-127">The following example creates a CDATA section that contains the text "Can contain literal \<XML> tags".</span></span>  
  
 [!code-vb[VbXMLSamples#23](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-cdata-literal_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="6827d-128">См. также</span><span class="sxs-lookup"><span data-stu-id="6827d-128">See Also</span></span>  
 <xref:System.Xml.Linq.XCData>  
 [<span data-ttu-id="6827d-129">XML-литерал элемента</span><span class="sxs-lookup"><span data-stu-id="6827d-129">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [<span data-ttu-id="6827d-130">XML-литералы</span><span class="sxs-lookup"><span data-stu-id="6827d-130">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="6827d-131">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6827d-131">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
