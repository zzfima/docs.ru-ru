---
title: Новые возможности .NET Core 3.0
description: Дополнительные сведения о новых возможностях .NET Core 3.0.
dev_langs:
- csharp
- vb
author: thraka
ms.author: adegeo
ms.date: 12/31/2018
ms.openlocfilehash: 086be4649f4e7e27ff98df6f26d08856683865c8
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2019
ms.locfileid: "59611787"
---
# <a name="whats-new-in-net-core-30-preview-2"></a>Новые возможности .NET Core 3.0 (предварительная версия 2)

В этой статье описываются новые возможности в .NET Core 3.0 (предварительная версия 2). Одно из основных усовершенствований — это поддержка классических приложений Windows (только Windows). Используя пакет SDK для .NET Core 3.0 под названием Windows Desktop, вы можете перенести приложения Windows Forms и Windows Presentation Foundation (WPF). Следует уточнить, что компонент Windows Desktop поддерживается и включен только в Windows. Дополнительные сведения см. в разделе [Классические приложения Windows](#windows-desktop), приведенном ниже.

В .NET Core 3.0 добавлена поддержка C# 8.0.

[Скачайте и начните работу с .NET Core 3.0 (предварительная версия 2)](https://aka.ms/netcore3download) прямо сейчас в Windows, Mac и Linux. Полное описание выпуска .NET Core 3.0 (предварительная версия 2) см. [здесь](https://aka.ms/netcore3releasenotes).

Ддля получения дополнительных сведений о новых возможностях в каждой версии см. следующие объявления:

- [Объявление о .NET Core 3.0, предварительная версия 1](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-1-and-open-sourcing-windows-desktop-frameworks/)
- [Объявление о .NET Core 3.0, предварительная версия 2](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-2/)

## <a name="c-8"></a>C# 8

.NET Core 3.0 поддерживает C# 8, а начиная с .NET Core 3.0, предварительная версия 2, поддерживает эти новые функции. Дополнительные сведения о функциях C# 8.0 см. в следующих записях блога:

- [Расширенные возможности шаблонов в C# 8.0](https://devblogs.microsoft.com/dotnet/do-more-with-patterns-in-c-8-0/)
- [C# 8.0 для ускорения работы](https://devblogs.microsoft.com/dotnet/take-c-8-0-for-a-spin/)
- [Сборка на C# 8.0](https://devblogs.microsoft.com/dotnet/building-c-8-0/)

### <a name="ranges-and-indices"></a>Диапазоны и индексы

Новый тип `Index` можно использовать для индексирования. Вы можете создать с помощью `int` индекс, который отсчитывается с начала, а с помощью оператора `^` префикса (C#) индекс, который отсчитывается с конца:

```csharp
Index i1 = 3;  // number 3 from beginning
Index i2 = ^4; // number 4 from end
int[] a = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
Console.WriteLine($"{a[i1]}, {a[i2]}"); // "3, 6"
```

Кроме того, есть тип `Range`, который состоит из двух значений `Index` (одно для начала и одно для конца) и который можно написать с помощью выражения диапазона `x..y` (C#). Затем можно индексировать с помощью `Range` для создания среза:

```csharp
var slice = a[i1..i2]; // { 3, 4, 5 }
```

### <a name="async-streams"></a>Асинхронные потоки

Тип `IAsyncEnumerable<T>` — это новая асинхронная версия `IEnumerable<T>`. Язык позволяет выполнить действие `await foreach` с этими объектами `IAsyncEnumerable<T>`, чтобы использовать их элементы, и действие `yield return` по отношению к ним, чтобы создать элементы.

В приведенном ниже примере демонстрируется создание и применение асинхронных потоков. Инструкция `foreach` является асинхронной и использует `yield return`, чтобы создать асинхронные потоки для вызывающих объектов. Этот шаблон (с использованием `yield return`) является рекомендуемой моделью для создания асинхронных потоков.

```csharp
async IAsyncEnumerable<int> GetBigResultsAsync()
{
    await foreach (var result in GetResultsAsync())
    {
        if (result > 20) yield return result;
    }
}
```

Помимо возможности `await foreach` вы также можете создать асинхронные итераторы, например, итератор, который возвращает `IAsyncEnumerable/IAsyncEnumerator`, для которого можно применить `await` и `yield`. Для объектов, которые необходимо удалить, можно использовать `IAsyncDisposable`, который реализовывают различные типы BCL, такие как `Stream` и `Timer`.

> [!NOTE]
> Вам потребуется .NET Core 3.0 (предварительная версия 2) для использования асинхронных потоков, если вы хотите выполнять разработку с помощью Visual Studio 2019 или последней предварительной версии [расширения C# для Visual Studio Code](https://github.com/OmniSharp/omnisharp-vscode/releases/tag/v1.18.0-beta5). Если вы используете .NET Core 3.0, предварительная версия 2, из командной строки, все будет работать правильно.

### <a name="using-declarations"></a>Использование объявлений

*Объявления using* — это новый способ обеспечить правильную ликвидацию объекта. *Объявление using* поддерживает активность объекта, пока он остается в области. Когда объект выходит за пределы области, он автоматически удаляется. Это позволяет сократить количество вложенных *инструкций using* и сделать код чище.

```csharp
static void Main(string[] args)
{
    using var options = Parse(args);
    if (options["verbose"]) { WriteLine("Logging..."); }

} // options disposed here
```

### <a name="switch-expressions"></a>Выражения switch

*Выражения switch* — это более аккуратный способ передать *оператор switch*, но, так как это выражение, оно возвращает значение. *Выражения switch* также полностью интегрированы с сопоставлением шаблонов и используют шаблон пустой переменной `_`, чтобы представить значение `default`.

Синтаксис *выражения switch* показан в следующем примере:

```csharp
static string Display(object o) => o switch
{
    Point { X: 0, Y: 0 }         => "origin",
    Point { X: var x, Y: var y } => $"({x}, {y})",
    _                            => "unknown"
};
```

В этом примере важны два шаблона. `o` сначала сопоставляется с *типом шаблона* `Point`, а затем с *шаблоном свойств* внутри *{фигурных скобок}*. `_` описывает `discard pattern`, который является аналогом `default` для *операторов switch*.

Шаблоны позволяют писать декларативный код, который выражает ваши намерения, а не процедурный код, реализующий для них тесты. Компилятор отвечает за реализацию этого скучного процедурного кода и всегда делает это правильно.

По-прежнему будут происходить ситуации, к которым *операторы switch* подходят лучше, чем *выражения switch*, и шаблоны могут использоваться в обоих стилях синтаксиса.

Дополнительные сведения см. в разделе [Расширенные возможности шаблонов в C# 8.0](https://devblogs.microsoft.com/dotnet/do-more-with-patterns-in-c-8-0/).

## <a name="ieee-floating-point-improvements"></a>Усовершенствования чисел с плавающей запятой по IEEE

API плавающей запятой сейчас обновляются, чтобы соответствовать [редакции IEEE 754-2008](https://en.wikipedia.org/wiki/IEEE_754-2008_revision). Цель этих изменений — предоставлять все обязательные операции и гарантировать, что их поведение будет соответствовать спецификации IEEE.

Исправления синтаксического анализа и форматирования:

* Правильный анализ и округление входных данных любой длины.
* Правильный анализ и форматирование отрицательного нуля.
* Правильный анализ знака бесконечности, а не чисел с помощью проверки без учета регистра и допущения необязательного `+` в начале, где это применимо.

Новые математические API-интерфейсы:

* `BitIncrement/BitDecrement`\
Соответствует операциям IEEE `nextUp` и `nextDown`. Они возвращают наименьшее число с плавающей запятой, которое может быть больше или меньше входных данных (соответственно). Например, `Math.BitIncrement(0.0)` вернет `double.Epsilon`.

* `MaxMagnitude/MinMagnitude`\
Соответствуют операциям IEEE `maxNumMag` и `minNumMag`. Они возвращают значение, которое будет больше или меньше из двух величин (соответственно). Например, `Math.MaxMagnitude(2.0, -3.0)` вернет `-3.0`.

* `ILogB`\
Соответствует операции IEEE `logB`, которая возвращает целочисленное значение. Она возвращает целочисленный логарифм по основанию 2 входного параметра. Это фактически то же, что `floor(log2(x))`, но с минимальными погрешностями округления.

* `ScaleB`\
Соответствует операции IEEE `scaleB`, которая принимает целочисленное значение. Возвращает `x * pow(2, n)`, но выполняется с минимальными погрешностями округления.

* `Log2`\
Соответствует операции IEEE `log2`. Возвращает логарифм по основанию 2. Сводит к минимуму погрешность округления.

* `FusedMultiplyAdd`\
Соответствует операции IEEE `fma`. Выполняет умножение и сложение. То есть он выполняет `(x * y) + z` как одну операцию, тем самым сводя к минимуму погрешность округления. Пример — `FusedMultiplyAdd(1e308, 2.0, -1e308)`, возвращающий `1e308`. Стандартный `(1e308 * 2.0) - 1e308` возвращает `double.PositiveInfinity`.

* `CopySign`\
Соответствует операции IEEE `copySign`. Возвращает значение `x`, но со знаком `y`.

## <a name="net-platform-dependent-intrinsics"></a>Встроенные объекты, зависимые от платформы .NET

Были добавлены API-интерфейсы, которые разрешают доступ к определенным инструкциям ЦП, ориентированным на производительность, например **SIMD** или наборы **инструкций побитовой обработки**. Эти инструкции помогут значительно улучшить производительность в некоторых сценариях, таких как эффективная параллельная обработка данных. Помимо предоставления API-интерфейсов для программ, библиотеки .NET стали использовать эти инструкции для повышения производительности.

Следующие запросы на вытягивание CoreCLR демонстрируют другие встроенные функции через реализацию или использование:

* [Реализация простых встроенных объектов оборудования SSE2](https://github.com/dotnet/coreclr/pull/15585)
* [Реализация встроенных объектов оборудования SSE](https://github.com/dotnet/coreclr/pull/15538)
* [Встроенные объекты Arm64 Base HW](https://github.com/dotnet/coreclr/pull/16822)
* [Использование TZCNT и LZCNT для Locate{First|Last}Found{Byte|Char}](https://github.com/dotnet/coreclr/pull/21073)

Дополнительные сведения см. в разделе [Встроенные объекты, зависимые от платформы .NET](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md), где описан подход к определению этой аппаратной инфраструктуры, который позволяет Майкрософт, поставщикам микросхем или другим людям и компаниям определять API оборудования или микросхем, которые должны быть предоставлены коду .NET.

## <a name="default-executables"></a>Исполняемые файлы по умолчанию

.NET Core теперь будет создавать [зависящие от платформы исполняемые файлы](../deploying/index.md#framework-dependent-executables-fde) по умолчанию. Это новый аспект для приложений, использующих глобально установленную версию .NET Core. До настоящего времени исполняемые файлы создавались только в [автономных развертываниях](../deploying/index.md#self-contained-deployments-scd).

Во время выполнения команды `dotnet build` или `dotnet publish` создается исполняемый файл, который соответствует среде и платформе используемого пакета SDK. Предполагается, что с этими исполняемыми файлами можно выполнять те же действия, что и с другими исполняемыми файлами в машинном коде, например:

* исполняемый файл можно дважды щелкнуть;
* приложение можно запустить из командной строки напрямую, например `myapp.exe` в Windows и `./myapp` в Linux и macOS.

## <a name="build-copies-dependencies"></a>Сборка копирует зависимости

`dotnet build` теперь копирует зависимости NuGet для вашего приложения из кэша NuGet в выходную папку сборки. Ранее зависимости копировались только в рамках выполнения команды `dotnet publish`.

Для некоторых операций, таких как связывание и публикация страницы Razor, по-прежнему будет требоваться публикация.

## <a name="local-dotnet-tools"></a>Локальные средства dotnet

> [!WARNING]
> Произошло изменение в локальных средствах .NET Core между .NET Core 3.0, предварительная версия 1, и .NET Core 3.0, предварительная версия 2.  Если вы опробовали локальные средства в предварительной версии 1 с помощью команды `dotnet tool restore` или `dotnet tool install`, удалите папку кэша локальных средств, чтобы локальные средства правильно работали в предварительной версии 2. Эта папка находится по адресу:
>
> На Mac, в Linux: `rm -r $HOME/.dotnet/toolResolverCache`
>
> В Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`
>
> Если вы не удалите папку, вы получите ошибку.

Хотя в .NET Core 2.1 была поддержка глобальных средств, в .NET Core 3.0 теперь есть локальные средства. Локальные средства похожи на глобальные средства, но связаны с определенным расположением на диске. Это обеспечивает инструменты для отдельных проектов и репозиториев. Любое средство, установленное локально, недоступно глобально. Средства распространяются в виде пакетов NuGet.

Локальные средства используют имя файла манифеста `dotnet-tools.json` в текущем каталоге. Этот файл манифеста определяет, какие средства доступны в этой папке и далее. Если создать этот файл манифеста в корне репозитория, любой пользователь, клонировавший код, сможет восстановить и использовать средства, необходимые для успешной работы с кодом.

Чтобы создать файл манифеста `dotnet-tools.json`, используйте:

```console
dotnet new tool-manifest
```

Добавьте новое средство в локальный манифест с помощью:

```console
dotnet tool install <packageId>
```

Можно также перечислить средства в локальном манифесте с помощью:

```console
dotnet tool list
```

Чтобы узнать, какие средства установлены глобально, используйте:

```console
dotnet tool list -g
```

Если файл манифеста локальных средств доступен, но средства, определенные в манифесте, не установлены, выполните приведенную ниже команду, чтобы автоматически скачать и установить эти средства:

```console
dotnet tool restore
```

Запустите локальное средство с помощью следующей команды:

```console
dotnet tool run <tool-command-name>
```

При запуске локального средства dotnet выполняет поиск манифеста вверх по текущей структуре каталогов. Когда файл манифеста средства обнаруживается, выполняется поиск запрашиваемого средства. Если средство обнаруживается в манифесте, а не в кэше, пользователь получает сообщение об ошибке и должен запустить `dotnet tool restore`.

Чтобы удалить средство из локального файла манифеста средства, выполните следующую команду:

```console
dotnet tool uninstall <packageId>
```

Файл манифеста средства разработан так, чтобы его можно было редактировать вручную, например, когда необходимо обновить требуемую версию для работы с репозиторием. Ниже приведен пример файла `dotnet-tools.json`:

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {
    "dotnetsay": {
      "version": "2.1.4",
      "commands": [
        "dotnetsay"
      ]
    },
    "t-rex": {
      "version": "1.0.103",
      "commands": [
        "t-rex"
      ]
    }
  }
}
```

Для глобальных и локальных средств требуется совместимая версия среды выполнения. Сейчас на сайте NuGet.org многие средства предназначены для среды выполнения .NET Core 2.1. Чтобы установить их глобально или локально, по-прежнему необходимо установить [среду выполнения NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1).

## <a name="windows-desktop"></a>Классические приложения Windows

Начиная с .NET Core 3.0 (предварительная версия 1), можно создавать классические приложения Windows с помощью WPF и Windows Forms. Эти платформы также поддерживают использование современных элементов управления и стилей Fluent из библиотеки XAML пользовательского интерфейса Windows (WinUI) через [острова XAML](/windows/uwp/xaml-platform/xaml-host-controls).

Компонент Windows Desktop является частью пакета SDK .NET Core 3.0 для Windows.

Вы можете создать приложение WPF или Windows Forms с помощью следующих команд `dotnet`:

```console
dotnet new wpf
dotnet new winforms
```

Visual Studio 2019 добавляет шаблоны **Новый проект** для .NET Core 3.0 Windows Forms и WPF. Конструкторы по-прежнему не поддерживаются. Вы можете открывать, запускать и отлаживать эти проекты в Visual Studio 2019.

Visual Studio 2017 15.9 добавляет возможность [включать предварительные версии .NET Core](https://devblogs.microsoft.com/dotnet/net-core-tooling-update-for-visual-studio-2017-version-15-9/), но необходимо включить эту функцию, и это не поддерживаемый сценарий.

Новые проекты идентичны имеющимся проектам .NET Core с некоторыми добавлениями. Ниже приведено сравнение базового консольного проекта .NET Core и базового проекта Windows Forms и WPF.

Консольный проект .NET Core использует пакет SDK `Microsoft.NET.Sdk` и объявляет зависимость в .NET Core 3.0 с помощью требуемой версии .NET Framework `netcoreapp3.0`. Чтобы создать приложение Windows Desktop, используйте пакет SDK `Microsoft.NET.Sdk.WindowsDesktop` и выберите, какую платформу пользовательского интерфейса использовать:

```diff
-<Project Sdk="Microsoft.NET.Sdk">
+<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
+   <UseWPF>true</UseWPF>
  </PropertyGroup>
</Project>
```

Чтобы выбрать Windows Forms вместо WPF, установите `UseWindowsForms` вместо `UseWPF`:

```diff
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
-   <UseWPF>true</UseWPF>
+   <UseWindowsForms>true</UseWindowsForms>
  </PropertyGroup>
</Project>
```

Для `UseWPF` и `UseWindowsForms` можно задать значение `true`, если приложение использует обе платформы, например, если в диалоговом окне Windows Forms размещен элемент управления WPF.

Оставьте свой отзыв в репозитории [dotnet/winforms](https://github.com/dotnet/winforms/issues), [dotnet/wpf](https://github.com/dotnet/wpf/issues) и [dotnet/core](https://github.com/dotnet/core/issues).

## <a name="msix-deployment-for-windows-desktop"></a>Развертывание MSIX для Windows Desktop

[MSIX](https://docs.microsoft.com/windows/msix/) — это новый формат пакета приложения Windows. Его можно использовать для развертывания классических приложений .NET Core 3.0 для Windows 10.

[Проект упаковки приложений Windows](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net), доступный в Visual Studio 2019, позволяет создавать пакеты MSIX с [автономными](../deploying/index.md#self-contained-deployments-scd) приложениями .NET Core.

> [!NOTE]
> Файл проекта .NET Core должен указывать поддерживаемые среды выполнения в свойстве `<RuntimeIdentifiers>`:
>
> ```xml
> <RuntimeIdentifiers>win-x86;win-x64</RuntimeIdentifiers>
> ```

## <a name="fast-built-in-json-support"></a>Быстрая встроенная поддержка JSON

В экосистеме .NET использовалась [**Json.NET**](https://www.newtonsoft.com/json) и другие популярные библиотеки JSON, которые по-прежнему остаются хорошими вариантами. **Json.NET** использует в качестве базового типа данных строки .NET, которые обладают внутренней структурой UTF-16.

Новая встроенная поддержка JSON отличается высокой производительностью и малым распределением и основана на `Span<byte>`. Были добавлены три новых основных типа, связанных с JSON, в пространство имен `System.Text.Json` в .NET Core 3.0.

### <a name="utf8jsonreader"></a>Utf8JsonReader

`System.Text.Json.Utf8JsonReader` — это однопроходный модуль чтения текста JSON в кодировке UTF-8 из `ReadOnlySpan<byte>` с высокой производительностью и низким уровнем распределения. `Utf8JsonReader` — это основной тип низкого уровня, с помощью которого можно создавать пользовательские средства синтаксического анализа и десериализаторы. Чтение полезных данных JSON с помощью нового `Utf8JsonReader` осуществляется в два раза быстрее, чем при использовании модуля чтения от **JSON.NET**. Распределение не осуществляется, пока не понадобится актуализировать токены JSON в виде строк (UTF-16).

Этот новый интерфейс API будет включать следующие компоненты:

* В предварительной версии 1: модуль чтения JSON (последовательный доступ).
* Ожидается в следующем выпуске: модуль записи JSON, DOM (произвольный доступ), сериализатор poco, десериализатор poco.

Ниже приведен цикл базового модуля чтения для `Utf8JsonReader`, который можно использовать в качестве отправной точки:

```csharp
using System.Text.Json;

public static void Utf8JsonReaderLoop(ReadOnlySpan<byte> dataUtf8)
{
    var json = new Utf8JsonReader(dataUtf8, isFinalBlock: true, state: default);

    while (json.Read())
    {
        JsonTokenType tokenType = json.TokenType;
        ReadOnlySpan<byte> valueSpan = json.ValueSpan;
        switch (tokenType)
        {
            case JsonTokenType.StartObject:
            case JsonTokenType.EndObject:
                break;
            case JsonTokenType.StartArray:
            case JsonTokenType.EndArray:
                break;
            case JsonTokenType.PropertyName:
                break;
            case JsonTokenType.String:
                string valueString = json.GetStringValue();
                break;
            case JsonTokenType.Number:
                if (!json.TryGetInt32Value(out int valueInteger))
                {
                    throw new FormatException();
                }
                break;
            case JsonTokenType.True:
            case JsonTokenType.False:
                bool valueBool = json.GetBooleanValue();
                break;
            case JsonTokenType.Null:
                break;
            default:
                throw new ArgumentException();
        }
    }

    dataUtf8 = dataUtf8.Slice((int)json.BytesConsumed);
    JsonReaderState state = json.CurrentState;
}
```

### <a name="utf8jsonwriter"></a>Utf8JsonWriter

`System.Text.Json.Utf8JsonWriter` предоставляет высокопроизводительный, не использующий кэширование и однонаправленный способ записи текста JSON в кодировке UTF-8 из распространенных типов .NET, например `String`, `Int32` и `DateTime`. Как и средство чтения, средство записи — это основной тип низкого уровня, с помощью которого можно создавать пользовательские сериализаторы. Запись полезных данных JSON с помощью нового `Utf8JsonWriter` выполняется на 30–80 % быстрее, чем с помощью средства записи из **Json.NET**, и не требует выделения.

Ниже приведен пример использования `Utf8JsonWriter`, который может использоваться в качестве отправной точки:

```csharp
static int WriteJson(IBufferWriter<byte> output, long[] extraData)
{
    var json = new Utf8JsonWriter(output, state: default);

    json.WriteStartObject();

    json.WriteNumber("age", 15, escape: false);
    json.WriteString("date", DateTime.Now);
    json.WriteString("first", "John");
    json.WriteString("last", "Smith");

    json.WriteStartArray("phoneNumbers", escape: false);
    json.WriteStringValue("425-000-1212", escape: false);
    json.WriteStringValue("425-000-1213");
    json.WriteEndArray();

    json.WriteStartObject("address");
    json.WriteString("street", "1 Microsoft Way");
    json.WriteString("city", "Redmond");
    json.WriteNumber("zip", 98052);
    json.WriteEndObject();

    json.WriteStartArray("ExtraArray");
    for (var i = 0; i < extraData.Length; i++)
    {
        json.WriteNumberValue(extraData[i]);
    }
    json.WriteEndArray();

    json.WriteEndObject();

    json.Flush(isFinalBlock: true);

    return (int)json.BytesWritten;
}
```

`Utf8JsonWriter` принимает `IBufferWriter<byte>` в качестве выходного расположения для синхронной записи данных json, и вы, как вызывающий объект, должны предоставить конкретную реализацию. В настоящее время платформа не включает реализацию этого интерфейса. Пример `IBufferWriter<byte>` см. в <https://gist.github.com/ahsonkhan/c76a1cc4dc7107537c3fdc0079a68b35>.

### <a name="jsondocument"></a>JsonDocument

`System.Text.Json.JsonDocument` создается на основе `Utf8JsonReader`. `JsonDocument` предоставляет возможность анализировать данные JSON и создавать модель DOM только для чтения, которая может запрашиваться для поддержки случайного доступа и перечисления. Доступ к элементам JSON, составляющим данные, может осуществляться через тип `JsonElement`, который предоставляется `JsonDocument` как свойство с именем `RootElement`. `JsonElement` содержит перечислители массива и объекта JSON вместе с API-интерфейсами для преобразования текста JSON в стандартные типы .NET. Синтаксический анализ типичных полезных данных JSON и доступ ко всем членам с помощью `JsonDocument` выполняется в 2–3 раза быстрее, чем **Json.NET**, с небольшим количеством распределений данных приемлемого размера (т. е. < 1 МБ).

Ниже приведен пример использования `JsonDocument` и `JsonElement`, который может использоваться в качестве отправной точки:

```csharp
static double ParseJson()
{
    const string json = " [ { \"name\": \"John\" }, [ \"425-000-1212\", 15 ], { \"grades\": [ 90, 80, 100, 75 ] } ]";

    double average = -1;

    using (JsonDocument doc = JsonDocument.Parse(json))
    {
        JsonElement root = doc.RootElement;
        JsonElement info = root[1];

        string phoneNumber = info[0].GetString();
        int age = info[1].GetInt32();

        JsonElement grades = root[2].GetProperty("grades");

        double sum = 0;
        foreach (JsonElement grade in grades.EnumerateArray())
        {
            sum += grade.GetInt32();
        }

        int numberOfCourses = grades.GetArrayLength();
        average = sum / numberOfCourses;
    }

    return average;
}
```

## <a name="assembly-unloadability"></a>Возможность выгрузки сборки

Выгрузка сборки — это новая возможность `AssemblyLoadContext`. Эта новая функция довольно прозрачна с точки зрения API и предоставляется с помощью всего нескольких новых API. Она позволяет выгружать контекст загрузчика, освобождая всю память для экземпляров типов, статических полей, а также для самой сборки. Приложение должно всегда иметь возможность загрузки и выгрузки сборок с помощью этого механизма без утечки памяти.

Эта новая возможность может использоваться в следующих сценариях:

* Подключаемый модуль, где требуется загрузка и выгрузка динамического подключаемого модуля.
* Динамическая компиляция, запуск и затем очистка кода. Это удобно для веб-сайтов, модулей написания скриптов и т. д.
* Загрузка сборок для анализа (например, ReflectionOnlyLoad), хотя [MetadataLoadContext](#type-metadataloadcontext) (выпущенный в предварительной версии 1) подойдет лучше во многих случаях.

Дополнительные сведения см. в статье [Использование выгрузки](https://github.com/dotnet/coreclr/pull/22221).

Выгрузка сборки требует большой осторожности, так как вы должны понимать и контролировать все ссылки на управляемые объекты вне контекста загрузчика. При запросе выгрузки контекста загрузчика необходимо отменить все внешние ссылки, чтобы контекст загрузчика соответствовал только самому себе.

Возможность выгрузки сборки предоставляется доменами приложения .NET Framework, которые не поддерживаются .NET Core. Домены приложений имеют свои преимущества и ограничения по сравнению с этой новой моделью. Новая модель загрузчика отличается большей гибкостью и производительностью по сравнению с доменами приложений.

## <a name="windows-native-interop"></a>Собственное взаимодействие Windows

Windows предоставляет собственный API с широкими возможностями в виде API C, COM и WinRT. Начиная с .NET Core 1.0 поддерживается **P/Invoke**. Теперь с .NET Core 3.0 поддерживается возможность **совместного создания API COM** и **активации API WinRT**.

Пример использования COM вы найдете в [исходном коде демонстрации Excel](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).

## <a name="type-sequencereader"></a>Тип: SequenceReader

В .NET Core 3.0 добавлен `System.Buffers.SequenceReader`, который можно использовать в качестве модуля чтения для `ReadOnlySequence<T>`. Это обеспечивает простой и высокопроизводительный анализ данных `System.IO.Pipelines` с низким уровнем распределения, которые могут пересекать несколько буферов резервного копирования.

В следующем примере входные данные `Sequence` разбиваются на допустимые строки `CR/LF` с разделителями:

```csharp
private static ReadOnlySpan<byte> CRLF => new byte[] { (byte)'\r', (byte)'\n' };

public static void ReadLines(ReadOnlySequence<byte> sequence)
{
    SequenceReader<byte> reader = new SequenceReader<byte>(sequence);

    while (!reader.End)
    {
        if (!reader.TryReadToAny(out ReadOnlySpan<byte> line, CRLF, advancePastDelimiter:false))
        {
            // Couldn't find another delimiter
            // ...
        }

        if (!reader.IsNext(CRLF, advancePast: true))
        {
            // Not a good CR/LF pair
            // ...
        }

        // line is valid, process
        ProcessLine(line);
    }
}
```

## <a name="type-metadataloadcontext"></a>Тип: MetadataLoadContext

Добавлен тип `MetadataLoadContext`, позволяющий считывать метаданные сборки, не влияя на домен приложения вызывающего объекта. Сборки считываются как данные, включая сборки, созданные для различных архитектур и платформ, а не для текущей среды выполнения. `MetadataLoadContext` перекрывается с <xref:System.Reflection.Assembly.ReflectionOnlyLoad*>, который доступен только в .NET Framework.

`MetdataLoadContext` доступен в [пакете System.Reflection.MetadataLoadContext](https://www.nuget.org/packages/System.Reflection.MetadataLoadContext). Это пакет .NET Standard 2.0.

`MetadataLoadContext` предоставляет интерфейсы API, подобные типу <xref:System.Runtime.Loader.AssemblyLoadContext>, но не на основе этого типа. Подобно <xref:System.Runtime.Loader.AssemblyLoadContext> `MetadataLoadContext` обеспечивает загрузку сборок в изолированной вселенной загрузки сборок. Интерфейсы API `MetdataLoadContext` возвращают объекты <xref:System.Reflection.Assembly>, позволяя использовать знакомые API отражения. Интерфейсы API, ориентированные на выполнение, такие как [MethodBase.Invoke](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/src/System/Reflection/TypeLoading/Methods/RoMethod.cs#L127), не разрешены и вызывают исключение InvalidOperationException.

В следующем примере показано, как найти конкретные типы в сборке, которая реализует данный интерфейс:

```csharp
var paths = new string[] {@"C:\myapp\mscorlib.dll", @"C:\myapp\myapp.dll"};
var resolver = new PathAssemblyResolver(paths);
using (var lc = new MetadataLoadContext(resolver))
{
    Assembly a = lc.LoadFromAssemblyName("myapp");
    Type myInterface = a.GetType("MyApp.IPluginInterface");
    foreach (Type t in a.GetTypes())
    {
        if (t.IsClass && myInterface.IsAssignableFrom(t))
            Console.WriteLine($"Class {t.FullName} implements IPluginInterface");
    }
}
```

Сценарии для `MetadataLoadContext` включают в себя возможности времени разработки, инструменты, используемые во время сборки, и возможности подготовки среды выполнения, в которые должна входить проверка набора сборок в качестве данных. В них есть все блокировки файлов, а после проверки память освобождается.

В `MetadataLoadContext` есть класс сопоставителя, переданный в конструктор. Заданием сопоставителя является загрузка сборки (`Assembly`) с учетом ее `AssemblyName`. Класс сопоставителя является производным от абстрактного класса `MetadataAssemblyResolver`. Реализация сопоставителя для сценариев на основе пути входит в состав `PathAssemblyResolver`.

[Тесты MetadataLoadContext](https://github.com/dotnet/corefx/tree/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests) демонстрируют множество вариантов использования. [Тесты сборки](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests/Assembly/AssemblyTests.cs) — хорошее место для начала.

## <a name="tls-13--openssl-111-on-linux"></a>TLS 1.3 и OpenSSL 1.1.1 в Linux

.NET Core теперь будет использовать преимущества [поддержки TLS 1.3 в OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), когда она станет доступна в данной среде. Есть несколько преимуществ TLS 1.3 для [команды OpenSSL](https://www.openssl.org/blog/blog/2018/09/11/release111/):

* уменьшено время соединения в результате уменьшения количества круговых путей между клиентом и сервером;

* улучшена безопасность в результате удаления различных устаревших и небезопасных алгоритмов шифрования и шифрования нескольких подтверждений соединения.

В .NET Core 3.0 (предварительная версия 1) предусмотрена возможность использования **OpenSSL 1.1.1**, **OpenSSL 1.1.0** или **OpenSSL 1.0.2** (зависит от того, какая лучшая версия найдена в системе Linux).  Когда **OpenSSL 1.1.1** доступен, типы SslStream и HttpClient будут применять **TLS 1.3** при использовании `SslProtocols.None` (протоколы системы по умолчанию) при условии, что клиент и сервер поддерживают **TLS 1.3**.

В следующем примере показано, как .NET Core 3.0 (предварительная версия 1) подключается к Ubuntu 18.10 <https://www.cloudflare.com>:

```csharp
using System;
using System.Net.Security;
using System.Net.Sockets;
using System.Threading.Tasks;

namespace tlstest
{
    class Program
    {
        static async Task Main()
        {
            using (TcpClient tcpClient = new TcpClient())
            {
                string targetHost = "www.cloudflare.com";

                await tcpClient.ConnectAsync(targetHost, 443);

                using (SslStream sslStream = new SslStream(tcpClient.GetStream()))
                {
                    await sslStream.AuthenticateAsClientAsync(targetHost);
                    await Console.Out.WriteLineAsync($"Connected to {targetHost} with {sslStream.SslProtocol}");
                }
            }
        }
    }
}
```

```console
user@comp-ubuntu1810:~/tlstest$ dotnet run
Connected to www.cloudflare.com with Tls13
user@comp-ubuntu1810:~/tlstest$ openssl version
OpenSSL 1.1.1  11 Sep 2018
```

>[!IMPORTANT]
>Windows и macOS еще не поддерживают **TLS 1.3**. .NET Core 3.0 будет поддерживать **TLS 1.3** в этих операционных системах, когда поддержка станет доступной.

## <a name="cryptography"></a>Шифрование

Добавлена поддержка шифров **AES-GCM** и **AES-CCM**, реализованных с помощью `System.Security.Cryptography.AesGcm` и `System.Security.Cryptography.AesCcm`. Эти алгоритмы являются [алгоритмами шифрования с проверкой подлинности с присоединенными данными](https://en.wikipedia.org/wiki/Authenticated_encryption), и первые алгоритмы шифрования с проверкой подлинности добавлены в .NET Core.

В следующем коде показано использование шифра **AesGcm** для шифрования и расшифровки случайных данных.

Код для **AesCcm** выглядит почти так же (только имена переменных класса отличаются).

```csharp
// key should be: pre-known, derived, or transported via another channel, such as RSA encryption
byte[] key = new byte[16];
RandomNumberGenerator.Fill(key);

byte[] nonce = new byte[12];
RandomNumberGenerator.Fill(nonce);

// normally this would be your data
byte[] dataToEncrypt = new byte[1234];
byte[] associatedData = new byte[333];
RandomNumberGenerator.Fill(dataToEncrypt);
RandomNumberGenerator.Fill(associatedData);

// these will be filled during the encryption
byte[] tag = new byte[16];
byte[] ciphertext = new byte[dataToEncrypt.Length];

using (AesGcm aesGcm = new AesGcm(key))
{
    aesGcm.Encrypt(nonce, dataToEncrypt, ciphertext, tag, associatedData);
}

// tag, nonce, ciphertext, associatedData should be sent to the other part

byte[] decryptedData = new byte[ciphertext.Length];

using (AesGcm aesGcm = new AesGcm(key))
{
    aesGcm.Decrypt(nonce, ciphertext, tag, decryptedData, associatedData);
}

// do something with the data
// this should always print that data is the same
Console.WriteLine($"AES-GCM: Decrypted data is{(dataToEncrypt.SequenceEqual(decryptedData) ? "the same as" : "different than")} original data.");
```

## <a name="cryptographic-key-importexport"></a>Импорт и экспорт криптографических ключей

.NET Core 3.0 (предварительная версия 1) поддерживает импорт и экспорт асимметричных открытых и закрытых ключей из стандартных форматов, и при этом не нужно использовать сертификат X.509.

Все основные типы (RSA, DSA, ECDsa, ECDiffieHellman) поддерживают формат **X.509 SubjectPublicKeyInfo** для открытых ключей и форматы **PKCS#8 PrivateKeyInfo** и **PKCS#8 EncryptedPrivateKeyInfo** для закрытых ключей. RSA также поддерживает **PKCS#1 RSAPublicKey** и **PKCS#1 RSAPrivateKey**. Все методы экспорта создают двоичные данные в кодировке DER, а методы импорта выполняют то же самое. Если ключ хранится в формате PEM в виде текста, вызывающему объекту потребуется выполнить декодирование содержимого в формате base64, прежде чем вызывать метод импорта.

```csharp
using System;
using System.IO;
using System.Security.Cryptography;

namespace rsakeyprint
{
    class Program
    {
        static void Main(string[] args)
        {
            using (RSA rsa = RSA.Create())
            {
                byte[] keyBytes = File.ReadAllBytes(args[0]);
                rsa.ImportRSAPrivateKey(keyBytes, out int bytesRead);

                Console.WriteLine($"Read {bytesRead} bytes, {keyBytes.Length-bytesRead} extra byte(s) in file.");
                RSAParameters rsaParameters = rsa.ExportParameters(true);
                Console.WriteLine(BitConverter.ToString(rsaParameters.D));
            }
        }
    }
}
```

```console
user@comp-ubuntu1810:~/rsakeyprint$ echo Making a small key to save on screen space.
Making a small key to save on screen space.
user@comp-ubuntu1810:~/rsakeyprint$ openssl genrsa 768 | openssl rsa -outform der -out rsa.key
Generating RSA private key, 768 bit long modulus (2 primes)
..+++++++
........+++++++
e is 65537 (0x010001)
writing RSA key
user@comp-ubuntu1810:~/rsakeyprint$ dotnet run rsa.key
Read 461 bytes, 0 extra byte(s) in file.
0F-D0-82-34-F8-13-38-4A-7F-C7-52-4A-F6-93-F8-FB-6D-98-7A-6A-04-3B-BC-35-8C-7D-AC-A5-A3-6E-AD-C1-66-30-81-2C-2A-DE-DA-60-03-6A-2C-D9-76-15-7F-61-97-57-
79-E1-6E-45-62-C3-83-04-97-CB-32-EF-C5-17-5F-99-60-92-AE-B6-34-6F-30-06-03-AC-BF-15-24-43-84-EB-83-60-EF-4D-3B-BD-D9-5D-56-26-F0-51-CE-F1
user@comp-ubuntu1810:~/rsakeyprint$ openssl rsa -in rsa.key -inform der -text -noout | grep -A7 private
privateExponent:
    0f:d0:82:34:f8:13:38:4a:7f:c7:52:4a:f6:93:f8:
    fb:6d:98:7a:6a:04:3b:bc:35:8c:7d:ac:a5:a3:6e:
    ad:c1:66:30:81:2c:2a:de:da:60:03:6a:2c:d9:76:
    15:7f:61:97:57:79:e1:6e:45:62:c3:83:04:97:cb:
    32:ef:c5:17:5f:99:60:92:ae:b6:34:6f:30:06:03:
    ac:bf:15:24:43:84:eb:83:60:ef:4d:3b:bd:d9:5d:
    56:26:f0:51:ce:f1
```

Файлы PKCS#8 можно проверить с помощью класса `System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo`.

Файлы PFX/PKCS#12 можно проверить и использовать с помощью `System.Security.Cryptography.Pkcs.Pkcs12Info` и `System.Security.Cryptography.Pkcs.Pkcs12Builder` соответственно.

## <a name="serialport-for-linux"></a>SerialPort для Linux

.NET Core 3.0 теперь поддерживает <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> в Linux.

Ранее среда .NET Core поддерживала только использование типа `SerialPort` в Windows.

## <a name="more-bcl-improvements"></a>Дополнительные улучшения BCL

`Span<T>`, `Memory<T>` и связанные типы, которые впервые появились в .NET Core 2.1, были оптимизированы в .NET Core 3.0. Такие распространенные операции, как создание span, создание срезов, анализ и форматирование, теперь работают лучше.

Кроме того, усовершенствованы такие типы, как `String`, чтобы повысить их эффективность при использовании в качестве ключей с `Dictionary<TKey, TValue>` и другими коллекциями. Для использования этих преимуществ изменения кода не требуются.

Следующие улучшения также являются новшествами в .NET Core 3 (предварительная версия 1):

* поддержка Brotli, встроенная в HttpClient;
* ThreadPool.UnsafeQueueWorkItem(IThreadPoolWorkItem);
* Unsafe.Unbox;
* CancellationToken.Unregister;
* сложные арифметические операторы;
* интерфейсы API сокета для поддержки TCP в активном состоянии;
* StringBuilder.GetChunks;
* синтаксический анализ IPEndPoint;
* RandomNumberGenerator.GetInt32.

## <a name="tiered-compilation"></a>Многоуровневая компиляция

[Многоуровневая компиляция](https://devblogs.microsoft.com/dotnet/tiered-compilation-preview-in-net-core-2-1/) по умолчанию включена в .NET Core 3.0. Это возможность, благодаря которой среда выполнения более адаптивно использует компилятор JIT для повышения производительности при запуске и максимального увеличения пропускной способности.

Эта возможность добавлена в качестве возможности, включаемой пользователем в [.NET Core 2.1](https://devblogs.microsoft.com/dotnet/announcing-net-core-2-1/), а затем была включена по умолчанию в [.NET Core 2.2 (предварительная версия 2)](https://devblogs.microsoft.com/dotnet/announcing-net-core-2-2-preview-2/). Затем в выпуске .NET Core 2.2 она была возвращена в состояние возможности, включаемой пользователем.

## <a name="arm64-linux-support"></a>Поддержка ARM64 Linux

Для Linux добавлена поддержка ARM64. Основной вариант использования для ARM64 в данный момент — это сценарии Интернета вещей.

[Образы Docker Alpine, Debian и Ubuntu доступны для .NET Core для ARM64](https://hub.docker.com/r/microsoft/dotnet/).

Дополнительные сведения см. в статье о [состоянии .NET Core ARM64](https://github.com/dotnet/announcements/issues/82).

>[!NOTE]
> Поддержка **ARM64** в Windows еще недоступна.

## <a name="install-net-core-30-previews-on-linux-with-snap"></a>Установка предварительных версий .NET Core 3.0 в Linux с помощью Snap

Snap — это предпочтительный способ устанавливать и испытывать предварительные версии .NET Core в [дистрибутивах Linux с поддержкой Snap](https://docs.snapcraft.io/installing-snapd/6735).

После настройки Snap в системе выполните следующую команду, чтобы установить [предварительную версию пакета SDK для .NET Core 3.0](https://snapcraft.io/dotnet-sdk).

```console
sudo snap install dotnet-sdk --beta --classic
```

Если .NET Core установлен с помощью пакета Snap, команда .NET Core по умолчанию — `dotnet-sdk.dotnet`, а не `dotnet`. Преимущество команды с пространством имен в том, что она не будет конфликтовать с глобально установленной версией .NET Core, если она у вас есть. Эта команда может получить псевдоним `dotnet` с помощью:

```console
sudo snap alias dotnet-sdk.dotnet dotnet
```

Для некоторых дистрибутивов требуется дополнительный шаг, чтобы разрешить доступ к SSL-сертификату. Дополнительные сведения см. в разделе [Настройка для Linux](https://github.com/dotnet/core/blob/master/Documentation/linux-setup.md).

## <a name="gpio-support-for-raspberry-pi"></a>Поддержка GPIO для Raspberry Pi

В NuGet выпущено два новых пакета, которые можно использовать для программирования GPIO.

* [System.Device.Gpio](https://www.nuget.org/packages/System.Device.Gpio/0.1.0-prerelease.19078.2)
* [Iot.Device.Bindings](https://www.nuget.org/packages/Iot.Device.Bindings/0.1.0-prerelease.19078.2)

Пакеты GPIO содержат API для устройств GPIO, SPI, I2C и PWM. Пакет привязок Интернета вещей включает в себя [привязки устройств](https://github.com/dotnet/iot/blob/master/src/devices/README.md) для различных микросхем и датчиков, которые доступны в [dotnet/iot - src/devices](https://github.com/dotnet/iot/tree/master/src/devices).

Обновленные API последовательного порта, которые были объявлены как часть .NET Core 3.0, предварительная версия 1, не входят в эти пакеты, но доступны как часть платформы .NET Core.

## <a name="platform-support"></a>Поддержка платформ

.NET Core 3.0 поддерживается в следующих операционных системах:

* Windows Client: 7, 8.1, 10 (1607+)
* Windows Server: 2012 R2 с пакетом обновления 1 (SP1) и выше
* macOS: 10.12+
* RHEL: 6+
* Fedora: 26+
* Ubuntu: 16.04+
* Debian: 9+
* SLES: 12+
* openSUSE: 42.3+
* Alpine: 3.8+

Поддержка микросхемы:

* x64 в Windows, macOS и Linux
* x86 в Windows
* ARM32 в Windows и Linux
* ARM64 в Linux

Для Linux ARM32 поддерживается на Debian 9+ и Ubuntu 16.04+. ARM64 аналогично ARM32, но с добавлением Alpine 3.8. Это те же версии этих дистрибутивов, что и для X64.

Образы Docker для .NET Core 3.0 можно найти в [microsoft/dotnet в Docker Hub](https://hub.docker.com/r/microsoft/dotnet/). В настоящее время Майкрософт внедряет [реестр контейнеров Microsoft (MCR)](https://cloudblogs.microsoft.com/opensource/2019/01/17/improved-discovery-experience-microsoft-containers-docker-hub/), и предполагается, что окончательные образы .NET Core 3.0 будут опубликованы только в MCR.
