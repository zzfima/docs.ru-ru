---
title: Портирование приложения WPF в .NET Core 3.0
description: В этой статье объясняется, как перенести приложение Windows Presentation Foundation из .NET Framework в .NET Core 3.0 для Windows.
author: Thraka
ms.author: adegeo
ms.date: 03/27/2019
ms.custom: ''
ms.openlocfilehash: 1528e578a978de38998b3f3f4b7beb72ff7422d4
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117072"
---
# <a name="how-to-port-a-wpf-desktop-app-to-net-core"></a>Практическое руководство. Портирование классического приложения WPF в .NET Core

В этой статье объясняется, как перенести классическое приложение, созданное на основе Windows Presentation Foundation, из .NET Framework в .NET Core 3.0. В пакет SDK для .NET Core 3.0 включена поддержка приложений WPF. Windows Presentation Foundation — это платформа, которая по-прежнему поддерживается и функционирует только в ОС Windows. В этом примере для создания проекта и управления им используется CLI пакета SDK для .NET Core.

В этой статье применяются различные имена для обозначения типов файлов, используемых для переноса. При переносе вашего проекта файлы будут называться иначе, поэтому попытайтесь мысленно сопоставить их с именами из этой таблицы:

| Файл | ОПИСАНИЕ |
| ---- | ----------- |
| **MyApps.sln** | Имя файла решения. |
| **MyWPF.csproj** | Имя проекта WPF в .NET Framework, который нужно перенести. |
| **MyWPFCore.csproj** | Имя создаваемого проекта .NET Core. |
| **MyAppCore.exe** | Исполняемый файл WPF-приложения .NET Core. |

>[!IMPORTANT]
>Несмотря на то, что в этой статье в качестве целевого языка используется C#, для VB.NET выполняются аналогичные действия, за исключением того, что VB.NET вместо файлов *CSPROJ* и *CS* использует файлы *VBPROJ* и *VB*, соответственно.

## <a name="prerequisites"></a>Предварительные требования

- [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) для выполнения конструкторских задач.

  Установите следующие рабочие нагрузки Visual Studio:
  - Разработка классических приложений .NET
  - разработка кроссплатформенных приложений .NET.

- Функционирующий проект WPF в решении, сборка и запуск которого выполняется без ошибок.
- Установите последнюю предварительную версию [.NET Core 3.0](https://aka.ms/netcore3download).

>[!NOTE]
>**Visual Studio 2017** не поддерживает проекты .NET Core 3.0. **Visual Studio 2019** поддерживает проекты .NET Core 3.0, но располагает ограниченной поддержкой визуального конструктора WPF для .NET Core. Чтобы использовать полностью поддерживаемый визуальный конструктор, необходимо, чтобы решение проекта WPF в .NET Framework имело общие файлы с проектом .NET Core.

### <a name="consider"></a>Consider

При переносе приложения WPF из .NET Framework необходимо учесть ряд аспектов.

01. Удостоверьтесь, что ваше приложение подходит для переноса.

    Воспользуйтесь [анализатором переносимости .NET](../../standard/analyzers/portability-analyzer.md), чтобы выяснить, можно ли перенести проект в .NET Core 3.0. Если у проекта есть проблемы с .NET Core 3.0, анализатор поможет их обнаружить.

01. Вы используете другую версию WPF.

    После выпуска .NET Core 3.0 предварительной версии 1 исходный код WPF был размещен в свободном доступе на сайте GitHub. Код .NET Core WPF является вилкой от базы кода .NET Framework WPF. Возможно, в используемой вами версии есть некоторые отличия и приложение не удастся перенести.

01. Помочь с переносом может [пакет обеспечения совместимости Windows][compat-pack].

    Некоторые API, доступные в .NET Framework, недоступны в .NET Core 3.0. [Пакет обеспечения совместимости Windows][compat-pack] поддерживает многие из этих API и может обеспечить совместимость WPF-приложения с .NET Core.

01. Обновите пакеты NuGet, используемые в проекте.

    Рекомендуется обновить пакеты NuGet до последней версии перед переносом. Если ваше приложение ссылается на пакеты NuGet, обновите их до последней версии. Убедитесь, что сборка приложения выполняется успешно. Если после обновления возникают ошибки пакетов, установите предыдущую версию пакетов, которая не нарушает работу вашего кода.

01. Visual Studio 2019 пока не поддерживает конструктор WPF для .NET Core 3.0.

    Вам необходимо сохранить существующий файл проекта WPF для .NET Framework, если вы хотите использовать конструктор WPF в Visual Studio.

## <a name="create-a-new-sdk-project"></a>Создание проекта пакета SDK

Проект .NET Core 3.0 необходимо создать в другом каталоге, а не в том, где находится проект .NET Framework. Если разместить проекты в одном каталоге, могут возникнуть конфликты с файлами, создаваемыми в каталоге **obj**. В этом примере мы создадим каталог с именем **MyWPFAppCore** в каталоге **SolutionFolder**.

```
SolutionFolder
├───MyApps.sln
├───MyWPFApp
│   └───MyWPF.csproj
└───MyWPFAppCore      <--- New folder for core project
```

Далее необходимо создать проект **MyWPFCore.csproj** в каталоге **MyWPFAppCore**. Можно создать этот файл вручную с помощью любого текстового редактора. Вставьте следующий код XML:

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

Если вы не хотите вручную создавать файл проекта, можно воспользоваться Visual Studio или пакетом SDK для .NET Core. Но необходимо удалить все остальные файлы, созданные с помощью шаблона проекта, за исключением файла проекта. Чтобы использовать пакет SDK, выполните следующую команду из каталога **SolutionFolder**:

```dotnetcli
dotnet new wpf -o MyWPFAppCore -n MyWPFCore
```

После создания **MyWPFCore.csproj** структура каталогов должна выглядеть следующим образом.

```
SolutionFolder
├───MyApps.sln
├───MyWPFApp
│   └───MyWPF.csproj
└───MyWPFAppCore
    └───MyWPFCore.csproj
```

С помощью Visual Studio или .NET Core CLI проект **MyWPFCore.csproj** необходимо добавить в файл **MyApps.sln** из каталога **SolutionFolder**.

```dotnetcli
dotnet sln add .\MyWPFAppCore\MyWPFCore.csproj
```

## <a name="fix-assembly-info-generation"></a>Устранение ошибки со сведениями о сборке

Проекты Windows Presentation Foundation, созданные с помощью .NET Framework, содержат файл `AssemblyInfo.cs` с атрибутами сборки, такими как версия создаваемой сборки. В проектах, созданных с помощью пакета SDK, эти сведения создаются автоматически на основе файла проекта. Наличие двух типов файлов со сведениями о сборке приводит к конфликту. Чтобы устранить эту проблему, нужно отключить автоматическое создание такого файла, и тогда в проекте будет использоваться существующий файл `AssemblyInfo.cs`.

В главный узел `<PropertyGroup>` необходимо добавить три параметра. 

- **GenerateAssemblyInfo**\
Если задать этому свойству значение `false`, атрибуты сборки создаваться не будут. Это позволит избежать конфликта с существующим файлом `AssemblyInfo.cs` из проекта .NET Framework.

- **AssemblyName**\
Значением этого свойства является выходной двоичный файл, создаваемый при сборке. К имени не требуется добавлять расширение. Например, если задать `MyCoreApp`, будет создан файл `MyCoreApp.exe`.

- **RootNamespace**\
Это пространство имен по умолчанию, используемое в проекте. Оно должно соответствовать пространству имен по умолчанию проекта .NET Framework.

Добавьте эти три элемента в узел `<PropertyGroup>` файла `MyWPFCore.csproj`.

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWPF>true</UseWPF>

    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    <AssemblyName>MyCoreApp</AssemblyName>
    <RootNamespace>MyWPF</RootNamespace>
  </PropertyGroup>

</Project>
```

## <a name="add-source-code"></a>Добавление исходного кода
Сейчас проект **MyWPFCore.csproj** не может компилировать код. По умолчанию проекты .NET Core автоматически добавляют весь исходный код в текущий каталог и все дочерние каталоги. Необходимо настроить проект так, чтобы добавлять код из проекта .NET Framework, используя относительный путь. Если в вашем проекте .NET Framework используются **RESX**-файлы для окон и элементов управления, их также необходимо добавить. 

Первый узел `<ItemGroup>`, который необходимо добавить в проект, включает файл **App.xaml**, представляющий конфигурацию запуска и ресурсы, используемые приложением. Файл **App.xaml** также сопровождает соответствующий файл **App.xaml.cs**, но он будет автоматически включаться в другом `<ItemGroup>`.

```xml
  <ItemGroup>
    <ApplicationDefinition Include="..\MyWPFApp\App.xaml">
      <Generator>MSBuild:Compile</Generator>
    </ApplicationDefinition>
  </ItemGroup>
```

Затем добавьте в проект указанный ниже узел `<ItemGroup>`. Каждая инструкция содержит стандартную маску файла, охватывающую дочерние каталоги. Он включает в себя исходный код для проекта, все файлы параметров и ресурсы. Каталог **Obj** явным образом исключен.

```xml
  <ItemGroup>
    <Compile Include="..\MyWPFApp\**\*.cs" Exclude="..\MyWPFApp\obj\**" />
    <None Include="..\MyWPFApp\**\*.settings" />
    <EmbeddedResource Include="..\MyWPFApp\**\*.resx" />
  </ItemGroup>
```

Далее включите другой узел `<ItemGroup>`, содержащий запись `<Page>` для каждого **XAML**-файла в проекте, за исключением **App.xaml**. Они содержат описания всех окон, страниц и ресурсов, которые находятся в формате **XAML**. Здесь невозможно использовать маски; следует добавить запись для каждого файла и указать используемый `<Generator>`.

```xml
  <ItemGroup>
    <Page Include="..\MyWPFApp\MainWindow.xaml">
      <Generator>MSBuild:Compile</Generator>
    </Page>
  </ItemGroup>
```

## <a name="add-nuget-packages"></a>Добавление пакетов NuGet

Добавьте в проект .NET Core все пакеты NuGet, на которые ссылается проект .NET Framework. 

В вашем WPF-приложении для .NET Framework, скорее всего, есть файл **packages.config**, содержащий список всех пакетов NuGet, на которые ссылается проект. Этот список поможет вам определить, какие пакеты NuGet нужно добавить в проект .NET Core. Например, если проект .NET Framework ссылается на пакет `MahApps.Metro` в NuGet, добавьте его в проект с помощью Visual Studio. Ссылку можно также добавить с помощью .NET Core CLI из каталога **SolutionFolder**.

```dotnetcli
dotnet add .\MyWPFAppCore\MyWPFCore.csproj package MahApps.Metro -v 2.0.0-alpha0262
```

Приведенная выше команда добавляет следующие ссылку на пакеты NuGet в проект **MyWPFCore.csproj**.

```xml
  <ItemGroup>
    <PackageReference Include="MahApps.Metro" Version="2.0.0-alpha0262" />
  </ItemGroup>
```

## <a name="problems-compiling"></a>Проблемы со сборкой

Если возникают проблемы при сборке проектов, причина может быть в том, что вы используете некоторые API только для Windows, которые доступны в .NET Framework, но недоступны в .NET Core. Попробуйте добавить в свой проект такой пакет NuGet, как [пакет обеспечения совместимости Windows][compat-pack]. Этот пакет выполняется только в среде Windows и добавляет около 20 000 API Windows в проекты .NET Core и .NET Standard.

```dotnetcli
dotnet add .\MyWPFAppCore\MyWPFCore.csproj package Microsoft.Windows.Compatibility
```

Предыдущая команда добавляет следующую ссылку в проект **MyWPFCore.csproj**:

```xml
  <ItemGroup>
    <PackageReference Include="Microsoft.Windows.Compatibility" Version="2.0.1" />
  </ItemGroup>
```

## <a name="wpf-designer"></a>Конструктор WPF

Как упоминалось выше, Visual Studio 2019 поддерживает конструктор WPF только в проектах .NET Framework. Создав параллельный проект .NET Core, можно проверить его работу в .NET Core, используя при этом конструктор форм в проекте .NET Framework. В файле решения будут присутствовать оба проекта — NET Framework и .NET Core. Добавляйте и создавайте формы и элементы управления в проекте .NET Framework, а стандартные маски файлов, добавленные нами в проекты .NET Core, позволят автоматически добавлять новые или измененные файлы в проекты .NET Core.

Когда в Visual Studio 2019 будет добавлена поддержка конструктора WPF, можно будет скопировать и вставить содержимое файла проекта .NET Core в файл проекта .NET Framework. Затем можно удалить стандартные маски файлов, добавленные с помощью элементов `<Source>` и `<EmbeddedResource>`. Исправьте пути ссылок проекта, используемых приложением. Это позволит полноценно преобразовать проект .NET Framework в проект .NET Core.

## <a name="next-steps"></a>Следующие шаги

- Дополнительные сведения о [пакете обеспечения совместимости Windows][compat-pack].
- [Видео о переносе](https://www.youtube.com/watch?v=5MomsgkWkVw&list=PLS__JrkRveTMiWxG-Lv4cBwYfMQ6m2gmt) проекта WPF из .NET Framework в .NET Core.

[compat-pack]: windows-compat-pack.md
