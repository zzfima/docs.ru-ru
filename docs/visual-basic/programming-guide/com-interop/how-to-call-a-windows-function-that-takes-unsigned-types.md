---
title: "Практическое руководство: вызов функции Windows, принимающей значение беззнакового типа (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Windows functions, calling
- unsigned data types
- UShort data type, using
- functions [Visual Basic], calling Windows functions
- ULong data type, using
- UInteger data type, using
- data types [Visual Basic], using
- unsigned types
- data types [Visual Basic], unsigned
- data types [Visual Basic], numeric
- unsigned types, using
ms.assetid: c2c0e712-8dc2-43b9-b4c6-345fbb02e7ce
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: fbff07f4923b0633a2bc9b4fd558d9d51f64370a
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-call-a-windows-function-that-takes-unsigned-types-visual-basic"></a>Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа (Visual Basic)
При использовании класса, модуля или структуры, имеющих члены беззнаковых целых типов, доступ к этим членам с помощью [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
### <a name="to-call-a-windows-function-that-takes-an-unsigned-type"></a>Для вызова функции Windows, которая принимает тип без знака  
  
1.  Используйте [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) сообщить [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] библиотеку, в которой содержится функция его имя, что последовательность вызова и как преобразовать строки при его вызове.  
  
2.  В `Declare` инструкции, используйте `UInteger`, `ULong`, `UShort`, или `Byte` соответствующим образом для каждого параметра с типом без знака.  
  
3.  Обратитесь к документации Windows функции, вызываемой для поиска имен и значений констант, которые он использует. Многие из них определены в файле WinUser.h.  
  
4.  Объявите необходимые константы в коде. Многие константы Windows-32-разрядные беззнаковые значения, их следует объявлять эти `As``UInteger`.  
  
5.  Вызовите функцию обычным образом. В следующем примере вызывается функция Windows `MessageBox`, который принимает в качестве аргумента целое число без знака.  
  
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
    >  `UInteger`, `ULong`, `UShort`, И `SByte` типы данных не являются частью [независимость от языка и независимые от языка компоненты](https://msdn.microsoft.com/library/12a7a7h3) (CLS), поэтому в CLS-совместимом коде нельзя использовать компонент, который использует их.  
  
    > [!IMPORTANT]
    >  Вызов неуправляемого кода, такие как интерфейс (API) Windows подвергает ваш код потенциальной опасности.  
  
    > [!IMPORTANT]
    >  Вызов Windows API требует разрешение неуправляемого кода, что может повлиять на его выполнение в случаях частичного доверия. Дополнительные сведения см. в разделе <xref:System.Security.Permissions.SecurityPermission>и [разрешений доступа к коду](http://msdn.microsoft.com/en-us/e5ae402f-6dda-4732-bbe8-77296630f675).</xref:System.Security.Permissions.SecurityPermission>  
  
## <a name="see-also"></a>См. также  
 [Типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Целочисленный тип данных](../../../visual-basic/language-reference/data-types/integer-data-type.md)   
 [Тип данных UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)   
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Пошаговое руководство. Вызов API-интерфейсов Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
