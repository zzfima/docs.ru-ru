---
title: "Практическое руководство: перехват ошибок (Visual Basic) разбора | Документы Microsoft"
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
ms.assetid: 22e9068e-ea58-447b-816e-cd1852c11787
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
ms.openlocfilehash: 6065bb7656151392e4a5b7ad1078706284ba5616
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-catch-parsing-errors-visual-basic"></a><span data-ttu-id="77c23-102">Практическое руководство: перехват разбора ошибок (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="77c23-102">How to: Catch Parsing Errors (Visual Basic)</span></span>
<span data-ttu-id="77c23-103">В этом разделе показано, как обнаружить код XML, имеющий неправильный формат или не прошедший проверку правильности.</span><span class="sxs-lookup"><span data-stu-id="77c23-103">This topic shows how to detect badly formed or invalid XML.</span></span>  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="77c23-104">реализуется с помощью <xref:System.Xml.XmlReader>.</xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="77c23-104"> is implemented using <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="77c23-105">Если передается код XML, имеющий неправильный формат или [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], базовый <xref:System.Xml.XmlReader>класса будет выдано исключение.</xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="77c23-105">If badly formed or invalid XML is passed to [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], the underlying <xref:System.Xml.XmlReader> class will throw an exception.</span></span> <span data-ttu-id="77c23-106">Различные методы, выполняющие синтаксический анализ XML, таких как <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>, не перехватывайте исключения, можно перехватить исключение в приложении.</xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="77c23-106">The various methods that parse XML, such as <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>, do not catch the exception; the exception can then be caught by your application.</span></span>  
  
 <span data-ttu-id="77c23-107">Обратите внимание, что при использовании XML-литералов невозможно обнаружить ошибки синтаксического анализа.</span><span class="sxs-lookup"><span data-stu-id="77c23-107">Note that you cannot get parse errors if you use XML literals.</span></span> <span data-ttu-id="77c23-108">Ошибки, активизируемые при обнаружении имеющего неправильный формат или не прошедшего проверку правильности кода XML, перехватывает компилятор Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="77c23-108">The Visual Basic compiler will catch errors of badly formed or invalid XML.</span></span>  
  
## <a name="example"></a><span data-ttu-id="77c23-109">Пример</span><span class="sxs-lookup"><span data-stu-id="77c23-109">Example</span></span>  
 <span data-ttu-id="77c23-110">В следующем коде предпринимается попытка выполнить синтаксический анализ кода XML, не прошедшего проверку правильности.</span><span class="sxs-lookup"><span data-stu-id="77c23-110">The following code tries to parse invalid XML:</span></span>  
  
```vb  
Try  
    Dim contacts As XElement = XElement.Parse("<Contacts>" & vbCrLf & _  
        "    <Contact>" & vbCrLf & _  
        "        <Name>Jim Wilson</Name>" & vbCrLf & _  
        "    </Contact>" & vbCrLf & _  
        "</Contcts>")  
  
    Console.WriteLine(contacts)  
Catch e As System.Xml.XmlException  
    Console.WriteLine(e.Message)  
End Try  
```  
  
 <span data-ttu-id="77c23-111">При выполнении этого кода активизируется следующее исключение.</span><span class="sxs-lookup"><span data-stu-id="77c23-111">When you run this code, it throws the following exception:</span></span>  
  
```  
The 'Contacts' start tag on line 1 does not match the end tag of 'Contcts'. Line 5, position 13.  
```  
  
 <span data-ttu-id="77c23-112">Сведения об исключениях, которые могут возникать <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>, и <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>методов, в разделе <xref:System.Xml.XmlReader>документации.</xref:System.Xml.XmlReader> </xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName> </xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName> </xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName> </xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="77c23-112">For information about the exceptions that you can expect the <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>, and <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName> methods to throw, see the <xref:System.Xml.XmlReader> documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77c23-113">См. также</span><span class="sxs-lookup"><span data-stu-id="77c23-113">See Also</span></span>  
 [<span data-ttu-id="77c23-114">Синтаксический анализ XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="77c23-114">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
