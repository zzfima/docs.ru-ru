---
title: Новые возможности .NET Core 3.0
description: Дополнительные сведения о новых возможностях .NET Core 3.0.
dev_langs:
- csharp
- vb
author: thraka
ms.author: adegeo
ms.date: 12/04/2018
ms.openlocfilehash: 3ca833031eb8bb0f43a334f833f2e0075842d57d
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53156672"
---
# <a name="whats-new-in-net-core-30-preview-1"></a>Новые возможности .NET Core 3.0 (предварительная версия 1)

В этой статье описываются новые возможности в .NET Core 3.0 (предварительная версия 1). Одно из основных усовершенствований — это поддержка классических приложений Windows (только Windows). Используя компонент .NET Core 3.0 под названием Windows Desktop, вы можете перенести приложения Windows Forms и Windows Presentation Foundation (WPF). Следует уточнить, что компонент Windows Desktop поддерживается только в Windows. Дополнительные сведения см. в разделе [Классические приложения Windows](#windows-desktop), приведенном ниже.

В .NET Core 3.0 добавлена поддержка C# 8.0.

[Скачайте и начните работу с .NET Core 3 (предварительная версия 1)](https://aka.ms/netcore3download) прямо сейчас в Windows, Mac и Linux. Полное описание выпуска .NET Core 3 (предварительная версия 1) см. [здесь](https://aka.ms/netcore3releasenotes).

Дополнительные сведения см. в статье, посвященной [объявлению .NET Core 3.0 (предварительная версия 1)](https://blogs.msdn.microsoft.com/dotnet/2018/12/04/announcing-net-core-3-preview-1-and-open-sourcing-windows-desktop-frameworks/).

## <a name="net-standard-21"></a>.NET Standard 2.1

.NET Core 3.0 реализует .NET Standard 2.1.

## <a name="default-executables"></a>Исполняемые файлы по умолчанию

.NET Core теперь будет создавать исполняемые файлы по умолчанию. Это новый аспект для приложений, использующих глобально установленную версию .NET Core. До настоящего времени исполняемые файлы были только в [автономных развертываниях](../deploying/index.md#self-contained-deployments-scd).

Во время выполнения команды `dotnet build` или `dotnet publish` создается исполняемый файл, который соответствует среде и платформе используемого пакета SDK. Предполагается, что с этими исполняемыми файлами можно выполнять те же действия, что и с другими исполняемыми файлами в машинном коде, например:

* исполняемый файл можно дважды щелкнуть;
* приложение можно запустить из командной строки напрямую, например `myapp.exe` в Windows и `./myapp` в Linux и macOS.

> [!NOTE]
> Указание конкретной среды выполнения с помощью аргументов `dotnet publish -r` или `dotnet build -r` для других сред выполнения не поддерживается.

## <a name="build-copies-dependencies"></a>Сборка копирует зависимости

`dotnet build` теперь копирует зависимости NuGet для вашего приложения из кэша NuGet в выходную папку сборки. Ранее зависимости копировались только в рамках выполнения команды `dotnet publish`. 

Для некоторых операций, таких как связывание и публикация страницы Razor, по-прежнему будет требоваться публикация.


## <a name="local-dotnet-tools"></a>Локальные средства dotnet

Хотя в .NET Core 2.1 была поддержка глобальных средств, в .NET Core 3.0 теперь есть локальные средства. Локальные средства похожи на глобальные средства, но связаны с определенным расположением на диске. Это обеспечивает инструменты для отдельных проектов и репозиториев. Любое средство, установленное локально, недоступно глобально.

Локальные средства используют имя файла манифеста `dotnet-tools.json` в текущем каталоге. Этот файл манифеста определяет, какие средства доступны. Если создать этот файл манифеста в корне репозитория, любой пользователь, клонировавший код, сможет восстановить и использовать средства, необходимые для успешной работы с кодом.

Если файл манифеста локальных средств доступен, выполните приведенную ниже команду, чтобы автоматически скачать и установить эти средства локально:

```console
dotnet tool restore
```

Запустите локальное средство с помощью следующей команды:

```console
dotnet tool run <tool-command-name>
```

При вызове локального средства dotnet выполняет поиск манифеста в структуре каталогов. Когда файл манифеста средства обнаруживается, выполняется поиск запрашиваемого средства. При обнаружении средства добавляются сведения, необходимые для поиска средства в расположении глобальных пакетов NuGet. 

Если средство обнаруживается в манифесте, а не в кэше, пользователь получает сообщение об ошибке. Сообщение будет усовершенствовано после выхода предварительной версии 1: оно будет содержать запрос для пользователя на запуск `dotnet tool restore`.

Чтобы добавить локальные средства в каталог, необходимо сначала создать файл манифеста средства. После выхода предварительной версии 1 мы предложим механизм создания файлов манифестов средств, например новый шаблон dotnet. Для предварительной версии 1 необходимо создать файл с именем `dotnet-tools.json` со следующим содержимым:

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {}
}
```

После создания манифеста можно добавить в него локальные средства с помощью следующей команды:

```console
dotnet tool install <toolPackageId>
```

Эта команда устанавливает последнюю версию средства, если не указана другая версия.  Даже если автоматически была выбрана последняя версия, версия средства записывается в файл манифеста средства, чтобы можно было восстановить или запустить правильную версию средства.

Файл манифеста средства разработан так, чтобы его можно было редактировать вручную, например, когда необходимо обновить требуемую версию для работы с репозиторием.

Ниже приведен пример файла `dotnet-tools.json`:

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

Чтобы удалить средство из файла манифеста средства, выполните следующую команду:

```console
dotnet tool uninstall <toolPackageId>
```

Для глобальных и локальных средств требуется совместимая версия среды выполнения. Сейчас на сайте NuGet.org многие средства предназначены для среды выполнения .NET Core 2.1. Чтобы установить их глобально или локально, по-прежнему необходимо установить [среду выполнения NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1).

Дополнительные сведения см. в [документации по предварительной версии локальных средств](https://github.com/dotnet/cli/issues/10288).

## <a name="windows-desktop"></a>Классические приложения Windows

Начиная с .NET Core 3.0 (предварительная версия 1), можно создавать классические приложения Windows с помощью WPF и Windows Forms. Эти платформы также поддерживают использование современных элементов управления и стилей Fluent из библиотеки XAML пользовательского интерфейса Windows (WinUI) через [острова XAML](/windows/uwp/xaml-platform/xaml-host-controls).

Компонент Windows Desktop является частью пакета SDK .NET Core 3.0 для Windows.

Вы можете создать приложение WPF или Windows Forms с помощью следующих команд `dotnet`:

```console
dotnet new wpf
dotnet new winforms
```

Вы можете также открывать и запускать проекты WPF и Windows Forms .NET Core 3.0 и выполнять их отладку в Visual Studio 2019 (предварительная версия 1). Сейчас эти проекты можно открывать в Visual Studio 2017 15.9, но этот сценарий не поддерживается (и вам нужно [включить предварительные версии](https://blogs.msdn.microsoft.com/dotnet/2018/11/13/net-core-tooling-update-for-visual-studio-2017-version-15-9/)).

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

## <a name="fast-built-in-json-support"></a>Быстрая встроенная поддержка JSON

`System.Text.Json.Utf8JsonReader` — это однопроходный модуль чтения текста JSON в кодировке UTF-8 из `ReadOnlySpan<byte>` с высокой производительностью и низким уровнем распределения. `Utf8JsonReader` — это основной тип низкого уровня, с помощью которого можно создавать пользовательские средства синтаксического анализа и десериализаторы. Чтение полезных данных JSON с помощью нового `Utf8JsonReader` осуществляется в два раза быстрее, чем при использовании модуля чтения от [JSON.NET](https://www.newtonsoft.com/json). Распределение не осуществляется, пока не понадобится актуализировать токены JSON в виде строк (UTF-16).

Этот новый интерфейс API будет включать следующие компоненты:

* в предварительной версии 1: модуль чтения JSON (последовательный доступ);
* ожидается в следующем выпуске: модуль записи JSON, DOM (произвольный доступ), сериализатор poco, десериализатор poco.

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

В экосистеме .NET использовалась [Json.NET](https://www.newtonsoft.com/json) и другие популярные библиотеки JSON, которые по-прежнему остаются хорошими вариантами. JSON.NET использует в качестве базового типа данных строки .NET, которые обладают внутренней структурой UTF-16. 

В .NET Core 2.1 и 3.0 добавлены новые интерфейсы API, что дает возможность записывать интерфейсы API JSON (такие как `Utf8JsonReader`), для которых требуется гораздо меньше памяти и которые основаны на использовании `Span<T>` и строк UTF-8 и лучше удовлетворяют потребности приложений с высокой пропускной способностью, таких как Kestrel, веб-сервер ASP. NET Core.

## <a name="ranges-and-indices"></a>Диапазоны и индексы

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

> [!NOTE]
> Только [C# 8.0](https://blogs.msdn.microsoft.com/dotnet/2018/11/12/building-c-8-0/) поддерживает синтаксис для `Range` и `Index`.

## <a name="async-streams"></a>Асинхронные потоки

Тип `IAsyncEnumerable<T>` — это новая асинхронная версия `IEnumerable<T>`. Язык позволяет выполнить действие `await foreach` с этими объектами, чтобы использовать их элементы, и действие `yield return` по отношению к ним, чтобы создать элементы.

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

> [!WARNING]
> В .NET Core 3.0 (предварительная версия 1) сейчас есть ошибка с `await foreach`. Вместо этого используйте `GetEnumerator` и `MoveNext` для обработки элементов. Дополнительные сведения см. в [roslyn/#31268](https://github.com/dotnet/roslyn/issues/31268).

Помимо возможности `await foreach` вы также можете создать асинхронные итераторы, например, итератор, который возвращает `IAsyncEnumerable/IAsyncEnumerator`, для которого можно применить `await` и `yield`. Для объектов, которые необходимо удалить, можно использовать `IAsyncDisposable`, который реализовывают различные типы BCL, такие как `Stream` и `Timer`.

> [!NOTE]
> Только [C# 8.0](https://blogs.msdn.microsoft.com/dotnet/2018/11/12/building-c-8-0/) поддерживает синтаксис `await foreach`.

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

[Многоуровневая компиляция](https://blogs.msdn.microsoft.com/dotnet/2018/08/02/tiered-compilation-preview-in-net-core-2-1/) по умолчанию включена в .NET Core 3.0. Это возможность, благодаря которой среда выполнения более адаптивно использует компилятор JIT для повышения производительности при запуске и максимального увеличения пропускной способности.

Эта возможность добавлена в качестве возможности, включаемой пользователем в [.NET Core 2.1](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/), а затем была включена по умолчанию в [.NET Core 2.2 (предварительная версия 2)](https://blogs.msdn.microsoft.com/dotnet/2018/09/12/announcing-net-core-2-2-preview-2/). Затем в выпуске .NET Core 2.2 она была возвращена в состояние возможности, включаемой пользователем.

## <a name="arm64-linux-support"></a>Поддержка ARM64 Linux

В этом выпуске мы добавили поддержку ARM64 для Linux. Для контекста мы добавили поддержку ARM32 для Linux в .NET Core 2.1 и Windows в .NET Core 2.2. Основной вариант использования для ARM64 в данный момент — это сценарии Интернета вещей.

[Образы Docker Alpine, Debian и Ubuntu доступны для .NET Core для ARM64](https://hub.docker.com/r/microsoft/dotnet/).

Дополнительные сведения см. в статье о [состоянии .NET Core ARM64](https://github.com/dotnet/announcements/issues/82).

>[!NOTE]
> Поддержка **ARM64** в Windows еще недоступна.
