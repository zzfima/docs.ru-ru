---
title: "Практическое руководство: сериализация с использованием DataContractSerializer (Visual Basic) | Документы Microsoft"
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
ms.assetid: ecaea518-8a0f-4249-b4e5-9b3fb0cdd8ad
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 7494a0296fd2bbba055fb1f49f87e8c73d85e8e4
ms.contentlocale: ru-ru
ms.lasthandoff: 05/23/2017

---
# <a name="how-to-serialize-using-datacontractserializer-visual-basic"></a><span data-ttu-id="23980-102">Практическое руководство: сериализация с использованием DataContractSerializer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="23980-102">How to: Serialize Using DataContractSerializer (Visual Basic)</span></span>
<span data-ttu-id="23980-103">В этом разделе приводится пример, где выполняется сериализация и десериализация с использованием <xref:System.Runtime.Serialization.DataContractSerializer>.</xref:System.Runtime.Serialization.DataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="23980-103">This topic shows an example that serializes and deserializes using <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23980-104">Пример</span><span class="sxs-lookup"><span data-stu-id="23980-104">Example</span></span>  
 <span data-ttu-id="23980-105">В следующем примере создается некоторое количество объектов, содержащих <xref:System.Xml.Linq.XElement>объектов.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="23980-105">The following example creates a number of objects that contain <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="23980-106">Затем они сериализуются в текстовые файлы и десериализуются из текстовых файлов.</span><span class="sxs-lookup"><span data-stu-id="23980-106">It then serializes them to text files, and then deserializes them from the text files.</span></span>  
  
```vb  
Imports System  
Imports System.Xml  
Imports System.Xml.Linq  
Imports System.IO  
Imports System.Runtime.Serialization  
  
Public Class XLinqTest  
    Shared Sub Main()  
        Test(Of XElement)(CreateXElement())  
        Test(Of XElementContainer)(New XElementContainer())  
        Test(Of XElementNullContainer)(New XElementNullContainer())  
    End Sub  
  
    Public Shared Sub Test(Of T)(ByRef obj)  
        Dim s As DataContractSerializer = New DataContractSerializer(GetType(T))  
        Using fs As FileStream = File.Open("test" & GetType(T).Name & ".xml", FileMode.Create)  
            Console.WriteLine("Testing for type: {0}", GetType(T))  
            s.WriteObject(fs, obj)  
        End Using  
  
        Using fs As FileStream = File.Open("test" & GetType(T).Name & ".xml", FileMode.Open)  
            Dim s2 As Object = s.ReadObject(fs)  
            If s2 Is Nothing Then  
                Console.WriteLine("  Deserialized object is null (Nothing in VB)")  
            Else  
                Console.WriteLine("  Deserialized type: {0}", s2.GetType())  
            End If  
        End Using  
    End Sub  
  
    Public Shared Function CreateXElement() As XElement  
        Return New XElement(XName.Get("NameInNamespace", "http://www.adventure-works.org"))  
    End Function  
End Class  
  
<DataContract()> _  
Public Class XElementContainer  
    <DataMember()> _  
    Public member As XElement  
  
    Public Sub XElementContainer()  
        member = XLinqTest.CreateXElement()  
    End Sub  
End Class  
  
<DataContract()> _  
Public Class XElementNullContainer  
    <DataMember()> _  
    Public member As XElement  
  
    Public Sub XElementNullContainer()  
        member = Nothing  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="23980-107">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="23980-107">This example produces the following output:</span></span>  
  
```  
Testing for type: System.Xml.Linq.XElement  
  Deserialized type: System.Xml.Linq.XElement  
Testing for type: XElementContainer  
  Deserialized type: XElementContainer  
Testing for type: XElementNullContainer  
  Deserialized type: XElementNullContainer  
```  
  
## <a name="see-also"></a><span data-ttu-id="23980-108">См. также</span><span class="sxs-lookup"><span data-stu-id="23980-108">See Also</span></span>  
 [<span data-ttu-id="23980-109">Сериализация графов объектов, содержащих объекты XElement (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="23980-109">Serializing Object Graphs that Contain XElement Objects (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-object-graphs-that-contain-xelement-objects.md)

