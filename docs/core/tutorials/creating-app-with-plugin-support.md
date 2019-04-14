---
title: Создание приложения .NET Core с подключаемыми модулями
description: Узнайте, как создать приложение .NET Core, которое поддерживает подключаемые модули.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/28/2019
ms.openlocfilehash: a9431ee28c7df21a8688f845be20e062eca21887
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59076813"
---
# <a name="create-a-net-core-application-with-plugins"></a>Создание приложения .NET Core с подключаемыми модулями

В этом учебнике демонстрируется выполнение следующих действий:

- Создание структуры проекта для поддержки подключаемых модулей.
- Создание пользовательского <xref:System.Runtime.Loader.AssemblyLoadContext> для загрузки каждого подключаемого модуля.
- Использование типа `System.Runtime.Loader.AssemblyDependencyResolver`, чтобы разрешить зависимости для подключаемых модулей.
- Создание подключаемых модулей, которые можно легко развернуть путем копирования артефактов сборки.

## <a name="prerequisites"></a>Предварительные требования

- Установите [пакет SDK для .NET Core 3.0, предварительная версия 2](https://www.microsoft.com/net/core) или более новой версии.

## <a name="create-the-application"></a>Создание приложения

Первым шагом является создание приложения:

1. Создайте новую папку и в этой папке выполните `dotnet new console -o AppWithPlugin`. 
2. Чтобы упросить создание проекта, создайте файл решения Visual Studio. Запустите `dotnet new sln` в этой же папке. 
3. Запустите `dotnet sln add AppWithPlugin/AppWithPlugin.csproj`, чтобы добавить проект приложения в решение.

Теперь можно заполнить каркас нашего приложения. В файле *AppWithPlugin/Program.cs* замените существующий код следующим кодом:

```csharp
using PluginBase;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Reflection;

namespace AppWithPlugin
{
    class Program
    {
        static void Main(string[] args)
        {
            try
            {
                if (args.Length == 1 && args[0] == "/d")
                {
                    Console.WriteLine("Waiting for any key...");
                    Console.ReadLine();
                }

                // Load commands from plugins.

                if (args.Length == 0)
                {
                    Console.WriteLine("Commands: ");
                    // Output the loaded commands.
                }
                else
                {
                    foreach (string commandName in args)
                    {
                        Console.WriteLine($"-- {commandName} --");

                        // Execute the command with the name passed as an argument.

                        Console.WriteLine();
                    }
                }
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex);
            }
        }
    }
}

```

## <a name="create-the-plugin-interfaces"></a>Создание интерфейсов подключаемых модулей

Следующий шаг при создании приложения с подключаемыми модулями — определение интерфейса, который подключаемые модули должны реализовывать. Мы рекомендуем создать библиотеку классов, содержащую типы, которые вы планируете использовать для обмена данными между приложением и подключаемыми модулями. Это разделение позволяет публиковать интерфейс подключаемого модуля как пакет без передачи всего приложения.

В корневой папке проекта запустите `dotnet new classlib -o PluginBase`. Также запустите `dotnet sln add PluginBase/PluginBase.csproj`, чтобы добавить проект в файл решения. Удалите файл `PluginBase/Class1.cs` и создайте новый файл в папке `PluginBase` с именем `ICommand.cs` со следующим определением интерфейса:

[!code-csharp[the-plugin-interface](~/samples/core/extensions/AppWithPlugin/PluginBase/ICommand.cs)]

Этот интерфейс `ICommand` является интерфейсом, который будут реализовывать все подключаемые модули.

Теперь, когда интерфейс `ICommand` определен, в проект приложения можно добавить другие элементы. Добавьте ссылку из проекта `AppWithPlugin` на проект `PluginBase` с командой `dotnet add AppWithPlugin\AppWithPlugin.csproj reference PluginBase\PluginBase.csproj` из корневой папки.

Замените комментарий `// Load commands from plugins` на следующий фрагмент кода, чтобы он мог загрузить подключаемые модули из указанных путей к файлам:

```csharp
string[] pluginPaths = new string[]
{
    // Paths to plugins to load.
};

IEnumerable<ICommand> commands = pluginPaths.SelectMany(pluginPath =>
{
    Assembly pluginAssembly = LoadPlugin(pluginPath);
    return CreateCommands(pluginAssembly);
}).ToList();
```

Затем замените комментарий `// Output the loaded commands` следующим фрагментом кода:

```csharp
foreach (ICommand command in commands)
{
    Console.WriteLine($"{command.Name}\t - {command.Description}");
}
```

Замените комментарий `// Execute the command with the name passed as an argument` следующим фрагментом кода:

```csharp
ICommand command = commands.FirstOrDefault(c => c.Name == commandName);
if (command == null)
{
    Console.WriteLine("No such command is known.");
    return;
}

command.Execute();
```

И, наконец, добавьте статические методы в класс `Program` с именем `LoadPlugin` и `CreateCommands`, как показано ниже:

```csharp
static Assembly LoadPlugin(string relativePath)
{
    throw new NotImplementedException();
}

static IEnumerable<ICommand> CreateCommands(Assembly assembly)
{
    int count = 0;

    foreach (Type type in assembly.GetTypes())
    {
        if (typeof(ICommand).IsAssignableFrom(type))
        {
            ICommand result = Activator.CreateInstance(type) as ICommand;
            if (result != null)
            {
                count++;
                yield return result;
            }
        }
    }

    if (count == 0)
    {
        string availableTypes = string.Join(",", assembly.GetTypes().Select(t => t.FullName));
        throw new ApplicationException(
            $"Can't find any type which implements ICommand in {assembly} from {assembly.Location}.\n" +
            $"Available types: {availableTypes}");
    }
}
```

## <a name="load-plugins"></a>Загрузка подключаемых модулей

Теперь приложение может правильно загрузить и создать экземпляры команд из загруженных сборок подключаемых модулей, но оно по-прежнему не может загрузить сборки подключаемых модулей. Создайте файл с именем *PluginLoadContext.cs* в папке *AppWithPlugin* со следующим содержимым:

[!code-csharp[loading-plugins](~/samples/core/extensions/AppWithPlugin/AppWithPlugin/PluginLoadContext.cs)]

Тип `PluginLoadContext` наследуется от класса <xref:System.Runtime.Loader.AssemblyLoadContext>. Тип `AssemblyLoadContext` — это специальный тип в среде выполнения, который позволяет разработчикам изолировать загруженные сборки в разные группы, чтобы версии сборок не конфликтовали друг с другом. Кроме того, пользовательский `AssemblyLoadContext` может выбирать различные пути для загрузки сборок и переопределять поведение по умолчанию. `PluginLoadContext` использует экземпляр типа `AssemblyDependencyResolver`, появившегося в .NET Core 3.0, для разрешения имен сборок в пути. Объект `AssemblyDependencyResolver` создается с путем к библиотеке классов .NET. Он разрешает сборки и собственные библиотеки в относительные пути на основе файла *deps.json* для библиотеки классов, путь которой был передан конструктору `AssemblyDependencyResolver`. Пользовательский `AssemblyLoadContext` позволяет подключаемым модулям иметь собственные зависимости, а `AssemblyDependencyResolver` упрощает правильную загрузку зависимостей.

Теперь, когда у проекта `AppWithPlugin` есть тип `PluginLoadContext`, дополните метод `Program.LoadPlugin` следующим текстом:

```csharp
static Assembly LoadPlugin(string relativePath)
{
    // Navigate up to the solution root
    string root = Path.GetFullPath(Path.Combine(
        Path.GetDirectoryName(
            Path.GetDirectoryName(
                Path.GetDirectoryName(
                    Path.GetDirectoryName(
                        Path.GetDirectoryName(typeof(Program).Assembly.Location)))))));

    string pluginLocation = Path.GetFullPath(Path.Combine(root, relativePath.Replace('\\', Path.DirectorySeparatorChar)));
    Console.WriteLine($"Loading commands from: {pluginLocation}");
    PluginLoadContext loadContext = new PluginLoadContext(pluginLocation);
    return loadContext.LoadFromAssemblyName(new AssemblyName(Path.GetFileNameWithoutExtension(pluginLocation)));
}
```

Если использовать другой экземпляр `PluginLoadContext` для каждого подключаемого модуля, подключаемые модули смогут иметь разные или даже конфликтующие зависимости без проблем.

## <a name="create-a-simple-plugin-with-no-dependencies"></a>Создание простого подключаемого модуля без зависимостей

В корневой папке сделайте следующее:

1. Запустите `dotnet new classlib -o HelloPlugin`, чтобы создать новый проект библиотеки классов с именем `HelloPlugin`.
2. Запустите `dotnet sln add HelloPlugin/HelloPlugin.csproj`, чтобы добавить проект в решение `AppWithPlugin`. 
3. Замените файл *HelloPlugin/Class1.cs* на файл с именем *HelloCommand.cs* со следующим содержимым:

[!code-csharp[the-hello-plugin](~/samples/core/extensions/AppWithPlugin/HelloPlugin/HelloCommand.cs)]

Теперь откройте файл *HelloPlugin.csproj*. Он должен выглядеть следующим образом:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.0</TargetFramework>
  </PropertyGroup>

</Project>

```

Между тегами `<Project>` добавьте следующие элементы:

```xml
<ItemGroup>
<ProjectReference Include="..\PluginBase\PluginBase.csproj">
    <Private>false</Private>
</ProjectReference>
</ItemGroup>
```

Элемент `<Private>false</Private>` очень важен. Он сообщает MSBuild, что не нужно копировать *PluginBase.dll* в выходной каталог для HelloPlugin. Если сборка *PluginBase.dll* присутствует в выходном каталоге, `PluginLoadContext` найдет там сборку и загрузит ее при загрузке сборки *HelloPlugin.dll*. На этом этапе тип `HelloPlugin.HelloCommand` реализует интерфейс `ICommand` из файла *PluginBase.dll* в выходном каталоге проекта `HelloPlugin`, а не интерфейс `ICommand`, загруженный в контекст загрузки по умолчанию. Так как среда выполнения считает эти два типа разными типами из разных сборок, метод `AppWithPlugin.Program.CreateCommands` не найдет команды. Поэтому для ссылки на сборку, содержащую интерфейсы подключаемого модуля, требуются метаданные `<Private>false</Private>`.

Теперь, когда проект `HelloPlugin` завершен, мы должны обновить проект `AppWithPlugin`, чтобы знать, где находится подключаемый модуль `HelloPlugin`. После комментария `// Paths to plugins to load` добавьте `@"HelloPlugin\bin\Debug\netcoreapp3.0\HelloPlugin.dll"` как элемент массива `pluginPaths`.

## <a name="create-a-plugin-with-library-dependencies"></a>Создание подключаемого модуля с зависимостями библиотек

Почти все подключаемые модули сложнее, чем простая программа "Hello World", и многие подключаемые модули имеют зависимости от других библиотек. Подключаемые модули `JsonPlugin` и `OldJson` в этом образце — это два примера подключаемых модулей с зависимостями пакета NuGet от `Newtonsoft.Json`. В самих файлах проекта нет особых сведений для ссылок проекта, и (после добавления пути подключаемого модуля к массиву `pluginPaths`) подключаемые модули запускаются идеально, даже при запуске в том же выполнении приложения AppWithPlugin. Но эти проекты не копируют сборки со ссылками в выходной каталог, поэтому сборки должны присутствовать на компьютере пользователя, чтобы функционировать. Существует два способа обойти эту проблему. Первый вариант — использовать команду `dotnet publish` для публикации библиотеки классов. Кроме того, если вы хотите иметь возможность использовать выходные данные `dotnet build` для подключаемого модуля, можно добавить свойство `<CopyLocalLockFileAssemblies>true</CopyLocalLockFileAssemblies>` между тегами `<PropertyGroup>` в файле проекта подключаемого модуля. См. проект подключаемого модуля `XcopyablePlugin` в качестве примера.

## <a name="other-plugin-examples-in-the-sample"></a>Другие примеры подключаемого модуля в образце

Полный исходный код для этого руководства можно найти в [репозитории dotnet/samples](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin). Полный пример включает несколько других примеров поведения `AssemblyDependencyResolver`. Например, объект `AssemblyDependencyResolver` может разрешить собственные библиотеки, а также локализованные вспомогательные сборки, включенные в пакеты NuGet. `UVPlugin` и `FrenchPlugin` в репозитории примеров демонстрируют такие сценарии.

## <a name="how-to-reference-a-plugin-interface-assembly-defined-in-a-nuget-package"></a>Способ создания ссылок на сборку интерфейса подключаемого модуля, определенную в пакете NuGet

Предположим, у вас есть приложение A, и интерфейс его подключаемого модуля определен в пакете NuGet `A.PluginBase`. Как правильно сослаться на пакет в проекте подключаемого модуля? Для ссылок проекта использование метаданных `<Private>false</Private>` в элементе `ProjectReference` в файле проекта не позволило скопировать DLL-файл в выходные данные.

Чтобы правильно сослаться на пакет `A.PluginBase`, необходимо изменить элемент `<PackageReference>` в файле проекта на следующий код:

```xml
<PackageReference Include="A.PluginBase" Version="1.0.0">
    <ExcludeAssets>runtime</ExcludeAssets>
</PackageReference>
```

Так сборки `A.PluginBase` не копируются в выходной каталог подключаемого модуля, и подключаемый модуль использует версию A для `A.PluginBase`.

## <a name="plugin-target-framework-recommendations"></a>Рекомендации для целевой платформы подключаемого модуля

Так как загрузка зависимости подключаемого модуля использует файл *deps.json*, с целевой платформой подключаемого модуля не все так просто. В частности, подключаемые модули должны быть нацелены на среду выполнения, такую как .NET Core 3.0, а не на версию .NET Standard. Файл `deps.json` создается в зависимости от целевой платформы проекта, и поскольку многие пакеты, совместимые с .NET Standard, ссылаются на сборки для .NET Standard и сборки реализации для конкретных сред выполнения, `deps.json` может неправильно распознавать сборки реализации или принимать версию сборки .NET Standard вместо ожидаемой версии .NET Core.
