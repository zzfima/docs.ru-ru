---
title: "Процедура Main в Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Main
helpviewer_keywords:
- Main procedure
- Main method [Visual Basic]
- main function
ms.assetid: f0db283e-f283-4464-b521-b90858cc1b44
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 90550ce3e62e4afbc94e2d383fa73db7178633d8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="main-procedure-in-visual-basic"></a>Процедура Main в Visual Basic
Каждое приложение Visual Basic должно содержать процедуру с именем `Main`. Эта процедура служит в качестве начальной точки и общего управления для приложения. Платформа .NET Framework вызывает вашей `Main` процедуру при загрузке приложения и все готово для передачи управления. Если вы создаете приложение Windows Forms, необходимо написать `Main` процедуры для приложений, которые выполняются самостоятельно.  
  
 `Main`содержит код, который выполняется первой. В `Main`, можно определить, какая форма загружается первой при запуске программы, установить, работают ли в системе копии данного приложения, ввести набор переменных для приложения или открыть базу данных, которому требуется приложению.  
  
## <a name="requirements-for-the-main-procedure"></a>Требования для процедуры Main  
 Файл, запускаемый самостоятельно (обычно с расширением .exe) должен содержать `Main` процедуры. Библиотека (например с расширением DLL) не запущена самостоятельно и не требует `Main` процедуры. Ниже приведены требования для различных типов проектов, которые можно создавать:  
  
-   Консольные приложения выполняются самостоятельно, и вы должны предоставить по крайней мере один `Main` процедуры. .  
  
-   Приложения Windows Forms выполняются самостоятельно. Однако компилятор Visual Basic автоматически создает `Main` процедуры таким приложением и не требуется создавать один.  
  
-   Библиотеки классов не требуют `Main` процедуры. Сюда входят библиотеки элементов управления Windows и библиотеки веб-элементов управления. Веб-приложения развертываются как библиотеки классов.  
  
## <a name="declaring-the-main-procedure"></a>Объявление процедуры Main  
 Существует четыре способа объявления `Main` процедуры. Она может принимать аргументы или не и может возвращать значение или нет.  
  
> [!NOTE]
>  При объявлении `Main` в классе, необходимо использовать `Shared` ключевое слово. В модуле `Main` необязательно должен быть `Shared`.  
  
-   Самый простой способ — объявить `Sub` процедуру, которая не принимает аргументы и возвращаемое значение.  
  
    ```  
    Module mainModule  
        Sub Main()  
            MsgBox("The Main procedure is starting the application.")  
            ' Insert call to appropriate starting place in your code.  
            MsgBox("The application is terminating.")  
        End Sub  
    End Module  
    ```  
  
-   `Main`Можно также вернуть `Integer` значение, которое использует операционной системе как код выхода для данной программы. Другие программы можно проверить код с помощью проверки значения Windows ERRORLEVEL. Чтобы вернуть код завершения, необходимо объявить `Main` как `Function` вместо `Sub` процедуры.  
  
    ```  
    Module mainModule  
        Function Main() As Integer  
            MsgBox("The Main procedure is starting the application.")  
            Dim returnValue As Integer = 0  
            ' Insert call to appropriate starting place in your code.  
            ' On return, assign appropriate value to returnValue.  
            ' 0 usually means successful completion.  
            MsgBox("The application is terminating with error level " &  
                 CStr(returnValue) & ".")  
            Return returnValue  
        End Function  
    End Module  
    ```  
  
-   `Main`Можно также воспользоваться `String` массив в качестве аргумента. Каждая строка в массиве содержит один из аргументов командной строки, используемый для вызова данной программы. Можно выполнять различные действия в зависимости от их значения.  
  
    ```  
    Module mainModule  
        Function Main(ByVal cmdArgs() As String) As Integer  
            MsgBox("The Main procedure is starting the application.")  
            Dim returnValue As Integer = 0  
            ' See if there are any arguments.  
            If cmdArgs.Length > 0 Then  
                For argNum As Integer = 0 To UBound(cmdArgs, 1)  
                    ' Insert code to examine cmdArgs(argNum) and take  
                    ' appropriate action based on its value.  
                Next argNum  
            End If  
            ' Insert call to appropriate starting place in your code.  
            ' On return, assign appropriate value to returnValue.  
            ' 0 usually means successful completion.  
            MsgBox("The application is terminating with error level " &  
                 CStr(returnValue) & ".")  
            Return returnValue  
        End Function  
    End Module  
    ```  
  
-   Можно объявить `Main` Проверьте аргументы командной строки, но возвращает код выхода, как показано ниже.  
  
    ```  
    Module mainModule  
        Sub Main(ByVal cmdArgs() As String)  
            MsgBox("The Main procedure is starting the application.")  
            Dim returnValue As Integer = 0  
            ' See if there are any arguments.  
            If cmdArgs.Length > 0 Then  
                For argNum As Integer = 0 To UBound(cmdArgs, 1)  
                    ' Insert code to examine cmdArgs(argNum) and take  
                    ' appropriate action based on its value.  
                Next argNum  
            End If  
            ' Insert call to appropriate starting place in your code.  
            MsgBox("The application is terminating.")  
        End Sub  
    End Module  
    ```  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>  
 <xref:System.Array.Length%2A>  
 <xref:Microsoft.VisualBasic.Information.UBound%2A>  
 [Структура программы Visual Basic](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 [NIB: версия Visual Basic Hello World](http://msdn.microsoft.com/en-us/9d030b60-e148-4366-a462-69532f02294c)  
 [/main](../../../visual-basic/reference/command-line-compiler/main.md)  
 [Общие](../../../visual-basic/language-reference/modifiers/shared.md)  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Тип данных Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [Тип данных String](../../../visual-basic/language-reference/data-types/string-data-type.md)
