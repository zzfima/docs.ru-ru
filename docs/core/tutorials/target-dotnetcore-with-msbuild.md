---
title: "Использование системы MSBuild для сборки проектов .NET Core"
description: "Использование системы MSBuild для сборки проектов .NET Core"
keywords: .NET, .NET Core
author: dsplaisted
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 13c66464-4f14-4db6-aa8b-06f25e7ba894
translationtype: Human Translation
ms.sourcegitcommit: a04755da6417bb28bad5f28a18ead9feeba2d957
ms.openlocfilehash: 5d37e78be88828d6c82777f96b6334903aecbe53

---

# <a name="using-msbuild-to-build-net-core-projects"></a>Использование системы MSBuild для сборки проектов .NET Core

Средства .NET Core будут [переводиться с использования файлов project.json на проекты на основе MSBuild](https://blogs.msdn.microsoft.com/dotnet/2016/05/23/changes-to-project-json/).
Мы планируем, что первая версия средств .NET Core, использующих систему MSBuild, будет входить в состав следующей версии Visual Studio.  Однако использовать систему MSBuild для проектов .NET Core можно уже сейчас, как описывается в этом разделе.

Мы рекомендуем большинству разработчиков, которые создают *новые* проекты, предназначенные для .NET Core, использовать файлы project.json (способ по умолчанию) по указанным ниже причинам:

- Система MSBuild пока не поддерживает многие преимущества файлов project.json.
- Многие средства на основе ASP.NET в настоящее время не работают с проектами MSBuild.
- Когда мы выпустим средства .NET Core, использующие MSBuild, проекты на основе project.json можно будет автоматически преобразовать в проекты MSBuild. 

Систему MSBuild можно применять для нацеливания на .NET Core уже существующих проектов, которые уже используют MSBuild и которые нужно перенести в .NET Core, или если вы используете расширяемость MSBuild при сборке для сценариев, которые плохо поддерживаются проектами на основе файлов project.json.

## <a name="prerequisites"></a>Предварительные требования

- [Visual Studio 2015 с обновлением 3](https://www.visualstudio.com/en-us/news/releasenotes/vs2015-update3-vs) или более поздней версии
- [Средства .NET Core для Visual Studio 2015](https://www.visualstudio.com/downloads/download-visual-studio-vs)
- Расширение NuGet для Visual Studio [бета-версии 3.5.0](https://dist.nuget.org/visualstudio-2015-vsix/v3.5.0-beta/NuGet.Tools.vsix) или более поздней

## <a name="creating-a-library-targeting-net-core"></a>Создание библиотеки, предназначенной для .NET Core

1. В строке меню Visual Studio выберите **Файл** | **Создать ** | **Проект**, а затем выберите пункт **Библиотека классов (переносимая)**.

  ![Создание проекта](./media/target-dotnetcore-with-msbuild/new-project-dialog-class-library-portable.png)

2. Выберите имя и расположение проекта, а затем нажмите кнопку **ОК**.

3. Появится диалоговое окно "Добавление переносимой библиотеки классов".  Выберите **.NET Framework 4.6** и **ASP.NET Core 1.0** в качестве целевых платформ и нажмите кнопку **ОК**.

  ![Диалоговое окно со списком целевых платформ](./media/target-dotnetcore-with-msbuild/pcl-targets-dialog-net46-aspnetcore10.png)

4. В обозревателе решений щелкните проект правой кнопкой мыши и выберите пункт **Свойства**.
5. На вкладке **Библиотека** окна свойств проекта щелкните ссылку **Нацелить на стандартную платформу .NET** и нажмите кнопку **Да** в появившемся диалоговом окне.
6. Откройте файл `project.json` в проекте и внесите указанные ниже изменения:
    - Измените номер версии пакета `NETStandard.Library` на `1.6.0` (это версия пакета в .NET Core 1.0).
    - Добавьте приведенное ниже определение `imports` внутри определения платформы `netstandard1.6`.  Это позволит проекту ссылаться на совместимые с .NET Core пакеты NuGet, которые не были обновлены для .NET Standard.

        ```json
        "netstandard1.6": {
            "imports": [ "dnxcore50", "portable-net452" ]
        }
        ```

## <a name="creating-a-net-core-console-application"></a>Создание консольного приложения .NET Core
Для создания консольного приложения для .NET Core требуется определенная настройка процесса сборки MSBuild.  Образец проекта консольного приложения .NET Core с именем [CoreApp](https://github.com/dotnet/corefxlab/tree/master/samples/NetCoreSample/CoreApp) можно найти в репозитории [corefxlab](https://github.com/dotnet/corefxlab).  Еще один хороший способ — начать с шаблона [coretemplate](https://github.com/mellinoe/coretemplate), в котором применяются отдельные целевые файлы MSBuild для нацеливания на .NET Core, вместо того чтобы вносить эти изменения непосредственно в файл проекта.  

Кроме того, можно сначала создать проект в Visual Studio, а затем изменить его так, чтобы он предназначался для .NET Core.  Ниже описывается минимальный набор действий, которые необходимо выполнить для этого.  В отличие от [CoreApp](https://github.com/dotnet/corefxlab/tree/master/samples/NetCoreSample/CoreApp) или [coretemplate](https://github.com/mellinoe/coretemplate), проект, созданный таким образом, не будет включать в себя конфигурации для нацеливания на Linux и Mac OS.

1. В строке меню Visual Studio выберите **Файл** | **Создать ** | **Проект**, а затем выберите пункт **Консольное приложение**.
2. Выберите имя и расположение проекта, а затем нажмите кнопку **ОК**.
3. В обозревателе решений щелкните проект правой кнопкой мыши, выберите пункт **Свойства**, а затем перейдите на вкладку **Сборка**.
4. В раскрывающемся списке **Конфигурация** (в верхней части страницы свойств) выберите пункт **Все конфигурации**, а затем измените значение свойства **Целевая платформа** на **x64**.
5. Удалите файл `app.config` из проекта.
6. Добавьте в проект файл `project.json` со следующим содержимым:

    ```json
    {
        "dependencies": {
            "Microsoft.NETCore.App": "1.0.0-rc2-3002702"
        },
        "runtimes": {
            "win7-x64": { },
            "ubuntu.14.04-x64": { },
            "osx.10.10-x64": { }
        },
        "frameworks": {
            "netcoreapp1.0": {
                "imports": [ "dnxcore50", "portable-net452" ]
            }
        }
    }
    ```

7. В обозревателе решений щелкните проект правой кнопкой мыши, выберите пункт **Выгрузить проект**, затем щелкните правой кнопкой мыши еще раз, выберите пункт **Изменить _MyProj.csproj_** и внесите указанные ниже изменения.
    - Удалите все элементы `Reference` по умолчанию (ссылки на `System`, `System.Core` и т. д.).
    - Добавьте следующие свойства в первый элемент `PropertyGroup` в проекте:

        ```xml
        <TargetFrameworkIdentifier>.NETCoreApp</TargetFrameworkIdentifier>
        <TargetFrameworkVersion>v1.0</TargetFrameworkVersion>
        <BaseNuGetRuntimeIdentifier>win7</BaseNuGetRuntimeIdentifier>
        <NoStdLib>true</NoStdLib>
        <NoWarn>$(NoWarn);1701</NoWarn>
        ```

    - Добавьте следующие строки в конец файла (после импорта `Microsoft.CSharp.Targets`):

        ```xml
        <PropertyGroup>
            <!-- We don't use any of MSBuild's resolution logic for resolving the framework, so just set these two
                    properties to any folder that exists to skip the GetReferenceAssemblyPaths task (not target) and
                    to prevent it from outputting a warning (MSB3644).
                -->
            <_TargetFrameworkDirectories>$(MSBuildThisFileDirectory)</_TargetFrameworkDirectories>
            <_FullFrameworkReferenceAssemblyPaths>$(MSBuildThisFileDirectory)</_FullFrameworkReferenceAssemblyPaths>

            <!-- MSBuild thinks all EXEs need binding redirects, not so for CoreCLR! -->
            <AutoUnifyAssemblyReferences>true</AutoUnifyAssemblyReferences>
            <AutoGenerateBindingRedirects>false</AutoGenerateBindingRedirects>

            <!-- Set up debug options to run with host, and to use the CoreCLR debug engine -->
            <StartAction>Program</StartAction>
            <StartProgram>$(TargetDir)dotnet.exe</StartProgram>
            <StartArguments>$(TargetPath)</StartArguments>
            <DebugEngines>{2E36F1D4-B23C-435D-AB41-18E608940038}</DebugEngines>
        </PropertyGroup>
        ```

    - Закройте файл .csproj и перезагрузите проект в Visual Studio.

8. Теперь программа должна запускаться путем нажатия клавиши F5 в Visual Studio или из папки выходных данных с помощью команды командной строки`dotnet MyApp.exe` 



<!--HONumber=Nov16_HO1-->


