---
title: Практическое руководство. Вызов метода расширения (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- calling extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: df07750f-40f4-4c07-a79e-1113a27cfbea
ms.openlocfilehash: 5cb0684637a716dfec947740ba345c62eaabddd7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59313805"
---
# <a name="how-to-call-an-extension-method-visual-basic"></a><span data-ttu-id="affdc-102">Практическое руководство. Вызов метода расширения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="affdc-102">How to: Call an Extension Method (Visual Basic)</span></span>
<span data-ttu-id="affdc-103">Методы расширения позволяют добавлять методы к существующему классу.</span><span class="sxs-lookup"><span data-stu-id="affdc-103">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="affdc-104">После объявления и добавлены в область действия методом расширения, его можно вызывать как метод экземпляра типа, который он расширяет.</span><span class="sxs-lookup"><span data-stu-id="affdc-104">After an extension method is declared and brought into scope, you can call it like an instance method of the type that it extends.</span></span> <span data-ttu-id="affdc-105">Дополнительные сведения о том, как написание метода расширения, см. в разделе [как: Написание метода расширения](./how-to-write-an-extension-method.md).</span><span class="sxs-lookup"><span data-stu-id="affdc-105">For more information about how to write an extension method, see [How to: Write an Extension Method](./how-to-write-an-extension-method.md).</span></span>  
  
 <span data-ttu-id="affdc-106">Приведенные ниже инструкции относятся к методу расширения `PrintAndPunctuate`, для второго параметра, который будет отображать экземпляр строки и вызывает его, любое значение отправляется в `punc`.</span><span class="sxs-lookup"><span data-stu-id="affdc-106">The following instructions refer to extension method `PrintAndPunctuate`, which will display the string instance that invokes it, followed by whatever value is sent in for the second parameter, `punc`.</span></span>  
  
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
  
 <span data-ttu-id="affdc-107">Метод должен находиться в области, при вызове.</span><span class="sxs-lookup"><span data-stu-id="affdc-107">The method must be in scope when it is called.</span></span>  
  
### <a name="to-call-an-extension-method"></a><span data-ttu-id="affdc-108">Для вызова метода расширения</span><span class="sxs-lookup"><span data-stu-id="affdc-108">To call an extension method</span></span>  
  
1. <span data-ttu-id="affdc-109">Объявите переменную, которая имеет тип данных первого параметра метода расширения.</span><span class="sxs-lookup"><span data-stu-id="affdc-109">Declare a variable that has the data type of the first parameter of the extension method.</span></span> <span data-ttu-id="affdc-110">Для `PrintAndPunctuate`, вам потребуется <xref:System.String> переменной:</span><span class="sxs-lookup"><span data-stu-id="affdc-110">For `PrintAndPunctuate`, you need a <xref:System.String> variable:</span></span>  
  
    ```  
    Dim example = "Ready"  
    ```  
  
2. <span data-ttu-id="affdc-111">Переменная будет вызвать метод расширения, что его значение, привязанное к первому параметру `aString`.</span><span class="sxs-lookup"><span data-stu-id="affdc-111">That variable will invoke the extension method, and its value is bound to the first parameter, `aString`.</span></span> <span data-ttu-id="affdc-112">Следующая инструкция вызова будет отображать `Ready?`.</span><span class="sxs-lookup"><span data-stu-id="affdc-112">The following calling statement will display `Ready?`.</span></span>  
  
    ```  
    example.PrintAndPunctuate("?")  
    ```  
  
     <span data-ttu-id="affdc-113">Обратите внимание, что вызов этого метода расширения выглядит, как вызов любого из <xref:System.String> экземпляра методов, которым требуется один параметр:</span><span class="sxs-lookup"><span data-stu-id="affdc-113">Notice that the call to this extension method looks just like a call to any one of the <xref:System.String> instance methods that require one parameter:</span></span>  
  
    ```  
    example.EndsWith("dy")  
    example.IndexOf("R")  
    ```  
  
3. <span data-ttu-id="affdc-114">Объявите другую строковую переменную и вызовите метод еще раз, чтобы увидеть, что он работает с любой строкой.</span><span class="sxs-lookup"><span data-stu-id="affdc-114">Declare another string variable and call the method again to see that it works with any string.</span></span>  
  
    ```  
    Dim example2 = " or not"  
    example2.PrintAndPunctuate("!!!")  
    ```  
  
     <span data-ttu-id="affdc-115">Результатом является это время: `or not!!!`.</span><span class="sxs-lookup"><span data-stu-id="affdc-115">The result this time is: `or not!!!`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="affdc-116">Пример</span><span class="sxs-lookup"><span data-stu-id="affdc-116">Example</span></span>  
 <span data-ttu-id="affdc-117">Ниже приведен полный пример создания и использования метода простого расширения.</span><span class="sxs-lookup"><span data-stu-id="affdc-117">The following code is a complete example of the creation and use of a simple extension method.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="affdc-118">См. также</span><span class="sxs-lookup"><span data-stu-id="affdc-118">See also</span></span>

- [<span data-ttu-id="affdc-119">Практическое руководство. Написание метода расширения</span><span class="sxs-lookup"><span data-stu-id="affdc-119">How to: Write an Extension Method</span></span>](./how-to-write-an-extension-method.md)
- [<span data-ttu-id="affdc-120">Методы расширения</span><span class="sxs-lookup"><span data-stu-id="affdc-120">Extension Methods</span></span>](./extension-methods.md)
- [<span data-ttu-id="affdc-121">Область, в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="affdc-121">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
