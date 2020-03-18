---
title: Разработка библиотек с помощью .NET Core CLI
description: Узнайте, как создавать библиотеки для .NET Core с помощью .NET Core CLI. Вы создадите библиотеку, которая поддерживает несколько платформ.
author: cartermp
ms.date: 05/01/2017
ms.openlocfilehash: c23c1f027b4d6d09c50eb2257d34f72ec56302f4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503506"
---
# <a name="develop-libraries-with-the-net-core-cli"></a>Разработка библиотек с помощью .NET Core CLI

В этой статье показано, как создавать библиотеки для .NET с помощью .NET Core CLI. CLI предоставляет эффективный и низкоуровневый интерфейс, работающий в любых поддерживаемых операционных системах. Вы по-прежнему можете создавать библиотеки с помощью Visual Studio. Если вы предпочитаете такой способ, обратитесь к [руководству по Visual Studio](library-with-visual-studio.md).

## <a name="prerequisites"></a>Prerequisites

На компьютере должны быть установлены [пакет SDK и интерфейс CLI для .NET Core ](https://dotnet.microsoft.com/download).

При работе с разделами, в которых используются различные версии .NET Framework, на компьютере с ОС Windows должна быть установлена платформа [.NET Framework](https://dotnet.microsoft.com).

Кроме того, если необходимо поддерживать целевые платформы .NET Framework предыдущих версий, требуется установить целевые пакеты или пакеты разработчиков со [страницы с доступными для скачивания архивами для .NET](https://dotnet.microsoft.com/download/archives) См. таблицу ниже.

| Версия платформы .NET Framework | Скачиваемые компоненты                                       |
| ---------------------- | ------------------------------------------------------ |
| 4.6.1                  | .NET Framework 4.6.1 Targeting Pack                    |
| 4.6                    | .NET Framework 4.6 Targeting Pack                      |
| 4.5.2                  | .NET Framework 4.5.2 Developer Pack                    |
| 4.5.1                  | .NET Framework 4.5.1 Developer Pack                    |
| 4,5                    | Пакет средств разработки программного обеспечения Windows для Windows 8         |
| 4.0                    | Пакет SDK для Windows 7 и .NET Framework 4         |
| 2.0, 3.0 и 3.5      | Среда выполнения .NET Framework 3.5 с пакетом обновления 1 (SP1) (либо версия для Windows 8 или более поздняя) |

## <a name="how-to-target-the-net-standard"></a>Нацеливание на .NET Standard

Если вы незнакомы с платформой .NET Standard, дополнительные сведения см. в [этом разделе](../../standard/net-standard.md).

В этом разделе есть таблица, которая сопоставляет версии .NET Standard с различными реализациями:

[!INCLUDE [net-standard-table](../../../includes/net-standard-table.md)]

Вот что значит эта таблица в контексте создания библиотеки:

Версия .NET Standard, которую вы выберете, будет компромиссом между наличием новейших API-интерфейсов и возможностью нацеливать приложение на большее количество реализаций .NET и версий .NET Standard. Диапазон целевых платформ и версий определяется выбранной версией `netstandardX.X` (где `X.X` — это номер версии), которая добавляется в файл проекта (`.csproj` или `.fsproj`).

При нацеливании на платформу .NET Standard есть три основных варианта, выбор которых зависит от ваших потребностей.

1. Вы можете использовать версию .NET Standard по умолчанию, которая предоставляется шаблонами `netstandard1.4`, что обеспечивает доступ к большинству API-интерфейсов .NET Standard, сохраняя совместимость с UWP, .NET Framework 4.6.1 и .NET Standard 2.0.

    ```xml
    <Project Sdk="Microsoft.NET.Sdk">
      <PropertyGroup>
        <TargetFramework>netstandard1.4</TargetFramework>
      </PropertyGroup>
    </Project>
    ```

2. Изменив значение в узле `TargetFramework` файла проекта можно использовать более раннюю или более позднюю версию .NET Standard.

    Версии .NET Standard обладают обратной совместимостью. Это означает, что библиотеки `netstandard1.0` выполняются на платформах `netstandard1.1` и более поздних версий. Однако, прямой совместимости нет. Платформы .NET Standard нижнего уровня не могут ссылаться на платформы высшего уровня. Это значит, что библиотеки `netstandard1.0` не могут ссылаться на библиотеки, предназначенные для `netstandard1.1` или более поздних версий. Выберите версию Standard, которая предоставляет подходящее сочетание интерфейсов API и поддерживаемых платформ для ваших потребностей. Сейчас рекомендуем использовать версию `netstandard1.4`.

3. Если требуется нацеливание на .NET Framework версии 4.0 или более ранней или использование интерфейса API, доступного в .NET Framework, но не в .NET Standard (например, `System.Drawing`), прочитайте следующие подразделы, чтобы узнать, как осуществляется настройка для разных версий.

## <a name="how-to-target-net-framework"></a>Нацеливание на .NET Framework.

> [!NOTE]
> В этих инструкциях предполагается, что на компьютере установлена платформа .NET Framework. Чтобы установить зависимости, обратитесь к разделу [Предварительные требования](#prerequisites).

Имейте в виду, что некоторые используемые здесь версии .NET Framework больше не поддерживаются. Сведения о неподдерживаемых версиях см. в статье [Вопросы и ответы о политике по срокам поддержки Microsoft .NET Framework](https://support.microsoft.com/gp/framework_faq/en-us).

Чтобы охватить максимальное количество разработчиков и проектов, используйте .NET Framework 4.0 в качестве базовой целевой платформы. Для нацеливания на .NET Framework начните использовать правильный моникер целевой платформы (TFM), соответствующий версии .NET Framework, которая должна поддерживаться.

| Версия платформы .NET Framework | TFM      |
| ---------------------- | -------- |
| .NET Framework 2.0     | `net20`  |
| .NET Framework 3.0     | `net30`  |
| .NET Framework 3,5     | `net35`  |
| .NET Framework 4.0     | `net40`  |
| .NET Framework 4.5     | `net45`  |
| .NET Framework 4.5.1   | `net451` |
| .NET Framework 4.5.2   | `net452` |
| .NET Framework 4.6     | `net46`  |
| .NET Framework 4.6.1   | `net461` |
| .NET Framework 4.6.2   | `net462` |
| .NET Framework 4.7     | `net47`  |
| .NET Framework 4.8     | `net48`  |

Вставьте этот моникер целевой платформы в раздел `TargetFramework` файла проекта. Например, вот как создать библиотеку, предназначенную для .NET Framework 4.0:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>net40</TargetFramework>
  </PropertyGroup>
</Project>
```

Вот и все! Хотя эта библиотека компилируется только для .NET Framework 4, ее можно использовать в более поздних версиях .NET Framework.

## <a name="how-to-multitarget"></a>Настройка для различных версий

> [!NOTE]
> В приведенных ниже инструкциях предполагается, что на компьютере установлена платформа .NET Framework. Сведения о зависимостях, которые необходимо установить, и о том, где их можно скачать, см. в разделе [Предварительные требования](#prerequisites).

Если проект поддерживает как .NET Framework, так и .NET Core, может потребоваться нацеливание на более старые версии .NET Framework. В такой ситуации, если вам нужно применять более новые интерфейсы API и языковые конструкции для новых целевых платформ, используйте директивы `#if` в коде. Кроме того, может потребоваться добавить разные пакеты и зависимости для каждой целевой платформы, чтобы включить различные интерфейсы API, необходимые в каждом случае.

Предположим, имеется библиотека, выполняющая сетевые операции по протоколу HTTP. Для .NET Standard и .NET Framework версии 4.5 или более поздней можно использовать класс `HttpClient` из пространства имен `System.Net.Http`. Однако в более ранних версиях .NET Framework нет класса `HttpClient`, поэтому вместо него можно использовать класс `WebClient` из пространства имен `System.Net`.

Файл проекта может выглядеть следующим образом:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFrameworks>netstandard1.4;net40;net45</TargetFrameworks>
  </PropertyGroup>

  <!-- Need to conditionally bring in references for the .NET Framework 4.0 target -->
  <ItemGroup Condition="'$(TargetFramework)' == 'net40'">
    <Reference Include="System.Net" />
  </ItemGroup>

  <!-- Need to conditionally bring in references for the .NET Framework 4.5 target -->
  <ItemGroup Condition="'$(TargetFramework)' == 'net45'">
    <Reference Include="System.Net.Http" />
    <Reference Include="System.Threading.Tasks" />
  </ItemGroup>
</Project>
```

Вы заметите три основных изменения:

1. Узел `TargetFramework` был заменен на `TargetFrameworks`, внутри которого содержатся три моникера целевой платформы.
1. Добавлен узел `<ItemGroup>` для целевой платформы `net40`, который извлекает одну ссылку на .NET Framework.
1. Добавлен узел `<ItemGroup>` для целевой платформы `net45`, который извлекает две ссылки на .NET Framework.

Система сборки распознает следующие символы препроцессора, используемые в директивах `#if`:

[!INCLUDE [Preprocessor symbols](../../../includes/preprocessor-symbols.md)]

Ниже приведен пример использования условной компиляции для каждого целевого объекта:

```csharp
using System;
using System.Text.RegularExpressions;
#if NET40
// This only compiles for the .NET Framework 4 targets
using System.Net;
#else
 // This compiles for all other targets
using System.Net.Http;
using System.Threading.Tasks;
#endif

namespace MultitargetLib
{
    public class Library
    {
#if NET40
        private readonly WebClient _client = new WebClient();
        private readonly object _locker = new object();
#else
        private readonly HttpClient _client = new HttpClient();
#endif

#if NET40
        // .NET Framework 4.0 does not have async/await
        public string GetDotNetCount()
        {
            string url = "https://www.dotnetfoundation.org/";

            var uri = new Uri(url);

            string result = "";

            // Lock here to provide thread-safety.
            lock(_locker)
            {
                result = _client.DownloadString(uri);
            }

            int dotNetCount = Regex.Matches(result, ".NET").Count;

            return $"Dotnet Foundation mentions .NET {dotNetCount} times!";
        }
#else
        // .NET 4.5+ can use async/await!
        public async Task<string> GetDotNetCountAsync()
        {
            string url = "https://www.dotnetfoundation.org/";

            // HttpClient is thread-safe, so no need to explicitly lock here
            var result = await _client.GetStringAsync(url);

            int dotNetCount = Regex.Matches(result, ".NET").Count;

            return $"dotnetfoundation.org mentions .NET {dotNetCount} times in its HTML!";
        }
#endif
    }
}
```

При сборке этого проекта с `dotnet build` вы увидите, что в папке `bin/` появились три каталога:

```
net40/
net45/
netstandard1.4/
```

Каждый из них содержит файлы `.dll` для соответствующего целевого объекта.

## <a name="how-to-test-libraries-on-net-core"></a>Тестирование библиотек в .NET Core

Необходимо иметь возможность тестирования проектов на различных платформах. Вы можете использовать [xUnit](https://xunit.github.io/) или MSTest без дополнительной настройки. Обе платформы тестирования идеально подходят для модульного тестирования библиотеки в .NET Core. Настройка тестовых проектов для решения зависит от [его структуры](#structuring-a-solution). В следующем примере предполагается, что каталог с тестами и каталог с исходным кодом находятся в одном и том же каталоге верхнего уровня.

> [!NOTE]
> В этом примере используются некоторые команды [.NET Core CLI](../tools/index.md). Дополнительные сведения см. в разделах [dotnet new](../tools/dotnet-new.md) и [dotnet sln](../tools/dotnet-sln.md).

1. Настройте решение. Это можно сделать с помощью следующих команд:

   ```dotnetcli
   mkdir SolutionWithSrcAndTest
   cd SolutionWithSrcAndTest
   dotnet new sln
   dotnet new classlib -o MyProject
   dotnet new xunit -o MyProject.Test
   dotnet sln add MyProject/MyProject.csproj
   dotnet sln add MyProject.Test/MyProject.Test.csproj
   ```

   Эти команды создадут проекты и объединят их в решение. Ваш каталог для `SolutionWithSrcAndTest` должен выглядеть следующим образом:

   ```
   /SolutionWithSrcAndTest
   |__SolutionWithSrcAndTest.sln
   |__MyProject/
   |__MyProject.Test/
   ```

1. Перейдите в каталог тестового проекта и добавьте ссылку на `MyProject.Test` из `MyProject`.

   ```dotnetcli
   cd MyProject.Test
   dotnet add reference ../MyProject/MyProject.csproj
   ```

1. Восстановите пакеты и соберите проекты:

   ```dotnetcli
   dotnet restore
   dotnet build
   ```

   [!INCLUDE[DotNet Restore Note](../../../includes/dotnet-restore-note.md)]

1. Убедитесь, что xUnit запущен, выполнив команду `dotnet test`. Если вы решили использовать MSTest, запустите средство запуска консоли MSTest вместо xUnit.

Вот и все! Теперь вы можете протестировать библиотеку для всех платформ с помощью средств командной строки. Теперь, когда все настроено, протестировать библиотеку очень легко:

1. Внесите изменения в библиотеку.
1. Выполните тесты в тестовом каталоге из командной строки с помощью команды `dotnet test`.

При вызове команды `dotnet test` будет автоматически выполнена повторная сборка кода.

## <a name="how-to-use-multiple-projects"></a>Использование нескольких проектов

В случае с более крупными библиотеками, как правило, требуется реализовывать функциональность в разных проектах.

Представим, что необходимо создать библиотеку, которую можно использовать в идиоматичном коде на языках C# и F#. Это означает, что библиотека будет использоваться способами, естественными для языков C# и F#. Например, в C# можно использовать библиотеку следующим образом:

```csharp
using AwesomeLibrary.CSharp;

public Task DoThings(Data data)
{
    var convertResult = await AwesomeLibrary.ConvertAsync(data);
    var result = AwesomeLibrary.Process(convertResult);
    // do something with result
}
```

В F# это может выглядеть так.

```fsharp
open AwesomeLibrary.FSharp

let doWork data = async {
    let! result = AwesomeLibrary.AsyncConvert data // Uses an F# async function rather than C# async method
    // do something with result
}
```

Подобные сценарии использования предполагают, что интерфейсы API, к которым осуществляется доступ, должны иметь разную структуру для C# и F#.  Стандартным подходом к решению этой задачи является факторинг всей логики библиотеки в базовом проекте и определение в проектах C# и F# уровней API, которые вызывают этот базовый проект.  Далее в этом разделе будут использоваться следующие имена:

* **AwesomeLibrary.Core** — базовый проект, содержащий всю логику библиотеки;
* **AwesomeLibrary.CSharp** — проект с открытыми интерфейсами API, предназначенными для использования в коде на языке C#
* **AwesomeLibrary.FSharp** — проект с открытыми интерфейсами API, предназначенными для использования в коде на языке F#

Чтобы получить ту же структуру каталогов, что и в этом руководстве, выполните следующие команды в окне терминала:

```dotnetcli
mkdir AwesomeLibrary && cd AwesomeLibrary
dotnet new sln
mkdir AwesomeLibrary.Core && cd AwesomeLibrary.Core && dotnet new classlib
cd ..
mkdir AwesomeLibrary.CSharp && cd AwesomeLibrary.CSharp && dotnet new classlib
cd ..
mkdir AwesomeLibrary.FSharp && cd AwesomeLibrary.FSharp && dotnet new classlib -lang "F#"
cd ..
dotnet sln add AwesomeLibrary.Core/AwesomeLibrary.Core.csproj
dotnet sln add AwesomeLibrary.CSharp/AwesomeLibrary.CSharp.csproj
dotnet sln add AwesomeLibrary.FSharp/AwesomeLibrary.FSharp.fsproj
```

Эти команды добавят три указанные выше проекта и файл решения, который их связывает. Создание файла решения и связывание проектов позволит создавать и восстанавливать проекты из верхнего уровня.

### <a name="project-to-project-referencing"></a>Ссылки проектов на проекты

Ссылку на проект лучше всего добавить с помощью интерфейса командной строки .NET Core. Из каталогов проекта **AwesomeLibrary.CSharp** и **AwesomeLibrary.FSharp** выполните следующую команду:

```dotnetcli
dotnet add reference ../AwesomeLibrary.Core/AwesomeLibrary.Core.csproj
```

Теперь файлы **AwesomeLibrary.CSharp** и **AwesomeLibrary.FSharp** будут ссылаться на **AwesomeLibrary.Core** в качестве целевого объекта `ProjectReference`.  Чтобы это проверить, просмотрите файлы проектов, и вы увидите в них следующий код:

```xml
<ItemGroup>
  <ProjectReference Include="..\AwesomeLibrary.Core\AwesomeLibrary.Core.csproj" />
</ItemGroup>
```

Если вы не хотите использовать интерфейс командной строки .NET Core, можете добавить этот раздел в каждый файл проекта вручную.

### <a name="structuring-a-solution"></a>Структурирование решения

Еще один важный аспект решений с несколькими проектами — правильное формирование общей структуры. Код можно упорядочить так, как вам удобно. Если каждый проект связан с файлом решения с помощью `dotnet sln add`, вы сможете запускать команды `dotnet restore` и `dotnet build` на уровне проекта.
