---
title: "Совместимость приложений в .NET Framework"
ms.custom: 
ms.date: 05/19/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
- app-compat
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application compatibility
- .NET Framework application compatibility
- .NET Framework changes
caps.latest.revision: "19"
ms.assetid: c4ba3ff2-fe59-4c5d-9e0b-86bba3cd865c
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e67fff19c4b187010b35519081f46e11effbad6c
ms.sourcegitcommit: d0f7646d67db5809cf43ff1d27b399a4020e8ee2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2017
---
# <a name="application-compatibility-in-the-net-framework"></a><span data-ttu-id="ca22e-102">Совместимость приложений в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ca22e-102">Application Compatibility in the .NET Framework</span></span>

## <a name="introduction"></a><span data-ttu-id="ca22e-103">Вступление</span><span class="sxs-lookup"><span data-stu-id="ca22e-103">Introduction</span></span>
<span data-ttu-id="ca22e-104">Важной задачей каждого выпуска .NET является совместимость.</span><span class="sxs-lookup"><span data-stu-id="ca22e-104">Compatibility is a very important goal of each .NET release.</span></span> <span data-ttu-id="ca22e-105">Совместимость гарантирует, что каждая версия дополняет предыдущие и позволяет им работать так же, как и раньше.</span><span class="sxs-lookup"><span data-stu-id="ca22e-105">Compatibility ensures that each version is additive, so previous versions will still work.</span></span> <span data-ttu-id="ca22e-106">С другой стороны, изменения в функциях по сравнению с предыдущими версиями (для улучшения производительности, устранения проблем с безопасностью или исправления ошибок) могут привести к проблемам совместимости в существующем коде или приложениях, которые запускаются в более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="ca22e-106">On the other hand, changes to previous functionality (to improve performance, address security issues, or fix bugs) can cause compatibility problems in existing code or existing applications that run under a later version.</span></span> <span data-ttu-id="ca22e-107">Платформа .NET Framework учитывает изменения целевой платформы и среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="ca22e-107">The .NET Framework recognizes retargeting changes and runtime changes.</span></span> <span data-ttu-id="ca22e-108">Изменения целевой платформы влияют на приложения, разработанные для конкретной версии .NET Framework, но запускаемые на более поздней версии платформы.</span><span class="sxs-lookup"><span data-stu-id="ca22e-108">Retargeting changes affect applications that target a specific version of the .NET Framework but are running on a later version.</span></span> <span data-ttu-id="ca22e-109">Изменения среды выполнения влияют на все приложения, запускаемые на конкретной версии платформы.</span><span class="sxs-lookup"><span data-stu-id="ca22e-109">Runtime changes affect all applications running on a particular version.</span></span>

<span data-ttu-id="ca22e-110">Каждое приложение разрабатывается для конкретной версии платформы .NET Framework, которую можно указать следующими способами.</span><span class="sxs-lookup"><span data-stu-id="ca22e-110">Each app targets a specific version of the .NET Framework, which can be specified by:</span></span>

* <span data-ttu-id="ca22e-111">Назначив требуемую версию .NET Framework в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ca22e-111">Defining a target framework in Visual Studio.</span></span>
* <span data-ttu-id="ca22e-112">Указав требуемую версию .NET Framework в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="ca22e-112">Specifying the target framework in a project file.</span></span>
* <span data-ttu-id="ca22e-113">Применив <xref:System.Runtime.Versioning.TargetFrameworkAttribute> к исходному коду.</span><span class="sxs-lookup"><span data-stu-id="ca22e-113">Applying a <xref:System.Runtime.Versioning.TargetFrameworkAttribute> to the source code.</span></span>

<span data-ttu-id="ca22e-114">При использовании более новой версии .NET Framework по сравнению с целевой, платформа будет имитировать поведение старой целевой версии.</span><span class="sxs-lookup"><span data-stu-id="ca22e-114">When running on a newer version than what was targeted, the .NET Framework will use quirked behavior to mimic the older targeted version.</span></span> <span data-ttu-id="ca22e-115">Другими словами, приложение будет запущено на более новой версии платформы, но будет работать так, как если бы оно было запущено на более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="ca22e-115">In other words, the app will run on the newer version of the Framework, but act as if it's running on the older version.</span></span> <span data-ttu-id="ca22e-116">Такая имитация позволяет устранить многие проблемы совместимости между версиями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ca22e-116">Many of the compatibility issues between versions of the .NET Framework are mitigated through this quirking model.</span></span>

## <a name="runtime-changes"></a><span data-ttu-id="ca22e-117">Изменения в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="ca22e-117">Runtime changes</span></span>

<span data-ttu-id="ca22e-118">Проблемы среды выполнения возникают, когда на компьютере устанавливается новая среда выполнения и запускаются те же двоичные файлы, но наблюдается другое поведение.</span><span class="sxs-lookup"><span data-stu-id="ca22e-118">Runtime issues are those that arise when a new runtime is placed on a machine and the same binaries are run, but different behavior is seen.</span></span> <span data-ttu-id="ca22e-119">Если двоичный файл был скомпилирован для платформы .NET Framework 4.0, он будет запускаться на платформе .NET Framework 4.5 и в более поздних версиях в режиме совместимости с .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="ca22e-119">If a binary was compiled for .NET Framework 4.0 it will run in .NET Framework 4.0 compatibility mode on 4.5 or later versions.</span></span> <span data-ttu-id="ca22e-120">Многие изменения, затрагивающие версию 4.5, не повлияют на двоичный файл, скомпилированный для версии 4.0.</span><span class="sxs-lookup"><span data-stu-id="ca22e-120">Many of the changes that affect 4.5 will not affect a binary compiled for 4.0.</span></span> <span data-ttu-id="ca22e-121">Это относится к домену приложения и зависит от параметров начальной сборки.</span><span class="sxs-lookup"><span data-stu-id="ca22e-121">This is specific to the AppDomain and depends on the settings of the entry assembly.</span></span>

## <a name="retargeting-changes"></a><span data-ttu-id="ca22e-122">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="ca22e-122">Retargeting changes</span></span>

<span data-ttu-id="ca22e-123">Проблемы, связанные с изменением целевой платформы, возникают, когда для сборки с целевой платформой 4.0 устанавливается целевая платформа 4.5.</span><span class="sxs-lookup"><span data-stu-id="ca22e-123">Retargeting issues are those that arise when an assembly that was targeting 4.0 is now set to target 4.5.</span></span> <span data-ttu-id="ca22e-124">Теперь в сборке доступны новые возможности, но могут возникнуть и проблемы совместимости со старыми функциями.</span><span class="sxs-lookup"><span data-stu-id="ca22e-124">Now the assembly opts into the new features as well as potential compatibility issues to old features.</span></span> <span data-ttu-id="ca22e-125">Опять же, это зависит от начальной сборки и распространяется на консольное приложение, которое использует сборку, или веб-сайт, который ссылается на сборку.</span><span class="sxs-lookup"><span data-stu-id="ca22e-125">Again, this is dictated by the entry assembly, so the console app that uses the assembly, or the website that references the assembly.</span></span>

## <a name="net-compatibility-diagnostics"></a><span data-ttu-id="ca22e-126">Диагностика совместимости .NET</span><span class="sxs-lookup"><span data-stu-id="ca22e-126">.NET Compatibility Diagnostics</span></span>

<span data-ttu-id="ca22e-127">Диагностика совместимости .NET выполняется с помощью анализаторов на базе Roslyn, которые помогают выявить проблемы совместимости приложений между версиями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ca22e-127">The .NET Compatibility Diagnostics are Roslyn-powered analyzers that help identify application compatibility issues between versions of the .NET Framework.</span></span> <span data-ttu-id="ca22e-128">Этот список содержит все доступные анализаторы, несмотря на то, что в рамках конкретной миграции будут действовать только некоторые из них.</span><span class="sxs-lookup"><span data-stu-id="ca22e-128">This list contains all of the analyzers available, although only a subset will apply to any specific migration.</span></span> <span data-ttu-id="ca22e-129">Анализаторы определят, какие проблемы применимы для запланированного переноса и будут исследовать только их.</span><span class="sxs-lookup"><span data-stu-id="ca22e-129">The analyzers will determine which issues are applicable for the planned migration and will only surface those.</span></span>

<span data-ttu-id="ca22e-130">Каждая проблема содержит следующую информацию.</span><span class="sxs-lookup"><span data-stu-id="ca22e-130">Each issue includes the following information:</span></span>

-   <span data-ttu-id="ca22e-131">Описание того, что изменилось по сравнению с предыдущей версией.</span><span class="sxs-lookup"><span data-stu-id="ca22e-131">The description of what has changed from a previous version.</span></span>

-   <span data-ttu-id="ca22e-132">Сведения о влиянии изменения на клиентов, а также о наличии обходных путей для сохранения совместимости между версиями.</span><span class="sxs-lookup"><span data-stu-id="ca22e-132">How the change affects customers and whether any workarounds are available to preserve compatibility across versions.</span></span>

-   <span data-ttu-id="ca22e-133">Оценка степени важности изменения.</span><span class="sxs-lookup"><span data-stu-id="ca22e-133">An assessment of how important the change is.</span></span> <span data-ttu-id="ca22e-134">Проблемы совместимости приложений делятся на следующие категории.</span><span class="sxs-lookup"><span data-stu-id="ca22e-134">Application compatibility issue are categorized as follows:</span></span>

    |   |   |
    |---|---|
    |<span data-ttu-id="ca22e-135">Значительно</span><span class="sxs-lookup"><span data-stu-id="ca22e-135">Major</span></span>|<span data-ttu-id="ca22e-136">Значительное изменение, влияющее на большое количество приложений или требующее существенного изменения кода.</span><span class="sxs-lookup"><span data-stu-id="ca22e-136">A significant change that affects a large number of apps or requires substantial modification of code.</span></span>|
    |<span data-ttu-id="ca22e-137">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="ca22e-137">Minor</span></span>|<span data-ttu-id="ca22e-138">Изменение, влияющее на небольшое количество приложений или требующее незначительного изменения кода.</span><span class="sxs-lookup"><span data-stu-id="ca22e-138">A change that affects a small number of apps or that requires minor modification of code.</span></span>|
    |<span data-ttu-id="ca22e-139">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="ca22e-139">Edge case</span></span>|<span data-ttu-id="ca22e-140">Изменение, влияющее на приложения в исключительных ситуациях.</span><span class="sxs-lookup"><span data-stu-id="ca22e-140">A change that affects apps under very specific, uncommon scenarios.</span></span>|
    |<span data-ttu-id="ca22e-141">Прозрачный</span><span class="sxs-lookup"><span data-stu-id="ca22e-141">Transparent</span></span>|<span data-ttu-id="ca22e-142">Изменение без заметного влияния на разработчика или пользователя приложения.</span><span class="sxs-lookup"><span data-stu-id="ca22e-142">A change with no noticeable effect on the application's developer or user.</span></span>|

-   <span data-ttu-id="ca22e-143">Версия указывает, когда изменение впервые появилось на платформе.</span><span class="sxs-lookup"><span data-stu-id="ca22e-143">Version indicates when the change first appears in the framework.</span></span> <span data-ttu-id="ca22e-144">Некоторые изменения появляются в конкретной версии и отменяются в более поздней версии; это также указывается.</span><span class="sxs-lookup"><span data-stu-id="ca22e-144">Some of the changes are introduced in a particular version and reverted in a later version; that is indicated as well.</span></span>

-   <span data-ttu-id="ca22e-145">Тип изменения:</span><span class="sxs-lookup"><span data-stu-id="ca22e-145">The type of change:</span></span>

    |   |   |
    |---|---|
    |<span data-ttu-id="ca22e-146">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="ca22e-146">Retargeting</span></span>|<span data-ttu-id="ca22e-147">Изменение влияет на приложения, которые перекомпилированы для использования в новой версии платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ca22e-147">The change affects apps that are recompiled to target a new version of the .NET Framework.</span></span>|
    |<span data-ttu-id="ca22e-148">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="ca22e-148">Runtime</span></span>|<span data-ttu-id="ca22e-149">Изменение влияет на существующие приложения, предназначенные для предыдущей версии платформы .NET Framework, но работающие в более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="ca22e-149">The change affects an existing app that targets a previous version of the .NET Framework but runs on a later version.</span></span>|

-   <span data-ttu-id="ca22e-150">Затронутые API, если таковые имеются.</span><span class="sxs-lookup"><span data-stu-id="ca22e-150">The affected APIS, if any.</span></span>

-   <span data-ttu-id="ca22e-151">Идентификаторы доступных средств диагностики</span><span class="sxs-lookup"><span data-stu-id="ca22e-151">The IDs of the available diagnostics</span></span>

## <a name="usage"></a><span data-ttu-id="ca22e-152">Использование</span><span class="sxs-lookup"><span data-stu-id="ca22e-152">Usage</span></span>
<span data-ttu-id="ca22e-153">Для начала выберите тип изменения совместимости ниже.</span><span class="sxs-lookup"><span data-stu-id="ca22e-153">To begin, select the type of compatibility change below:</span></span>

* [<span data-ttu-id="ca22e-154">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="ca22e-154">Retargeting Changes</span></span>](./retargeting/index.md)
* [<span data-ttu-id="ca22e-155">Изменения среды выполнения</span><span class="sxs-lookup"><span data-stu-id="ca22e-155">Runtime Changes</span></span>](./runtime/index.md)


## <a name="see-also"></a><span data-ttu-id="ca22e-156">См. также</span><span class="sxs-lookup"><span data-stu-id="ca22e-156">See Also</span></span>

* [<span data-ttu-id="ca22e-157">Версии и зависимости</span><span class="sxs-lookup"><span data-stu-id="ca22e-157">Versions and Dependencies</span></span>](../../../docs/framework/migration-guide/versions-and-dependencies.md)
* [<span data-ttu-id="ca22e-158">Новые возможности</span><span class="sxs-lookup"><span data-stu-id="ca22e-158">What's New</span></span>](../../../docs/framework/whats-new/index.md)
* [<span data-ttu-id="ca22e-159">Устаревшие классы библиотеки классов</span><span class="sxs-lookup"><span data-stu-id="ca22e-159">What's Obsolete in the Class Library</span></span>](../../../docs/framework/whats-new/whats-obsolete.md)
