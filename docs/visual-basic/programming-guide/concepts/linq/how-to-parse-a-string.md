---
title: "Практическое руководство: синтаксический анализ строки (Visual Basic) | Документы Microsoft"
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
ms.assetid: 896e1b4b-f9bd-4975-8bc1-55b6badce1ac
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d06a0ca84650a860a7528cefafaa1c3158e5949a
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-parse-a-string-visual-basic"></a><span data-ttu-id="aab79-102">Практическое руководство: синтаксический анализ строки (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aab79-102">How to: Parse a String (Visual Basic)</span></span>
<span data-ttu-id="aab79-103">В этом разделе показано, как создать XML-дерева в C#.</span><span class="sxs-lookup"><span data-stu-id="aab79-103">This topic shows how to create an XML tree in C#.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aab79-104">Пример</span><span class="sxs-lookup"><span data-stu-id="aab79-104">Example</span></span>  
 <span data-ttu-id="aab79-105">Можно выполнить синтаксический анализ строки в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] с помощью `XElement.Parse` метод.</span><span class="sxs-lookup"><span data-stu-id="aab79-105">You can parse a string in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] by using the `XElement.Parse` method.</span></span> <span data-ttu-id="aab79-106">Однако более эффективно используются XML-литералы, как показано в следующем коде, поскольку применение XML-литералов не приводит к снижению производительности, в отличие от синтаксического анализа кода XML, полученного из строки.</span><span class="sxs-lookup"><span data-stu-id="aab79-106">However, it is more efficient to use XML literals, as shown in following code, because XML literals do not suffer from the same performance penalties as parsing XML from a string.</span></span>  
  
 <span data-ttu-id="aab79-107">С помощью XML-литералов можно копировать и вставлять код XML в программу [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="aab79-107">By using XML literals, you can just copy and paste your XML into your [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] program.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aab79-108">Синтаксический анализ текста или загрузка XML-документа из текстового файла менее эффективны, чем функциональное построение.</span><span class="sxs-lookup"><span data-stu-id="aab79-108">Parsing text or loading an XML document from a text file is less efficient than functional construction.</span></span> <span data-ttu-id="aab79-109">При инициализации XML-дерева из кода для осуществления функционального построения требуется меньше процессорного времени, чем для синтаксического анализа текста.</span><span class="sxs-lookup"><span data-stu-id="aab79-109">If you are initializing an XML tree from code, it takes less processor time to use functional construction than to parse text.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="aab79-110">См. также</span><span class="sxs-lookup"><span data-stu-id="aab79-110">See Also</span></span>  
 [<span data-ttu-id="aab79-111">Синтаксический анализ XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aab79-111">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
