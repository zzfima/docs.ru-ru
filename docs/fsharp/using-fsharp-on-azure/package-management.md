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
# <a name="package-management-for-f-azure-dependencies"></a><span data-ttu-id="9ac81-103">Управление пакетами для зависимостей F# в Azure</span><span class="sxs-lookup"><span data-stu-id="9ac81-103">Package Management for F# Azure Dependencies</span></span>

<span data-ttu-id="9ac81-104">Получение пакетов для разработки Azure удобно при использовании диспетчера пакетов.</span><span class="sxs-lookup"><span data-stu-id="9ac81-104">Obtaining packages for Azure development is easy when you use a package manager.</span></span> <span data-ttu-id="9ac81-105">Ниже приведены два варианта [Paket](https://fsprojects.github.io/Paket/) и [NuGet](https://www.nuget.org/).</span><span class="sxs-lookup"><span data-stu-id="9ac81-105">The two options are [Paket](https://fsprojects.github.io/Paket/) and [NuGet](https://www.nuget.org/).</span></span>

## <a name="using-paket"></a><span data-ttu-id="9ac81-106">С помощью Paket</span><span class="sxs-lookup"><span data-stu-id="9ac81-106">Using Paket</span></span>

<span data-ttu-id="9ac81-107">Если вы используете [Paket](https://fsprojects.github.io/Paket/) качестве менеджера зависимостей можно использовать `paket.exe` средство для добавления зависимости Azure.</span><span class="sxs-lookup"><span data-stu-id="9ac81-107">If you're using [Paket](https://fsprojects.github.io/Paket/) as your dependency manager, you can use the `paket.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="9ac81-108">Пример:</span><span class="sxs-lookup"><span data-stu-id="9ac81-108">For example:</span></span>

    > paket add nuget WindowsAzure.Storage

<span data-ttu-id="9ac81-109">Или, если вы используете [моно](https://www.mono-project.com/) для кросс платформенной разработки .NET:</span><span class="sxs-lookup"><span data-stu-id="9ac81-109">Or, if you're using [Mono](https://www.mono-project.com/) for cross-platform .NET development:</span></span>

    > mono paket.exe add nuget WindowsAzure.Storage

<span data-ttu-id="9ac81-110">При этом будет добавлено `WindowsAzure.Storage` в набор зависимых элементов пакета для проекта в текущем каталоге, измените `paket.dependencies` файла и загрузки пакета.</span><span class="sxs-lookup"><span data-stu-id="9ac81-110">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, modify the `paket.dependencies` file, and download the package.</span></span> <span data-ttu-id="9ac81-111">Если вы ранее настроили зависимости или работы с проектом где зависимости были настроены с другим разработчиком, можно решить и установка зависимостей локально следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9ac81-111">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

    > paket install

<span data-ttu-id="9ac81-112">Или моно разработки:</span><span class="sxs-lookup"><span data-stu-id="9ac81-112">Or, for Mono development:</span></span>

    > mono paket.exe install

<span data-ttu-id="9ac81-113">Можно обновить все зависимости пакета до последней версии следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9ac81-113">You can update all your package dependencies to the latest version like this:</span></span>

    > paket update

<span data-ttu-id="9ac81-114">Или моно разработки:</span><span class="sxs-lookup"><span data-stu-id="9ac81-114">Or, for Mono development:</span></span>

    > mono paket.exe update

## <a name="using-nuget"></a><span data-ttu-id="9ac81-115">С помощью Nuget</span><span class="sxs-lookup"><span data-stu-id="9ac81-115">Using Nuget</span></span>

<span data-ttu-id="9ac81-116">Если вы используете [NuGet](https://www.nuget.org/) качестве менеджера зависимостей можно использовать `nuget.exe` средство для добавления зависимости Azure.</span><span class="sxs-lookup"><span data-stu-id="9ac81-116">If you're using [NuGet](https://www.nuget.org/) as your dependency manager, you can use the `nuget.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="9ac81-117">Пример:</span><span class="sxs-lookup"><span data-stu-id="9ac81-117">For example:</span></span>

    > nuget install WindowsAzure.Storage -ExcludeVersion

<span data-ttu-id="9ac81-118">Или моно разработки:</span><span class="sxs-lookup"><span data-stu-id="9ac81-118">Or, for Mono development:</span></span>

    > mono nuget.exe install WindowsAzure.Storage -ExcludeVersion

<span data-ttu-id="9ac81-119">При этом будет добавлено `WindowsAzure.Storage` в набор зависимых элементов пакета для проекта в текущем каталоге и загрузки пакета.</span><span class="sxs-lookup"><span data-stu-id="9ac81-119">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, and download the package.</span></span> <span data-ttu-id="9ac81-120">Если вы ранее настроили зависимости или работы с проектом где зависимости были настроены с другим разработчиком, можно решить и установка зависимостей локально следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9ac81-120">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

    > nuget restore 

<span data-ttu-id="9ac81-121">Или моно разработки:</span><span class="sxs-lookup"><span data-stu-id="9ac81-121">Or, for Mono development:</span></span>

    > mono nuget.exe restore

<span data-ttu-id="9ac81-122">Можно обновить все зависимости пакета до последней версии следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9ac81-122">You can update all your package dependencies to the latest version like this:</span></span>

    > nuget update

<span data-ttu-id="9ac81-123">Или моно разработки:</span><span class="sxs-lookup"><span data-stu-id="9ac81-123">Or, for Mono development:</span></span>

    > mono nuget.exe update

## <a name="referencing-assemblies"></a><span data-ttu-id="9ac81-124">Ссылки на сборки</span><span class="sxs-lookup"><span data-stu-id="9ac81-124">Referencing Assemblies</span></span>

<span data-ttu-id="9ac81-125">Чтобы использовать пакеты в скрипте F #, необходимо ссылаться на сборки, включенные в пакеты, с помощью `#r` директивы.</span><span class="sxs-lookup"><span data-stu-id="9ac81-125">In order to use your packages in your F# script, you need to reference the assemblies included in the packages using a `#r` directive.</span></span> <span data-ttu-id="9ac81-126">Пример:</span><span class="sxs-lookup"><span data-stu-id="9ac81-126">For example:</span></span>

    > #r "packages/WindowsAzure.Storage/lib/net40/Microsoft.WindowsAzure.Storage.dll"

<span data-ttu-id="9ac81-127">Как видите, необходимо будет указать относительный путь к DLL и полное имя библиотеки DLL, которые могут не соответствовать точно совпадает с именем пакета.</span><span class="sxs-lookup"><span data-stu-id="9ac81-127">As you can see, you'll need to specify the relative path to the DLL and the full DLL name, which may not be exactly the same as the package name.</span></span> <span data-ttu-id="9ac81-128">Путь будет содержать версию платформы и, возможно, номер версии пакета.</span><span class="sxs-lookup"><span data-stu-id="9ac81-128">The path will include a framework version and possibly a package version number.</span></span> <span data-ttu-id="9ac81-129">Чтобы найти всех установленных сборок, можно использовать нечто подобное командной строке Windows:</span><span class="sxs-lookup"><span data-stu-id="9ac81-129">To find all the installed assemblies, you can use something like this on a Windows command line:</span></span>

    > cd packages/WindowsAzure.Storage
    > dir /s/b *.dll

<span data-ttu-id="9ac81-130">Или оболочки Unix, примерно следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9ac81-130">Or in a Unix shell, something like this:</span></span>

    > find packages/WindowsAzure.Storage -name "*.dll"

<span data-ttu-id="9ac81-131">Это позволит получить пути к установленных сборок.</span><span class="sxs-lookup"><span data-stu-id="9ac81-131">This will give you the paths to the installed assemblies.</span></span> <span data-ttu-id="9ac81-132">После этого можно выбрать правильный путь для вашей версии framework.</span><span class="sxs-lookup"><span data-stu-id="9ac81-132">From there, you can select the correct path for your framework version.</span></span>
