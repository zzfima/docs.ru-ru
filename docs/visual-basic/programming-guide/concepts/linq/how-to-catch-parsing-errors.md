---
title: Практическое руководство. Перехват ошибок разбора
ms.date: 07/20/2015
ms.assetid: 22e9068e-ea58-447b-816e-cd1852c11787
ms.openlocfilehash: 14c4f76c5f10616f9346084cda276e2862b2b41d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353341"
---
# <a name="how-to-catch-parsing-errors-visual-basic"></a>Как перехватывать ошибки синтаксического анализа (Visual Basic)
В этом разделе показано, как обнаружить код XML, имеющий неправильный формат или не прошедший проверку правильности.  
  
 Технология [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] реализуется с помощью объекта <xref:System.Xml.XmlReader>. Если средствам [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] передается код XML, имеющий неправильный формат или не прошедший проверку правильности, то в базовом классе <xref:System.Xml.XmlReader> активизируется исключение. Различные методы, выполняющие синтаксический анализ XML, например <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, не перехватывают это исключение; его можно перехватить позднее в приложении.  
  
 Обратите внимание, что при использовании XML-литералов невозможно обнаружить ошибки синтаксического анализа. Ошибки, активизируемые при обнаружении имеющего неправильный формат или не прошедшего проверку правильности кода XML, перехватывает компилятор Visual Basic.  
  
## <a name="example"></a>Пример  
 В следующем коде предпринимается попытка выполнить синтаксический анализ кода XML, не прошедшего проверку правильности.  
  
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
  
 При выполнении этого кода активизируется следующее исключение.  
  
```console  
The 'Contacts' start tag on line 1 does not match the end tag of 'Contcts'. Line 5, position 13.  
```  
  
 Сведения об исключениях, которые могут возникать при использовании методов <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> и <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> см. в документации <xref:System.Xml.XmlReader>.  
  
## <a name="see-also"></a>См. также

- [Синтаксический анализ XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
