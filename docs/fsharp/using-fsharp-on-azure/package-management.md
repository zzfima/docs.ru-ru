---
title: 'С помощью пакета управления с помощью F # для Azure'
description: 'Используйте Paket или Nuget для управления зависимостями Azure F #'
author: sylvanc
ms.author: phcart
ms.date: 09/20/2016
ms.topic: conceptual
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: da6938c6ee29292571f4269c68a9148c13738422
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="package-management-for-f-azure-dependencies"></a>Управление пакетами для зависимостей F# в Azure

Получение пакетов для разработки Azure удобно при использовании диспетчера пакетов. Ниже приведены два варианта [Paket](https://fsprojects.github.io/Paket/) и [NuGet](https://www.nuget.org/).

## <a name="using-paket"></a>С помощью Paket

Если вы используете [Paket](https://fsprojects.github.io/Paket/) качестве менеджера зависимостей можно использовать `paket.exe` средство для добавления зависимости Azure. Пример:

    > paket add nuget WindowsAzure.Storage

Или, если вы используете [моно](https://www.mono-project.com/) для кросс платформенной разработки .NET:

    > mono paket.exe add nuget WindowsAzure.Storage

При этом будет добавлено `WindowsAzure.Storage` в набор зависимых элементов пакета для проекта в текущем каталоге, измените `paket.dependencies` файла и загрузки пакета. Если вы ранее настроили зависимости или работы с проектом где зависимости были настроены с другим разработчиком, можно решить и установка зависимостей локально следующим образом:

    > paket install

Или моно разработки:

    > mono paket.exe install

Можно обновить все зависимости пакета до последней версии следующим образом:

    > paket update

Или моно разработки:

    > mono paket.exe update

## <a name="using-nuget"></a>С помощью Nuget

Если вы используете [NuGet](https://www.nuget.org/) качестве менеджера зависимостей можно использовать `nuget.exe` средство для добавления зависимости Azure. Пример:

    > nuget install WindowsAzure.Storage -ExcludeVersion

Или моно разработки:

    > mono nuget.exe install WindowsAzure.Storage -ExcludeVersion

При этом будет добавлено `WindowsAzure.Storage` в набор зависимых элементов пакета для проекта в текущем каталоге и загрузки пакета. Если вы ранее настроили зависимости или работы с проектом где зависимости были настроены с другим разработчиком, можно решить и установка зависимостей локально следующим образом:

    > nuget restore 

Или моно разработки:

    > mono nuget.exe restore

Можно обновить все зависимости пакета до последней версии следующим образом:

    > nuget update

Или моно разработки:

    > mono nuget.exe update

## <a name="referencing-assemblies"></a>Ссылки на сборки

Чтобы использовать пакеты в скрипте F #, необходимо ссылаться на сборки, включенные в пакеты, с помощью `#r` директивы. Пример:

    > #r "packages/WindowsAzure.Storage/lib/net40/Microsoft.WindowsAzure.Storage.dll"

Как видите, необходимо будет указать относительный путь к DLL и полное имя библиотеки DLL, которые могут не соответствовать точно совпадает с именем пакета. Путь будет содержать версию платформы и, возможно, номер версии пакета. Чтобы найти всех установленных сборок, можно использовать нечто подобное командной строке Windows:

    > cd packages/WindowsAzure.Storage
    > dir /s/b *.dll

Или оболочки Unix, примерно следующим образом:

    > find packages/WindowsAzure.Storage -name "*.dll"

Это позволит получить пути к установленных сборок. После этого можно выбрать правильный путь для вашей версии framework.
