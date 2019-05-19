---
title: С помощью пакета управления с помощью F# для Azure
description: Использовать Paket или Nuget для управления F# зависимости Azure
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: b180024e2276a2fd7786f35cb922b1aa1d91f0ad
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880020"
---
# <a name="package-management-for-f-azure-dependencies"></a><span data-ttu-id="78afe-103">Управление пакетами для зависимостей F# в Azure</span><span class="sxs-lookup"><span data-stu-id="78afe-103">Package Management for F# Azure Dependencies</span></span>

<span data-ttu-id="78afe-104">Получение пакетов для разработки для Azure прост, при использовании диспетчера пакетов.</span><span class="sxs-lookup"><span data-stu-id="78afe-104">Obtaining packages for Azure development is easy when you use a package manager.</span></span> <span data-ttu-id="78afe-105">Ниже приведены два варианта [Paket](https://fsprojects.github.io/Paket/) и [NuGet](https://www.nuget.org/).</span><span class="sxs-lookup"><span data-stu-id="78afe-105">The two options are [Paket](https://fsprojects.github.io/Paket/) and [NuGet](https://www.nuget.org/).</span></span>

## <a name="using-paket"></a><span data-ttu-id="78afe-106">С помощью Paket</span><span class="sxs-lookup"><span data-stu-id="78afe-106">Using Paket</span></span>

<span data-ttu-id="78afe-107">Если вы используете [Paket](https://fsprojects.github.io/Paket/) как ваш Диспетчер зависимостей, вы можете использовать `paket.exe` средство, чтобы добавить зависимости Azure.</span><span class="sxs-lookup"><span data-stu-id="78afe-107">If you're using [Paket](https://fsprojects.github.io/Paket/) as your dependency manager, you can use the `paket.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="78afe-108">Пример:</span><span class="sxs-lookup"><span data-stu-id="78afe-108">For example:</span></span>

```
> paket add nuget WindowsAzure.Storage
```

<span data-ttu-id="78afe-109">Или, если вы используете [Mono](https://www.mono-project.com/) для кросс Платформенная разработка .NET:</span><span class="sxs-lookup"><span data-stu-id="78afe-109">Or, if you're using [Mono](https://www.mono-project.com/) for cross-platform .NET development:</span></span>

```
> mono paket.exe add nuget WindowsAzure.Storage
```

<span data-ttu-id="78afe-110">При этом будет добавлено `WindowsAzure.Storage` в набор зависимых элементов пакета для проекта в текущем каталоге, измените `paket.dependencies` файл и загрузить пакет.</span><span class="sxs-lookup"><span data-stu-id="78afe-110">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, modify the `paket.dependencies` file, and download the package.</span></span> <span data-ttu-id="78afe-111">Если вы ранее настроили зависимости или при работе с проектом, где зависимости были настроены с другим разработчиком, можно решить и установите зависимости локально следующим образом:</span><span class="sxs-lookup"><span data-stu-id="78afe-111">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

```
> paket install
```

<span data-ttu-id="78afe-112">Или, для разработки Mono:</span><span class="sxs-lookup"><span data-stu-id="78afe-112">Or, for Mono development:</span></span>

```
> mono paket.exe install
```

<span data-ttu-id="78afe-113">Вы можете обновить все зависимости пакета до последней версии следующим образом:</span><span class="sxs-lookup"><span data-stu-id="78afe-113">You can update all your package dependencies to the latest version like this:</span></span>

```
> paket update
```

<span data-ttu-id="78afe-114">Или, для разработки Mono:</span><span class="sxs-lookup"><span data-stu-id="78afe-114">Or, for Mono development:</span></span>

```
> mono paket.exe update
```

## <a name="using-nuget"></a><span data-ttu-id="78afe-115">С помощью Nuget</span><span class="sxs-lookup"><span data-stu-id="78afe-115">Using Nuget</span></span>

<span data-ttu-id="78afe-116">Если вы используете [NuGet](https://www.nuget.org/) как ваш Диспетчер зависимостей, вы можете использовать `nuget.exe` средство, чтобы добавить зависимости Azure.</span><span class="sxs-lookup"><span data-stu-id="78afe-116">If you're using [NuGet](https://www.nuget.org/) as your dependency manager, you can use the `nuget.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="78afe-117">Пример:</span><span class="sxs-lookup"><span data-stu-id="78afe-117">For example:</span></span>

```
> nuget install WindowsAzure.Storage -ExcludeVersion
```

<span data-ttu-id="78afe-118">Или, для разработки Mono:</span><span class="sxs-lookup"><span data-stu-id="78afe-118">Or, for Mono development:</span></span>

```
> mono nuget.exe install WindowsAzure.Storage -ExcludeVersion
```

<span data-ttu-id="78afe-119">При этом будет добавлено `WindowsAzure.Storage` в набор зависимых элементов пакета для проекта в текущем каталоге и загрузки пакета.</span><span class="sxs-lookup"><span data-stu-id="78afe-119">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, and download the package.</span></span> <span data-ttu-id="78afe-120">Если вы ранее настроили зависимости или при работе с проектом, где зависимости были настроены с другим разработчиком, можно решить и установите зависимости локально следующим образом:</span><span class="sxs-lookup"><span data-stu-id="78afe-120">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

```
> nuget restore
```

<span data-ttu-id="78afe-121">Или, для разработки Mono:</span><span class="sxs-lookup"><span data-stu-id="78afe-121">Or, for Mono development:</span></span>

```
> mono nuget.exe restore
```

<span data-ttu-id="78afe-122">Вы можете обновить все зависимости пакета до последней версии следующим образом:</span><span class="sxs-lookup"><span data-stu-id="78afe-122">You can update all your package dependencies to the latest version like this:</span></span>

```
> nuget update
```

<span data-ttu-id="78afe-123">Или, для разработки Mono:</span><span class="sxs-lookup"><span data-stu-id="78afe-123">Or, for Mono development:</span></span>

```
> mono nuget.exe update
```

## <a name="referencing-assemblies"></a><span data-ttu-id="78afe-124">Ссылки на сборки</span><span class="sxs-lookup"><span data-stu-id="78afe-124">Referencing Assemblies</span></span>

<span data-ttu-id="78afe-125">Чтобы использовать пакеты в вашей F# скрипта, необходимо сослаться на сборки, включенные в пакеты, с помощью `#r` директива.</span><span class="sxs-lookup"><span data-stu-id="78afe-125">In order to use your packages in your F# script, you need to reference the assemblies included in the packages using a `#r` directive.</span></span> <span data-ttu-id="78afe-126">Пример:</span><span class="sxs-lookup"><span data-stu-id="78afe-126">For example:</span></span>

```
> #r "packages/WindowsAzure.Storage/lib/net40/Microsoft.WindowsAzure.Storage.dll"
```

<span data-ttu-id="78afe-127">Как вы видите, вам потребуется указать относительный путь к DLL и полное имя библиотеки DLL, которые могут не соответствовать точно совпадает с именем пакета.</span><span class="sxs-lookup"><span data-stu-id="78afe-127">As you can see, you'll need to specify the relative path to the DLL and the full DLL name, which may not be exactly the same as the package name.</span></span> <span data-ttu-id="78afe-128">Этот путь будет содержать версии платформы и, возможно, номер версии пакета.</span><span class="sxs-lookup"><span data-stu-id="78afe-128">The path will include a framework version and possibly a package version number.</span></span> <span data-ttu-id="78afe-129">Чтобы найти всех установленных сборок, можно использовать примерно следующее в командной строке Windows:</span><span class="sxs-lookup"><span data-stu-id="78afe-129">To find all the installed assemblies, you can use something like this on a Windows command line:</span></span>

```
> cd packages/WindowsAzure.Storage
> dir /s/b *.dll
```

<span data-ttu-id="78afe-130">Или в оболочке Unix, примерно следующим образом:</span><span class="sxs-lookup"><span data-stu-id="78afe-130">Or in a Unix shell, something like this:</span></span>

```
> find packages/WindowsAzure.Storage -name "*.dll"
```

<span data-ttu-id="78afe-131">Это позволит получить пути к установленными сборками.</span><span class="sxs-lookup"><span data-stu-id="78afe-131">This will give you the paths to the installed assemblies.</span></span> <span data-ttu-id="78afe-132">После этого можно выбрать правильный путь для вашей версии платформы.</span><span class="sxs-lookup"><span data-stu-id="78afe-132">From there, you can select the correct path for your framework version.</span></span>
