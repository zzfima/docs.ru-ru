---
title: Процедура Main в Visual Basic
ms.date: 07/20/2015
f1_keywords:
- vb.Main
helpviewer_keywords:
- Main procedure
- Main method [Visual Basic]
- main function
ms.assetid: f0db283e-f283-4464-b521-b90858cc1b44
ms.openlocfilehash: 641edd2d0e0dde5f509c8fa77ccf65358fa76a31
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58833677"
---
# <a name="main-procedure-in-visual-basic"></a>Процедура Main в Visual Basic
Каждое приложение Visual Basic должен содержать процедура с именем `Main`. Эта процедура служит начальной точкой программы и осуществляющей общее управление для вашего приложения. Платформа .NET Framework вызывает ваш `Main` процедуру при загрузке приложения и все готово для передачи управления. Если вы создаете приложение Windows Forms, необходимо написать `Main` процедуры для приложений, работающих на собственные.  
  
 `Main` содержит код, который выполняется первым. В `Main`, можно определить, какая форма загружается первой при запуске программы, узнать, если копия приложения уже выполняется в системе, ввести набор переменных для приложения или открыть базу данных, которая необходима для приложения.  
  
## <a name="requirements-for-the-main-procedure"></a>Требования для процедуры Main  
 Файл, который запускается сам по себе (обычно с расширением .exe) должен содержать `Main` процедуры. Библиотека (например с расширением .dll) не работает на собственный и не требует `Main` процедуры. Далее приведены требования для различных типов проектов, которые можно создать.  
  
-   Консольные приложения выполняются самостоятельно, и необходимо указать по крайней мере `Main` процедуры. .  
  
-   Приложения Windows Forms выполняются самостоятельно. Тем не менее, компилятор Visual Basic автоматически создает `Main` процедуры таким приложением и не обязательно должны написать.  
  
-   Библиотеки классов не требуют `Main` процедуры. Сюда входят библиотеки элементов управления Windows и библиотеки управления Web. Веб-приложения развертываются как библиотеки классов.  
  
## <a name="declaring-the-main-procedure"></a>Объявление процедуры Main  
 Существуют четыре способа объявления `Main` процедуры. Он может принимать аргументы, или нет и она может возвращать значение, или нет.  
  
> [!NOTE]
>  При объявлении `Main` в классе, необходимо использовать `Shared` ключевое слово. В модуле `Main` не нужно быть `Shared`.  
  
-   Проще всего объявить `Sub` процедуру, которая не принимает аргументы и возвращать значение.  
  
    ```  
    Module mainModule  
        Sub Main()  
            MsgBox("The Main procedure is starting the application.")  
            ' Insert call to appropriate starting place in your code.  
            MsgBox("The application is terminating.")  
        End Sub  
    End Module  
    ```  
  
-   `Main` также может возвращать `Integer` значение, которое операционная система использует как код выхода программы. Другие программы можно проверить этот код, путем проверки значения Windows ERRORLEVEL. Чтобы вернуть код завершения, необходимо объявить `Main` как `Function` вместо `Sub` процедуры.  
  
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
  
-   `Main` Можно также воспользоваться `String` массива в качестве аргумента. Каждая строка в массиве содержит один из аргументов командной строки, используемые для вызова программы. Можно выполнять разные действия в зависимости от их значения.  
  
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
  
-   Можно объявить `Main` аргументы командной строки, но возвращает код выхода, как показано ниже.  
  
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

- <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>
- <xref:System.Array.Length%2A>
- <xref:Microsoft.VisualBasic.Information.UBound%2A>
- [Структура программы на Visual Basic](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [/main](../../../visual-basic/reference/command-line-compiler/main.md)
- [Общие](../../../visual-basic/language-reference/modifiers/shared.md)
- [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)
- [Тип данных Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [Тип данных String](../../../visual-basic/language-reference/data-types/string-data-type.md)
