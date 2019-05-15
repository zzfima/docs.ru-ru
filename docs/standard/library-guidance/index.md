---
title: Руководство по библиотекам .NET с открытым кодом
description: Рекомендации для разработчиков по созданию высококачественных библиотек .NET.
author: jamesnk
ms.author: mairaw
ms.date: 10/17/2018
ms.openlocfilehash: 85d76c8b2bd0f030e3fbc1987e6ff51d6da44e76
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65644387"
---
# <a name="open-source-library-guidance"></a><span data-ttu-id="7e9bf-103">Руководство по библиотекам с открытым исходным кодом</span><span class="sxs-lookup"><span data-stu-id="7e9bf-103">Open-source library guidance</span></span>

<span data-ttu-id="7e9bf-104">В этом руководстве приводятся рекомендации для разработчиков по созданию высококачественных библиотек .NET.</span><span class="sxs-lookup"><span data-stu-id="7e9bf-104">This guidance provides recommendations for developers to create high-quality .NET libraries.</span></span> <span data-ttu-id="7e9bf-105">Документация в основном освещает, *что* следует делать при создании библиотеки .NET и *почему*, не останавливаясь на *способах* достижения.</span><span class="sxs-lookup"><span data-stu-id="7e9bf-105">This documentation focuses on the *what* and the *why* when building a .NET library, not the *how*.</span></span>

<span data-ttu-id="7e9bf-106">Признаки высококачественных библиотек .NET с открытым исходным кодом:</span><span class="sxs-lookup"><span data-stu-id="7e9bf-106">Aspects of high-quality open-source .NET libraries:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="7e9bf-107">**Инклюзивные** — хорошие библиотеки .NET поддерживают разнообразные платформы, языки программирования и приложения.</span><span class="sxs-lookup"><span data-stu-id="7e9bf-107">**Inclusive** - Good .NET libraries strive to support many platforms, programming languages, and applications.</span></span>
> * <span data-ttu-id="7e9bf-108">**Стабильные** — хорошие библиотеки .NET сосуществуют в экосистеме .NET, позволяя запускать приложения, собранные с использованием множества библиотек.</span><span class="sxs-lookup"><span data-stu-id="7e9bf-108">**Stable** - Good .NET libraries coexist in the .NET ecosystem, running in applications built with many libraries.</span></span>
> * <span data-ttu-id="7e9bf-109">**Развивающиеся** — библиотеки .NET со временем должны улучшаться и совершенствоваться, одновременно предоставляя поддержку существующим пользователям.</span><span class="sxs-lookup"><span data-stu-id="7e9bf-109">**Designed to evolve** - .NET libraries should improve and evolve over time, while supporting existing users.</span></span>
> * <span data-ttu-id="7e9bf-110">**Отлаживаемые** — библиотеки .NET должны использовать новейшие средства для создания отличных возможностей отладки для пользователей.</span><span class="sxs-lookup"><span data-stu-id="7e9bf-110">**Debuggable** - .NET libraries should use the latest tools to create a great debugging experience for users.</span></span>
> * <span data-ttu-id="7e9bf-111">**Доверенные** — библиотеки .NET завоевывают доверие разработчиков, если публикуются в NuGet с использованием рекомендаций по безопасности.</span><span class="sxs-lookup"><span data-stu-id="7e9bf-111">**Trusted** - .NET libraries have developers' trust by publishing to NuGet using security best practices.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="7e9bf-112">Начало работы</span><span class="sxs-lookup"><span data-stu-id="7e9bf-112">Get Started</span></span>](./get-started.md)

## <a name="types-of-recommendations"></a><span data-ttu-id="7e9bf-113">Типы рекомендаций</span><span class="sxs-lookup"><span data-stu-id="7e9bf-113">Types of recommendations</span></span>

<span data-ttu-id="7e9bf-114">В каждой статье приводится список рекомендаций таких типов: **Do**, **Consider**, **Avoid** и **Do not**.</span><span class="sxs-lookup"><span data-stu-id="7e9bf-114">Each article presents four types of recommendations: **Do**, **Consider**, **Avoid**, and **Do not**.</span></span> <span data-ttu-id="7e9bf-115">Тип рекомендации свидетельствует о том, насколько строго следует придерживаться рекомендации.</span><span class="sxs-lookup"><span data-stu-id="7e9bf-115">The type of recommendation indicates how strongly it should be followed.</span></span>

<span data-ttu-id="7e9bf-116">Рекомендациям **Do** нужно следовать практически всегда.</span><span class="sxs-lookup"><span data-stu-id="7e9bf-116">You should almost always follow a **Do** recommendation.</span></span> <span data-ttu-id="7e9bf-117">Например:</span><span class="sxs-lookup"><span data-stu-id="7e9bf-117">For example:</span></span>

<span data-ttu-id="7e9bf-118">**✔️ DO** Распространение библиотеки с помощью пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="7e9bf-118">**✔️ DO** distribute your library using a NuGet package.</span></span>

<span data-ttu-id="7e9bf-119">Рекомендациям **Consider** обычно также нужно следовать, за некоторыми допустимыми исключениями. Если вы не придерживаетесь такой рекомендации, это не страшно:</span><span class="sxs-lookup"><span data-stu-id="7e9bf-119">On the other hand, **Consider** recommendations should generally be followed, but there are legitimate exceptions to the rule and you shouldn't feel bad about not following the guidance:</span></span>

<span data-ttu-id="7e9bf-120">**✔️ CONSIDER** Использование [SemVer 2.0.0](https://semver.org/) для управления версиями пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="7e9bf-120">**✔️ CONSIDER** using [SemVer 2.0.0](https://semver.org/) to version your NuGet package.</span></span>

<span data-ttu-id="7e9bf-121">Рекомендации **Avoid** обычно относятся к нежелательным действиям, но иногда их можно нарушать.</span><span class="sxs-lookup"><span data-stu-id="7e9bf-121">**Avoid** recommendations mention things that are generally not a good idea, but breaking the rule sometimes makes sense:</span></span>

<span data-ttu-id="7e9bf-122">**❌ AVOID** Ссылки на пакеты NuGet, требующие указания точной версии.</span><span class="sxs-lookup"><span data-stu-id="7e9bf-122">**❌ AVOID** NuGet package references that demand an exact version.</span></span>

<span data-ttu-id="7e9bf-123">Рекомендации **Do not** указывают на то, чего практически никогда не следует делать.</span><span class="sxs-lookup"><span data-stu-id="7e9bf-123">And finally, **Do not** recommendations indicate something you should almost never do:</span></span>

<span data-ttu-id="7e9bf-124">**❌ DO NOT** Публикация версий библиотеки со строгим и нестрогим именем.</span><span class="sxs-lookup"><span data-stu-id="7e9bf-124">**❌ DO NOT** publish strong-named and non-strong-named versions of your library.</span></span> <span data-ttu-id="7e9bf-125">Например, `Contoso.Api` и `Contoso.Api.StrongNamed`.</span><span class="sxs-lookup"><span data-stu-id="7e9bf-125">For example, `Contoso.Api` and `Contoso.Api.StrongNamed`.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="7e9bf-126">Вперед</span><span class="sxs-lookup"><span data-stu-id="7e9bf-126">Next</span></span>](get-started.md)
