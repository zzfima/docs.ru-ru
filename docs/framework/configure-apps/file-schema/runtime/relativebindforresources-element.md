---
title: Элемент <relativeBindForResources>
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b1ac2900707ddb39c62b34b0ebfbc4547cdd2653
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252351"
---
# <a name="relativebindforresources-element"></a><span data-ttu-id="ea4f2-102">\<Элемент > relativeBindForResources</span><span class="sxs-lookup"><span data-stu-id="ea4f2-102">\<relativeBindForResources> Element</span></span>
<span data-ttu-id="ea4f2-103">Оптимизирует поиск вспомогательных сборок.</span><span class="sxs-lookup"><span data-stu-id="ea4f2-103">Optimizes the probe for satellite assemblies.</span></span>  
  
<span data-ttu-id="ea4f2-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ea4f2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ea4f2-105">&nbsp;&nbsp;[ **\<> среды выполнения**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="ea4f2-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="ea4f2-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<relativeBindForResources>**</span><span class="sxs-lookup"><span data-stu-id="ea4f2-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<relativeBindForResources>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea4f2-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ea4f2-107">Syntax</span></span>  
  
```xml
<relativeBindForResources    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ea4f2-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ea4f2-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ea4f2-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ea4f2-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ea4f2-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ea4f2-110">Attributes</span></span>  
  
|<span data-ttu-id="ea4f2-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ea4f2-111">Attribute</span></span>|<span data-ttu-id="ea4f2-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ea4f2-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="ea4f2-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="ea4f2-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="ea4f2-114">Указывает, оптимизирует ли среда CLR проверку на наличие вспомогательных сборок.</span><span class="sxs-lookup"><span data-stu-id="ea4f2-114">Specifies whether the common language runtime optimizes the probe for satellite assemblies.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="ea4f2-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="ea4f2-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="ea4f2-116">Значение</span><span class="sxs-lookup"><span data-stu-id="ea4f2-116">Value</span></span>|<span data-ttu-id="ea4f2-117">Описание</span><span class="sxs-lookup"><span data-stu-id="ea4f2-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="ea4f2-118">Среда выполнения не оптимизирует зонд для вспомогательных сборок.</span><span class="sxs-lookup"><span data-stu-id="ea4f2-118">The runtime does not optimize the probe for satellite assemblies.</span></span> <span data-ttu-id="ea4f2-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ea4f2-119">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="ea4f2-120">Среда выполнения оптимизирует зонд для вспомогательных сборок.</span><span class="sxs-lookup"><span data-stu-id="ea4f2-120">The runtime optimizes the probe for satellite assemblies.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ea4f2-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ea4f2-121">Child Elements</span></span>  
 <span data-ttu-id="ea4f2-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="ea4f2-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ea4f2-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ea4f2-123">Parent Elements</span></span>  
  
|<span data-ttu-id="ea4f2-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="ea4f2-124">Element</span></span>|<span data-ttu-id="ea4f2-125">Описание</span><span class="sxs-lookup"><span data-stu-id="ea4f2-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ea4f2-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ea4f2-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="ea4f2-127">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="ea4f2-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea4f2-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="ea4f2-128">Remarks</span></span>  
 <span data-ttu-id="ea4f2-129">Как правило, диспетчер ресурсов зонды для ресурсов, как описано в разделе [Упаковка и развертывание ресурсов](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) .</span><span class="sxs-lookup"><span data-stu-id="ea4f2-129">In general, Resource Manager probes for resources, as documented in the [Packaging and Deploying Resources](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) topic.</span></span> <span data-ttu-id="ea4f2-130">Это означает, что при диспетчер ресурсов зондах для конкретной локализованной версии ресурса она может искать в глобальном кэше сборок, искать в папке, зависящей от языка и региональных параметров, в базе кода приложения, запрашивать установщик Windows для вспомогательных сборок и вызывать <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> событие.</span><span class="sxs-lookup"><span data-stu-id="ea4f2-130">This means that when Resource Manager probes for a particular localized version of a resource, it may look in the global assembly cache, look in a culture-specific folder in the application's code base, query Windows Installer for satellite assemblies, and raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="ea4f2-131">`<relativeBindForResources>` Элемент оптимизирует способ диспетчер ресурсов проверки для вспомогательных сборок.</span><span class="sxs-lookup"><span data-stu-id="ea4f2-131">The `<relativeBindForResources>` element optimizes the way in which Resource Manager probes for satellite assemblies.</span></span> <span data-ttu-id="ea4f2-132">Это может повысить производительность при проверке ресурсов при следующих условиях.</span><span class="sxs-lookup"><span data-stu-id="ea4f2-132">It can improve performance when probing for resources under the following conditions:</span></span>  
  
- <span data-ttu-id="ea4f2-133">При развертывании вспомогательной сборки в том же расположении, что и сборка кода.</span><span class="sxs-lookup"><span data-stu-id="ea4f2-133">When the satellite assembly is deployed in the same location as the code assembly.</span></span> <span data-ttu-id="ea4f2-134">Иными словами, если сборка кода установлена в глобальном кэше сборок, вспомогательные сборки также должны быть установлены там.</span><span class="sxs-lookup"><span data-stu-id="ea4f2-134">In other words, if the code assembly is installed in the global assembly cache, the satellite assemblies must also be installed there.</span></span> <span data-ttu-id="ea4f2-135">Если сборка кода установлена в базе кода приложения, вспомогательные сборки также должны быть установлены в папке, зависящей от языка и региональных параметров, в базе кода.</span><span class="sxs-lookup"><span data-stu-id="ea4f2-135">If the code assembly is installed in the application's code base, the satellite assemblies must also be installed in a culture-specific folder in the code base.</span></span>  
  
- <span data-ttu-id="ea4f2-136">Если установщик Windows не используется или используется редко для установки вспомогательных сборок по требованию.</span><span class="sxs-lookup"><span data-stu-id="ea4f2-136">When Windows Installer is not used or is used only rarely for on-demand installation of satellite assemblies.</span></span>  
  
- <span data-ttu-id="ea4f2-137">Когда код приложения не обрабатывает <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> событие.</span><span class="sxs-lookup"><span data-stu-id="ea4f2-137">When application code does not handle the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
 <span data-ttu-id="ea4f2-138">`enabled` Установка атрибута `<relativeBindForResources>` элемента для`true` оптимизации проверки диспетчер ресурсов для вспомогательных сборок выполняется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ea4f2-138">Setting the `enabled` attribute of the `<relativeBindForResources>` element to `true` optimizes Resource Manager's probe for satellite assemblies as follows:</span></span>  
  
- <span data-ttu-id="ea4f2-139">Он использует расположение сборки родительского кода для проверки вспомогательной сборки.</span><span class="sxs-lookup"><span data-stu-id="ea4f2-139">It uses the location of the parent code assembly to probe for the satellite assembly.</span></span>  
  
- <span data-ttu-id="ea4f2-140">Он не запрашивает установщик Windows для вспомогательных сборок.</span><span class="sxs-lookup"><span data-stu-id="ea4f2-140">It does not query Windows Installer for satellite assemblies.</span></span>  
  
- <span data-ttu-id="ea4f2-141">Он не вызывает <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> событие.</span><span class="sxs-lookup"><span data-stu-id="ea4f2-141">It does not raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea4f2-142">См. также</span><span class="sxs-lookup"><span data-stu-id="ea4f2-142">See also</span></span>

- [<span data-ttu-id="ea4f2-143">Упаковка и развертывание ресурсов</span><span class="sxs-lookup"><span data-stu-id="ea4f2-143">Packaging and Deploying Resources</span></span>](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [<span data-ttu-id="ea4f2-144">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="ea4f2-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="ea4f2-145">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="ea4f2-145">Configuration File Schema</span></span>](../index.md)
