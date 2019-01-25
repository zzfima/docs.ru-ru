---
title: Как выполнить Написание метода расширения (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
ms.openlocfilehash: 019104956b21e527c0498c286d85da27abdc5695
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54576075"
---
# <a name="how-to-write-an-extension-method-visual-basic"></a><span data-ttu-id="2221d-102">Как выполнить Написание метода расширения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2221d-102">How to: Write an Extension Method (Visual Basic)</span></span>
<span data-ttu-id="2221d-103">Методы расширения позволяют добавлять методы к существующему классу.</span><span class="sxs-lookup"><span data-stu-id="2221d-103">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="2221d-104">Метод расширения может вызываться, как если бы это был экземпляр этого класса.</span><span class="sxs-lookup"><span data-stu-id="2221d-104">The extension method can be called as if it were an instance of that class.</span></span>  
  
### <a name="to-define-an-extension-method"></a><span data-ttu-id="2221d-105">Для определения метода расширения</span><span class="sxs-lookup"><span data-stu-id="2221d-105">To define an extension method</span></span>  
  
1.  <span data-ttu-id="2221d-106">Откройте новые или существующие приложения Visual Basic в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2221d-106">Open a new or existing Visual Basic application in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="2221d-107">В верхней части файла, в котором вы хотите определить метод расширения включите следующую инструкцию import:</span><span class="sxs-lookup"><span data-stu-id="2221d-107">At the top of the file in which you want to define an extension method, include the following import statement:</span></span>  
  
    ```  
    Imports System.Runtime.CompilerServices  
    ```  
  
3.  <span data-ttu-id="2221d-108">В модуле нового или существующего приложения определите метод атрибутом расширения:</span><span class="sxs-lookup"><span data-stu-id="2221d-108">Within a module in your new or existing application, begin the method definition with the extension attribute:</span></span>  
  
    ```  
    <Extension()>  
    ```  
  
4.  <span data-ttu-id="2221d-109">Объявите метод обычным способом, за исключением того, что тип первого параметра должен быть тип данных, который требуется расширить.</span><span class="sxs-lookup"><span data-stu-id="2221d-109">Declare your method in the ordinary way, except that the type of the first parameter must be the data type you want to extend.</span></span>  
  
    ```  
    <Extension()>   
    Public Sub subName (ByVal para1 As ExtendedType, <other parameters>)  
         ' < Body of the method >  
    End Sub  
    ```  
  
## <a name="example"></a><span data-ttu-id="2221d-110">Пример</span><span class="sxs-lookup"><span data-stu-id="2221d-110">Example</span></span>  
 <span data-ttu-id="2221d-111">В следующем примере объявляется метод расширения в модуле `StringExtensions`.</span><span class="sxs-lookup"><span data-stu-id="2221d-111">The following example declares an extension method in module `StringExtensions`.</span></span> <span data-ttu-id="2221d-112">Второй модуль `Module1`, импортирует `StringExtensions` и вызывает метод.</span><span class="sxs-lookup"><span data-stu-id="2221d-112">A second module, `Module1`, imports `StringExtensions` and calls the method.</span></span> <span data-ttu-id="2221d-113">Метод расширения должен находиться в области, при вызове.</span><span class="sxs-lookup"><span data-stu-id="2221d-113">The extension method must be in scope when it is called.</span></span> <span data-ttu-id="2221d-114">Метод расширения `PrintAndPunctuate` расширяет <xref:System.String> класс с методом, который отображает экземпляр строки и строки символов пунктуации, отправляемый в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="2221d-114">Extension method `PrintAndPunctuate` extends the <xref:System.String> class with a method that displays the string instance followed by a string of punctuation symbols sent in as a parameter.</span></span>  
  
```vb  
' Declarations will typically be in a separate module.  
Imports System.Runtime.CompilerServices  
  
Module StringExtensions  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
        Console.WriteLine(aString & punc)  
    End Sub  
  
End Module  
```  
  
```vb  
' Import the module that holds the extension method you want to use,   
' and call it.  
  
Imports ConsoleApplication2.StringExtensions  
  
Module Module1  
  
    Sub Main()  
        Dim example = "Hello"  
        example.PrintAndPunctuate("?")  
        example.PrintAndPunctuate("!!!!")  
    End Sub  
  
End Module  
```  
  
 <span data-ttu-id="2221d-115">Обратите внимание на то, что метод определен с двумя параметрами и только с одним именем.</span><span class="sxs-lookup"><span data-stu-id="2221d-115">Notice that the method is defined with two parameters and called with only one.</span></span> <span data-ttu-id="2221d-116">Первый параметр, `aString`, в методе связано `example`, экземпляр `String` , вызывает метод.</span><span class="sxs-lookup"><span data-stu-id="2221d-116">The first parameter, `aString`, in the method definition is bound to `example`, the instance of `String` that calls the method.</span></span> <span data-ttu-id="2221d-117">Выходные данные примера могут быть следующими:</span><span class="sxs-lookup"><span data-stu-id="2221d-117">The output of the example is as follows:</span></span>  
  
 `Hello?`  
  
 `Hello!!!!`  
  
## <a name="see-also"></a><span data-ttu-id="2221d-118">См. также</span><span class="sxs-lookup"><span data-stu-id="2221d-118">See also</span></span>
- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [<span data-ttu-id="2221d-119">Методы расширения</span><span class="sxs-lookup"><span data-stu-id="2221d-119">Extension Methods</span></span>](./extension-methods.md)
- [<span data-ttu-id="2221d-120">Оператор Module</span><span class="sxs-lookup"><span data-stu-id="2221d-120">Module Statement</span></span>](../../../../visual-basic/language-reference/statements/module-statement.md)
- [<span data-ttu-id="2221d-121">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="2221d-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="2221d-122">Область, в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2221d-122">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
