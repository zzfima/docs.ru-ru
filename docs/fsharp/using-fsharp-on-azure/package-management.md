---
title: "С помощью пакета управления с помощью F # для Azure"
description: "Используйте Paket или Nuget для управления зависимостями Azure F #"
keywords: "Visual f #, f #, функционального программирования, .NET, .NET Core, Azure"
author: sylvanc
ms.author: phcart
ms.date: 09/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: dd32ef9c-5416-467e-9fa3-c9ee3bb08456
ms.openlocfilehash: 22dc94ea69e0dfb95e22da4bc64ce915398190d2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="package-management-for-f-azure-dependencies"></a><span data-ttu-id="2f02a-104">Управление пакетами для зависимостей F# в Azure</span><span class="sxs-lookup"><span data-stu-id="2f02a-104">Package Management for F# Azure Dependencies</span></span>

<span data-ttu-id="2f02a-105">Получение пакетов для разработки Azure удобно при использовании диспетчера пакетов.</span><span class="sxs-lookup"><span data-stu-id="2f02a-105">Obtaining packages for Azure development is easy when you use a package manager.</span></span> <span data-ttu-id="2f02a-106">Ниже приведены два варианта [Paket](https://fsprojects.github.io/Paket/) и [NuGet](https://www.nuget.org/).</span><span class="sxs-lookup"><span data-stu-id="2f02a-106">The two options are [Paket](https://fsprojects.github.io/Paket/) and [NuGet](https://www.nuget.org/).</span></span>

## <a name="using-paket"></a><span data-ttu-id="2f02a-107">С помощью Paket</span><span class="sxs-lookup"><span data-stu-id="2f02a-107">Using Paket</span></span>

<span data-ttu-id="2f02a-108">Если вы используете [Paket](https://fsprojects.github.io/Paket/) качестве менеджера зависимостей можно использовать `paket.exe` средство для добавления зависимости Azure.</span><span class="sxs-lookup"><span data-stu-id="2f02a-108">If you're using [Paket](https://fsprojects.github.io/Paket/) as your dependency manager, you can use the `paket.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="2f02a-109">Пример:</span><span class="sxs-lookup"><span data-stu-id="2f02a-109">For example:</span></span>

    > paket add nuget WindowsAzure.Storage

<span data-ttu-id="2f02a-110">Или, если вы используете [моно](http://www.mono-project.com/) для кросс платформенной разработки .NET:</span><span class="sxs-lookup"><span data-stu-id="2f02a-110">Or, if you're using [Mono](http://www.mono-project.com/) for cross-platform .NET development:</span></span>

    > mono paket.exe add nuget WindowsAzure.Storage

<span data-ttu-id="2f02a-111">При этом будет добавлено `WindowsAzure.Storage` в набор зависимых элементов пакета для проекта в текущем каталоге, измените `paket.dependencies` файла и загрузки пакета.</span><span class="sxs-lookup"><span data-stu-id="2f02a-111">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, modify the `paket.dependencies` file, and download the package.</span></span> <span data-ttu-id="2f02a-112">Если вы ранее настроили зависимости или работы с проектом где зависимости были настроены с другим разработчиком, можно решить и установка зависимостей локально следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2f02a-112">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

    > paket install

<span data-ttu-id="2f02a-113">Или моно разработки:</span><span class="sxs-lookup"><span data-stu-id="2f02a-113">Or, for Mono development:</span></span>

    > mono paket.exe install

<span data-ttu-id="2f02a-114">Можно обновить все зависимости пакета до последней версии следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2f02a-114">You can update all your package dependencies to the latest version like this:</span></span>

    > paket update

<span data-ttu-id="2f02a-115">Или моно разработки:</span><span class="sxs-lookup"><span data-stu-id="2f02a-115">Or, for Mono development:</span></span>

    > mono paket.exe update

## <a name="using-nuget"></a><span data-ttu-id="2f02a-116">С помощью Nuget</span><span class="sxs-lookup"><span data-stu-id="2f02a-116">Using Nuget</span></span>

<span data-ttu-id="2f02a-117">Если вы используете [NuGet](https://www.nuget.org/) качестве менеджера зависимостей можно использовать `nuget.exe` средство для добавления зависимости Azure.</span><span class="sxs-lookup"><span data-stu-id="2f02a-117">If you're using [NuGet](https://www.nuget.org/) as your dependency manager, you can use the `nuget.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="2f02a-118">Пример:</span><span class="sxs-lookup"><span data-stu-id="2f02a-118">For example:</span></span>

    > nuget install WindowsAzure.Storage -ExcludeVersion

<span data-ttu-id="2f02a-119">Или моно разработки:</span><span class="sxs-lookup"><span data-stu-id="2f02a-119">Or, for Mono development:</span></span>

    > mono nuget.exe install WindowsAzure.Storage -ExcludeVersion

<span data-ttu-id="2f02a-120">При этом будет добавлено `WindowsAzure.Storage` в набор зависимых элементов пакета для проекта в текущем каталоге и загрузки пакета.</span><span class="sxs-lookup"><span data-stu-id="2f02a-120">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, and download the package.</span></span> <span data-ttu-id="2f02a-121">Если вы ранее настроили зависимости или работы с проектом где зависимости были настроены с другим разработчиком, можно решить и установка зависимостей локально следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2f02a-121">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

    > nuget restore 

<span data-ttu-id="2f02a-122">Или моно разработки:</span><span class="sxs-lookup"><span data-stu-id="2f02a-122">Or, for Mono development:</span></span>

    > mono nuget.exe restore

<span data-ttu-id="2f02a-123">Можно обновить все зависимости пакета до последней версии следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2f02a-123">You can update all your package dependencies to the latest version like this:</span></span>

    > nuget update

<span data-ttu-id="2f02a-124">Или моно разработки:</span><span class="sxs-lookup"><span data-stu-id="2f02a-124">Or, for Mono development:</span></span>

    > mono nuget.exe update

## <a name="referencing-assemblies"></a><span data-ttu-id="2f02a-125">Ссылки на сборки</span><span class="sxs-lookup"><span data-stu-id="2f02a-125">Referencing Assemblies</span></span>

<span data-ttu-id="2f02a-126">Чтобы использовать пакеты в скрипте F #, необходимо ссылаться на сборки, включенные в пакеты, с помощью `#r` директивы.</span><span class="sxs-lookup"><span data-stu-id="2f02a-126">In order to use your packages in your F# script, you need to reference the assemblies included in the packages using a `#r` directive.</span></span> <span data-ttu-id="2f02a-127">Пример:</span><span class="sxs-lookup"><span data-stu-id="2f02a-127">For example:</span></span>

    > #r "packages/WindowsAzure.Storage/lib/net40/Microsoft.WindowsAzure.Storage.dll"

<span data-ttu-id="2f02a-128">Как видите, необходимо будет указать относительный путь к DLL и полное имя библиотеки DLL, которые могут не соответствовать точно совпадает с именем пакета.</span><span class="sxs-lookup"><span data-stu-id="2f02a-128">As you can see, you'll need to specify the relative path to the DLL and the full DLL name, which may not be exactly the same as the package name.</span></span> <span data-ttu-id="2f02a-129">Путь будет содержать версию платформы и, возможно, номер версии пакета.</span><span class="sxs-lookup"><span data-stu-id="2f02a-129">The path will include a framework version and possibly a package version number.</span></span> <span data-ttu-id="2f02a-130">Чтобы найти всех установленных сборок, можно использовать нечто подобное командной строке Windows:</span><span class="sxs-lookup"><span data-stu-id="2f02a-130">To find all the installed assemblies, you can use something like this on a Windows command line:</span></span>

    > cd packages/WindowsAzure.Storage
    > dir /s/b *.dll

<span data-ttu-id="2f02a-131">Или оболочки Unix, примерно следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2f02a-131">Or in a Unix shell, something like this:</span></span>

    > find packages/WindowsAzure.Storage -name "*.dll"

<span data-ttu-id="2f02a-132">Это позволит получить пути к установленных сборок.</span><span class="sxs-lookup"><span data-stu-id="2f02a-132">This will give you the paths to the installed assemblies.</span></span> <span data-ttu-id="2f02a-133">После этого можно выбрать правильный путь для вашей версии framework.</span><span class="sxs-lookup"><span data-stu-id="2f02a-133">From there, you can select the correct path for your framework version.</span></span>
