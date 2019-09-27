---
title: Практическое руководство. Написание метода расширения (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
ms.openlocfilehash: 31ccb18e0e6d1569764ec2a67201d7f758129425
ms.sourcegitcommit: 8b8dd14dde727026fd0b6ead1ec1df2e9d747a48
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2019
ms.locfileid: "71332760"
---
# <a name="how-to-write-an-extension-method-visual-basic"></a><span data-ttu-id="38629-102">Практическое руководство. Написание метода расширения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="38629-102">How to: Write an Extension Method (Visual Basic)</span></span>

<span data-ttu-id="38629-103">Методы расширения позволяют добавлять методы в существующий класс.</span><span class="sxs-lookup"><span data-stu-id="38629-103">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="38629-104">Метод расширения можно вызвать так, как если бы он был экземпляром этого класса.</span><span class="sxs-lookup"><span data-stu-id="38629-104">The extension method can be called as if it were an instance of that class.</span></span>

### <a name="to-define-an-extension-method"></a><span data-ttu-id="38629-105">Определение метода расширения</span><span class="sxs-lookup"><span data-stu-id="38629-105">To define an extension method</span></span>

1. <span data-ttu-id="38629-106">Откройте новое или существующее приложение Visual Basic в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="38629-106">Open a new or existing Visual Basic application in Visual Studio.</span></span>

2. <span data-ttu-id="38629-107">В верхней части файла, в котором нужно определить метод расширения, включите следующую инструкцию импорта:</span><span class="sxs-lookup"><span data-stu-id="38629-107">At the top of the file in which you want to define an extension method, include the following import statement:</span></span>

    ```vb
    Imports System.Runtime.CompilerServices
    ```

3. <span data-ttu-id="38629-108">В модуле в новом или существующем приложении приступите к определению метода с помощью атрибута extension:</span><span class="sxs-lookup"><span data-stu-id="38629-108">Within a module in your new or existing application, begin the method definition with the extension attribute:</span></span>

    ```vb
    <Extension()>
    ```

4. <span data-ttu-id="38629-109">Объявите метод обычным способом, за исключением того, что тип первого параметра должен быть типом данных, который требуется расширить.</span><span class="sxs-lookup"><span data-stu-id="38629-109">Declare your method in the ordinary way, except that the type of the first parameter must be the data type you want to extend.</span></span>

    ```vb
    <Extension()>
    Public Sub SubName(para1 As ExtendedType, <other parameters>)
         ' < Body of the method >
    End Sub
    ```

## <a name="example"></a><span data-ttu-id="38629-110">Пример</span><span class="sxs-lookup"><span data-stu-id="38629-110">Example</span></span>

 <span data-ttu-id="38629-111">В следующем примере объявляется метод расширения в модуле `StringExtensions`.</span><span class="sxs-lookup"><span data-stu-id="38629-111">The following example declares an extension method in module `StringExtensions`.</span></span> <span data-ttu-id="38629-112">Второй модуль, `Module1`, импортирует `StringExtensions` и вызывает метод.</span><span class="sxs-lookup"><span data-stu-id="38629-112">A second module, `Module1`, imports `StringExtensions` and calls the method.</span></span> <span data-ttu-id="38629-113">Метод расширения должен находиться в области видимости при его вызове.</span><span class="sxs-lookup"><span data-stu-id="38629-113">The extension method must be in scope when it is called.</span></span> <span data-ttu-id="38629-114">Метод расширения `PrintAndPunctuate` расширяет класс <xref:System.String> с помощью метода, который отображает экземпляр строки, за которым следует строка символов пунктуации, отправленная в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="38629-114">Extension method `PrintAndPunctuate` extends the <xref:System.String> class with a method that displays the string instance followed by a string of punctuation symbols sent in as a parameter.</span></span>
  
```vb
' Declarations will typically be in a separate module.
Imports System.Runtime.CompilerServices

Module StringExtensions
    <Extension()>
    Public Sub PrintAndPunctuate(aString As String, punc As String)
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
  
 <span data-ttu-id="38629-115">Обратите внимание, что метод определен с двумя параметрами и вызывается только с одним.</span><span class="sxs-lookup"><span data-stu-id="38629-115">Notice that the method is defined with two parameters and called with only one.</span></span> <span data-ttu-id="38629-116">Первый параметр, `aString`, в определении метода привязан к `example`, экземпляру `String`, который вызывает метод.</span><span class="sxs-lookup"><span data-stu-id="38629-116">The first parameter, `aString`, in the method definition is bound to `example`, the instance of `String` that calls the method.</span></span> <span data-ttu-id="38629-117">Выходные данные примера могут быть следующими:</span><span class="sxs-lookup"><span data-stu-id="38629-117">The output of the example is as follows:</span></span>
  
 ```console
 Hello?
 Hello!!!!
 ```
  
## <a name="see-also"></a><span data-ttu-id="38629-118">См. также</span><span class="sxs-lookup"><span data-stu-id="38629-118">See also</span></span>

- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [<span data-ttu-id="38629-119">Методы расширения</span><span class="sxs-lookup"><span data-stu-id="38629-119">Extension Methods</span></span>](extension-methods.md)
- [<span data-ttu-id="38629-120">Оператор Module</span><span class="sxs-lookup"><span data-stu-id="38629-120">Module Statement</span></span>](../../../language-reference/statements/module-statement.md)
- [<span data-ttu-id="38629-121">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="38629-121">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="38629-122">Область в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="38629-122">Scope in Visual Basic</span></span>](../declared-elements/scope.md)
