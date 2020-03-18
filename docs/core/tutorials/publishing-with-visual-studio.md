---
title: Публикация приложения Hello World .NET Core в Visual Studio
description: При публикации создается набор файлов, которые необходимы для запуска приложения .NET Core.
author: BillWagner
ms.author: wiwagn
ms.date: 12/10/2019
ms.custom: vs-dotnet
ms.openlocfilehash: bdd6e28713bdece2bd144e6763bd84d719e91449
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "78156638"
---
# <a name="publish-your-net-core-hello-world-application-with-visual-studio"></a><span data-ttu-id="21433-103">Публикация приложения Hello World .NET Core в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="21433-103">Publish your .NET Core Hello World application with Visual Studio</span></span>

<span data-ttu-id="21433-104">В разделе [Создание приложения Hello World на C# с помощью пакета SDK для .NET Core в Visual Studio 2017](with-visual-studio.md). Вы создали консольное приложение Hello World.</span><span class="sxs-lookup"><span data-stu-id="21433-104">In [Create a Hello World application with .NET Core in Visual Studio](with-visual-studio.md), you built a Hello World console application.</span></span> <span data-ttu-id="21433-105">В следующем руководстве [Отладка приложения Hello World в Visual Studio](debugging-with-visual-studio.md) вы протестировали его с помощью отладчика Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="21433-105">In [Debug your Hello World application with Visual Studio](debugging-with-visual-studio.md), you tested it using the Visual Studio debugger.</span></span> <span data-ttu-id="21433-106">Теперь вы уверены, что приложение работает правильно, и его можно опубликовать для выполнения другими пользователями.</span><span class="sxs-lookup"><span data-stu-id="21433-106">Now that you're sure that it works as expected, you can publish it so that other users can run it.</span></span> <span data-ttu-id="21433-107">При публикации создается набор файлов, которые необходимы для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="21433-107">Publishing creates the set of files that are needed to run your application.</span></span> <span data-ttu-id="21433-108">Чтобы развернуть файлы, скопируйте их на целевой компьютер.</span><span class="sxs-lookup"><span data-stu-id="21433-108">To deploy the files, copy them to the target machine.</span></span>

## <a name="publish-the-app"></a><span data-ttu-id="21433-109">Публикация приложения</span><span class="sxs-lookup"><span data-stu-id="21433-109">Publish the app</span></span>

1. <span data-ttu-id="21433-110">Убедитесь, что в Visual Studio настроен режим сборки для версии выпуска.</span><span class="sxs-lookup"><span data-stu-id="21433-110">Make sure that Visual Studio is building the Release version of your application.</span></span> <span data-ttu-id="21433-111">При необходимости измените конфигурацию сборки на панели инструментов, указав конфигурацию **Выпуск** вместо конфигурации **Отладка**.</span><span class="sxs-lookup"><span data-stu-id="21433-111">If necessary, change the build configuration setting on the toolbar from **Debug** to **Release**.</span></span>

   ![Панель инструментов Visual Studio с выбранной сборкой выпуска](media/publishing-with-visual-studio/visual-studio-toolbar-release.png)

1. <span data-ttu-id="21433-113">Щелкните проект **HelloWorld** (не решение HelloWorld) правой кнопкой мыши и выберите **Опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="21433-113">Right-click on the **HelloWorld** project (not the HelloWorld solution) and select **Publish** from the menu.</span></span> <span data-ttu-id="21433-114">(Также можно выбрать **Публикация HelloWorld** из раздела **Сборка** в главном меню.)</span><span class="sxs-lookup"><span data-stu-id="21433-114">(You can also select **Publish HelloWorld** from the main **Build** menu.)</span></span>

   ![Контекстное меню "Опубликовать" в Visual Studio](media/publishing-with-visual-studio/publish-context-menu.png)

1. <span data-ttu-id="21433-116">На странице **Выберите целевой объект публикации** выберите **Папка**, а затем — **Создать профиль**.</span><span class="sxs-lookup"><span data-stu-id="21433-116">On the **Pick a publish target** page, select **Folder**, and then select **Create Profile**.</span></span>

   ![Выбор целевого объекта публикации в Visual Studio](media/publishing-with-visual-studio/pick-publish-target.png)

1. <span data-ttu-id="21433-118">На странице **Публикация** выберите **Опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="21433-118">On the **Publish** page, select **Publish**.</span></span>

   ![Окно публикации в Visual Studio](media/publishing-with-visual-studio/publish-page.png)

## <a name="inspect-the-files"></a><span data-ttu-id="21433-120">Проверка файлов</span><span class="sxs-lookup"><span data-stu-id="21433-120">Inspect the files</span></span>

<span data-ttu-id="21433-121">В ходе публикации создается платформенно-зависимое развертывание. При таком развертывании опубликованное приложение выполнится на любой платформе, поддерживаемой .NET Core, при условии, что платформа .NET Core установлена в системе.</span><span class="sxs-lookup"><span data-stu-id="21433-121">The publishing process creates a framework-dependent deployment, which is a type of deployment where the published application runs on any platform supported by .NET Core with .NET Core installed on the system.</span></span> <span data-ttu-id="21433-122">Пользователи могут запустить опубликованное приложение, дважды щелкнув исполняемый файл или выполнив команду `dotnet HelloWorld.dll` из командной строки.</span><span class="sxs-lookup"><span data-stu-id="21433-122">Users can run the published app by double-clicking the executable or issuing the `dotnet HelloWorld.dll` command from a command prompt.</span></span>

<span data-ttu-id="21433-123">В следующих шагах будут рассмотрены файлы, созданные в процессе публикации.</span><span class="sxs-lookup"><span data-stu-id="21433-123">In the following steps, you'll look at the files created by the publish process.</span></span>

1. <span data-ttu-id="21433-124">Откройте командную строку.</span><span class="sxs-lookup"><span data-stu-id="21433-124">Open a command prompt.</span></span>

   <span data-ttu-id="21433-125">Одним из способов открыть командную строку является ввод **командной строки** (или **cmd** если коротко) в поле поиска на панели задач Windows.</span><span class="sxs-lookup"><span data-stu-id="21433-125">One way to open a command prompt is to enter **Command Prompt** (or **cmd** for short) in the search box on the Windows taskbar.</span></span> <span data-ttu-id="21433-126">Выберите приложение **Командной строки** для рабочего стола или нажмите **Ввод**, если оно уже выбрано в результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="21433-126">Select the **Command Prompt** desktop app, or press **Enter** if it's already selected in the search results.</span></span>

1. <span data-ttu-id="21433-127">Перейдите к опубликованному приложению в подкаталоге проекта приложения *bin\Release\netcoreapp3.1\publish*.</span><span class="sxs-lookup"><span data-stu-id="21433-127">Navigate to the published application in the *bin\Release\netcoreapp3.1\publish* subdirectory of the application's project directory.</span></span>

   ![Окно консоли с опубликованными файлами](media/publishing-with-visual-studio/published-files-output.png)

   <span data-ttu-id="21433-129">Как показано на рисунке, опубликованные выходные данные включают следующие файлы:</span><span class="sxs-lookup"><span data-stu-id="21433-129">As the image shows, the published output includes the following files:</span></span>

      * <span data-ttu-id="21433-130">*HelloWorld.deps.json*</span><span class="sxs-lookup"><span data-stu-id="21433-130">*HelloWorld.deps.json*</span></span>

         <span data-ttu-id="21433-131">Это файл зависимостей среды выполнения приложения.</span><span class="sxs-lookup"><span data-stu-id="21433-131">This is the application's runtime dependencies file.</span></span> <span data-ttu-id="21433-132">Он определяет библиотеки и компоненты .NET Core (включая библиотеку DLL, содержащую приложение), необходимые для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="21433-132">It defines the .NET Core components and the libraries (including the dynamic link library that contains your application) needed to run the app.</span></span> <span data-ttu-id="21433-133">Дополнительные сведения см. в разделе [Runtime Configuration Files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md) (Файлы конфигурации среды выполнения).</span><span class="sxs-lookup"><span data-stu-id="21433-133">For more information, see [Runtime configuration files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>

      * <span data-ttu-id="21433-134">*HelloWorld.dll*</span><span class="sxs-lookup"><span data-stu-id="21433-134">*HelloWorld.dll*</span></span>

         <span data-ttu-id="21433-135">Это версия [зависимого от платформы развертывания](../deploying/deploy-with-cli.md#framework-dependent-deployment) приложения.</span><span class="sxs-lookup"><span data-stu-id="21433-135">This is the [framework-dependent deployment](../deploying/deploy-with-cli.md#framework-dependent-deployment) version of the application.</span></span> <span data-ttu-id="21433-136">Чтобы выполнить эту библиотеку динамической компоновки, введите `dotnet HelloWorld.dll` в командной строке.</span><span class="sxs-lookup"><span data-stu-id="21433-136">To execute this dynamic link library, enter `dotnet HelloWorld.dll` at a command prompt.</span></span>

      * <span data-ttu-id="21433-137">*HelloWorld.exe*</span><span class="sxs-lookup"><span data-stu-id="21433-137">*HelloWorld.exe*</span></span>

         <span data-ttu-id="21433-138">Это версия [исполняемого, зависящего от платформы файла](../deploying/deploy-with-cli.md#framework-dependent-executable) приложения.</span><span class="sxs-lookup"><span data-stu-id="21433-138">This is the [framework-dependent executable](../deploying/deploy-with-cli.md#framework-dependent-executable) version of the application.</span></span> <span data-ttu-id="21433-139">Чтобы запустить его, введите `HelloWorld.exe` в командной строке.</span><span class="sxs-lookup"><span data-stu-id="21433-139">To run it, enter `HelloWorld.exe` at a command prompt.</span></span>

      * <span data-ttu-id="21433-140">*HelloWorld.pdb* (необязателен для развертывания)</span><span class="sxs-lookup"><span data-stu-id="21433-140">*HelloWorld.pdb* (optional for deployment)</span></span>

         <span data-ttu-id="21433-141">Это файл отладочных символов.</span><span class="sxs-lookup"><span data-stu-id="21433-141">This is the debug symbols file.</span></span> <span data-ttu-id="21433-142">Этот файл не нужно распространять вместе с приложением, но желательно сохранить его на случай, если придется выполнять отладку опубликованной версии приложения.</span><span class="sxs-lookup"><span data-stu-id="21433-142">You aren't required to deploy this file along with your application, although you should save it in the event that you need to debug the published version of your application.</span></span>

      * <span data-ttu-id="21433-143">*HelloWorld.runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="21433-143">*HelloWorld.runtimeconfig.json*</span></span>

         <span data-ttu-id="21433-144">Это файл конфигурации среды выполнения для приложения.</span><span class="sxs-lookup"><span data-stu-id="21433-144">This is the application's run-time configuration file.</span></span> <span data-ttu-id="21433-145">Он определяет версию платформы .NET Core, для которой предназначено приложение.</span><span class="sxs-lookup"><span data-stu-id="21433-145">It identifies the version of .NET Core that your application was built to run on.</span></span> <span data-ttu-id="21433-146">Кроме того, в него можно добавить параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="21433-146">You can also add configuration options to it.</span></span> <span data-ttu-id="21433-147">Дополнительные сведения см. в статье [Параметры конфигурации среды выполнения .NET Core](../run-time-config/index.md#runtimeconfigjson).</span><span class="sxs-lookup"><span data-stu-id="21433-147">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="21433-148">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="21433-148">Additional resources</span></span>

- [<span data-ttu-id="21433-149">Развертывание приложений .NET Core</span><span class="sxs-lookup"><span data-stu-id="21433-149">.NET Core application deployment</span></span>](../deploying/index.md)
