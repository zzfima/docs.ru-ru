---
title: Руководство по .NET Core
description: .NET Core — это модульная высокопроизводительная реализация .NET для создания приложений Windows, Linux и Mac. Для начала получите дополнительную информацию о .NET Core.
author: richlander
ms.date: 12/04/2019
ms.custom: updateeachrelease
ms.openlocfilehash: b2622dba53d64c9dcf58e852d57de117fe79eb2e
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837016"
---
# <a name="net-core-guide"></a>Руководство по .NET Core

[.NET Core](about.md) — это универсальная платформа разработки с [открытым кодом](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT), которую поддерживает корпорация Майкрософт и сообщество .NET на сайте [GitHub](https://github.com/dotnet/core). Она является кроссплатформенной (поддерживает Windows, macOS и Linux) и может использоваться для создания приложений для устройств, облака и Интернета вещей.

Дополнительные сведения о среде .NET Core, включая ее характеристики, поддерживаемые языки и платформы, а также основные API-интерфейсы, см. в [этой статье](about.md).

Просмотрите [руководства по .NET Core](tutorials/index.md), чтобы узнать, как создать простое приложение .NET Core. На создание и запуск первого приложения потребуется буквально несколько минут. Если вы хотите попробовать поработать с .NET Core в браузере, перейдите на страницу онлайн-руководства [Числа в C#](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml).

## <a name="download-net-core"></a>Скачать .NET Core

Скачайте [пакет SDK для .NET Core](https://www.microsoft.com/net/download), чтобы поработать с .NET Core на компьютере Windows, macOS или Linux. Если вы предпочитаете использовать контейнеры Docker, перейдите на страницу[.NET Core Docker Hub](https://hub.docker.com/_/microsoft-dotnet-core/).

Если вам нужна другая версия .NET Core, все версии доступны на [странице скачиваемых файлов .NET Core](https://dotnet.microsoft.com/download/dotnet-core).

## <a name="net-core-31"></a>.NET Core 3.1

.NET Core 3.1 является последней версией. В нее входят незначительные улучшения версии .NET Core 3.0. Однако .NET Core 3.1 является долгосрочным поддерживаемым выпуском. Дополнительные сведения о выпуске .NET Core 3.1 см. в разделе [Новые возможности .NET Core 3.1](./whats-new/dotnet-core-3-1.md).

## <a name="create-your-first-application"></a>Создание первого приложения

После установки пакета SDK для .NET Core откройте командную строку. Для создания и запуска приложения C# введите следующие команды `dotnet`:

```dotnetcli
dotnet new console
dotnet run
```

Должны выводиться следующие данные:

```output
Hello World!
```

## <a name="support"></a>Поддержка

Поддержку платформы .NET Core реализует [корпорация Майкрософт](https://dotnet.microsoft.com/platform/support/policy). Поддержка предоставляется для операционных систем Windows, macOS и Linux. Для повышения безопасности и качества платформа обновляется несколько раз в год, обычно ежемесячно.

Двоичные дистрибутивы .NET Core собираются и тестируются в Azure на серверах Майкрософт и поддерживаются наравне с другими продуктами Майкрософт.

[Red Hat поддерживает .NET Core](http://redhatloves.net/) в операционной системе Red Hat Enterprise Linux (RHEL). Red Hat собирает .NET Core из исходного кода и публикует сборки на сайте [Red Hat Software Collections](https://developers.redhat.com/products/softwarecollections/overview/). Red Hat и Майкрософт совместно занимаются обеспечением беспроблемной работы .NET Core в RHEL.
