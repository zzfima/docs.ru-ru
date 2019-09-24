---
title: Использование Управление пакетами с F# для Azure
description: Использование пакет или NuGet для управления F# зависимостями Azure
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 4aa32ace91f30d0e43b9c40067f5f0f456cc4069
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2019
ms.locfileid: "71214229"
---
# <a name="package-management-for-f-azure-dependencies"></a>Управление пакетами для зависимостей F# в Azure

Получение пакетов для разработки Azure несложно при использовании диспетчера пакетов. Два варианта — [пакет](https://fsprojects.github.io/Paket/) и [NuGet](https://www.nuget.org/).

## <a name="using-paket"></a>Использование пакет

Если вы используете [пакет](https://fsprojects.github.io/Paket/) в качестве диспетчера зависимостей, вы можете использовать это `paket.exe` средство для добавления зависимостей Azure. Например:

```console
> paket add nuget WindowsAzure.Storage
```

Или, если вы используете [Mono](https://www.mono-project.com/) для кросс-платформенной разработки .NET:

```console
> mono paket.exe add nuget WindowsAzure.Storage
```

При этом будет `WindowsAzure.Storage` добавлен набор зависимостей пакета для проекта в текущем каталоге, `paket.dependencies` изменен файл и загружен пакет. Если вы ранее настроили зависимости или работаете с проектом, в котором зависимости были настроены другим разработчиком, вы можете разрешить и установить зависимости в локальной среде следующим образом:

```console
> paket install
```

Или, для разработки Mono:

```console
> mono paket.exe install
```

Вы можете обновить все зависимости пакета до последней версии следующим образом:

```console
> paket update
```

Или, для разработки Mono:

```console
> mono paket.exe update
```

## <a name="using-nuget"></a>Использование NuGet

Если вы используете [NuGet](https://www.nuget.org/) в качестве диспетчера зависимостей, это `nuget.exe` средство можно использовать для добавления зависимостей Azure. Например:

```console
> nuget install WindowsAzure.Storage -ExcludeVersion
```

Или, для разработки Mono:

```console
> mono nuget.exe install WindowsAzure.Storage -ExcludeVersion
```

Это приведет к `WindowsAzure.Storage` добавлению набора зависимостей пакета для проекта в текущем каталоге и загрузке пакета. Если вы ранее настроили зависимости или работаете с проектом, в котором зависимости были настроены другим разработчиком, вы можете разрешить и установить зависимости в локальной среде следующим образом:

```console
> nuget restore
```

Или, для разработки Mono:

```console
> mono nuget.exe restore
```

Вы можете обновить все зависимости пакета до последней версии следующим образом:

```console
> nuget update
```

Или, для разработки Mono:

```console
> mono nuget.exe update
```

## <a name="referencing-assemblies"></a>Ссылки на сборки

Чтобы использовать пакеты в F# скрипте, необходимо сослаться на сборки, содержащиеся в пакетах, с помощью `#r` директивы. Например:

```fsharp
> #r "packages/WindowsAzure.Storage/lib/net40/Microsoft.WindowsAzure.Storage.dll"
```

Как видите, необходимо указать относительный путь к библиотеке DLL и полное имя библиотеки DLL, которое может не совпадать с именем пакета. Путь будет содержать версию платформы и, возможно, номер версии пакета. Чтобы найти все установленные сборки, можно использовать в командной строке Windows нечто подобное:

```console
> cd packages/WindowsAzure.Storage
> dir /s/b *.dll
```

Или в оболочке UNIX примерно так:

```console
> find packages/WindowsAzure.Storage -name "*.dll"
```

При этом будут предоставлены пути к установленным сборкам. После этого можно выбрать правильный путь к версии платформы.
