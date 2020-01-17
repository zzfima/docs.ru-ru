---
title: Установка .NET Core на openSUSE 15 — диспетчер пакетов — .NET Core
description: Используйте диспетчер пакетов для установки пакета SDK для .NET Core и среды выполнения на openSUSE 15.
author: thraka
ms.author: adegeo
ms.date: 12/26/2019
ms.openlocfilehash: cba07bafc32cc71a1cdaec08902284e105af4776
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740670"
---
# <a name="opensuse-15-package-manager---install-net-core"></a><span data-ttu-id="5e165-103">Диспетчер пакетов openSUSE 15 — установка .NET Core</span><span class="sxs-lookup"><span data-stu-id="5e165-103">openSUSE 15 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="5e165-104">Эта статья описывает, как использовать диспетчер пакетов для установки .NET Core на openSUSE 15.</span><span class="sxs-lookup"><span data-stu-id="5e165-104">This article describes how to use a package manager to install .NET Core on openSUSE 15.</span></span> <span data-ttu-id="5e165-105">Если вы устанавливаете среду выполнения, мы рекомендуем установить [среду выполнения ASP.NET Core](#install-the-aspnet-core-runtime), так как она включает в себя среды выполнения .NET Core и ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="5e165-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="5e165-106">Регистрация ключа Майкрософт и веб-канала</span><span class="sxs-lookup"><span data-stu-id="5e165-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="5e165-107">Перед установкой .NET нужно сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="5e165-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="5e165-108">зарегистрировать ключ Майкрософт;</span><span class="sxs-lookup"><span data-stu-id="5e165-108">Register the Microsoft key.</span></span>
- <span data-ttu-id="5e165-109">зарегистрировать репозиторий продуктов;</span><span class="sxs-lookup"><span data-stu-id="5e165-109">Register the product repository.</span></span>
- <span data-ttu-id="5e165-110">установить необходимые зависимости.</span><span class="sxs-lookup"><span data-stu-id="5e165-110">Install required dependencies.</span></span>

<span data-ttu-id="5e165-111">Данную операцию достаточно выполнить один раз для каждого компьютера.</span><span class="sxs-lookup"><span data-stu-id="5e165-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="5e165-112">Откройте терминал и выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="5e165-112">Open a terminal and run the following commands.</span></span>

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget -q https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

## <a name="dependency-error-with-net-core-31"></a><span data-ttu-id="5e165-113">Ошибка зависимости в .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="5e165-113">Dependency error with .NET Core 3.1</span></span>

<span data-ttu-id="5e165-114">В веб-канале пакетов .NET Core 3.1 для openSUSE возникла проблема с зависимостью**krb5**.</span><span class="sxs-lookup"><span data-stu-id="5e165-114">The .NET Core 3.1 package feed for openSUSE has a problem with the **krb5** dependency.</span></span> <span data-ttu-id="5e165-115">Используйте следующую команду, чтобы установить правильные зависимости перед установкой .NET Core 3.1 или ASP.NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="5e165-115">Use the following command to install the correct dependencies prior to installing .NET Core 3.1 or ASP.NET Core 3.1.</span></span>

```bash
sudo zypper install https://packages.microsoft.com/opensuse/15/prod/dotnet-runtime-deps-3.1.0-opensuse.42-x64.rpm
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="5e165-116">Установка пакета SDK для .NET Core</span><span class="sxs-lookup"><span data-stu-id="5e165-116">Install the .NET Core SDK</span></span>

<span data-ttu-id="5e165-117">Обновите продукты, доступные для установки, а затем установите пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5e165-117">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="5e165-118">В терминале выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="5e165-118">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="5e165-119">В веб-канале пакетов .NET Core 3.1 для openSUSE возникла проблема с зависимостью**krb5**.</span><span class="sxs-lookup"><span data-stu-id="5e165-119">The .NET Core 3.1 package feed for openSUSE has a problem with the **krb5** dependency.</span></span> <span data-ttu-id="5e165-120">Используйте следующую команду, чтобы установить правильные зависимости перед установкой пакета SDK для .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="5e165-120">Use the following command to install the correct dependencies, then install the .NET Core 3.1 SDK.</span></span>
>
> ```bash
> sudo zypper install https://packages.microsoft.com/opensuse/15/prod/dotnet-runtime-deps-3.1.0-opensuse.42-x64.rpm
> ```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="5e165-121">Установка среды выполнения ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="5e165-121">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="5e165-122">Обновите продукты, доступные для установки, а затем установите среду выполнения ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="5e165-122">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="5e165-123">В терминале выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="5e165-123">In your terminal, run the following command.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="5e165-124">В веб-канале пакетов .NET Core 3.1 для openSUSE возникла проблема с зависимостью**krb5**.</span><span class="sxs-lookup"><span data-stu-id="5e165-124">The .NET Core 3.1 package feed for openSUSE has a problem with the **krb5** dependency.</span></span> <span data-ttu-id="5e165-125">Используйте следующую команду, чтобы установить правильные зависимости перед установкой среды выполнения для ASP.NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="5e165-125">Use the following command to install the correct dependencies, then install the ASP.NET Core 3.1 runtime.</span></span>
>
> ```bash
> sudo zypper install https://packages.microsoft.com/opensuse/15/prod/dotnet-runtime-deps-3.1.0-opensuse.42-x64.rpm
> ```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="5e165-126">Установка среды выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="5e165-126">Install the .NET Core runtime</span></span>

<span data-ttu-id="5e165-127">Обновите продукты, доступные для установки, а затем установите среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5e165-127">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="5e165-128">В терминале выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="5e165-128">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="5e165-129">В веб-канале пакетов .NET Core 3.1 для openSUSE возникла проблема с зависимостью**krb5**.</span><span class="sxs-lookup"><span data-stu-id="5e165-129">The .NET Core 3.1 package feed for openSUSE has a problem with the **krb5** dependency.</span></span> <span data-ttu-id="5e165-130">Используйте следующую команду, чтобы установить правильные зависимости перед установкой среды выполнения для .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="5e165-130">Use the following command to install the correct dependencies, then install the .NET Core 3.1 runtime.</span></span>
>
> ```bash
> sudo zypper install https://packages.microsoft.com/opensuse/15/prod/dotnet-runtime-deps-3.1.0-opensuse.42-x64.rpm
> ```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="5e165-131">Установка других версий</span><span class="sxs-lookup"><span data-stu-id="5e165-131">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]
