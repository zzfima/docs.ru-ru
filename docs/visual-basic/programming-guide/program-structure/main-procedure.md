---
title: Основная процедура
ms.date: 07/20/2015
f1_keywords:
- vb.Main
helpviewer_keywords:
- Main procedure
- Main method [Visual Basic]
- main function
ms.assetid: f0db283e-f283-4464-b521-b90858cc1b44
ms.openlocfilehash: 61cd397b82b4bb9a8b24a1a7d30eaea68e37368f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347348"
---
# <a name="main-procedure-in-visual-basic"></a>Процедура Main в Visual Basic
Каждое приложение Visual Basic должно содержать процедуру с именем `Main`. Эта процедура выступает в качестве начальной точки и общего управления для приложения. .NET Framework вызывает процедуру `Main`, когда она загрузила приложение и готова передать ему управление. Если вы не создаете Windows Forms приложение, необходимо написать `Main` процедуру для приложений, которые выполняются самостоятельно.

 `Main` содержит код, который выполняется в первую очередь. В `Main`можно определить, какая форма должна загружаться первым при запуске программы, определить, выполняется ли в системе копия приложения, установить набор переменных для приложения или открыть базу данных, требуемую для приложения.

## <a name="requirements-for-the-main-procedure"></a>Требования для основной процедуры
 Файл, который выполняется самостоятельно (обычно с расширением exe), должен содержать процедуру `Main`. Библиотека (например, с расширением DLL) не запускается самостоятельно и не требует `Main` процедуры. Ниже приведены требования к различным типам проектов, которые можно создать.

- Консольные приложения выполняются самостоятельно, и необходимо указать хотя бы одну `Main` процедуру.

- Windows Forms приложения выполняются самостоятельно. Однако компилятор Visual Basic автоматически создает в таком приложении `Main` процедуру, и вам не нужно писать его.

- Библиотеки классов не нуждаются в `Main` процедуре. К ним относятся библиотеки элементов управления Windows и библиотеки веб-элементов управления. Веб-приложения развертываются в виде библиотек классов.

## <a name="declaring-the-main-procedure"></a>Объявление основной процедуры
 Существует четыре способа объявления процедуры `Main`. Он может принимать аргументы, а также не может возвращать значение.

> [!NOTE]
> При объявлении `Main` в классе необходимо использовать ключевое слово `Shared`. В модуле `Main` не нужно `Shared`.

- Самый простой способ — объявить `Sub`ную процедуру, которая не принимает аргументы или возвращает значение.

    ```vb
    Module mainModule
        Sub Main()
            MsgBox("The Main procedure is starting the application.")
            ' Insert call to appropriate starting place in your code.
            MsgBox("The application is terminating.")
        End Sub
    End Module
    ```

- `Main` также может возвращать значение `Integer`, используемое операционной системой в качестве кода выхода для программы. Другие программы могут протестировать этот код, изучая значение ERRORLEVEL Windows. Чтобы получить код выхода, необходимо объявить `Main` в качестве `Function` процедуры, а не `Sub` процедуры.

    ```vb
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

- `Main` также может принимать `String` массив в качестве аргумента. Каждая строка в массиве содержит один из аргументов командной строки, используемых для вызова программы. В зависимости от их значений можно выполнять различные действия.

    ```vb
    Module mainModule
        Function Main(ByVal cmdArgs() As String) As Integer
            MsgBox("The Main procedure is starting the application.")
            Dim returnValue As Integer = 0
            ' See if there are any arguments.
            If cmdArgs.Length > 0 Then
                For argNum As Integer = 0 To UBound(cmdArgs, 1)
                    ' Insert code to examine cmdArgs(argNum) and take
                    ' appropriate action based on its value.
                Next
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

- Можно объявить `Main`, чтобы проверить аргументы командной строки, но не вернуть код выхода, как показано ниже.

    ```vb
    Module mainModule
        Sub Main(ByVal cmdArgs() As String)
            MsgBox("The Main procedure is starting the application.")
            Dim returnValue As Integer = 0
            ' See if there are any arguments.
            If cmdArgs.Length > 0 Then
                For argNum As Integer = 0 To UBound(cmdArgs, 1)
                    ' Insert code to examine cmdArgs(argNum) and take
                    ' appropriate action based on its value.
                Next
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
- [Структура программы Visual Basic](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [-main](../../../visual-basic/reference/command-line-compiler/main.md)
- [Общие](../../../visual-basic/language-reference/modifiers/shared.md)
- [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)
- [Тип данных Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [Тип данных String](../../../visual-basic/language-reference/data-types/string-data-type.md)
