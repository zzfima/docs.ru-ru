---
title: "Как: перехватывать синтаксический анализ ошибок (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 22e9068e-ea58-447b-816e-cd1852c11787
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 82b7c51aa8d0f9f64094211c56875e6595607c00
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-catch-parsing-errors-visual-basic"></a><span data-ttu-id="2f636-102">Как: перехватывать синтаксический анализ ошибок (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2f636-102">How to: Catch Parsing Errors (Visual Basic)</span></span>
<span data-ttu-id="2f636-103">В этом разделе показано, как обнаружить код XML, имеющий неправильный формат или не прошедший проверку правильности.</span><span class="sxs-lookup"><span data-stu-id="2f636-103">This topic shows how to detect badly formed or invalid XML.</span></span>  
  
 <span data-ttu-id="2f636-104">Технология [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] реализуется с помощью объекта <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="2f636-104">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is implemented using <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="2f636-105">Если средствам [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] передается код XML, имеющий неправильный формат или не прошедший проверку правильности, то в базовом классе <xref:System.Xml.XmlReader> активизируется исключение.</span><span class="sxs-lookup"><span data-stu-id="2f636-105">If badly formed or invalid XML is passed to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], the underlying <xref:System.Xml.XmlReader> class will throw an exception.</span></span> <span data-ttu-id="2f636-106">Различные методы, выполняющие синтаксический анализ XML, например <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, не перехватывают это исключение; его можно перехватить позднее в приложении.</span><span class="sxs-lookup"><span data-stu-id="2f636-106">The various methods that parse XML, such as <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, do not catch the exception; the exception can then be caught by your application.</span></span>  
  
 <span data-ttu-id="2f636-107">Обратите внимание, что при использовании XML-литералов невозможно обнаружить ошибки синтаксического анализа.</span><span class="sxs-lookup"><span data-stu-id="2f636-107">Note that you cannot get parse errors if you use XML literals.</span></span> <span data-ttu-id="2f636-108">Ошибки, активизируемые при обнаружении имеющего неправильный формат или не прошедшего проверку правильности кода XML, перехватывает компилятор Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="2f636-108">The Visual Basic compiler will catch errors of badly formed or invalid XML.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f636-109">Пример</span><span class="sxs-lookup"><span data-stu-id="2f636-109">Example</span></span>  
 <span data-ttu-id="2f636-110">В следующем коде предпринимается попытка выполнить синтаксический анализ кода XML, не прошедшего проверку правильности.</span><span class="sxs-lookup"><span data-stu-id="2f636-110">The following code tries to parse invalid XML:</span></span>  
  
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
  
 <span data-ttu-id="2f636-111">При выполнении этого кода активизируется следующее исключение.</span><span class="sxs-lookup"><span data-stu-id="2f636-111">When you run this code, it throws the following exception:</span></span>  
  
```  
The 'Contacts' start tag on line 1 does not match the end tag of 'Contcts'. Line 5, position 13.  
```  
  
 <span data-ttu-id="2f636-112">Сведения об исключениях, которые могут возникать при использовании методов <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> и <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> см. в документации <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="2f636-112">For information about the exceptions that you can expect the <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>, and <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> methods to throw, see the <xref:System.Xml.XmlReader> documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f636-113">См. также</span><span class="sxs-lookup"><span data-stu-id="2f636-113">See Also</span></span>  
 [<span data-ttu-id="2f636-114">Синтаксический анализ XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2f636-114">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
