---
title: Учебник. Создание средства .NET Core
description: Сведения о создании средства .NET Core. Средство — это консольное приложение, которое устанавливается с помощью интерфейса командной строки .NET Core.
ms.date: 02/12/2020
ms.openlocfilehash: 88cc3be7b149834ace0c5f3ba8ac8c039199908f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "78156729"
---
# <a name="tutorial-create-a-net-core-tool-using-the-net-core-cli"></a><span data-ttu-id="05c04-104">Учебник. Создание средства .NET Core с помощью интерфейса командной строки .NET Core</span><span class="sxs-lookup"><span data-stu-id="05c04-104">Tutorial: Create a .NET Core tool using the .NET Core CLI</span></span>

<span data-ttu-id="05c04-105">**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="05c04-105">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="05c04-106">В этом учебнике объясняется, как создать и упаковать средство .NET Core.</span><span class="sxs-lookup"><span data-stu-id="05c04-106">This tutorial teaches you how to create and package a .NET Core tool.</span></span> <span data-ttu-id="05c04-107">Интерфейс командной строки .NET Core позволяет создавать консольное приложение в качестве средства, которое смогут установить и запустить другие пользователи.</span><span class="sxs-lookup"><span data-stu-id="05c04-107">The .NET Core CLI lets you create a console application as a tool, which others can install and run.</span></span> <span data-ttu-id="05c04-108">Средства .NET Core представляют собой пакеты NuGet, которые устанавливаются из командной строки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="05c04-108">.NET Core tools are NuGet packages that are installed from the .NET Core CLI.</span></span> <span data-ttu-id="05c04-109">Дополнительные сведения см. в статье [Обзор глобальных средств .NET Core](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="05c04-109">For more information about tools, see [.NET Core tools overview](global-tools.md).</span></span>

<span data-ttu-id="05c04-110">Создаваемое средство — это консольное приложение, которое принимает сообщение в качестве входных данных и отображает сообщение вместе со строками текста, которые создают образ робота.</span><span class="sxs-lookup"><span data-stu-id="05c04-110">The tool that you'll create is a console application that takes a message as input and displays the message along with lines of text that create the image of a robot.</span></span>

<span data-ttu-id="05c04-111">Это первый учебник из серии из трех частей.</span><span class="sxs-lookup"><span data-stu-id="05c04-111">This is the first in a series of three tutorials.</span></span> <span data-ttu-id="05c04-112">В этом руководстве описано, как создать и упаковать средство.</span><span class="sxs-lookup"><span data-stu-id="05c04-112">In this tutorial, you create and package a tool.</span></span> <span data-ttu-id="05c04-113">В следующих двух учебниках вы будете [использовать средство в качестве глобального средства](global-tools-how-to-use.md) и [использовать средство в качестве локального средства](local-tools-how-to-use.md).</span><span class="sxs-lookup"><span data-stu-id="05c04-113">In the next two tutorials you [use the tool as a global tool](global-tools-how-to-use.md) and [use the tool as a local tool](local-tools-how-to-use.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="05c04-114">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="05c04-114">Prerequisites</span></span>

- <span data-ttu-id="05c04-115">[Пакет SDK для .NET Core 3.1](https://dotnet.microsoft.com/download) или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="05c04-115">[.NET Core SDK 3.1](https://dotnet.microsoft.com/download) or a later version.</span></span>

  <span data-ttu-id="05c04-116">Этот и следующий [учебник по глобальным средствам](global-tools-how-to-use.md) применим к пакету SDK для .NET Core 2.1 и более поздних версий, поскольку глобальные средства доступны только начиная с этой версии.</span><span class="sxs-lookup"><span data-stu-id="05c04-116">This tutorial and the following [tutorial for global tools](global-tools-how-to-use.md) apply to .NET Core SDK 2.1 and later versions because global tools are available starting in that version.</span></span> <span data-ttu-id="05c04-117">Однако в этом учебнике предполагается, что вы установили версию 3.1 или более позднюю версию, чтобы иметь возможность перехода к [учебнику по работе с локальными средствами](local-tools-how-to-use.md).</span><span class="sxs-lookup"><span data-stu-id="05c04-117">But this tutorial assumes you have installed 3.1 or later so that you have the option of continuing on to the [local tools tutorial](local-tools-how-to-use.md).</span></span> <span data-ttu-id="05c04-118">Глобальные средства доступны в пакете SDK для .NET Core, начиная с версии 3.0.</span><span class="sxs-lookup"><span data-stu-id="05c04-118">Local tools are available starting in .NET Core SDK 3.0.</span></span> <span data-ttu-id="05c04-119">Процедуры создания средства одинаковы как для глобального так и локального средства.</span><span class="sxs-lookup"><span data-stu-id="05c04-119">The procedures for creating a tool are the same whether you use it as a global tool or as a local tool.</span></span>
  
- <span data-ttu-id="05c04-120">Текстовый редактор или редактор кода по вашему выбору.</span><span class="sxs-lookup"><span data-stu-id="05c04-120">A text editor or code editor of your choice.</span></span>

## <a name="create-a-project"></a><span data-ttu-id="05c04-121">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="05c04-121">Create a project</span></span>

1. <span data-ttu-id="05c04-122">Откройте командную строку и создайте папку с именем *репозиторий*.</span><span class="sxs-lookup"><span data-stu-id="05c04-122">Open a command prompt and create a folder named *repository*.</span></span>

1. <span data-ttu-id="05c04-123">Перейдите в папку *repository* и введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="05c04-123">Navigate to the *repository* folder and enter the following command:</span></span>

   ```dotnetcli
   dotnet new console -n microsoft.botsay
   ```

   <span data-ttu-id="05c04-124">Команда создает папку с именем *microsoft.botsay* в папке *repository*.</span><span class="sxs-lookup"><span data-stu-id="05c04-124">The command creates a new folder named *microsoft.botsay* under the *repository* folder.</span></span>

1. <span data-ttu-id="05c04-125">Перейдите в папку *microsoft.botsay*.</span><span class="sxs-lookup"><span data-stu-id="05c04-125">Navigate to the *microsoft.botsay* folder.</span></span>

   ```console
   cd microsoft.botsay
   ```

## <a name="add-the-code"></a><span data-ttu-id="05c04-126">Добавление кода</span><span class="sxs-lookup"><span data-stu-id="05c04-126">Add the code</span></span>

1. <span data-ttu-id="05c04-127">Откройте файл `Program.cs` с помощью редактора кода.</span><span class="sxs-lookup"><span data-stu-id="05c04-127">Open the `Program.cs` file with your code editor.</span></span>

1. <span data-ttu-id="05c04-128">Добавьте следующую директиву `using` в начало файла.</span><span class="sxs-lookup"><span data-stu-id="05c04-128">Add the following `using` directive to the top of the file:</span></span>

   ```csharp
   using System.Reflection;
   ```

1. <span data-ttu-id="05c04-129">Замените этот метод `Main` приведенным ниже кодом, который будет обрабатывать аргументы командной строки для приложения.</span><span class="sxs-lookup"><span data-stu-id="05c04-129">Replace the `Main` method with the following code to process the command-line arguments for the application.</span></span>

   ```csharp
   static void Main(string[] args)
   {
       if (args.Length == 0)
       {
           var versionString = Assembly.GetEntryAssembly()
                                   .GetCustomAttribute<AssemblyInformationalVersionAttribute>()
                                   .InformationalVersion
                                   .ToString();

           Console.WriteLine($"botsay v{versionString}");
           Console.WriteLine("-------------");
           Console.WriteLine("\nUsage:");
           Console.WriteLine("  botsay <message>");
           return;
       }

       ShowBot(string.Join(' ', args));
   }
   ```

   <span data-ttu-id="05c04-130">Если аргументы не переданы, отображается короткое справочное сообщение.</span><span class="sxs-lookup"><span data-stu-id="05c04-130">If no arguments are passed, a short help message is displayed.</span></span> <span data-ttu-id="05c04-131">В противном случае все аргументы объединяются в одну строку и выводятся путем вызова метода `ShowBot`, созданного на следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="05c04-131">Otherwise, all of the arguments are concatenated into a single string and printed by calling the `ShowBot` method that you create in the next step.</span></span>

1. <span data-ttu-id="05c04-132">Добавьте новый метод с именем `ShowBot`, который принимает один строковый параметр.</span><span class="sxs-lookup"><span data-stu-id="05c04-132">Add a new method named `ShowBot` that takes a string parameter.</span></span> <span data-ttu-id="05c04-133">Метод выводит сообщение и образ робота, используя строки текста.</span><span class="sxs-lookup"><span data-stu-id="05c04-133">The method prints out the message and an image of a robot using lines of text.</span></span>

   ```csharp
   static void ShowBot(string message)
   {
       string bot = $"\n        {message}";
       bot += @"
       __________________
                         \
                          \
                             ....
                             ....'
                              ....
                           ..........
                       .............'..'..
                    ................'..'.....
                  .......'..........'..'..'....
                 ........'..........'..'..'.....
                .'....'..'..........'..'.......'.
                .'..................'...   ......
                .  ......'.........         .....
                .    _            __        ......
               ..    #            ##        ......
              ....       .                 .......
              ......  .......          ............
               ................  ......................
               ........................'................
              ......................'..'......    .......
           .........................'..'.....       .......
        ........    ..'.............'..'....      ..........
      ..'..'...      ...............'.......      ..........
     ...'......     ...... ..........  ......         .......
    ...........   .......              ........        ......
   .......        '...'.'.              '.'.'.'         ....
   .......       .....'..               ..'.....
      ..       ..........               ..'........
             ............               ..............
            .............               '..............
           ...........'..              .'.'............
          ...............              .'.'.............
         .............'..               ..'..'...........
         ...............                 .'..............
          .........                        ..............
           .....
   ";
       Console.WriteLine(bot);
   }
   ```

1. <span data-ttu-id="05c04-134">Сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="05c04-134">Save your changes.</span></span>

## <a name="test-the-application"></a><span data-ttu-id="05c04-135">Тестирование приложения</span><span class="sxs-lookup"><span data-stu-id="05c04-135">Test the application</span></span>

<span data-ttu-id="05c04-136">Запустите проект и просмотрите выходные данные.</span><span class="sxs-lookup"><span data-stu-id="05c04-136">Run the project and see the output.</span></span> <span data-ttu-id="05c04-137">Поработайте с разными вариантами командной строки и сравните результаты.</span><span class="sxs-lookup"><span data-stu-id="05c04-137">Try these variations at the command line to see different results:</span></span>

```dotnetcli
dotnet run
dotnet run -- "Hello from the bot"
dotnet run -- Hello from the bot
```

<span data-ttu-id="05c04-138">Все аргументы после разделителя `--` передаются выполняемому приложению.</span><span class="sxs-lookup"><span data-stu-id="05c04-138">All arguments after the `--` delimiter are passed to your application.</span></span>

## <a name="package-the-tool"></a><span data-ttu-id="05c04-139">Упаковка средства</span><span class="sxs-lookup"><span data-stu-id="05c04-139">Package the tool</span></span>

<span data-ttu-id="05c04-140">Прежде чем упаковать и распространять приложение в качестве средства, измените файл проекта.</span><span class="sxs-lookup"><span data-stu-id="05c04-140">Before you can pack and distribute the application as a tool, you need to modify the project file.</span></span>

1. <span data-ttu-id="05c04-141">Откройте файл *microsoft.botsay.csproj* и добавьте три новых узла XML в конец узла `<PropertyGroup>`:</span><span class="sxs-lookup"><span data-stu-id="05c04-141">Open the *microsoft.botsay.csproj* file and add three new XML nodes to the end of the `<PropertyGroup>` node:</span></span>

   ```xml
   <PackAsTool>true</PackAsTool>
   <ToolCommandName>botsay</ToolCommandName>
   <PackageOutputPath>./nupkg</PackageOutputPath>
   ```

   <span data-ttu-id="05c04-142">`<ToolCommandName>` — это необязательный элемент, указывающий команду, которая будет вызывать средство после его установки.</span><span class="sxs-lookup"><span data-stu-id="05c04-142">`<ToolCommandName>` is an optional element that specifies the command that will invoke the tool after it's installed.</span></span> <span data-ttu-id="05c04-143">Если этот элемент не указан, имя команды для средства — это имя файла проекта без расширения *.csproj*.</span><span class="sxs-lookup"><span data-stu-id="05c04-143">If this element isn't provided, the command name for the tool is the project file name without the *.csproj* extension.</span></span>

   <span data-ttu-id="05c04-144">`<PackageOutputPath>` — это необязательный элемент, который определяет, где будет создан пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="05c04-144">`<PackageOutputPath>` is an optional element that determines where the NuGet package will be produced.</span></span> <span data-ttu-id="05c04-145">Пакет NuGet будет использоваться в интерфейсе командной строки .NET Core для установки средства.</span><span class="sxs-lookup"><span data-stu-id="05c04-145">The NuGet package is what the .NET Core CLI uses to install your tool.</span></span>

   <span data-ttu-id="05c04-146">Файл проекта выглядит так, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="05c04-146">The project file now looks like the following example:</span></span>

   ```xml
   <Project Sdk="Microsoft.NET.Sdk">
  
     <PropertyGroup>

       <OutputType>Exe</OutputType>
       <TargetFramework>netcoreapp3.1</TargetFramework>
  
       <PackAsTool>true</PackAsTool>
       <ToolCommandName>botsay</ToolCommandName>
       <PackageOutputPath>./nupkg</PackageOutputPath>
  
     </PropertyGroup>

   </Project>
   ```

1. <span data-ttu-id="05c04-147">Создайте пакет NuGet с помощью команды [dotnet pack](dotnet-pack.md):</span><span class="sxs-lookup"><span data-stu-id="05c04-147">Create a NuGet package by running the [dotnet pack](dotnet-pack.md) command:</span></span>

   ```dotnetcli
   dotnet pack
   ```

   <span data-ttu-id="05c04-148">Файл *microsoft.botsay.1.0.0.nupkg* создается в папке, которую указывает значение `<PackageOutputPath>` из файла *microsoft.botsay.csproj*. В нашем примере это папка *./nupkg*.</span><span class="sxs-lookup"><span data-stu-id="05c04-148">The *microsoft.botsay.1.0.0.nupkg* file is created in the folder identified by the `<PackageOutputPath>` value from the *microsoft.botsay.csproj* file, which in this example is the *./nupkg* folder.</span></span>
  
   <span data-ttu-id="05c04-149">Если вы решите сделать это средство общедоступным, его можно отправить в `https://www.nuget.org`.</span><span class="sxs-lookup"><span data-stu-id="05c04-149">When you want to release a tool publicly, you can upload it to `https://www.nuget.org`.</span></span> <span data-ttu-id="05c04-150">Когда это средство станет доступно в NuGet, разработчикам можно будет выполнить его установку, используя команду [dotnet tool install](dotnet-tool-install.md).</span><span class="sxs-lookup"><span data-stu-id="05c04-150">Once the tool is available on NuGet, developers can install the tool by using the [dotnet tool install](dotnet-tool-install.md) command.</span></span> <span data-ttu-id="05c04-151">В этом учебнике пакет устанавливается непосредственно из локальной папки *nupkg*, поэтому его не нужно передавать в NuGet.</span><span class="sxs-lookup"><span data-stu-id="05c04-151">For this tutorial you install the package directly from the local *nupkg* folder, so there's no need to upload the package to NuGet.</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="05c04-152">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="05c04-152">Troubleshoot</span></span>

<span data-ttu-id="05c04-153">Если при выполнении учебника появляется сообщение об ошибке, см. статью [Устранение неполадок при использовании средства .NET Core](troubleshoot-usage-issues.md).</span><span class="sxs-lookup"><span data-stu-id="05c04-153">If you get an error message while following the tutorial, see [Troubleshoot .NET Core tool usage issues](troubleshoot-usage-issues.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="05c04-154">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="05c04-154">Next steps</span></span>

<span data-ttu-id="05c04-155">В этом учебнике вы создали консольное приложение и упаковали его в качестве средства.</span><span class="sxs-lookup"><span data-stu-id="05c04-155">In this tutorial, you created a console application and packaged it as a tool.</span></span> <span data-ttu-id="05c04-156">Чтобы узнать, как использовать это средство в качестве глобального, перейдите к следующему учебнику.</span><span class="sxs-lookup"><span data-stu-id="05c04-156">To learn how to use the tool as a global tool, advance to the next tutorial.</span></span>

> [!div class="nextstepaction"]
> <span data-ttu-id="05c04-157">[Tutorial: Install and use a .NET Core global tool using the .NET Core CLI](global-tools-how-to-use.md) (Краткое руководство. Установка и использование глобального средства .NET Core с помощью CLI .NET Core)</span><span class="sxs-lookup"><span data-stu-id="05c04-157">[Install and use a global tool](global-tools-how-to-use.md)</span></span>

<span data-ttu-id="05c04-158">При желании вы можете пропустить учебник по глобальным средствам и перейти непосредственно к учебнику для локальных средств.</span><span class="sxs-lookup"><span data-stu-id="05c04-158">If you prefer, you can skip the global tools tutorial and go directly to the local tools tutorial.</span></span>

> [!div class="nextstepaction"]
> <span data-ttu-id="05c04-159">[Tutorial: Install and use a .NET Core local tool using the .NET Core CLI](local-tools-how-to-use.md) (Краткое руководство. Установка и использование локального средства .NET Core с помощью CLI .NET Core)</span><span class="sxs-lookup"><span data-stu-id="05c04-159">[Install and use a local tool](local-tools-how-to-use.md)</span></span>
