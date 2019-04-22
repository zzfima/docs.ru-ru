---
title: Практическое руководство. Внедрить выражения в XML-литералах (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
ms.openlocfilehash: 31e79a8787978ffab2e35cd2827b80a8f1ed843e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58841593"
---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a><span data-ttu-id="cdf45-102">Практическое руководство. Внедрить выражения в XML-литералах (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cdf45-102">How to: Embed Expressions in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="cdf45-103">XML-литералов можно объединить с внедренными выражениями для создания документа XML, фрагмент или элемент, содержащий содержимое, созданное во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="cdf45-103">You can combine XML literals with embedded expressions to create an XML document, fragment, or element that contains content created at run time.</span></span> <span data-ttu-id="cdf45-104">Следующие примеры демонстрируют, как использовать внедренные выражения для заполнения содержимого элемента, атрибутов и имена элементов во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="cdf45-104">The following examples demonstrate how to use embedded expressions to populate element content, attributes, and element names at run time.</span></span>  
  
 <span data-ttu-id="cdf45-105">Для внедренного выражения используется синтаксис `<%=` `exp` `%>`, который является такой же синтаксис, [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] использует.</span><span class="sxs-lookup"><span data-stu-id="cdf45-105">The syntax for an embedded expression is `<%=` `exp` `%>`, which is the same syntax that [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] uses.</span></span> <span data-ttu-id="cdf45-106">Дополнительные сведения см. в разделе [встроенные выражения в XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="cdf45-106">For more information, see [Embedded Expressions in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>  
  
 <span data-ttu-id="cdf45-107">Можно также использовать [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] API-интерфейсы для создания [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объектов.</span><span class="sxs-lookup"><span data-stu-id="cdf45-107">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="cdf45-108">Дополнительные сведения см. в разделе <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="cdf45-108">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="cdf45-109">Процедуры</span><span class="sxs-lookup"><span data-stu-id="cdf45-109">Procedures</span></span>  
  
#### <a name="to-insert-text-as-element-content"></a><span data-ttu-id="cdf45-110">Для вставки текста в качестве содержимого элемента</span><span class="sxs-lookup"><span data-stu-id="cdf45-110">To insert text as element content</span></span>  
  
-   <span data-ttu-id="cdf45-111">В следующем примере показано, как вставить текст, содержащийся в `contactName` переменной между открывающей и закрывающей имен элементов.</span><span class="sxs-lookup"><span data-stu-id="cdf45-111">The following example shows how to insert the text that is contained in the `contactName` variable between the opening and closing name elements.</span></span>  
  
     [!code-vb[VbXMLSamples#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#39)]  
  
     <span data-ttu-id="cdf45-112">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="cdf45-112">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a><span data-ttu-id="cdf45-113">Для вставки текста в качестве значения атрибута</span><span class="sxs-lookup"><span data-stu-id="cdf45-113">To insert text as an attribute value</span></span>  
  
-   <span data-ttu-id="cdf45-114">В следующем примере показано, как вставить текст, содержащийся в `phoneType` переменной в качестве значения `type` атрибута.</span><span class="sxs-lookup"><span data-stu-id="cdf45-114">The following example shows how to insert the text that is contained in the `phoneType` variable as the value of the `type` attribute.</span></span>  
  
     [!code-vb[VbXMLSamples#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#40)]  
  
     <span data-ttu-id="cdf45-115">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="cdf45-115">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a><span data-ttu-id="cdf45-116">Для вставки текста для имени элемента</span><span class="sxs-lookup"><span data-stu-id="cdf45-116">To insert text for an element name</span></span>  
  
-   <span data-ttu-id="cdf45-117">В следующем примере показано, как вставить текст, содержащийся в `elementName` переменной в качестве имени элемента.</span><span class="sxs-lookup"><span data-stu-id="cdf45-117">The following example shows how to insert the text that is contained in the `elementName` variable as the name of an element.</span></span>  
  
     <span data-ttu-id="cdf45-118">При создании элементов при использовании этого метода, необходимо закрыть их с помощью \</ > тег.</span><span class="sxs-lookup"><span data-stu-id="cdf45-118">When creating elements by using this technique, you must close them with the \</> tag.</span></span>  
  
     [!code-vb[VbXMLSamples#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#41)]  
  
     <span data-ttu-id="cdf45-119">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="cdf45-119">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="cdf45-120">См. также</span><span class="sxs-lookup"><span data-stu-id="cdf45-120">See also</span></span>

- [<span data-ttu-id="cdf45-121">Практическое руководство. Создание XML-литералов</span><span class="sxs-lookup"><span data-stu-id="cdf45-121">How to: Create XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)
- [<span data-ttu-id="cdf45-122">Встроенные выражения в XML</span><span class="sxs-lookup"><span data-stu-id="cdf45-122">Embedded Expressions in XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [<span data-ttu-id="cdf45-123">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cdf45-123">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="cdf45-124">XML</span><span class="sxs-lookup"><span data-stu-id="cdf45-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
