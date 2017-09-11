---
title: "Управление версиями зависимостей пакетов для .NET Core 1.0"
description: "В этой статье содержатся сведения об управлении версиями зависимостей пакетов для библиотек и приложений .NET Core."
keywords: .NET, .NET Core
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 4424a947-bdf9-4775-8d48-dc350a4e0aee
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 7f31aeb3c07a75059a4f8cd9392dcea31eb5bf41
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---

# <a name="how-to-manage-package-dependency-versions-for-net-core-10"></a><span data-ttu-id="c925c-104">Управление версиями зависимостей пакетов для .NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="c925c-104">How to Manage Package Dependency Versions for .NET Core 1.0</span></span>

<span data-ttu-id="c925c-105">В этой статье приводятся необходимые сведения о версиях пакетов для библиотек и приложений .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c925c-105">This article covers what you need to know about package versions for your .NET Core libraries and apps.</span></span>

## <a name="glossary"></a><span data-ttu-id="c925c-106">Глоссарий</span><span class="sxs-lookup"><span data-stu-id="c925c-106">Glossary</span></span>

<span data-ttu-id="c925c-107">**Исправление**. Под исправлением зависимостей понимается использование "семейства" пакетов, выпущенного в NuGet, для .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="c925c-107">**Fix** - Fixing dependencies means you are using the same "family" of packages released on NuGet for .NET Core 1.0.</span></span>

<span data-ttu-id="c925c-108">**Метапакет** — пакет NuGet, представляющий набор пакетов NuGet.</span><span class="sxs-lookup"><span data-stu-id="c925c-108">**Metapackage** - A NuGet package that represents a set of NuGet packages.</span></span>

<span data-ttu-id="c925c-109">**Усечение** — удаление пакетов, которые не используются, из метапакета.</span><span class="sxs-lookup"><span data-stu-id="c925c-109">**Trimming** - The act of removing the packages you do not depend on from a metapackage.</span></span>  <span data-ttu-id="c925c-110">Эта операция выполняется разработчиками пакетов NuGet.</span><span class="sxs-lookup"><span data-stu-id="c925c-110">This is something relevant for NuGet package authors.</span></span>  <span data-ttu-id="c925c-111">Дополнительные сведения см. в разделе [Сокращение зависимостей пакетов с помощью файла project.json](../deploying/reducing-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="c925c-111">See [Reducing Package Dependencies with project.json](../deploying/reducing-dependencies.md) for more information.</span></span> 

## <a name="fix-your-dependencies-to-net-core-10"></a><span data-ttu-id="c925c-112">Исправление зависимостей для .NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="c925c-112">Fix your dependencies to .NET Core 1.0</span></span>

<span data-ttu-id="c925c-113">Для надежного восстановления пакетов и написания надежного кода важно исправить зависимости до версий пакетов, поставляемых вместе с .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="c925c-113">To reliably restore packages and write reliable code, it's important that you fix your dependencies to the versions of packages shipping alongside .NET Core 1.0.</span></span>  <span data-ttu-id="c925c-114">Это означает, что каждый пакет должен иметь одну версию без дополнительных квалификаторов.</span><span class="sxs-lookup"><span data-stu-id="c925c-114">This means every package should have a single version with no additional qualifiers.</span></span>

<span data-ttu-id="c925c-115">**Примеры пакетов, исправленных до версии 1.0**</span><span class="sxs-lookup"><span data-stu-id="c925c-115">**Examples of packages fixed to 1.0**</span></span>

`"System.Collections":"4.0.11"`

`"NETStandard.Library":"1.6.0"`

`"Microsoft.NETCore.App":"1.0.0"`

<span data-ttu-id="c925c-116">**Примеры пакетов, которые НЕ исправлены до версии 1.0**</span><span class="sxs-lookup"><span data-stu-id="c925c-116">**Examples of packages that are NOT fixed to 1.0**</span></span>

`"Microsoft.NETCore.App":"1.0.0-rc4-00454-00"`

`"System.Net.Http":"4.1.0-*"`

`"System.Text.RegularExpressions":"4.0.10-rc3-24021-00"`

### <a name="why-does-this-matter"></a><span data-ttu-id="c925c-117">Почему это важно</span><span class="sxs-lookup"><span data-stu-id="c925c-117">Why does this matter?</span></span>

<span data-ttu-id="c925c-118">Мы гарантируем, что, если вы исправите зависимости до версий, поставляемых вместе с .NET Core 1.0, эти пакеты будут работать вместе.</span><span class="sxs-lookup"><span data-stu-id="c925c-118">We guarantee that if you fixed your dependencies to what ships alongside .NET Core 1.0, those packages will all work together.</span></span>  <span data-ttu-id="c925c-119">При использовании пакетов, которые не исправлены подобным образом, такой гарантии нет.</span><span class="sxs-lookup"><span data-stu-id="c925c-119">There is no such guarantee if you use packages which aren't fixed in this way.</span></span>

### <a name="scenarios"></a><span data-ttu-id="c925c-120">Сценарии</span><span class="sxs-lookup"><span data-stu-id="c925c-120">Scenarios</span></span>

<span data-ttu-id="c925c-121">Хотя список пакетов и их версий, выпускаемых с .NET Core 1.0, весьма велик, вам не придется изучать его полностью, если ваш код соответствует ряду условий.</span><span class="sxs-lookup"><span data-stu-id="c925c-121">Although there is a big list of all packages and their versions released with .NET Core 1.0, you may not have to look through it if your code falls under certain scenarios.</span></span>

<span data-ttu-id="c925c-122">**Используете ли вы только** `NETStandard.Library`**?**</span><span class="sxs-lookup"><span data-stu-id="c925c-122">**Are you depending only on** `NETStandard.Library`**?**</span></span>

<span data-ttu-id="c925c-123">Если да, пакет `NETStandard.Library` следует исправить до версии `1.6`.</span><span class="sxs-lookup"><span data-stu-id="c925c-123">If so, you should fixed your `NETStandard.Library` package to version `1.6`.</span></span>  <span data-ttu-id="c925c-124">Так как это проверенный метапакет, его оболочка также исправляется до версии 1.0.</span><span class="sxs-lookup"><span data-stu-id="c925c-124">Because this is a curated metapackage, its package closure is also fixed to 1.0.</span></span>

<span data-ttu-id="c925c-125">**Используете ли вы только** `Microsoft.NETCore.App`**?**</span><span class="sxs-lookup"><span data-stu-id="c925c-125">**Are you depending only on** `Microsoft.NETCore.App`**?**</span></span>

<span data-ttu-id="c925c-126">Если да, пакет `Microsoft.NETCore.App` следует исправить до версии `1.0.0`.</span><span class="sxs-lookup"><span data-stu-id="c925c-126">If so, you should fixed your `Microsoft.NETCore.App` package to version `1.0.0`.</span></span>  <span data-ttu-id="c925c-127">Так как это проверенный метапакет, его оболочка также исправляется до версии 1.0.</span><span class="sxs-lookup"><span data-stu-id="c925c-127">Because this is a curated metapackage, its package closure is also fixed to 1.0.</span></span>

<span data-ttu-id="c925c-128">**[Усекаете](../deploying/reducing-dependencies.md) ли вы зависимости метапакета** `NETStandard.Library` **или** `Microsoft.NETCore.App`**?**</span><span class="sxs-lookup"><span data-stu-id="c925c-128">**Are you [trimming](../deploying/reducing-dependencies.md) your** `NETStandard.Library` **or** `Microsoft.NETCore.App` **metapackage dependencies?**</span></span>

<span data-ttu-id="c925c-129">Если да, то используемый метапакет должен быть исправлен до версии 1.0.</span><span class="sxs-lookup"><span data-stu-id="c925c-129">If so, you should ensure that the metapackage you start with is fixed to 1.0.</span></span>  <span data-ttu-id="c925c-130">Отдельные пакеты, которые вы используете после усечения, также исправляются до версии 1.0.</span><span class="sxs-lookup"><span data-stu-id="c925c-130">The individual packages you depend on after trimming are also fixed to 1.0.</span></span>

<span data-ttu-id="c925c-131">**Используются ли пакеты вне метапакета** `NETStandard.Library` **или** `Microsoft.NETCore.App`**?**</span><span class="sxs-lookup"><span data-stu-id="c925c-131">**Are you depending on packages outside the** `NETStandard.Library` **or** `Microsoft.NETCore.App` **metapackages?**</span></span>

<span data-ttu-id="c925c-132">Если да, необходимо исправить остальные зависимости до версии 1.0.</span><span class="sxs-lookup"><span data-stu-id="c925c-132">If so, you need to fix your other dependencies to 1.0.</span></span>  <span data-ttu-id="c925c-133">Правильные версии пакетов и номера сборок см. в конце этой статьи.</span><span class="sxs-lookup"><span data-stu-id="c925c-133">See the correct package versions and build numbers at the end of this article.</span></span>

### <a name="a-note-on-using-a-splat-string--when-versioning"></a><span data-ttu-id="c925c-134">Замечание об использовании строки со звездочкой (\*) при управлении версиями</span><span class="sxs-lookup"><span data-stu-id="c925c-134">A note on using a splat string (\*) when versioning</span></span>

<span data-ttu-id="c925c-135">Возможно, вы применяете шаблон управления версиями, предусматривающий использование строки со звездочкой (\*) наподобие следующей: `"System.Collections":"4.0.11-*"`.</span><span class="sxs-lookup"><span data-stu-id="c925c-135">You may have adopted a versioning pattern which uses a splat (\*) string like this: `"System.Collections":"4.0.11-*"`.</span></span>

<span data-ttu-id="c925c-136">**Этого не следует делать**.</span><span class="sxs-lookup"><span data-stu-id="c925c-136">**You should not do this**.</span></span>  <span data-ttu-id="c925c-137">Использование строки со звездочкой может привести к восстановлению пакетов из разных сборок, некоторые из которых могут быть более поздними, чем выпускаемые с .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="c925c-137">Using the splat string could result in restoring packages from different builds, some of which may be further along than .NET Core 1.0.</span></span>  <span data-ttu-id="c925c-138">Это, в свою очередь, может привести к несовместимости некоторых пакетов.</span><span class="sxs-lookup"><span data-stu-id="c925c-138">This could then result in some packages being incompatible.</span></span>

## <a name="packages-and-version-numbers-organized-by-metapackage"></a><span data-ttu-id="c925c-139">Пакеты и номера версий по метапакетам</span><span class="sxs-lookup"><span data-stu-id="c925c-139">Packages and Version Numbers organized by Metapackage</span></span>

<span data-ttu-id="c925c-140">[Список всех пакетов .NET Standard и их версий для 1.0](https://github.com/dotnet/versions/blob/master/build-info/dotnet/corefx/release/1.0.0/Latest_Packages.txt).</span><span class="sxs-lookup"><span data-stu-id="c925c-140">[List of all .NET Standard packages and their versions for 1.0](https://github.com/dotnet/versions/blob/master/build-info/dotnet/corefx/release/1.0.0/Latest_Packages.txt).</span></span>

<span data-ttu-id="c925c-141">[Список всех пакетов среды выполнения и их версий для 1.0](https://github.com/dotnet/versions/blob/master/build-info/dotnet/coreclr/release/1.0.0/LKG_Packages.txt).</span><span class="sxs-lookup"><span data-stu-id="c925c-141">[List of all runtime packages and their versions for 1.0](https://github.com/dotnet/versions/blob/master/build-info/dotnet/coreclr/release/1.0.0/LKG_Packages.txt).</span></span>

<span data-ttu-id="c925c-142">[Список всех пакетов приложений .NET Core и их версий для 1.0](https://github.com/dotnet/versions/blob/master/build-info/dotnet/core-setup/release/1.0.0/Latest_Packages.txt).</span><span class="sxs-lookup"><span data-stu-id="c925c-142">[List of all .NET Core application packages and their versions for 1.0](https://github.com/dotnet/versions/blob/master/build-info/dotnet/core-setup/release/1.0.0/Latest_Packages.txt).</span></span>

