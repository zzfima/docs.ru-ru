---
title: Практическое руководство. Написание метода расширения
ms.date: 07/20/2015
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
ms.openlocfilehash: 697508f86ff4ff0a89150b65782121395d0fed12
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346019"
---
# <a name="how-to-write-an-extension-method-visual-basic"></a><span data-ttu-id="b6305-102">Практическое руководство. Написание метода расширения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b6305-102">How to: Write an Extension Method (Visual Basic)</span></span>

<span data-ttu-id="b6305-103">Методы расширения позволяют добавлять методы в существующий класс.</span><span class="sxs-lookup"><span data-stu-id="b6305-103">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="b6305-104">Метод расширения можно вызвать так, как если бы он был экземпляром этого класса.</span><span class="sxs-lookup"><span data-stu-id="b6305-104">The extension method can be called as if it were an instance of that class.</span></span>

### <a name="to-define-an-extension-method"></a><span data-ttu-id="b6305-105">Определение метода расширения</span><span class="sxs-lookup"><span data-stu-id="b6305-105">To define an extension method</span></span>

1. <span data-ttu-id="b6305-106">Откройте новое или существующее приложение Visual Basic в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b6305-106">Open a new or existing Visual Basic application in Visual Studio.</span></span>

2. <span data-ttu-id="b6305-107">В верхней части файла, в котором нужно определить метод расширения, включите следующую инструкцию импорта:</span><span class="sxs-lookup"><span data-stu-id="b6305-107">At the top of the file in which you want to define an extension method, include the following import statement:</span></span>

    ```vb
    Imports System.Runtime.CompilerServices
    ```

3. <span data-ttu-id="b6305-108">В модуле в новом или существующем приложении приступите к определению метода с помощью атрибута [`<Extension>`](xref:System.Runtime.CompilerServices.ExtensionAttribute) :</span><span class="sxs-lookup"><span data-stu-id="b6305-108">Within a module in your new or existing application, begin the method definition with the [`<Extension>`](xref:System.Runtime.CompilerServices.ExtensionAttribute) attribute:</span></span>

    ```vb
    <Extension()>
    ```

    <span data-ttu-id="b6305-109">Обратите внимание, что атрибут `Extension` можно применить только к методу (`Sub` или процедуре `Function`) в [модуле](../../../language-reference/statements/module-statement.md)Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b6305-109">Note that the `Extension` attribute can only be applied to a method (a `Sub` or `Function` procedure) in a Visual Basic [Module](../../../language-reference/statements/module-statement.md).</span></span> <span data-ttu-id="b6305-110">Если применить его к методу в `Class` или `Structure`, компилятор Visual Basic создает ошибку [BC36551](../../../misc/bc36551.md), "методы расширения могут быть определены только в модулях".</span><span class="sxs-lookup"><span data-stu-id="b6305-110">If you apply it to a method in a `Class` or a `Structure`, the Visual Basic compiler generates error [BC36551](../../../misc/bc36551.md), "Extension methods can be defined only in modules."</span></span>

4. <span data-ttu-id="b6305-111">Объявите метод обычным способом, за исключением того, что тип первого параметра должен быть типом данных, который требуется расширить.</span><span class="sxs-lookup"><span data-stu-id="b6305-111">Declare your method in the ordinary way, except that the type of the first parameter must be the data type you want to extend.</span></span>

    ```vb
    <Extension()>
    Public Sub SubName(para1 As ExtendedType, <other parameters>)
         ' < Body of the method >
    End Sub
    ```

## <a name="example"></a><span data-ttu-id="b6305-112">Пример</span><span class="sxs-lookup"><span data-stu-id="b6305-112">Example</span></span>

<span data-ttu-id="b6305-113">В следующем примере объявляется метод расширения в модуле `StringExtensions`.</span><span class="sxs-lookup"><span data-stu-id="b6305-113">The following example declares an extension method in module `StringExtensions`.</span></span> <span data-ttu-id="b6305-114">Второй модуль, `Module1`, импортирует `StringExtensions` и вызывает метод.</span><span class="sxs-lookup"><span data-stu-id="b6305-114">A second module, `Module1`, imports `StringExtensions` and calls the method.</span></span> <span data-ttu-id="b6305-115">Метод расширения должен находиться в области видимости при его вызове.</span><span class="sxs-lookup"><span data-stu-id="b6305-115">The extension method must be in scope when it is called.</span></span> <span data-ttu-id="b6305-116">Метод расширения `PrintAndPunctuate` расширяет класс <xref:System.String> с помощью метода, который отображает экземпляр строки, за которым следует строка символов пунктуации, отправленная в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="b6305-116">Extension method `PrintAndPunctuate` extends the <xref:System.String> class with a method that displays the string instance followed by a string of punctuation symbols sent in as a parameter.</span></span>

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

<span data-ttu-id="b6305-117">Обратите внимание, что метод определен с двумя параметрами и вызывается только с одним.</span><span class="sxs-lookup"><span data-stu-id="b6305-117">Notice that the method is defined with two parameters and called with only one.</span></span> <span data-ttu-id="b6305-118">Первый параметр, `aString`, в определении метода привязан к `example`, экземпляр `String`, который вызывает метод.</span><span class="sxs-lookup"><span data-stu-id="b6305-118">The first parameter, `aString`, in the method definition is bound to `example`, the instance of `String` that calls the method.</span></span> <span data-ttu-id="b6305-119">Выходные данные примера могут быть следующими:</span><span class="sxs-lookup"><span data-stu-id="b6305-119">The output of the example is as follows:</span></span>

```console
Hello?
Hello!!!!
```

## <a name="see-also"></a><span data-ttu-id="b6305-120">См. также</span><span class="sxs-lookup"><span data-stu-id="b6305-120">See also</span></span>

- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [<span data-ttu-id="b6305-121">Методы расширения</span><span class="sxs-lookup"><span data-stu-id="b6305-121">Extension Methods</span></span>](extension-methods.md)
- [<span data-ttu-id="b6305-122">Оператор Module</span><span class="sxs-lookup"><span data-stu-id="b6305-122">Module Statement</span></span>](../../../language-reference/statements/module-statement.md)
- [<span data-ttu-id="b6305-123">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="b6305-123">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="b6305-124">Область в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b6305-124">Scope in Visual Basic</span></span>](../declared-elements/scope.md)
