---
title: "Команда dotnet-add package — CLI .NET Core | Документы Майкрософт"
description: "Команду dotnet-add package удобно использовать для добавления ссылки на пакет NuGet в проект."
keywords: "dotnet-add, CLI, команда CLI, .NET Core"
author: spboyer
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 88e0da69-a5ea-46cc-8b46-5493242b7af9
translationtype: Human Translation
ms.sourcegitcommit: dff752a9d31ec92b113dae9eed20cd72faf57c84
ms.openlocfilehash: 41b46e879056d385ceb3abaec27db974cab812e3
ms.lasthandoff: 03/22/2017

---

# <a name="dotnet-add-package"></a>dotnet-add package

## <a name="name"></a>Имя

`dotnet-add package` — добавляет ссылку на пакет в файл проекта.

## <a name="synopsis"></a>Краткий обзор

`dotnet add [<PROJECT>] package <PACKAGE_NAME> [-v|--version] [-f|--framework] [-n|--no-restore] [-s|--source] [--package-directory] [-h|--help]`

## <a name="description"></a>Описание

Команда `dotnet add package` предоставляет удобный способ для добавления ссылки на пакет в файл проекта. После запуска этой команды выполняется проверка совместимости, чтобы убедиться, что пакет совместим со всеми платформами в проекте. Если проверка проходит успешно, в файл проекта добавляется элемент `<PackageReference>` и выполняется команда [dotnet restore](dotnet-restore.md).

Например, при добавлении `Newtonsoft.Json` в *ToDo.csproj* создаются выходные данные примерно следующего вида:

```
Microsoft (R) Build Engine version 15.1.545.13942
Copyright (C) Microsoft Corporation. All rights reserved.

Writing /var/folders/gj/1mgg_4jx7mbdqbhw1kgcpcjr0000gn/T/tmpm0kTMD.tmp
info : Adding PackageReference for package 'Newtonsoft.Json' into project 'ToDo.csproj'.
log  : Restoring packages for ToDo.csproj...
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json 119ms
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/9.0.1/newtonsoft.json.9.0.1.nupkg
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/9.0.1/newtonsoft.json.9.0.1.nupkg 27ms
info : Package 'Newtonsoft.Json' is compatible with all the specified frameworks in project 'ToDo.csproj'.
info : PackageReference for package 'Newtonsoft.Json' version '9.0.1' added to file 'ToDo.csproj'.
```

Файл *ToDo.csproj* теперь содержит элемент [`<PackageReference>`](https://docs.microsoft.com/nuget/consume-packages/package-references-in-project-files) для пакета, на который указывает ссылка.

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

