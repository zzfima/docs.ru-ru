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
# <a name="how-to-catch-parsing-errors-c"></a>Практическое руководство. Перехват ошибок анализа (C#)
В этом разделе показано, как обнаружить код XML, имеющий неправильный формат или не прошедший проверку правильности.  
  
 Технология [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] реализуется с помощью объекта <xref:System.Xml.XmlReader>. Если средствам [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] передается код XML, имеющий неправильный формат или не прошедший проверку правильности, то в базовом классе <xref:System.Xml.XmlReader> активизируется исключение. Различные методы, выполняющие синтаксический анализ XML, например <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>, не перехватывают это исключение; его можно перехватить позднее в приложении.  
  
## <a name="example"></a>Пример  
 В следующем коде предпринимается попытка выполнить синтаксический анализ кода XML, не прошедшего проверку правильности.  
  
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
  
 При выполнении этого кода активизируется следующее исключение.  
  
```  
The 'Contacts' start tag on line 1 does not match the end tag of 'Contcts'. Line 5, position 13.  
```  
  
 Сведения об исключениях, которые могут возникать при использовании методов <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName> и <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName> см. в документации <xref:System.Xml.XmlReader>.  
  
## <a name="see-also"></a>См. также  
 [Анализ XML (C#)](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md)

