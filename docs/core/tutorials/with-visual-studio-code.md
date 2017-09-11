---
title: "Начало работы с C# и Visual Studio Code — руководство по языку C# | Документация Майкрософт"
description: "Узнайте, как создать и отладить в Visual Studio Code свое первое приложение .NET Core на языке C#."
keywords: "C#, приступая к работе, получение, установка, Visual Studio Code, кроссплатформенный"
author: kendrahavens
ms.author: mairaw
ms.date: 8/01/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 76c23597-4cf9-467e-8a47-0c3703ce37e7
ms.translationtype: HT
ms.sourcegitcommit: 3bd8800e7410ae4a3b89f5962af957789edd48b0
ms.openlocfilehash: a10fda5663f0a49069388ee8ee7a9ebb575cd549
ms.contentlocale: ru-ru
ms.lasthandoff: 08/03/2017

---

# <a name="get-started-with-c-and-visual-studio-code"></a><span data-ttu-id="a3ca6-104">Начало работы с C# и Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="a3ca6-104">Get Started with C# and Visual Studio Code</span></span>

<span data-ttu-id="a3ca6-105">.NET Core предcтавляет собой быструю модульную платформу для создания приложений, работающих на ОС Windows, Linux и macOS.</span><span class="sxs-lookup"><span data-stu-id="a3ca6-105">.NET Core gives you a fast and modular platform for creating applications that run on Windows, Linux, and macOS.</span></span> <span data-ttu-id="a3ca6-106">Visual Studio Code с расширением C# позволяет эффективно работать с кодом, а также обеспечивает полную поддержку IntelliSense (интеллектуальное завершение кода) и отладки для языка C#.</span><span class="sxs-lookup"><span data-stu-id="a3ca6-106">Use Visual Studio Code with the C# extension to get a powerful editing experience with full support for C# IntelliSense (smart code completion) and debugging.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a3ca6-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="a3ca6-107">Prerequisites</span></span>

1. <span data-ttu-id="a3ca6-108">Установите [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="a3ca6-108">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
2. <span data-ttu-id="a3ca6-109">Установите [пакета SDK для .NET Core](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="a3ca6-109">Install the [.NET Core SDK](https://www.microsoft.com/net/download/core).</span></span>
3. <span data-ttu-id="a3ca6-110">Установите [расширение C#](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp) из Marketplace для Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="a3ca6-110">Install the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp) from the Visual Studio Code Marketplace.</span></span>

## <a name="hello-world"></a><span data-ttu-id="a3ca6-111">Hello World</span><span class="sxs-lookup"><span data-stu-id="a3ca6-111">Hello World</span></span>

<span data-ttu-id="a3ca6-112">Давайте начнем с создания простой программы Hello World для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a3ca6-112">Let's get started with a simple "Hello World" program on .NET Core:</span></span>

1. <span data-ttu-id="a3ca6-113">Откройте проект.</span><span class="sxs-lookup"><span data-stu-id="a3ca6-113">Open a project:</span></span>

    * <span data-ttu-id="a3ca6-114">Откройте Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="a3ca6-114">Open Visual Studio Code.</span></span>
    * <span data-ttu-id="a3ca6-115">Щелкните значок обозревателя в расположенном слева меню, затем щелкните**Открыть папку**.</span><span class="sxs-lookup"><span data-stu-id="a3ca6-115">Click on the Explorer icon on the left menu and then click **Open Folder**.</span></span>
    * <span data-ttu-id="a3ca6-116">Выберите папку, в которой вы хотите разместить проект C#, и щелкните **Выбрать папку**.</span><span class="sxs-lookup"><span data-stu-id="a3ca6-116">Select the folder you want your C# project to be in and click **Select Folder**.</span></span> <span data-ttu-id="a3ca6-117">В нашем примере мы создадим для проекта новую папку с именем HelloWorld.</span><span class="sxs-lookup"><span data-stu-id="a3ca6-117">For our example, we'll create a folder for our project named 'HelloWorld'.</span></span> 

  ![VSCodeOpenFolder](media/with-visual-studio-code/vscodeopenfolder.png)

    * <span data-ttu-id="a3ca6-119">Также вы можете открыть уже существующую папку проекта, используя пункт **Файл** > **Открыть папку** из главного меню.</span><span class="sxs-lookup"><span data-stu-id="a3ca6-119">Alternatively, you can select **File** > **Open Folder** from the main menu to open your project folder.</span></span>

2. <span data-ttu-id="a3ca6-120">Инициализируйте проект C#.</span><span class="sxs-lookup"><span data-stu-id="a3ca6-120">Initialize a C# project:</span></span>
    * <span data-ttu-id="a3ca6-121">Откройте в Visual Studio Code встроенный терминал, нажав клавиши <kbd>CTRL</kbd>+<kbd>\\`</kbd> (обратный апостроф).</span><span class="sxs-lookup"><span data-stu-id="a3ca6-121">Open the Integrated Terminal from Visual Studio Code by typing <kbd>CTRL</kbd>+<kbd>\\`</kbd> (backtick).</span></span> <span data-ttu-id="a3ca6-122">Также можно выбрать в главном меню пункты **Просмотр** > **Встроенный терминал**.</span><span class="sxs-lookup"><span data-stu-id="a3ca6-122">Alternatively, you can select **View** > **Integrated Terminal** from the main menu.</span></span>
    * <span data-ttu-id="a3ca6-123">В окне терминала введите `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="a3ca6-123">In the terminal window, type `dotnet new console`.</span></span>
    * <span data-ttu-id="a3ca6-124">Эта команда создает в выбранной папке файл `Program.cs` с уже готовой простой программой Hello World, а также файл проекта C# с именем `HelloWorld.csproj`.</span><span class="sxs-lookup"><span data-stu-id="a3ca6-124">This creates a `Program.cs` file in your folder with a simple "Hello World" program already written, along with a C# project file named `HelloWorld.csproj`.</span></span>

  ![Команда dotnet new](media/with-visual-studio-code/dotnetnew.png)

3. <span data-ttu-id="a3ca6-126">Выполните разрешение для средств сборки:</span><span class="sxs-lookup"><span data-stu-id="a3ca6-126">Resolve the build assets:</span></span>

    * <span data-ttu-id="a3ca6-127">Для **.NET Core 1.1** введите `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="a3ca6-127">For **.NET Core 1.1**, type `dotnet restore`.</span></span> <span data-ttu-id="a3ca6-128">Команда `dotnet restore` предоставляет доступ к пакетам .NET Core, которые необходимы для сборки этого проекта.</span><span class="sxs-lookup"><span data-stu-id="a3ca6-128">Running `dotnet restore` gives you access to the  required .NET Core packages that are needed to build your project.</span></span>

   ![Команда dotnet restore](media/with-visual-studio-code/dotnetrestore.png)

    * <span data-ttu-id="a3ca6-130">Для **.NET Core 2.0** этот этап является необязательным.</span><span class="sxs-lookup"><span data-stu-id="a3ca6-130">For **.NET Core 2.0**, this step is optional.</span></span> <span data-ttu-id="a3ca6-131">Команда `dotnet restore` выполняется автоматически при создании нового проекта.</span><span class="sxs-lookup"><span data-stu-id="a3ca6-131">The `dotnet restore` command executes automatically when a new project is created.</span></span>

4. <span data-ttu-id="a3ca6-132">Запустите программу Hello World.</span><span class="sxs-lookup"><span data-stu-id="a3ca6-132">Run the "Hello World" program:</span></span>

    * <span data-ttu-id="a3ca6-133">Введите `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="a3ca6-133">Type `dotnet run`.</span></span> 

  ![Команда dotnet run](media/with-visual-studio-code/dotnetrun.png)

<span data-ttu-id="a3ca6-135">Вы можете просмотреть небольшие видеоматериалы с информацией о процессе настройки для [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS), или [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span><span class="sxs-lookup"><span data-stu-id="a3ca6-135">You can also watch a short video tutorial for further setup help on [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS), or [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span></span>

## <a name="debug"></a><span data-ttu-id="a3ca6-136">Отладка</span><span class="sxs-lookup"><span data-stu-id="a3ca6-136">Debug</span></span>
1. <span data-ttu-id="a3ca6-137">Откройте файл *Program.cs*, щелкнув его.</span><span class="sxs-lookup"><span data-stu-id="a3ca6-137">Open *Program.cs* by clicking on it.</span></span> <span data-ttu-id="a3ca6-138">Когда вы в первый раз открываете файл C# в Visual Studio Code, в редакторе загружается [OmniSharp](http://www.omnisharp.net/).</span><span class="sxs-lookup"><span data-stu-id="a3ca6-138">The first time you open a C# file in Visual Studio Code, [OmniSharp](http://www.omnisharp.net/) will load in the editor.</span></span>

  ![Откройте файл Program.cs](media/with-visual-studio-code/opencs.png)

2. <span data-ttu-id="a3ca6-140">Visual Studio Code предложит добавить недостающие ресурсы для сборки и отладки приложения.</span><span class="sxs-lookup"><span data-stu-id="a3ca6-140">Visual Studio Code will prompt you to add the missing assets to build and debug your app.</span></span> <span data-ttu-id="a3ca6-141">Выберите ответ **Да**.</span><span class="sxs-lookup"><span data-stu-id="a3ca6-141">Select **Yes**.</span></span> 

  ![Предупреждение о недостающих ресурсах](media/with-visual-studio-code/missing-assets.png)

3. <span data-ttu-id="a3ca6-143">Чтобы открыть окно отладки, щелкните значок "Отладка" в меню слева.</span><span class="sxs-lookup"><span data-stu-id="a3ca6-143">To open the Debug view, click on the Debugging icon on the left side menu.</span></span>

  ![Откройте вкладку "Отладка"](media/with-visual-studio-code/opendebug.png)

4. <span data-ttu-id="a3ca6-145">Найдите зеленую стрелку в верхней части панели.</span><span class="sxs-lookup"><span data-stu-id="a3ca6-145">Locate the green arrow at the top of the pane.</span></span> <span data-ttu-id="a3ca6-146">Убедитесь, что в раскрывающемся списке рядом с ней выбран вариант `.NET Core Launch (console)`.</span><span class="sxs-lookup"><span data-stu-id="a3ca6-146">Make sure the drop-down next to it has `.NET Core Launch (console)` selected.</span></span>

  ![Выбор .NET Core](media/with-visual-studio-code/selectcore.png)

5. <span data-ttu-id="a3ca6-148">Добавьте в проект точку останова, щелкнув **левое поле редактора кода** (пустое пространство слева от номера строк) в строке 9.</span><span class="sxs-lookup"><span data-stu-id="a3ca6-148">Add a breakpoint to your project by clicking on the **editor margin** (the space on the left of the line numbers in the editor) next to line 9.</span></span>

  ![Установка точки останова](media/with-visual-studio-code/setbreakpoint.png)

6. <span data-ttu-id="a3ca6-150">Нажмите клавишу <kbd>F5</kbd> или щелкните зеленую стрелку, чтобы начать отладку.</span><span class="sxs-lookup"><span data-stu-id="a3ca6-150">Select <kbd>F5</kbd> or the green arrow to start debugging.</span></span> <span data-ttu-id="a3ca6-151">Отладчик останавливает выполнение программы, когда достигнет точки останова, которую вы только что установили.</span><span class="sxs-lookup"><span data-stu-id="a3ca6-151">The debugger stops execution of your program when it reaches the breakpoint you set in the previous step.</span></span>
    * <span data-ttu-id="a3ca6-152">Во время отладки вы можете просматривать локальные переменные в верхней левой области или в консоли отладки.</span><span class="sxs-lookup"><span data-stu-id="a3ca6-152">While debugging you can view your local variables in the top left pane or use the debug console.</span></span>

  ![Запуск и отладка](media/with-visual-studio-code/rundebug.png)

7. <span data-ttu-id="a3ca6-154">Выберите зеленую стрелку в верхней части, чтобы продолжить отладку, или выберите красный квадрат в верхней части, чтобы остановить процесс.</span><span class="sxs-lookup"><span data-stu-id="a3ca6-154">Select the green arrow at the top to continue debugging, or select the red square at the top to stop.</span></span>

> [!TIP] 
> <span data-ttu-id="a3ca6-155">Дополнительные сведения и советы по отладке .NET Core в Visual Studio Code с помощью OmniSharp см. в разделе [Инструкции по настройке отладчика .NET Core](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span><span class="sxs-lookup"><span data-stu-id="a3ca6-155">For more information and troubleshooting tips on .NET Core debugging with OmniSharp in Visual Studio Code, see [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a3ca6-156">См. также</span><span class="sxs-lookup"><span data-stu-id="a3ca6-156">See also</span></span>
<span data-ttu-id="a3ca6-157">[Настройка Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview) </span><span class="sxs-lookup"><span data-stu-id="a3ca6-157">[Setting up Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview) </span></span>  
<span data-ttu-id="a3ca6-158">[Debugging in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging) (Отладка в Visual Studio Code)</span><span class="sxs-lookup"><span data-stu-id="a3ca6-158">[Debugging in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging)</span></span>

