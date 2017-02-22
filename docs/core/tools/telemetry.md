---
title: "Сбор телеметрии по инструментам .NET Core | Microsoft Docs"
description: .NET Core
keywords: .NET, .NET Core
author: richlander
ms.author: mairaw
ms.date: 07/06/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: f2b312bb-f80b-4b0d-9101-93908f06a6fa
translationtype: Human Translation
ms.sourcegitcommit: 796df1549a7553aa93158598d62338c02d4df73e
ms.openlocfilehash: f19efabc4330682ebfe6e38384086e2338cd6264

---

# <a name="net-core-tools-telemetry"></a>Средства телеметрии .NET Core

> [!WARNING]
> Эта статья применима к инструментам .NET Core (предварительная версия 2). Сведения для версии-кандидата 4 средств .NET Core см. в разделе [Телеметрия средств .NET Core (версия-кандидат 4 средств .NET Core)](../preview3/tools/telemetry.md).

Средства .NET Core включают в себя [функцию телеметрии](https://github.com/dotnet/cli/pull/2145), которая собирает сведения об использовании. Команде разработчиков .NET важно знать, как используются эти средства, чтобы иметь возможность улучшить их.

Данные собираются анонимно и публикуются в сводной форме для использования корпорацией Майкрософт и специалистами сообщества по [лицензии Creative Commons Attribution](https://creativecommons.org/licenses/by/4.0/).

## <a name="scope"></a>Область

Команда `dotnet` служит для запуска как приложений, так и средств .NET Core. Сама по себе команда `dotnet` не собирает данные телеметрии. Этим занимаются средства .NET Core, которые запускаются с помощью команды `dotnet`.

Команды .NET Core (телеметрия не включена):

- `dotnet`
- `dotnet [path-to-app]`

[Команды](index.md) средств .NET Core (телеметрия включена):

- `dotnet build`
- `dotnet pack`
- `dotnet restore`
- `dotnet run`

##<a name="behavior"></a>Поведение

Функция телеметрии средств .NET Core по умолчанию включена. Вы можете отказаться от ее использования, присвоив переменной среды DOTNET_CLI_TELEMETRY_OPTOUT (например, `export` в Mac OS и Linux или `set` в Windows) значение true (или 1).

##<a name="data-points"></a>Точки данных

Средство собирает следующие данные:

- используемая команда (например, build, restore);
- код выхода команды;
- используемое средство запуска тестов в случае тестового проекта;
- метка времени вызова;
- используемая платформа;
- наличие идентификаторов сред выполнения в узле runtimes;
- используемая версия интерфейса командной строки (CLI).

Функция не собирает личные данные, например имена пользователей и их адреса электронной почты. Она не проверяет код и не извлекает данные уровня проекта, которые могут считаться конфиденциальными, например имена или репозиторий (если они заданы в файле project.json). Мы хотим узнать, как используются средства, а не что вы создаете с их помощью. Если вы обнаружили, что собираются конфиденциальные данные, это следствие ошибки. [Сообщите о проблеме](https://github.com/dotnet/cli/issues), и она будет исправлена.

##<a name="license"></a>Лицензия

Платформа .NET Core распространяется корпорацией Майкрософт на условиях [ЛИЦЕНЗИОННОГО СОГЛАШЕНИЯ НА ИСПОЛЬЗОВАНИЕ БИБЛИОТЕКИ MICROSOFT .NET](https://aka.ms/dotnet-core-eula). Использование телеметрии оговорено в его разделе ДАННЫЕ, который приводится ниже.

Эта же лицензия распространяется на [пакеты NuGet .NET](https://www.nuget.org/profiles/dotnetframework), для которых, однако, телеметрия не включена (см. разделе [Область действия](#scope) выше).

```text
2.      DATA.  The software may collect information about you and your use of
the software, and send that to Microsoft. Microsoft may use this information
to improve our products and services. You can learn more about data collection
and use in the help documentation and the privacy statement at
http://go.microsoft.com/fwlink/?LinkId=528096 . Your use of the software
operates as your consent to these practices.
```

## <a name="disclosure"></a>Раскрытие информации

При первом выполнении одной из команд (например, `dotnet restore`) средства .NET Core выводят приведенный ниже текст. Именно таким образом корпорация Майкрософт уведомляет вас о сборе данных. Кроме того, при первом выполнении команды происходит начальное заполнение кэша NuGet библиотеками из пакета SDK для .NET Core, что позволяет избежать отправки запросов в NuGet.org (или другой канал NuGet) для получения этих библиотек.

```text
Welcome to .NET Core!
---------------------

Learn more about .NET Core @ https://aka.ms/dotnet-docs. Use dotnet --help to
see available commands or go to https://aka.ms/dotnet-cli-docs.

Telemetry
---------

The .NET Core tools collect usage data in order to improve your experience.
The data is anonymous and does not include commandline arguments. The data is
collected by Microsoft and shared with the community.

You can opt out of telemetry by setting a DOTNET_CLI_TELEMETRY_OPTOUT
environment variable to 1 using your favorite shell.

You can read more about .NET Core tools telemetry @ https://aka.ms/dotnet-cli-
telemetry.

Configuring...
--------------

A command is running to initially populate your local package cache, to
improve restore speed and enable offline access. This command will take up to
a minute to complete and will only happen once. 
```



<!--HONumber=Feb17_HO2-->


