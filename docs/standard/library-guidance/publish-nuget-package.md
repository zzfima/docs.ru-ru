---
title: Публикация пакета NuGet
description: Рекомендации по публикации .NET-библиотек в NuGet.
ms.date: 10/02/2018
ms.openlocfilehash: 089c660bc51252c6295858b1462ae59bde968564
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744555"
---
# <a name="publishing-a-nuget-package"></a><span data-ttu-id="9b479-103">Публикация пакета NuGet</span><span class="sxs-lookup"><span data-stu-id="9b479-103">Publishing a NuGet package</span></span>

<span data-ttu-id="9b479-104">Пакеты NuGet публикуются и загружаются в репозиториях.</span><span class="sxs-lookup"><span data-stu-id="9b479-104">NuGet packages are published and consumed from package repositories.</span></span> <span data-ttu-id="9b479-105">Самым известным и часто используемым репозиторием является портал NuGet.org, но существует множество мест для публикации пакетов:</span><span class="sxs-lookup"><span data-stu-id="9b479-105">While NuGet.org is the most widely known and used repository, there are many places to publish NuGet packages:</span></span>

* <span data-ttu-id="9b479-106">**[NuGet.org](https://www.nuget.org/)**  — это главный репозиторий пакетов NuGet в Интернете.</span><span class="sxs-lookup"><span data-stu-id="9b479-106">**[NuGet.org](https://www.nuget.org/)** is the primary online repository for NuGet packages.</span></span> <span data-ttu-id="9b479-107">Все пакеты NuGet.org находятся в открытом доступе.</span><span class="sxs-lookup"><span data-stu-id="9b479-107">All packages on NuGet.org are publicly available to everyone.</span></span> <span data-ttu-id="9b479-108">Портал NuGet.org является источником пакетов по умолчанию в Visual Studio, и многие разработчики работают только с этим репозиторием.</span><span class="sxs-lookup"><span data-stu-id="9b479-108">By default, Visual Studio has NuGet.org as a package source and for many developers NuGet.org is the only package repository they'll interact with.</span></span> <span data-ttu-id="9b479-109">NuGet.org — лучшее место для публикации стабильных пакетов, а также предварительных выпусков, по которым вы хотите получить обратную связь.</span><span class="sxs-lookup"><span data-stu-id="9b479-109">NuGet.org is the best place to publish stable packages and pre-release packages that you want community feedback on.</span></span>

* <span data-ttu-id="9b479-110">**[MyGet](https://myget.org/)**  — это служба репозиториев, поддерживающая пользовательские веб-каналы пакетов для проектов с открытым кодом.</span><span class="sxs-lookup"><span data-stu-id="9b479-110">**[MyGet](https://myget.org/)** is a repository service that supports custom package feeds for open-source projects.</span></span> <span data-ttu-id="9b479-111">Общедоступный пользовательский веб-канал MyGet — идеальное место для публикации предварительных выпусков пакетов, создаваемых вашей службой непрерывной интеграции.</span><span class="sxs-lookup"><span data-stu-id="9b479-111">A MyGet public custom feed is an ideal place to publish pre-release packages created by your CI service.</span></span> <span data-ttu-id="9b479-112">MyGet также предлагает платные закрытые каналы.</span><span class="sxs-lookup"><span data-stu-id="9b479-112">MyGet also provides private feeds commercially.</span></span>

* <span data-ttu-id="9b479-113">**[Локальный веб-канал](/nuget/hosting-packages/local-feeds)** позволяет создать пакетный репозиторий из обычной папки и сделать ее файлы `*.nupkg` доступными в NuGet.</span><span class="sxs-lookup"><span data-stu-id="9b479-113">A **[local feed](/nuget/hosting-packages/local-feeds)** allows you to treat a folder like a package repository and makes the `*.nupkg` files in the folder accessible by NuGet.</span></span> <span data-ttu-id="9b479-114">Это удобно для тестирования пакета NuGet перед публикацией на NuGet.org.</span><span class="sxs-lookup"><span data-stu-id="9b479-114">A local feed is useful for testing a NuGet package before publishing it to NuGet.org.</span></span>

> [!NOTE]
> <span data-ttu-id="9b479-115">NuGet.org [не позволяет удалять пакеты](/nuget/policies/deleting-packages) после публикации.</span><span class="sxs-lookup"><span data-stu-id="9b479-115">NuGet.org [does not allow a package to be deleted](/nuget/policies/deleting-packages) once it is uploaded.</span></span> <span data-ttu-id="9b479-116">Пакет можно скрыть из общедоступного списка в пользовательском интерфейсе, однако файл `*.nupkg` по-прежнему доступен для загрузки при операции восстановления.</span><span class="sxs-lookup"><span data-stu-id="9b479-116">A package can be unlisted so that it is not publicly visible in the UI but the `*.nupkg` can still be downloaded on restore.</span></span> <span data-ttu-id="9b479-117">Кроме того, NuGet.org не поддерживает дублирование версий пакетов.</span><span class="sxs-lookup"><span data-stu-id="9b479-117">Also, nuget.org does not allow duplicate package versions.</span></span> <span data-ttu-id="9b479-118">Чтобы исправить пакет NuGet, содержащий ошибку, необходимо скрыть его из списка, увеличить номер версии и опубликовать новую версию пакета.</span><span class="sxs-lookup"><span data-stu-id="9b479-118">To correct a NuGet package with an error you have to unlist the incorrect package, increment the version number and publish a new version of the package.</span></span>

<span data-ttu-id="9b479-119">✔️ СЛЕДУЕТ [опубликовать стабильные пакеты и предварительные выпуски пакетов](/nuget/create-packages/publish-a-package), по которым нужна обратная связь, на NuGet.org.</span><span class="sxs-lookup"><span data-stu-id="9b479-119">✔️ DO [publish stable packages and pre-release packages](/nuget/create-packages/publish-a-package) you want community feedback on to NuGet.org.</span></span>

<span data-ttu-id="9b479-120">✔️ РЕКОМЕНДУЕТСЯ публиковать предварительные выпуски пакетов из сборки непрерывной интеграции в канале MyGet.</span><span class="sxs-lookup"><span data-stu-id="9b479-120">✔️ CONSIDER publishing pre-release packages to a MyGet feed from a continuous integration build.</span></span>

<span data-ttu-id="9b479-121">✔️ РЕКОМЕНДУЕТСЯ тестировать пакеты в собственной среде разработки с помощью локального веб-канала или MyGet.</span><span class="sxs-lookup"><span data-stu-id="9b479-121">✔️ CONSIDER testing packages in your development environment using a local feed or MyGet.</span></span> <span data-ttu-id="9b479-122">Проверьте, что пакет работает, а затем опубликуйте его на NuGet.org.</span><span class="sxs-lookup"><span data-stu-id="9b479-122">Check the package works then publish it to NuGet.org.</span></span>

## <a name="nugetorg-security"></a><span data-ttu-id="9b479-123">Безопасность NuGet.org</span><span class="sxs-lookup"><span data-stu-id="9b479-123">NuGet.org security</span></span>

<span data-ttu-id="9b479-124">Очень важно обеспечить защиту вашей учетной записи NuGet, чтобы злоумышленники не могли получить к ней доступ и выложить вредоносную версию вашей библиотеки.</span><span class="sxs-lookup"><span data-stu-id="9b479-124">It's important that bad actors can't access your NuGet account and upload a malicious version of your library.</span></span> <span data-ttu-id="9b479-125">NuGet.org поддерживает двухфакторную проверку подлинности и уведомления по электронной почте при публикации пакетов.</span><span class="sxs-lookup"><span data-stu-id="9b479-125">NuGet.org offers two-factor authentication and email notifications when a package is published.</span></span> <span data-ttu-id="9b479-126">Вы можете включить эти функции, выполнив вход в NuGet.org и зайдя на страницу **Параметров учетной записи**.</span><span class="sxs-lookup"><span data-stu-id="9b479-126">Enable these features after logging into NuGet.org on the **Account settings** page.</span></span>

<span data-ttu-id="9b479-127">![alt text](./media/publish-nuget-package/nuget-2fa.png "Безопасность учетной записи NuGet")</span><span class="sxs-lookup"><span data-stu-id="9b479-127">![alt text](./media/publish-nuget-package/nuget-2fa.png "NuGet Account Security")</span></span>

<span data-ttu-id="9b479-128">✔️ СЛЕДУЕТ использовать учетную запись Майкрософт для входа в NuGet.</span><span class="sxs-lookup"><span data-stu-id="9b479-128">✔️ DO use a Microsoft account to sign in to NuGet.</span></span>

<span data-ttu-id="9b479-129">✔️ СЛЕДУЕТ включить в NuGet двухфакторную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="9b479-129">✔️ DO enable two-factor authentication for accessing NuGet.</span></span>

<span data-ttu-id="9b479-130">✔️ СЛЕДУЕТ включить уведомления по электронной почте при публикации пакета.</span><span class="sxs-lookup"><span data-stu-id="9b479-130">✔️ DO enable email notification when a package is published.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="9b479-131">[Назад](sourcelink.md)
>[Вперед](versioning.md)</span><span class="sxs-lookup"><span data-stu-id="9b479-131">[Previous](sourcelink.md)
[Next](versioning.md)</span></span>
