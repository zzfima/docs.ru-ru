---
title: Элемент <NetFx40_LegacySecurityPolicy>
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_LegacySecurityPolicy> element
- NetFx40_LegacySecurityPolicy element
ms.assetid: 07132b9c-4a72-4710-99d7-e702405e02d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 20a0ca8560fcd5d7f9d171df3e3b4c3f42e78641
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59075994"
---
# <a name="netfx40legacysecuritypolicy-element"></a><span data-ttu-id="5dda6-102">\<NetFx40_LegacySecurityPolicy > элемент</span><span class="sxs-lookup"><span data-stu-id="5dda6-102">\<NetFx40_LegacySecurityPolicy> Element</span></span>
<span data-ttu-id="5dda6-103">Указывает, использует ли среда выполнения устаревшую политику разграничения доступа кода.</span><span class="sxs-lookup"><span data-stu-id="5dda6-103">Specifies whether the runtime uses legacy code access security (CAS) policy.</span></span>  
  
 <span data-ttu-id="5dda6-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="5dda6-104">\<configuration></span></span>  
<span data-ttu-id="5dda6-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="5dda6-105">\<runtime></span></span>  
<span data-ttu-id="5dda6-106"><NetFx40_LegacySecurityPolicy></span><span class="sxs-lookup"><span data-stu-id="5dda6-106"><NetFx40_LegacySecurityPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5dda6-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5dda6-107">Syntax</span></span>  
  
```xml  
<NetFx40_LegacySecurityPolicy  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5dda6-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5dda6-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5dda6-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5dda6-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5dda6-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5dda6-110">Attributes</span></span>  
  
|<span data-ttu-id="5dda6-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5dda6-111">Attribute</span></span>|<span data-ttu-id="5dda6-112">Описание</span><span class="sxs-lookup"><span data-stu-id="5dda6-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="5dda6-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="5dda6-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="5dda6-114">Указывает, использует ли среда выполнения политику разграничения доступа кода прежних версий.</span><span class="sxs-lookup"><span data-stu-id="5dda6-114">Specifies whether the runtime uses legacy CAS policy.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="5dda6-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="5dda6-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="5dda6-116">Значение</span><span class="sxs-lookup"><span data-stu-id="5dda6-116">Value</span></span>|<span data-ttu-id="5dda6-117">Описание</span><span class="sxs-lookup"><span data-stu-id="5dda6-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="5dda6-118">Среда выполнения использует политику разграничения доступа кода прежних версий.</span><span class="sxs-lookup"><span data-stu-id="5dda6-118">The runtime does not use legacy CAS policy.</span></span> <span data-ttu-id="5dda6-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5dda6-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="5dda6-120">Среда выполнения использует политику разграничения доступа кода прежних версий.</span><span class="sxs-lookup"><span data-stu-id="5dda6-120">The runtime uses legacy CAS policy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5dda6-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5dda6-121">Child Elements</span></span>  
 <span data-ttu-id="5dda6-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5dda6-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5dda6-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5dda6-123">Parent Elements</span></span>  
  
|<span data-ttu-id="5dda6-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="5dda6-124">Element</span></span>|<span data-ttu-id="5dda6-125">Описание</span><span class="sxs-lookup"><span data-stu-id="5dda6-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="5dda6-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5dda6-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="5dda6-127">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="5dda6-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5dda6-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="5dda6-128">Remarks</span></span>  
 <span data-ttu-id="5dda6-129">В .NET Framework версии 3.5 и более ранних версий политика разграничения доступа кода настроена на срабатывание всегда.</span><span class="sxs-lookup"><span data-stu-id="5dda6-129">In the .NET Framework version 3.5 and earlier versions, CAS policy is always in effect.</span></span> <span data-ttu-id="5dda6-130">В [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], необходимо включить политику CAS.</span><span class="sxs-lookup"><span data-stu-id="5dda6-130">In the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], CAS policy must be enabled.</span></span>  
  
 <span data-ttu-id="5dda6-131">Политика разграничения доступа кода зависит от версии.</span><span class="sxs-lookup"><span data-stu-id="5dda6-131">CAS policy is version-specific.</span></span> <span data-ttu-id="5dda6-132">Пользовательские политики разграничения доступа кода, которые существуют в более ранних версиях платформы .NET Framework, необходимо заново определить в [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5dda6-132">Custom CAS policies that exist in earlier versions of the .NET Framework must be respecified in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span></span>  
  
 <span data-ttu-id="5dda6-133">Применение `<NetFx40_LegacySecurityPolicy>` элемент [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] сборки не влияет на [прозрачный с точки зрения безопасности код](../../../../../docs/framework/misc/security-transparent-code.md); по-прежнему применяются правила прозрачности.</span><span class="sxs-lookup"><span data-stu-id="5dda6-133">Applying the `<NetFx40_LegacySecurityPolicy>` element to a [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] assembly does not affect [security-transparent code](../../../../../docs/framework/misc/security-transparent-code.md); the transparency rules still apply.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5dda6-134">Применение `<NetFx40_LegacySecurityPolicy>` элемента может привести к снижению производительности для сборки образов в машинном коде, созданные [генератором машинных образов (Ngen.exe)](../../../../../docs/framework/tools/ngen-exe-native-image-generator.md) , которые не установлены в [глобальный кэш сборок ](../../../../../docs/framework/app-domains/gac.md).</span><span class="sxs-lookup"><span data-stu-id="5dda6-134">Applying the `<NetFx40_LegacySecurityPolicy>` element can result in significant performance penalties for native image assemblies created by the [Native Image Generator (Ngen.exe)](../../../../../docs/framework/tools/ngen-exe-native-image-generator.md) that are not installed in the [global assembly cache](../../../../../docs/framework/app-domains/gac.md).</span></span> <span data-ttu-id="5dda6-135">На снижение производительности связано с невозможностью среды выполнения загружать сборки как образы в машинном коде при применении атрибута, что приводит к их загруженных сборок как just-in-time.</span><span class="sxs-lookup"><span data-stu-id="5dda6-135">The performance degradation is caused by the inability of the runtime to load the assemblies as native images when the attribute is applied, resulting in their being loaded as just-in-time assemblies.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5dda6-136">Если вы укажите целевой версии .NET Framework, более ранняя, чем [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] в параметрах проекта для проекта Visual Studio, политика разграничения доступа кода будет включена, включая любые настраиваемые политики разграничения доступа кода, указанных для данной версии.</span><span class="sxs-lookup"><span data-stu-id="5dda6-136">If you specify a target .NET Framework version that is earlier than the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] in the project settings for your Visual Studio project, CAS policy will be enabled, including any custom CAS policies you specified for that version.</span></span> <span data-ttu-id="5dda6-137">Тем не менее, нельзя будет использовать новое [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] типы и члены.</span><span class="sxs-lookup"><span data-stu-id="5dda6-137">However, you will not be able to use new [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] types and members.</span></span> <span data-ttu-id="5dda6-138">Можно также указать более ранней версии платформы .NET Framework с помощью [ \<supportedRuntime > элемент](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) в схеме параметров запуска в вашей [файла конфигурации приложения](../../../../../docs/framework/configure-apps/index.md).</span><span class="sxs-lookup"><span data-stu-id="5dda6-138">You can also specify an earlier version of the .NET Framework by using the [\<supportedRuntime> element](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) in the startup settings schema in your [application configuration file](../../../../../docs/framework/configure-apps/index.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5dda6-139">Синтаксис файлов конфигурации учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="5dda6-139">Configuration file syntax is case-sensitive.</span></span> <span data-ttu-id="5dda6-140">Следует использовать синтаксис, как указано в разделах синтаксиса и пример.</span><span class="sxs-lookup"><span data-stu-id="5dda6-140">You should use the syntax as provided in the Syntax and Example sections.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="5dda6-141">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="5dda6-141">Configuration File</span></span>  
 <span data-ttu-id="5dda6-142">Этот элемент может использоваться только в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="5dda6-142">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5dda6-143">Пример</span><span class="sxs-lookup"><span data-stu-id="5dda6-143">Example</span></span>  
 <span data-ttu-id="5dda6-144">В следующем примере показано включение устаревшая политика CAS для приложения.</span><span class="sxs-lookup"><span data-stu-id="5dda6-144">The following example shows how to enable legacy CAS policy for an application.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_LegacySecurityPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5dda6-145">См. также</span><span class="sxs-lookup"><span data-stu-id="5dda6-145">See also</span></span>

- [<span data-ttu-id="5dda6-146">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="5dda6-146">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="5dda6-147">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="5dda6-147">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
