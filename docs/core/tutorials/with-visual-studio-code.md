---
title: Начало работы с C# и Visual Studio Code — руководство по языку C#
description: Узнайте, как создать и отладить в Visual Studio Code свое первое приложение .NET Core на языке C#.
author: kendrahavens
ms.author: mairaw
ms.date: 09/27/2017
ms.openlocfilehash: 74fdd9ce122482a027931405cc9a94011a9c13bb
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50192587"
---
# <a name="get-started-with-c-and-visual-studio-code"></a><span data-ttu-id="60a43-103">Начало работы с C# и Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="60a43-103">Get Started with C# and Visual Studio Code</span></span>

<span data-ttu-id="60a43-104">.NET Core предcтавляет собой быструю модульную платформу для создания приложений, работающих на ОС Windows, Linux и macOS.</span><span class="sxs-lookup"><span data-stu-id="60a43-104">.NET Core gives you a fast and modular platform for creating applications that run on Windows, Linux, and macOS.</span></span> <span data-ttu-id="60a43-105">Visual Studio Code с расширением C# позволяет эффективно работать с кодом, а также обеспечивает полную поддержку IntelliSense (интеллектуальное завершение кода) и отладки для языка C#.</span><span class="sxs-lookup"><span data-stu-id="60a43-105">Use Visual Studio Code with the C# extension to get a powerful editing experience with full support for C# IntelliSense (smart code completion) and debugging.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="60a43-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="60a43-106">Prerequisites</span></span>

1. <span data-ttu-id="60a43-107">Установите [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="60a43-107">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
2. <span data-ttu-id="60a43-108">Установите [пакета SDK для .NET Core](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="60a43-108">Install the [.NET Core SDK](https://www.microsoft.com/net/download/core).</span></span>
3. <span data-ttu-id="60a43-109">Установите [расширение C#](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp) для Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="60a43-109">Install the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp) for Visual Studio Code.</span></span> <span data-ttu-id="60a43-110">См. дополнительные сведения об [установке расширений Visual Studio Code из Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span><span class="sxs-lookup"><span data-stu-id="60a43-110">For more information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>

## <a name="hello-world"></a><span data-ttu-id="60a43-111">Hello World</span><span class="sxs-lookup"><span data-stu-id="60a43-111">Hello World</span></span>

<span data-ttu-id="60a43-112">Давайте начнем с создания простой программы Hello World для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="60a43-112">Let's get started with a simple "Hello World" program on .NET Core:</span></span>

1. <span data-ttu-id="60a43-113">Откройте проект.</span><span class="sxs-lookup"><span data-stu-id="60a43-113">Open a project:</span></span>

    * <span data-ttu-id="60a43-114">Откройте Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="60a43-114">Open Visual Studio Code.</span></span>
    * <span data-ttu-id="60a43-115">Щелкните значок обозревателя в расположенном слева меню, затем щелкните**Открыть папку**.</span><span class="sxs-lookup"><span data-stu-id="60a43-115">Click on the Explorer icon on the left menu and then click **Open Folder**.</span></span>
    * <span data-ttu-id="60a43-116">Выберите **Файл** > **Открыть папку** в главном меню, чтобы открыть папку, в которой вы хотите разместить проект C#, и щелкните **Выбрать папку**.</span><span class="sxs-lookup"><span data-stu-id="60a43-116">Select **File** > **Open Folder** from the main menu to open the folder you want your C# project to be in and click **Select Folder**.</span></span> <span data-ttu-id="60a43-117">В нашем примере мы создаем для проекта папку с именем *HelloWorld*.</span><span class="sxs-lookup"><span data-stu-id="60a43-117">For our example, we're creating a folder for our project named *HelloWorld*.</span></span>

      ![VSCodeOpenFolder](media/with-visual-studio-code/vscodeopenfolder.png)

2. <span data-ttu-id="60a43-119">Инициализируйте проект C#.</span><span class="sxs-lookup"><span data-stu-id="60a43-119">Initialize a C# project:</span></span>
    * <span data-ttu-id="60a43-120">Откройте в Visual Studio Code интегрированный терминал, выбрав **Просмотр** > **Интегрированный терминал** в главном меню.</span><span class="sxs-lookup"><span data-stu-id="60a43-120">Open the Integrated Terminal from Visual Studio Code by selecting **View** > **Integrated Terminal** from the main menu.</span></span>
    * <span data-ttu-id="60a43-121">В окне терминала введите `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="60a43-121">In the terminal window, type `dotnet new console`.</span></span>
    * <span data-ttu-id="60a43-122">Эта команда создает в выбранной папке файл `Program.cs` с уже готовой простой программой Hello World, а также файл проекта C# с именем `HelloWorld.csproj`.</span><span class="sxs-lookup"><span data-stu-id="60a43-122">This command creates a `Program.cs` file in your folder with a simple "Hello World" program already written, along with a C# project file named `HelloWorld.csproj`.</span></span>

      ![Команда dotnet new](media/with-visual-studio-code/dotnetnew.png)

3. <span data-ttu-id="60a43-124">Выполните разрешение для средств сборки:</span><span class="sxs-lookup"><span data-stu-id="60a43-124">Resolve the build assets:</span></span>

    * <span data-ttu-id="60a43-125">Для **.NET Core 1.x** введите `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="60a43-125">For **.NET Core 1.x**, type `dotnet restore`.</span></span> <span data-ttu-id="60a43-126">Команда `dotnet restore` предоставляет доступ к пакетам .NET Core, которые необходимы для сборки этого проекта.</span><span class="sxs-lookup"><span data-stu-id="60a43-126">Running `dotnet restore` gives you access to the  required .NET Core packages that are needed to build your project.</span></span>

      ![Команда dotnet restore](media/with-visual-studio-code/dotnetrestore.png)

      [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

4. <span data-ttu-id="60a43-128">Запустите программу Hello World.</span><span class="sxs-lookup"><span data-stu-id="60a43-128">Run the "Hello World" program:</span></span>

    * <span data-ttu-id="60a43-129">Введите `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="60a43-129">Type `dotnet run`.</span></span>

      ![Команда dotnet run](media/with-visual-studio-code/dotnetrun.png)

<span data-ttu-id="60a43-131">Вы можете просмотреть небольшие видеоматериалы с информацией о процессе настройки для [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS), или [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span><span class="sxs-lookup"><span data-stu-id="60a43-131">You can also watch a short video tutorial for further setup help on [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS), or [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span></span>

## <a name="debug"></a><span data-ttu-id="60a43-132">Отладка</span><span class="sxs-lookup"><span data-stu-id="60a43-132">Debug</span></span>

1. <span data-ttu-id="60a43-133">Откройте файл *Program.cs*, щелкнув его.</span><span class="sxs-lookup"><span data-stu-id="60a43-133">Open *Program.cs* by clicking on it.</span></span> <span data-ttu-id="60a43-134">Когда вы в первый раз открываете файл C# в Visual Studio Code, в редакторе загружается [OmniSharp](https://www.omnisharp.net/).</span><span class="sxs-lookup"><span data-stu-id="60a43-134">The first time you open a C# file in Visual Studio Code, [OmniSharp](https://www.omnisharp.net/) loads in the editor.</span></span>

    ![Откройте файл Program.cs](media/with-visual-studio-code/opencs.png)

2. <span data-ttu-id="60a43-136">Visual Studio Code предлагает добавить недостающие ресурсы для сборки и отладки приложения.</span><span class="sxs-lookup"><span data-stu-id="60a43-136">Visual Studio Code should prompt you to add the missing assets to build and debug your app.</span></span> <span data-ttu-id="60a43-137">Выберите ответ **Да**.</span><span class="sxs-lookup"><span data-stu-id="60a43-137">Select **Yes**.</span></span>

    ![Предупреждение о недостающих ресурсах](media/with-visual-studio-code/missing-assets.png)

3. <span data-ttu-id="60a43-139">Чтобы открыть окно отладки, щелкните значок "Отладка" в меню слева.</span><span class="sxs-lookup"><span data-stu-id="60a43-139">To open the Debug view, click on the Debugging icon on the left side menu.</span></span>

    ![Откройте вкладку "Отладка"](media/with-visual-studio-code/opendebug.png)

4. <span data-ttu-id="60a43-141">Найдите зеленую стрелку в верхней части панели.</span><span class="sxs-lookup"><span data-stu-id="60a43-141">Locate the green arrow at the top of the pane.</span></span> <span data-ttu-id="60a43-142">Убедитесь, что в раскрывающемся списке рядом с ней выбран вариант `.NET Core Launch (console)`.</span><span class="sxs-lookup"><span data-stu-id="60a43-142">Make sure the drop-down next to it has `.NET Core Launch (console)` selected.</span></span>

    ![Выбор .NET Core](media/with-visual-studio-code/selectcore.png)

5. <span data-ttu-id="60a43-144">Добавьте в проект точку останова, щелкнув **поле редактора** (пустое пространство слева от номеров строк) в строке 9, или переместите курсор текста в строку 9 в редакторе и нажмите клавишу <kbd>F9</kbd>.</span><span class="sxs-lookup"><span data-stu-id="60a43-144">Add a breakpoint to your project by clicking on the **editor margin**, which is the space on the left of the line numbers in the editor, next to line 9, or move the text cursor onto line 9 in the editor and  press <kbd>F9</kbd>.</span></span>

    ![Установка точки останова](media/with-visual-studio-code/setbreakpoint.png)

6. <span data-ttu-id="60a43-146">Чтобы начать отладку, нажмите клавишу <kbd>F5</kbd> или щелкните зеленую стрелку.</span><span class="sxs-lookup"><span data-stu-id="60a43-146">To start debugging, select <kbd>F5</kbd> or the green arrow.</span></span> <span data-ttu-id="60a43-147">Отладчик останавливает выполнение программы, когда достигнет точки останова, которую вы только что установили.</span><span class="sxs-lookup"><span data-stu-id="60a43-147">The debugger stops execution of your program when it reaches the breakpoint you set in the previous step.</span></span>
    * <span data-ttu-id="60a43-148">Во время отладки вы можете просматривать локальные переменные в верхней левой области или в консоли отладки.</span><span class="sxs-lookup"><span data-stu-id="60a43-148">While debugging, you can view your local variables in the top left pane or use the debug console.</span></span>

    ![Запуск и отладка](media/with-visual-studio-code/rundebug.png)

7. <span data-ttu-id="60a43-150">Выберите зеленую стрелку в верхней части, чтобы продолжить отладку, или выберите красный квадрат в верхней части, чтобы остановить процесс.</span><span class="sxs-lookup"><span data-stu-id="60a43-150">Select the green arrow at the top to continue debugging, or select the red square at the top to stop.</span></span>

> [!TIP]
> <span data-ttu-id="60a43-151">Дополнительные сведения и советы по отладке .NET Core в Visual Studio Code с помощью OmniSharp см. в разделе [Инструкции по настройке отладчика .NET Core](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span><span class="sxs-lookup"><span data-stu-id="60a43-151">For more information and troubleshooting tips on .NET Core debugging with OmniSharp in Visual Studio Code, see [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span></span>

## <a name="faq"></a><span data-ttu-id="60a43-152">часто задаваемые вопросы</span><span class="sxs-lookup"><span data-stu-id="60a43-152">FAQ</span></span>

### <a name="im-missing-required-assets-to-build-and-debug-c-in-visual-studio-code-my-debugger-says-no-configuration"></a><span data-ttu-id="60a43-153">Мне не хватает ресурсов для выполнения сборки и отладки C# в Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="60a43-153">I'm missing required assets to build and debug C# in Visual Studio Code.</span></span> <span data-ttu-id="60a43-154">Отладчик выдает сообщение: "Конфигурация отсутствует".</span><span class="sxs-lookup"><span data-stu-id="60a43-154">My debugger says "No Configuration."</span></span>

<span data-ttu-id="60a43-155">Ресурсы для сборки и отладки можно создать с помощью расширения Visual Studio Code C#.</span><span class="sxs-lookup"><span data-stu-id="60a43-155">The Visual Studio Code C# extension can generate assets to build and debug for you.</span></span> <span data-ttu-id="60a43-156">Visual Studio Code предложит создать эти ресурсы при первом открытии проекта C#.</span><span class="sxs-lookup"><span data-stu-id="60a43-156">Visual Studio Code prompts you to generate these assets when you first open a C# project.</span></span> <span data-ttu-id="60a43-157">Если вы не создали ресурсы, то все равно сможете выполнить эту команду. Для этого откройте палитру команд (**Вид > Палитра команд**) и введите ">.NET: Создать ресурсы для сборки и отладки".</span><span class="sxs-lookup"><span data-stu-id="60a43-157">If you didn't generate assets then, you can still run this command by opening the Command Palette (**View > Command Palette**) and typing ">.NET: Generate Assets for Build and Debug".</span></span> <span data-ttu-id="60a43-158">После этого будут созданы необходимые конфигурационные файлы .vscode, launch.json и tasks.json.</span><span class="sxs-lookup"><span data-stu-id="60a43-158">Selecting this generates the .vscode, launch.json, and tasks.json configuration files that you need.</span></span>

## <a name="see-also"></a><span data-ttu-id="60a43-159">См. также</span><span class="sxs-lookup"><span data-stu-id="60a43-159">See also</span></span>

* <span data-ttu-id="60a43-160">[Setting up Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview) (Настройка Visual Studio Code)</span><span class="sxs-lookup"><span data-stu-id="60a43-160">[Setting up Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview)</span></span>
* <span data-ttu-id="60a43-161">[Debugging in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging) (Отладка в Visual Studio Code)</span><span class="sxs-lookup"><span data-stu-id="60a43-161">[Debugging in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging)</span></span>
