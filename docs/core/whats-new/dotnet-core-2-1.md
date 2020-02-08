---
title: Новые возможности .NET Core 2.1
description: Дополнительные сведения о новых возможностях .NET Core 2.1.
dev_langs:
- csharp
- vb
ms.date: 10/10/2018
ms.openlocfilehash: 32784f7d4b9e3a93eb7f81b4829b39c1a06ef949
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920396"
---
# <a name="whats-new-in-net-core-21"></a>Новые возможности .NET Core 2.1

В .NET Core 2.1 представлены следующие улучшения и новые возможности:

- [инструментарий](#tooling);
- [накат](#roll-forward);
- [Развертывание](#deployment)
- [пакет обеспечения совместимости с Windows](#windows-compatibility-pack);
- [улучшения JIT-компиляции](#jit-compiler-improvements);
- [изменения API](#api-changes);

## <a name="tooling"></a>Инструментарий

Пакет SDK .NET Core 2.1 (версия 2.1.300), который входит в комплектацию .NET Core 2.1, включает следующие изменения и усовершенствования.

### <a name="build-performance-improvements"></a>Повышение производительности сборки.

Основное внимание в .NET Core 2.1 уделено производительности сборки, что позволило сократить требуемое время, особенно для добавочной сборки. Эти улучшения производительности применяются к сборке, выполняемой из командной строки с помощью `dotnet build` или в Visual Studio. Вот несколько из этих улучшений:

- при разрешении ресурсов в пакете разрешаются только те ресурсы, которые используются для сборки, а не все;

- кэширование ссылок на сборки;

- использование серверов сборки SDK длительного выполнения, которые не завершаются после каждого отдельного вызова `dotnet build`. Это позволяет не применять JIT-компиляцию для больших блоков кода при каждом вызове `dotnet build`. Процессы серверов сборки можно автоматически завершить с помощью следующей команды:

   ```dotnetcli
   dotnet buildserver shutdown
   ```

### <a name="new-cli-commands"></a>Новые команды интерфейса командной строки

Ряд средств, которые ранее были доступны только для отдельных проектов с использованием [`DotnetCliToolReference`](../tools/extensibility.md), теперь стали частью пакета SDK для .NET Core. К ним относятся следующие средства:

- `dotnet watch` предоставляет наблюдатель файловой системы, который ожидает изменений в файле и выполняет для него указанный набор команд. Например, следующая команда автоматически перестраивает текущий проект и выводит подробные результаты при любом изменении файла в проекте:

   ```dotnetcli
   dotnet watch -- --verbose build
   ```

   Обратите внимание на параметр `--` перед параметром `--verbose`. Он отделяет параметры, передаваемые непосредственно в команду `dotnet watch`, от аргументов для дочернего процесса `dotnet`. Без него параметр `--verbose` был бы применен к команде `dotnet watch`, а не к `dotnet build`.
  
   Дополнительные сведения см. в статье [Разработка приложений ASP.NET Core с использованием наблюдателя файлов](/aspnet/core/tutorials/dotnet-watch).

- `dotnet dev-certs` создает сертификаты, используемые при разработке в приложениях ASP.NET Core, и управляет ими;

- `dotnet user-secrets` управляет секретами в хранилище секретов пользователя в приложениях ASP.NET Core;

- `dotnet sql-cache` создает в базе данных Microsoft SQL Server таблицу и индексы, которые будут использоваться для распределенного кэширования;

- `dotnet ef` выполняет роль средства для управления базами данных, объектами <xref:Microsoft.EntityFrameworkCore.DbContext> и миграциями в приложениях Entity Framework Core. Дополнительные сведения см. в [описании программ командной строки для EF Core .NET](/ef/core/miscellaneous/cli/dotnet).

### <a name="global-tools"></a>Глобальные инструменты

.NET Core 2.1 поддерживает *глобальные инструменты*, то есть специальные средства, которые доступны глобально из командной строки. Модель расширяемости в предыдущих версиях .NET Core предоставляла пользовательские средства только отдельно для каждого проекта с использованием [`DotnetCliToolReference`](../tools/extensibility.md#consuming-per-project-tools).

Чтобы установить глобальные инструменты, выполните команду [dotnet tool install](../tools/dotnet-tool-install.md). Пример:

```dotnetcli
dotnet tool install -g dotnetsay
```

Установленные инструменты можно запускать из командной строки, указав имя инструмента. См. дополнительные сведения о [глобальных инструментах .NET Core](../tools/global-tools.md).

### <a name="tool-management-with-the-dotnet-tool-command"></a>Управление инструментами с помощью команды `dotnet tool`

В пакете SDK для .NET Core 2.1 все действия с инструментами выполняются с помощью команды `dotnet tool`. Доступны следующие параметры.

- [`dotnet tool install`](../tools/dotnet-tool-install.md) устанавливает инструмент.

- [`dotnet tool update`](../tools/dotnet-tool-update.md) удаляет и переустанавливает инструмент, то есть по сути обновляет его.

- [`dotnet tool list`](../tools/dotnet-tool-list.md) выводит список установленных инструментов.

- [`dotnet tool uninstall`](../tools/dotnet-tool-uninstall.md) удаляет все установленные инструменты.

## <a name="roll-forward"></a>Накат

Все приложения .NET Core, начиная с .NET Core версии 2.0, выполняют автоматический накат до последней *дополнительной версии*, установленной в системе.

Начиная с .NET Core 2.0, если приложение было создано с помощью версии .NET Core, которая отсутствует во время выполнения, приложение автоматически выполняется в самой новой из установленных *дополнительных версий* .NET Core. Другими словами, если приложение создано с помощью .NET 2.0 Core и выполняется в системе, где отсутствует .NET Core 2.0, но присутствует .NET Core 2.1, это приложение выполняется в .NET Core 2.1.

> [!IMPORTANT]
> Стратегия наката не применяется к предварительным версиям. По умолчанию она также не применяется к основным версиям, однако это поведение можно изменить с помощью показанных ниже параметров.

С помощью этого параметра вы можете изменить это поведение для выполнения наката при отсутствии подходящей общей платформы. Доступные параметры:

- `0`. Отключает накат для дополнительных версий. Если задано это значение, для приложения для .NET Core 2.0.0 будет выполняться накат до версии .NET Core 2.0.1, но не до версии .NET Core 2.2.0 или .NET Core 3.0.0.
- `1`. Включает накат для дополнительных версий. Это значение параметра по умолчанию. Если задано это значение, для приложения для .NET Core 2.0.0 будет выполняться накат либо до версии .NET Core 2.0.1, либо до версии .NET Core 2.2.0 (в зависимости от установленной версии), но не до версии .NET Core 3.0.0.
- `2`. Включает накат для дополнительных и основных версий. Если установлено это значение, учитываются разные основные версии, поэтому для приложения для .NET Core 2.0.0 будет выполняться накат до версии .NET Core 3.0.0.

Этот параметр можно изменить любым из трех способов:

- Присвоить нужное значение переменной среды `DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`.

- Добавить следующую строку с нужным значением в файл *.runtimeconfig.json*:

   ```json
   "rollForwardOnNoCandidateFx" : 0
   ```

- При использовании [.NET Core CLI](../tools/index.md) включить следующий параметр с нужным значением помощью команды .NET Core, например `run`:

   ```dotnetcli
   dotnet run --rollForwardOnNoCandidateFx=0
   ```

Накат версий исправлений выполняется независимо от значения этого параметра после применения любых потенциальных дополнительных или основных версий.

## <a name="deployment"></a>Развертывание

### <a name="self-contained-application-servicing"></a>Обслуживание автономного приложения

Теперь `dotnet publish` публикует автономные приложения с обслуживаемой версией среды выполнения. При публикации автономного приложения с помощью пакета SDK для .NET Core 2.1 (версия 2.1.300) такое приложение использует самую последнюю обслуживаемую версию среды выполнения, известную этому пакету SDK. После обновления до последнего выпуска пакета SDK публикация выполняется с использованием последней версии среды выполнения .NET Core. Это применимо для сред выполнения .NET Core 1.0 и более поздних версий.

Автономная публикации зависит от версии среды выполнения в NuGet.org. Вам не нужно иметь обслуживаемую среду выполнения на локальном компьютере.

Если используется пакет SDK 2.0 для .NET Core, автономные приложения публикуются с помощью среды выполнения .NET Core 2.0.0, если в свойстве `RuntimeFrameworkVersion` не указана другая версия. Такое поведение позволяет не устанавливать это свойство, когда нужно выбрать более позднюю версию среды выполнения для автономного приложения. Для перехода к новой версии проще всего опубликовать приложение с пакетом SDK для .NET Core 2.1 (версия 2.1.300).

Дополнительные сведения см. в статье [Обновление версии среды выполнения автономного развертывания](../deploying/runtime-patch-selection.md).
## <a name="windows-compatibility-pack"></a>Пакет обеспечения совместимости с Windows

При переносе существующего кода с платформы .NET Framework на .NET Core вы можете использовать [пакет обеспечения совместимости с Windows](https://www.nuget.org/packages/Microsoft.Windows.Compatibility). Он предоставляет доступ к 20 000 дополнительных интерфейсов API, которые не поддерживаются в .NET Core. Сюда входят такие API-интерфейсы, как пространство имен <xref:System.Drawing?displayProperty=nameWithType>, класс <xref:System.Diagnostics.EventLog>, инструментарий WMI, счетчики производительности, службы Windows, типы и члены реестра Windows.

## <a name="jit-compiler-improvements"></a>Усовершенствования JIT-компилятора

.NET Core теперь включает новую технологию JIT-компиляции, которая называется *многоуровневая компиляция* (или *адаптивная оптимизация*), что позволяет значительно повысить производительность. Многоуровневая компиляции включается пользователем.

Одна из важных задач, которую выполняет JIT-компилятор, это оптимизация выполнения кода. Но для редко используемых путей кода компилятор может потратить на оптимизацию больше времени, чем потребуется на выполнение неоптимизированного кода. Многоуровневая компиляция разделяет JIT-компиляцию на два уровня.

- **Первый уровень** создает код настолько быстро, насколько это возможно.

- **Второй уровень** создает оптимизированный код для тех методов, которые выполняются часто. Второй уровень компиляции выполняется параллельно, чтобы повысить производительность.

Вы можете включить многоуровневую компиляцию одним из двух способов.

- Чтобы использовать многоуровневую компиляцию во всех проектах, которые работают с пакетом SDK для 2.1 .NET Core, задайте следующую переменную среды:

  ```console
  COMPlus_TieredCompilation="1"
  ```

- Чтобы использовать многоуровневую компиляцию отдельно для конкретных проектов, добавьте свойство `<TieredCompilation>` в раздел `<PropertyGroup>` файла проекта MSBuild, как показано в следующем примере:

   ```xml
   <PropertyGroup>
      <!-- other property definitions -->

      <TieredCompilation>true</TieredCompilation>
   </PropertyGroup>
   ```

## <a name="api-changes"></a>Изменения API

### <a name="spant-and-memoryt"></a>`Span<T>` и `Memory<T>`

.NET Core 2.1 включает несколько новых типов, которые значительно повышают эффективность работы с массивами и другими типами памяти. Новые типы включают:

- <xref:System.Span%601?displayProperty=nameWithType> и <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>.

- <xref:System.Memory%601?displayProperty=nameWithType> и <xref:System.ReadOnlyMemory%601?displayProperty=nameWithType>.

Без этих типов при передаче таких элементов в составе массива или в сегменте буфера памяти необходимо создавать копию данных перед их передачей в метод. Эти типы обеспечивают виртуальное представление данных, что позволяет не выделять дополнительную память и не выполнять дополнительные операции копирования.

В следующем примере экземпляр <xref:System.Span%601> и <xref:System.Memory%601> используется для создания виртуального представления 10 элементов массива.

[!code-csharp[Span\<T>](~/samples/core/whats-new/whats-new-in-21/cs/program.cs)]

[!code-vb[Memory\<T>](~/samples/core/whats-new/whats-new-in-21/vb/program.vb)]

### <a name="brotli-compression"></a>Сжатие Brotli

В .NET Core 2.1 добавлена поддержка сжатия и распаковки Brotli. Brotli — это универсальный алгоритм сжатия данных без потерь, который определен в [RFC 7932](https://www.ietf.org/rfc/rfc7932.txt) и поддерживается большинством веб-браузеров и всеми основными веб-серверами. Вы можете использовать потоковый класс <xref:System.IO.Compression.BrotliStream?displayProperty=nameWithType> или высокопроизводительные классы <xref:System.IO.Compression.BrotliEncoder?displayProperty=nameWithType> и <xref:System.IO.Compression.BrotliDecoder?displayProperty=nameWithType> на основе диапазонов. Следующий пример демонстрирует сжатие с применением класса <xref:System.IO.Compression.BrotliStream>.

[!code-csharp[Brotli compression](~/samples/core/whats-new/whats-new-in-21/cs/brotli.cs#1)]

[!code-vb[Brotli compression](~/samples/core/whats-new/whats-new-in-21/vb/brotli.vb#1)]

<xref:System.IO.Compression.BrotliStream> действует так же, как <xref:System.IO.Compression.DeflateStream> и <xref:System.IO.Compression.GZipStream>, что позволяет легко преобразовать в <xref:System.IO.Compression.BrotliStream> код, вызывающий эти API-интерфейсы.

### <a name="new-cryptography-apis-and-cryptography-improvements"></a>Новые улучшения и API криптографии

.NET Core 2.1 включает многочисленные улучшения API криптографии:

- <xref:System.Security.Cryptography.Pkcs.SignedCms?displayProperty=nameWithType> доступно в пакете System.Security.Cryptography.Pkcs. Реализация здесь такая же, как и в классе <xref:System.Security.Cryptography.Pkcs.SignedCms> для .NET Framework.

- Новые перегрузки методов <xref:System.Security.Cryptography.X509Certificates.X509Certificate.GetCertHash%2A?displayProperty=nameWithType> и <xref:System.Security.Cryptography.X509Certificates.X509Certificate.GetCertHashString%2A?displayProperty=nameWithType> принимают идентификатор хэш-алгоритма, чтобы вызывающие методы могли получать значения отпечатка сертификата с алгоритмами, отличными от SHA-1.

- Доступен новый API криптографии на основе <xref:System.Span%601>, который поддерживает хэширование, HMAC, криптографический генератор случайных чисел, генератор асимметричной подписи, обработку асимметричной подписи и шифрование RSA.

- Производительность <xref:System.Security.Cryptography.Rfc2898DeriveBytes?displayProperty=nameWithType> улучшена примерно на 15 % благодаря реализации на основе <xref:System.Span%601>.

- Новый класс <xref:System.Security.Cryptography.CryptographicOperations?displayProperty=nameWithType> включает два новых метода:

  - <xref:System.Security.Cryptography.CryptographicOperations.FixedTimeEquals%2A> выполняется в течение строго фиксированного промежутка времени для любых входных параметров одинаковой длины, что очень удобно для использования в криптографической проверке без добавления информации о времени работы стороннего канала.

  - Процедура <xref:System.Security.Cryptography.CryptographicOperations.ZeroMemory%2A> выполняет очистку памяти и не может быть оптимизирована.

- Статический метод <xref:System.Security.Cryptography.RandomNumberGenerator.Fill%2A?displayProperty=nameWithType> заполняет <xref:System.Span%601> случайными значениями.

- Теперь <xref:System.Security.Cryptography.Pkcs.EnvelopedCms?displayProperty=nameWithType> поддерживается в macOS и Linux.

- Эллиптические кривые Диффи—Хелмана (ECDH) теперь доступны в семействе классов <xref:System.Security.Cryptography.ECDiffieHellman?displayProperty=nameWithType>. Контактная зона сохраняется такой же, как в .NET Framework.

- Экземпляр, возвращаемый <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType>, умеет шифровать и расшифровывать данные с помощью OAEP и хэш-кода SHA-2, а также создавать и проверять подписи с помощью RSA-PSS.

### <a name="sockets-improvements"></a>Улучшения для сокетов

.NET Core включает новый тип <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> и переработанный <xref:System.Net.Http.HttpMessageHandler?displayProperty=nameWithType>, которые создают основу для сетевых API-интерфейсов более высокого уровня.  Например, <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> является основой для реализации <xref:System.Net.Http.HttpClient>. В предыдущих версиях .NET Core API-интерфейсы более высокого уровня основывались на собственных реализациях сетевых служб.

Реализация сокетов, добавленная в .NET Core 2.1 имеет ряд преимуществ:

- Значительное улучшение производительности по сравнению с предыдущей реализацией.

- Устранение зависимостей платформы, что упрощает развертывание и обслуживание.

- Согласованное поведение на всех платформах .NET Core.

<xref:System.Net.Http.SocketsHttpHandler> является реализацией по умолчанию в .NET Core 2.1. Но вы можете настроить в приложении использование более старой версии класса <xref:System.Net.Http.HttpClientHandler>, вызвав метод <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>:

```csharp
AppContext.SetSwitch("System.Net.Http.UseSocketsHttpHandler", false);
```

```vb
AppContext.SetSwitch("System.Net.Http.UseSocketsHttpHandler", False)
```

Можно также использовать переменную среды, чтобы отказаться от использования реализации сокетов на основе <xref:System.Net.Http.SocketsHttpHandler>. Для этого задайте для свойства `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` значение `false` или 0.

В Windows можно использовать также <xref:System.Net.Http.WinHttpHandler?displayProperty=nameWithType>, чтобы использовать собственную реализацию, или класс <xref:System.Net.Http.SocketsHttpHandler>, передав экземпляр этого класса в конструктор <xref:System.Net.Http.HttpClient>.

В macOS и Linux вы можете настроить <xref:System.Net.Http.HttpClient> только отдельно для каждого процесса. В Linux необходимо развернуть [libcurl](https://curl.haxx.se/libcurl/), если вы хотите использовать старую реализацию <xref:System.Net.Http.HttpClient>. (Она устанавливается вместе с .NET Core 2.0.)

## <a name="see-also"></a>См. также

- [Новые возможности .NET Core](index.md)
- [Новые возможности в EF Core 2.1](/ef/core/what-is-new/ef-core-2.1)
- [Новые возможности ASP.NET Core 2.1](/aspnet/core/aspnetcore-2.1)
