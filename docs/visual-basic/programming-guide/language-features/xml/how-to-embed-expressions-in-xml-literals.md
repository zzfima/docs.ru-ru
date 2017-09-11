---
title: "Практическое руководство: внедрение выражений в XML-литералах (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
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
ms.openlocfilehash: e4f086b06575cb8300bd65d450cda6b9893bb692
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a><span data-ttu-id="653cf-102">Практическое руководство. Внедрение выражений в XML-литералы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="653cf-102">How to: Embed Expressions in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="653cf-103">Можно объединять XML-литералы с внедренными выражениями для создания документа XML, фрагмент или элемент, содержащий содержимое, созданное во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="653cf-103">You can combine XML literals with embedded expressions to create an XML document, fragment, or element that contains content created at run time.</span></span> <span data-ttu-id="653cf-104">Следующие примеры демонстрируют, как использовать внедренные выражения для заполнения содержимого элемента, атрибутов и имен элементов во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="653cf-104">The following examples demonstrate how to use embedded expressions to populate element content, attributes, and element names at run time.</span></span>  
  
 <span data-ttu-id="653cf-105">Синтаксис для встроенных выражений `<%=` `exp` `%>`, который является такой же синтаксис, [!INCLUDE[vstecasp](../../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)] использует.</span><span class="sxs-lookup"><span data-stu-id="653cf-105">The syntax for an embedded expression is `<%=` `exp` `%>`, which is the same syntax that [!INCLUDE[vstecasp](../../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)] uses.</span></span> <span data-ttu-id="653cf-106">Дополнительные сведения см. в разделе [встроенные выражения в XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="653cf-106">For more information, see [Embedded Expressions in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>  
  
 <span data-ttu-id="653cf-107">Можно также использовать [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] API для создания [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] объектов.</span><span class="sxs-lookup"><span data-stu-id="653cf-107">You can also use the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] APIs to create [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] objects.</span></span> <span data-ttu-id="653cf-108">Дополнительные сведения см. в разделе <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="653cf-108">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="653cf-109">Процедуры</span><span class="sxs-lookup"><span data-stu-id="653cf-109">Procedures</span></span>  
  
#### <a name="to-insert-text-as-element-content"></a><span data-ttu-id="653cf-110">Для вставки текста в качестве содержимого элемента</span><span class="sxs-lookup"><span data-stu-id="653cf-110">To insert text as element content</span></span>  
  
-   <span data-ttu-id="653cf-111">В следующем примере показано, как вставить текст, содержащийся в `contactName` между открывающими и закрывающими элементами имени переменной.</span><span class="sxs-lookup"><span data-stu-id="653cf-111">The following example shows how to insert the text that is contained in the `contactName` variable between the opening and closing name elements.</span></span>  
  
     <span data-ttu-id="653cf-112">[!code-vb[VbXMLSamples&#39;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="653cf-112">[!code-vb[VbXMLSamples#39](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_1.vb)]</span></span>  
  
     <span data-ttu-id="653cf-113">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="653cf-113">This example produces the following output:</span></span>  
  
    ```  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a><span data-ttu-id="653cf-114">Для вставки текста в качестве значения атрибута</span><span class="sxs-lookup"><span data-stu-id="653cf-114">To insert text as an attribute value</span></span>  
  
-   <span data-ttu-id="653cf-115">В следующем примере показано, как вставить текст, содержащийся в `phoneType` в качестве значения переменной `type` атрибута.</span><span class="sxs-lookup"><span data-stu-id="653cf-115">The following example shows how to insert the text that is contained in the `phoneType` variable as the value of the `type` attribute.</span></span>  
  
     <span data-ttu-id="653cf-116">[!code-vb[VbXMLSamples&#40;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="653cf-116">[!code-vb[VbXMLSamples#40](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_2.vb)]</span></span>  
  
     <span data-ttu-id="653cf-117">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="653cf-117">This example produces the following output:</span></span>  
  
    ```  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a><span data-ttu-id="653cf-118">Вставка текста для имени элемента</span><span class="sxs-lookup"><span data-stu-id="653cf-118">To insert text for an element name</span></span>  
  
-   <span data-ttu-id="653cf-119">В следующем примере показано, как вставить текст, содержащийся в `elementName` переменной в качестве имени элемента.</span><span class="sxs-lookup"><span data-stu-id="653cf-119">The following example shows how to insert the text that is contained in the `elementName` variable as the name of an element.</span></span>  
  
     <span data-ttu-id="653cf-120">При создании элементов с помощью данного метода, необходимо закрыть их с помощью \<и настроек тег.</span><span class="sxs-lookup"><span data-stu-id="653cf-120">When creating elements by using this technique, you must close them with the \</> tag.</span></span>  
  
     <span data-ttu-id="653cf-121">[!code-vb[VbXMLSamples&#41;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="653cf-121">[!code-vb[VbXMLSamples#41](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_3.vb)]</span></span>  
  
     <span data-ttu-id="653cf-122">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="653cf-122">This example produces the following output:</span></span>  
  
    ```  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="653cf-123">См. также</span><span class="sxs-lookup"><span data-stu-id="653cf-123">See Also</span></span>  
 <span data-ttu-id="653cf-124">[Практическое руководство: Создание XML-литералов](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md) </span><span class="sxs-lookup"><span data-stu-id="653cf-124">[How to: Create XML Literals](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md) </span></span>  
<span data-ttu-id="653cf-125"> [Встроенные выражения в XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md) </span><span class="sxs-lookup"><span data-stu-id="653cf-125"> [Embedded Expressions in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md) </span></span>  
<span data-ttu-id="653cf-126"> [Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="653cf-126"> [Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="653cf-127"> [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)</span><span class="sxs-lookup"><span data-stu-id="653cf-127"> [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)</span></span>
