---
title: "Команда dotnet-nuget-push | Пакет SDK для .NET Core"
description: "Команда dotnet-nuget-push отправляет пакет на сервер и публикует его."
keywords: "dotnet-nuget-push, CLI, команда CLI, .NET Core"
author: karann-msft
ms.author: mairaw
manager: wpickett
ms.date: 11/11/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: f54d9adf-94f8-41cc-bb52-42f7ca3be6ff
translationtype: Human Translation
ms.sourcegitcommit: 1a84c694945fe0c77468eb77274ab46618bccae6
ms.openlocfilehash: 04369a7f478cc77b6351f2fbee05d4e4ec8b19fb

---

#<a name="dotnet-nuget-push"></a>dotnet-nuget-push

[!INCLUDE[preview-warning](../../../includes/warning.md)]

## <a name="name"></a>Имя 
`dotnet-nuget-push` — отправляет пакет на сервер и публикует его. 

## <a name="synopsis"></a>Краткий обзор

`dotnet nuget push [<package>] [--help] [--source] [--symbols-source] 
    [--timeout] [--api-key] [--symbol-api-key] [--disable-buffering] [--no-symbols] 
    [--force-english-output] [--config-file] [--verbosity]`

## <a name="description"></a>Описание

Команда `dotnet nuget push` отправляет пакет на сервер и публикует его. Команда push использует сервер и учетные данные, указанные в системном файле конфигурации NuGet или цепочке файлов конфигурации. См. дополнительные сведения о файлах конфигурации в статье о [настройке поведения NuGet](https://docs.nuget.org/ndocs/consume-packages/configuring-nuget-behavior). Конфигурацию NuGet по умолчанию можно получить, загрузив файл *%AppData%\NuGet\NuGet.config* (Windows) или *$HOME/.local/share* (Linux и macOS). Затем нужно загрузить все файлы *nuget.config* или *.nuget\nuget.config*, начиная с корневого каталога диска и заканчивая текущим каталогом.

## <a name="options"></a>Параметры

`-h|--help`

Выводит краткую справку по команде.  

`-s|--source <SOURCE>`

Определяет URL-адрес сервера. Этот параметр является обязательным, если значение параметра конфигурации DefaultPushSource задано в файле конфигурации NuGet.

`--symbols-source <SOURCE>`

Указывает URL-адрес сервера символов.

`-t|--timeout <TIMEOUT>`

Указывает время ожидания для передачи на сервер в секундах. Значение по умолчанию — 300 секунд (5 минут). Если указать значение 0, будет использоваться значение по умолчанию.

`-k|--api-key <API_KEY>`

Ключ API для сервера.

`--symbol-api-key <API_KEY>`

Ключ API для сервера символов.

`-d|--disable-buffering`

Отключает буферизацию при передаче данных на сервер HTTP(S), чтобы снизить использование памяти.

`-n|--no-symbols`

Не передает символы (даже если они присутствуют).

`--force-english-output`

Принудительно отображает все зарегистрированные выходные данные на английском языке. Кроме возможности создавать выходные данные на английском языке на компьютере, на который не используется этот язык, этот параметр обеспечивает согласованность между платформам. Это очень удобная функция для автоматизированных средств, которые ищут текст в журналах.

`--config-file <FILE>`

Файл конфигурации NuGet используется специально для этой команды, заменяя другие файлы конфигурации, обнаруженные стандартным процессом поиска и построения цепочки. Путь может быть как абсолютным, так и относительным.
См. дополнительные сведения о файлах конфигурации в статье о [настройке поведения NuGet](https://docs.nuget.org/ndocs/consume-packages/configuring-nuget-behavior). 

`--verbosity <LEVEL>`

Отображает эти сведения в выходных данных. Доступные уровни: `normal`, `quiet` или `detailed`.

## <a name="examples"></a>Примеры

Отправляет foo.nupkg в источник push-уведомлений по умолчанию, предоставляя ключ API.

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a`

Отправляет foo.nupkg в пользовательский источник push-уведомлений `http://customsource`, предоставляя ключ API.

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s http://customsource/` 

Отправляет foo.nupkg в источник push-уведомлений по умолчанию.

`dotnet nuget push foo.nupkg` 

Отправляет foo.symbols.nupkg в источник символов по умолчанию.

`dotnet nuget push foo.symbols.nupkg`

Отправляет foo.nupkg в источник push-уведомлений по умолчанию, указав время ожидания 360 секунд.

`dotnet nuget push foo.nupkg --timeout 360`

Отправляет все файлы NUPKG из текущего каталога в источник push-уведомлений по умолчанию.

`dotnet nuget push *.nupkg`

Отправляет все файлы NUPKG из текущего каталога в источник push-уведомлений по умолчанию, указав собственный файл конфигурации *./config/My.Config*.

`dotnet nuget push *.nupkg --config-file ./config/My.Config`

Отправляет все файлы NUPKG из текущего каталога в источник push-уведомлений по умолчанию с максимальным уровнем детализации.

`dotnet nuget push *.nupkg --verbosity detailed`



<!--HONumber=Nov16_HO3-->


