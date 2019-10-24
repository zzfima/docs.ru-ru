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
ms.openlocfilehash: 1c76e3ade0b383727c3241fdaf5ae44b677559c8
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775696"
---
# <a name="main-procedure-in-visual-basic"></a><span data-ttu-id="dece1-102">Процедура Main в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dece1-102">Main Procedure in Visual Basic</span></span>
<span data-ttu-id="dece1-103">Каждое приложение Visual Basic должно содержать процедуру с именем `Main`.</span><span class="sxs-lookup"><span data-stu-id="dece1-103">Every Visual Basic application must contain a procedure called `Main`.</span></span> <span data-ttu-id="dece1-104">Эта процедура выступает в качестве начальной точки и общего управления для приложения.</span><span class="sxs-lookup"><span data-stu-id="dece1-104">This procedure serves as the starting point and overall control for your application.</span></span> <span data-ttu-id="dece1-105">.NET Framework вызывает процедуру `Main`, когда она загрузила приложение и готова передать ему управление.</span><span class="sxs-lookup"><span data-stu-id="dece1-105">The .NET Framework calls your `Main` procedure when it has loaded your application and is ready to pass control to it.</span></span> <span data-ttu-id="dece1-106">Если вы не создаете Windows Forms приложение, необходимо написать `Main` процедуру для приложений, которые выполняются самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="dece1-106">Unless you are creating a Windows Forms application, you must write the `Main` procedure for applications that run on their own.</span></span>

 <span data-ttu-id="dece1-107">`Main` содержит код, который выполняется в первую очередь.</span><span class="sxs-lookup"><span data-stu-id="dece1-107">`Main` contains the code that runs first.</span></span> <span data-ttu-id="dece1-108">В `Main` можно определить, какая форма должна загружаться первым при запуске программы, определить, выполняется ли в системе копия приложения, установить набор переменных для приложения или открыть базу данных, требуемую для приложения.</span><span class="sxs-lookup"><span data-stu-id="dece1-108">In `Main`, you can determine which form is to be loaded first when the program starts, find out if a copy of your application is already running on the system, establish a set of variables for your application, or open a database that the application requires.</span></span>

## <a name="requirements-for-the-main-procedure"></a><span data-ttu-id="dece1-109">Требования для основной процедуры</span><span class="sxs-lookup"><span data-stu-id="dece1-109">Requirements for the Main Procedure</span></span>
 <span data-ttu-id="dece1-110">Файл, который выполняется самостоятельно (обычно с расширением exe), должен содержать процедуру `Main`.</span><span class="sxs-lookup"><span data-stu-id="dece1-110">A file that runs on its own (usually with extension .exe) must contain a `Main` procedure.</span></span> <span data-ttu-id="dece1-111">Библиотека (например, с расширением DLL) не запускается самостоятельно и не требует `Main` процедуры.</span><span class="sxs-lookup"><span data-stu-id="dece1-111">A library (for example with extension .dll) does not run on its own and does not require a `Main` procedure.</span></span> <span data-ttu-id="dece1-112">Ниже приведены требования к различным типам проектов, которые можно создать.</span><span class="sxs-lookup"><span data-stu-id="dece1-112">The requirements for the different types of projects you can create are as follows:</span></span>

- <span data-ttu-id="dece1-113">Консольные приложения выполняются самостоятельно, и необходимо указать хотя бы одну `Main` процедуру.</span><span class="sxs-lookup"><span data-stu-id="dece1-113">Console applications run on their own, and you must supply at least one `Main` procedure.</span></span>

- <span data-ttu-id="dece1-114">Windows Forms приложения выполняются самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="dece1-114">Windows Forms applications run on their own.</span></span> <span data-ttu-id="dece1-115">Однако компилятор Visual Basic автоматически создает в таком приложении `Main` процедуру, и вам не нужно писать его.</span><span class="sxs-lookup"><span data-stu-id="dece1-115">However, the Visual Basic compiler automatically generates a `Main` procedure in such an application, and you do not need to write one.</span></span>

- <span data-ttu-id="dece1-116">Библиотеки классов не нуждаются в `Main` процедуре.</span><span class="sxs-lookup"><span data-stu-id="dece1-116">Class libraries do not require a `Main` procedure.</span></span> <span data-ttu-id="dece1-117">К ним относятся библиотеки элементов управления Windows и библиотеки веб-элементов управления.</span><span class="sxs-lookup"><span data-stu-id="dece1-117">These include Windows Control Libraries and Web Control Libraries.</span></span> <span data-ttu-id="dece1-118">Веб-приложения развертываются в виде библиотек классов.</span><span class="sxs-lookup"><span data-stu-id="dece1-118">Web applications are deployed as class libraries.</span></span>

## <a name="declaring-the-main-procedure"></a><span data-ttu-id="dece1-119">Объявление основной процедуры</span><span class="sxs-lookup"><span data-stu-id="dece1-119">Declaring the Main Procedure</span></span>
 <span data-ttu-id="dece1-120">Существует четыре способа объявления процедуры `Main`.</span><span class="sxs-lookup"><span data-stu-id="dece1-120">There are four ways to declare the `Main` procedure.</span></span> <span data-ttu-id="dece1-121">Он может принимать аргументы, а также не может возвращать значение.</span><span class="sxs-lookup"><span data-stu-id="dece1-121">It can take arguments or not, and it can return a value or not.</span></span>

> [!NOTE]
> <span data-ttu-id="dece1-122">При объявлении `Main` в классе необходимо использовать ключевое слово `Shared`.</span><span class="sxs-lookup"><span data-stu-id="dece1-122">If you declare `Main` in a class, you must use the `Shared` keyword.</span></span> <span data-ttu-id="dece1-123">В модуле `Main` не нужно `Shared`.</span><span class="sxs-lookup"><span data-stu-id="dece1-123">In a module, `Main` does not need to be `Shared`.</span></span>

- <span data-ttu-id="dece1-124">Самый простой способ — объявить `Sub`ную процедуру, которая не принимает аргументы или возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="dece1-124">The simplest way is to declare a `Sub` procedure that does not take arguments or return a value.</span></span>

    ```vb
    Module mainModule
        Sub Main()
            MsgBox("The Main procedure is starting the application.")
            ' Insert call to appropriate starting place in your code.
            MsgBox("The application is terminating.")
        End Sub
    End Module
    ```

- <span data-ttu-id="dece1-125">`Main` также может возвращать значение `Integer`, используемое операционной системой в качестве кода выхода для программы.</span><span class="sxs-lookup"><span data-stu-id="dece1-125">`Main` can also return an `Integer` value, which the operating system uses as the exit code for your program.</span></span> <span data-ttu-id="dece1-126">Другие программы могут протестировать этот код, изучая значение ERRORLEVEL Windows.</span><span class="sxs-lookup"><span data-stu-id="dece1-126">Other programs can test this code by examining the Windows ERRORLEVEL value.</span></span> <span data-ttu-id="dece1-127">Чтобы получить код выхода, необходимо объявить `Main` в качестве `Function` процедуры, а не `Sub` процедуры.</span><span class="sxs-lookup"><span data-stu-id="dece1-127">To return an exit code, you must declare `Main` as a `Function` procedure instead of a `Sub` procedure.</span></span>

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

- <span data-ttu-id="dece1-128">`Main` также может принимать `String` массив в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="dece1-128">`Main` can also take a `String` array as an argument.</span></span> <span data-ttu-id="dece1-129">Каждая строка в массиве содержит один из аргументов командной строки, используемых для вызова программы.</span><span class="sxs-lookup"><span data-stu-id="dece1-129">Each string in the array contains one of the command-line arguments used to invoke your program.</span></span> <span data-ttu-id="dece1-130">В зависимости от их значений можно выполнять различные действия.</span><span class="sxs-lookup"><span data-stu-id="dece1-130">You can take different actions depending on their values.</span></span>

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

- <span data-ttu-id="dece1-131">Можно объявить `Main`, чтобы проверить аргументы командной строки, но не вернуть код выхода, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="dece1-131">You can declare `Main` to examine the command-line arguments but not return an exit code, as follows.</span></span>

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
  
## <a name="see-also"></a><span data-ttu-id="dece1-132">См. также</span><span class="sxs-lookup"><span data-stu-id="dece1-132">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>
- <xref:System.Array.Length%2A>
- <xref:Microsoft.VisualBasic.Information.UBound%2A>
- [<span data-ttu-id="dece1-133">Структура программы Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dece1-133">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [<span data-ttu-id="dece1-134">-main</span><span class="sxs-lookup"><span data-stu-id="dece1-134">-main</span></span>](../../../visual-basic/reference/command-line-compiler/main.md)
- [<span data-ttu-id="dece1-135">Общие</span><span class="sxs-lookup"><span data-stu-id="dece1-135">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="dece1-136">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="dece1-136">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="dece1-137">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="dece1-137">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="dece1-138">Тип данных Integer</span><span class="sxs-lookup"><span data-stu-id="dece1-138">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="dece1-139">Тип данных String</span><span class="sxs-lookup"><span data-stu-id="dece1-139">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)
