---
title: Практическое руководство. Синтаксический анализ строки (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 896e1b4b-f9bd-4975-8bc1-55b6badce1ac
ms.openlocfilehash: 815e94b3b41c2c0cc1d18d598307ab292919bea4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58827306"
---
# <a name="how-to-parse-a-string-visual-basic"></a><span data-ttu-id="d0623-102">Практическое руководство. Синтаксический анализ строки (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d0623-102">How to: Parse a String (Visual Basic)</span></span>
<span data-ttu-id="d0623-103">В этом разделе показано, как создать XML-дерева в C#.</span><span class="sxs-lookup"><span data-stu-id="d0623-103">This topic shows how to create an XML tree in C#.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0623-104">Пример</span><span class="sxs-lookup"><span data-stu-id="d0623-104">Example</span></span>  
 <span data-ttu-id="d0623-105">Синтаксический анализ строки в Visual Basic с помощью `XElement.Parse` метод.</span><span class="sxs-lookup"><span data-stu-id="d0623-105">You can parse a string in Visual Basic by using the `XElement.Parse` method.</span></span> <span data-ttu-id="d0623-106">Однако более эффективно используются XML-литералы, как показано в следующем коде, поскольку применение XML-литералов не приводит к снижению производительности, в отличие от синтаксического анализа кода XML, полученного из строки.</span><span class="sxs-lookup"><span data-stu-id="d0623-106">However, it is more efficient to use XML literals, as shown in following code, because XML literals do not suffer from the same performance penalties as parsing XML from a string.</span></span>  
  
 <span data-ttu-id="d0623-107">С помощью литералов XML, можно просто скопируйте и вставьте XML в программу Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d0623-107">By using XML literals, you can just copy and paste your XML into your Visual Basic program.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d0623-108">Синтаксический анализ текста или загрузка XML-документа из текстового файла менее эффективны, чем функциональное построение.</span><span class="sxs-lookup"><span data-stu-id="d0623-108">Parsing text or loading an XML document from a text file is less efficient than functional construction.</span></span> <span data-ttu-id="d0623-109">При инициализации XML-дерева из кода для осуществления функционального построения требуется меньше процессорного времени, чем для синтаксического анализа текста.</span><span class="sxs-lookup"><span data-stu-id="d0623-109">If you are initializing an XML tree from code, it takes less processor time to use functional construction than to parse text.</span></span>  
  
```vb  
Dim contacts as XElement = _  
    <Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone Type="home">206-555-0144</Phone>  
            <Phone Type="work">425-555-0145</Phone>  
            <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
            </Address>  
            <NetWorth>10</NetWorth>  
        </Contact>  
        <Contact>  
            <Name>Gretchen Rivas</Name>  
            <Phone Type="mobile">206-555-0163</Phone>  
            <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
            </Address>  
            <NetWorth>11</NetWorth>  
        </Contact>  
    </Contacts>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d0623-110">См. также</span><span class="sxs-lookup"><span data-stu-id="d0623-110">See also</span></span>

- [<span data-ttu-id="d0623-111">Синтаксический анализ XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d0623-111">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
