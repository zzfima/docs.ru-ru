---
title: "Публикация приложения Hello World с помощью Visual Studio 2017"
description: "При публикации создается набор файлов, которые необходимы для запуска приложения."
keywords: ".NET, .NET Core, консольное приложение, публикация, развертывание"
author: BillWagner
ms.author: wiwagn
ms.date: 10/05/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: a19545d3-24af-4a32-9778-cfb5ae938287
ms.openlocfilehash: a3e5bda5c99144c9ab5bbaf5e2f5566261af4813
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="publish-your-hello-world-application-with-visual-studio-2017"></a><span data-ttu-id="c3a97-104">Публикация приложения Hello World с помощью Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="c3a97-104">Publish your Hello World application with Visual Studio 2017</span></span>

<span data-ttu-id="c3a97-105">Изучая руководство [Создание приложения Hello World на C# с помощью .NET Core в Visual Studio 2017](with-visual-studio.md) или [Создание приложения Hello World на Visual Basic с помощью .NET Core в Visual Studio 2017](vb-with-visual-studio.md), вы создали консольное приложение Hello World.</span><span class="sxs-lookup"><span data-stu-id="c3a97-105">In [Build a C# Hello World application with .NET Core in Visual Studio 2017](with-visual-studio.md) or [Build a Visual Basic Hello World application with .NET Core in Visual Studio 2017](vb-with-visual-studio.md), you built a Hello World console application.</span></span> <span data-ttu-id="c3a97-106">В следующем руководстве [Отладка приложения Hello World на C# в Visual Studio 2017](debugging-with-visual-studio.md) вы протестировали его с помощью отладчика Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c3a97-106">In [Debug your C# Hello World application with Visual Studio 2017](debugging-with-visual-studio.md), you tested it using the Visual Studio debugger.</span></span> <span data-ttu-id="c3a97-107">Теперь вы уверены, что приложение работает правильно, и его можно опубликовать для выполнения другими пользователями.</span><span class="sxs-lookup"><span data-stu-id="c3a97-107">Now that you're sure that it works as expected, you can publish it so that other users can run it.</span></span> <span data-ttu-id="c3a97-108">При публикации создается набор файлов, которые необходимы для запуска приложения. Чтобы развернуть приложение, скопируйте эти файлы на целевой компьютер.</span><span class="sxs-lookup"><span data-stu-id="c3a97-108">Publishing creates the set of files that are needed to run your application, and you can deploy the files by copying them to a target machine.</span></span>

<span data-ttu-id="c3a97-109">Действия для публикации и запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="c3a97-109">To publish and run your application:</span></span> 

1. <span data-ttu-id="c3a97-110">Убедитесь, что в Visual Studio настроен режим сборки для версии выпуска.</span><span class="sxs-lookup"><span data-stu-id="c3a97-110">Make sure that Visual Studio is building the Release version of your application.</span></span> <span data-ttu-id="c3a97-111">При необходимости измените конфигурацию сборки на панели инструментов, указав конфигурацию **Выпуск** вместо конфигурации **Отладка**.</span><span class="sxs-lookup"><span data-stu-id="c3a97-111">If necessary, change the build configuration setting on the toolbar from **Debug** to **Release**.</span></span>

   ![Панель инструментов Visual Studio](media/publishing-with-visual-studio/toolbar.png)

1. <span data-ttu-id="c3a97-113">Щелкните проект **HelloWorld** (не решение HelloWorld) правой кнопкой мыши и выберите **Опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="c3a97-113">Right-click on the **HelloWorld** project (not the HelloWorld solution) and select **Publish** from the menu.</span></span> <span data-ttu-id="c3a97-114">Также можно выбрать **Публикация HelloWorld** из раздела **Сборка** в главном меню Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c3a97-114">You can also select **Publish HelloWorld** from the main Visual Studio **Build** menu.</span></span>

   ![Панель инструментов Visual Studio](media/publishing-with-visual-studio/publish1.png)


   ![Панель инструментов Visual Studio](media/publishing-with-visual-studio/publishwindow.png)

1. <span data-ttu-id="c3a97-117">Откройте окно консоли.</span><span class="sxs-lookup"><span data-stu-id="c3a97-117">Open a console window.</span></span> <span data-ttu-id="c3a97-118">Например, в текстовом поле **Введите здесь текст для поиска** на панели задач Windows введите `Command Prompt` (или `cmd` для краткости), а затем откройте окно консоли с помощью приложения **командной строки** или клавиши ВВОД, если оно выделено в результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="c3a97-118">For example in the **Type here to search** text box in the Windows taskbar, enter `Command Prompt` (or `cmd` for short), and open a console window by either selecting the **Command Prompt** desktop app or pressing Enter if it's selected in the search results.</span></span>

1. <span data-ttu-id="c3a97-119">Перейдите к опубликованному приложению в подкаталоге `bin\release\PublishOutput` проекта приложения.</span><span class="sxs-lookup"><span data-stu-id="c3a97-119">Navigate to the published application in the `bin\release\PublishOutput` subdirectory of your application's project directory.</span></span> <span data-ttu-id="c3a97-120">Как показано на следующем рисунке, опубликованные выходные данные включают следующие четыре файла:</span><span class="sxs-lookup"><span data-stu-id="c3a97-120">As the following figure shows, the published output includes the following four files:</span></span>

      * <span data-ttu-id="c3a97-121">*HelloWorld.deps.json*</span><span class="sxs-lookup"><span data-stu-id="c3a97-121">*HelloWorld.deps.json*</span></span>

         <span data-ttu-id="c3a97-122">Файл зависимости среды выполнения приложения.</span><span class="sxs-lookup"><span data-stu-id="c3a97-122">The application's runtime dependencies file.</span></span> <span data-ttu-id="c3a97-123">Он определяет компоненты .NET Core и библиотек (включая библиотеку динамической компоновки, содержащий приложение), необходимые для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="c3a97-123">It defines the .NET Core components and the libraries (including the dynamic link library that contains your application) needed to run your application.</span></span> <span data-ttu-id="c3a97-124">Дополнительные сведения см. в разделе [файлы конфигурации среды выполнения](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="c3a97-124">For more information, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>
 
      * <span data-ttu-id="c3a97-125">*HelloWorld.dll*</span><span class="sxs-lookup"><span data-stu-id="c3a97-125">*HelloWorld.dll*</span></span>

         <span data-ttu-id="c3a97-126">Файл, содержащий приложение.</span><span class="sxs-lookup"><span data-stu-id="c3a97-126">The file that contains your application.</span></span> <span data-ttu-id="c3a97-127">Это библиотеки DLL, которая может быть выполнена путем ввода `dotnet HelloWorld.dll` команду в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="c3a97-127">It is a dynamic link library that can be executed by entering the `dotnet HelloWorld.dll` command in a console window.</span></span> 

      * <span data-ttu-id="c3a97-128">*HelloWorld.pdb* (необязателен для развертывания)</span><span class="sxs-lookup"><span data-stu-id="c3a97-128">*HelloWorld.pdb* (optional for deployment)</span></span>

         <span data-ttu-id="c3a97-129">Файл, содержащий отладочные символы.</span><span class="sxs-lookup"><span data-stu-id="c3a97-129">A file that contains debug symbols.</span></span> <span data-ttu-id="c3a97-130">Этот файл не нужно распространять вместе с приложением, но желательно сохранить его на случай, если придется выполнять отладку опубликованной версии приложения.</span><span class="sxs-lookup"><span data-stu-id="c3a97-130">You aren't required to deploy this file along with your application, although you should save it in the event that you need to debug the published version of your application.</span></span>

      * <span data-ttu-id="c3a97-131">*HelloWorld.runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="c3a97-131">*HelloWorld.runtimeconfig.json*</span></span>

         <span data-ttu-id="c3a97-132">Файл конфигурации приложения среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="c3a97-132">The application's runtime configuration file.</span></span> <span data-ttu-id="c3a97-133">Он определяет версию платформы .NET Core, которое было создано приложение для запуска.</span><span class="sxs-lookup"><span data-stu-id="c3a97-133">It identifies the version of .NET Core that your application was built to run on.</span></span> <span data-ttu-id="c3a97-134">Дополнительные сведения см. в разделе [файлы конфигурации среды выполнения](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="c3a97-134">For more information, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>  

   ![Окно консоли с опубликованными файлами](media/publishing-with-visual-studio/publishedfiles.png)

<span data-ttu-id="c3a97-136">В ходе публикации создается платформенно-зависимое развертывание. При таком развертывании опубликованное приложение будет выполняться на любой платформе, поддерживаемой .NET Core, при условии, что платформа .NET Core установлена в системе.</span><span class="sxs-lookup"><span data-stu-id="c3a97-136">The publishing process creates a framework-dependent deployment, which is a type of deployment where the published application will run on any platform supported by .NET Core with .NET Core installed on the system.</span></span> <span data-ttu-id="c3a97-137">Пользователи могут запускать приложение командой `dotnet HelloWorld.dll` из окна консоли.</span><span class="sxs-lookup"><span data-stu-id="c3a97-137">Users can run your application by issuing the `dotnet HelloWorld.dll` command from a console window.</span></span>

<span data-ttu-id="c3a97-138">Дополнительные сведения о публикации и развертывании приложений .NET Core см. в статье [Развертывание приложений .NET Core](../../core/deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="c3a97-138">For more information on publishing and deploying .NET Core applications, see [.NET Core Application Deployment](../../core/deploying/index.md).</span></span>
