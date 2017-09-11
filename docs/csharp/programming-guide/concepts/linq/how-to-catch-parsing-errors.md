---
title: "Практическое руководство. Перехват ошибок анализа (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: bfb612d4-5605-48ef-8c93-915cf9d5dcfb
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 240bc9770475bdf7b6da2102bd8b552a0991eea6
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-catch-parsing-errors-c"></a><span data-ttu-id="3db28-102">Практическое руководство. Перехват ошибок анализа (C#)</span><span class="sxs-lookup"><span data-stu-id="3db28-102">How to: Catch Parsing Errors (C#)</span></span>
<span data-ttu-id="3db28-103">В этом разделе показано, как обнаружить код XML, имеющий неправильный формат или не прошедший проверку правильности.</span><span class="sxs-lookup"><span data-stu-id="3db28-103">This topic shows how to detect badly formed or invalid XML.</span></span>  
  
 <span data-ttu-id="3db28-104">Технология [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] реализуется с помощью объекта <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="3db28-104">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is implemented using <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="3db28-105">Если средствам [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] передается код XML, имеющий неправильный формат или не прошедший проверку правильности, то в базовом классе <xref:System.Xml.XmlReader> активизируется исключение.</span><span class="sxs-lookup"><span data-stu-id="3db28-105">If badly formed or invalid XML is passed to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], the underlying <xref:System.Xml.XmlReader> class will throw an exception.</span></span> <span data-ttu-id="3db28-106">Различные методы, выполняющие синтаксический анализ XML, например <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>, не перехватывают это исключение; его можно перехватить позднее в приложении.</span><span class="sxs-lookup"><span data-stu-id="3db28-106">The various methods that parse XML, such as <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>, do not catch the exception; the exception can then be caught by your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3db28-107">Пример</span><span class="sxs-lookup"><span data-stu-id="3db28-107">Example</span></span>  
 <span data-ttu-id="3db28-108">В следующем коде предпринимается попытка выполнить синтаксический анализ кода XML, не прошедшего проверку правильности.</span><span class="sxs-lookup"><span data-stu-id="3db28-108">The following code tries to parse invalid XML:</span></span>  
  
```csharp  
try {  
    XElement contacts = XElement.Parse(  
        @"<Contacts>  
            <Contact>  
                <Name>Jim Wilson</Name>  
            </Contact>  
          </Contcts>");  
  
    Console.WriteLine(contacts);  
}  
catch (System.Xml.XmlException e)  
{  
    Console.WriteLine(e.Message);  
}  
```  
  
 <span data-ttu-id="3db28-109">При выполнении этого кода активизируется следующее исключение.</span><span class="sxs-lookup"><span data-stu-id="3db28-109">When you run this code, it throws the following exception:</span></span>  
  
```  
The 'Contacts' start tag on line 1 does not match the end tag of 'Contcts'. Line 5, position 13.  
```  
  
 <span data-ttu-id="3db28-110">Сведения об исключениях, которые могут возникать при использовании методов <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName> и <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName> см. в документации <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="3db28-110">For information about the exceptions that you can expect the <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>, and <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName> methods to throw, see the <xref:System.Xml.XmlReader> documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3db28-111">См. также</span><span class="sxs-lookup"><span data-stu-id="3db28-111">See Also</span></span>  
 [<span data-ttu-id="3db28-112">Анализ XML (C#)</span><span class="sxs-lookup"><span data-stu-id="3db28-112">Parsing XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md)

