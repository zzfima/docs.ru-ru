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
# <a name="main-procedure-in-visual-basic"></a><span data-ttu-id="26c5f-102">Процедура Main в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="26c5f-102">Main Procedure in Visual Basic</span></span>
<span data-ttu-id="26c5f-103">Каждое приложение Visual Basic должно содержать процедуру с именем `Main`.</span><span class="sxs-lookup"><span data-stu-id="26c5f-103">Every Visual Basic application must contain a procedure called `Main`.</span></span> <span data-ttu-id="26c5f-104">Эта процедура служит в качестве начальной точки и общего управления для приложения.</span><span class="sxs-lookup"><span data-stu-id="26c5f-104">This procedure serves as the starting point and overall control for your application.</span></span> <span data-ttu-id="26c5f-105">Платформа .NET Framework вызывает вашей `Main` процедуру при загрузке приложения и все готово для передачи управления.</span><span class="sxs-lookup"><span data-stu-id="26c5f-105">The .NET Framework calls your `Main` procedure when it has loaded your application and is ready to pass control to it.</span></span> <span data-ttu-id="26c5f-106">Если вы создаете приложение Windows Forms, необходимо написать `Main` процедуры для приложений, которые выполняются самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="26c5f-106">Unless you are creating a Windows Forms application, you must write the `Main` procedure for applications that run on their own.</span></span>  
  
 <span data-ttu-id="26c5f-107">`Main`содержит код, который выполняется первой.</span><span class="sxs-lookup"><span data-stu-id="26c5f-107">`Main` contains the code that runs first.</span></span> <span data-ttu-id="26c5f-108">В `Main`, можно определить, какая форма загружается первой при запуске программы, установить, работают ли в системе копии данного приложения, ввести набор переменных для приложения или открыть базу данных, которому требуется приложению.</span><span class="sxs-lookup"><span data-stu-id="26c5f-108">In `Main`, you can determine which form is to be loaded first when the program starts, find out if a copy of your application is already running on the system, establish a set of variables for your application, or open a database that the application requires.</span></span>  
  
## <a name="requirements-for-the-main-procedure"></a><span data-ttu-id="26c5f-109">Требования для процедуры Main</span><span class="sxs-lookup"><span data-stu-id="26c5f-109">Requirements for the Main Procedure</span></span>  
 <span data-ttu-id="26c5f-110">Файл, запускаемый самостоятельно (обычно с расширением .exe) должен содержать `Main` процедуры.</span><span class="sxs-lookup"><span data-stu-id="26c5f-110">A file that runs on its own (usually with extension .exe) must contain a `Main` procedure.</span></span> <span data-ttu-id="26c5f-111">Библиотека (например с расширением DLL) не запущена самостоятельно и не требует `Main` процедуры.</span><span class="sxs-lookup"><span data-stu-id="26c5f-111">A library (for example with extension .dll) does not run on its own and does not require a `Main` procedure.</span></span> <span data-ttu-id="26c5f-112">Ниже приведены требования для различных типов проектов, которые можно создавать:</span><span class="sxs-lookup"><span data-stu-id="26c5f-112">The requirements for the different types of projects you can create are as follows:</span></span>  
  
-   <span data-ttu-id="26c5f-113">Консольные приложения выполняются самостоятельно, и вы должны предоставить по крайней мере один `Main` процедуры.</span><span class="sxs-lookup"><span data-stu-id="26c5f-113">Console applications run on their own, and you must supply at least one `Main` procedure.</span></span> <span data-ttu-id="26c5f-114">.</span><span class="sxs-lookup"><span data-stu-id="26c5f-114">.</span></span>  
  
-   <span data-ttu-id="26c5f-115">Приложения Windows Forms выполняются самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="26c5f-115">Windows Forms applications run on their own.</span></span> <span data-ttu-id="26c5f-116">Однако компилятор Visual Basic автоматически создает `Main` процедуры таким приложением и не требуется создавать один.</span><span class="sxs-lookup"><span data-stu-id="26c5f-116">However, the Visual Basic compiler automatically generates a `Main` procedure in such an application, and you do not need to write one.</span></span>  
  
-   <span data-ttu-id="26c5f-117">Библиотеки классов не требуют `Main` процедуры.</span><span class="sxs-lookup"><span data-stu-id="26c5f-117">Class libraries do not require a `Main` procedure.</span></span> <span data-ttu-id="26c5f-118">Сюда входят библиотеки элементов управления Windows и библиотеки веб-элементов управления.</span><span class="sxs-lookup"><span data-stu-id="26c5f-118">These include Windows Control Libraries and Web Control Libraries.</span></span> <span data-ttu-id="26c5f-119">Веб-приложения развертываются как библиотеки классов.</span><span class="sxs-lookup"><span data-stu-id="26c5f-119">Web applications are deployed as class libraries.</span></span>  
  
## <a name="declaring-the-main-procedure"></a><span data-ttu-id="26c5f-120">Объявление процедуры Main</span><span class="sxs-lookup"><span data-stu-id="26c5f-120">Declaring the Main Procedure</span></span>  
 <span data-ttu-id="26c5f-121">Существует четыре способа объявления `Main` процедуры.</span><span class="sxs-lookup"><span data-stu-id="26c5f-121">There are four ways to declare the `Main` procedure.</span></span> <span data-ttu-id="26c5f-122">Она может принимать аргументы или не и может возвращать значение или нет.</span><span class="sxs-lookup"><span data-stu-id="26c5f-122">It can take arguments or not, and it can return a value or not.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="26c5f-123">При объявлении `Main` в классе, необходимо использовать `Shared` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="26c5f-123">If you declare `Main` in a class, you must use the `Shared` keyword.</span></span> <span data-ttu-id="26c5f-124">В модуле `Main` необязательно должен быть `Shared`.</span><span class="sxs-lookup"><span data-stu-id="26c5f-124">In a module, `Main` does not need to be `Shared`.</span></span>  
  
-   <span data-ttu-id="26c5f-125">Самый простой способ — объявить `Sub` процедуру, которая не принимает аргументы и возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="26c5f-125">The simplest way is to declare a `Sub` procedure that does not take arguments or return a value.</span></span>  
  
    ```  
    Module mainModule  
        Sub Main()  
            MsgBox("The Main procedure is starting the application.")  
            ' Insert call to appropriate starting place in your code.  
            MsgBox("The application is terminating.")  
        End Sub  
    End Module  
    ```  
  
-   <span data-ttu-id="26c5f-126">`Main`Можно также вернуть `Integer` значение, которое использует операционной системе как код выхода для данной программы.</span><span class="sxs-lookup"><span data-stu-id="26c5f-126">`Main` can also return an `Integer` value, which the operating system uses as the exit code for your program.</span></span> <span data-ttu-id="26c5f-127">Другие программы можно проверить код с помощью проверки значения Windows ERRORLEVEL.</span><span class="sxs-lookup"><span data-stu-id="26c5f-127">Other programs can test this code by examining the Windows ERRORLEVEL value.</span></span> <span data-ttu-id="26c5f-128">Чтобы вернуть код завершения, необходимо объявить `Main` как `Function` вместо `Sub` процедуры.</span><span class="sxs-lookup"><span data-stu-id="26c5f-128">To return an exit code, you must declare `Main` as a `Function` procedure instead of a `Sub` procedure.</span></span>  
  
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
  
-   <span data-ttu-id="26c5f-129">`Main`Можно также воспользоваться `String` массив в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="26c5f-129">`Main` can also take a `String` array as an argument.</span></span> <span data-ttu-id="26c5f-130">Каждая строка в массиве содержит один из аргументов командной строки, используемый для вызова данной программы.</span><span class="sxs-lookup"><span data-stu-id="26c5f-130">Each string in the array contains one of the command-line arguments used to invoke your program.</span></span> <span data-ttu-id="26c5f-131">Можно выполнять различные действия в зависимости от их значения.</span><span class="sxs-lookup"><span data-stu-id="26c5f-131">You can take different actions depending on their values.</span></span>  
  
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
  
-   <span data-ttu-id="26c5f-132">Можно объявить `Main` Проверьте аргументы командной строки, но возвращает код выхода, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="26c5f-132">You can declare `Main` to examine the command-line arguments but not return an exit code, as follows.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="26c5f-133">См. также</span><span class="sxs-lookup"><span data-stu-id="26c5f-133">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>  
 <xref:System.Array.Length%2A>  
 <xref:Microsoft.VisualBasic.Information.UBound%2A>  
 [<span data-ttu-id="26c5f-134">Структура программы Visual Basic</span><span class="sxs-lookup"><span data-stu-id="26c5f-134">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 [<span data-ttu-id="26c5f-135">NIB: версия Visual Basic Hello World</span><span class="sxs-lookup"><span data-stu-id="26c5f-135">NIB: Visual Basic Version of Hello, World</span></span>](http://msdn.microsoft.com/en-us/9d030b60-e148-4366-a462-69532f02294c)  
 [<span data-ttu-id="26c5f-136">/main</span><span class="sxs-lookup"><span data-stu-id="26c5f-136">/main</span></span>](../../../visual-basic/reference/command-line-compiler/main.md)  
 [<span data-ttu-id="26c5f-137">Общие</span><span class="sxs-lookup"><span data-stu-id="26c5f-137">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)  
 [<span data-ttu-id="26c5f-138">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="26c5f-138">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="26c5f-139">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="26c5f-139">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="26c5f-140">Тип данных Integer</span><span class="sxs-lookup"><span data-stu-id="26c5f-140">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [<span data-ttu-id="26c5f-141">Тип данных String</span><span class="sxs-lookup"><span data-stu-id="26c5f-141">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)
