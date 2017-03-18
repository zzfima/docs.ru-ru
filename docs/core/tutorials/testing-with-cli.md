---
title: "Организация и тестирование проектов с использованием командной строки .NET Core | Документы Майкрософт"
description: "В этом учебнике объясняется, как упорядочить и протестировать проекты .NET Core из командной строки."
keywords: .NET, .NET Core
author: cartermp
ms.author: mairaw
ms.date: 03/07/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 52ff1be3-d92e-4477-9c84-8c1771e87ab5
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 3f401907a59d5427cbcfaa0b785931a7ed82110f
ms.lasthandoff: 03/07/2017

---

# <a name="organizing-and-testing-projects-with-the-net-core-command-line"></a>Организация и тестирование проектов с использованием командной строки .NET Core

В этом руководстве раскрывается тема, начатая в статье [Начало работы с .NET Core в Windows, Linux или Mac OS из командной строки](./using-with-xplat-cli.md). Здесь показано, как можно перейти от создания простых "hello world" к разработке более сложных и хорошо организованных приложений.

## <a name="using-folders-to-organize-code"></a>Упорядочение кода с помощью папок

Предположим, что требуется добавить новые типы для выполнения поставленных задач. Это можно сделать путем добавления дополнительных файлов и назначения им пространств имен, которые можно включить в файл *Program.cs*.

```
/MyProject
|__Program.cs
|__AccountInformation.cs
|__MonthlyReportRecords.cs
|__MyProject.csproj
```

такой подход работает, если размер проект относительно мал. Но если у вас большое приложение со множеством различных типов данных и, возможно, несколькими уровнями, вам может потребоваться логически упорядочить их. Как раз для этого и могут пригодиться папки. Вы можете разобрать [образец проекта NewTypes](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/NewTypesMsBuild), который рассматривается в этом руководстве, или создать собственные файлы и папки.

Для начала создайте папку в корневом каталоге проекта. В этом случае выбрано `/Model`.

```
/NewTypes
|__/Model
|__Program.cs
|__NewTypes.csproj
```

Далее добавьте в папку новые типы:

```
/NewTypes
|__/Model
   |__AccountInformation.cs
   |__MonthlyReportRecords.cs
|__Program.cs
|__NewTypes.csproj
```

Теперь присвойте им всем одно и то же пространство имен, как если бы они были файлами в одном каталоге, чтобы их можно было включить в файл `Program.cs`.

### <a name="example-pet-types"></a>Пример. Типы домашних животных

В этом примере создаются два типа, `Dog` и `Cat`, которые реализуют общий интерфейс `IPet`.

Структура папок:

```
/NewTypes
|__/Pets
   |__Dog.cs
   |__Cat.cs
   |__IPet.cs
|__Program.cs
|__NewTypes.csproj
```

`IPet.cs`:
```csharp
using System;

namespace Pets
{
    public interface IPet
    {
        string TalkToOwner();
    }
}
```

`Dog.cs`:
```csharp
using System;

namespace Pets
{
    public class Dog : IPet
    {
        public string TalkToOwner() => "Woof!";
    }
}
```

`Cat.cs`:
```csharp
using System;

namespace Pets
{
    public class Cat : IPet
    {
        public string TalkToOwner() => "Meow!";
    }
}
```

`Program.cs`:
```csharp
using System;
using Pets;
using System.Collections.Generic;

namespace ConsoleApplication
{
    public class Program
    {
        public static void Main(string[] args)
        {
            List<IPet> pets = new List<IPet>
            {
                new Dog(),
                new Cat()  
            };
            
            foreach (var pet in pets)
            {
                Console.WriteLine(pet.TalkToOwner());
            }
        }
    }
}
```

`NewTypes.csproj`:
```xml
<Project ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" />
  
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.0</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <Compile Include="**\*.cs" />
    <EmbeddedResource Include="**\*.resx" />
  </ItemGroup>

  <ItemGroup>
    <PackageReference Include="Microsoft.NETCore.App">
      <Version>1.0.1</Version>
    </PackageReference>
    <PackageReference Include="Microsoft.NET.Sdk">
      <Version>1.0.0-alpha-20161104-2</Version>
      <PrivateAssets>All</PrivateAssets>
    </PackageReference>
  </ItemGroup>
  
  <Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />
</Project>
```

Если выполнить эту программу:

```
$ dotnet restore
$ dotnet run
Woof!
Meow!
```

Чтобы расширить проект, можно добавить новые типы домашних животных (например, `Bird`).

## <a name="testing-your-console-app"></a>Тестирование консольного приложения

На некотором этапе может потребоваться протестировать проект. Вот как можно это сделать.

1. Переместите исходный код существующего проекта в новую папку `src`.

   ```
   /Project
   |__/src
   ```

2. Создайте каталог `/test`, а затем перейдите в него с помощью команды `cd`.

   ```
   /Project
   |__/src
   |__/test
   ```

3. Инициализируйте каталог с помощью команды `dotnet new xunit`. Предполагается, что вы воспользуетесь Xunit, но это также можно сделать с помощью MSTest, изменив `xunit` на `mstest`.
   
### <a name="example-extending-the-newtypes-project"></a>Пример. Расширение проекта NewTypes

Теперь, когда вы реализовали систему проектов, можно создать тестовый проект и приступить к созданию тестов. Далее в этом руководстве мы будем использовать и расширять [образец проекта Types](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/NewTypesMsBuild). Кроме того, будет использоваться платформа тестирования [Xunit](https://xunit.github.io/). Вы можете рассмотреть этот пример или создать собственную многопроектную систему с тестами.

Структура проекта в целом должна выглядеть следующим образом:

```
/NewTypes
|__/src
   |__/NewTypes
      |__/Pets
         |__Dog.cs
         |__Cat.cs
         |__IPet.cs
      |__Program.cs
      |__NewTypes.csproj
|__/test
   |__NewTypesTests
      |__PetTests.cs
      |__NewTypesTests.csproj
```

В тестовом проекте должно быть еще два новых компонента:

1. Правильный файл *NewTypesTests.csproj* со следующими элементами:

   * ссылка на `xunit`
   * ссылка на `dotnet-test-xunit`
   * ссылка на пространство имен, соответствующее тестируемому коду;

   Для сборки просто введите `dotnet new xunit` в командной строке в каталоге *NewTypesTests*, а затем добавьте ссылку на проект в проект `NewTypes`.

    `NewTypesTests/NewTypesTests.csproj`:
    ```xml
    <Project ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
      <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" />

      <PropertyGroup>
        <OutputType>Exe</OutputType>
        <TargetFramework>netcoreapp1.0</TargetFramework>
      </PropertyGroup>

      <ItemGroup>
        <Compile Include="**\*.cs" />
        <EmbeddedResource Include="**\*.resx" />
      </ItemGroup>

      <ItemGroup>
        <PackageReference Include="Microsoft.NETCore.App">
          <Version>1.0.1</Version>
        </PackageReference>
        <PackageReference Include="Microsoft.NET.Sdk">
          <Version>1.0.0-alpha-20161104-2</Version>
          <PrivateAssets>All</PrivateAssets>
        </PackageReference>
        <PackageReference Include="Microsoft.NET.Test.Sdk">
          <Version>15.0.0-preview-20161024-02</Version>
        </PackageReference>
        <PackageReference Include="xunit">
          <Version>2.2.0-beta3-build3402</Version>
        </PackageReference>
        <PackageReference Include="xunit.runner.visualstudio">
          <Version>2.2.0-beta4-build1188</Version>
        </PackageReference>
        <ProjectReference Include="../../src/NewTypes/NewTypes.csproj"/>
      </ItemGroup>

      <Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />
    </Project>
    ```

2. класс теста xUnit.

    `PetTests.cs`: 
    ```csharp
    using System;
    using Xunit;
    using Pets;
    public class PetTests
    {
        [Fact]
        public void DogTalkToOwnerTest()
        {
            string expected = "Woof!";
            string actual = new Dog().TalkToOwner();
            
            Assert.Equal(expected, actual);
        }
        
        [Fact]
        public void CatTalkToOwnerTest()
        {
            string expected = "Meow!";
            string actual = new Cat().TalkToOwner();
            
            Assert.Equal(expected, actual);
        }
    }
    ```
   
Теперь можно выполнить тесты. Команда [`dotnet test`](../tools/dotnet-test.md) запускает средство выполнения тестов, которое вы указали в проекте. Начинать следует с каталога верхнего уровня.
 
```
$ cd test/NewTypesTests
$ dotnet restore
$ dotnet test
```
 
Выходные данные должны выглядеть следующим образом:
 
```
xUnit.net .NET CLI test runner (64-bit win10-x64)
  Discovering: NewTypesTests
  Discovered:  NewTypesTests
  Starting:    NewTypesTests
  Finished:    NewTypesTests
=== TEST EXECUTION SUMMARY ===
   NewTypesTests  Total: 2, Errors: 0, Failed: 0, Skipped: 0, Time: 0.144s
SUMMARY: Total: 1 targets, Passed: 1, Failed: 0.
```

