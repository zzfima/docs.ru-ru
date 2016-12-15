---
title: "Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "типы данных [Visual Basic], числовой"
  - "типы данных [Visual Basic], беззнаковый"
  - "типы данных [Visual Basic], использование"
  - "функции [Visual Basic], вызов функций Windows"
  - "UInteger - тип данных, использование"
  - "тип данных ULong, использование"
  - "беззнаковый тип данных"
  - "беззнаковые типы"
  - "беззнаковые типы, использование"
  - "UShort - тип данных, использование"
  - "функции Windows, вызов"
ms.assetid: c2c0e712-8dc2-43b9-b4c6-345fbb02e7ce
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

При использовании класса, модуля или структуры, имеющих члены беззнаковых целых типов, можно получить доступ к этим членам с помощью [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
### Для вызова функции Windows, которая принимает беззнаковый тип  
  
1.  Используйте [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md), чтобы сообщить [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], какая из библиотек содержит функцию с данным именем, какова последовательность вызова, и как преобразовать строки при её вызове.  
  
2.  В инструкции `Declare` используйте `UInteger`, `ULong`, `UShort` или `Byte` соответственно для каждого параметра с беззнаковым типом.  
  
3.  Обратитесь к документации вызываемой функции Windows для поиска имен и значений констант, которые она использует.  Многие из них определены в файле WinUser.h.  
  
4.  Объявите необходимые константы в коде программы.  Многие константы Windows \- 32\-разрядные беззнаковые значения, их следует объявлять как `As` `UInteger`.  
  
5.  Вызовите функцию обычным образом.  В следующем примере вызывается Windows функция `MessageBox`, которая принимает беззнаковое целое число в качестве аргумента.  
  
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
  
     Можно проверить функцию `messageThroughWindows` с помощью следующего кода.  
  
    ```  
    Public Sub consumeWindowsMessage()  
        Dim w As New windowsMessage  
        w.messageThroughWindows()  
    End Sub  
    ```  
  
    > [!CAUTION]
    >  Типы данных `UInteger`, `ULong`, `UShort` и `SByte` не являются частью [Независимость от языка и независимые от языка компоненты](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\), поэтому CLS\-совместимый код не может использовать компонент, который использует их.  
  
    > [!IMPORTANT]
    >  Создание вызова неуправляемого кода, такого как программного интерфейса приложения \(API\), подвергает ваш код потенциальной опасности.  
  
    > [!IMPORTANT]
    >  Вызов Windows API требует разрешения неуправляемого кода, которое может повлиять на его выполнение в случаях частичного доверия.  Дополнительные сведения см. в разделах <xref:System.Security.Permissions.SecurityPermission> и [Code Access Permissions](http://msdn.microsoft.com/ru-ru/e5ae402f-6dda-4732-bbe8-77296630f675).  
  
## См. также  
 [Типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Тип данных Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)   
 [Тип данных UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)   
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Пошаговое руководство. Вызов API Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)