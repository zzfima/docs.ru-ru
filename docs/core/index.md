---
title: Руководство по .NET Core
description: .NET Core — это модульная высокопроизводительная реализация .NET для создания приложений Windows, Linux и Mac. Для начала получите дополнительную информацию о .NET Core.
author: richlander
ms.date: 12/04/2019
ms.custom: updateeachrelease
ms.openlocfilehash: b2622dba53d64c9dcf58e852d57de117fe79eb2e
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837016"
---
# <a name="net-core-guide"></a><span data-ttu-id="399bf-104">Руководство по .NET Core</span><span class="sxs-lookup"><span data-stu-id="399bf-104">.NET Core Guide</span></span>

<span data-ttu-id="399bf-105">[.NET Core](about.md) — это универсальная платформа разработки с [открытым кодом](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT), которую поддерживает корпорация Майкрософт и сообщество .NET на сайте [GitHub](https://github.com/dotnet/core).</span><span class="sxs-lookup"><span data-stu-id="399bf-105">[.NET Core](about.md) is an [open-source](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT), general-purpose development platform maintained by Microsoft and the .NET community on [GitHub](https://github.com/dotnet/core).</span></span> <span data-ttu-id="399bf-106">Она является кроссплатформенной (поддерживает Windows, macOS и Linux) и может использоваться для создания приложений для устройств, облака и Интернета вещей.</span><span class="sxs-lookup"><span data-stu-id="399bf-106">It's cross-platform (supporting Windows, macOS, and Linux) and can be used to build device, cloud, and IoT applications.</span></span>

<span data-ttu-id="399bf-107">Дополнительные сведения о среде .NET Core, включая ее характеристики, поддерживаемые языки и платформы, а также основные API-интерфейсы, см. в [этой статье](about.md).</span><span class="sxs-lookup"><span data-stu-id="399bf-107">See [About .NET Core](about.md) to learn more about .NET Core, including its characteristics, supported languages and frameworks, and key APIs.</span></span>

<span data-ttu-id="399bf-108">Просмотрите [руководства по .NET Core](tutorials/index.md), чтобы узнать, как создать простое приложение .NET Core.</span><span class="sxs-lookup"><span data-stu-id="399bf-108">Check out [.NET Core Tutorials](tutorials/index.md) to learn how to create a simple .NET Core application.</span></span> <span data-ttu-id="399bf-109">На создание и запуск первого приложения потребуется буквально несколько минут.</span><span class="sxs-lookup"><span data-stu-id="399bf-109">It only takes a few minutes to get your first app up and running.</span></span> <span data-ttu-id="399bf-110">Если вы хотите попробовать поработать с .NET Core в браузере, перейдите на страницу онлайн-руководства [Числа в C#](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml).</span><span class="sxs-lookup"><span data-stu-id="399bf-110">If you want to try .NET Core in your browser, look at the [Numbers in C#](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml) online tutorial.</span></span>

## <a name="download-net-core"></a><span data-ttu-id="399bf-111">Скачать .NET Core</span><span class="sxs-lookup"><span data-stu-id="399bf-111">Download .NET Core</span></span>

<span data-ttu-id="399bf-112">Скачайте [пакет SDK для .NET Core](https://www.microsoft.com/net/download), чтобы поработать с .NET Core на компьютере Windows, macOS или Linux.</span><span class="sxs-lookup"><span data-stu-id="399bf-112">Download the [.NET Core SDK](https://www.microsoft.com/net/download) to try .NET Core on your Windows, macOS, or Linux machine.</span></span> <span data-ttu-id="399bf-113">Если вы предпочитаете использовать контейнеры Docker, перейдите на страницу[.NET Core Docker Hub](https://hub.docker.com/_/microsoft-dotnet-core/).</span><span class="sxs-lookup"><span data-stu-id="399bf-113">And if you prefer to use Docker containers, visit the [.NET Core Docker Hub](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span>

<span data-ttu-id="399bf-114">Если вам нужна другая версия .NET Core, все версии доступны на [странице скачиваемых файлов .NET Core](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="399bf-114">All .NET Core versions are available at [.NET Core Downloads](https://dotnet.microsoft.com/download/dotnet-core) if you're looking for another .NET Core version.</span></span>

## <a name="net-core-31"></a><span data-ttu-id="399bf-115">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="399bf-115">.NET Core 3.1</span></span>

<span data-ttu-id="399bf-116">.NET Core 3.1 является последней версией.</span><span class="sxs-lookup"><span data-stu-id="399bf-116">The latest version is .NET Core 3.1.</span></span> <span data-ttu-id="399bf-117">В нее входят незначительные улучшения версии .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="399bf-117">Which includes minor improvements over .NET Core 3.0.</span></span> <span data-ttu-id="399bf-118">Однако .NET Core 3.1 является долгосрочным поддерживаемым выпуском.</span><span class="sxs-lookup"><span data-stu-id="399bf-118">However, .NET Core 3.1 is a long-term supported release.</span></span> <span data-ttu-id="399bf-119">Дополнительные сведения о выпуске .NET Core 3.1 см. в разделе [Новые возможности .NET Core 3.1](./whats-new/dotnet-core-3-1.md).</span><span class="sxs-lookup"><span data-stu-id="399bf-119">For more information about the .NET Core 3.1 release, see [What's new in .NET Core 3.1](./whats-new/dotnet-core-3-1.md).</span></span>

## <a name="create-your-first-application"></a><span data-ttu-id="399bf-120">Создание первого приложения</span><span class="sxs-lookup"><span data-stu-id="399bf-120">Create your first application</span></span>

<span data-ttu-id="399bf-121">После установки пакета SDK для .NET Core откройте командную строку.</span><span class="sxs-lookup"><span data-stu-id="399bf-121">After installing the .NET Core SDK, open a command prompt.</span></span> <span data-ttu-id="399bf-122">Для создания и запуска приложения C# введите следующие команды `dotnet`:</span><span class="sxs-lookup"><span data-stu-id="399bf-122">Type the following `dotnet` commands to create and run a C# application:</span></span>

```dotnetcli
dotnet new console
dotnet run
```

<span data-ttu-id="399bf-123">Должны выводиться следующие данные:</span><span class="sxs-lookup"><span data-stu-id="399bf-123">You should see the following output:</span></span>

```output
Hello World!
```

## <a name="support"></a><span data-ttu-id="399bf-124">Поддержка</span><span class="sxs-lookup"><span data-stu-id="399bf-124">Support</span></span>

<span data-ttu-id="399bf-125">Поддержку платформы .NET Core реализует [корпорация Майкрософт](https://dotnet.microsoft.com/platform/support/policy). Поддержка предоставляется для операционных систем Windows, macOS и Linux.</span><span class="sxs-lookup"><span data-stu-id="399bf-125">.NET Core is [supported by Microsoft](https://dotnet.microsoft.com/platform/support/policy), on Windows, macOS, and Linux.</span></span> <span data-ttu-id="399bf-126">Для повышения безопасности и качества платформа обновляется несколько раз в год, обычно ежемесячно.</span><span class="sxs-lookup"><span data-stu-id="399bf-126">It's updated for security and quality several times a year, typically monthly.</span></span>

<span data-ttu-id="399bf-127">Двоичные дистрибутивы .NET Core собираются и тестируются в Azure на серверах Майкрософт и поддерживаются наравне с другими продуктами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="399bf-127">.NET Core binary distributions are built and tested on Microsoft-maintained servers in Azure and supported just like any Microsoft product.</span></span>

<span data-ttu-id="399bf-128">[Red Hat поддерживает .NET Core](http://redhatloves.net/) в операционной системе Red Hat Enterprise Linux (RHEL).</span><span class="sxs-lookup"><span data-stu-id="399bf-128">[Red Hat supports .NET Core](http://redhatloves.net/) on Red Hat Enterprise Linux (RHEL).</span></span> <span data-ttu-id="399bf-129">Red Hat собирает .NET Core из исходного кода и публикует сборки на сайте [Red Hat Software Collections](https://developers.redhat.com/products/softwarecollections/overview/).</span><span class="sxs-lookup"><span data-stu-id="399bf-129">Red Hat builds .NET Core from source and makes it available in the [Red Hat Software Collections](https://developers.redhat.com/products/softwarecollections/overview/).</span></span> <span data-ttu-id="399bf-130">Red Hat и Майкрософт совместно занимаются обеспечением беспроблемной работы .NET Core в RHEL.</span><span class="sxs-lookup"><span data-stu-id="399bf-130">Red Hat and Microsoft collaborate to ensure that .NET Core works well on RHEL.</span></span>
