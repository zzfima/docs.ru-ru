---
title: Написание пользовательского хост-приложения среды выполнения .NET Core
description: Узнайте, как разместить среду выполнения .NET Core из машинного кода для поддержки сложных сценариев, требующих управления ее работой.
author: mjrousos
ms.date: 12/21/2018
ms.openlocfilehash: 46c7873a1865db04cf1c2b1bb2ded2b5dacbcc8d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "78239902"
---
# <a name="write-a-custom-net-core-host-to-control-the-net-runtime-from-your-native-code"></a>Написание пользовательского хост-приложения NET Core для управления средой выполнения .NET из машинного кода

Как и весь управляемый код, приложения .NET Core выполняются основным приложением. Основное приложение отвечает за запуск среды выполнения (включая такие компоненты, как JIT и сборщик мусора) и вызов управляемых точек входа.

Размещение среды выполнения .NET Core является расширенным сценарием, и в большинстве случаев разработчикам .NET Core не нужно беспокоиться о размещении, так как процессы сборки .NET Core предоставляют основное приложение по умолчанию для запуска приложений .NET Core. Но в отдельных ситуациях бывает удобно разместить среду выполнения .NET Core явным образом — либо как средство вызова управляемого кода в собственном процессе, либо для получения большего контроля над работой среды выполнения.

В этой статье приводится обзор действий, необходимых для запуска среды выполнения .NET Core из машинного кода и выполнения в нем управляемого кода.

## <a name="prerequisites"></a>Предварительные требования

Так как основные приложения являются собственными, в этом учебнике рассматривается создание приложения C++ для размещения .NET Core. Вам потребуется среда разработки C++ (например, предоставляемая в [Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)).

Потребуется также и простое приложение .NET Core для проверки основного приложения, поэтому следует установить пакет [.NET Core SDK](https://dotnet.microsoft.com/download) и [создать небольшое тестовое приложение .NET Core](with-visual-studio.md) (например, приложение "Hello World"). Достаточно приложения "Hello World", созданного с помощью нового шаблона для консольного проекта .NET Core.

## <a name="hosting-apis"></a>Размещение API
Есть три разных API, которые можно использовать для размещения .NET Core. В этой статье (и связанных с ней [примерах](https://github.com/dotnet/samples/tree/master/core/hosting)) рассматриваются все возможные варианты.

* Предпочтительный способ для размещения среды выполнения .NET Core в .NET Core 3.0 и более поздних версиях — это библиотеки API `nethost` и `hostfxr`. Эти точки входа решают все сложности по поиску и настройке среды выполнения для инициализации, а также поддерживают как запуск управляемого приложения, так и вызов статического управляемого метода.
* Предпочтительный способ размещения среды выполнения .NET Core в версиях до .NET Core 3.0 — API [CoreClrHost.h](https://github.com/dotnet/runtime/blob/master/src/coreclr/src/hosts/inc/coreclrhost.h). Этот API предоставляет функции для облегчения запуска и остановки среды выполнения и вызова управляемого кода (либо путем запуска управляемого EXE-файла, либо путем вызова статических управляемых методов).
* Среду .NET Core можно размещать с помощью интерфейса `ICLRRuntimeHost4` в [mscoree.h](https://github.com/dotnet/runtime/blob/master/src/coreclr/src/pal/prebuilt/inc/mscoree.h). Этот API существует дольше, чем CoreClrHost.h, и вы могли заметить старые основные приложения, использующие его. Он по-прежнему работает и допускает немного большую степень контроля над процессом размещения, чем CoreClrHost. В большинстве случаев CoreClrHost.h теперь является предпочтительным из-за более простых API.

## <a name="sample-hosts"></a>Примеры основного приложения

[Пример основного приложения](https://github.com/dotnet/samples/tree/master/core/hosting), в котором демонстрируются описанные в учебнике ниже действия, доступны в репозитории dotnet/samples на сайте GitHub. Комментарии в примерах четко соответствуют пронумерованным шагам в этих учебниках. Инструкции по загрузке см. в разделе [Просмотр и скачивание примеров](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

Помните, что пример основного приложения предназначен для учебных целей, поэтому в нем реализована минимальная проверка ошибок, а удобочитаемость поставлена выше эффективности.

## <a name="create-a-host-using-nethosth-and-hostfxrh"></a>Создание узла с помощью NetHost.h и HostFxr.h

Следующая процедура описывает применение библиотек `nethost` и `hostfxr` для запуска среды выполнения .NET Core в собственном приложении и вызова управляемого статического метода. В этом [примере](https://github.com/dotnet/samples/tree/master/core/hosting/HostWithHostFxr) используется заголовок `nethost` и библиотеки, установленные в составе пакета SDK для .NET, чтобы скопировать файлы [`coreclr_delegates.h`](https://github.com/dotnet/core-setup/blob/master/src/corehost/cli/coreclr_delegates.h) и [`hostfxr.h`](https://github.com/dotnet/core-setup/blob/master/src/corehost/cli/hostfxr.h) из репозитория [dotnet/core-setup](https://github.com/dotnet/core-setup).

### <a name="step-1---load-hostfxr-and-get-exported-hosting-functions"></a>Шаг 1. Загрузка HostFxr и получение экспортированных функций размещения

Библиотека `nethost` предоставляет функцию `get_hostfxr_path` для поиска библиотеки `hostfxr`. Библиотека `hostfxr` предоставляет функции для размещения среды выполнения .NET Core. Полный список этих функций можно найти в статье [`hostfxr.h`](https://github.com/dotnet/core-setup/blob/master/src/corehost/cli/hostfxr.h) и в [документации по проектированию стандартного размещения](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/native-hosting.md). В этом примере и руководстве в целом применяются следующие элементы.

* `hostfxr_initialize_for_runtime_config`. инициализирует контекст узла и подготавливает среду выполнения .NET Core к инициализации, используя указанную конфигурацию среды выполнения.
* `hostfxr_get_runtime_delegate`. получает делегат для функций среды выполнения.
* `hostfxr_close`. закрывает контекст узла.

Для поиска библиотеки `hostfxr` используется `get_hostfxr_path`. После этого она загружается с извлечением всех экспортов.

[!code-cpp[HostFxrHost#LoadHostFxr](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithHostFxr/src/NativeHost/nativehost.cpp#LoadHostFxr)]

### <a name="step-2---initialize-and-start-the-net-core-runtime"></a>Шаг 2. Инициализация и запуск среды выполнения .NET Core

Функции `hostfxr_initialize_for_runtime_config` и `hostfxr_get_runtime_delegate` инициализируют и запускают среду выполнения .NET Core, используя конфигурацию среды выполнения для управляемого компонента, которая будет загружена. Функция `hostfxr_get_runtime_delegate` используется для получения делегата среды выполнения, который позволяет загрузить управляемую сборку и получить указатель на функцию для статического метода в этой сборке.

[!code-cpp[HostFxrHost#Initialize](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithHostFxr/src/NativeHost/nativehost.cpp#Initialize)]

### <a name="step-3---load-managed-assembly-and-get-function-pointer-to-a-managed-method"></a>Шаг 3. Загрузка управляемой сборки и получение указателя на функцию для управляемого метода

Делегат среды выполнения вызывается для загрузки управляемой сборки и получения указателя на функцию для управляемого метода. Этот делегат ожидает получить в качестве входных данных путь к сборке, имя типа и имя метода, а затем возвращает указатель на функцию, который можно использовать для вызова управляемого метода.

[!code-cpp[HostFxrHost#LoadAndGet](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithHostFxr/src/NativeHost/nativehost.cpp#LoadAndGet)]

Передавая `nullptr` в качестве имени типа делегата при вызове делегата среды выполнения, этот пример применяет подпись по умолчанию для управляемого метода:

```csharp
public delegate int ComponentEntryPoint(IntPtr args, int sizeBytes);
```

Вы можете использовать другую подпись, указав имя типа делегата при вызове делегата среды выполнения.

### <a name="step-4---run-managed-code"></a>Шаг 4. Выполнение управляемого кода

Теперь собственный узел может вызывать управляемый метод и передавать ему нужные параметры.

[!code-cpp[HostFxrHost#CallManaged](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithHostFxr/src/NativeHost/nativehost.cpp#CallManaged)]

## <a name="create-a-host-using-coreclrhosth"></a>Создание основного приложения с помощью CoreClrHost.h

Ниже приведены способы использования API CoreClrHost.h для запуска среды выполнения .NET Core в собственном приложении и вызова управляемых статических методов. Фрагменты кода в этом документе могут использовать некоторые API-интерфейсы Windows, но [полный пример основного приложения](https://github.com/dotnet/samples/tree/master/core/hosting/HostWithCoreClrHost) содержит пути кода для Windows и Linux.

[Узел Unix CoreRun](https://github.com/dotnet/runtime/tree/master/src/coreclr/src/hosts/unixcorerun) демонстрирует более сложный и приближенный к реальности пример размещения с применением файла coreclrhost.h.

### <a name="step-1---find-and-load-coreclr"></a>Шаг 1. Поиск и загрузка CoreCLR

Интерфейсы API среды выполнения .NET Core находятся в *coreclr.dll* (в Windows), в *libcoreclr.so* (на платформе Linux) или в *libcoreclr.dylib* (в macOS). Первым шагом для размещения .NET Core является загрузка библиотеки CoreCLR. Некоторые основные приложения проверяют разные пути или используют входные параметры для поиска библиотеки, пока другие могут загрузить ее по заранее определенному пути (рядом с основным приложением, например, или из известного расположения на компьютере).

После обнаружения библиотека загружается с помощью `LoadLibraryEx` (в Windows) или `dlopen` (в Linux или macOS).

[!code-cpp[CoreClrHost#1](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithCoreClrHost/src/SampleHost.cpp#1)]

### <a name="step-2---get-net-core-hosting-functions"></a>Шаг 2. Получение функций размещения .NET Core

В CoreClrHost есть несколько важных методов, полезных для размещения .NET Core:

* `coreclr_initialize`. запускает среду выполнения .NET Core и задает AppDomain по умолчанию (и только его).
* `coreclr_execute_assembly`. выполняет управляемую сборку.
* `coreclr_create_delegate`. создает указатель на функцию для управляемого метода.
* `coreclr_shutdown`. завершает среду выполнения .NET Core.
* `coreclr_shutdown_2`. аналогично `coreclr_shutdown`, но возвращает код выхода управляемого кода.

После загрузки библиотеки CoreCLR следующим шагом является получение ссылки на эти функции с помощью `GetProcAddress` (в Windows) или `dlsym` (в Linux или macOS).

[!code-cpp[CoreClrHost#2](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithCoreClrHost/src/SampleHost.cpp#2)]

### <a name="step-3---prepare-runtime-properties"></a>Шаг 3. Подготовка свойств среды выполнения

Прежде чем запустить среду выполнения, необходимо подготовить некоторые свойства, чтобы задать поведение (особенно касающиеся загрузчика сборок).

Ряд общих свойств:

* `TRUSTED_PLATFORM_ASSEMBLIES` Это список путей сборок (с разделителями ";" в Windows и ":" в Linux), которые среда выполнения сможет разрешить по умолчанию. Некоторые основные приложения имеют жестко заданные манифесты со списком сборок, которые можно загрузить. Другие добавляют в этот список все библиотеки в определенных местах (рядом с *coreclr.dll*, например).
* `APP_PATHS` Это список путей для поиска сборки, когда ее не удается найти в списке доверенных платформенных сборок (TPA). Так как основное приложение имеет больший контроль над тем, какие сборки загружаются с помощью списка доверенных платформенных сборок, рекомендуется определить, загрузку каких сборок оно ожидает, и явным образом перечислить их. Если же необходима проверка во время выполнения, это свойство позволяет реализовать и этот сценарий.
* `APP_NI_PATHS` Этот список очень похож на APP_PATHS за исключением того, что он обозначает пути для поиска образов в машинном коде.
* `NATIVE_DLL_SEARCH_DIRECTORIES` Это свойство представляет собой список путей, по которым загрузчик ищет собственные библиотеки, вызываемые через p/invoke.
* `PLATFORM_RESOURCE_ROOTS` Этот список содержит пути для поиска вспомогательных сборок ресурсов (в подкаталогах для конкретных языков и региональных параметров).

В этом примере основного приложения список доверенных платформенных сборок создается простым указанием всех библиотек в текущем каталоге:

[!code-cpp[CoreClrHost#7](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithCoreClrHost/src/SampleHost.cpp#7)]

Так как пример простой, вполне достаточно использовать свойство `TRUSTED_PLATFORM_ASSEMBLIES`:

[!code-cpp[CoreClrHost#3](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithCoreClrHost/src/SampleHost.cpp#3)]

### <a name="step-4---start-the-runtime"></a>Шаг 4. Запуск среды выполнения

В отличие от API размещения mscoree.h (описан ниже), API-интерфейсы CoreCLRHost.h запускают среду выполнения и создают домен приложения по умолчанию в рамках одного вызова. Функция `coreclr_initialize` принимает базовый путь, имя и свойства, описанные ранее, и возвращает дескриптор обратно в основное приложение с помощью параметра `hostHandle`.

[!code-cpp[CoreClrHost#4](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithCoreClrHost/src/SampleHost.cpp#4)]

### <a name="step-5---run-managed-code"></a>Шаг 5. Выполнение управляемого кода

После запуска среды выполнения основное приложение может вызывать управляемый код. Это можно сделать двумя способами. Пример кода в этом руководстве использует функцию `coreclr_create_delegate` для создания делегата для управляемого статического метода. Этот API принимает [имя сборки](../../standard/assembly/names.md), имя типа с указанием пространства имен и имя метода в качестве входных данных и возвращает делегат, который может использоваться для вызова метода.

[!code-cpp[CoreClrHost#5](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithCoreClrHost/src/SampleHost.cpp#5)]

В этом примере основное приложение теперь может вызвать `managedDelegate` для запуска метода `ManagedWorker.DoWork`.

Кроме того, функция `coreclr_execute_assembly` может использоваться для запуска управляемого исполняемого файла. Этот API принимает путь к сборке и массив аргументов в качестве входных параметров. Он загружает сборку по этому пути и вызывает ее метод main.

```C++
int hr = executeAssembly(
        hostHandle,
        domainId,
        argumentCount,
        arguments,
        "HelloWorld.exe",
        (unsigned int*)&exitCode);
```

### <a name="step-6---shutdown-and-clean-up"></a>Шаг 6. Завершение работы и очистка

Наконец, когда основное приложение закончило выполнение управляемого кода, работа среды выполнения .NET Core завершается с помощью `coreclr_shutdown` или `coreclr_shutdown_2`.

[!code-cpp[CoreClrHost#6](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithCoreClrHost/src/SampleHost.cpp#6)]

CoreCLR не поддерживает повторную инициализацию или выгрузку. Не вызывайте `coreclr_initialize` еще раз или выгрузите библиотеку CoreCLR.

## <a name="create-a-host-using-mscoreeh"></a>Создание узла с помощью Mscoree.h

Как говорилось ранее, теперь предпочтительный способ размещения среды выполнения .NET Core — API CoreClrHost.h. Интерфейс `ICLRRuntimeHost4` можно использовать по-прежнему, если интерфейса CoreClrHost.h недостаточно (если требуются нестандартные флаги загрузки, например, или если AppDomainManager необходим для домена по умолчанию). Эти инструкции помогут провести размещение .NET Core с помощью mscoree.h.

[Узел CoreRun](https://github.com/dotnet/runtime/tree/master/src/coreclr/src/hosts/corerun) демонстрирует более сложный и приближенный к реальности пример размещения с применением файла mscoree.h.

### <a name="a-note-about-mscoreeh"></a>Примечание о mscoree.h
Интерфейс размещения .NET Core (`ICLRRuntimeHost4`) определяется в [MSCOREE.IDL](https://github.com/dotnet/runtime/blob/master/src/coreclr/src/inc/MSCOREE.IDL). Версия заголовка этого файла (mscoree.h), на которую должно ссылаться ваше основное приложение, создается через MIDL при сборке [среды выполнения .NET Core](https://github.com/dotnet/runtime/). Если вы не хотите создавать среду выполнения .NET Core, в репозитории dotnet/runtime имеется [уже готовый заголовок](https://github.com/dotnet/runtime/blob/master/src/coreclr/src/pal/prebuilt/inc/) mscoree.h.

### <a name="step-1---identify-the-managed-entry-point"></a>Шаг 1. Определение управляемой точки входа
Сразу после задания ссылки на необходимые заголовки (например, [mscoree.h](https://github.com/dotnet/runtime/blob/master/src/coreclr/src/pal/prebuilt/inc/mscoree.h) и stdio.h) основное приложение .NET Core, среди прочего, должно найти управляемую точку входа, которую будет использовать. В нашем примере основного приложения это осуществляется простым использованием первого аргумента командной строки в качестве пути к управляемому двоичному файлу, из которого будет выполнен метод `main`.

[!code-cpp[NetCoreHost#1](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithMscoree/host.cpp#1)]

### <a name="step-2---find-and-load-coreclr"></a>Шаг 2. Поиск и загрузка CoreCLR
API среды выполнения .NET Core находятся в *CoreCLR.dll* (для Windows). Чтобы получить интерфейс размещения (`ICLRRuntimeHost4`), нужно найти и загрузить *CoreCLR.dll*. Соглашение о поиске *CoreCLR.dll* определяется самим основным приложением. Некоторые основные приложения ожидают найти этот файл в известном в рамках всего компьютера расположении (например, *%programfiles%\dotnet\shared\Microsoft.NETCore.App\2.1.6*). Другие ожидают, что *CoreCLR.dll* будет загружен из расположения, где размещается основное или обычное приложение. Отдельные приложения для поиска библиотеки обращаются к переменной среды.

В Linux или macOS основной библиотекой среды выполнения является *libcoreclr.so* или *libcoreclr.dylib*, соответственно.

Наш пример основного приложения проверяет наличие *CoreCLR.dll* в нескольких общих расположениях. После нахождения ее требуется загрузить через `LoadLibrary` (либо `dlopen` в Linux или macOS).

[!code-cpp[NetCoreHost#2](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithMscoree/host.cpp#2)]

### <a name="step-3---get-an-iclrruntimehost4-instance"></a>Шаг 3. Получение экземпляра ICLRRuntimeHost4
Интерфейс размещения `ICLRRuntimeHost4` извлекается путем вызова `GetProcAddress` (либо `dlsym` в Linux или macOS) на `GetCLRRuntimeHost` с последующим вызовом этой функции.

[!code-cpp[NetCoreHost#3](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithMscoree/host.cpp#3)]

### <a name="step-4---set-startup-flags-and-start-the-runtime"></a>Шаг 4. Установка флагов запуска и запуск среды выполнения
Располагая `ICLRRuntimeHost4`, можно задать флаги запуска для всей среды выполнения и запустить ее. Флаги запуска определяют, какой сборщик мусора (GC) используется (параллельный или серверный), будем ли мы применять один или несколько доменов приложений и какая используется политика оптимизации загрузчика (для нейтральной к доменам загрузки сборок).

[!code-cpp[NetCoreHost#4](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithMscoree/host.cpp#4)]

Среда выполнения запускается с помощью вызова функции `Start`.

```C++
hr = runtimeHost->Start();
```

### <a name="step-5---preparing-appdomain-settings"></a>Шаг 5. Параметры подготовки домена приложения
После запуска среды выполнения нужно настроить домен приложения. Существует ряд параметров, которые требуется указать при создании домена приложения .NET, но сначала их нужно подготовить.

Флаги домена приложения указывают его поведение, связанное с безопасностью и взаимодействием. Более старые основные приложения Silverlight использовали эти параметры для выполнения пользовательского кода в "песочнице", но большинство современных основных приложений .NET Core выполняет пользовательский код с полным доверием и допускает взаимодействие.

[!code-cpp[NetCoreHost#5](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithMscoree/host.cpp#5)]

Определив используемые флаги домена приложения, следует задать его свойства. Они представляют собой пары строк "ключ-значение". Многие свойства определят, как домен приложения загружает сборки.

К распространенным свойствам домена приложения относятся следующие:

* `TRUSTED_PLATFORM_ASSEMBLIES`Это список путей сборки (с разделителями `;` в Windows и `:` в Linux и macOS), которому домен приложения должен предоставлять приоритет при загрузке и назначать полное доверие (даже в частично доверенных доменах). Этот список предназначен для хранения сборок "Framework" и других доверенных модулей аналогично глобальному кэшу сборок в сценариях .NET Framework. Некоторые основные приложения помещают все библиотеки рядом с *coreclr.dll* в этом списке, другие имеют жестко заданные манифесты, где перечислены нужные доверенные сборки.
* `APP_PATHS` Это список путей для поиска сборки, когда ее не удается найти в списке доверенных платформенных сборок (TPA). Так как основное приложение имеет больший контроль над тем, какие сборки загружаются с помощью списка доверенных платформенных сборок, рекомендуется определить, загрузку каких сборок оно ожидает, и явным образом перечислить их. Если же необходима проверка во время выполнения, это свойство позволяет реализовать и этот сценарий.
* `APP_NI_PATHS` Этот список очень похож на APP_PATHS, за исключением того, что он обозначает пути для поиска образов в машинном коде.
* `NATIVE_DLL_SEARCH_DIRECTORIES` Это свойство представляет собой список путей, по которым загрузчик ищет собственные библиотеки DLL, вызываемые через p/invoke.
* `PLATFORM_RESOURCE_ROOTS` Этот список содержит пути для поиска вспомогательных сборок ресурсов (в подкаталогах для конкретных языков и региональных параметров).

В нашем [простом примере основного приложения](https://github.com/dotnet/samples/tree/master/core/hosting/HostWithMscoree) эти свойства настроены следующим образом:

[!code-cpp[NetCoreHost#6](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithMscoree/host.cpp#6)]

### <a name="step-6---create-the-appdomain"></a>Шаг 6. Создание домена приложения
После подготовки всех свойств и флагов домена приложения можно воспользоваться `ICLRRuntimeHost4::CreateAppDomainWithManager` для настройки домена приложения. При необходимости эта функция принимает полное имя сборки и имя типа, используемые в качестве диспетчера домена приложения. Диспетчер домена приложения может позволить основному приложению управлять некоторыми аспектами поведения домена приложения и предоставлять точки входа для запуска управляемого кода, если основное приложение не предназначено для вызова пользовательского кода напрямую.

[!code-cpp[NetCoreHost#7](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithMscoree/host.cpp#7)]

### <a name="step-7---run-managed-code"></a>Шаг 7. Выполнение управляемого кода
Запустив домен приложения, основное приложение может приступить в выполнению управляемого кода. Для этого проще всего использовать `ICLRRuntimeHost4::ExecuteAssembly`, чтобы вызвать метод точки входа управляемой сборки. Обратите внимание, что эта функция работает только в сценариях с одним доменом.

[!code-cpp[NetCoreHost#8](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithMscoree/host.cpp#8)]

Если `ExecuteAssembly` не соответствует потребностям вашего основного приложения, можно использовать `CreateDelegate`, чтобы создать указатель функции в статическом управляемом методе. При этом основному приложению нужно знать сигнатуру вызываемого метода (чтобы создать тип указателя функции), но основные приложения способны гибко вызывать код, отличный от точки входа сборки. Имя сборки, указанное во втором параметре, соответствует [полному имени управляемой сборки](../../standard/assembly/names.md) библиотеки для загрузки.

```C++
void *pfnDelegate = NULL;
hr = runtimeHost->CreateDelegate(
    domainId,
    L"HW, Version=1.0.0.0, Culture=neutral", // Target managed assembly
    L"ConsoleApplication.Program",           // Target managed type
    L"Main",                                 // Target entry point (static method)
    (INT_PTR*)&pfnDelegate);

((MainMethodFp*)pfnDelegate)(NULL);
```

### <a name="step-8---clean-up"></a>Шаг 8. Очистка
Наконец, основное приложение должно выполнить очистку, выгрузив домены приложений, остановив среду выполнения и освободив ссылку `ICLRRuntimeHost4`.

[!code-cpp[NetCoreHost#9](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithMscoree/host.cpp#9)]

CoreCLR не поддерживает выгрузку. Не выгружайте библиотеку CoreCLR.

## <a name="conclusion"></a>Заключение
После создания основного приложения его можно проверить, запустив из командной строки и передав любые аргументы (например, запускаемое в примере основного приложения mscoree управляемое приложение), которые оно ожидает. При указании запускаемого приложения .NET Core для основного приложения обязательно используйте библиотеку DLL, созданную `dotnet build`. Исполняемые EXE-файлы, созданные `dotnet publish` для автономных приложений, фактически являются основным приложением .NET Core по умолчанию (таким образом, в ключевых сценариях приложение можно запустить непосредственно из командной строки); пользовательский код компилируется в DLL-файл с тем же именем.

Если изначально что-то работает неправильно, еще раз убедитесь, что *coreclr.dll* находится в расположении, ожидаемом основным приложением, все необходимые библиотеки Framework включены в список доверенных платформенных сборок, а разрядность CoreCLR (32- или 64-разрядная версия) соответствует сборке основного приложения.

Размещение среды выполнения .NET Core — это расширенный сценарий, который многие разработчики не используют. Но он может сильно пригодиться тем, кому нужно запускать управляемый код из собственного процесса либо требуется расширенный контроль над поведением среды выполнения .NET Core.
