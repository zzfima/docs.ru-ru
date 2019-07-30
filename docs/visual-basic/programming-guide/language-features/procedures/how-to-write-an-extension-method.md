---
title: Практическое руководство. Написание метода расширения (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
ms.openlocfilehash: 7a7a9d16d9f69071e9d1dacb0558f7ca92e1d21e
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68631033"
---
# <a name="how-to-write-an-extension-method-visual-basic"></a><span data-ttu-id="56fde-102">Практическое руководство. Написание метода расширения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="56fde-102">How to: Write an Extension Method (Visual Basic)</span></span>
<span data-ttu-id="56fde-103">Методы расширения позволяют добавлять методы в существующий класс.</span><span class="sxs-lookup"><span data-stu-id="56fde-103">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="56fde-104">Метод расширения можно вызвать так, как если бы он был экземпляром этого класса.</span><span class="sxs-lookup"><span data-stu-id="56fde-104">The extension method can be called as if it were an instance of that class.</span></span>

### <a name="to-define-an-extension-method"></a><span data-ttu-id="56fde-105">Определение метода расширения</span><span class="sxs-lookup"><span data-stu-id="56fde-105">To define an extension method</span></span>

1. <span data-ttu-id="56fde-106">Откройте новое или существующее приложение Visual Basic в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="56fde-106">Open a new or existing Visual Basic application in Visual Studio.</span></span>

2. <span data-ttu-id="56fde-107">В верхней части файла, в котором нужно определить метод расширения, включите следующую инструкцию импорта:</span><span class="sxs-lookup"><span data-stu-id="56fde-107">At the top of the file in which you want to define an extension method, include the following import statement:</span></span>

    ```vb
    Imports System.Runtime.CompilerServices
    ```

3. <span data-ttu-id="56fde-108">В модуле в новом или существующем приложении приступите к определению метода с помощью атрибута extension:</span><span class="sxs-lookup"><span data-stu-id="56fde-108">Within a module in your new or existing application, begin the method definition with the extension attribute:</span></span>

    ```vb
    <Extension()>
    ```

4. <span data-ttu-id="56fde-109">Объявите метод обычным способом, за исключением того, что тип первого параметра должен быть типом данных, который требуется расширить.</span><span class="sxs-lookup"><span data-stu-id="56fde-109">Declare your method in the ordinary way, except that the type of the first parameter must be the data type you want to extend.</span></span>

    ```vb
    <Extension()>
    Public Sub SubName (ByVal para1 As ExtendedType, <other parameters>)
         ' < Body of the method >
    End Sub
    ```

## <a name="example"></a><span data-ttu-id="56fde-110">Пример</span><span class="sxs-lookup"><span data-stu-id="56fde-110">Example</span></span>
 <span data-ttu-id="56fde-111">В следующем примере объявляется метод расширения в модуле `StringExtensions`.</span><span class="sxs-lookup"><span data-stu-id="56fde-111">The following example declares an extension method in module `StringExtensions`.</span></span> <span data-ttu-id="56fde-112">Второй модуль, `Module1`, импортирует `StringExtensions` и вызывает метод.</span><span class="sxs-lookup"><span data-stu-id="56fde-112">A second module, `Module1`, imports `StringExtensions` and calls the method.</span></span> <span data-ttu-id="56fde-113">Метод расширения должен находиться в области видимости при его вызове.</span><span class="sxs-lookup"><span data-stu-id="56fde-113">The extension method must be in scope when it is called.</span></span> <span data-ttu-id="56fde-114">Метод `PrintAndPunctuate` расширения<xref:System.String> расширяет класс с помощью метода, который отображает экземпляр строки, за которым следует строка символов пунктуации, отправленная в в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="56fde-114">Extension method `PrintAndPunctuate` extends the <xref:System.String> class with a method that displays the string instance followed by a string of punctuation symbols sent in as a parameter.</span></span>
  
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
  
 <span data-ttu-id="56fde-115">Обратите внимание, что метод определен с двумя параметрами и вызывается только с одним.</span><span class="sxs-lookup"><span data-stu-id="56fde-115">Notice that the method is defined with two parameters and called with only one.</span></span> <span data-ttu-id="56fde-116">Первый параметр, `aString`, в определении метода, привязан к `example`экземпляру `String` , который вызывает метод.</span><span class="sxs-lookup"><span data-stu-id="56fde-116">The first parameter, `aString`, in the method definition is bound to `example`, the instance of `String` that calls the method.</span></span> <span data-ttu-id="56fde-117">Выходные данные примера могут быть следующими:</span><span class="sxs-lookup"><span data-stu-id="56fde-117">The output of the example is as follows:</span></span>
  
 `Hello?`  
  
 `Hello!!!!`  
  
## <a name="see-also"></a><span data-ttu-id="56fde-118">См. также</span><span class="sxs-lookup"><span data-stu-id="56fde-118">See also</span></span>

- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [<span data-ttu-id="56fde-119">Методы расширения</span><span class="sxs-lookup"><span data-stu-id="56fde-119">Extension Methods</span></span>](./extension-methods.md)
- [<span data-ttu-id="56fde-120">Оператор Module</span><span class="sxs-lookup"><span data-stu-id="56fde-120">Module Statement</span></span>](../../../../visual-basic/language-reference/statements/module-statement.md)
- [<span data-ttu-id="56fde-121">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="56fde-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="56fde-122">Область в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="56fde-122">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
