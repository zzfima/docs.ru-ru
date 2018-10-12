---
title: Руководство по .NET Core
description: .NET Core — это модульная высокопроизводительная реализация .NET для создания приложений Windows, Linux и Mac. Для начала получите дополнительную информацию о .NET Core.
author: richlander
ms.author: mairaw
ms.date: 08/01/2018
ms.custom: updateeachrelease
ms.openlocfilehash: b302b6fc7e097a811c718d2244f603246cb5c259
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49121042"
---
# <a name="net-core-guide"></a>Руководство по .NET Core

[.NET Core](about.md) — это универсальная платформа разработки с [открытым кодом](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT), которую поддерживает корпорация Майкрософт и сообщество .NET на сайте [GitHub](https://github.com/dotnet/core). Она является кроссплатформенной, поддерживает Windows, macOS и Linux, и может использоваться на устройствах, в облаке и в приложениях Интернета вещей.

Дополнительные сведения о среде .NET Core, включая ее характеристики, поддерживаемые языки и платформы, а также основные API-интерфейсы, см. в [этой статье](about.md).

Просмотрите [руководства по .NET Core](tutorials/index.md), чтобы узнать, как создать простое приложение .NET Core. На создание и запуск первого приложения потребуется буквально несколько минут. Если вы хотите опробовать .NET Core в браузере, ознакомьтесь [кратким руководством по C#](https://docs.microsoft.com/dotnet/csharp/quick-starts/numbers-in-csharp).

## <a name="download-net-core-21"></a>Скачивание .NET Core 2.1

Скачайте [пакет SDK для .NET Core 2.1](https://www.microsoft.com/net/download), чтобы опробовать .NET Core на компьютере под управлением Windows, macOS или Linux. Если вы предпочитаете использовать контейнеры Docker, посетите страницу [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/).

Если вам нужна другая версия .NET Core, все версии доступны на [странице скачиваемых файлов .NET Core](https://www.microsoft.com/net/download/archives).

## <a name="net-core-21"></a>.NET Core 2.1

[.NET Core 2.1](whats-new/dotnet-core-2-1.md) — последняя версия .NET Core. Новые возможности включают в себя глобальные средства, высокопроизводительные интерфейсы API (например, <xref:System.Span%601?displayProperty=nameWithType>), многоуровневую JIT-компиляцию, улучшение производительности [сборки](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/) и [выполнения](https://blogs.msdn.microsoft.com/dotnet/2018/04/18/performance-improvements-in-net-core-2-1/), а также поддержку Alpine и ARM32.

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
