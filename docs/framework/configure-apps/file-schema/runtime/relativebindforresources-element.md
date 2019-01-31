---
title: Элемент <relativeBindForResources>
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51129f9bb3a278d32a5da723dcc339f5e918c0f4
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55289813"
---
# <a name="relativebindforresources-element"></a><span data-ttu-id="966da-102">\<relativeBindForResources > элемент</span><span class="sxs-lookup"><span data-stu-id="966da-102">\<relativeBindForResources> Element</span></span>
<span data-ttu-id="966da-103">Оптимизирует поиск вспомогательных сборок.</span><span class="sxs-lookup"><span data-stu-id="966da-103">Optimizes the probe for satellite assemblies.</span></span>  
  
 <span data-ttu-id="966da-104">\<Конфигурация > элемент</span><span class="sxs-lookup"><span data-stu-id="966da-104">\<configuration> Element</span></span>  
<span data-ttu-id="966da-105">\<Среда выполнения > элемент</span><span class="sxs-lookup"><span data-stu-id="966da-105">\<runtime> Element</span></span>  
<span data-ttu-id="966da-106">\<relativeBindForResources > элемент</span><span class="sxs-lookup"><span data-stu-id="966da-106">\<relativeBindForResources> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="966da-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="966da-107">Syntax</span></span>  
  
```xml
<relativeBindForResources    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="966da-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="966da-108">Attributes and Elements</span></span>  
 <span data-ttu-id="966da-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="966da-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="966da-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="966da-110">Attributes</span></span>  
  
|<span data-ttu-id="966da-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="966da-111">Attribute</span></span>|<span data-ttu-id="966da-112">Описание</span><span class="sxs-lookup"><span data-stu-id="966da-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="966da-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="966da-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="966da-114">Указывает, является ли среда CLR оптимизирует поиск вспомогательных сборок.</span><span class="sxs-lookup"><span data-stu-id="966da-114">Specifies whether the common language runtime optimizes the probe for satellite assemblies.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="966da-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="966da-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="966da-116">Значение</span><span class="sxs-lookup"><span data-stu-id="966da-116">Value</span></span>|<span data-ttu-id="966da-117">Описание:</span><span class="sxs-lookup"><span data-stu-id="966da-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="966da-118">Среда выполнения не Оптимизируйте поиск вспомогательных сборок.</span><span class="sxs-lookup"><span data-stu-id="966da-118">The runtime does not optimize the probe for satellite assemblies.</span></span> <span data-ttu-id="966da-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="966da-119">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="966da-120">Среда выполнения оптимизирует поиск вспомогательных сборок.</span><span class="sxs-lookup"><span data-stu-id="966da-120">The runtime optimizes the probe for satellite assemblies.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="966da-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="966da-121">Child Elements</span></span>  
 <span data-ttu-id="966da-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="966da-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="966da-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="966da-123">Parent Elements</span></span>  
  
|<span data-ttu-id="966da-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="966da-124">Element</span></span>|<span data-ttu-id="966da-125">Описание:</span><span class="sxs-lookup"><span data-stu-id="966da-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="966da-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="966da-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="966da-127">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="966da-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="966da-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="966da-128">Remarks</span></span>  
 <span data-ttu-id="966da-129">Как правило, Resource Manager проверяет наличие ресурсов, как описано в статье [упаковка и развертывание ресурсов](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md) раздела.</span><span class="sxs-lookup"><span data-stu-id="966da-129">In general, Resource Manager probes for resources, as documented in the [Packaging and Deploying Resources](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md) topic.</span></span> <span data-ttu-id="966da-130">Это означает, что при Resource Manager проверяет наличие некоторой локализованной версии ресурса, он может выглядеть в глобальном кэше сборок, поиск вспомогательных сборок в папке для определенного языка и региональных параметров в запросе базовый, код приложения установщика Windows и инициации <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> событий.</span><span class="sxs-lookup"><span data-stu-id="966da-130">This means that when Resource Manager probes for a particular localized version of a resource, it may look in the global assembly cache, look in a culture-specific folder in the application's code base, query Windows Installer for satellite assemblies, and raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="966da-131">`<relativeBindForResources>` Элемент оптимизирует процесс, в которой диспетчер ресурсов выполняет поиск вспомогательных сборок.</span><span class="sxs-lookup"><span data-stu-id="966da-131">The `<relativeBindForResources>` element optimizes the way in which Resource Manager probes for satellite assemblies.</span></span> <span data-ttu-id="966da-132">Он может повысить производительность, если проверка для ресурсов при следующих условиях:</span><span class="sxs-lookup"><span data-stu-id="966da-132">It can improve performance when probing for resources under the following conditions:</span></span>  
  
-   <span data-ttu-id="966da-133">Когда вспомогательная сборка развертывается в том же расположении, что и сборка кода.</span><span class="sxs-lookup"><span data-stu-id="966da-133">When the satellite assembly is deployed in the same location as the code assembly.</span></span> <span data-ttu-id="966da-134">Другими словами Если сборка кода установлена в глобальном кэше сборок, вспомогательные сборки должны также быть там установлены.</span><span class="sxs-lookup"><span data-stu-id="966da-134">In other words, if the code assembly is installed in the global assembly cache, the satellite assemblies must also be installed there.</span></span> <span data-ttu-id="966da-135">Если сборка кода установлена в базе кода приложения, вспомогательные сборки также устанавливается в папке для определенного языка и региональных параметров в базе кода.</span><span class="sxs-lookup"><span data-stu-id="966da-135">If the code assembly is installed in the application's code base, the satellite assemblies must also be installed in a culture-specific folder in the code base.</span></span>  
  
-   <span data-ttu-id="966da-136">Если установщик Windows не используется или используется лишь изредка для установки вспомогательных сборок по требованию.</span><span class="sxs-lookup"><span data-stu-id="966da-136">When Windows Installer is not used or is used only rarely for on-demand installation of satellite assemblies.</span></span>  
  
-   <span data-ttu-id="966da-137">Когда код приложения не обрабатывает <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> событий.</span><span class="sxs-lookup"><span data-stu-id="966da-137">When application code does not handle the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
 <span data-ttu-id="966da-138">Установка `enabled` атрибут `<relativeBindForResources>` элемент `true` оптимизирует зонда диспетчера ресурсов для вспомогательных сборок следующим образом:</span><span class="sxs-lookup"><span data-stu-id="966da-138">Setting the `enabled` attribute of the `<relativeBindForResources>` element to `true` optimizes Resource Manager's probe for satellite assemblies as follows:</span></span>  
  
-   <span data-ttu-id="966da-139">Он использует расположение родительской сборки кода для проверки вспомогательной сборки.</span><span class="sxs-lookup"><span data-stu-id="966da-139">It uses the location of the parent code assembly to probe for the satellite assembly.</span></span>  
  
-   <span data-ttu-id="966da-140">Он не запрашивает установщик Windows для вспомогательных сборок.</span><span class="sxs-lookup"><span data-stu-id="966da-140">It does not query Windows Installer for satellite assemblies.</span></span>  
  
-   <span data-ttu-id="966da-141">Не вызывалось <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> событий.</span><span class="sxs-lookup"><span data-stu-id="966da-141">It does not raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="966da-142">См. также</span><span class="sxs-lookup"><span data-stu-id="966da-142">See also</span></span>
- [<span data-ttu-id="966da-143">Упаковка и развертывание ресурсов</span><span class="sxs-lookup"><span data-stu-id="966da-143">Packaging and Deploying Resources</span></span>](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [<span data-ttu-id="966da-144">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="966da-144">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="966da-145">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="966da-145">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
