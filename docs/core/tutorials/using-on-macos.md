---
title: "Начало работы с .NET Core в Mac OS"
description: "Начало работы с .NET Core в Mac OS с помощью Visual Studio Code"
keywords: .NET, .NET Core
author: bleroy
ms.author: mairaw
ms.date: 02/08/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 8ad82148-dac8-4b31-9128-b0e9610f4d9b
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: c4d1b7690ca87f2a1a9ced4d82e47aee2f7ecc9f
ms.lasthandoff: 03/07/2017

---

# <a name="getting-started-with-net-core-on-macos-using-visual-studio-code"></a>Начало работы с .NET Core в Mac OS с помощью Visual Studio Code

В этом документе приводится обзор действий и рабочего процесса для создания решения .NET Core с помощью [Visual Studio Code](http://code.visualstudio.com).
Вы узнаете, как создавать проекты и модульные тесты, использовать средства отладки и включать библиотеки сторонних разработчиков посредством [NuGet](http://nuget.org).

В этой статье используется Visual Studio Code в Mac OS. Где это необходимо, приводятся отличия для платформы Windows.

## <a name="prerequisites"></a>Предварительные требования

Прежде чем приступать к работе, нужно установить [пакет SDK для .NET Core](https://www.microsoft.com/net/core). Пакет SDK для .NET Core содержит последний выпуск платформы и среды выполнения .NET Core.

Также необходимо установить [Visual Studio Code](http://code.visualstudio.com).
В процессе изучения этой статьи вы также установите расширения, которые улучшат возможности разработки для .NET Core.

## <a name="getting-started"></a>Начало работы

Исходный код для этого учебника доступен на сайте [GitHub](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/golden).

Запустите Visual Studio Code. Нажмите клавиши CTRL+"\`" (символ обратной кавычки), чтобы открыть встроенный терминал в VS Code. (Если хотите, вы можете использовать отдельное окно терминала.)

К моменту завершения учебника вы создадите три проекта: проект библиотеки, тесты для этого проекта и консольное приложение, использующее библиотеку. 

Начнем с создания папок. В терминале создайте каталог golden. В VS Code откройте каталог *golden*. Это корневой каталог вашего решения. Запустите команду [`dotnet new`](../tools/dotnet-new.md), чтобы создать решение:

```
dotnet new sln
```

Эта команда создает файл *golden.sln* для всего решения.

Ваша следующая задача — создать библиотеку. В окне терминала (встроенного терминала в VS Code или другого терминала) перейдите в каталог *golden/* и введите следующую команду:

```
dotnet new classlib -o library
```

При этом создается проект библиотеки с двумя файлами *library.csproj* и *Class1.cs* в каталоге *library*. Этот проект библиотеки требуется включить в ваше решение. Запустите команду [`dotnet sln`](../tools/dotnet-sln.md), чтобы добавить только что созданный проект *library.csproj* в решение:

```
dotnet sln add library/library.csproj
```

Давайте рассмотрим созданный проект. Файл *library.csproj* содержит следующие сведения:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netstandard1.4</TargetFramework>
  </PropertyGroup>

</Project>
```

В этом проекте библиотеки будет использоваться представление JSON объектов, поэтому необходимо добавить ссылку на пакет NuGet `Newtonsoft.Json`. Команда `dotnet add` добавляет в проект новые элементы. Чтобы добавить ссылку на пакет NuGet, используйте команду `package` и укажите имя пакета. 

```
dotnet add library package Newtonsoft.Json
```

При этом `Newtonsoft.Json` и его зависимости добавляются в проект библиотеки. Кроме того, можно вручную изменить файл *library.csproj* и добавить следующий узел:

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json">
    <Version>9.0.1</Version>
  </PackageReference>
</ItemGroup>
```

После добавления этих зависимостей вам необходимо установить пакеты в рабочем пространстве. Выполните команду `dotnet restore`, чтобы обновить все зависимости, и запишите файл *obj/project.assets.json* в каталог проекта. Этот файл содержит полное дерево зависимостей со всеми зависимостями в проекте. Считывать этот файл не нужно; он используется средствами из пакета SDK для .NET Core.

Теперь обновим код на языке C#. Давайте создадим класс `Thing`, который содержит один общий метод. Этот метод будет возвращать сумму двух чисел, но для этого он будет преобразовывать число в строку JSON, а затем десериализовывать ее. Измените имя файла *Class1.cs* на *Thing.cs*. Затем замените существующий код (шаблонного класса Class1) следующим кодом:

```csharp
using static Newtonsoft.Json.JsonConvert;

namespace Library
{
    public class Thing
    {
        public int Get(int left, int right) =>
            DeserializeObject<int>($"{left + right}");
    }
}
```

В нем используется ряд современных возможностей C#, таких как статические операторы using, члены, воплощающие выражения, и интерполированные строки. Сведения о них можно получить из [руководства по языку C#](../../csharp/index.md).

Теперь, когда вы обновили код, вы можете выполнить сборку библиотеки с помощью команды `dotnet build`.

Теперь у вас есть готовый файл *library.dll* в каталоге *golden/library/bin/Debug/netstandard1.4*.

### <a name="writing-the-test-project"></a>Написание тестового проекта

Давайте создадим тестовый проект для библиотеки, сборку которой вы выполнили. Перейдите в каталог *golden*. Выполните команду `dotnet new xunit -o test-library`, чтобы создать тестовый проект. Этот проект также нужно добавить в решение, выполнив `dotnet sln add test-library/test-library.csproj`.

Вам потребуется добавить узел зависимости для библиотеки, которую вы создали в предыдущих шагах. Команда `dotnet add reference` делает это:

```
dotnet add test-library/test-library.csproj reference library/library.csproj
```

Или можно вручную изменить файл *test-library.csproj* и добавить следующий узел:

```xml
<ItemGroup>
  <ProjectReference Include="..\library\library.csproj" />
</ItemGroup>
```

Узел `library` указывает, что эта зависимость должна разрешаться в проект в текущем рабочем пространстве. Если явно не указать это, существует возможность того, что сборка тестового проекта будет выполнена для пакета NuGet с тем же именем.

Теперь, когда зависимости правильно настроены, давайте создадим тесты для библиотеки. Откройте файл *UnitTest1.cs* и замените его содержимое следующим кодом:

```csharp
using Library;
using Xunit;

namespace TestApp
{
    public class LibraryTests
    {
        [Fact]
        public void TestThing() {
            Assert.Equal(42, new Thing().Get(19, 23));
        }
    }
}
```

Теперь выполните команды `dotnet restore` и `dotnet build`. Эти команды будут рекурсивно искать все проекты для восстановления зависимостей и их сборки.
Наконец, выполните команду `dotnet test test-library/test-library.csproj` для запуска тестов.
Консольное средство выполнения тестов xUnit проведет один тест и сообщит о том, что он пройден. 

### <a name="writing-the-console-app"></a>Написание консольного приложения

Выполните команду `dotnet new console -o app` в терминале, чтобы создать консольное приложение. Этот проект также является частью решения, поэтому запустите `dotnet sln add app/app.csproj` для добавления проекта в решение.

Консольное приложение использует библиотеку, которую вы создали и протестировали в предыдущих шагах. Это нужно указать, выполнив `dotnet add reference` еще раз:

```
dotnet add app/app.csproj reference library/library.csproj
```

Выполните команду `dotnet restore`, чтобы восстановить все зависимости. Откройте файл *program.cs* и замените содержимое метода `Main` следующей строкой:

```csharp
WriteLine($"The answer is {new Thing().Get(19, 23)}");
```

В начало файла необходимо добавить пару директив `using`:

```csharp
using static System.Console;
using Library;
```

Затем выполните команду `dotnet build`. Она создаст сборки, после чего вы можете ввести `dotnet run -p app/app.csproj`, чтобы запустить исполняемый файл.
Аргумент `-p` для `dotnet run` указывает проект для основного приложения.

### <a name="debugging-your-application"></a>Отладка приложения

Вы можете отладить код в VS Code с помощью расширения C#.
Для установки этого расширения нажмите клавишу `F1`, чтобы открыть палитру VS Code. Введите команду `ext install`, чтобы просмотреть список расширений. Выберите расширение C#. (Дополнительные сведения см. на странице [документации по расширению C# для Visual Studio Code](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).)

После установки расширения в VS Code появится запрос на перезапуск приложения для загрузки нового расширения. После установки расширения можно открыть вкладку отладчика (см. рисунок).

![Отладчик VS Code](./media/using-on-macos/vscodedebugger.png)

Установите точку останова в операторе `WriteLine` в методе `Main`. Для этого нажмите клавишу `F9` или щелкните мышью в левом поле напротив строки, в которой нужно установить точку останова. Откройте отладчик, щелкнув значок отладки в левой части экрана VS Code (см. рисунок). После этого нажмите кнопку "Воспроизвести", чтобы запустить приложение в режиме отладки.

Вы должны достичь точки останова. Выполните метод `Get` по шагам и убедитесь в том, что переданы правильные аргументы. Проверьте, равен ли результат 42.

