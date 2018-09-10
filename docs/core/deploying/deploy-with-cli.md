---
title: Развертывание приложений .NET Core с помощью средств интерфейса командной строки
description: Сведения о развертывании приложений .NET Core с помощью средств интерфейса командной строки (CLI)
author: rpetrusha
ms.author: ronpet
ms.date: 04/18/2017
ms.openlocfilehash: dbef9d91aa4e7af8e6e0ed2d8f361238385d4976
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43855026"
---
# <a name="deploying-net-core-apps-with-command-line-interface-cli-tools"></a><span data-ttu-id="af563-103">Развертывание приложений .NET Core с помощью средств командной строки (CLI)</span><span class="sxs-lookup"><span data-stu-id="af563-103">Deploying .NET Core apps with command-line interface (CLI) tools</span></span>

<span data-ttu-id="af563-104">Приложение .NET Core можно развернуть как *развертывание, зависящее от платформы*, которое содержит двоичные файлы приложений, но зависит от наличия .NET Core в целевой системе, или как *автономное развертывание*, которое содержит и приложение, и двоичные файлы .NET Core.</span><span class="sxs-lookup"><span data-stu-id="af563-104">You can deploy a .NET Core application either as a *framework-dependent deployment*, which includes your application binaries but depends on the presence of .NET Core on the target system, or as a *self-contained deployment*, which includes both your application and the .NET Core binaries.</span></span> <span data-ttu-id="af563-105">Общие сведения см. в разделе [Развертывание приложений .NET Core](index.md).</span><span class="sxs-lookup"><span data-stu-id="af563-105">For an overview, see [.NET Core Application Deployment](index.md).</span></span>

<span data-ttu-id="af563-106">В разделах ниже содержатся сведения об использовании [средств интерфейса командной строки .NET Core](../tools/index.md) для создания следующих типов развертывания:</span><span class="sxs-lookup"><span data-stu-id="af563-106">The following sections show how to use [.NET Core command-line interface tools](../tools/index.md) to create the following kinds of deployments:</span></span>

- <span data-ttu-id="af563-107">развертывание, зависящее от платформы;</span><span class="sxs-lookup"><span data-stu-id="af563-107">Framework-dependent deployment</span></span>
- <span data-ttu-id="af563-108">развертывание, зависящее от платформы, с зависимостями сторонних разработчиков;</span><span class="sxs-lookup"><span data-stu-id="af563-108">Framework-dependent deployment with third-party dependencies</span></span>
- <span data-ttu-id="af563-109">автономное развертывание;</span><span class="sxs-lookup"><span data-stu-id="af563-109">Self-contained deployment</span></span>
- <span data-ttu-id="af563-110">Автономное развертывание с зависимостями сторонних разработчиков</span><span class="sxs-lookup"><span data-stu-id="af563-110">Self-contained deployment with third-party dependencies</span></span>

<span data-ttu-id="af563-111">При работе из командной строки можно использовать выбранный по своему усмотрению редактор кода.</span><span class="sxs-lookup"><span data-stu-id="af563-111">When working from the command line, you can use a program editor of your choice.</span></span> <span data-ttu-id="af563-112">Если в качестве редактора используется [Visual Studio Code](https://code.visualstudio.com), можно открыть консоль командной строки в среде Visual Studio Code, выбрав **Вид** > **Интегрированный терминал**.</span><span class="sxs-lookup"><span data-stu-id="af563-112">If your program editor is [Visual Studio Code](https://code.visualstudio.com), you can open a command console inside your Visual Studio Code environment by selecting **View** > **Integrated Terminal**.</span></span>

## <a name="framework-dependent-deployment"></a><span data-ttu-id="af563-113">развертывание, зависящее от платформы;</span><span class="sxs-lookup"><span data-stu-id="af563-113">Framework-dependent deployment</span></span>

<span data-ttu-id="af563-114">Если развертывание, зависящее от платформы, не содержит зависимостей сторонних разработчиков, то необходимо просто выполнить сборку, протестировать и опубликовать приложение.</span><span class="sxs-lookup"><span data-stu-id="af563-114">Deploying a framework-dependent deployment with no third-party dependencies simply involves building, testing, and publishing the app.</span></span> <span data-ttu-id="af563-115">Проиллюстрируем этот процесс на примере простого приложения, написанного на языке C#.</span><span class="sxs-lookup"><span data-stu-id="af563-115">A simple example written in C# illustrates the process.</span></span>

1. <span data-ttu-id="af563-116">Создайте каталог проекта.</span><span class="sxs-lookup"><span data-stu-id="af563-116">Create a project directory.</span></span>

   <span data-ttu-id="af563-117">Создайте каталог для проекта и сделайте его текущим каталогом.</span><span class="sxs-lookup"><span data-stu-id="af563-117">Create a directory for your project and make it your current directory.</span></span>

1. <span data-ttu-id="af563-118">создание проекта;</span><span class="sxs-lookup"><span data-stu-id="af563-118">Create the project.</span></span>

   <span data-ttu-id="af563-119">В командной строке введите [dotnet new](../tools/dotnet-new.md), чтобы создать проект консольного приложения C# в этом каталоге.</span><span class="sxs-lookup"><span data-stu-id="af563-119">From the command line, type [dotnet new console](../tools/dotnet-new.md) to create a new C# console project in that directory.</span></span>

1. <span data-ttu-id="af563-120">Добавление исходного кода приложения.</span><span class="sxs-lookup"><span data-stu-id="af563-120">Add the application's source code.</span></span>

   <span data-ttu-id="af563-121">Откройте файл *Program.cs* в редакторе и замените автоматически созданный код приведенным ниже кодом.</span><span class="sxs-lookup"><span data-stu-id="af563-121">Open the *Program.cs* file in your editor and replace the auto-generated code with the following code.</span></span> <span data-ttu-id="af563-122">Он выводит запрос на ввод текста и отображает отдельные слова, введенные пользователем.</span><span class="sxs-lookup"><span data-stu-id="af563-122">It prompts the user to enter text and displays the individual words entered by the user.</span></span> <span data-ttu-id="af563-123">Для разделения слов во введенном тексте в нем используется регулярное выражение `\w+`.</span><span class="sxs-lookup"><span data-stu-id="af563-123">It uses the regular expression `\w+` to separate the words in the input text.</span></span>

   [!code-csharp[deployment#1](../../../samples/snippets/core/deploying/deployment-example.cs)]

1. <span data-ttu-id="af563-124">Обновление зависимостей и средств проекта.</span><span class="sxs-lookup"><span data-stu-id="af563-124">Update the project's dependencies and tools.</span></span>

   <span data-ttu-id="af563-125">Запустите [dotnet restore](../tools/dotnet-restore.md) ([см. Примечание](#dotnet-restore-note)) для восстановления зависимостей, указанных в проекте.</span><span class="sxs-lookup"><span data-stu-id="af563-125">Run the [dotnet restore](../tools/dotnet-restore.md) ([see note](#dotnet-restore-note)) command to restore the dependencies specified in your project.</span></span>

1. <span data-ttu-id="af563-126">Создание отладочной сборки приложения.</span><span class="sxs-lookup"><span data-stu-id="af563-126">Create a Debug build of your app.</span></span>

   <span data-ttu-id="af563-127">Используйте команду [dotnet build](../tools/dotnet-build.md), чтобы построить приложение, или команду [dotnet run](../tools/dotnet-run.md), чтобы построить приложение и запустить его.</span><span class="sxs-lookup"><span data-stu-id="af563-127">Use the [dotnet build](../tools/dotnet-build.md) command to build your application or the [dotnet run](../tools/dotnet-run.md) command to build and run it.</span></span>

1. <span data-ttu-id="af563-128">Развертывание приложения.</span><span class="sxs-lookup"><span data-stu-id="af563-128">Deploy your app.</span></span>

   <span data-ttu-id="af563-129">После отладки и тестирования программы создайте развертывание с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="af563-129">After you've debugged and tested the program, create the deployment by using the following command:</span></span>

      ```console
      dotnet publish -f netcoreapp1.1 -c Release
      ```
   <span data-ttu-id="af563-130">При этом создается версия выпуска приложения (а не отладочная версия).</span><span class="sxs-lookup"><span data-stu-id="af563-130">This creates a Release (rather than a Debug) version of your app.</span></span> <span data-ttu-id="af563-131">Итоговые файлы помещаются в каталог с именем *publish*, который находится в подкаталоге каталога *bin* проекта.</span><span class="sxs-lookup"><span data-stu-id="af563-131">The resulting files are placed in a directory named *publish*      that's in a subdirectory of your project's *bin* directory.</span></span>

   <span data-ttu-id="af563-132">Помимо файлов приложения, процесс публикации создает файл базы данных программы (PDB), который содержит отладочную информацию о приложении.</span><span class="sxs-lookup"><span data-stu-id="af563-132">Along with your application's files, the publishing process emits a program database (.pdb) file that contains debugging information about your app.</span></span> <span data-ttu-id="af563-133">Файл используется в основном для отладки исключений.</span><span class="sxs-lookup"><span data-stu-id="af563-133">The file is useful primarily for debugging exceptions.</span></span> <span data-ttu-id="af563-134">Его можно не распространять вместе с файлами приложения.</span><span class="sxs-lookup"><span data-stu-id="af563-134">You can choose not to distribute it with your application's files.</span></span> <span data-ttu-id="af563-135">Однако его следует сохранить на случай, если потребуется выполнить отладку сборки выпуска приложения.</span><span class="sxs-lookup"><span data-stu-id="af563-135">You should, however, save it in the event that you want to debug the Release build of your app.</span></span>

   <span data-ttu-id="af563-136">Полный набор файлов приложения можно развернуть любым способом, каким вы хотите.</span><span class="sxs-lookup"><span data-stu-id="af563-136">You can deploy the complete set of application files in any way you like.</span></span> <span data-ttu-id="af563-137">Например, их можно упаковать в ZIP-файл, использовать простую команду `copy` или развернуть их с помощью любого установочного пакета на ваш выбор.</span><span class="sxs-lookup"><span data-stu-id="af563-137">For example, you can package them in a Zip file, use a simple `copy` command, or deploy them with any installation package of your choice.</span></span>

1. <span data-ttu-id="af563-138">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="af563-138">Run your app</span></span>

   <span data-ttu-id="af563-139">После установки пользователи могут выполнять приложение с помощью команды `dotnet`, указав имя файла приложения, например `dotnet fdd.dll`.</span><span class="sxs-lookup"><span data-stu-id="af563-139">Once installed, users can execute your application by using the `dotnet` command and providing the application filename, such as `dotnet fdd.dll`.</span></span>

   <span data-ttu-id="af563-140">Помимо двоичных файлов приложения, установщик должен либо включать в себя установщик общей платформы, либо проверять наличие платформы в процессе установки приложения.</span><span class="sxs-lookup"><span data-stu-id="af563-140">In addition to the application binaries, your installer should also either bundle the shared framework installer or check for it as a prerequisite as part of the application installation.</span></span>  <span data-ttu-id="af563-141">Установка общей платформы требует наличия прав администратора или прав root.</span><span class="sxs-lookup"><span data-stu-id="af563-141">Installation of the shared framework requires Administrator/root access.</span></span>

## <a name="framework-dependent-deployment-with-third-party-dependencies"></a><span data-ttu-id="af563-142">Развертывание, зависящее от платформы, с зависимостями сторонних разработчиков</span><span class="sxs-lookup"><span data-stu-id="af563-142">Framework-dependent deployment with third-party dependencies</span></span>

<span data-ttu-id="af563-143">Для зависящего от платформы развертывания с одной или более зависимостями сторонних разработчиков требуется, чтобы эти зависимости были доступны в проекте.</span><span class="sxs-lookup"><span data-stu-id="af563-143">Deploying a framework-dependent deployment with one or more third-party dependencies requires that those dependencies be available to your project.</span></span> <span data-ttu-id="af563-144">Требуется выполнить два дополнительных шага, прежде чем запускать команду `dotnet restore` ([см. Примечание](#dotnet-restore-note)):</span><span class="sxs-lookup"><span data-stu-id="af563-144">Two additional steps are required before you can run the `dotnet restore` ([see note](#dotnet-restore-note)) command:</span></span>

1. <span data-ttu-id="af563-145">Добавьте ссылки на требуемые библиотеки сторонних разработчиков в раздел `<ItemGroup>` файла *csproj*.</span><span class="sxs-lookup"><span data-stu-id="af563-145">Add references to required third-party libraries to the `<ItemGroup>` section of your *csproj* file.</span></span> <span data-ttu-id="af563-146">В следующем разделе `<ItemGroup>` в качестве библиотеки стороннего разработчика используется зависимость от [Json.NET](http://www.newtonsoft.com/json).</span><span class="sxs-lookup"><span data-stu-id="af563-146">The following `<ItemGroup>` section contains a dependency on [Json.NET](http://www.newtonsoft.com/json) as a third-party library:</span></span>

      ```xml
      <ItemGroup>
        <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
      </ItemGroup>
      ```

1. <span data-ttu-id="af563-147">Скачайте пакет NuGet, содержащий зависимость стороннего разработчика, в систему, если вы этого еще не сделали.</span><span class="sxs-lookup"><span data-stu-id="af563-147">If you haven't already, download the NuGet package containing the third-party dependency.</span></span> <span data-ttu-id="af563-148">Чтобы скачать пакет, выполните команду `dotnet restore` ([см. примечание](#dotnet-restore-note)) после добавления зависимости.</span><span class="sxs-lookup"><span data-stu-id="af563-148">To download the package, execute the `dotnet restore` ([see note](#dotnet-restore-note)) command after adding the dependency.</span></span> <span data-ttu-id="af563-149">Так как зависимость разрешается из локального кэша NuGet во время публикации, она должна быть доступна в системе.</span><span class="sxs-lookup"><span data-stu-id="af563-149">Because the dependency is resolved out of the local NuGet cache at publish time, it must be available on your system.</span></span>

<span data-ttu-id="af563-150">Имейте в виду, что переносимость зависящего от платформы развертывания с зависимостями сторонних разработчиков напрямую зависит от переносимости этих зависимостей.</span><span class="sxs-lookup"><span data-stu-id="af563-150">Note that a framework-dependent deployment with third-party dependencies is only as portable as its third-party dependencies.</span></span> <span data-ttu-id="af563-151">Например, если библиотека стороннего разработчика поддерживает только Mac OS, приложение нельзя перенести в системы Windows.</span><span class="sxs-lookup"><span data-stu-id="af563-151">For example, if a third-party library only supports macOS, the app isn't portable to Windows systems.</span></span> <span data-ttu-id="af563-152">Это происходит, если зависимость стороннего разработчика сама зависит от машинного кода.</span><span class="sxs-lookup"><span data-stu-id="af563-152">This happens if the third-party dependency itself depends on native code.</span></span> <span data-ttu-id="af563-153">Хорошим примером является [сервер Kestrel](/aspnet/core/fundamentals/servers/kestrel), требующий собственной зависимости от [libuv](https://github.com/libuv/libuv).</span><span class="sxs-lookup"><span data-stu-id="af563-153">A good example of this is [Kestrel server](/aspnet/core/fundamentals/servers/kestrel), which requires a native dependency on [libuv](https://github.com/libuv/libuv).</span></span> <span data-ttu-id="af563-154">Когда зависящее от платформы развертывание создается для приложения с таким типом зависимости стороннего разработчика, опубликованные выходные данные содержат папку для каждого [идентификатора среды выполнения (RID)](../rid-catalog.md), поддерживаемого зависимостью (и имеющегося в ее пакете NuGet).</span><span class="sxs-lookup"><span data-stu-id="af563-154">When an FDD is created for an application with this kind of third-party dependency, the published output contains a folder for each [Runtime Identifier (RID)](../rid-catalog.md) that the native dependency supports (and that exists in its NuGet package).</span></span>

## <a name="simpleSelf"></a> <span data-ttu-id="af563-155">Автономное развертывание без зависимостей сторонних разработчиков</span><span class="sxs-lookup"><span data-stu-id="af563-155">Self-contained deployment without third-party dependencies</span></span>

<span data-ttu-id="af563-156">Выполнение автономного развертывания без зависимостей сторонних разработчиков предполагает создание проекта, изменение файла *csproj*, сборку, тестирование и публикацию приложения.</span><span class="sxs-lookup"><span data-stu-id="af563-156">Deploying a self-contained deployment without third-party dependencies involves creating the project, modifying the *csproj* file, building, testing, and publishing the app.</span></span> <span data-ttu-id="af563-157">Проиллюстрируем этот процесс на примере простого приложения, написанного на языке C#.</span><span class="sxs-lookup"><span data-stu-id="af563-157">A simple example written in C# illustrates the process.</span></span> <span data-ttu-id="af563-158">В примере показано создание автономного развертывания с помощью [dotnet utility](../tools/dotnet.md) из командной строки.</span><span class="sxs-lookup"><span data-stu-id="af563-158">The example shows how to create a self-contained deployment using the [dotnet utility](../tools/dotnet.md) from the command line.</span></span>

1. <span data-ttu-id="af563-159">Создайте каталог для проекта.</span><span class="sxs-lookup"><span data-stu-id="af563-159">Create a directory for the project.</span></span>

   <span data-ttu-id="af563-160">Создайте каталог для проекта и сделайте его текущим каталогом.</span><span class="sxs-lookup"><span data-stu-id="af563-160">Create a directory for your project, and make it your current directory.</span></span>

1. <span data-ttu-id="af563-161">Создание проекта.</span><span class="sxs-lookup"><span data-stu-id="af563-161">Create the project.</span></span>

   <span data-ttu-id="af563-162">В командной строке введите [dotnet new](../tools/dotnet-new.md), чтобы создать проект консольного приложения C# в этом каталоге.</span><span class="sxs-lookup"><span data-stu-id="af563-162">From the command line, type [dotnet new console](../tools/dotnet-new.md) to create a new C# console project in that directory.</span></span>

1. <span data-ttu-id="af563-163">Добавление исходного кода приложения.</span><span class="sxs-lookup"><span data-stu-id="af563-163">Add the application's source code.</span></span>

   <span data-ttu-id="af563-164">Откройте файл *Program.cs* в редакторе и замените автоматически созданный код приведенным ниже кодом.</span><span class="sxs-lookup"><span data-stu-id="af563-164">Open the *Program.cs* file in your editor and replace the auto-generated code with the following code.</span></span> <span data-ttu-id="af563-165">Он выводит запрос на ввод текста и отображает отдельные слова, введенные пользователем.</span><span class="sxs-lookup"><span data-stu-id="af563-165">It prompts the user to enter text and displays the individual words entered by the user.</span></span> <span data-ttu-id="af563-166">Для разделения слов во введенном тексте в нем используется регулярное выражение `\w+`.</span><span class="sxs-lookup"><span data-stu-id="af563-166">It uses the regular expression `\w+` to separate the words in the input text.</span></span>

   [!code-csharp[deployment#1](../../../samples/snippets/core/deploying/deployment-example.cs)]

1. <span data-ttu-id="af563-167">Определение платформ, для которых будет предназначено приложение.</span><span class="sxs-lookup"><span data-stu-id="af563-167">Define the platforms that your app will target.</span></span>

   <span data-ttu-id="af563-168">В разделе `<PropertyGroup>` файла *csproj* создайте тег `<RuntimeIdentifiers>`, определяющий платформы, для которых предназначено приложение, и укажите идентификатор среды выполнения (RID) для каждой целевой платформы.</span><span class="sxs-lookup"><span data-stu-id="af563-168">Create a `<RuntimeIdentifiers>` tag in the `<PropertyGroup>` section of your *csproj* file that defines the platforms your app targets and specify the runtime identifier (RID) for each platform that you target.</span></span> <span data-ttu-id="af563-169">Обратите внимание, что для разделения идентификаторов RID необходимо добавлять точку с запятой.</span><span class="sxs-lookup"><span data-stu-id="af563-169">Note that you also need to add a semicolon to separate the RIDs.</span></span> <span data-ttu-id="af563-170">Список идентификаторов сред выполнения см. в [каталоге идентификаторов сред выполнения](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="af563-170">See [Runtime IDentifier catalog](../rid-catalog.md) for a list of runtime identifiers.</span></span>

   <span data-ttu-id="af563-171">Например, приведенный ниже раздел `<PropertyGroup>` указывает, что приложение выполняется в 64-разрядной операционной системе Windows 10 и в 64-разрядной операционной системе OS X 10.11.</span><span class="sxs-lookup"><span data-stu-id="af563-171">For example, the following `<PropertyGroup>` section indicates that the app runs on 64-bit Windows 10 operating systems and the 64-bit OS X Version 10.11 operating system.</span></span>

     ```xml
     <PropertyGroup>
         <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
     </PropertyGroup>
     ```

   <span data-ttu-id="af563-172">Обратите внимание, что элемент `<RuntimeIdentifiers>` может находиться в любом разделе `<PropertyGroup>` в файле *csproj*.</span><span class="sxs-lookup"><span data-stu-id="af563-172">Note that the `<RuntimeIdentifiers>` element can appear in any `<PropertyGroup>` in your *csproj* file.</span></span> <span data-ttu-id="af563-173">Полный пример файла *csproj* будет приведен далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="af563-173">A complete sample *csproj* file appears later in this section.</span></span>

1. <span data-ttu-id="af563-174">Обновление зависимостей и средств проекта.</span><span class="sxs-lookup"><span data-stu-id="af563-174">Update the project's dependencies and tools.</span></span>

   <span data-ttu-id="af563-175">Запустите [dotnet restore](../tools/dotnet-restore.md) ([см. Примечание](#dotnet-restore-note)) для восстановления зависимостей, указанных в проекте.</span><span class="sxs-lookup"><span data-stu-id="af563-175">Run the [dotnet restore](../tools/dotnet-restore.md) ([see note](#dotnet-restore-note)) command to restore the dependencies specified in your project.</span></span>

1. <span data-ttu-id="af563-176">Создание отладочной сборки приложения.</span><span class="sxs-lookup"><span data-stu-id="af563-176">Create a Debug build of your app.</span></span>

   <span data-ttu-id="af563-177">Из командной строки запустите команду [dotnet build](../tools/dotnet-build.md).</span><span class="sxs-lookup"><span data-stu-id="af563-177">From the command line, use the [dotnet build](../tools/dotnet-build.md) command.</span></span>

1. <span data-ttu-id="af563-178">Отладив и протестировав программу, создайте файлы, которые будут развертываться с приложением, для каждой целевой платформы.</span><span class="sxs-lookup"><span data-stu-id="af563-178">After you've debugged and tested the program, create the files to be deployed with your app for each platform that it targets.</span></span>

   <span data-ttu-id="af563-179">Используйте команду `dotnet publish` для обеих платформ, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="af563-179">Use the `dotnet publish` command for both target platforms as follows:</span></span>

      ```console
      dotnet publish -c Release -r win10-x64
      dotnet publish -c Release -r osx.10.11-x64
      ```

   <span data-ttu-id="af563-180">При этом создается версия выпуска приложения (а не отладочная версия) для каждой целевой платформы.</span><span class="sxs-lookup"><span data-stu-id="af563-180">This creates a Release (rather than a Debug) version of your app for each target platform.</span></span> <span data-ttu-id="af563-181">Итоговые файлы помещаются в подкаталог с именем *publish*, который находится в подкаталоге *.\bin\Release\netcoreapp1.1 \<идентификатор_среды_выполнения>* каталога проекта.</span><span class="sxs-lookup"><span data-stu-id="af563-181">The resulting files are placed in a subdirectory named *publish* that's in a subdirectory of your project's *.\bin\Release\netcoreapp1.1\<runtime_identifier>* subdirectory.</span></span> <span data-ttu-id="af563-182">Обратите внимание на то, что каждый подкаталог содержит полный набор файлов (как файлов приложения, так и всех файлов .NET Core), необходимых для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="af563-182">Note that each subdirectory contains the complete set of files (both your app files and all .NET Core files) needed to launch your app.</span></span>

<span data-ttu-id="af563-183">Помимо файлов приложения, процесс публикации создает файл базы данных программы (PDB), который содержит отладочную информацию о приложении.</span><span class="sxs-lookup"><span data-stu-id="af563-183">Along with your application's files, the publishing process emits a program database (.pdb) file that contains debugging information about your app.</span></span> <span data-ttu-id="af563-184">Файл используется в основном для отладки исключений.</span><span class="sxs-lookup"><span data-stu-id="af563-184">The file is useful primarily for debugging exceptions.</span></span> <span data-ttu-id="af563-185">Его можно не упаковывать вместе с файлами приложения.</span><span class="sxs-lookup"><span data-stu-id="af563-185">You can choose not to package it with your application's files.</span></span> <span data-ttu-id="af563-186">Однако его следует сохранить на случай, если потребуется выполнить отладку сборки выпуска приложения.</span><span class="sxs-lookup"><span data-stu-id="af563-186">You should, however, save it in the event that you want to debug the Release build of your app.</span></span>

<span data-ttu-id="af563-187">Разверните опубликованные файлы любым способом.</span><span class="sxs-lookup"><span data-stu-id="af563-187">Deploy the published files in any way you like.</span></span> <span data-ttu-id="af563-188">Например, их можно упаковать в ZIP-файл, использовать простую команду `copy` или развернуть их с помощью любого установочного пакета на ваш выбор.</span><span class="sxs-lookup"><span data-stu-id="af563-188">For example, you can package them in a Zip file, use a simple `copy` command, or deploy them with any installation package of your choice.</span></span>

<span data-ttu-id="af563-189">Ниже приведено полное содержимое файла *csproj* для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="af563-189">The following is the complete *csproj* file for this project.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

## <a name="self-contained-deployment-with-third-party-dependencies"></a><span data-ttu-id="af563-190">автономное развертывание с зависимостями сторонних разработчиков;</span><span class="sxs-lookup"><span data-stu-id="af563-190">Self-contained deployment with third-party dependencies</span></span>

<span data-ttu-id="af563-191">Выполнение автономного развертывания с одной или несколькими зависимостями сторонних разработчиков предполагает добавление этих зависимостей.</span><span class="sxs-lookup"><span data-stu-id="af563-191">Deploying a self-contained deployment with one or more third-party dependencies involves adding the dependencies.</span></span> <span data-ttu-id="af563-192">Требуется выполнить два дополнительных шага, прежде чем запускать команду `dotnet restore` ([см. Примечание](#dotnet-restore-note)):</span><span class="sxs-lookup"><span data-stu-id="af563-192">Two additional steps are required before you can run the `dotnet restore` ([see note](#dotnet-restore-note)) command:</span></span>

1. <span data-ttu-id="af563-193">Добавьте ссылки на библиотеки сторонних разработчиков в раздел `<ItemGroup>` файла *csproj*.</span><span class="sxs-lookup"><span data-stu-id="af563-193">Add references to any third-party libraries to the `<ItemGroup>` section of your *csproj* file.</span></span> <span data-ttu-id="af563-194">В следующем разделе `<ItemGroup>` в качестве библиотеки стороннего разработчика используется библиотека Json.NET.</span><span class="sxs-lookup"><span data-stu-id="af563-194">The following `<ItemGroup>` section uses Json.NET as a third-party library.</span></span>

    ```xml
      <ItemGroup>
        <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
      </ItemGroup>
    ```

1. <span data-ttu-id="af563-195">Скачайте пакет NuGet, содержащий зависимость стороннего разработчика, в систему, если вы этого еще не сделали.</span><span class="sxs-lookup"><span data-stu-id="af563-195">If you haven't already, download the NuGet package containing the third-party dependency to your system.</span></span> <span data-ttu-id="af563-196">Чтобы сделать зависимость доступной для приложения, выполните команду `dotnet restore` ([см. Примечание](#dotnet-restore-note)) после ее добавления.</span><span class="sxs-lookup"><span data-stu-id="af563-196">To make the dependency available to your app, execute the `dotnet restore` ([see note](#dotnet-restore-note)) command after adding the dependency.</span></span> <span data-ttu-id="af563-197">Так как зависимость разрешается из локального кэша NuGet во время публикации, она должна быть доступна в системе.</span><span class="sxs-lookup"><span data-stu-id="af563-197">Because the dependency is resolved out of the local NuGet cache at publish time, it must be available on your system.</span></span>

<span data-ttu-id="af563-198">Ниже приведено полное содержимое файла *csproj* для этого проекта:</span><span class="sxs-lookup"><span data-stu-id="af563-198">The following is the complete *csproj* file for this project:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="af563-199">При развертывании приложения все зависимости сторонних разработчиков, используемые в нем, также содержатся в файлах приложения.</span><span class="sxs-lookup"><span data-stu-id="af563-199">When you deploy your application, any third-party dependencies used in your app are also contained with your application files.</span></span> <span data-ttu-id="af563-200">Библиотеки сторонних разработчиков не требуются в системе, в которой выполняется приложение.</span><span class="sxs-lookup"><span data-stu-id="af563-200">Third-party libraries aren't required on the system on which the app is running.</span></span>

<span data-ttu-id="af563-201">Имейте в виду, что автономное развертывание с библиотекой стороннего разработчика возможно только на платформах, которые поддерживаются этой библиотекой.</span><span class="sxs-lookup"><span data-stu-id="af563-201">Note that you can only deploy a self-contained deployment with a third-party library to platforms supported by that library.</span></span> <span data-ttu-id="af563-202">Это похоже на наличие сторонних зависимостей с собственными зависимостями в развертывании, зависящем от платформы, где собственные зависимости должны быть совместимы с платформой, на которой развертывается приложение.</span><span class="sxs-lookup"><span data-stu-id="af563-202">This is similar to having third-party dependencies with native dependencies in a framework-dependent deployment, where the native dependencies must be compatible with the platform to which the app is deployed.</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

## <a name="see-also"></a><span data-ttu-id="af563-203">См. также</span><span class="sxs-lookup"><span data-stu-id="af563-203">See also</span></span>

* [<span data-ttu-id="af563-204">Развертывание приложений .NET Core</span><span class="sxs-lookup"><span data-stu-id="af563-204">.NET Core Application Deployment</span></span>](index.md)
* [<span data-ttu-id="af563-205">Каталог идентификаторов сред выполнения (RID) в .NET Core</span><span class="sxs-lookup"><span data-stu-id="af563-205">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
