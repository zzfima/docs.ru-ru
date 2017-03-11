---
title: "Процедура Main в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Main"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "main - функция"
  - "Main - метод [Visual Basic]"
  - "Main - процедура"
ms.assetid: f0db283e-f283-4464-b521-b90858cc1b44
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Процедура Main в Visual Basic
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Каждое приложение Visual Basic должно содержать процедуру с именем `Main`.  Эта процедура служит начальной точкой программы и осуществляет общее управление работой приложения.  Платформа .NET Framework вызывает процедуру `Main` при загрузке приложения и готовности передачи управления.  При создании приложения Windows Forms для приложений, которые выполняются самостоятельно, необходимо написать процедуру `Main`.  
  
 `Main` содержит код, который будет выполняться в первую очередь.  В процедуре `Main` пользователь может определить, какая форма загружается первой при запуске программы, установить, работают ли в системе копии данного приложения, ввести набор переменных для приложения или открыть необходимую для приложения базу данных.  
  
## Требования для процедуры Main  
 Файл, запускаемый самостоятельно \(обычно с расширением .exe\), должен содержать процедуру `Main`.  Библиотека \(например с расширением .dll\) не может быть запущена самостоятельно и не требует процедуры `Main`.  Ниже приведены требования для различных типов проектов, которые можно создать:  
  
-   Консольные приложения выполняются самостоятельно. Необходимо указать по крайней мере одну процедуру `Main`.  .  
  
-   Приложения Windows Forms выполняются самостоятельно.  В то же время компилятор Visual Basic в таких приложениях создает процедуру `Main` автоматически, и поэтому ее не требуется создавать.  
  
-   Библиотеки классов не требуют процедуры `Main`.  В это число входят библиотеки элементов управления Windows и библиотеки веб\-элементов управления.  Веб\-приложения развертываются как библиотеки классов.  
  
## Объявление процедуры Main  
 Существуют четыре способа объявления процедуры `Main`.  Она может принимать аргументы или не принимать их, а также может возвращать или не возвращать значение.  
  
> [!NOTE]
>  Если `Main` объявляется в классе, то необходимо использовать ключевое слово `Shared`.  В модуле нет необходимости объявлять `Main` с ключевым словом `Shared`.  
  
-   Проще всего объявить процедуру `Sub`, не принимающую аргументы и не возвращающую значение.  
  
    ```  
    Module mainModule  
        Sub Main()  
            MsgBox("The Main procedure is starting the application.")  
            ' Insert call to appropriate starting place in your code.  
            MsgBox("The application is terminating.")  
        End Sub  
    End Module  
    ```  
  
-   `Main` может также возвращать значение типа `Integer`, которое операционная система использует в качестве кода выхода для данной программы.  Другие программы могут сверять этот код путем проверки значения Windows ERRORLEVEL.   Чтобы вернуть код завершения, необходимо объявить `Main` как `Function` вместо `Sub`.  
  
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
  
-   `Main` может также в качестве аргумента получать массив `String`.  В этом массиве каждая строка содержит один из аргументов командной строки, используемых для вызова данной программы.  В зависимости от задаваемых им значений могут быть предприняты различные действия.  
  
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
  
-   Объявленная следующим образом процедура `Main` будет проверять аргументы командной строки, не возвращая код выхода:  
  
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
  
## См. также  
 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>   
 <xref:System.Array.Length%2A>   
 <xref:Microsoft.VisualBasic.Information.UBound%2A>   
 [Структура программы Visual Basic](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)   
 ["Hello, World", версия на языке Visual Basic](http://msdn.microsoft.com/ru-ru/9d030b60-e148-4366-a462-69532f02294c)   
 [\/main](../../../visual-basic/reference/command-line-compiler/main.md)   
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)   
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Тип данных Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)   
 [Тип данных String](../../../visual-basic/language-reference/data-types/string-data-type.md)