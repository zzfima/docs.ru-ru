---
title: Учебник. Создание решения .NET Core в macOS с помощью Visual Studio Code
description: В этом документе приводится обзор действий и рабочего процесса для создания решения .NET Core в Visual Studio Code.
ms.date: 12/19/2019
ms.openlocfilehash: 4dc44a0aa155dca3c106a7da68cf100ef644b58b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715304"
---
# <a name="tutorial-create-a-net-core-solution-in-macos-using-visual-studio-code"></a>Учебник. Создание решения .NET Core в macOS с помощью Visual Studio Code

В этом документе приводится обзор действий и рабочего процесса для создания решения .NET Core для macOS. Вы узнаете, как создавать проекты и модульные тесты, использовать средства отладки и включать библиотеки сторонних разработчиков с помощью [NuGet](https://www.nuget.org/).

> [!NOTE]
> В этой статье используется [Visual Studio Code](https://code.visualstudio.com) для macOS.

## <a name="prerequisites"></a>Предварительные требования

Установите [пакета SDK для .NET Core](https://dotnet.microsoft.com/download). Пакет SDK для .NET Core содержит последний выпуск платформы и среды выполнения .NET Core.

Установите [Visual Studio Code](https://code.visualstudio.com). В ходе этой статьи вы также установите расширения Visual Studio Code, которые улучшат возможности разработки .NET Core.

Установите расширение C# для Visual Studio Code. Для этого откройте Visual Studio Code и нажмите клавишу <kbd>Fn</kbd>+<kbd>F1</kbd>, чтобы открыть палитру Visual Studio Code. Введите команду **ext install**, чтобы просмотреть список расширений. Выберите расширение C#. Перезапустите Visual Studio Code, чтобы включить расширение. Дополнительные сведения см. в [документации по расширению C# для Visual Studio Code](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).

## <a name="get-started"></a>Начало работы

В этом руководстве вы создадите три проекта: проект библиотеки, тесты для этого проекта библиотеки и консольное приложение, которое использует библиотеку. [Просмотреть и скачать исходный код](https://github.com/dotnet/samples/tree/master/core/getting-started/golden) для этой статьи можно в репозитории dotnet/samples на сайте GitHub. Инструкции по загрузке см. в разделе [Просмотр и скачивание примеров](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

Запустите Visual Studio Code. Нажмите клавишу <kbd>CTRL</kbd>+<kbd>\`</kbd> (символ обратной кавычки или обратного апострофа) или выберите **Вид > Терминал**, чтобы открыть встроенный терминал в Visual Studio Code. Если вы предпочитаете работать не в среде Visual Studio Code, можете открыть внешнюю оболочку в Explorer, выбрав пункт меню проводника **Открыть в командной строке** (в Mac и Linux — **Открыть в терминале**).

Для начала нужно создать файл решения, который выступает в качестве контейнера для одного или нескольких проектов .NET Core. В окне терминала выполните команду [`dotnet new`](../tools/dotnet-new.md), чтобы создать новое решение *golden.sln* в новой папке с именем *golden*:

```dotnetcli
dotnet new sln -o golden
```

Перейдите в новую папку *golden* и выполните следующую команду, чтобы создать проект библиотеки. Эта команда создает два файла — *library.csproj* и *Class1.cs* — в папке *library*:

```dotnetcli
dotnet new classlib -o library
```

Выполните команду [`dotnet sln`](../tools/dotnet-sln.md), чтобы добавить только что созданный проект *library.csproj* в решение:

```dotnetcli
dotnet sln add library/library.csproj
```

Файл *library.csproj* содержит следующие сведения:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
  </PropertyGroup>

</Project>
```

Наши библиотечные методы сериализуют и десериализуют объекты в формате JSON. Для поддержки сериализации и десериализации JSON добавьте ссылку на пакет NuGet `Newtonsoft.Json`. Команда `dotnet add` добавляет в проект новые элементы. Чтобы добавить ссылку на пакет NuGet, выполните команду [`dotnet add package`](../tools/dotnet-add-package.md), указав имя пакета:

```dotnetcli
dotnet add library package Newtonsoft.Json
```

Эта команда добавляет `Newtonsoft.Json` и его зависимости в проект библиотеки. Также можно изменить файл *library.csproj* вручную, добавив следующий узел:

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="12.0.2" />
</ItemGroup>
```

Выполните команду [`dotnet restore`](../tools/dotnet-restore.md) ([см. примечание](#dotnet-restore-note)), которая восстанавливает зависимости и создает подкаталог *obj* в каталоге *library*. Этот подкаталог содержит три файла, в том числе файл *project.assets.json*:

```dotnetcli
dotnet restore
```

В каталоге *library* переименуйте файл *Class1.cs* в *Thing.cs*. Замените код следующим кодом:

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

Класс `Thing` содержит один открытый метод `Get`, который возвращает сумму двух чисел, но для этого преобразует сумму в строку и затем десериализует ее в целое число. В нем используется ряд современных возможностей C#, таких как [директивы `using static`](../../csharp/language-reference/keywords/using-static.md), [члены, воплощающие выражения](../../csharp/whats-new/csharp-7.md#more-expression-bodied-members) и [интерполяция строк](../../csharp/language-reference/tokens/interpolated.md).

Соберите библиотеку, выполнив команду [`dotnet build`](../tools/dotnet-build.md). Эта команда создает файл *library.dll* в каталоге *golden/library/bin/Debug/netstandard1.4*:

```dotnetcli
dotnet build
```

## <a name="create-the-test-project"></a>Создание тестового проекта

Создайте тестовый проект для библиотеки. Из папки *golden* создайте тестовый проект:

```dotnetcli
dotnet new xunit -o test-library
```

Добавьте тестовый проект в решение:

```dotnetcli
dotnet sln add test-library/test-library.csproj
```

Добавьте ссылку на проект библиотеки, созданной в предыдущем разделе, чтобы компилятор мог найти и использовать проект библиотеки. Используйте команду [`dotnet add reference`](../tools/dotnet-add-reference.md):

```dotnetcli
dotnet add test-library/test-library.csproj reference library/library.csproj
```

Также можно изменить файл *test-library.csproj* вручную, добавив следующий узел:

```xml
<ItemGroup>
  <ProjectReference Include="..\library\library.csproj" />
</ItemGroup>
```

Теперь, когда зависимости правильно настроены, создайте тесты для библиотеки. Откройте файл *UnitTest1.cs* и замените его содержимое следующим кодом:

```csharp
using Library;
using Xunit;

namespace TestApp
{
    public class LibraryTests
    {
        [Fact]
        public void TestThing() {
            Assert.NotEqual(42, new Thing().Get(19, 23));
        }
    }
}
```

Обратите внимание, что при создании модульного теста (`Assert.NotEqual`), который завершается ошибкой, вы проверяете утверждение, что 42 не равно 19+23 (42). При создании модульных тестов важно создать такое условие, при котором тест завершится с ошибкой. Это позволяет проверить его логику.

Из папки *golden* выполните следующие команды:

```dotnetcli
dotnet restore 
dotnet test test-library/test-library.csproj
```

Эти команды рекурсивно найдут все проекты для восстановления зависимостей, соберут эти проекты и активируют средство запуска тестов xUnit для запуска тестов. Первый тест, как и ожидается, завершается с ошибкой.

Откройте файл *UnitTest1.cs* и измените проверочное утверждение с `Assert.NotEqual` на `Assert.Equal`. Выполните следующую команду из папки *golden*, чтобы повторно запустить тест, который на этот раз завершится успешно:

```dotnetcli
dotnet test test-library/test-library.csproj
```

## <a name="create-the-console-app"></a>Создание консольного приложения

Консольное приложение, которое будет создано в этом разделе, зависит от проекта библиотеки, который был создан ранее, и вызывает библиотечный метод этого проекта при запуске. Вы увидите, как создавать повторно используемые библиотеки для нескольких проектов с помощью этого шаблона разработки.

Создайте новое консольное приложение из папки *golden*:

```dotnetcli
dotnet new console -o app
```

Добавьте проект консольного приложения в решение:

```dotnetcli
dotnet sln add app/app.csproj
```

Создайте зависимость от библиотеки, выполнив команду `dotnet add reference`:

```dotnetcli
dotnet add app/app.csproj reference library/library.csproj
```

Выполните команду `dotnet restore` ([см. примечание](#dotnet-restore-note)), чтобы восстановить зависимости для трех проектов в решении. Откройте файл *Program.cs* и замените содержимое метода `Main` следующей строкой:

```csharp
WriteLine($"The answer is {new Thing().Get(19, 23)}");
```

Добавьте две директивы `using` в начало файла *Program.cs*:

```csharp
using static System.Console;
using Library;
```

Выполните следующую команду `dotnet run`, чтобы запустить исполняемый файл. Значение `dotnet run` параметра `-p` указывает проект для основного приложения. Приложение выводит строку "The answer is 42".

```dotnetcli
dotnet run -p app/app.csproj
```

## <a name="debug-the-application"></a>Отладка приложения

Установите точку останова в инструкции `WriteLine` метода `Main`. Для этого нажмите клавишу <kbd>Fn</kbd>+<kbd>F9</kbd>, установив курсор в строку `WriteLine`, или щелкнув в левом поле строки, в которой вы хотите установить точку останова. В поле рядом со строкой кода появится красный кружок. При достижении точки останова выполнение кода приостанавливается *перед* той строкой, в которой расположена точка останова.

Откройте вкладку отладчика, щелкнув значок "Отладка" на панели инструментов Visual Studio Code и выбрав **Вид > Отладка** в меню или нажав клавиши <kbd>Command</kbd>+<kbd>SHIFT</kbd>+<kbd>D</kbd>:

![Отладчик Visual Studio Code](./media/using-on-macos/visual-studio-code-debugger.png)

Нажмите кнопку "Воспроизвести", чтобы запустить приложение в режиме отладки. Вы создали тестовый проект и приложение в этом проекте. Отладчик спрашивает, какой проект нужно запустить. Выберите нужный проект приложения. Приложение выполняется до точки останова, в которой оно останавливается. Выполните метод `Get` по шагам и убедитесь в том, что переданы правильные аргументы. Убедитесь, что ответ равен 42.

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
