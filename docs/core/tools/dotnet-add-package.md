---
title: "Команда dotnet add package — CLI .NET Core"
description: "Команду dotnet add package удобно использовать для добавления ссылки на пакет NuGet в проект."
author: mairaw
ms.author: mairaw
ms.date: 08/11/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload: dotnetcore
ms.openlocfilehash: 3b372b55cbdd8e0e6cc6a6b1089915e0da802489
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="dotnet-add-package"></a>dotnet add package

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet add package` — добавляет ссылку на пакет в файл проекта.

## <a name="synopsis"></a>Краткий обзор

`dotnet add [<PROJECT>] package <PACKAGE_NAME> [-h|--help] [-v|--version] [-f|--framework] [-n|--no-restore] [-s|--source] [--package-directory]`

## <a name="description"></a>Описание:

Команда `dotnet add package` предоставляет удобный способ для добавления ссылки на пакет в файл проекта. После запуска этой команды выполняется проверка совместимости, чтобы убедиться, что пакет совместим со всеми платформами в проекте. Если проверка проходит успешно, в файл проекта добавляется элемент `<PackageReference>` и выполняется команда [dotnet restore](dotnet-restore.md).

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

Например, при добавлении `Newtonsoft.Json` в *ToDo.csproj* создаются выходные данные примерно следующего вида:

```
  Writing C:\Users\mairaw\AppData\Local\Temp\tmp95A8.tmp
info : Adding PackageReference for package 'Newtonsoft.Json' into project 'C:\projects\ToDo\ToDo.csproj'.
log  : Restoring packages for C:\projects\ToDo\ToDo.csproj...
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json 235ms
info : Package 'Newtonsoft.Json' is compatible with all the specified frameworks in project 'C:\projects\ToDo\ToDo.csproj'.
info : PackageReference for package 'Newtonsoft.Json' version '10.0.3' added to file 'C:\projects\ToDo\ToDo.csproj'.
```

Файл *ToDo.csproj* теперь содержит элемент [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) для пакета, на который указывает ссылка.

```xml
<PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
```

## <a name="arguments"></a>Аргументы

`PROJECT`

Указывает файл проекта. Если он не указан, команда ищет текущий каталог для него.

`PACKAGE_NAME`

Добавляемая ссылка на пакет.

## <a name="options"></a>Параметры

`-h|--help`

Выводит краткую справку по команде.

`-v|--version <VERSION>`

Версия пакета.

`-f|--framework <FRAMEWORK>`

Добавляет ссылку на пакет только при ориентации на конкретную [платформу](../../standard/frameworks.md).

`-n|--no-restore`

Добавляет ссылку на пакет без предварительного просмотра восстановления и проверки совместимости.

`-s|--source <SOURCE>`

Указывает конкретный источник пакета NuGet во время операции восстановления.

`--package-directory <PACKAGE_DIRECTORY>`

Восстанавливает пакет в указанный каталог.

## <a name="examples"></a>Примеры

Добавление пакета NuGet `Newtonsoft.Json` в проект:

`dotnet add package Newtonsoft.Json`

Добавление определенной версии пакета в проект:

`dotnet add ToDo.csproj package Microsoft.Azure.DocumentDB.Core -v 1.0.0`

Добавление пакета с помощью определенного источника NuGet:

`dotnet add package Microsoft.AspNetCore.StaticFiles -s https://dotnet.myget.org/F/dotnet-core/api/v3/index.json`
