---
title: Публикация пакета NuGet
description: Практические рекомендации для публикации библиотек .NET NuGet.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 0602712311411ef3d59825bec8c5e550bc8d8265
ms.sourcegitcommit: d88024e6d6d8b242feae5f4007a709379355aa24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2018
ms.locfileid: "49370325"
---
# <a name="publishing-a-nuget-package"></a><span data-ttu-id="6d333-103">Публикация пакета NuGet</span><span class="sxs-lookup"><span data-stu-id="6d333-103">Publishing a NuGet package</span></span>

<span data-ttu-id="6d333-104">Пакеты NuGet публикация и потребление из репозиториев пакета.</span><span class="sxs-lookup"><span data-stu-id="6d333-104">NuGet packages are published and consumed from package repositories.</span></span> <span data-ttu-id="6d333-105">Несмотря на то NuGet.org, наиболее широко известные и используется репозиторий существует много места для публикации пакетов NuGet:</span><span class="sxs-lookup"><span data-stu-id="6d333-105">While NuGet.org is the most widely known and used repository, there are many places to publish NuGet packages:</span></span>

* <span data-ttu-id="6d333-106">**[NuGet.org](https://www.nuget.org/)**  является основной веб-репозиторий пакетов NuGet.</span><span class="sxs-lookup"><span data-stu-id="6d333-106">**[NuGet.org](https://www.nuget.org/)** is the primary online repository for NuGet packages.</span></span> <span data-ttu-id="6d333-107">Все пакеты на сайте NuGet.org публично доступны всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="6d333-107">All packages on NuGet.org are publicly available to everyone.</span></span> <span data-ttu-id="6d333-108">По умолчанию Visual Studio имеет NuGet.org в качестве источника пакета, а для многих разработчиков NuGet.org — только репозиторий пакетов, которые они будет взаимодействовать с.</span><span class="sxs-lookup"><span data-stu-id="6d333-108">By default, Visual Studio has NuGet.org as a package source and for many developers NuGet.org is the only package repository they'll interact with.</span></span> <span data-ttu-id="6d333-109">NuGet.org — это лучшее место для публикации стабильные пакеты и пакеты предварительного выпуска, которые вы хотите отзывы и предложения сообщества на.</span><span class="sxs-lookup"><span data-stu-id="6d333-109">NuGet.org is the best place to publish stable packages and pre-release packages that you want community feedback on.</span></span>

* <span data-ttu-id="6d333-110">**[MyGet](https://myget.org/)**  поддерживает службы репозитория [бесплатный пакет пользовательских веб-каналы для проектов с открытым кодом](https://www.myget.org/opensource).</span><span class="sxs-lookup"><span data-stu-id="6d333-110">**[MyGet](https://myget.org/)** repository service supports [free custom package feeds for open-source projects](https://www.myget.org/opensource).</span></span> <span data-ttu-id="6d333-111">Общедоступный пользовательский канал MyGet — это идеальное место для публикации пакетов предварительных версий, созданных службы CI.</span><span class="sxs-lookup"><span data-stu-id="6d333-111">A MyGet public custom feed is an ideal place to publish pre-release packages created by your CI service.</span></span> <span data-ttu-id="6d333-112">MyGet также предоставляет закрытые веб-каналы имеющихся на рынке.</span><span class="sxs-lookup"><span data-stu-id="6d333-112">MyGet also provides private feeds commercially.</span></span>

* <span data-ttu-id="6d333-113">Объект **[локальный веб-канал](/nuget/hosting-packages/local-feeds)** позволяет обрабатывать папок как репозитория пакетов и делает `*.nupkg` файлы в папку, доступную с NuGet.</span><span class="sxs-lookup"><span data-stu-id="6d333-113">A **[local feed](/nuget/hosting-packages/local-feeds)** allows you to treat a folder like a package repository and makes the `*.nupkg` files in the folder accessible by NuGet.</span></span> <span data-ttu-id="6d333-114">Локальный веб-канал удобен для тестирования пакета NuGet до публикации на сайте NuGet.org.</span><span class="sxs-lookup"><span data-stu-id="6d333-114">A local feed is useful for testing a NuGet package before publishing it to NuGet.org.</span></span>

> [!NOTE]
> <span data-ttu-id="6d333-115">NuGet.org [не поддерживает пакет для удаления](/nuget/policies/deleting-packages) после его отправки.</span><span class="sxs-lookup"><span data-stu-id="6d333-115">NuGet.org [does not allow a package to be deleted](/nuget/policies/deleting-packages) once it is uploaded.</span></span> <span data-ttu-id="6d333-116">Пакет может быть удалена из списка, так как это не отображаемым в пользовательском Интерфейсе, но `*.nupkg` по-прежнему доступен для загрузки на восстановление.</span><span class="sxs-lookup"><span data-stu-id="6d333-116">A package can be unlisted so that it is not publicly visible in the UI but the `*.nupkg` can still be downloaded on restore.</span></span> <span data-ttu-id="6d333-117">Кроме того nuget.org не поддерживает версии дублирование пакета.</span><span class="sxs-lookup"><span data-stu-id="6d333-117">Also, nuget.org does not allow duplicate package versions.</span></span> <span data-ttu-id="6d333-118">Чтобы исправить это NuGet-пакет с ошибкой, необходимо удалить из списка Неверный пакет, увеличить номер версии и публиковать новые версии пакета.</span><span class="sxs-lookup"><span data-stu-id="6d333-118">To correct a NuGet package with an error you have to unlist the incorrect package, increment the version number and publish a new version of the package.</span></span>

<span data-ttu-id="6d333-119">**СДЕЛАТЬ ✔️** [публикации стабильные пакеты и пакеты предварительного выпуска](/nuget/create-packages/publish-a-package) требуется отзывы и предложения сообщества на сайте NuGet.org.</span><span class="sxs-lookup"><span data-stu-id="6d333-119">**✔️ DO** [publish stable packages and pre-release packages](/nuget/create-packages/publish-a-package) you want community feedback on to NuGet.org.</span></span>

<span data-ttu-id="6d333-120">**Рассмотрите ВОЗМОЖНОСТЬ ✔️** публикации пакетов предварительных версий MyGet веб-канала из сборки непрерывной интеграции.</span><span class="sxs-lookup"><span data-stu-id="6d333-120">**✔️ CONSIDER** publishing pre-release packages to a MyGet feed from a continuous integration build.</span></span>

<span data-ttu-id="6d333-121">**Рассмотрите ВОЗМОЖНОСТЬ ✔️** тестирования пакетов в среде разработки с помощью локального веб-канала или MyGet.</span><span class="sxs-lookup"><span data-stu-id="6d333-121">**✔️ CONSIDER** testing packages in your development environment using a local feed or MyGet.</span></span> <span data-ttu-id="6d333-122">Проверить их работоспособность пакета, а затем опубликовать его на сайте NuGet.org.</span><span class="sxs-lookup"><span data-stu-id="6d333-122">Check the package works then publish it to NuGet.org.</span></span>

## <a name="nugetorg-security"></a><span data-ttu-id="6d333-123">Безопасность NuGet.org</span><span class="sxs-lookup"><span data-stu-id="6d333-123">NuGet.org security</span></span>

<span data-ttu-id="6d333-124">Очень важно, что недобросовестных сторон не может доступа к учетной записи NuGet и отправить вредоносный версию библиотеки.</span><span class="sxs-lookup"><span data-stu-id="6d333-124">It's important that bad actors can't access your NuGet account and upload a malicious version of your library.</span></span> <span data-ttu-id="6d333-125">NuGet.org предлагает двухфакторной проверки подлинности и по электронной почте уведомления, когда пакет публикуется.</span><span class="sxs-lookup"><span data-stu-id="6d333-125">NuGet.org offers two-factor authentication and email notifications when a package is published.</span></span> <span data-ttu-id="6d333-126">Эти функции можно включить после входа в NuGet.org на **параметры учетной записи** страницы.</span><span class="sxs-lookup"><span data-stu-id="6d333-126">Enable these features after logging into NuGet.org on the **Account settings** page.</span></span>

<span data-ttu-id="6d333-127">![Замещающий текст](./media/publish-nuget-package/nuget-2fa.png "безопасность учетной записи NuGet")</span><span class="sxs-lookup"><span data-stu-id="6d333-127">![alt text](./media/publish-nuget-package/nuget-2fa.png "NuGet Account Security")</span></span>

<span data-ttu-id="6d333-128">**СДЕЛАТЬ ✔️** использовать учетную запись Майкрософт для входа в NuGet.</span><span class="sxs-lookup"><span data-stu-id="6d333-128">**✔️ DO** use a Microsoft account to sign in to NuGet.</span></span>

<span data-ttu-id="6d333-129">**СДЕЛАТЬ ✔️** включить двухфакторную проверку подлинности для доступа к NuGet.</span><span class="sxs-lookup"><span data-stu-id="6d333-129">**✔️ DO** enable two-factor authentication for accessing NuGet.</span></span>

<span data-ttu-id="6d333-130">**СДЕЛАТЬ ✔️** включить уведомления по электронной почте при публикации пакета.</span><span class="sxs-lookup"><span data-stu-id="6d333-130">**✔️ DO** enable email notification when a package is published.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="6d333-131">[Назад](./sourcelink.md)
[Вперед](./versioning.md)</span><span class="sxs-lookup"><span data-stu-id="6d333-131">[Previous](./sourcelink.md)
[Next](./versioning.md)</span></span>
