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
# <a name="how-to-parse-a-string-visual-basic"></a>Как: синтаксический анализ строки (Visual Basic)
В этом разделе показано, как создать XML-дерева в C#.  
  
## <a name="example"></a>Пример  
 Можно выполнить синтаксический анализ строки в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] с помощью `XElement.Parse` метод. Однако более эффективно используются XML-литералы, как показано в следующем коде, поскольку применение XML-литералов не приводит к снижению производительности, в отличие от синтаксического анализа кода XML, полученного из строки.  
  
 С помощью XML-литералов можно копировать и вставлять код XML в программу [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].  
  
> [!NOTE]
>  Синтаксический анализ текста или загрузка XML-документа из текстового файла менее эффективны, чем функциональное построение. При инициализации XML-дерева из кода для осуществления функционального построения требуется меньше процессорного времени, чем для синтаксического анализа текста.  
  
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
  
## <a name="see-also"></a>См. также  
 [Синтаксический анализ XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
