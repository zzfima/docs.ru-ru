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
# <a name="how-to-write-an-extension-method-visual-basic"></a>Практическое руководство. Написание метода расширения (Visual Basic)

Методы расширения позволяют добавлять методы в существующий класс. Метод расширения можно вызвать так, как если бы он был экземпляром этого класса.

### <a name="to-define-an-extension-method"></a>Определение метода расширения

1. Откройте новое или существующее приложение Visual Basic в Visual Studio.

2. В верхней части файла, в котором нужно определить метод расширения, включите следующую инструкцию импорта:

    ```vb
    Imports System.Runtime.CompilerServices
    ```

3. В модуле в новом или существующем приложении приступите к определению метода с помощью атрибута [`<Extension>`](xref:System.Runtime.CompilerServices.ExtensionAttribute) :

    ```vb
    <Extension()>
    ```

    Обратите внимание, что атрибут `Extension` можно применить только к методу (`Sub` или процедуре `Function`) в [модуле](../../../language-reference/statements/module-statement.md)Visual Basic. Если применить его к методу в `Class` или `Structure`, компилятор Visual Basic создает ошибку [BC36551](../../../misc/bc36551.md), "методы расширения могут быть определены только в модулях".

4. Объявите метод обычным способом, за исключением того, что тип первого параметра должен быть типом данных, который требуется расширить.

    ```vb
    <Extension()>
    Public Sub SubName(para1 As ExtendedType, <other parameters>)
         ' < Body of the method >
    End Sub
    ```

## <a name="example"></a>Пример

В следующем примере объявляется метод расширения в модуле `StringExtensions`. Второй модуль, `Module1`, импортирует `StringExtensions` и вызывает метод. Метод расширения должен находиться в области видимости при его вызове. Метод расширения `PrintAndPunctuate` расширяет класс <xref:System.String> с помощью метода, который отображает экземпляр строки, за которым следует строка символов пунктуации, отправленная в качестве параметра.

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

Обратите внимание, что метод определен с двумя параметрами и вызывается только с одним. Первый параметр, `aString`, в определении метода привязан к `example`, экземпляр `String`, который вызывает метод. Выходные данные примера могут быть следующими:

```console
Hello?
Hello!!!!
```

## <a name="see-also"></a>См. также

- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [Методы расширения](extension-methods.md)
- [Оператор Module](../../../language-reference/statements/module-statement.md)
- [Параметры и аргументы процедуры](procedure-parameters-and-arguments.md)
- [Область в Visual Basic](../declared-elements/scope.md)
