---
title: Руководство по .NET Core
description: .NET Core — это модульная высокопроизводительная реализация .NET для создания приложений Windows, Linux и Mac. Для начала получите дополнительную информацию о .NET Core.
author: richlander
ms.date: 08/01/2018
ms.custom: updateeachrelease
ms.openlocfilehash: 79a0c09074159160dd01b0c7970612f7058cc3fc
ms.sourcegitcommit: a3db1a9eafca89f95ccf361bc1833b47fbb2bb30
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/04/2019
ms.locfileid: "58920627"
---
# <a name="net-core-guide"></a>Руководство по .NET Core

[.NET Core](about.md) — это универсальная платформа разработки с [открытым кодом](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT), которую поддерживает корпорация Майкрософт и сообщество .NET на сайте [GitHub](https://github.com/dotnet/core). Она является кроссплатформенной (поддерживает Windows, macOS и Linux) и может использоваться для создания приложений для устройств, облака и Интернета вещей.

Дополнительные сведения о среде .NET Core, включая ее характеристики, поддерживаемые языки и платформы, а также основные API-интерфейсы, см. в [этой статье](about.md).

Просмотрите [руководства по .NET Core](tutorials/index.md), чтобы узнать, как создать простое приложение .NET Core. На создание и запуск первого приложения потребуется буквально несколько минут. Если вы хотите попробовать поработать с .NET Core в браузере, перейдите на страницу онлайн-руководства [Числа в C#](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml).

## <a name="download-net-core-22"></a>Скачать .NET Core 2.2

Скачайте [пакет SDK для .NET Core 2.2](https://www.microsoft.com/net/download), чтобы опробовать .NET Core на компьютере под управлением Windows, macOS или Linux. Если вы предпочитаете использовать контейнеры Docker, перейдите на страницу [dotnet/core](https://hub.docker.com/_/microsoft-dotnet-core/).

Если вам нужна другая версия .NET Core, все версии доступны на [странице скачиваемых файлов .NET Core](https://www.microsoft.com/net/download/archives).

## <a name="net-core-22"></a>.NET Core 2.2

[.NET Core 2.2](whats-new/dotnet-core-2-2.md) — самая новая версия .NET Core. Ее новые возможности: развертывание с учетом платформ, перехватчики при запуске, проверка подлинности AAD в Azure SQL и поддержка Windows ARM32.

## <a name="create-your-first-application"></a>Создание первого приложения

После установки пакета SDK для .NET Core откройте командную строку. Для создания и запуска приложения C# введите следующие команды `dotnet`.

```console
dotnet new console
dotnet run
```

Должны выводиться следующие данные:

```console
Hello World!
```

## <a name="support"></a>Поддержка

Поддержкой платформы .NET Core занимается [корпорация Майкрософт](https://www.microsoft.com/net/support/policy). Поддержка предоставляется для операционных систем Windows, macOS и Linux. Для повышения безопасности и качества платформа обновляется несколько раз в год, обычно ежемесячно.

Двоичные дистрибутивы .NET Core собираются и тестируются в Azure на серверах Майкрософт и поддерживаются наравне с другими продуктами Майкрософт.

[Red Hat поддерживает .NET Core](http://redhatloves.net/) в операционной системе Red Hat Enterprise Linux (RHEL). Red Hat собирает .NET Core из исходного кода и публикует сборки на сайте [Red Hat Software Collections](https://developers.redhat.com/products/softwarecollections/overview/). Red Hat и Майкрософт совместно занимаются обеспечением беспроблемной работы .NET Core в RHEL.
