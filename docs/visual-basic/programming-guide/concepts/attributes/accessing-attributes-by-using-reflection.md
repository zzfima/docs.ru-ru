---
title: "Доступ к атрибутам с помощью отражения (Visual Basic) | Документы Microsoft"
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
ms.assetid: c56e41da-5433-464f-a7bf-2a722e78bc9f
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
ms.openlocfilehash: ac1e017ae13fc1291fd41e5747171160a9d70238
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="accessing-attributes-by-using-reflection-visual-basic"></a><span data-ttu-id="15b28-102">Доступ к атрибутам с помощью отражения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="15b28-102">Accessing Attributes by Using Reflection (Visual Basic)</span></span>
<span data-ttu-id="15b28-103">Тот факт, что можно определять настраиваемые атрибуты и поместить их в исходный код будет мало пользы, без какой-либо способ извлечения этих сведений и работы с ними.</span><span class="sxs-lookup"><span data-stu-id="15b28-103">The fact that you can define custom attributes and place them in your source code would be of little value without some way of retrieving that information and acting on it.</span></span> <span data-ttu-id="15b28-104">С помощью отражения, можно получить информацию, которая была определена с настраиваемыми атрибутами.</span><span class="sxs-lookup"><span data-stu-id="15b28-104">By using reflection, you can retrieve the information that was defined with custom attributes.</span></span> <span data-ttu-id="15b28-105">Основной метод — `GetCustomAttributes`, который возвращает массив объектов, которые являются эквивалентами времени выполнения атрибутов исходного кода.</span><span class="sxs-lookup"><span data-stu-id="15b28-105">The key method is `GetCustomAttributes`, which returns an array of objects that are the run-time equivalents of the source code attributes.</span></span> <span data-ttu-id="15b28-106">Этот метод имеет несколько перегруженных версий.</span><span class="sxs-lookup"><span data-stu-id="15b28-106">This method has several overloaded versions.</span></span> <span data-ttu-id="15b28-107">Дополнительные сведения см. в разделе <xref:System.Attribute>.</xref:System.Attribute></span><span class="sxs-lookup"><span data-stu-id="15b28-107">For more information, see <xref:System.Attribute>.</span></span>  
  
 <span data-ttu-id="15b28-108">Спецификация атрибута, например:</span><span class="sxs-lookup"><span data-stu-id="15b28-108">An attribute specification such as:</span></span>  
  
```vb  
<Author("P. Ackerman", Version:=1.1)>   
Class SampleClass  
    ' P. Ackerman's code goes here...  
End Class  
```  
  
 <span data-ttu-id="15b28-109">эквивалентен концептуально это:</span><span class="sxs-lookup"><span data-stu-id="15b28-109">is conceptually equivalent to this:</span></span>  
  
```vb  
Dim anonymousAuthorObject As Author = New Author("P. Ackerman")  
anonymousAuthorObject.version = 1.1  
```  
  
 <span data-ttu-id="15b28-110">Тем не менее, код не выполняется до `SampleClass` запрос по атрибутам.</span><span class="sxs-lookup"><span data-stu-id="15b28-110">However, the code is not executed until `SampleClass` is queried for attributes.</span></span> <span data-ttu-id="15b28-111">Вызов `GetCustomAttributes` на `SampleClass` вызывает `Author` объект создается и инициализируется как описано выше.</span><span class="sxs-lookup"><span data-stu-id="15b28-111">Calling `GetCustomAttributes` on `SampleClass` causes an `Author` object to be constructed and initialized as above.</span></span> <span data-ttu-id="15b28-112">Если класс имеет другие атрибуты, другие объекты атрибута создаются аналогично.</span><span class="sxs-lookup"><span data-stu-id="15b28-112">If the class has other attributes, other attribute objects are constructed similarly.</span></span> <span data-ttu-id="15b28-113">`GetCustomAttributes`Возвращает `Author` объектом и другими объектами атрибута в массив.</span><span class="sxs-lookup"><span data-stu-id="15b28-113">`GetCustomAttributes` then returns the `Author` object and any other attribute objects in an array.</span></span> <span data-ttu-id="15b28-114">Затем можно перейти по этому массиву, определить, какие атрибуты были применены на основе типа элемента массива и извлечь сведения из объектов.</span><span class="sxs-lookup"><span data-stu-id="15b28-114">You can then iterate over this array, determine what attributes were applied based on the type of each array element, and extract information from the attribute objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15b28-115">Пример</span><span class="sxs-lookup"><span data-stu-id="15b28-115">Example</span></span>  
 <span data-ttu-id="15b28-116">Ниже приведен полный пример.</span><span class="sxs-lookup"><span data-stu-id="15b28-116">Here is a complete example.</span></span> <span data-ttu-id="15b28-117">Настраиваемый атрибут определен, применяется к нескольким сущностям и извлекается через отражение.</span><span class="sxs-lookup"><span data-stu-id="15b28-117">A custom attribute is defined, applied to several entities, and retrieved via reflection.</span></span>  
  
```vb  
' Multiuse attribute  
<System.AttributeUsage(System.AttributeTargets.Class Or   
                       System.AttributeTargets.Struct,   
                       AllowMultiple:=True)>   
Public Class Author  
    Inherits System.Attribute  
    Private name As String  
    Public version As Double  
    Sub New(ByVal authorName As String)  
        name = authorName  
  
        ' Default value  
        version = 1.0  
    End Sub  
  
    Function GetName() As String  
        Return name  
    End Function          
End Class  
  
' Class with the Author attribute  
<Author("P. Ackerman")>   
Public Class FirstClass  
End Class  
  
' Class without the Author attribute  
Public Class SecondClass  
End Class  
  
' Class with multiple Author attributes.  
<Author("P. Ackerman"), Author("R. Koch", Version:=2.0)>   
Public Class ThirdClass  
End Class  
  
Class TestAuthorAttribute  
    Sub Main()  
        PrintAuthorInfo(GetType(FirstClass))  
        PrintAuthorInfo(GetType(SecondClass))  
        PrintAuthorInfo(GetType(ThirdClass))  
    End Sub  
  
    Private Shared Sub PrintAuthorInfo(ByVal t As System.Type)  
        System.Console.WriteLine("Author information for {0}", t)  
  
        ' Using reflection  
        Dim attrs() As System.Attribute = System.Attribute.GetCustomAttributes(t)  
  
        ' Displaying output  
        For Each attr In attrs  
            Dim a As Author = CType(attr, Author)  
            System.Console.WriteLine("   {0}, version {1:f}", a.GetName(), a.version)  
        Next              
    End Sub  
  
    ' Output:  
    '   Author information for FirstClass  
    '     P. Ackerman, version 1.00  
    ' Author information for SecondClass  
    ' Author information for ThirdClass  
    '  R. Koch, version 2.00  
    '  P. Ackerman, version 1.00  
  
End Class  
```  
  
## <a name="see-also"></a><span data-ttu-id="15b28-118">См. также</span><span class="sxs-lookup"><span data-stu-id="15b28-118">See Also</span></span>  
 <span data-ttu-id="15b28-119"><xref:System.Reflection></xref:System.Reflection></span><span class="sxs-lookup"><span data-stu-id="15b28-119"><xref:System.Reflection></span></span>   
 <span data-ttu-id="15b28-120"><xref:System.Attribute></xref:System.Attribute></span><span class="sxs-lookup"><span data-stu-id="15b28-120"><xref:System.Attribute></span></span>   
<span data-ttu-id="15b28-121"> [Руководство по программированию на Visual Basic](../../../../visual-basic/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="15b28-121"> [Visual Basic Programming Guide](../../../../visual-basic/programming-guide/index.md) </span></span>  
<span data-ttu-id="15b28-122"> [Извлечение информации, сохраненной в атрибуте](http://msdn.microsoft.com/library/37dfe4e3-7da0-48b6-a3d9-398981524e1c) </span><span class="sxs-lookup"><span data-stu-id="15b28-122"> [Retrieving Information Stored in Attributes](http://msdn.microsoft.com/library/37dfe4e3-7da0-48b6-a3d9-398981524e1c) </span></span>  
<span data-ttu-id="15b28-123"> [Отражение (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span><span class="sxs-lookup"><span data-stu-id="15b28-123"> [Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span></span>  
<span data-ttu-id="15b28-124"> [Атрибуты (Visual Basic)](../../../../visual-basic/language-reference/attributes.md) </span><span class="sxs-lookup"><span data-stu-id="15b28-124"> [Attributes (Visual Basic)](../../../../visual-basic/language-reference/attributes.md) </span></span>  
<span data-ttu-id="15b28-125"> [Создание настраиваемых атрибутов (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)</span><span class="sxs-lookup"><span data-stu-id="15b28-125"> [Creating Custom Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)</span></span>
