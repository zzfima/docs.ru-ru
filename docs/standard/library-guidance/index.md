---
title: Руководство по библиотекам .NET с открытым кодом
description: Рекомендации для разработчиков по созданию высококачественных библиотек .NET.
ms.date: 10/17/2018
ms.openlocfilehash: 4c76dfae6ffc39df7f15381be64e33657067d79d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "76731424"
---
# <a name="open-source-library-guidance"></a><span data-ttu-id="712d4-103">Руководство по библиотекам с открытым исходным кодом</span><span class="sxs-lookup"><span data-stu-id="712d4-103">Open-source library guidance</span></span>

<span data-ttu-id="712d4-104">В этом руководстве приводятся рекомендации для разработчиков по созданию высококачественных библиотек .NET.</span><span class="sxs-lookup"><span data-stu-id="712d4-104">This guidance provides recommendations for developers to create high-quality .NET libraries.</span></span> <span data-ttu-id="712d4-105">Документация в основном освещает, *что* следует делать при создании библиотеки .NET и *почему*, не останавливаясь на *способах* достижения.</span><span class="sxs-lookup"><span data-stu-id="712d4-105">This documentation focuses on the *what* and the *why* when building a .NET library, not the *how*.</span></span>

<span data-ttu-id="712d4-106">Признаки высококачественных библиотек .NET с открытым исходным кодом:</span><span class="sxs-lookup"><span data-stu-id="712d4-106">Aspects of high-quality open-source .NET libraries:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="712d4-107">**Инклюзивные** — хорошие библиотеки .NET поддерживают разнообразные платформы, языки программирования и приложения.</span><span class="sxs-lookup"><span data-stu-id="712d4-107">**Inclusive** - Good .NET libraries strive to support many platforms, programming languages, and applications.</span></span>
> * <span data-ttu-id="712d4-108">**Стабильные** — хорошие библиотеки .NET сосуществуют в экосистеме .NET, позволяя запускать приложения, собранные с использованием множества библиотек.</span><span class="sxs-lookup"><span data-stu-id="712d4-108">**Stable** - Good .NET libraries coexist in the .NET ecosystem, running in applications built with many libraries.</span></span>
> * <span data-ttu-id="712d4-109">**Развивающиеся** — библиотеки .NET со временем должны улучшаться и совершенствоваться, одновременно предоставляя поддержку существующим пользователям.</span><span class="sxs-lookup"><span data-stu-id="712d4-109">**Designed to evolve** - .NET libraries should improve and evolve over time, while supporting existing users.</span></span>
> * <span data-ttu-id="712d4-110">**Отлаживаемые** — библиотеки .NET должны использовать новейшие средства для создания отличных возможностей отладки для пользователей.</span><span class="sxs-lookup"><span data-stu-id="712d4-110">**Debuggable** - .NET libraries should use the latest tools to create a great debugging experience for users.</span></span>
> * <span data-ttu-id="712d4-111">**Доверенные** — библиотеки .NET завоевывают доверие разработчиков, если публикуются в NuGet с использованием рекомендаций по безопасности.</span><span class="sxs-lookup"><span data-stu-id="712d4-111">**Trusted** - .NET libraries have developers' trust by publishing to NuGet using security best practices.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="712d4-112">Начало работы</span><span class="sxs-lookup"><span data-stu-id="712d4-112">Get Started</span></span>](./get-started.md)

## <a name="types-of-recommendations"></a><span data-ttu-id="712d4-113">Типы рекомендаций</span><span class="sxs-lookup"><span data-stu-id="712d4-113">Types of recommendations</span></span>

<span data-ttu-id="712d4-114">В каждой статье приводится список рекомендаций таких типов: **Do**, **Consider**, **Avoid** и **Do not**.</span><span class="sxs-lookup"><span data-stu-id="712d4-114">Each article presents four types of recommendations: **Do**, **Consider**, **Avoid**, and **Do not**.</span></span> <span data-ttu-id="712d4-115">Тип рекомендации свидетельствует о том, насколько строго следует придерживаться рекомендации.</span><span class="sxs-lookup"><span data-stu-id="712d4-115">The type of recommendation indicates how strongly it should be followed.</span></span>

<span data-ttu-id="712d4-116">Рекомендациям **Do** нужно следовать практически всегда.</span><span class="sxs-lookup"><span data-stu-id="712d4-116">You should almost always follow a **Do** recommendation.</span></span> <span data-ttu-id="712d4-117">Пример:</span><span class="sxs-lookup"><span data-stu-id="712d4-117">For example:</span></span>

<span data-ttu-id="712d4-118">✔️ DO Распространение библиотеки с помощью пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="712d4-118">✔️ DO distribute your library using a NuGet package.</span></span>

<span data-ttu-id="712d4-119">Рекомендациям **Consider** обычно также нужно следовать, за некоторыми допустимыми исключениями. Если вы не придерживаетесь такой рекомендации, это не страшно:</span><span class="sxs-lookup"><span data-stu-id="712d4-119">On the other hand, **Consider** recommendations should generally be followed, but there are legitimate exceptions to the rule and you shouldn't feel bad about not following the guidance:</span></span>

<span data-ttu-id="712d4-120">✔️ CONSIDER Использование [SemVer 2.0.0](https://semver.org/) для управления версиями пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="712d4-120">✔️ CONSIDER using [SemVer 2.0.0](https://semver.org/) to version your NuGet package.</span></span>

<span data-ttu-id="712d4-121">Рекомендации **Avoid** обычно относятся к нежелательным действиям, но иногда их можно нарушать.</span><span class="sxs-lookup"><span data-stu-id="712d4-121">**Avoid** recommendations mention things that are generally not a good idea, but breaking the rule sometimes makes sense:</span></span>

<span data-ttu-id="712d4-122">❌ AVOID Ссылки на пакеты NuGet, требующие указания точной версии.</span><span class="sxs-lookup"><span data-stu-id="712d4-122">❌ AVOID NuGet package references that demand an exact version.</span></span>

<span data-ttu-id="712d4-123">Рекомендации **Do not** указывают на то, чего практически никогда не следует делать.</span><span class="sxs-lookup"><span data-stu-id="712d4-123">And finally, **Do not** recommendations indicate something you should almost never do:</span></span>

<span data-ttu-id="712d4-124">❌ DO NOT Не публикуйте версии библиотеки со строгим и нестрогим именем.</span><span class="sxs-lookup"><span data-stu-id="712d4-124">❌ DO NOT publish strong-named and non-strong-named versions of your library.</span></span> <span data-ttu-id="712d4-125">Например, `Contoso.Api` и `Contoso.Api.StrongNamed`.</span><span class="sxs-lookup"><span data-stu-id="712d4-125">For example, `Contoso.Api` and `Contoso.Api.StrongNamed`.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="712d4-126">Вперед</span><span class="sxs-lookup"><span data-stu-id="712d4-126">Next</span></span>](get-started.md)
