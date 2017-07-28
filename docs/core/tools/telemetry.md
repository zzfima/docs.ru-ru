---
title: "Сбор телеметрии по инструментам .NET Core | Microsoft Docs"
description: .NET Core
keywords: .NET, .NET Core
author: richlander
ms.author: mairaw
ms.date: 11/16/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 480df976-7568-4df4-9d26-9911357b5a31
ms.translationtype: Human Translation
ms.sourcegitcommit: 6f3dc4235c75d7438f019838cb22192f4dc7c41a
ms.openlocfilehash: b7de81f38c0d4fa259f1c9d8ada675197930e945
ms.contentlocale: ru-ru
ms.lasthandoff: 05/30/2017

---

# Средства телеметрии .NET Core
<a id="net-core-tools-telemetry" class="xliff"></a>

Средства .NET Core включают в себя [функцию телеметрии](https://github.com/dotnet/cli/pull/2145), которая собирает сведения об использовании. Команде разработчиков .NET важно знать, как используются эти средства, чтобы иметь возможность улучшить их.

Данные собираются анонимно и публикуются в сводной форме для использования корпорацией Майкрософт и специалистами сообщества по [лицензии Creative Commons Attribution](https://creativecommons.org/licenses/by/4.0/).

## Область
<a id="scope" class="xliff"></a>

Команда `dotnet` служит для запуска как приложений, так и средств .NET Core. Сама по себе команда `dotnet` не собирает данные телеметрии. Этим занимаются средства .NET Core, которые запускаются с помощью команды `dotnet`.

Команды .NET Core (телеметрия не включена):

- `dotnet`
- `dotnet [path-to-app]`

[Команды](index.md) средств .NET Core (телеметрия включена):

- `dotnet build`
- `dotnet pack`
- `dotnet restore`
- `dotnet run`

## Поведение
<a id="behavior" class="xliff"></a>

Функция телеметрии средств .NET Core по умолчанию включена. Вы можете отказаться от ее использования. Для этого установите переменную среды DOTNET_CLI_TELEMETRY_OPTOUT (например, `export` в macOS и Linux или `set` в Windows) в значение true (например, "true", 1).

## Точки данных
<a id="data-points" class="xliff"></a>

Средство собирает следующие данные:

- используемая команда (например, "build", "restore");
- код выхода команды;
- используемое средство запуска тестов в случае тестового проекта;
- метка времени вызова;
- используемая платформа;
- наличие идентификаторов сред выполнения в узле "runtimes";
- используемая версия интерфейса командной строки (CLI).

Функция не собирает личные данные, например имена пользователей и их адреса электронной почты. Она не проверяет код и не извлекает данные уровня проекта, которые могут считаться конфиденциальными, например имена или репозиторий (если они заданы в файле project.json). Мы хотим узнать, как используются средства, а не что вы создаете с их помощью. Если вы обнаружили, что собираются конфиденциальные данные, это следствие ошибки. [Сообщите о проблеме](https://github.com/dotnet/cli/issues), и она будет исправлена.

## Лицензия
<a id="license" class="xliff"></a>

Платформа .NET Core распространяется корпорацией Майкрософт на условиях [ЛИЦЕНЗИОННОГО СОГЛАШЕНИЯ НА ИСПОЛЬЗОВАНИЕ БИБЛИОТЕКИ MICROSOFT .NET](https://aka.ms/dotnet-core-eula). Использование телеметрии определяется разделом "ДАННЫЕ" этого соглашения, который приведен ниже.

Эта же лицензия распространяется на [пакеты NuGet .NET](https://www.nuget.org/profiles/dotnetframework), для которых, однако, телеметрия не включена (см. разделе [Область действия](#scope) выше).

> 2. Данные Программное обеспечение может собирать сведения о вас и его использовании, а также отправлять эти данные в корпорацию Майкрософт. Корпорация Майкрософт может использовать эти сведения для совершенствования своих продуктов и услуг. Сведения о сборе и использовании данных в справочной документации и заявлении о конфиденциальности см. на странице http://go.microsoft.com/fwlink/?LinkId=528096. Использование этого программного обеспечения рассматривается как согласие на применение ваших данных.

## Раскрытие информации
<a id="disclosure" class="xliff"></a>

При первом выполнении одной из команд (например, `dotnet restore`) средства .NET Core выводят приведенный ниже текст. Именно таким образом корпорация Майкрософт уведомляет вас о сборе данных. Кроме того, при первом выполнении команды происходит начальное заполнение кэша NuGet библиотеками из пакета SDK для .NET Core, что позволяет избежать отправки запросов в NuGet.org (или другой канал NuGet) для получения этих библиотек.

```console
Welcome to .NET Core!
---------------------
Learn more about .NET Core @ https://aka.ms/dotnet-docs. Use dotnet --help to see available commands or go to https://aka.ms/dotnet-cli-docs.

Telemetry
--------------
The .NET Core tools collect usage data in order to improve your experience.
The data is anonymous and does not include command-line arguments. The data is collected by Microsoft and shared with the community.
You can opt out of telemetry by setting a DOTNET_CLI_TELEMETRY_OPTOUT environment variable to 1 using your favorite shell.
You can read more about .NET Core tools telemetry @ https://aka.ms/dotnet-cli-telemetry.

Configuring...
-------------------
A command is running to initially populate your local package cache, to improve restore speed and enable offline access. This command will take up to a minute to complete and will only happen once.
```

