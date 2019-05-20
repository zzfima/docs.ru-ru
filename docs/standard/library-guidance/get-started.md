---
title: Приступая к созданию библиотек .NET высокого качества
description: Начало работы по созданию библиотек .NET.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 980f0edcee07688935f6d08f3ce1ed812159695e
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65640743"
---
# <a name="get-started"></a><span data-ttu-id="093eb-103">Начало работы</span><span class="sxs-lookup"><span data-stu-id="093eb-103">Get started</span></span>

## <a name="cross-platform-targetingcross-platform-targetingmd"></a>[<span data-ttu-id="093eb-104">Разработка для различных платформ</span><span class="sxs-lookup"><span data-stu-id="093eb-104">Cross-platform targeting</span></span>](./cross-platform-targeting.md)

<span data-ttu-id="093eb-105">Создание кроссплатформенных библиотек с помощью .NET Standard и многоплатформенного нацеливания.</span><span class="sxs-lookup"><span data-stu-id="093eb-105">How to use .NET Standard and multi-targeting to create cross-platform libraries.</span></span> <span data-ttu-id="093eb-106">.NET работает в разных средах, и правильная библиотека .NET должна поддерживать максимально возможное количество платформ и разработчиков.</span><span class="sxs-lookup"><span data-stu-id="093eb-106">.NET runs in many places, and good .NET libraries should strive to support as many platforms and developers as possible.</span></span>

## <a name="strong-namingstrong-namingmd"></a>[<span data-ttu-id="093eb-107">Строгое именование</span><span class="sxs-lookup"><span data-stu-id="093eb-107">Strong naming</span></span>](./strong-naming.md)

<span data-ttu-id="093eb-108">Сведения о строгом именовании, в том числе о его преимуществах и недостатках.</span><span class="sxs-lookup"><span data-stu-id="093eb-108">Learn about strong naming and its advantages and disadvantages.</span></span> <span data-ttu-id="093eb-109">Строгое именование для библиотеки .NET позволит большинству разработчиков использовать ее. Мы рекомендуем всегда использовать этот вариант.</span><span class="sxs-lookup"><span data-stu-id="093eb-109">Strong naming a .NET library allows the most developers to use it and is a recommended best practice.</span></span>

## <a name="nuget-and-open-source-librariesnugetmd"></a>[<span data-ttu-id="093eb-110">NuGet и библиотеки с открытым исходным кодом</span><span class="sxs-lookup"><span data-stu-id="093eb-110">NuGet and open-source libraries</span></span>](./nuget.md)

<span data-ttu-id="093eb-111">Описание лучшего метода создания пакетов NuGet для библиотек .NET с открытым кодом, в том числе рекомендации по метаданным для всех пакетов в открытом доступе на сайте NuGet.org.</span><span class="sxs-lookup"><span data-stu-id="093eb-111">The best way to create NuGet packages for open-source .NET libraries, including recommended metadata for all packages published publicly on NuGet.org.</span></span>

### <a name="dependenciesdependenciesmd"></a>[<span data-ttu-id="093eb-112">Зависимости</span><span class="sxs-lookup"><span data-stu-id="093eb-112">Dependencies</span></span>](./dependencies.md)

<span data-ttu-id="093eb-113">NuGet упрощает применение существующих пакетов при создании библиотеки .NET.</span><span class="sxs-lookup"><span data-stu-id="093eb-113">NuGet makes it easy to use existing packages when building a .NET library.</span></span> <span data-ttu-id="093eb-114">Здесь собраны сведения о распространенных источниках трудностей при создании зависимостей NuGet и рекомендации, позволяющие их избежать.</span><span class="sxs-lookup"><span data-stu-id="093eb-114">Learn about NuGet dependencies' common sources of friction and how to avoid them.</span></span>

### <a name="source-linksourcelinkmd"></a>[<span data-ttu-id="093eb-115">Ссылка на источник</span><span class="sxs-lookup"><span data-stu-id="093eb-115">Source Link</span></span>](./sourcelink.md)

<span data-ttu-id="093eb-116">Source Link является отличным средством, которое позволяет пользователям при отладке библиотеки .NET выполнять исходный код по шагам.</span><span class="sxs-lookup"><span data-stu-id="093eb-116">Source Link is a great tool that allows users of your .NET library to step into its source code while debugging.</span></span> <span data-ttu-id="093eb-117">Эта статья описывает назначение и преимущества Source Link.</span><span class="sxs-lookup"><span data-stu-id="093eb-117">This article is an overview of what Source Link is and why you should use it.</span></span>

### <a name="publishingpublish-nuget-packagemd"></a>[<span data-ttu-id="093eb-118">Публикация</span><span class="sxs-lookup"><span data-stu-id="093eb-118">Publishing</span></span>](./publish-nuget-package.md)

<span data-ttu-id="093eb-119">Конечно же, сайт nuget.org является самым известным и популярным репозиторием, но это не единственное средство для публикации пакетов NuGet.</span><span class="sxs-lookup"><span data-stu-id="093eb-119">While NuGet.org is the most widely known and used repository, there are many places to publish NuGet packages.</span></span> <span data-ttu-id="093eb-120">Узнайте, какие еще существуют репозитории для пакетов NuGet и получите рекомендации по обеспечению безопасности при публикации библиотек .NET.</span><span class="sxs-lookup"><span data-stu-id="093eb-120">Learn about the different NuGet package repositories available, and security best practices for publishing a .NET library.</span></span>

## <a name="versioningversioningmd"></a>[<span data-ttu-id="093eb-121">Управление версиями</span><span class="sxs-lookup"><span data-stu-id="093eb-121">Versioning</span></span>](./versioning.md)

<span data-ttu-id="093eb-122">Хорошая библиотека .NET постоянно развивается: в каждом очередном выпуске появляются новые функции, исправляются ошибки и повышается производительность.</span><span class="sxs-lookup"><span data-stu-id="093eb-122">Good .NET libraries evolve over time, adding features, fixing bugs, and improving performance in later releases.</span></span> <span data-ttu-id="093eb-123">Узнайте, как правильно использовать номера версий и сообщать разработчикам о наличии критических изменений.</span><span class="sxs-lookup"><span data-stu-id="093eb-123">Learn about the various version numbers and how to communicate breaking changes to developers.</span></span>

### <a name="breaking-changesbreaking-changesmd"></a>[<span data-ttu-id="093eb-124">Критические изменения</span><span class="sxs-lookup"><span data-stu-id="093eb-124">Breaking changes</span></span>](./breaking-changes.md)

<span data-ttu-id="093eb-125">При разработке библиотеки .NET очень важно сохранять правильный баланс между стабильностью для существующих пользователей и возможностью реализации новых функций.</span><span class="sxs-lookup"><span data-stu-id="093eb-125">It's important for a .NET library to find a balance between stability for existing users and innovation for the future.</span></span> <span data-ttu-id="093eb-126">Узнайте, какие бывают виды критических изменений и как правильно добавлять новые функции с сохранением обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="093eb-126">Learn about the different kinds of breaking changes and strategies for adding new features while maintaining backwards compatibility.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="093eb-127">[Назад](index.md)
>[Вперед](cross-platform-targeting.md)</span><span class="sxs-lookup"><span data-stu-id="093eb-127">[Previous](index.md)
[Next](cross-platform-targeting.md)</span></span>
