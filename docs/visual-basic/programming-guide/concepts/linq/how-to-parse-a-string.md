---
title: "Как: синтаксический анализ строки (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 896e1b4b-f9bd-4975-8bc1-55b6badce1ac
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 10b80c72cae70437ff812c4b67b2532d708f1e69
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-parse-a-string-visual-basic"></a><span data-ttu-id="9fcc8-102">Как: синтаксический анализ строки (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9fcc8-102">How to: Parse a String (Visual Basic)</span></span>
<span data-ttu-id="9fcc8-103">В этом разделе показано, как создать XML-дерева в C#.</span><span class="sxs-lookup"><span data-stu-id="9fcc8-103">This topic shows how to create an XML tree in C#.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9fcc8-104">Пример</span><span class="sxs-lookup"><span data-stu-id="9fcc8-104">Example</span></span>  
 <span data-ttu-id="9fcc8-105">Можно выполнить синтаксический анализ строки в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] с помощью `XElement.Parse` метод.</span><span class="sxs-lookup"><span data-stu-id="9fcc8-105">You can parse a string in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] by using the `XElement.Parse` method.</span></span> <span data-ttu-id="9fcc8-106">Однако более эффективно используются XML-литералы, как показано в следующем коде, поскольку применение XML-литералов не приводит к снижению производительности, в отличие от синтаксического анализа кода XML, полученного из строки.</span><span class="sxs-lookup"><span data-stu-id="9fcc8-106">However, it is more efficient to use XML literals, as shown in following code, because XML literals do not suffer from the same performance penalties as parsing XML from a string.</span></span>  
  
 <span data-ttu-id="9fcc8-107">С помощью XML-литералов можно копировать и вставлять код XML в программу [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9fcc8-107">By using XML literals, you can just copy and paste your XML into your [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] program.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9fcc8-108">Синтаксический анализ текста или загрузка XML-документа из текстового файла менее эффективны, чем функциональное построение.</span><span class="sxs-lookup"><span data-stu-id="9fcc8-108">Parsing text or loading an XML document from a text file is less efficient than functional construction.</span></span> <span data-ttu-id="9fcc8-109">При инициализации XML-дерева из кода для осуществления функционального построения требуется меньше процессорного времени, чем для синтаксического анализа текста.</span><span class="sxs-lookup"><span data-stu-id="9fcc8-109">If you are initializing an XML tree from code, it takes less processor time to use functional construction than to parse text.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9fcc8-110">См. также</span><span class="sxs-lookup"><span data-stu-id="9fcc8-110">See Also</span></span>  
 [<span data-ttu-id="9fcc8-111">Синтаксический анализ XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9fcc8-111">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
