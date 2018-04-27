---
title: Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: dd0738300ec846041e78f19836f29e7adff1c821
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-call-a-windows-function-that-takes-unsigned-types-visual-basic"></a>Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа (Visual Basic)
При использовании класса, модуля или структуры, имеющих члены беззнаковых целых типов можно получить доступ к этим членам с помощью Visual Basic.  
  
### <a name="to-call-a-windows-function-that-takes-an-unsigned-type"></a>Для вызова функции Windows, которая принимает тип без знака  
  
1.  Используйте [инструкции Declare](../../../visual-basic/language-reference/statements/declare-statement.md) нужно сообщить Visual Basic, какая из библиотек содержит функцию его имя, что последовательность вызова и как преобразовать строки при его вызове.  
  
2.  В `Declare` инструкции, используйте `UInteger`, `ULong`, `UShort`, или `Byte` соответствующим образом для каждого параметра с типом без знака.  
  
3.  Обратитесь к документации для вызова, чтобы найти имена и значения констант, которые он использует функции Windows. Многие из них определены в файле WinUser.h.  
  
4.  Объявите необходимые константы в коде. Многие константы Windows-32-разрядных беззнаковых значений и следует объявлять `As``UInteger`.  
  
5.  Вызовите функцию обычным способом. В следующем примере вызывается функция Windows `MessageBox`, которая принимает аргументы целое число без знака.  
  
    ```  
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
  
     Можно проверить функцию `messageThroughWindows` следующим кодом.  
  
    ```  
    Public Sub consumeWindowsMessage()  
        Dim w As New windowsMessage  
        w.messageThroughWindows()  
    End Sub  
    ```  
  
    > [!CAUTION]
    >  `UInteger`, `ULong`, `UShort`, И `SByte` типы данных не являются частью [независимость от языка и независимые от языка компоненты](../../../standard/language-independence-and-language-independent-components.md) (CLS), поэтому CLS-совместимом коде нельзя использовать компонент, который они используются.  
  
    > [!IMPORTANT]
    >  Вызов неуправляемого кода, такие как интерфейс (API), Windows предоставляет код, чтобы потенциальные угрозы безопасности.  
  
    > [!IMPORTANT]
    >  Вызов Windows API требует разрешение неуправляемого кода, что может повлиять на его выполнение в случаях частичного доверия. Дополнительные сведения см. в разделе <xref:System.Security.Permissions.SecurityPermission> и [разрешений доступа к коду](http://msdn.microsoft.com/library/e5ae402f-6dda-4732-bbe8-77296630f675).  
  
## <a name="see-also"></a>См. также  
 [Типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Тип данных Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [Тип данных UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [Пошаговое руководство. Вызов API-интерфейсов Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
