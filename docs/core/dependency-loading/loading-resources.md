---
title: Алгоритм загрузки вспомогательных сборок (.NET Core)
description: Подробный алгоритм загрузки вспомогательных сборок в .NET Core
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: bfdc1d8179d46a13b3d137a87397fa3e573da33c
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2019
ms.locfileid: "72303626"
---
# <a name="satellite-assembly-loading-algorithm"></a><span data-ttu-id="7d4e0-103">Алгоритм загрузки вспомогательных сборок</span><span class="sxs-lookup"><span data-stu-id="7d4e0-103">Satellite assembly loading algorithm</span></span>

<span data-ttu-id="7d4e0-104">Вспомогательные сборки используются для хранения локализованных ресурсов, то есть настроенных для конкретного языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="7d4e0-104">Satellite assemblies are used to store localized resources customized for language and culture.</span></span>

<span data-ttu-id="7d4e0-105">Для вспомогательных сборок используется другой алгоритм загрузки, отличный от алгоритма для обычных управляемых сборок.</span><span class="sxs-lookup"><span data-stu-id="7d4e0-105">Satellite assemblies use a different loading algorithm than general managed assemblies.</span></span>

## <a name="when-are-satellite-assemblies-loaded"></a><span data-ttu-id="7d4e0-106">Когда загружаются вспомогательные сборки?</span><span class="sxs-lookup"><span data-stu-id="7d4e0-106">When are satellite assemblies loaded?</span></span>

<span data-ttu-id="7d4e0-107">Вспомогательные сборки загружаются вместе с локализованным ресурсом.</span><span class="sxs-lookup"><span data-stu-id="7d4e0-107">Satellite assemblies are loaded when loading a localized resource.</span></span>

<span data-ttu-id="7d4e0-108">Базовый API для загрузки локализованных ресурсов — класс <xref:System.Resources.ResourceManager?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="7d4e0-108">The basic API to load localized resources is the <xref:System.Resources.ResourceManager?displayProperty=fullName> class.</span></span> <span data-ttu-id="7d4e0-109">В конечном итоге именно класс <xref:System.Resources.ResourceManager> будет вызывать метод <xref:System.Reflection.Assembly.GetSatelliteAssembly%2A> для каждого свойства <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7d4e0-109">Ultimately the <xref:System.Resources.ResourceManager> class will call the <xref:System.Reflection.Assembly.GetSatelliteAssembly%2A> method for each <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="7d4e0-110">Интерфейсы API более высокого уровня могут быть абстракцией API нижнего уровня.</span><span class="sxs-lookup"><span data-stu-id="7d4e0-110">Higher-level APIs may abstract the low-level API.</span></span>

## <a name="algorithm"></a><span data-ttu-id="7d4e0-111">Алгоритм</span><span class="sxs-lookup"><span data-stu-id="7d4e0-111">Algorithm</span></span>

<span data-ttu-id="7d4e0-112">Процесс использования резервных ресурсов .NET Core включает следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="7d4e0-112">The .NET Core resource fallback process involves the following steps:</span></span>

1. <span data-ttu-id="7d4e0-113">Определение экземпляра `active` <xref:System.Runtime.Loader.AssemblyLoadContext>.</span><span class="sxs-lookup"><span data-stu-id="7d4e0-113">Determine the `active` <xref:System.Runtime.Loader.AssemblyLoadContext> instance.</span></span> <span data-ttu-id="7d4e0-114">Во всех случаях экземпляром `active` считается <xref:System.Runtime.Loader.AssemblyLoadContext> исполняемой сборки.</span><span class="sxs-lookup"><span data-stu-id="7d4e0-114">In all cases, the `active` instance is the executing assembly's <xref:System.Runtime.Loader.AssemblyLoadContext>.</span></span>

2. <span data-ttu-id="7d4e0-115">Экземпляр `active` пытается загрузить вспомогательную сборку для запрошенного языка и региональных параметров в следующем порядке приоритета:</span><span class="sxs-lookup"><span data-stu-id="7d4e0-115">The `active` instance attempts to load a satellite assembly for the requested culture in priority order by:</span></span>
    - <span data-ttu-id="7d4e0-116">Проверяется кэш.</span><span class="sxs-lookup"><span data-stu-id="7d4e0-116">Checking its cache.</span></span>
    - <span data-ttu-id="7d4e0-117">Проверяется каталог выполняемой в данный момент сборки на наличие подкаталога, соответствующего запрошенному <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> (например, `es-MX`).</span><span class="sxs-lookup"><span data-stu-id="7d4e0-117">Checking the directory of the currently executing assembly for a subdirectory that matches the requested <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> (for example `es-MX`).</span></span>

        > [!NOTE]
        > <span data-ttu-id="7d4e0-118">Эта возможность появилась в .NET Core, начиная с версии 3.0.</span><span class="sxs-lookup"><span data-stu-id="7d4e0-118">This feature was not implemented in .NET Core before 3.0.</span></span>
        >
        > [!NOTE]
        > <span data-ttu-id="7d4e0-119">В ОС Linux и macOS в именах подкаталогов учитывается регистр. Они должны:</span><span class="sxs-lookup"><span data-stu-id="7d4e0-119">On Linux and macOS, the subdirectory is case-sensitive and must either:</span></span>
        > - <span data-ttu-id="7d4e0-120">либо точно совпадать с учетом регистра;</span><span class="sxs-lookup"><span data-stu-id="7d4e0-120">Exactly match case.</span></span>
        > - <span data-ttu-id="7d4e0-121">либо содержать только строчные буквы.</span><span class="sxs-lookup"><span data-stu-id="7d4e0-121">Be in lower case.</span></span>

    - <span data-ttu-id="7d4e0-122">Если `active` — экземпляр <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType>, запускается логика [стандартного зондирования для поиска вспомогательных сборок (ресурсов)](default-probing.md#satellite-resource-assembly-probing).</span><span class="sxs-lookup"><span data-stu-id="7d4e0-122">If `active` is the <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType> instance, by running the [default satellite (resource) assembly probing](default-probing.md#satellite-resource-assembly-probing) logic.</span></span>

    - <span data-ttu-id="7d4e0-123">Вызывается функция <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7d4e0-123">Calling the <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType> function.</span></span>

    - <span data-ttu-id="7d4e0-124">Создается событие <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7d4e0-124">Raising the <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType> event.</span></span>

    - <span data-ttu-id="7d4e0-125">Создается событие <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7d4e0-125">Raising the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>

3. <span data-ttu-id="7d4e0-126">Если вспомогательная сборка загружена:</span><span class="sxs-lookup"><span data-stu-id="7d4e0-126">If a satellite assembly is loaded:</span></span>
   - <span data-ttu-id="7d4e0-127">Возникает событие <xref:System.AppDomain.AssemblyLoad?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7d4e0-127">The <xref:System.AppDomain.AssemblyLoad?displayProperty=nameWithType> event is raised.</span></span>
   - <span data-ttu-id="7d4e0-128">В сборке выполняется поиск запрошенного ресурса.</span><span class="sxs-lookup"><span data-stu-id="7d4e0-128">The assembly is searched it for the requested resource.</span></span> <span data-ttu-id="7d4e0-129">Если среда выполнения обнаружит ресурс в сборке, она использует его.</span><span class="sxs-lookup"><span data-stu-id="7d4e0-129">If the runtime finds the resource in the assembly, it uses it.</span></span> <span data-ttu-id="7d4e0-130">Если ресурс не найден, поиск продолжается.</span><span class="sxs-lookup"><span data-stu-id="7d4e0-130">If it doesn't find the resource, it continues the search.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7d4e0-131">Чтобы найти ресурс во вспомогательной сборке, среда выполнения выполняет поиск файла ресурсов по запросу <xref:System.Resources.ResourceManager> для текущего <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7d4e0-131">To find a resource within the satellite assembly, the runtime searches for the resource file requested by the <xref:System.Resources.ResourceManager> for the current <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>.</span></span> <span data-ttu-id="7d4e0-132">В файле ресурсов выполняется поиск имени запрошенного ресурса.</span><span class="sxs-lookup"><span data-stu-id="7d4e0-132">Within the resource file, it searches for the requested resource name.</span></span> <span data-ttu-id="7d4e0-133">Если имя не найдено, ресурс обрабатывается как ненайденный.</span><span class="sxs-lookup"><span data-stu-id="7d4e0-133">If either is not found, the resource is treated as not found.</span></span>

4. <span data-ttu-id="7d4e0-134">Затем среда выполнения ищет родительские сборки языка и региональных параметров по нескольким уровням, каждый раз повторяя действия 2 и 3.</span><span class="sxs-lookup"><span data-stu-id="7d4e0-134">The runtime next searches the parent culture assemblies through many potential levels, each time repeating steps 2 & 3.</span></span>

    <span data-ttu-id="7d4e0-135">Для любого языка и региональных параметров есть только один родительский элемент, определенный свойством <xref:System.Globalization.CultureInfo.Parent%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7d4e0-135">Each culture has only one parent, which is defined by the <xref:System.Globalization.CultureInfo.Parent%2A?displayProperty=nameWithType> property.</span></span>

    <span data-ttu-id="7d4e0-136">Поиск родительского языка и региональных параметров останавливается, когда свойство <xref:System.Globalization.CultureInfo.Parent%2A> для языка и региональных параметров имеет значение <xref:System.Globalization.CultureInfo.InvariantCulture?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7d4e0-136">The search for parent cultures stops when a culture's <xref:System.Globalization.CultureInfo.Parent%2A> property is <xref:System.Globalization.CultureInfo.InvariantCulture?displayProperty=nameWithType>.</span></span>

    <span data-ttu-id="7d4e0-137">Для <xref:System.Globalization.CultureInfo.InvariantCulture> выполняется не возврат к шагам 2 и 3, а сразу переход к шагу 5.</span><span class="sxs-lookup"><span data-stu-id="7d4e0-137">For the <xref:System.Globalization.CultureInfo.InvariantCulture>, we don't return to steps 2 & 3, but rather continue with step 5.</span></span>

5. <span data-ttu-id="7d4e0-138">Если ресурс еще не найден, используется ресурс для языка и региональных параметров по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7d4e0-138">If the resource is still not found, the resource for the default (fallback) culture is used.</span></span>

   <span data-ttu-id="7d4e0-139">Обычно ресурсы для языка региональных параметров по умолчанию включены в основную сборку приложения.</span><span class="sxs-lookup"><span data-stu-id="7d4e0-139">Typically, the resources for the default culture are included in the main application assembly.</span></span> <span data-ttu-id="7d4e0-140">Но вы можете указать значение <xref:System.Resources.UltimateResourceFallbackLocation.Satellite?displayProperty=nameWithType> для свойства <xref:System.Resources.NeutralResourcesLanguageAttribute.Location?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7d4e0-140">However, you can specify <xref:System.Resources.UltimateResourceFallbackLocation.Satellite?displayProperty=nameWithType> for the <xref:System.Resources.NeutralResourcesLanguageAttribute.Location?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="7d4e0-141">Это означает, что конечным расположением ресурсов по умолчанию будет вспомогательная, а не основная сборка.</span><span class="sxs-lookup"><span data-stu-id="7d4e0-141">This value indicates that the ultimate fallback location for resources is a satellite assembly rather than the main assembly.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7d4e0-142">Если ничего не найдено, применяется язык и региональные параметры по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7d4e0-142">The default culture is the ultimate fallback.</span></span> <span data-ttu-id="7d4e0-143">Поэтому мы рекомендуем всегда включать полный набор ресурсов в файл ресурсов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7d4e0-143">Therefore, we recommend that you always include an exhaustive set of resources in the default resource file.</span></span> <span data-ttu-id="7d4e0-144">Это помогает избежать появления исключений.</span><span class="sxs-lookup"><span data-stu-id="7d4e0-144">This helps prevent exceptions from being thrown.</span></span> <span data-ttu-id="7d4e0-145">Полный набор обеспечивает запасной вариант для всех ресурсов и гарантирует, что у пользователю всегда будет доступ хотя бы к одному ресурсу, даже если он не связан с определенным языком и региональными параметрами.</span><span class="sxs-lookup"><span data-stu-id="7d4e0-145">By having an exhaustive set, you provide a fallback for all resources and ensure that at least one resource is always present for the user, even if it is not culturally specific.</span></span>

6. <span data-ttu-id="7d4e0-146">Итак:</span><span class="sxs-lookup"><span data-stu-id="7d4e0-146">Finally,</span></span>
   - <span data-ttu-id="7d4e0-147">если среда выполнения не находит файл ресурсов для стандартного (резервного) языка и региональных параметров, возникает исключение <xref:System.Resources.MissingManifestResourceException> или <xref:System.Resources.MissingSatelliteAssemblyException>;</span><span class="sxs-lookup"><span data-stu-id="7d4e0-147">If the runtime doesn't find a resource file for a default (fallback) culture, a <xref:System.Resources.MissingManifestResourceException> or <xref:System.Resources.MissingSatelliteAssemblyException> exception is thrown.</span></span>
   - <span data-ttu-id="7d4e0-148">если файл ресурсов найден, но запрошенного ресурса в нем нет, то запрос возвращает `null`.</span><span class="sxs-lookup"><span data-stu-id="7d4e0-148">If the resource file is found but the requested resource isn't present, the request returns `null`.</span></span>
