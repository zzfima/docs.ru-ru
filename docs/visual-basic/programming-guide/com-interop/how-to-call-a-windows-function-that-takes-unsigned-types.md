---
title: Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Windows functions [Visual Basic], calling
- unsigned data types [Visual Basic]
- UShort data type [Visual Basic], using
- functions [Visual Basic], calling Windows functions
- ULong data type [Visual Basic], using
- UInteger data type [Visual Basic], using
- data types [Visual Basic], using
- unsigned types [Visual Basic]
- data types [Visual Basic], unsigned
- data types [Visual Basic], numeric
- unsigned types [Visual Basic], using
ms.assetid: c2c0e712-8dc2-43b9-b4c6-345fbb02e7ce
ms.openlocfilehash: d1a679242f89c17e58a837ac2d356e1594972fb3
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57374561"
---
# <a name="how-to-call-a-windows-function-that-takes-unsigned-types-visual-basic"></a>Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа (Visual Basic)

При использовании класса, модуля или структура, которая содержит члены типов целое число без знака, можно получить доступ к этим членам с помощью Visual Basic.

### <a name="to-call-a-windows-function-that-takes-an-unsigned-type"></a>Для вызова функции Windows, принимающей тип без знака

1. Используйте [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) сообщить Visual Basic, какая из библиотек содержит функцию его имя, что последовательность вызова и как преобразовать строки, при его вызове.

2. В `Declare` выражение use `UInteger`, `ULong`, `UShort`, или `Byte` соответствующим образом для каждого параметра с типом без знака.

3. См. в документации для функции Windows, чтобы найти имена и значения констант, используемых при вызове. Многие из них определяются в файле WinUser.h.

4. Объявите необходимые константы в коде. Многие константы Windows-32-разрядных неподписанных значений, их следует объявлять `As UInteger`.

5. Вызовите функцию обычным способом. В следующем примере вызывается функция Windows `MessageBox`, который принимает в качестве аргумента целого числа без знака.

    ```vb
    Public Class windowsMessage
        Private Declare Auto Function mb Lib "user32.dll" Alias "MessageBox" (
            ByVal hWnd As Integer,
            ByVal lpText As String,
            ByVal lpCaption As String,
            ByVal uType As UInteger) As Integer
        Private Const MB_OK As UInteger = 0
        Private Const MB_ICONEXCLAMATION As UInteger = &H30
        Private Const IDOK As UInteger = 1
        Private Const IDCLOSE As UInteger = 8
        Private Const c As UInteger = MB_OK Or MB_ICONEXCLAMATION
        Public Function messageThroughWindows() As String
            Dim r As Integer = mb(0, "Click OK if you see this!",
                "Windows API call", c)
            Dim s As String = "Windows API MessageBox returned " &
                 CStr(r)& vbCrLf & "(IDOK = " & CStr(IDOK) &
                 ", IDCLOSE = " & CStr(IDCLOSE) & ")"
            Return s
        End Function
    End Class
    ```

     Можно протестировать функцию `messageThroughWindows` следующим кодом.

    ```vb
    Public Sub consumeWindowsMessage()
        Dim w As New windowsMessage
        w.messageThroughWindows()
    End Sub
    ```

    > [!CAUTION]
    > `UInteger`, `ULong`, `UShort`, И `SByte` типы данных не являются частью [независимость от языка и независимые от языка компоненты](../../../standard/language-independence-and-language-independent-components.md) (CLS), поэтому CLS-совместимого кода нельзя использовать компонент, который они используются.

    > [!IMPORTANT]
    > Вызов неуправляемого кода, таких как интерфейс (API), Windows предоставляет код, чтобы потенциальные угрозы безопасности.

    > [!IMPORTANT]
    > Вызов Windows API требует разрешение неуправляемого кода, которое может повлиять на выполнение в ситуациях частичного доверия. Дополнительные сведения см. в разделе <xref:System.Security.Permissions.SecurityPermission> и [разрешений доступа к коду](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/h846e9b3(v=vs.100)).

## <a name="see-also"></a>См. также

- [Типы данных](../../../visual-basic/language-reference/data-types/index.md)
- [Тип данных Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [Тип данных UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)
- [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)
- [Пошаговое руководство: Вызов API Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
