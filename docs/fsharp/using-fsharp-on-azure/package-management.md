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
# <a name="package-management-for-f-azure-dependencies"></a><span data-ttu-id="cb60e-103">Управление пакетами для зависимостей F# в Azure</span><span class="sxs-lookup"><span data-stu-id="cb60e-103">Package Management for F# Azure Dependencies</span></span>

<span data-ttu-id="cb60e-104">Получение пакетов для разработки Azure несложно при использовании диспетчера пакетов.</span><span class="sxs-lookup"><span data-stu-id="cb60e-104">Obtaining packages for Azure development is easy when you use a package manager.</span></span> <span data-ttu-id="cb60e-105">Два варианта — [пакет](https://fsprojects.github.io/Paket/) и [NuGet](https://www.nuget.org/).</span><span class="sxs-lookup"><span data-stu-id="cb60e-105">The two options are [Paket](https://fsprojects.github.io/Paket/) and [NuGet](https://www.nuget.org/).</span></span>

## <a name="using-paket"></a><span data-ttu-id="cb60e-106">Использование пакет</span><span class="sxs-lookup"><span data-stu-id="cb60e-106">Using Paket</span></span>

<span data-ttu-id="cb60e-107">Если вы используете [пакет](https://fsprojects.github.io/Paket/) в качестве диспетчера зависимостей, вы можете использовать это `paket.exe` средство для добавления зависимостей Azure.</span><span class="sxs-lookup"><span data-stu-id="cb60e-107">If you're using [Paket](https://fsprojects.github.io/Paket/) as your dependency manager, you can use the `paket.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="cb60e-108">Например:</span><span class="sxs-lookup"><span data-stu-id="cb60e-108">For example:</span></span>

```console
> paket add nuget WindowsAzure.Storage
```

<span data-ttu-id="cb60e-109">Или, если вы используете [Mono](https://www.mono-project.com/) для кросс-платформенной разработки .NET:</span><span class="sxs-lookup"><span data-stu-id="cb60e-109">Or, if you're using [Mono](https://www.mono-project.com/) for cross-platform .NET development:</span></span>

```console
> mono paket.exe add nuget WindowsAzure.Storage
```

<span data-ttu-id="cb60e-110">При этом будет `WindowsAzure.Storage` добавлен набор зависимостей пакета для проекта в текущем каталоге, `paket.dependencies` изменен файл и загружен пакет.</span><span class="sxs-lookup"><span data-stu-id="cb60e-110">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, modify the `paket.dependencies` file, and download the package.</span></span> <span data-ttu-id="cb60e-111">Если вы ранее настроили зависимости или работаете с проектом, в котором зависимости были настроены другим разработчиком, вы можете разрешить и установить зависимости в локальной среде следующим образом:</span><span class="sxs-lookup"><span data-stu-id="cb60e-111">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

```console
> paket install
```

<span data-ttu-id="cb60e-112">Или, для разработки Mono:</span><span class="sxs-lookup"><span data-stu-id="cb60e-112">Or, for Mono development:</span></span>

```console
> mono paket.exe install
```

<span data-ttu-id="cb60e-113">Вы можете обновить все зависимости пакета до последней версии следующим образом:</span><span class="sxs-lookup"><span data-stu-id="cb60e-113">You can update all your package dependencies to the latest version like this:</span></span>

```console
> paket update
```

<span data-ttu-id="cb60e-114">Или, для разработки Mono:</span><span class="sxs-lookup"><span data-stu-id="cb60e-114">Or, for Mono development:</span></span>

```console
> mono paket.exe update
```

## <a name="using-nuget"></a><span data-ttu-id="cb60e-115">Использование NuGet</span><span class="sxs-lookup"><span data-stu-id="cb60e-115">Using Nuget</span></span>

<span data-ttu-id="cb60e-116">Если вы используете [NuGet](https://www.nuget.org/) в качестве диспетчера зависимостей, это `nuget.exe` средство можно использовать для добавления зависимостей Azure.</span><span class="sxs-lookup"><span data-stu-id="cb60e-116">If you're using [NuGet](https://www.nuget.org/) as your dependency manager, you can use the `nuget.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="cb60e-117">Например:</span><span class="sxs-lookup"><span data-stu-id="cb60e-117">For example:</span></span>

```console
> nuget install WindowsAzure.Storage -ExcludeVersion
```

<span data-ttu-id="cb60e-118">Или, для разработки Mono:</span><span class="sxs-lookup"><span data-stu-id="cb60e-118">Or, for Mono development:</span></span>

```console
> mono nuget.exe install WindowsAzure.Storage -ExcludeVersion
```

<span data-ttu-id="cb60e-119">Это приведет к `WindowsAzure.Storage` добавлению набора зависимостей пакета для проекта в текущем каталоге и загрузке пакета.</span><span class="sxs-lookup"><span data-stu-id="cb60e-119">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, and download the package.</span></span> <span data-ttu-id="cb60e-120">Если вы ранее настроили зависимости или работаете с проектом, в котором зависимости были настроены другим разработчиком, вы можете разрешить и установить зависимости в локальной среде следующим образом:</span><span class="sxs-lookup"><span data-stu-id="cb60e-120">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

```console
> nuget restore
```

<span data-ttu-id="cb60e-121">Или, для разработки Mono:</span><span class="sxs-lookup"><span data-stu-id="cb60e-121">Or, for Mono development:</span></span>

```console
> mono nuget.exe restore
```

<span data-ttu-id="cb60e-122">Вы можете обновить все зависимости пакета до последней версии следующим образом:</span><span class="sxs-lookup"><span data-stu-id="cb60e-122">You can update all your package dependencies to the latest version like this:</span></span>

```console
> nuget update
```

<span data-ttu-id="cb60e-123">Или, для разработки Mono:</span><span class="sxs-lookup"><span data-stu-id="cb60e-123">Or, for Mono development:</span></span>

```console
> mono nuget.exe update
```

## <a name="referencing-assemblies"></a><span data-ttu-id="cb60e-124">Ссылки на сборки</span><span class="sxs-lookup"><span data-stu-id="cb60e-124">Referencing Assemblies</span></span>

<span data-ttu-id="cb60e-125">Чтобы использовать пакеты в F# скрипте, необходимо сослаться на сборки, содержащиеся в пакетах, с помощью `#r` директивы.</span><span class="sxs-lookup"><span data-stu-id="cb60e-125">In order to use your packages in your F# script, you need to reference the assemblies included in the packages using a `#r` directive.</span></span> <span data-ttu-id="cb60e-126">Например:</span><span class="sxs-lookup"><span data-stu-id="cb60e-126">For example:</span></span>

```fsharp
> #r "packages/WindowsAzure.Storage/lib/net40/Microsoft.WindowsAzure.Storage.dll"
```

<span data-ttu-id="cb60e-127">Как видите, необходимо указать относительный путь к библиотеке DLL и полное имя библиотеки DLL, которое может не совпадать с именем пакета.</span><span class="sxs-lookup"><span data-stu-id="cb60e-127">As you can see, you'll need to specify the relative path to the DLL and the full DLL name, which may not be exactly the same as the package name.</span></span> <span data-ttu-id="cb60e-128">Путь будет содержать версию платформы и, возможно, номер версии пакета.</span><span class="sxs-lookup"><span data-stu-id="cb60e-128">The path will include a framework version and possibly a package version number.</span></span> <span data-ttu-id="cb60e-129">Чтобы найти все установленные сборки, можно использовать в командной строке Windows нечто подобное:</span><span class="sxs-lookup"><span data-stu-id="cb60e-129">To find all the installed assemblies, you can use something like this on a Windows command line:</span></span>

```console
> cd packages/WindowsAzure.Storage
> dir /s/b *.dll
```

<span data-ttu-id="cb60e-130">Или в оболочке UNIX примерно так:</span><span class="sxs-lookup"><span data-stu-id="cb60e-130">Or in a Unix shell, something like this:</span></span>

```console
> find packages/WindowsAzure.Storage -name "*.dll"
```

<span data-ttu-id="cb60e-131">При этом будут предоставлены пути к установленным сборкам.</span><span class="sxs-lookup"><span data-stu-id="cb60e-131">This will give you the paths to the installed assemblies.</span></span> <span data-ttu-id="cb60e-132">После этого можно выбрать правильный путь к версии платформы.</span><span class="sxs-lookup"><span data-stu-id="cb60e-132">From there, you can select the correct path for your framework version.</span></span>
