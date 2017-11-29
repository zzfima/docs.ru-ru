---
title: "Практическое руководство. Внедрение выражений в XML-литералы (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bef4662d69ca7ceddeb2641cbe265d93712c5d16
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a><span data-ttu-id="df582-102">Практическое руководство. Внедрение выражений в XML-литералы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="df582-102">How to: Embed Expressions in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="df582-103">XML-литералов можно объединить с внедренными выражениями для создания XML документ, фрагмент или элемент, который содержит содержимое, созданное во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="df582-103">You can combine XML literals with embedded expressions to create an XML document, fragment, or element that contains content created at run time.</span></span> <span data-ttu-id="df582-104">Следующие примеры демонстрируют, как использовать внедренные выражения для заполнения содержимого элемента, атрибутов и имен элементов во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="df582-104">The following examples demonstrate how to use embedded expressions to populate element content, attributes, and element names at run time.</span></span>  
  
 <span data-ttu-id="df582-105">Для внедренного выражения используется синтаксис `<%=` `exp` `%>`, который имеет тот же синтаксис, [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] использует.</span><span class="sxs-lookup"><span data-stu-id="df582-105">The syntax for an embedded expression is `<%=` `exp` `%>`, which is the same syntax that [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] uses.</span></span> <span data-ttu-id="df582-106">Дополнительные сведения см. в разделе [встроенные выражения в XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="df582-106">For more information, see [Embedded Expressions in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>  
  
 <span data-ttu-id="df582-107">Можно также использовать [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] API для создания [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объектов.</span><span class="sxs-lookup"><span data-stu-id="df582-107">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="df582-108">Для получения дополнительной информации см. <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="df582-108">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="df582-109">Процедуры</span><span class="sxs-lookup"><span data-stu-id="df582-109">Procedures</span></span>  
  
#### <a name="to-insert-text-as-element-content"></a><span data-ttu-id="df582-110">Вставка текста в качестве содержимого элемента</span><span class="sxs-lookup"><span data-stu-id="df582-110">To insert text as element content</span></span>  
  
-   <span data-ttu-id="df582-111">В следующем примере показано, как вставить текст, содержащийся в `contactName` между открывающим и закрывающим элементами имя переменной.</span><span class="sxs-lookup"><span data-stu-id="df582-111">The following example shows how to insert the text that is contained in the `contactName` variable between the opening and closing name elements.</span></span>  
  
     [!code-vb[VbXMLSamples#39](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_1.vb)]  
  
     <span data-ttu-id="df582-112">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="df582-112">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a><span data-ttu-id="df582-113">Вставка текста в качестве значения атрибута</span><span class="sxs-lookup"><span data-stu-id="df582-113">To insert text as an attribute value</span></span>  
  
-   <span data-ttu-id="df582-114">В следующем примере показано, как вставить текст, содержащийся в `phoneType` в качестве значения переменной `type` атрибута.</span><span class="sxs-lookup"><span data-stu-id="df582-114">The following example shows how to insert the text that is contained in the `phoneType` variable as the value of the `type` attribute.</span></span>  
  
     [!code-vb[VbXMLSamples#40](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_2.vb)]  
  
     <span data-ttu-id="df582-115">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="df582-115">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a><span data-ttu-id="df582-116">Вставка текста для имени элемента</span><span class="sxs-lookup"><span data-stu-id="df582-116">To insert text for an element name</span></span>  
  
-   <span data-ttu-id="df582-117">В следующем примере показано, как вставить текст, содержащийся в `elementName` переменной в качестве имени элемента.</span><span class="sxs-lookup"><span data-stu-id="df582-117">The following example shows how to insert the text that is contained in the `elementName` variable as the name of an element.</span></span>  
  
     <span data-ttu-id="df582-118">При создании элементов с помощью данного метода, необходимо закрыть их с \</ > тег.</span><span class="sxs-lookup"><span data-stu-id="df582-118">When creating elements by using this technique, you must close them with the \</> tag.</span></span>  
  
     [!code-vb[VbXMLSamples#41](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_3.vb)]  
  
     <span data-ttu-id="df582-119">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="df582-119">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="df582-120">См. также</span><span class="sxs-lookup"><span data-stu-id="df582-120">See Also</span></span>  
 [<span data-ttu-id="df582-121">Практическое руководство. Создание XML-литералов</span><span class="sxs-lookup"><span data-stu-id="df582-121">How to: Create XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)  
 [<span data-ttu-id="df582-122">Встроенные выражения в XML</span><span class="sxs-lookup"><span data-stu-id="df582-122">Embedded Expressions in XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)  
 [<span data-ttu-id="df582-123">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="df582-123">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="df582-124">XML</span><span class="sxs-lookup"><span data-stu-id="df582-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
