---
title: Руководство по .NET Core
description: .NET Core — это модульная высокопроизводительная реализация .NET для создания приложений Windows, Linux и Mac. Для начала получите дополнительную информацию о .NET Core.
author: richlander
ms.date: 09/23/2019
ms.custom: updateeachrelease
ms.openlocfilehash: 95f18ca09852ce139a4b99ed7aef4802d4883e13
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216218"
---
# <a name="net-core-guide"></a><span data-ttu-id="57865-104">Руководство по .NET Core</span><span class="sxs-lookup"><span data-stu-id="57865-104">.NET Core Guide</span></span>

<span data-ttu-id="57865-105">[.NET Core](about.md) — это универсальная платформа разработки с [открытым кодом](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT), которую поддерживает корпорация Майкрософт и сообщество .NET на сайте [GitHub](https://github.com/dotnet/core).</span><span class="sxs-lookup"><span data-stu-id="57865-105">[.NET Core](about.md) is an [open-source](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT), general-purpose development platform maintained by Microsoft and the .NET community on [GitHub](https://github.com/dotnet/core).</span></span> <span data-ttu-id="57865-106">Она является кроссплатформенной (поддерживает Windows, macOS и Linux) и может использоваться для создания приложений для устройств, облака и Интернета вещей.</span><span class="sxs-lookup"><span data-stu-id="57865-106">It's cross-platform (supporting Windows, macOS, and Linux) and can be used to build device, cloud, and IoT applications.</span></span>

<span data-ttu-id="57865-107">Дополнительные сведения о среде .NET Core, включая ее характеристики, поддерживаемые языки и платформы, а также основные API-интерфейсы, см. в [этой статье](about.md).</span><span class="sxs-lookup"><span data-stu-id="57865-107">See [About .NET Core](about.md) to learn more about .NET Core, including its characteristics, supported languages and frameworks, and key APIs.</span></span>

<span data-ttu-id="57865-108">Просмотрите [руководства по .NET Core](tutorials/index.md), чтобы узнать, как создать простое приложение .NET Core.</span><span class="sxs-lookup"><span data-stu-id="57865-108">Check out [.NET Core Tutorials](tutorials/index.md) to learn how to create a simple .NET Core application.</span></span> <span data-ttu-id="57865-109">На создание и запуск первого приложения потребуется буквально несколько минут.</span><span class="sxs-lookup"><span data-stu-id="57865-109">It only takes a few minutes to get your first app up and running.</span></span> <span data-ttu-id="57865-110">Если вы хотите попробовать поработать с .NET Core в браузере, перейдите на страницу онлайн-руководства [Числа в C#](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml).</span><span class="sxs-lookup"><span data-stu-id="57865-110">If you want to try .NET Core in your browser, look at the [Numbers in C#](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml) online tutorial.</span></span>

## <a name="download-net-core"></a><span data-ttu-id="57865-111">Скачать .NET Core</span><span class="sxs-lookup"><span data-stu-id="57865-111">Download .NET Core</span></span>

<span data-ttu-id="57865-112">Скачайте [пакет SDK для .NET Core](https://www.microsoft.com/net/download), чтобы поработать с .NET Core на компьютере Windows, macOS или Linux.</span><span class="sxs-lookup"><span data-stu-id="57865-112">Download the [.NET Core SDK](https://www.microsoft.com/net/download) to try .NET Core on your Windows, macOS, or Linux machine.</span></span> <span data-ttu-id="57865-113">Если вы предпочитаете использовать контейнеры Docker, перейдите на страницу[.NET Core Docker Hub](https://hub.docker.com/_/microsoft-dotnet-core/).</span><span class="sxs-lookup"><span data-stu-id="57865-113">And if you prefer to use Docker containers, visit the [.NET Core Docker Hub](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span>

<span data-ttu-id="57865-114">Если вам нужна другая версия .NET Core, все версии доступны на [странице скачиваемых файлов .NET Core](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="57865-114">All .NET Core versions are available at [.NET Core Downloads](https://dotnet.microsoft.com/download/dotnet-core) if you're looking for another .NET Core version.</span></span>

## <a name="net-core-30"></a><span data-ttu-id="57865-115">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="57865-115">.NET Core 3.0</span></span>

<span data-ttu-id="57865-116">.NET Core 3.0 является последней версией.</span><span class="sxs-lookup"><span data-stu-id="57865-116">The latest version is .NET Core 3.0.</span></span> <span data-ttu-id="57865-117">Новые возможности включают поддержку Windows Desktop в Windows Presentation Foundation (WPF) и Windows Forms, комплексную разработку веб-приложений C# с помощью Blazor, новые усовершенствования SignalR и службы SignalR Azure, новые функции языка C# 8 и многое другое.</span><span class="sxs-lookup"><span data-stu-id="57865-117">New features include Windows Desktop support with Windows Presentation Foundation (WPF) and Windows Forms, full stack C# web development with Blazor, new enhancements to SignalR and Azure SignalR Service, new C# language features with C# 8, and much more.</span></span> <span data-ttu-id="57865-118">См. [полный список новых возможностей .NET Core 3.0](./whats-new/dotnet-core-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="57865-118">For a full listing of the new features in .NET Core 3.0, see [What's new in .NET Core 3.0](./whats-new/dotnet-core-3-0.md).</span></span>

## <a name="create-your-first-application"></a><span data-ttu-id="57865-119">Создание первого приложения</span><span class="sxs-lookup"><span data-stu-id="57865-119">Create your first application</span></span>

<span data-ttu-id="57865-120">После установки пакета SDK для .NET Core откройте командную строку.</span><span class="sxs-lookup"><span data-stu-id="57865-120">After installing the .NET Core SDK, open a command prompt.</span></span> <span data-ttu-id="57865-121">Для создания и запуска приложения C# введите следующие команды `dotnet`:</span><span class="sxs-lookup"><span data-stu-id="57865-121">Type the following `dotnet` commands to create and run a C# application:</span></span>

```dotnetcli
dotnet new console
dotnet run
```

<span data-ttu-id="57865-122">Должны выводиться следующие данные:</span><span class="sxs-lookup"><span data-stu-id="57865-122">You should see the following output:</span></span>

```output
Hello World!
```

## <a name="support"></a><span data-ttu-id="57865-123">Поддержка</span><span class="sxs-lookup"><span data-stu-id="57865-123">Support</span></span>

<span data-ttu-id="57865-124">Поддержку платформы .NET Core реализует [корпорация Майкрософт](https://dotnet.microsoft.com/platform/support/policy). Поддержка предоставляется для операционных систем Windows, macOS и Linux.</span><span class="sxs-lookup"><span data-stu-id="57865-124">.NET Core is [supported by Microsoft](https://dotnet.microsoft.com/platform/support/policy), on Windows, macOS, and Linux.</span></span> <span data-ttu-id="57865-125">Для повышения безопасности и качества платформа обновляется несколько раз в год, обычно ежемесячно.</span><span class="sxs-lookup"><span data-stu-id="57865-125">It's updated for security and quality several times a year, typically monthly.</span></span>

<span data-ttu-id="57865-126">Двоичные дистрибутивы .NET Core собираются и тестируются в Azure на серверах Майкрософт и поддерживаются наравне с другими продуктами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="57865-126">.NET Core binary distributions are built and tested on Microsoft-maintained servers in Azure and supported just like any Microsoft product.</span></span>

<span data-ttu-id="57865-127">[Red Hat поддерживает .NET Core](http://redhatloves.net/) в операционной системе Red Hat Enterprise Linux (RHEL).</span><span class="sxs-lookup"><span data-stu-id="57865-127">[Red Hat supports .NET Core](http://redhatloves.net/) on Red Hat Enterprise Linux (RHEL).</span></span> <span data-ttu-id="57865-128">Red Hat собирает .NET Core из исходного кода и публикует сборки на сайте [Red Hat Software Collections](https://developers.redhat.com/products/softwarecollections/overview/).</span><span class="sxs-lookup"><span data-stu-id="57865-128">Red Hat builds .NET Core from source and makes it available in the [Red Hat Software Collections](https://developers.redhat.com/products/softwarecollections/overview/).</span></span> <span data-ttu-id="57865-129">Red Hat и Майкрософт совместно занимаются обеспечением беспроблемной работы .NET Core в RHEL.</span><span class="sxs-lookup"><span data-stu-id="57865-129">Red Hat and Microsoft collaborate to ensure that .NET Core works well on RHEL.</span></span>
