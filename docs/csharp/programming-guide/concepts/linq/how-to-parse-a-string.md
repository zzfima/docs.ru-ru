---
title: Практическое руководство. Анализ строки (C#)
ms.date: 07/20/2015
ms.assetid: 81e5686c-9658-42d8-a7e3-b11be0a2c98b
ms.openlocfilehash: 8039e22a3ba1e37818064fafca7c404b57f39021
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66485285"
---
# <a name="how-to-parse-a-string-c"></a><span data-ttu-id="18ff5-102">Практическое руководство. Анализ строки (C#)</span><span class="sxs-lookup"><span data-stu-id="18ff5-102">How to: Parse a String (C#)</span></span>
<span data-ttu-id="18ff5-103">В этом разделе демонстрируется анализ строки для создания XML-дерева в C#.</span><span class="sxs-lookup"><span data-stu-id="18ff5-103">This topic shows how to parse a string to create an XML tree in C#.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18ff5-104">Пример</span><span class="sxs-lookup"><span data-stu-id="18ff5-104">Example</span></span>  
 <span data-ttu-id="18ff5-105">В следующем коде C# показано, как выполнять синтаксический анализ строки.</span><span class="sxs-lookup"><span data-stu-id="18ff5-105">The following C# code shows how to parse a string.</span></span>  
  
```csharp  
XElement contacts = XElement.Parse(  
    @"<Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone Type=""home"">206-555-0144</Phone>  
            <Phone type=""work"">425-555-0145</Phone>  
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
            <Phone Type=""mobile"">206-555-0163</Phone>  
            <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
            </Address>  
            <NetWorth>11</NetWorth>  
        </Contact>  
    </Contacts>");  
Console.WriteLine(contacts);  
```  
