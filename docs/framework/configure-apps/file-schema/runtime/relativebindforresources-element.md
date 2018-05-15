---
title: '&lt;relativeBindForResources&gt; элемент'
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ae5d1ca6403d84c9828dcf9550e9fbf40b28e1b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltrelativebindforresourcesgt-element"></a><span data-ttu-id="b5331-102">&lt;relativeBindForResources&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="b5331-102">&lt;relativeBindForResources&gt; Element</span></span>
<span data-ttu-id="b5331-103">Оптимизирует поиск вспомогательных сборок.</span><span class="sxs-lookup"><span data-stu-id="b5331-103">Optimizes the probe for satellite assemblies.</span></span>  
  
 <span data-ttu-id="b5331-104">\<Конфигурация > элемент</span><span class="sxs-lookup"><span data-stu-id="b5331-104">\<configuration> Element</span></span>  
<span data-ttu-id="b5331-105">\<Среда выполнения > элемент</span><span class="sxs-lookup"><span data-stu-id="b5331-105">\<runtime> Element</span></span>  
<span data-ttu-id="b5331-106">\<relativeBindForResources > элемент</span><span class="sxs-lookup"><span data-stu-id="b5331-106">\<relativeBindForResources> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5331-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b5331-107">Syntax</span></span>  
  
```xml
<relativeBindForResources    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b5331-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b5331-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b5331-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b5331-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b5331-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b5331-110">Attributes</span></span>  
  
|<span data-ttu-id="b5331-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b5331-111">Attribute</span></span>|<span data-ttu-id="b5331-112">Описание</span><span class="sxs-lookup"><span data-stu-id="b5331-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="b5331-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="b5331-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="b5331-114">Указывает, является ли среда оптимизирует поиск вспомогательных сборок.</span><span class="sxs-lookup"><span data-stu-id="b5331-114">Specifies whether the common language runtime optimizes the probe for satellite assemblies.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="b5331-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="b5331-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="b5331-116">Значение</span><span class="sxs-lookup"><span data-stu-id="b5331-116">Value</span></span>|<span data-ttu-id="b5331-117">Описание</span><span class="sxs-lookup"><span data-stu-id="b5331-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="b5331-118">Среда выполнения не Оптимизируйте поиск вспомогательных сборок.</span><span class="sxs-lookup"><span data-stu-id="b5331-118">The runtime does not optimize the probe for satellite assemblies.</span></span> <span data-ttu-id="b5331-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b5331-119">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="b5331-120">Среда выполнения оптимизирует поиск вспомогательных сборок.</span><span class="sxs-lookup"><span data-stu-id="b5331-120">The runtime optimizes the probe for satellite assemblies.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b5331-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b5331-121">Child Elements</span></span>  
 <span data-ttu-id="b5331-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b5331-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b5331-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b5331-123">Parent Elements</span></span>  
  
|<span data-ttu-id="b5331-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="b5331-124">Element</span></span>|<span data-ttu-id="b5331-125">Описание</span><span class="sxs-lookup"><span data-stu-id="b5331-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b5331-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b5331-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="b5331-127">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="b5331-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b5331-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="b5331-128">Remarks</span></span>  
 <span data-ttu-id="b5331-129">Как правило, диспетчер ресурсов проверяет наличие ресурсов, как описано в [упаковка и развертывание ресурсов](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md) раздела.</span><span class="sxs-lookup"><span data-stu-id="b5331-129">In general, Resource Manager probes for resources, as documented in the [Packaging and Deploying Resources](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md) topic.</span></span> <span data-ttu-id="b5331-130">Это означает, что при Resource Manager проверяет наличие определенного локализованную версию ресурса, он может поиск в глобальном кэше сборок, поиск вспомогательных сборок в папке для определенного языка и региональных параметров в запросе базу кода приложения установщика Windows и вызова <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> события.</span><span class="sxs-lookup"><span data-stu-id="b5331-130">This means that when Resource Manager probes for a particular localized version of a resource, it may look in the global assembly cache, look in a culture-specific folder in the application's code base, query Windows Installer for satellite assemblies, and raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="b5331-131">`<relativeBindForResources>` Элемент оптимизирует процесс, в котором диспетчер ресурсов выполняет поиск вспомогательных сборок.</span><span class="sxs-lookup"><span data-stu-id="b5331-131">The `<relativeBindForResources>` element optimizes the way in which Resource Manager probes for satellite assemblies.</span></span> <span data-ttu-id="b5331-132">Это может повысить производительность при поиске ресурсов при следующих условиях:</span><span class="sxs-lookup"><span data-stu-id="b5331-132">It can improve performance when probing for resources under the following conditions:</span></span>  
  
-   <span data-ttu-id="b5331-133">При развертывании вспомогательную сборку в том же расположении, что и сборка кода.</span><span class="sxs-lookup"><span data-stu-id="b5331-133">When the satellite assembly is deployed in the same location as the code assembly.</span></span> <span data-ttu-id="b5331-134">Другими словами Если код сборки, которая установлена в глобальном кэше сборок, вспомогательные сборки также должны быть установлены существует.</span><span class="sxs-lookup"><span data-stu-id="b5331-134">In other words, if the code assembly is installed in the global assembly cache, the satellite assemblies must also be installed there.</span></span> <span data-ttu-id="b5331-135">Если сборка кода устанавливается в базу кода приложения, вспомогательных сборок также устанавливается в папке для определенного языка и региональных параметров в базе кода.</span><span class="sxs-lookup"><span data-stu-id="b5331-135">If the code assembly is installed in the application's code base, the satellite assemblies must also be installed in a culture-specific folder in the code base.</span></span>  
  
-   <span data-ttu-id="b5331-136">Когда установщика Windows не используется или редко используется для установки вспомогательных сборок по требованию.</span><span class="sxs-lookup"><span data-stu-id="b5331-136">When Windows Installer is not used or is used only rarely for on-demand installation of satellite assemblies.</span></span>  
  
-   <span data-ttu-id="b5331-137">Когда код приложения не может обрабатывать <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> событий.</span><span class="sxs-lookup"><span data-stu-id="b5331-137">When application code does not handle the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
 <span data-ttu-id="b5331-138">Установка `enabled` атрибут `<relativeBindForResources>` элемент `true` оптимизирует пробы диспетчера ресурсов для вспомогательных сборок следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b5331-138">Setting the `enabled` attribute of the `<relativeBindForResources>` element to `true` optimizes Resource Manager's probe for satellite assemblies as follows:</span></span>  
  
-   <span data-ttu-id="b5331-139">Она использует расположение родительской сборки кода для проверки для вспомогательной сборки.</span><span class="sxs-lookup"><span data-stu-id="b5331-139">It uses the location of the parent code assembly to probe for the satellite assembly.</span></span>  
  
-   <span data-ttu-id="b5331-140">Он не запрашивает установщик Windows для вспомогательных сборок.</span><span class="sxs-lookup"><span data-stu-id="b5331-140">It does not query Windows Installer for satellite assemblies.</span></span>  
  
-   <span data-ttu-id="b5331-141">Не вызывалось <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> событий.</span><span class="sxs-lookup"><span data-stu-id="b5331-141">It does not raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5331-142">См. также</span><span class="sxs-lookup"><span data-stu-id="b5331-142">See Also</span></span>  
 [<span data-ttu-id="b5331-143">Упаковка и развертывание ресурсов</span><span class="sxs-lookup"><span data-stu-id="b5331-143">Packaging and Deploying Resources</span></span>](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)  
 [<span data-ttu-id="b5331-144">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="b5331-144">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="b5331-145">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="b5331-145">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
