---
title: Руководство по библиотекам с открытым исходным кодом
description: Рекомендации для разработчиков по созданию высококачественных библиотек .NET.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 50fb745f7eb65abcaca76cebaf9991c48f559e59
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2018
ms.locfileid: "49374912"
---
# <a name="open-source-library-guidance"></a><span data-ttu-id="e2c4c-103">Руководство по библиотекам с открытым исходным кодом</span><span class="sxs-lookup"><span data-stu-id="e2c4c-103">Open-source library guidance</span></span>

<span data-ttu-id="e2c4c-104">В этом руководстве приводятся рекомендации для разработчиков по созданию высококачественных библиотек .NET.</span><span class="sxs-lookup"><span data-stu-id="e2c4c-104">This guidance provides recommendations for developers to create high-quality .NET libraries.</span></span> <span data-ttu-id="e2c4c-105">Документация в основном освещает, *что* следует делать при создании библиотеки .NET и *почему*, не останавливаясь на *способах* достижения.</span><span class="sxs-lookup"><span data-stu-id="e2c4c-105">This documentation focuses on the *what* and the *why* when building a .NET library, not the *how*.</span></span>

<span data-ttu-id="e2c4c-106">Признаки высококачественных библиотек .NET с открытым исходным кодом:</span><span class="sxs-lookup"><span data-stu-id="e2c4c-106">Aspects of high-quality open-source .NET libraries:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="e2c4c-107">**Инклюзивные** — хорошие библиотеки .NET поддерживают множество платформ и приложений.</span><span class="sxs-lookup"><span data-stu-id="e2c4c-107">**Inclusive** - Good .NET libraries strive to support many platforms and applications.</span></span>
> * <span data-ttu-id="e2c4c-108">**Стабильные** — хорошие библиотеки .NET сосуществуют в экосистеме .NET, позволяя запускать приложения, собранные с использованием множества библиотек.</span><span class="sxs-lookup"><span data-stu-id="e2c4c-108">**Stable** - Good .NET libraries coexist in the .NET ecosystem, running in applications built with many libraries.</span></span>
> * <span data-ttu-id="e2c4c-109">**Развивающиеся** — библиотеки .NET со временем должны улучшаться и совершенствоваться, одновременно предоставляя поддержку существующим пользователям.</span><span class="sxs-lookup"><span data-stu-id="e2c4c-109">**Designed to evolve** - .NET libraries should improve and evolve over time, while supporting existing users.</span></span>
> * <span data-ttu-id="e2c4c-110">**Отлаживаемые** — библиотеки .NET должны использовать новейшие средства для создания отличных возможностей отладки для пользователей.</span><span class="sxs-lookup"><span data-stu-id="e2c4c-110">**Debuggable** - .NET libraries should use the latest tools to create a great debugging experience for users.</span></span>
> * <span data-ttu-id="e2c4c-111">**Доверенные** — библиотеки .NET завоевывают доверие разработчиков, если публикуются в NuGet с использованием рекомендаций по безопасности.</span><span class="sxs-lookup"><span data-stu-id="e2c4c-111">**Trusted** - .NET libraries have developers' trust by publishing to NuGet using security best practices.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e2c4c-112">Начало работы</span><span class="sxs-lookup"><span data-stu-id="e2c4c-112">Get Started</span></span>](./get-started.md)

## <a name="recommendations"></a><span data-ttu-id="e2c4c-113">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="e2c4c-113">Recommendations</span></span>

<span data-ttu-id="e2c4c-114">В каждой статье приводится список рекомендаций для библиотек .NET с категориями **Do**, **Consider**, **Avoid** и **Do not**.</span><span class="sxs-lookup"><span data-stu-id="e2c4c-114">With each article, there is a list of recommendations for your .NET library using **Do**, **Consider**, **Avoid**, and **Do not**.</span></span> <span data-ttu-id="e2c4c-115">Формулировка каждой рекомендации показывает, насколько строго ее следует придерживаться.</span><span class="sxs-lookup"><span data-stu-id="e2c4c-115">The wording of each recommendation indicates how strongly it should be followed.</span></span>

<span data-ttu-id="e2c4c-116">Рекомендациям **Do** нужно следовать практически всегда:</span><span class="sxs-lookup"><span data-stu-id="e2c4c-116">A **Do** recommendation is one that should almost always be followed:</span></span>

<span data-ttu-id="e2c4c-117">**✔️ DO** Распространение библиотеки с помощью пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="e2c4c-117">**✔️ DO** distribute your library using a NuGet package.</span></span>

<span data-ttu-id="e2c4c-118">Рекомендациям **Consider** обычно также нужно следовать, за некоторыми допустимыми исключениями. Если вы не придерживаетесь такой рекомендации, это не страшно:</span><span class="sxs-lookup"><span data-stu-id="e2c4c-118">On the other hand, **Consider** recommendations should generally be followed, but there are legitimate exceptions to the rule and you shouldn't feel bad about not following the guidance:</span></span>

<span data-ttu-id="e2c4c-119">**✔️ CONSIDER** Использование [SemVer 2.0.0](https://semver.org/) для управления версиями пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="e2c4c-119">**✔️ CONSIDER** using [SemVer 2.0.0](https://semver.org/) to version your NuGet package.</span></span>

<span data-ttu-id="e2c4c-120">Рекомендации **Avoid** обычно относятся к нежелательным действиям, но иногда их можно нарушать:</span><span class="sxs-lookup"><span data-stu-id="e2c4c-120">**Avoid** recommendations are things that are generally not a good idea, but breaking the rule sometimes makes sense:</span></span>

<span data-ttu-id="e2c4c-121">**❌ AVOID** Ссылки на пакеты NuGet, требующие указания точной версии.</span><span class="sxs-lookup"><span data-stu-id="e2c4c-121">**❌ AVOID** NuGet package references that demand an exact version.</span></span>

<span data-ttu-id="e2c4c-122">Наконец, **do not** указывает на то, что практически никогда не следует делать:</span><span class="sxs-lookup"><span data-stu-id="e2c4c-122">And finally, **do not** indicates something you should almost never do:</span></span>

<span data-ttu-id="e2c4c-123">**❌ DO NOT** Публикация версий библиотеки со строгим и нестрогим именем.</span><span class="sxs-lookup"><span data-stu-id="e2c4c-123">**❌ DO NOT** publish strong-named and non-strong-named versions of your library.</span></span> <span data-ttu-id="e2c4c-124">Например, `Contoso.Api` и `Contoso.Api.StrongNamed`.</span><span class="sxs-lookup"><span data-stu-id="e2c4c-124">For example, `Contoso.Api` and `Contoso.Api.StrongNamed`.</span></span>

>[!div class="step-by-step"]
[<span data-ttu-id="e2c4c-125">Вперед</span><span class="sxs-lookup"><span data-stu-id="e2c4c-125">Next</span></span>](./get-started.md)
