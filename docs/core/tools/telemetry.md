---
title: Телеметрия пакета SDK для .NET Core
description: Сведения о функциях телеметрии пакета SDK для .NET Core, позволяющих собирать сведения об использовании для анализа, а также о собираемых данных и способе отключения этих функций.
author: KathleenDollard
ms.date: 08/27/2019
ms.custom: seodec18
ms.openlocfilehash: ecb8dbed036a04726867d004dbadf6205c1fa09f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74281777"
---
# <a name="net-core-sdk-telemetry"></a>Телеметрия пакета SDK для .NET Core

[Пакет SDK для .NET Core](index.md) включает функцию телеметрии, которая собирает данные об использовании и сведения об исключениях при сбоях .NET Core CLI. .NET Core CLI поставляется с пакетом SDK для .NET Core и представляет собой набор команд, позволяющих создавать, тестировать и публиковать приложения .NET Core. Команде разработчиков .NET важно знать, как используются эти средства, чтобы их можно было улучшить. Сведения об ошибках помогают команде решать проблемы и устранять ошибки.

Данные собираются анонимно и публикуются в сводной форме по [лицензии Creative Commons Attribution](https://creativecommons.org/licenses/by/4.0/). 

## <a name="scope"></a>Область

`dotnet` имеет две функции: для запуска приложений и для выполнения команд CLI. Данные телеметрии *не собираются* при использовании `dotnet` для запуска приложения в следующем формате:

- `dotnet [path-to-app].dll`

Данные телеметрии *собираются* при использовании [команд CLI .NET Core](index.md), например:

- `dotnet build`
- `dotnet pack`
- `dotnet run`

## <a name="how-to-opt-out"></a>Как отключить функцию

Функция телеметрии пакета SDK для .NET Core по умолчанию включена. Чтобы отключить ее, присвойте переменной среды `DOTNET_CLI_TELEMETRY_OPTOUT` значение `1` или `true`. 

При успешной установке программа установки пакета SDK для .NET Core отправляет единую запись телеметрии. Чтобы отказаться от этого, задайте переменную среды `DOTNET_CLI_TELEMETRY_OPTOUT` перед установкой пакета SDK для .NET Core.

## <a name="disclosure"></a>Раскрытие информации

При первом выполнении одной из [команд .NET Core CLI](index.md) (например, `dotnet build`) пакет SDK для .NET Core выводит следующий текст. Он может немного отличаться в зависимости от используемой версии пакета SDK. Именно таким образом корпорация Майкрософт уведомляет вас о сборе данных.

```console
Telemetry
---------
The .NET Core tools collect usage data in order to help us improve your experience. The data is anonymous. It is collected by Microsoft and shared with the community. You can opt-out of telemetry by setting the DOTNET_CLI_TELEMETRY_OPTOUT environment variable to '1' or 'true' using your favorite shell.

Read more about .NET Core CLI Tools telemetry: https://aka.ms/dotnet-cli-telemetry
```

## <a name="data-points"></a>Точки данных

Функция телеметрии не собирает персональные данные, например имена пользователей и их адреса электронной почты. Она не проверяет код и не извлекает данные уровня проекта, например имя, репозиторий или автора. Данные отправляются по защищенному протоколу на серверы Майкрософт с помощью технологии [Azure Monitor](https://azure.microsoft.com/services/monitor/), хранятся в режиме ограниченного доступа и используются в защищенных системах [хранилища Azure](https://azure.microsoft.com/services/storage/) с соблюдением строгих мер безопасности.

Мы заботимся о вашей конфиденциальности. Если у вас есть подозрения, что функция телеметрии собирает конфиденциальные данные или что мы обрабатываем данные небезопасным либо неподобающим образом, отправьте сообщение о проблеме в репозитории [dotnet/cli](https://github.com/dotnet/cli/issues) или по адресу [dotnet@microsoft.com](mailto:dotnet@microsoft.com) для изучения.

Функция телеметрии собирает следующие данные:

| Версии пакета SDK | Data |
|--------------|------|
| Все          | Метка времени вызова. |
| Все          | Вызываемая команда (например, build), хэшируется с версии 2.1. |
| Все          | Состоящий из трех октетов IP-адрес, используемый для определения географического местоположения. |
| Все          | Операционная система и ее версия. |
| Все          | Идентификатор среды выполнения (RID), в которой работает пакет SDK. |
| Все          | Версия пакета SDK для .NET Core. |
| Все          | Профиль телеметрии: необязательное значение используется только при явном включении пользователем и внутри корпорации Майкрософт. |
| >= 2.0        | Аргументы и параметры команды: собираются только известные аргументы и параметры (но не произвольные строки). См. раздел о [собираемых параметрах](#collected-options). Хэшируется после версии 2.1.300. |
| >= 2.0         | выполняется ли пакет SDK в контейнере; |
| >= 2.0         | Целевые платформы (из события `TargetFramework`), хэшируются начиная с версии 2.1. |
| >= 2.0         | Хэшированный MAC-адрес: криптографически (SHA256) анонимный и уникальный идентификатор компьютера. |
| >= 2.0         | хэшированный текущий рабочий каталог. |
| >= 2.0         | Отчет об успешном выполнении установки с хэшированным именем EXE-файла установщика. |
| >= 2.1.300     | Версия ядра. |
| >= 2.1.300     | Выпуск или версия libc. |
| >= 3.0.100     | Были ли перенаправлены выходные данные (true или false). |
| >= 3.0.100     | При сбое интерфейса командной строки или пакета SDK тип исключения и его трассировка стека (в отправляемую трассировку стека включается только код CLI или SDK). Дополнительные сведения см. в разделе [Сбор данных телеметрии об исключениях при сбоях .NET Core CLI и SDK](#net-core-clisdk-crash-exception-telemetry-collected). |

### <a name="collected-options"></a>Собираемые параметры

Некоторые команды отправляют дополнительные данные. Подмножество команд отправляет первый аргумент:

| Команда               | Данные первого аргумента отправлены                |
|-----------------------|-----------------------------------------|
| `dotnet help <arg>`   | Запрашивается справка по командам.  |
| `dotnet new <arg>`    | Имя шаблона (хэшированное).             |
| `dotnet add <arg>`    | Слово `package` или `reference`.      |
| `dotnet remove <arg>` | Слово `package` или `reference`.      |
| `dotnet list <arg>`   | Слово `package` или `reference`.      |
| `dotnet sln <arg>`    | Слово `add`, `list` или `remove`.    |
| `dotnet nuget <arg>`  | Слово `delete`, `locals` или `push`. |

Подмножество команд отправляет выбранные параметры, если они используются, а также их значения:

| Параметр                  | Команды                                                                                       |
|-------------------------|------------------------------------------------------------------------------------------------|
| `--verbosity`           | Все команды                                                                                   |
| `--language`            | `dotnet new`                                                                                   |
| `--configuration`       | `dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`                  |
| `--framework`           | `dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`, `dotnet vstest` |
| `--runtime`             | `dotnet build`, `dotnet publish`                                                              |
| `--platform`            | `dotnet vstest`                                                                                |
| `--logger`              | `dotnet vstest`                                                                                |
| `--sdk-package-version` | `dotnet migrate`                                                                               |

За исключением `--verbosity` и `--sdk-package-version` все остальные значения хэшируются, начиная с пакета SDK для .NET Core 2.1.100.

## <a name="net-core-clisdk-crash-exception-telemetry-collected"></a>Сбор данных телеметрии об исключениях при сбоях .NET Core CLI и SDK

В случае сбоя .NET Core CLI или пакета SDK он собирает имя исключения и трассировку стека кода CLI/SDK. Эти сведения собираются для оценки проблем и улучшения качества пакета SDK для .NET Core и интерфейса командной строки. В этой статье приводятся сведения о данных, которые мы собираем. Кроме того, она содержит советы, помогающие пользователям, создающим собственную версию пакета SDK для .NET Core, избежать случайного раскрытия личных или конфиденциальных сведений.

### <a name="types-of-collected-data"></a>Типы собираемых данных

.NET Core CLI собирает сведения только об исключениях CLI/SDK, а не об исключениях в приложении. Собранные данные содержат имя исключения и трассировку стека. Эта трассировка стека относится к коду CLI или пакета SDK.

В следующем примере показан тип собираемых данных:

```console
System.IO.IOException
at System.ConsolePal.WindowsConsoleStream.Write(Byte[] buffer, Int32 offset, Int32 count)
at System.IO.StreamWriter.Flush(Boolean flushStream, Boolean flushEncoder)
at System.IO.StreamWriter.Write(Char[] buffer)
at System.IO.TextWriter.WriteLine()
at System.IO.TextWriter.SyncTextWriter.WriteLine()
at Microsoft.DotNet.Cli.Utils.Reporter.WriteLine()
at Microsoft.DotNet.Tools.Run.RunCommand.EnsureProjectIsBuilt()
at Microsoft.DotNet.Tools.Run.RunCommand.Execute()
at Microsoft.DotNet.Tools.Run.RunCommand.Run(String[] args)
at Microsoft.DotNet.Cli.Program.ProcessArgs(String[] args, ITelemetry telemetryClient)
at Microsoft.DotNet.Cli.Program.Main(String[] args)
```

### <a name="avoid-inadvertent-disclosure-information"></a>Избегайте случайного разглашения информации

Участники .NET Core и все остальные, кто использует версию пакета SDK для .NET Core, которую они создали сами, должны учитывать путь к исходному коду пакета SDK. Если сбой происходит при использовании пакета SDK для .NET Core, который является пользовательской сборкой отладки или настроен с помощью файлов пользовательских символов сборки, путь к исходному файлу пакета SDK с компьютера сборки собирается как часть трассировки стека и не хэшируется.

По этой причине пользовательские сборки пакета SDK для .NET Core не должны размещаться в каталогах, имена путей которых раскрывают персональные или конфиденциальные сведения. 

## <a name="see-also"></a>См. также

- [Телеметрия .NET Core CLI, данные за 2 кв 2019 г.](https://dotnet.microsoft.com/platform/telemetry/dotnet-core-cli-2019q2)
- [Справочные материалы по телеметрии (репозиторий dotnet/cli)](https://github.com/dotnet/cli/tree/master/src/dotnet/Telemetry)
