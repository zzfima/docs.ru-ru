---
title: "Практическое руководство. Вызов метода расширения (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- calling extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: df07750f-40f4-4c07-a79e-1113a27cfbea
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 25b5a86af15694e6f64f96a5d5d645a01f8f1f12
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-an-extension-method-visual-basic"></a><span data-ttu-id="1f37e-102">Практическое руководство. Вызов метода расширения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f37e-102">How to: Call an Extension Method (Visual Basic)</span></span>
<span data-ttu-id="1f37e-103">Методы расширения позволяют добавлять методы в существующий класс.</span><span class="sxs-lookup"><span data-stu-id="1f37e-103">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="1f37e-104">После объявления метода расширения и добавлены в область действия, его можно вызывать как метод экземпляра типа, который он расширяет.</span><span class="sxs-lookup"><span data-stu-id="1f37e-104">After an extension method is declared and brought into scope, you can call it like an instance method of the type that it extends.</span></span> <span data-ttu-id="1f37e-105">Дополнительные сведения о написании метода расширения см. в разделе [как: написание метода расширения](./how-to-write-an-extension-method.md).</span><span class="sxs-lookup"><span data-stu-id="1f37e-105">For more information about how to write an extension method, see [How to: Write an Extension Method](./how-to-write-an-extension-method.md).</span></span>  
  
 <span data-ttu-id="1f37e-106">Следующие инструкции относятся к методу расширения `PrintAndPunctuate`, который будет отображать экземпляр строки и вызывает его любое значение отправляется для второго параметра `punc`.</span><span class="sxs-lookup"><span data-stu-id="1f37e-106">The following instructions refer to extension method `PrintAndPunctuate`, which will display the string instance that invokes it, followed by whatever value is sent in for the second parameter, `punc`.</span></span>  
  
```vb  
Imports System.Runtime.CompilerServices  
  
Module StringExtensions  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
        Console.WriteLine(aString & punc)  
    End Sub  
  
End Module  
```  
  
 <span data-ttu-id="1f37e-107">Метод должен быть в области, когда он вызывается.</span><span class="sxs-lookup"><span data-stu-id="1f37e-107">The method must be in scope when it is called.</span></span>  
  
### <a name="to-call-an-extension-method"></a><span data-ttu-id="1f37e-108">Вызов метода расширения</span><span class="sxs-lookup"><span data-stu-id="1f37e-108">To call an extension method</span></span>  
  
1.  <span data-ttu-id="1f37e-109">Объявите переменную, которая имеет тип данных первого параметра метода расширения.</span><span class="sxs-lookup"><span data-stu-id="1f37e-109">Declare a variable that has the data type of the first parameter of the extension method.</span></span> <span data-ttu-id="1f37e-110">Для `PrintAndPunctuate`, требуется <xref:System.String> переменной:</span><span class="sxs-lookup"><span data-stu-id="1f37e-110">For `PrintAndPunctuate`, you need a <xref:System.String> variable:</span></span>  
  
    ```  
    Dim example = "Ready"  
    ```  
  
2.  <span data-ttu-id="1f37e-111">Переменная будет вызвать метод расширения, что его значение, привязанное к первому параметру `aString`.</span><span class="sxs-lookup"><span data-stu-id="1f37e-111">That variable will invoke the extension method, and its value is bound to the first parameter, `aString`.</span></span> <span data-ttu-id="1f37e-112">Следующая инструкция вызова будет отображать `Ready?`.</span><span class="sxs-lookup"><span data-stu-id="1f37e-112">The following calling statement will display `Ready?`.</span></span>  
  
    ```  
    example.PrintAndPunctuate("?")  
    ```  
  
     <span data-ttu-id="1f37e-113">Обратите внимание, что вызов этого метода расширения выглядит, как вызов любого из <xref:System.String> экземпляра методов, которым требуется один параметр:</span><span class="sxs-lookup"><span data-stu-id="1f37e-113">Notice that the call to this extension method looks just like a call to any one of the <xref:System.String> instance methods that require one parameter:</span></span>  
  
    ```  
    example.EndsWith("dy")  
    example.IndexOf("R")  
    ```  
  
3.  <span data-ttu-id="1f37e-114">Объявите другую строковую переменную и вызовите метод, чтобы проверить, что он работает с любой строкой.</span><span class="sxs-lookup"><span data-stu-id="1f37e-114">Declare another string variable and call the method again to see that it works with any string.</span></span>  
  
    ```  
    Dim example2 = " or not"  
    example2.PrintAndPunctuate("!!!")  
    ```  
  
     <span data-ttu-id="1f37e-115">Результатом является это время: `or not!!!`.</span><span class="sxs-lookup"><span data-stu-id="1f37e-115">The result this time is: `or not!!!`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f37e-116">Пример</span><span class="sxs-lookup"><span data-stu-id="1f37e-116">Example</span></span>  
 <span data-ttu-id="1f37e-117">Ниже приведен полный пример создания и использования метода простого расширения.</span><span class="sxs-lookup"><span data-stu-id="1f37e-117">The following code is a complete example of the creation and use of a simple extension method.</span></span>  
  
```vb  
Imports System.Runtime.CompilerServices  
Imports ConsoleApplication1.StringExtensions  
  
Module Module1  
  
    Sub Main()  
  
        Dim example = "Hello"  
        example.PrintAndPunctuate(".")  
        example.PrintAndPunctuate("!!!!")  
  
        Dim example2 = "Goodbye"  
        example2.PrintAndPunctuate("?")  
    End Sub  
  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
        Console.WriteLine(aString & punc)  
    End Sub  
End Module  
  
' Output:  
' Hello.  
' Hello!!!!  
' Goodbye?  
```  
  
## <a name="see-also"></a><span data-ttu-id="1f37e-118">См. также</span><span class="sxs-lookup"><span data-stu-id="1f37e-118">See Also</span></span>  
 [<span data-ttu-id="1f37e-119">Практическое руководство. Написание метода расширения</span><span class="sxs-lookup"><span data-stu-id="1f37e-119">How to: Write an Extension Method</span></span>](./how-to-write-an-extension-method.md)  
 [<span data-ttu-id="1f37e-120">Методы расширения</span><span class="sxs-lookup"><span data-stu-id="1f37e-120">Extension Methods</span></span>](./extension-methods.md)  
 [<span data-ttu-id="1f37e-121">Область в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1f37e-121">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
