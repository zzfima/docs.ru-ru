---
title: Телеметрия средств интерфейса командной строки для .NET Core
description: Сведения о функциях телеметрии средств .NET Core, позволяющих собирать сведения об использовании для анализа, а также о собираемых данных и способе отключения этих функций.
author: richlander
ms.author: mairaw
ms.date: 08/04/2017
ms.openlocfilehash: 4c04867f5db512ef53c23ec41ea66db570a82021
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33216087"
---
# <a name="net-core-cli-tools-telemetry"></a>Телеметрия средств интерфейса командной строки для .NET Core

[Пакет SDK для .NET Core](index.md) включает в себя [функцию телеметрии](https://github.com/dotnet/cli/pull/2145), которая собирает сведения об использовании. Команде разработчиков .NET важно знать, как используются эти средства, чтобы иметь возможность улучшить их. Дополнительные сведения см. в разделе [Что мы узнали благодаря данным телеметрии пакета SDK для .NET Core](https://blogs.msdn.microsoft.com/dotnet/2017/07/21/what-weve-learned-from-net-core-sdk-telemetry/).

Данные собираются анонимно и публикуются в сводной форме для использования корпорацией Майкрософт и сообществом по [лицензии Creative Commons Attribution](https://creativecommons.org/licenses/by/4.0/). 

## <a name="scope"></a>Область

Команда `dotnet` служит для запуска как приложений, так и интерфейса командной строки .NET Core. Сама по себе команда `dotnet` не собирает данные телеметрии. Этим занимаются команды интерфейса командной строки .NET Core, которые выполняются с помощью команды `dotnet`.

Телеметрия *не включена*, если команда `dotnet` используется без дополнительных команд:

- `dotnet`
- `dotnet [path-to-app]`

Телеметрия *включена* при использовании [команд интерфейса командной строки .NET Core](index.md), например:

- `dotnet build`
- `dotnet pack`
- `dotnet restore`
- `dotnet run`


## <a name="behavior"></a>Поведение

Функция телеметрии средств интерфейса командной строки .NET Core по умолчанию включена. Чтобы отключить ее, присвойте переменной среды `DOTNET_CLI_TELEMETRY_OPTOUT` значение `1` или `true`.

## <a name="data-points"></a>Точки данных

Средство собирает следующие данные:

- метка времени вызова&#8224;
- вызываемая команда (например, build)&#8224;
- состоящий из трех октетов IP-адрес, используемый для определения географического местоположения&#8224;
- `ExitCode` команды;
- средство выполнения тестов (для тестовых проектов);
- операционная система и ее версия&#8224;
- наличие идентификаторов сред выполнения в узле runtimes;
- версия пакета SDK для .NET Core&#8224.

&#8224;Эта метрика публикуется.

Начиная с версии .NET Core SDK 2.0, собираются новые точки данных:

- аргументы и параметры команды `dotnet`: собираются только известные аргументы и параметры (но не произвольные строки);
- выполняется ли пакет SDK в контейнере;
- целевые платформы;
- хэшированный MAC-адрес: криптографически (SHA256) анонимный и уникальный идентификатор компьютера; эта метрика не публикуется;
- хэшированный текущий рабочий каталог.

Функция не собирает личные данные, например имена пользователей и их адреса электронной почты. Она не проверяет код и не извлекает конфиденциальные данные уровня проекта, например имена и репозиторий. Данные отправляются по защищенному протоколу на серверы Майкрософт с помощью технологии [Microsoft Azure Application Insights](https://azure.microsoft.com/services/application-insights/), хранятся в режиме ограниченного доступа и публикуются из защищенных систем [хранилища Azure](https://azure.microsoft.com/services/storage/) с соблюдением строгих мер безопасности.

Мы хотим узнать, как используются средства и правильно ли они работают, а не что вы создаете с их помощью. Если у вас есть подозрения, что функция телеметрии собирает конфиденциальные данные или что мы обрабатываем данные небезопасным либо неподобающим образом, [отправьте сообщение о проблеме в репозитории dotnet/cli](https://github.com/dotnet/cli/issues) для изучения.

## <a name="published-data"></a>Опубликованные данные

Данные публикуются ежеквартально и доступны на странице [данных по использованию пакета SDK для .NET](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md). Файл данных содержит следующие столбцы:
- Метка времени
- Occurrences&#8224;
- Команда
- Geography&#8225;
- OSFamily
- RuntimeID
- OSVersion
- SDKVersion

&#8224;В столбце *Occurrences* приводится совокупное число раз, которое команда использовалась для метрики соответствующей строки в указанный день. 

&#8225;В столбце *Geography*, как правило, содержится название страны. В некоторых случаях в этом столбце может указываться Антарктида, либо потому что исследователи используют .NET Core в Антарктиде, либо из-за неправильных сведений о расположении.

### <a name="example"></a>Пример

| Метка времени      | Occurrences | Команда | Geography | OSFamily | RuntimeID     | OSVersion | SDKVersion |
| -------------- | ----------- | ------- | --------- | -------- | ------------- | --------- | ---------- |
| 4/16/2017 0:00 | 8           | запуск     | Уганда    | Darwin   | osx.10.12-x64 | 10.12     | 1.0.1      |

### <a name="datasets"></a>Наборы данных

[2016 — КВ3](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2016-q3.tsv)  
[2016 — КВ4](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2016-q4.tsv)  
[2017 — КВ1](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q1.tsv)  
[2017 — КВ2](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q2.tsv)

Дополнительные наборы данных публикуются с помощью стандартного формата URL-адресов. Замените `<YEAR>` на год, а `<QUARTER>` — на квартал (используйте `1`, `2`, `3` или `4`). Файлы имеют формат значений с разделением знаками табуляции (*TSV*). 

```
https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-<YEAR>-q<QUARTER>.tsv
```

## <a name="license"></a>Лицензия

Платформа .NET Core распространяется корпорацией Майкрософт на условиях [ЛИЦЕНЗИОННОГО СОГЛАШЕНИЯ НА ИСПОЛЬЗОВАНИЕ БИБЛИОТЕКИ MICROSOFT .NET](https://aka.ms/dotnet-core-eula). Использование телеметрии определяется разделом "ДАННЫЕ" этого соглашения, который приведен ниже.

Эта же лицензия распространяется на [пакеты NuGet .NET](https://www.nuget.org/profiles/dotnetframework), для которых, однако, телеметрия не включена (см. раздел [Область действия](#scope)).

> 2. Данные Программное обеспечение может собирать сведения о вас и его использовании, а также отправлять эти данные в корпорацию Майкрософт. Корпорация Майкрософт может использовать эти сведения для совершенствования своих продуктов и услуг. Сведения о сборе и использовании данных в справочной документации и заявлении о конфиденциальности см. на странице http://go.microsoft.com/fwlink/?LinkId=528096. Использование этого программного обеспечения рассматривается как согласие на применение ваших данных.

## <a name="disclosure"></a>Раскрытие информации

При первом выполнении одной из команд (например, `dotnet restore`) средства интерфейса командной строки .NET Core выводят приведенный ниже текст. Он может немного отличаться в зависимости от используемой версии пакета SDK. Именно таким образом корпорация Майкрософт уведомляет вас о сборе данных.

```console
Welcome to .NET Core!
---------------------
Learn more about .NET Core @ https://aka.ms/dotnet-docs. Use dotnet --help to see available commands or go to https://aka.ms/dotnet-cli-docs.
 
Telemetry
--------------
The .NET Core tools collect usage data in order to improve your experience. The data is anonymous and does not include command-line arguments. The data is collected by Microsoft and shared with the community.
You can opt out of telemetry by setting a DOTNET_CLI_TELEMETRY_OPTOUT environment variable to 1 using your favorite shell.
You can read more about .NET Core tools telemetry @ https://aka.ms/dotnet-cli-telemetry.
```

## <a name="see-also"></a>См. также

[Что мы узнали благодаря данным телеметрии пакета SDK для .NET Core](https://blogs.msdn.microsoft.com/dotnet/2017/07/21/what-weve-learned-from-net-core-sdk-telemetry/)  
[Справочные материалы по телеметрии (репозиторий dotnet/cli; ветвь release/2.0.0)](https://github.com/dotnet/cli/tree/release/2.0.0/src/dotnet/Telemetry)   
[Данные по использованию пакета SDK для .NET Core](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md)
