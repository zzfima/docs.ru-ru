---
title: Перенос приложения Windows Forms в .NET Core 3.0
description: В этой статье объясняется, как перенести приложение Windows Forms из .NET Framework в .NET Core 3.0 для Windows.
author: Thraka
ms.author: adegeo
ms.date: 03/01/2019
ms.custom: ''
ms.openlocfilehash: 64920f1d226fcc8265d0be252d4751f2ba278cc1
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73973280"
---
# <a name="how-to-port-a-windows-forms-desktop-app-to-net-core"></a>Процесс переноса классического приложения Windows Forms в .NET Core

В этой статье объясняется, как перенести классическое приложение, созданное на основе Windows Forms, из .NET Framework в .NET Core 3.0. В пакет SDK для .NET Core 3.0 включена поддержка приложений Windows Forms. Windows Forms — это платформа, которая по-прежнему поддерживается и функционирует только в ОС Windows. В этом примере для создания проекта и управления им используется CLI пакета SDK для .NET Core.

В этой статье применяются различные имена для обозначения типов файлов, используемых для переноса. При переносе вашего проекта файлы будут называться иначе, поэтому попытайтесь мысленно сопоставить их с именами из этой таблицы:

| Файл | ОПИСАНИЕ |
| ---- | ----------- |
| **MyApps.sln** | Имя файла решения. |
| **MyForms.csproj** | Имя проекта Windows Forms в .NET Framework, который нужно перенести. |
| **MyFormsCore.csproj** | Имя создаваемого проекта .NET Core. |
| **MyAppCore.exe** | Исполняемый файл приложения Windows Forms в .NET Core. |

## <a name="prerequisites"></a>Предварительные требования

- [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) для выполнения конструкторских задач.

  Установите следующие рабочие нагрузки Visual Studio:
  - Разработка классических приложений .NET
  - разработка кроссплатформенных приложений .NET.

- Функционирующий проект Windows Forms в решении, сборка и запуск которого выполняется без ошибок.
- Код проекта должен быть написан на C#. 
- Установите последнюю предварительную версию [.NET Core 3.0](https://aka.ms/netcore3download).

>[!NOTE]
>**Visual Studio 2017** не поддерживает проекты .NET Core 3.0. **Visual Studio 2019** поддерживает проекты .NET Core 3.0, но пока не поддерживает визуальный конструктор для проектов Windows Forms в .NET Core 3.0. Чтобы использовать визуальный конструктор, необходимо, чтобы решение проекта Windows Forms в .NET имело общие файлы форм с проектом .NET Core.

### <a name="consider"></a>Consider

При переносе приложения .NET Framework Windows Forms необходимо учесть ряд аспектов.

01. Удостоверьтесь, что ваше приложение подходит для переноса.

    Воспользуйтесь [анализатором переносимости .NET](../../standard/analyzers/portability-analyzer.md), чтобы выяснить, можно ли перенести проект в .NET Core 3.0. Если у проекта есть проблемы с .NET Core 3.0, анализатор поможет их обнаружить.

01. Вы используете другую версию Windows Forms.

    После выпуска .NET Core 3.0 предварительной версии 1 исходный код Windows Forms был размещен в свободном доступе на сайте GitHub. Код .NET Core Windows Forms является вилкой с базой кода .NET Framework Windows Forms. Возможно, в используемой вами версии есть некоторые отличия и приложение не удастся перенести.

01. Помочь с переносом может [пакет обеспечения совместимости Windows][compat-pack].

    Некоторые API, доступные в .NET Framework, недоступны в .NET Core 3.0. [Пакет обеспечения совместимости Windows][compat-pack] поддерживает многие из этих API и может обеспечить приложению Windows Forms совместимость с .NET Core.

01. Обновите пакеты NuGet, используемые в проекте.

    Рекомендуется обновить пакеты NuGet до последней версии перед переносом. Если ваше приложение ссылается на пакеты NuGet, обновите их до последней версии. Убедитесь, что сборка приложения выполняется успешно. Если после обновления возникают ошибки пакетов, установите предыдущую версию пакетов, которая не нарушает работу вашего кода.

01. Visual Studio 2019 пока не поддерживает конструктор Forms для .NET Core 3.0.

    Вам необходимо сохранить существующий файл проекта .NET Framework Windows Forms, если вы хотите использовать конструктор форм в Visual Studio.

## <a name="create-a-new-sdk-project"></a>Создание проекта пакета SDK

Проект .NET Core 3.0 необходимо создать в другом каталоге, а не в том, где находится проект .NET Framework. Если разместить проекты в одном каталоге, могут возникнуть конфликты с файлами, создаваемыми в каталоге **obj**. В этом примере мы создадим каталог с именем **MyFormsAppCore** в каталоге **SolutionFolder**.

```
SolutionFolder
├───MyApps.sln
├───MyFormsApp
│   └───MyForms.csproj
└───MyFormsAppCore      <--- New folder for core project
```

Далее необходимо создать проект **MyFormsCore.csproj** в каталоге **MyFormsAppCore**. Можно создать этот файл вручную с помощью любого текстового редактора. Вставьте следующий код XML:

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWindowsForms>true</UseWindowsForms>
  </PropertyGroup>

</Project>
```

Если вы не хотите вручную создавать файл проекта, можно воспользоваться Visual Studio или пакетом SDK для .NET Core. Но необходимо удалить все остальные файлы, созданные с помощью шаблона проекта, за исключением файла проекта. Чтобы использовать пакет SDK, выполните следующую команду из каталога **SolutionFolder**:

```dotnetcli
dotnet new winforms -o MyFormsAppCore -n MyFormsCore
```

После создания **MyFormsCore.csproj** структура каталогов должна выглядеть следующим образом.

```
SolutionFolder
├───MyApps.sln
├───MyFormsApp
│   └───MyForms.csproj
└───MyFormsAppCore
    └───MyFormsCore.csproj
```

С помощью Visual Studio или .NET Core CLI проект **MyFormsCore.csproj** необходимо добавить в файл **MyApps.sln** из каталога **SolutionFolder**.

```dotnetcli
dotnet sln add .\MyFormsAppCore\MyFormsCore.csproj
```

## <a name="fix-assembly-info-generation"></a>Устранение ошибки со сведениями о сборке

Проекты Windows Forms, созданные с помощью .NET Framework, содержат файл `AssemblyInfo.cs` с атрибутами сборки, такими как версия создаваемой сборки. В проектах, созданных с помощью пакета SDK, эти сведения создаются автоматически на основе файла проекта. Наличие двух типов файлов со сведениями о сборке приводит к конфликту. Чтобы устранить эту проблему, нужно отключить автоматическое создание такого файла, и тогда в проекте будет использоваться существующий файл `AssemblyInfo.cs`.

В главный узел `<PropertyGroup>` необходимо добавить три параметра. 

- **GenerateAssemblyInfo**\
Если задать этому свойству значение `false`, атрибуты сборки создаваться не будут. Это позволит избежать конфликта с существующим файлом `AssemblyInfo.cs` из проекта .NET Framework.

- **AssemblyName**\
Значением этого свойства является выходной двоичный файл, создаваемый при сборке. К имени не требуется добавлять расширение. Например, если задать `MyCoreApp`, будет создан файл `MyCoreApp.exe`.

- **RootNamespace**\
Это пространство имен по умолчанию, используемое в проекте. Оно должно соответствовать пространству имен по умолчанию проекта .NET Framework.

Добавьте эти три элемента в узел `<PropertyGroup>` файла `MyFormsCore.csproj`.

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWindowsForms>true</UseWindowsForms>

    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    <AssemblyName>MyCoreApp</AssemblyName>
    <RootNamespace>WindowsFormsApp1</RootNamespace>
  </PropertyGroup>

</Project>
```

## <a name="add-source-code"></a>Добавление исходного кода

Сейчас проект **MyFormsCore.csproj** не может компилировать код. По умолчанию проекты .NET Core автоматически добавляют весь исходный код в текущий каталог и все дочерние каталоги. Необходимо настроить проект так, чтобы добавлять код из проекта .NET Framework, используя относительный путь. Если в вашем проекте .NET Framework используются файлы **RESX** для значков и ресурсов форм, их также необходимо добавить. 

Добавьте в проект указанный ниже узел `<ItemGroup>`. Каждая инструкция содержит стандартную маску файла, охватывающую дочерние каталоги.

```xml
  <ItemGroup>
    <Compile Include="..\MyFormsApp\**\*.cs" />
    <EmbeddedResource Include="..\MyFormsApp\**\*.resx" />
  </ItemGroup>
```

Кроме того, можно создать запись `<Compile>` или `<EmbeddedResource>` для каждого файла в проекте .NET Framework.

## <a name="add-nuget-packages"></a>Добавление пакетов NuGet

Добавьте в проект .NET Core все пакеты NuGet, на которые ссылается проект .NET Framework. 

В вашем приложении .NET Framework Windows Forms, скорее всего, есть файл **packages.config**, содержащий список всех пакетов NuGet, на которые ссылается проект. Этот список поможет вам определить, какие пакеты NuGet нужно добавить в проект .NET Core. Например, если проект .NET Framework ссылается на пакеты NuGet `MetroFramework`, `MetroFramework.Design` и `MetroFramework.Fonts`, добавьте каждый из них в проект с помощью Visual Studio или .NET Core CLI из каталога **SolutionFolder**.

```dotnetcli
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package MetroFramework
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package MetroFramework.Design
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package MetroFramework.Fonts
```

Приведенные выше команды добавляют следующие ссылки на пакеты NuGet в проект **MyFormsCore.csproj**.

```xml
  <ItemGroup>
    <PackageReference Include="MetroFramework" Version="1.2.0.3" />
    <PackageReference Include="MetroFramework.Design" Version="1.2.0.3" />
    <PackageReference Include="MetroFramework.Fonts" Version="1.2.0.3" />
  </ItemGroup>
```

## <a name="port-control-libraries"></a>Перенос библиотек элементов управления

Если вы переносите проект библиотеки элементов управления Windows Forms, действия будут такими же, как при переносе проекта приложения .NET Framework Windows Forms, за несколькими исключениями. При этом выполняется сборка не исполняемого файла, а библиотеки. Различия при переносе проекта исполняемого файла и проекта библиотеки, помимо путей для масок файлов с исходным кодом, сводятся к минимуму.

Используя пример из предыдущего шага, расширим перечень проектов и файлов, с которыми мы работаем.

| Файл | ОПИСАНИЕ |
| ---- | ----------- |
| **MyApps.sln** | Имя файла решения. |
| **MyControls.csproj** | Имя проекта библиотеки элементов управления Windows Forms, который нужно перенести. |
| **MyControlsCore.csproj** | Имя создаваемого проекта библиотеки .NET Core. |
| **MyCoreControls.dll** | Библиотека элементов управления Windows Forms в .NET Core. |

```
SolutionFolder
├───MyApps.sln
├───MyFormsApp
│   └───MyForms.csproj
├───MyFormsAppCore
│   └───MyFormsCore.csproj
│
├───MyFormsControls
│   └───MyControls.csproj
└───MyFormsControlsCore
    └───MyControlsCore.csproj   <--- New project for core controls
```

Рассмотрим различия между проектом `MyControlsCore.csproj` и ранее созданным проектом `MyFormsCore.csproj`.

```diff
 <Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

   <PropertyGroup>
-    <OutputType>WinExe</OutputType>
     <TargetFramework>netcoreapp3.0</TargetFramework>
     <UseWindowsForms>true</UseWindowsForms>

     <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
-    <AssemblyName>MyCoreApp</AssemblyName>
-    <RootNamespace>WindowsFormsApp1</RootNamespace>
+    <AssemblyName>MyControlsCore</AssemblyName>
+    <RootNamespace>WindowsFormsControlLibrary1</RootNamespace>
   </PropertyGroup>

   <ItemGroup>
-    <Compile Include="..\MyFormsApp\**\*.cs" />
-    <EmbeddedResource Include="..\MyFormsApp\**\*.resx" />
+    <Compile Include="..\MyFormsControls\**\*.cs" />
+    <EmbeddedResource Include="..\MyFormsControls\**\*.resx" />
   </ItemGroup>

 </Project>
```

Ниже приведен пример, как мог бы выглядеть файл проекта библиотеки элементов управления Windows Forms в .NET Core.

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWindowsForms>true</UseWindowsForms>

    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    <AssemblyName>MyCoreControls</AssemblyName>
    <RootNamespace>WindowsFormsControlLibrary1</RootNamespace>
  </PropertyGroup>
  
  <ItemGroup>
    <Compile Include="..\MyFormsControls\**\*.cs" />
    <EmbeddedResource Include="..\MyFormsControls\**\*.resx" />
  </ItemGroup>
  
</Project>
```

Как можно видеть, узел `<OutputType>` был удален, поэтому компилятор создает библиотеку, а не исполняемый файл. Узлы `<AssemblyName>` и `<RootNamespace>` были изменены. В частности, узел `<RootNamespace>` должен совпадать с пространством имен переносимой библиотеки элементов управления Windows Forms. Наконец, узлы `<Compile>` и `<EmbeddedResource>` были откорректированы и теперь указывают на папку переносимой библиотеки элементов управления Windows Forms.

Теперь в главном проекте .NET Core **MyFormsCore.csproj** нужно добавить ссылку на новую библиотеку элементов управления Windows Forms в .NET Core. Добавьте ссылку с помощью Visual Studio или .NET Core CLI из каталога **SolutionFolder**.

```dotnetcli
dotnet add .\MyFormsAppCore\MyFormsCore.csproj reference .\MyFormsControlsCore\MyControlsCore.csproj
```

Предыдущая команда добавляет следующую ссылку в проект **MyFormsCore.csproj**:

```xml
  <ItemGroup>
    <ProjectReference Include="..\MyFormsControlsCore\MyControlsCore.csproj" />
  </ItemGroup>
```

## <a name="problems-compiling"></a>Проблемы со сборкой

Если возникают проблемы при сборке проектов, причина может быть в том, что вы используете некоторые API только для Windows, которые доступны в .NET Framework, но недоступны в .NET Core. Попробуйте добавить в свой проект такой пакет NuGet, как [пакет обеспечения совместимости Windows][compat-pack]. Этот пакет выполняется только в среде Windows и добавляет около 20 000 API Windows в проекты .NET Core и .NET Standard.

```dotnetcli
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package Microsoft.Windows.Compatibility
```

Предыдущая команда добавляет следующую ссылку в проект **MyFormsCore.csproj**:

```xml
  <ItemGroup>
    <PackageReference Include="Microsoft.Windows.Compatibility" Version="2.0.1" />
  </ItemGroup>
```

## <a name="windows-forms-designer"></a>Конструктор Windows Forms

Как упоминалось выше, Visual Studio 2019 поддерживает конструктор Forms только в проектах .NET Framework. Создав параллельный проект .NET Core, можно проверить его работу в .NET Core, используя при этом конструктор форм в проекте .NET Framework. В файле решения будут присутствовать оба проекта — NET Framework и .NET Core. Добавляйте и создавайте формы и элементы управления в проекте .NET Framework, а стандартные маски файлов, добавленные нами в проекты .NET Core, позволят автоматически добавлять новые или измененные файлы в проекты .NET Core.

Когда в Visual Studio 2019 будет добавлена поддержка конструктора Windows Forms, можно скопировать и вставить содержимое файла проекта .NET Core в файл проекта .NET Framework. Затем можно удалить стандартные маски файлов, добавленные с помощью элементов `<Source>` и `<EmbeddedResource>`. Исправьте пути ссылок проекта, используемых приложением. Это позволит полноценно преобразовать проект .NET Framework в проект .NET Core.
 
## <a name="next-steps"></a>Следующие шаги

- Дополнительные сведения о [пакете обеспечения совместимости Windows][compat-pack].
- [Видео о переносе](https://www.youtube.com/watch?v=upVQEUc_KwU) проекта Windows Forms из .NET Framework в .NET Core.

[compat-pack]: windows-compat-pack.md
