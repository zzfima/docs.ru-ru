---
title: С помощью пакета управления с помощью F# для Azure
description: Использовать Paket или Nuget для управления F# зависимости Azure
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: fd9c4a15ab0741d44d6d5cf909b7219d310affb0
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2018
ms.locfileid: "33566979"
---
# <a name="package-management-for-f-azure-dependencies"></a>Управление пакетами для зависимостей F# в Azure

Получение пакетов для разработки для Azure прост, при использовании диспетчера пакетов. Ниже приведены два варианта [Paket](https://fsprojects.github.io/Paket/) и [NuGet](https://www.nuget.org/).

## <a name="using-paket"></a>С помощью Paket

Если вы используете [Paket](https://fsprojects.github.io/Paket/) как ваш Диспетчер зависимостей, вы можете использовать `paket.exe` средство, чтобы добавить зависимости Azure. Пример:

    > paket add nuget WindowsAzure.Storage

Или, если вы используете [Mono](https://www.mono-project.com/) для кросс Платформенная разработка .NET:

    > mono paket.exe add nuget WindowsAzure.Storage

При этом будет добавлено `WindowsAzure.Storage` в набор зависимых элементов пакета для проекта в текущем каталоге, измените `paket.dependencies` файл и загрузить пакет. Если вы ранее настроили зависимости или при работе с проектом, где зависимости были настроены с другим разработчиком, можно решить и установите зависимости локально следующим образом:

    > paket install

Или, для разработки Mono:

    > mono paket.exe install

Вы можете обновить все зависимости пакета до последней версии следующим образом:

    > paket update

Или, для разработки Mono:

    > mono paket.exe update

## <a name="using-nuget"></a>С помощью Nuget

Если вы используете [NuGet](https://www.nuget.org/) как ваш Диспетчер зависимостей, вы можете использовать `nuget.exe` средство, чтобы добавить зависимости Azure. Пример:

    > nuget install WindowsAzure.Storage -ExcludeVersion

Или, для разработки Mono:

    > mono nuget.exe install WindowsAzure.Storage -ExcludeVersion

При этом будет добавлено `WindowsAzure.Storage` в набор зависимых элементов пакета для проекта в текущем каталоге и загрузки пакета. Если вы ранее настроили зависимости или при работе с проектом, где зависимости были настроены с другим разработчиком, можно решить и установите зависимости локально следующим образом:

    > nuget restore 

Или, для разработки Mono:

    > mono nuget.exe restore

Вы можете обновить все зависимости пакета до последней версии следующим образом:

    > nuget update

Или, для разработки Mono:

    > mono nuget.exe update

## <a name="referencing-assemblies"></a>Ссылки на сборки

Чтобы использовать пакеты в вашей F# скрипта, необходимо сослаться на сборки, включенные в пакеты, с помощью `#r` директива. Пример:

    > #r "packages/WindowsAzure.Storage/lib/net40/Microsoft.WindowsAzure.Storage.dll"

Как вы видите, вам потребуется указать относительный путь к DLL и полное имя библиотеки DLL, которые могут не соответствовать точно совпадает с именем пакета. Этот путь будет содержать версии платформы и, возможно, номер версии пакета. Чтобы найти всех установленных сборок, можно использовать примерно следующее в командной строке Windows:

    > cd packages/WindowsAzure.Storage
    > dir /s/b *.dll

Или в оболочке Unix, примерно следующим образом:

    > find packages/WindowsAzure.Storage -name "*.dll"

Это позволит получить пути к установленными сборками. После этого можно выбрать правильный путь для вашей версии платформы.
