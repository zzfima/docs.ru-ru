---
title: Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа
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
ms.openlocfilehash: 790c680744e2100a40a7cea8b8cef80c68d586bb
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348734"
---
# <a name="how-to-call-a-windows-function-that-takes-unsigned-types-visual-basic"></a>Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа (Visual Basic)

При использовании класса, модуля или структуры, имеющей члены целочисленных типов без знака, можно получить доступ к этим членам с помощью Visual Basic.

## <a name="to-call-a-windows-function-that-takes-an-unsigned-type"></a>Вызов функции Windows, которая принимает неподписанный тип

1. Используйте [инструкцию Declare](../../../visual-basic/language-reference/statements/declare-statement.md) , чтобы сообщить Visual Basic, какая библиотека содержит функцию, ее имя в этой библиотеке, последовательность вызова и способ преобразования строк при вызове.

2. В инструкции `Declare` используйте `UInteger`, `ULong`, `UShort`или `Byte` соответственно для каждого параметра с типом без знака.

3. Обратитесь к документации по функции Windows, которую вы вызываете, чтобы найти имена и значения используемых констант. Многие из них определены в файле WinUser. h.

4. Объявите необходимые константы в коде. Многие константы Windows представляют собой 32-разрядные значения без знака, и их следует объявлять как `As UInteger`.

5. Вызовите функцию обычным образом. В следующем примере вызывается функция Windows `MessageBox`, которая принимает беззнаковый целочисленный аргумент.

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

     Вы можете протестировать функцию `messageThroughWindows` с помощью следующего кода.

    ```vb
    Public Sub consumeWindowsMessage()
        Dim w As New windowsMessage
        w.messageThroughWindows()
    End Sub
    ```

    > [!CAUTION]
    > Типы данных `UInteger`, `ULong`, `UShort`и `SByte` не являются частью [независимость от языка и независимых от языка компонентов](../../../standard/language-independence-and-language-independent-components.md) (CLS), поэтому CLS-совместимый код не может использовать компонент, который их использует.

    > [!IMPORTANT]
    > Вызов неуправляемого кода, например программного интерфейса Windows (API), предоставляет ваш код потенциальным угрозам безопасности.

    > [!IMPORTANT]
    > Для вызова API Windows требуется разрешение неуправляемого кода, которое может повлиять на его выполнение в ситуациях частичного доверия. Дополнительные сведения см. в разделе <xref:System.Security.Permissions.SecurityPermission> и [разрешения на доступ к коду](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/h846e9b3(v=vs.100)).

## <a name="see-also"></a>См. также

- [Типы данных](../../../visual-basic/language-reference/data-types/index.md)
- [Тип данных Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [Тип данных UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)
- [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)
- [Пошаговое руководство. Вызов API-интерфейсов Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
