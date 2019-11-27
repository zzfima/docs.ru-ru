---
title: Практическое руководство. Внедрение выражений в XML-литералы
ms.date: 07/20/2015
helpviewer_keywords:
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
ms.openlocfilehash: 2e8dd10b334b0271e3c9de11ed155c9d5d7aae48
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74332931"
---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a><span data-ttu-id="9d338-102">Практическое руководство. Внедрение выражений в XML-литералы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9d338-102">How to: Embed Expressions in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="9d338-103">Литералы XML можно объединять с внедренными выражениями для создания XML-документа, фрагмента или элемента, содержащего содержимое, созданное во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="9d338-103">You can combine XML literals with embedded expressions to create an XML document, fragment, or element that contains content created at run time.</span></span> <span data-ttu-id="9d338-104">В следующих примерах показано, как использовать внедренные выражения для заполнения содержимого, атрибутов и имен элементов во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="9d338-104">The following examples demonstrate how to use embedded expressions to populate element content, attributes, and element names at run time.</span></span>  
  
 <span data-ttu-id="9d338-105">Синтаксис для внедренного выражения `<%=` `exp` `%>`— тот же синтаксис, который ASP.NET использует.</span><span class="sxs-lookup"><span data-stu-id="9d338-105">The syntax for an embedded expression is `<%=` `exp` `%>`, which is the same syntax that ASP.NET uses.</span></span> <span data-ttu-id="9d338-106">Дополнительные сведения см. [в разделе внедренные выражения в XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="9d338-106">For more information, see [Embedded Expressions in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>  
  
 <span data-ttu-id="9d338-107">Для создания [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объектов также можно использовать [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] интерфейсы API.</span><span class="sxs-lookup"><span data-stu-id="9d338-107">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="9d338-108">Дополнительные сведения см. в разделе <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="9d338-108">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="9d338-109">Процедуры</span><span class="sxs-lookup"><span data-stu-id="9d338-109">Procedures</span></span>  
  
#### <a name="to-insert-text-as-element-content"></a><span data-ttu-id="9d338-110">Вставка текста в качестве содержимого элемента</span><span class="sxs-lookup"><span data-stu-id="9d338-110">To insert text as element content</span></span>  
  
- <span data-ttu-id="9d338-111">В следующем примере показано, как вставить текст, содержащийся в переменной `contactName`, между открывающим и закрывающим элементами Name.</span><span class="sxs-lookup"><span data-stu-id="9d338-111">The following example shows how to insert the text that is contained in the `contactName` variable between the opening and closing name elements.</span></span>  
  
     [!code-vb[VbXMLSamples#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#39)]  
  
     <span data-ttu-id="9d338-112">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="9d338-112">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a><span data-ttu-id="9d338-113">Вставка текста в качестве значения атрибута</span><span class="sxs-lookup"><span data-stu-id="9d338-113">To insert text as an attribute value</span></span>  
  
- <span data-ttu-id="9d338-114">В следующем примере показано, как вставить текст, содержащийся в переменной `phoneType`, в качестве значения атрибута `type`.</span><span class="sxs-lookup"><span data-stu-id="9d338-114">The following example shows how to insert the text that is contained in the `phoneType` variable as the value of the `type` attribute.</span></span>  
  
     [!code-vb[VbXMLSamples#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#40)]  
  
     <span data-ttu-id="9d338-115">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="9d338-115">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a><span data-ttu-id="9d338-116">Вставка текста для имени элемента</span><span class="sxs-lookup"><span data-stu-id="9d338-116">To insert text for an element name</span></span>  
  
- <span data-ttu-id="9d338-117">В следующем примере показано, как вставить текст, содержащийся в переменной `elementName`, в качестве имени элемента.</span><span class="sxs-lookup"><span data-stu-id="9d338-117">The following example shows how to insert the text that is contained in the `elementName` variable as the name of an element.</span></span>  
  
     <span data-ttu-id="9d338-118">При создании элементов с помощью этого метода их необходимо закрыть с помощью тега \</>.</span><span class="sxs-lookup"><span data-stu-id="9d338-118">When creating elements by using this technique, you must close them with the \</> tag.</span></span>  
  
     [!code-vb[VbXMLSamples#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#41)]  
  
     <span data-ttu-id="9d338-119">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="9d338-119">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9d338-120">См. также</span><span class="sxs-lookup"><span data-stu-id="9d338-120">See also</span></span>

- [<span data-ttu-id="9d338-121">Практическое руководство. Создание XML-литералов</span><span class="sxs-lookup"><span data-stu-id="9d338-121">How to: Create XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)
- [<span data-ttu-id="9d338-122">Встроенные выражения в XML</span><span class="sxs-lookup"><span data-stu-id="9d338-122">Embedded Expressions in XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [<span data-ttu-id="9d338-123">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9d338-123">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="9d338-124">XML</span><span class="sxs-lookup"><span data-stu-id="9d338-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
