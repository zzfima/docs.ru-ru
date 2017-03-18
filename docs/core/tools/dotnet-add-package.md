---
title: "Команда dotnet-add package | Документы Майкрософт"
description: "Команду dotnet-add package удобно использовать для добавления ссылки на пакет NuGet в проект."
keywords: "dotnet-add, CLI, команда CLI, .NET Core"
author: spboyer
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 88e0da69-a5ea-46cc-8b46-5493242b7af9
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 806f4383452cb250f302dc30ab2d59f7e4772026
ms.lasthandoff: 03/07/2017

---
# <a name="dotnet-add-package"></a>dotnet-add package

## <a name="name"></a>Имя

`dotnet-add package` — добавляет ссылку на пакет в файл проекта.

## <a name="synopsis"></a>Краткий обзор

```
dotnet add [project] package <package_name> [-v|--version] [-f|--framework] [-n|--no-restore] [-s|--source] [--package-directory]
dotnet add package [-h|--help]
```

## <a name="description"></a>Описание

`dotnet add package` предоставляет удобный способ для добавления ссылки на пакет в файл проекта. После запуска этой команды выполняется проверка совместимости, чтобы убедиться, что добавляемый пакет совместим со всеми платформами в проекте. Если проверка проходит успешно, выполняется команда восстановления [restore](dotnet-restore.md) и в файл проекта добавляется фрагмент `<PackageReference>`.

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

Файл *ToDo.csproj* теперь содержит фрагмент [`<PackageReference>`](https://docs.microsoft.com/nuget/consume-packages/package-references-in-project-files) для пакета, на который указывает ссылка.

```xml
<PackageReference Include="Newtonsoft.Json">
  <Version>9.0.1</Version>
</PackageReference>
```

## <a name="arguments"></a>Аргументы

`project`

Целевой файл проекта. Если он не указан, команда ищет текущий каталог для него.

`package_name`

Добавляемая ссылка на пакет.

## <a name="options"></a>Параметры

`-h|--help`

Выводит краткую справку по команде.

`-v|--version <VERSION>`

Версия пакета.

`-f|--framework <FRAMEWORK>`

Добавляет ссылку на пакет только при ориентации на конкретную платформу.

`-n|--no-restore`

Добавляет ссылку на пакет без предварительного просмотра восстановления и проверки совместимости.

`-s|--source <SOURCE>`

Указывает конкретный источник пакета NuGet для использования во время операции восстановления.

`--package-directory <PACKAGE_DIRECTORY>`

Восстанавливает пакет в указанный каталог.

## <a name="examples"></a>Примеры

Добавление пакета NuGet `Newtonsoft.Json` в проект:

`dotnet add package Newtonsoft.Json`

Добавление определенной версии пакета в проект:

`dotnet add ToDo.csproj package Microsoft.Azure.DocumentDB.Core -v 1.0.0`

Добавление пакета с помощью определенного источника NuGet:

`dotnet add package Microsoft.AspNetCore.StaticFiles -s https://dotnet.myget.org/F/dotnet-core/api/v3/index.json`

