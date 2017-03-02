---
title: "Разработка библиотек с помощью кроссплатформенных средств"
description: "Разработка библиотек с помощью кроссплатформенных средств"
keywords: .NET, .NET Core
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 9f6e8679-bd7e-4317-b3f9-7255a260d9cf
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 7f419e1fc2c9f442b08e19ede4e84f9cf6843a94
ms.lasthandoff: 03/02/2017

---

# <a name="developing-libraries-with-cross-platform-tools"></a>Разработка библиотек с помощью кроссплатформенных средств

**Некоторые сведения могут меняться по мере развития цепочки инструментов.**

В этой статье рассматривается создание библиотек для .NET с помощью кроссплатформенных средств интерфейса командной строки (CLI).  CLI предоставляет эффективный и низкоуровневый интерфейс, работающий в любых поддерживаемых операционных системах.  Вы по-прежнему можете создавать библиотеки с помощью Visual Studio. Если вы предпочитаете такой способ, обратитесь к [руководству по Visual Studio](libraries-with-vs.md).

## <a name="prerequisites"></a>Предварительные требования

На компьютере должны быть установлены [пакет SDK и интерфейс CLI для .NET Core ](https://www.microsoft.com/net/core).

Для разделов этого документа, касающихся версий .NET Framework или переносимых библиотек классов (PCL), необходима платформа [.NET Framework](http://getdotnet.azurewebsites.net/), установленная на компьютере с Windows.  

Кроме того, если необходимо поддерживать целевые платформы .NET Framework предыдущих версий, требуется установить пакеты нацеливания и пакеты для разработчиков, предназначенные для предыдущих версий платформы, со [страницы целевых платформ .NET](http://getdotnet.azurewebsites.net/target-dotnet-platforms.html).  См. таблицу ниже.

| Версия платформы .NET Framework | Скачиваемые компоненты |
| ---------------------- | ----------------- |
| 4.6.1 | .NET Framework 4.6.1 Targeting Pack |
| 4.6 | .NET Framework 4.6 Targeting Pack |
| 4.5.2 | .NET Framework 4.5.2 Developer Pack |
| 4.5.1 | .NET Framework 4.5.1 Developer Pack |
| 4.5 | Пакет средств разработки программного обеспечения Windows для Windows 8 |
| 4.0 | Пакет SDK для Windows 7 и .NET Framework 4 |
| 2.0, 3.0 и 3.5 | Среда выполнения .NET Framework 3.5 с пакетом обновления 1 (SP1) (либо версия для Windows 8 или более поздняя) |

## <a name="how-to-target-the-net-standard"></a>Нацеливание на .NET Standard

Если вы плохо знакомы с платформой .NET Standard, дополнительные сведения можно получить в разделе [Библиотека .NET Standard](../../standard/library.md).

В этом разделе есть таблица, в которой версии .NET Standard сопоставляются с различными реализациями:

| Имя платформы | Alias |  |  |  |  |  | | |
| :---------- | :--------- |:--------- |:--------- |:--------- |:--------- |:--------- |:--------- |:--------- |
|.NET Standard | netstandard | 1,0 | 1.1 | 1.2 | 1.3 | 1.4 | 1.5 | 1.6 |
|.NET Core|netcoreapp|&rarr;|&rarr;|&rarr;|&rarr;|&rarr;|&rarr;|1,0|
|.NET Framework|net|&rarr;|4.5|4.5.1|4.6|4.6.1|4.6.2|4.6.3|
|Платформы Mono и Xamarin||&rarr;|&rarr;|&rarr;|&rarr;|&rarr;|&rarr;|*|
|Универсальная платформа Windows |uap|&rarr;|&rarr;|&rarr;|&rarr;|10.0|||
|Windows|win|&rarr;|8.0|8.1|||||
|Windows Phone|wpa|&rarr;|&rarr;|8.1|||||
|Windows Phone Silverlight|wp|8.0|||||||

Вот что значит эта таблица в контексте создания библиотеки:

При выборе версии платформы .NET Standard необходимо найти компромисс между доступом к новейшим интерфейсам API и возможностью нацеливания на большее количество платформ и версий .NET.  Диапазон поддерживаемых платформ и версий определяется выбранной версией `netstandardX.X` (где `X.X` — это номер версии), которая добавляется в файл `project.json`.

Кроме того, соответствующий [зависимый пакет NuGet](https://www.nuget.org/packages/NETStandard.Library/) — `NETStandard.Library` версии `1.6.0`.  Хотя ничто не мешает вам использовать `Microsoft.NETCore.App`, как в случае с консольными приложениями, как правило, делать это не рекомендуется.  Если вам нужны интерфейсы API из пакета, который не указан в `NETStandard.Library`, вы всегда можете указать его в дополнение к `NETStandard.Library` в разделе `dependencies` файла `project.json`.

При нацеливании на платформу .NET Standard есть три основных варианта, выбор которых зависит от ваших потребностей.

1. Можно использовать последнюю версию .NET Standard (`netstandard1.6`), если вам нужен доступ к большинству интерфейсов API, а охват максимально возможного количества реализаций не важен.
2. Вы можете использовать более раннюю версию .NET Standard для нацеливания на более ранние реализации .NET за счет отсутствия доступа к некоторым новейшим интерфейсам API.
    
    Например, если требуется гарантированная совместимость с .NET Framework 4.6 и более поздними версиями, следует выбрать `netstandard1.3`:

    ```json
    {
        "dependencies":{
            "NETStandard.Library":"1.6.0"
        },
        "frameworks":{
            "netstandard1.3":{}
        }
    }
    ```
    
    Версии .NET Standard обладают обратной совместимостью. Это означает, что библиотеки `netstandard1.0` выполняются на платформах `netstandard1.1` и более поздних версий.  Однако прямой совместимости нет: более ранние платформы .NET Standard не могут ссылаться на более поздние.  Это значит, что библиотеки `netstandard1.0` не могут ссылаться на библиотеки, предназначенные для `netstandard1.1` или более поздних версий.  Выберите версию Standard, которая предоставляет подходящее сочетание интерфейсов API и поддерживаемых платформ для ваших потребностей.
    
3. Если требуется нацеливание на .NET Framework версии 4.0 или более ранней или использование интерфейса API, доступного в .NET Framework, но не в .NET Standard (например, `System.Drawing`), прочитайте следующие подразделы, чтобы узнать, как осуществляется настройка для разных версий.

## <a name="how-to-target-the-net-framework"></a>Нацеливание на .NET Framework

> [!NOTE]
> В этих инструкциях предполагается, что на компьютере установлена платформа .NET Framework.  Чтобы установить зависимости, обратитесь к разделу [Предварительные требования](#prerequisites).

Имейте в виду, что некоторые используемые здесь версии .NET Framework больше не поддерживаются.  Сведения о неподдерживаемых версиях см. в статье [Вопросы и ответы о политике по срокам поддержки Microsoft .NET Framework](https://support.microsoft.com/gp/framework_faq/en-us).

Чтобы охватить максимальное количество разработчиков и проектов, используйте .NET Framework 4 в качестве базовой целевой платформы. Для нацеливания на .NET Framework сначала необходимо использовать моникер целевой платформы (TFM), соответствующий версии .NET Framework, которая должна поддерживаться.

```
.NET Framework 2.0   --> net20
.NET Framework 3.0   --> net30
.NET Framework 3.5   --> net35
.NET Framework 4.0   --> net40
.NET Framework 4.5   --> net45
.NET Framework 4.5.1 --> net451
.NET Framework 4.5.2 --> net452
.NET Framework 4.6   --> net46
.NET Framework 4.6.1 --> net461
.NET Framework 4.6.2 --> net462
.NET Framework 4.6.3 --> net463
```

Например, вот как создать библиотеку, предназначенную для .NET Framework 4:

```json
{
    "frameworks":{
        "net40":{}
    }
}
```

Вот и все!  Хотя эта библиотека компилируется только для .NET Framework 4, ее можно использовать в более поздних версиях .NET Framework.

## <a name="how-to-target-a-portable-class-library-pcl"></a>Нацеливание на переносимую библиотеку классов (PCL)

> [!NOTE]
> В этих инструкциях предполагается, что на компьютере установлена платформа .NET Framework.  Чтобы установить зависимости, обратитесь к разделу [Предварительные требования](#prerequisites).

Нацеливание на библиотеку PCL немного сложнее, чем на платформу .NET Standard или .NET Framework.  Начинающие могут обратиться к [списку профилей PCL](http://embed.plnkr.co/03ck2dCtnJogBKHJ9EjY/preview), чтобы найти целевой пакет NuGet, соответствующий нужному профилю PCL.

Затем необходимо выполнить указанные ниже действия:

1. В разделе `frameworks` файла `project.json` создайте запись с именем `.NETPortable,Version=v{version},Profile=Profile{profile}`, где `{version}` и `{profile}` — это номера версии и профиля PCL соответственно.
2. В этой новой записи укажите каждую сборку, используемую для данной целевой платформы, в записи `frameworkAssemblies`.  Эти сборки включают `mscorlib`, `System` и `System.Core`.
3. При настройке для различных версий (см. следующий раздел) необходимо явным образом перечислить зависимости для каждой целевой платформы в соответствующих записях.  Вы больше не сможете использовать глобальную запись `dependencies`.

Ниже приведен пример нацеливания на профиль PCL 328. Профиль 328 поддерживает: .NET Standard 1.4, .NET Framework 4, Windows 8, Windows Phone 8.1, Windows Phone Silverlight 8.1 и Silverlight 5.

```json
{
    "frameworks":{
        ".NETPortable,Version=v4.0,Profile=Profile328":{
            "frameworkAssemblies":{
                "mscorlib":"",
                "System":"",
                "System.Core":""
            }
        }
    }
}
```

При сборке проекта, включающего профиль PCL 328 в качестве платформы в файле *project.json*, в папке */bin/debug* должна быть следующая вложенная папка:

```
portable-net40+sl50+netcore45+wpa81+wp8/
```

Эта папка содержит файлы `.dll`, необходимые для выполнения библиотеки.

## <a name="how-to-multitarget"></a>Настройка для различных версий

> [!NOTE]
> В приведенных ниже инструкциях предполагается, что на компьютере установлена платформа .NET Framework.  Сведения о зависимостях, которые необходимо установить, и о том, где их можно скачать, см. в разделе [Предварительные требования](#prerequisites).

Если проект поддерживает как .NET Framework, так и .NET Core, может потребоваться нацеливание на более старые версии .NET Framework. В такой ситуации, если вам нужно применять более новые интерфейсы API и языковые конструкции для новых целевых платформ, используйте директивы `#if` в коде. Кроме того, может потребоваться добавить разные пакеты и зависимости в файл `project.json file` для каждой целевой платформы, чтобы включить различные интерфейсы API, необходимые в каждом случае.

Предположим, имеется библиотека, выполняющая сетевые операции по протоколу HTTP. Для .NET Standard и .NET Framework версии 4.5 или более поздней можно использовать класс `HttpClient` из пространства имен `System.Net.Http`. Однако в более ранних версиях .NET Framework нет класса `HttpClient`, поэтому вместо него можно использовать класс `WebClient` из пространства имен `System.Net`.

Файл `project.json` мог бы выглядеть следующим образом.

```json
{
    "frameworks":{
        "net40":{
            "frameworkAssemblies": {
                "System.Net":"",
                "System.Text.RegularExpressions":""
            }
        },
        "net452":{
            "frameworkAssemblies":{
                "System.Net":"",
                "System.Net.Http":"",
                "System.Text.RegularExpressions":"",
                "System.Threading.Tasks":""
            }
        },
        "netstandard1.6":{
            "dependencies": {
                "NETStandard.Library":"1.6.0",
            }
        }
    }
}
```

Обратите внимание на то, что на сборки .NET Framework необходимо ссылаться явным образом для целевых платформ `net40` и `net452`, а ссылки на пакеты NuGet также указываются явным образом для целевой платформы `netstandard1.6`.  Это обязательное требование в сценариях настройки для различных систем.

Далее операторы `using` в файле исходного кода можно изменить следующим образом:

```csharp
#if NET40
// This only compiles for the .NET Framework 4 targets
using System.Net;
#else
// This compiles for all other targets
using System.Net.Http;
using System.Threading.Tasks;
#endif
```

Система сборки распознает следующие символы препроцессора, используемые в директивах `#if`:

```
.NET Framework 2.0   --> NET20
.NET Framework 3.5   --> NET35
.NET Framework 4.0   --> NET40
.NET Framework 4.5   --> NET45
.NET Framework 4.5.1 --> NET451
.NET Framework 4.5.2 --> NET452
.NET Framework 4.6   --> NET46
.NET Framework 4.6.1 --> NET461
.NET Framework 4.6.2 --> NET462
.NET Standard 1.0    --> NETSTANDARD1_0
.NET Standard 1.1    --> NETSTANDARD1_1
.NET Standard 1.2    --> NETSTANDARD1_2
.NET Standard 1.3    --> NETSTANDARD1_3
.NET Standard 1.4    --> NETSTANDARD1_4
.NET Standard 1.5    --> NETSTANDARD1_5
.NET Standard 1.6    --> NETSTANDARD1_6
```

В середине исходного кода можно применять директивы `#if` для условного использования библиотек. Пример:

```csharp
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
            string url = "http://www.dotnetfoundation.org/";
          
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
            string url = "http://www.dotnetfoundation.org/";
            
            // HttpClient is thread-safe, so no need to explicitly lock here
            var result = await _client.GetStringAsync(url);
            
            int dotNetCount = Regex.Matches(result, ".NET").Count;
            
            return $"dotnetfoundation.orgmentions .NET {dotNetCount} times in its HTML!";
        }
#endif
    }
```

При сборке проекта, включающего профиль `net40`, `net45` и `netstandard1.6` в качестве платформ в файле *project.json*, в папке */bin/debug* должны быть следующие вложенные папки:

```
net40/
net45/
netstandard1.6/
```

### <a name="but-what-about-multitargeting-with-portable-class-libraries"></a>Настройка для различных версий в случае с переносимыми библиотеками классов

Для кроссплатформенной компиляции с PCL в качестве целевой платформы необходимо добавить определение сборки в файл `project.json` в разделе `buildOptions` целевой библиотеки PCL.  Затем можно применять директивы `#if` в исходном коде, которые используют определение сборки в качестве символа препроцессора.

Например, для нацеливания на [профиль PCL 328](http://embed.plnkr.co/03ck2dCtnJogBKHJ9EjY/preview) (.NET Framework 4, Windows 8, Windows Phone Silverlight 8, Windows Phone 8.1, Silverlight 5) при кроссплатформенной компиляции можно сослаться на него как PORTABLE328.  Просто добавьте его в файл `project.json` в виде атрибута `buildOptions`:

```json
{
    "frameworks":{
        "netstandard1.6":{
           "dependencies":{
                "NETStandard.Library":"1.6.0",
            }
        },
        ".NETPortable,Version=v4.0,Profile=Profile328":{
            "buildOptions": {
                "define": [ "PORTABLE328" ]
            },
            "frameworkAssemblies":{
                "mscorlib":"",
                "System":"",
                "System.Core":"",
                "System.Net"
            }
        }
    }
}

```

Теперь можно выполнить условную компиляцию для целевой платформы:

```csharp
#if !PORTABLE328
using System.Net.Http;
using System.Threading.Tasks;
// Potentially other namespaces which aren't compatible with Profile 328
#endif
```

Так как `PORTABLE328` теперь распознается компилятором, библиотека профиля PCL 328, созданная компилятором, не будет включать `System.Net.Http` или `System.Threading.Tasks`.

При сборке проекта, включающего профиль PCL 328 и `netstandard1.6` в качестве платформ в файле *project.json*, в папке */bin/debug* будут следующие вложенные папки:

```
portable-net40+sl50+netcore45+wpa81+wp8/
netstandard1.6/
```

## <a name="how-to-use-native-dependencies"></a>Использование зависимостей в машинном коде

Вам может потребоваться создать библиотеку, которая зависит от файла `.dll` в машинном коде.  При создании такой библиотеки есть два варианта:

1. сошлитесь на библиотеку `.dll` в машинном коде непосредственно в файле `project.json`;
2. упакуйте библиотеку `.dll` в собственный пакет NuGet а затем установите зависимость от него.

В первом случае в файл `project.json` необходимо включить следующее:

1. задать для `allowUnsafe` значение `true` в разделе `buildOptions`;
2. указать [идентификатор среды выполнения (RID)](../rid-catalog.md) в разделе `runtimes`;
3. указать путь на файлы `.dll` в машинном коде, ссылки на которые задаются.

Вот пример файла `project.json` для файла `.dll` в машинном коде в корневом каталоге проекта, выполняющегося в Windows:

```json
{
    "buildOptions":{
        "allowUnsafe":true
    },
    "runtimes":{
        "win10-x64":{}
    },
    "packOptions":{
        "files":{
            "mappings":{
                "runtimes/win10-x64/native":{
                    "includeFiles":[ "native-lib.dll"]
                }
            }            
        }
    }
}
```

Если вы распространяете библиотеку в виде пакета, файл `.dll` рекомендуется размещать на корневом уровне проекта.

Во втором случае вам необходимо выполнить сборку пакета NuGet на основе файлов `.dll`, разместите его в канале NuGet или MyGet, а затем напрямую установите зависимость от него.  Вам по-прежнему необходимо задать для `allowUnsafe` значение `true` в разделе `buildOptions` файла `project.json`.  Ниже приведен пример (предполагается, что `MyNativeLib` — это пакет Nuget версии `1.2.0`).

```json
{
    "buildOptions":{
        "allowUnsafe":true
    },
    "dependencies":{
        "MyNativeLib":"1.2.0"
    }
}
```

Пример упаковки кроссплатформенных двоичных файлов в машинном коде см. на странице [Пакет Libuv для ASP.NET](https://github.com/aspnet/libuv-package) и в [соответствующей справке в KestrelHttpServer](https://github.com/aspnet/KestrelHttpServer/blob/1.0.0/src/Microsoft.AspNetCore.Server.Kestrel/project.json#L19).

## <a name="how-to-test-libraries-on-net-core"></a>Тестирование библиотек в .NET Core

Необходимо иметь возможность тестирования проектов на различных платформах.  Проще всего применять средство тестирования [xUnit](http://xunit.github.io/), которое также используется проектами .NET Core.  Настройка тестовых проектов для решения зависит от [его структуры](#structuring-a-solution).  В приведенном ниже примере предполагается, что все исходные проекты находятся в папке `/src` верхнего уровня, а все тестовые проекты — в папке `/test` верхнего уровня.

1. Файл `global.json` должен находиться на уровне решения, на котором известно, где находятся тестовые проекты:
    
    ```json
    {
        "projects":[ "src", "test"]
    }
    ```
    
    Структура папок решения должна выглядеть следующим образом.
    
    ```
    /SolutionWithSrcAndTest
    |__global.json
    |__/src
    |__/test
    ```
    
2. Создайте тестовый проект, создав папку проекта в папке `/test` и файл `project.json` в новой папке проекта.  Вы можете создать файл `project.json`, выполнив команду `dotnet new`, и изменить файл `project.json` впоследствии.  Файл должен содержать следующее:

   * `netcoreapp1.0`в качестве единственной записи в разделе `frameworks`;
   * ссылка на `Microsoft.NETCore.App` версии `1.0.0`;
   * ссылка на xUnit версии `2.2.0-beta2-build3300`;
   * ссылка на `dotnet-test-xunit`версию `2.2.0-preview2-build1029`;
   * ссылка проекта на тестируемую библиотеку;
   * запись `"testRunner":"xunit"`.
   
   Вот пример (тестируется библиотека `LibraryUnderTest` версии `1.0.0`):
   
   ```json
   {
        "testRunner":"xunit",
        "dependencies":{
            "LibraryUnderTest":{
                "version":"1.0.0",
                "target":"project"
            },
            "Microsoft.NETCore.App":{
                "version":"1.0.0",
                "type":"platform"
            },
            "xunit":"2.2.0-beta2-build3300",
            "dotnet-test-xunit":"2.2.0-preview2-build1029",
        },
        "frameworks":{
            "netcoreapp1.0":{}
        }
   }
   ```
3. Восстановите пакеты, выполнив команду `dotnet restore`.  Если вы еще не восстановили пакеты, это следует сделать на уровне решения.

4. Перейдите к тестовому проекту и выполните тесты с помощью команды `dotnet test`:

    ```
    $ cd path-to-your-test-project
    $ dotnet test
    ```

Вот и все!  Теперь вы можете протестировать библиотеку для всех платформ с помощью средств командной строки.  Теперь, когда все настроено, протестировать библиотеку очень легко:

1. Внесите изменения в библиотеку.
2. Выполните тесты в тестовом каталоге из командной строки с помощью команды `dotnet test`.

При вызове команды `dotnet test` будет автоматически выполнена повторная сборка кода.

Не забывайте выполнять команду `dotnet restore` из командной строки каждый раз при добавлении новой зависимости.

## <a name="how-to-use-multiple-projects"></a>Использование нескольких проектов

В случае с более крупными библиотеками, как правило, требуется реализовывать функциональность в разных проектах.

Представим, что необходимо создать библиотеку, которую можно использовать в идиоматичном коде на языках C# и F#.  Это означает, что библиотека будет использоваться способами, естественными для языков C# и F#.  Например, в C# можно использовать библиотеку следующим образом:

```csharp
var convertResult = await AwesomeLibrary.ConvertAsync(data);
var result = AwesomeLibrary.Process(convertResult);
```  

В F# это может выглядеть так.

```fsharp
let result =
    data
    |> AwesomeLibrary.convertAsync 
    |> Async.RunSynchronously 
    |> AwesomeLibrary.process
```

Подобные сценарии использования предполагают, что интерфейсы API, к которым осуществляется доступ, должны иметь разную структуру для C# и F#.  Стандартным подходом к решению этой задачи является факторинг всей логики библиотеки в базовом проекте и определение в проектах C# и F# уровней API, которые вызывают этот базовый проект.  Далее в этом разделе будут использоваться следующие имена:

* **AwesomeLibrary.Core** — базовый проект, содержащий всю логику библиотеки;
* **AwesomeLibrary.CSharp** — проект с открытыми интерфейсами API, предназначенными для использования в коде на языке C;#
* **AwesomeLibrary.FSharp** — проект с открытыми интерфейсами API, предназначенными для использования в коде на языке F.#

### <a name="project-to-project-referencing"></a>Ссылки проектов на проекты

Для ссылки на проект лучше всего использовать указанный ниже способ:

1. Убедитесь в том, что проект, на который необходимо сослаться, имеет подходящее имя для содержащей его папки на диске.  Это имя будет применяться для ссылки на проект.
2. Сошлитесь на имя из (1) в файле `project.json` исходного проекта, указав `"target":"project"`.

Файлы `project.json` проектов **AwesomeLibrary.CSharp** и **AwesomeLibrary.FSharp** теперь должны ссылаться на **AwesomeLibrary.Core** в качестве целевого проекта `project`.  Если настройка для различных версий не производится, можно использовать глобальную запись `dependencies`:

```json
{
    "dependencies":{
        "AwesomeLibrary.Core":{
            "target":"project"
        }
    }
}
```

Если настройка для различных версий производится, использование глобальной записи `dependencies` может быть невозможным. В этом случае необходимо сослаться на **AwesomeLibrary.Core** в целевой записи `dependencies`.  Например, при нацеливании на `netstandard1.6` это можно сделать следующим образом:

```json
{
    "frameworks":{
        "netstandard1.6":{
            "dependencies":{
                "AwesomeLibrary.Core":{
                    "target":"project"
                }
            }
        }
    }
}
```

### <a name="structuring-a-solution"></a>Структурирование решения

Еще один важный аспект решений с несколькими проектами — правильное формирование общей структуры. Чтобы структурировать библиотеку из нескольких проектов, необходимо использовать папки `/src` и `/test` верхнего уровня:

```
/AwesomeLibrary
|__global.json
|__/src
   |__/AwesomeLibrary.Core
      |__Source Files
      |__project.json
   |__/AwesomeLibrary.CSharp
      |__Source Files
      |__project.json
   |__/AwesomeLibrary.FSharp
      |__Source Files
      |__project.json
|__/test
   |__/AwesomeLibrary.Core.Tests
      |__Test Files
      |__project.json
   |__/AwesomeLibrary.CSharp.Tests
      |__Test Files
      |__project.json
   |__/AwesomeLibrary.FSharp.Tests
      |__Test Files
      |__project.json
```

Файл `global.json` для этого решения будет выглядеть следующим образом.

```json
{
    "projects":["src", "test"]
}
```

При таком подходе применяется структура, аналогичная той, что создается при выполнении команды `dotnet new`: все проекты помещаются в каталог `/src`, а все тесты — в каталог `/test`.

Вот как можно восстановить пакеты, выполнить сборку и протестировать весь проект:

```
$ dotnet restore
$ cd src/AwesomeLibrary.FSharp
$ dotnet build
$ cd ../AwesomeLibrary.CSharp
$ dotnet build
$ cd ../../test/AwesomeLibrary.Core.Tests
$ dotnet test
$ cd ../AwesomeLibrary.CSharp.Tests
$ dotnet test
$ cd ../AwesomeLibrary.FSharp.Tests
$ dotnet test
```

Вот и все!

