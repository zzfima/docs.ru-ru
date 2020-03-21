---
title: Элемент <relativeBindForResources>
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
ms.openlocfilehash: cd49d424019a4e8422fee0ae16217d49cfc456b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153910"
---
# <a name="relativebindforresources-element"></a><span data-ttu-id="66c49-102">\<относительныеBindForРесурсы> Элемент</span><span class="sxs-lookup"><span data-stu-id="66c49-102">\<relativeBindForResources> Element</span></span>
<span data-ttu-id="66c49-103">Оптимизирует поиск вспомогательных сборок.</span><span class="sxs-lookup"><span data-stu-id="66c49-103">Optimizes the probe for satellite assemblies.</span></span>  
  
<span data-ttu-id="66c49-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="66c49-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="66c49-105">&nbsp;&nbsp;[**\<>выполнения**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="66c49-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="66c49-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<родственникБюдфорРесурсы>**</span><span class="sxs-lookup"><span data-stu-id="66c49-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<relativeBindForResources>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66c49-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="66c49-107">Syntax</span></span>  
  
```xml
<relativeBindForResources
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="66c49-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="66c49-108">Attributes and Elements</span></span>  
 <span data-ttu-id="66c49-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="66c49-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="66c49-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="66c49-110">Attributes</span></span>  
  
|<span data-ttu-id="66c49-111">attribute</span><span class="sxs-lookup"><span data-stu-id="66c49-111">Attribute</span></span>|<span data-ttu-id="66c49-112">Описание</span><span class="sxs-lookup"><span data-stu-id="66c49-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="66c49-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="66c49-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="66c49-114">Уточняется, оптимизирует ли общее время выполнения языка зонд для спутниковых сборок.</span><span class="sxs-lookup"><span data-stu-id="66c49-114">Specifies whether the common language runtime optimizes the probe for satellite assemblies.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="66c49-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="66c49-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="66c49-116">Значение</span><span class="sxs-lookup"><span data-stu-id="66c49-116">Value</span></span>|<span data-ttu-id="66c49-117">Описание</span><span class="sxs-lookup"><span data-stu-id="66c49-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="66c49-118">Время выполнения не оптимизирует зонд для спутниковых сборок.</span><span class="sxs-lookup"><span data-stu-id="66c49-118">The runtime does not optimize the probe for satellite assemblies.</span></span> <span data-ttu-id="66c49-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="66c49-119">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="66c49-120">Время выполнения оптимизирует зонд для спутниковых сборок.</span><span class="sxs-lookup"><span data-stu-id="66c49-120">The runtime optimizes the probe for satellite assemblies.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="66c49-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="66c49-121">Child Elements</span></span>  
 <span data-ttu-id="66c49-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="66c49-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="66c49-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="66c49-123">Parent Elements</span></span>  
  
|<span data-ttu-id="66c49-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="66c49-124">Element</span></span>|<span data-ttu-id="66c49-125">Описание</span><span class="sxs-lookup"><span data-stu-id="66c49-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="66c49-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="66c49-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="66c49-127">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="66c49-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="66c49-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="66c49-128">Remarks</span></span>  
 <span data-ttu-id="66c49-129">Как правило, ресурсный менеджер проверяет ресурсы, как это описано в теме [упаковки и развертывания ресурсов.](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)</span><span class="sxs-lookup"><span data-stu-id="66c49-129">In general, Resource Manager probes for resources, as documented in the [Packaging and Deploying Resources](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) topic.</span></span> <span data-ttu-id="66c49-130">Это означает, что, когда диспетчер ресурсов зондирует конкретную локализованную версию ресурса, он может заглянуть в кэш глобальной сборки, заглянуть в папку для <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> конкретной культуры в кодовой базе приложения, запросить установку Windows для спутниковых сборок и поднять событие.</span><span class="sxs-lookup"><span data-stu-id="66c49-130">This means that when Resource Manager probes for a particular localized version of a resource, it may look in the global assembly cache, look in a culture-specific folder in the application's code base, query Windows Installer for satellite assemblies, and raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="66c49-131">Элемент `<relativeBindForResources>` оптимизирует способ зондирования ресурсного менеджера для спутниковых сборок.</span><span class="sxs-lookup"><span data-stu-id="66c49-131">The `<relativeBindForResources>` element optimizes the way in which Resource Manager probes for satellite assemblies.</span></span> <span data-ttu-id="66c49-132">Это может повысить производительность при зондирования ресурсов при следующих условиях:</span><span class="sxs-lookup"><span data-stu-id="66c49-132">It can improve performance when probing for resources under the following conditions:</span></span>  
  
- <span data-ttu-id="66c49-133">При развертывании сборки спутника в том же месте, что и сборка кода.</span><span class="sxs-lookup"><span data-stu-id="66c49-133">When the satellite assembly is deployed in the same location as the code assembly.</span></span> <span data-ttu-id="66c49-134">Другими словами, если сборка кода установлена в кэше глобальной сборки, то там должны быть установлены и сборки спутников.</span><span class="sxs-lookup"><span data-stu-id="66c49-134">In other words, if the code assembly is installed in the global assembly cache, the satellite assemblies must also be installed there.</span></span> <span data-ttu-id="66c49-135">Если сборка кода установлена в кодовой базе приложения, сборки спутников также должны быть установлены в папке, предназначенной для культуры, в базе кода.</span><span class="sxs-lookup"><span data-stu-id="66c49-135">If the code assembly is installed in the application's code base, the satellite assemblies must also be installed in a culture-specific folder in the code base.</span></span>  
  
- <span data-ttu-id="66c49-136">Когда Установка Windows не используется или используется только редко для установки спутниковых сборок по требованию.</span><span class="sxs-lookup"><span data-stu-id="66c49-136">When Windows Installer is not used or is used only rarely for on-demand installation of satellite assemblies.</span></span>  
  
- <span data-ttu-id="66c49-137">Когда код приложения не <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> обрабатывает событие.</span><span class="sxs-lookup"><span data-stu-id="66c49-137">When application code does not handle the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
 <span data-ttu-id="66c49-138">Установка `enabled` атрибута `<relativeBindForResources>` элемента `true` для оптимизации зонда Resource Manager для спутниковых сборок следующим образом:</span><span class="sxs-lookup"><span data-stu-id="66c49-138">Setting the `enabled` attribute of the `<relativeBindForResources>` element to `true` optimizes Resource Manager's probe for satellite assemblies as follows:</span></span>  
  
- <span data-ttu-id="66c49-139">Он использует расположение родительского кода для зондирования для сборки спутника.</span><span class="sxs-lookup"><span data-stu-id="66c49-139">It uses the location of the parent code assembly to probe for the satellite assembly.</span></span>  
  
- <span data-ttu-id="66c49-140">Он не задает запрос установки Windows для спутниковых сборок.</span><span class="sxs-lookup"><span data-stu-id="66c49-140">It does not query Windows Installer for satellite assemblies.</span></span>  
  
- <span data-ttu-id="66c49-141">Это не поднимает <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> событие.</span><span class="sxs-lookup"><span data-stu-id="66c49-141">It does not raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66c49-142">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="66c49-142">See also</span></span>

- [<span data-ttu-id="66c49-143">Packaging and Deploying Resources</span><span class="sxs-lookup"><span data-stu-id="66c49-143">Packaging and Deploying Resources</span></span>](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [<span data-ttu-id="66c49-144">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="66c49-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="66c49-145">Схема конфигурации файлов</span><span class="sxs-lookup"><span data-stu-id="66c49-145">Configuration File Schema</span></span>](../index.md)
