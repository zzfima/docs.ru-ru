---
title: '&lt;disableFusionUpdatesFromADManager&gt; элемент'
ms.date: 03/30/2017
helpviewer_keywords:
- disableFusionUpdatesFromADManager element
- <disableFusionUpdatesFromADManager> element
ms.assetid: 58d2866c-37bd-4ffa-abaf-ff35926a2939
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4ceaf0b51677a17a2f2a8c0d9d9316cb5b9b34cb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54547245"
---
# <a name="ltdisablefusionupdatesfromadmanagergt-element"></a><span data-ttu-id="39929-102">&lt;disableFusionUpdatesFromADManager&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="39929-102">&lt;disableFusionUpdatesFromADManager&gt; Element</span></span>
<span data-ttu-id="39929-103">Указывает, отключено ли поведение по умолчанию, которое разрешает хост-приложению среды выполнения переопределять параметры конфигурации для домена приложения.</span><span class="sxs-lookup"><span data-stu-id="39929-103">Specifies whether the default behavior, which is to allow the runtime host to override configuration settings for an application domain, is disabled.</span></span>  
  
 <span data-ttu-id="39929-104">\<Конфигурация > элемент</span><span class="sxs-lookup"><span data-stu-id="39929-104">\<configuration> Element</span></span>  
<span data-ttu-id="39929-105">\<Среда выполнения > элемент</span><span class="sxs-lookup"><span data-stu-id="39929-105">\<runtime> Element</span></span>  
<span data-ttu-id="39929-106">\<disableFusionUpdatesFromADManager ></span><span class="sxs-lookup"><span data-stu-id="39929-106">\<disableFusionUpdatesFromADManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39929-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="39929-107">Syntax</span></span>  
  
```xml  
<disableFusionUpdatesFromADManager enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="39929-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="39929-108">Attributes and Elements</span></span>  
 <span data-ttu-id="39929-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="39929-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="39929-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="39929-110">Attributes</span></span>  
  
|<span data-ttu-id="39929-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="39929-111">Attribute</span></span>|<span data-ttu-id="39929-112">Описание</span><span class="sxs-lookup"><span data-stu-id="39929-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="39929-113">enabled</span><span class="sxs-lookup"><span data-stu-id="39929-113">enabled</span></span>|<span data-ttu-id="39929-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="39929-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="39929-115">Указывает, отключен ли по умолчанию возможность переопределения параметров Fusion.</span><span class="sxs-lookup"><span data-stu-id="39929-115">Specifies whether the default ability to override Fusion settings is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="39929-116">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="39929-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="39929-117">Значение</span><span class="sxs-lookup"><span data-stu-id="39929-117">Value</span></span>|<span data-ttu-id="39929-118">Описание</span><span class="sxs-lookup"><span data-stu-id="39929-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="39929-119">0</span><span class="sxs-lookup"><span data-stu-id="39929-119">0</span></span>|<span data-ttu-id="39929-120">Не отключайте возможность переопределения параметров Fusion.</span><span class="sxs-lookup"><span data-stu-id="39929-120">Do not disable the ability to override Fusion settings.</span></span> <span data-ttu-id="39929-121">Это поведение по умолчанию, начиная с [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39929-121">This is the default behavior, starting with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].</span></span>|  
|<span data-ttu-id="39929-122">1</span><span class="sxs-lookup"><span data-stu-id="39929-122">1</span></span>|<span data-ttu-id="39929-123">Отключите возможность переопределения параметров Fusion.</span><span class="sxs-lookup"><span data-stu-id="39929-123">Disable the ability to override Fusion settings.</span></span> <span data-ttu-id="39929-124">При этом восстанавливается поведение более ранних версий платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="39929-124">This reverts to the behavior of earlier versions of the .NET Framework.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="39929-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="39929-125">Child Elements</span></span>  
 <span data-ttu-id="39929-126">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="39929-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="39929-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="39929-127">Parent Elements</span></span>  
  
|<span data-ttu-id="39929-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="39929-128">Element</span></span>|<span data-ttu-id="39929-129">Описание</span><span class="sxs-lookup"><span data-stu-id="39929-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="39929-130">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="39929-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="39929-131">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="39929-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39929-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="39929-132">Remarks</span></span>  
 <span data-ttu-id="39929-133">Начиная с [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], поведение по умолчанию — разрешить <xref:System.AppDomainManager> объекта для переопределения параметров конфигурации с помощью <xref:System.AppDomainSetup.ConfigurationFile%2A> свойство или <xref:System.AppDomainSetup.SetConfigurationBytes%2A> метод <xref:System.AppDomainSetup> объекта, который передается в реализацию из <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> метода в подкласс элементов <xref:System.AppDomainManager>.</span><span class="sxs-lookup"><span data-stu-id="39929-133">Starting with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], the default behavior is to allow the <xref:System.AppDomainManager> object to override configuration settings by using the <xref:System.AppDomainSetup.ConfigurationFile%2A> property or the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method of the <xref:System.AppDomainSetup> object that is passed to your implementation of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method, in your subclass of <xref:System.AppDomainManager>.</span></span> <span data-ttu-id="39929-134">Для домена приложения по умолчанию можно изменить параметры переопределяют параметры, которые были заданы в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="39929-134">For the default application domain, the settings you change override the settings that were specified by the application configuration file.</span></span> <span data-ttu-id="39929-135">Для других доменов приложений, они переопределяют параметры конфигурации, которые были переданы <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> или <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="39929-135">For other application domains, they override the configuration settings that were passed to the <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> or <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="39929-136">Можно передать новую информацию о конфигурации, или передать значение null (`Nothing` в Visual Basic) для исключения сведений о конфигурации, который был передан.</span><span class="sxs-lookup"><span data-stu-id="39929-136">You can either pass new configuration information, or pass null (`Nothing` in Visual Basic) to eliminate configuration information that was passed in.</span></span>  
  
 <span data-ttu-id="39929-137">Не следует передавать сведения о конфигурации оба <xref:System.AppDomainSetup.ConfigurationFile%2A> свойство и <xref:System.AppDomainSetup.SetConfigurationBytes%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="39929-137">Do not pass configuration information to both the <xref:System.AppDomainSetup.ConfigurationFile%2A> property and the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method.</span></span> <span data-ttu-id="39929-138">Если передать сведения о конфигурации оба, сведения, переданные <xref:System.AppDomainSetup.ConfigurationFile%2A> свойство игнорируется, поскольку <xref:System.AppDomainSetup.SetConfigurationBytes%2A> метод переопределяет сведения о конфигурации из файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="39929-138">If you pass configuration information to both, the information you pass to the <xref:System.AppDomainSetup.ConfigurationFile%2A> property is ignored, because the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method overrides configuration information from the application configuration file.</span></span> <span data-ttu-id="39929-139">Если вы используете <xref:System.AppDomainSetup.ConfigurationFile%2A> свойство, можно передать значение null (`Nothing` в Visual Basic) для <xref:System.AppDomainSetup.SetConfigurationBytes%2A> метод, чтобы исключить все байты конфигурации, которые были указаны в вызове <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> или <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="39929-139">If you use the <xref:System.AppDomainSetup.ConfigurationFile%2A> property, you can pass null (`Nothing` in Visual Basic) to the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method to eliminate any configuration bytes that were specified in the call to the <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> or <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="39929-140">Помимо сведений о конфигурации, можно изменить следующие параметры на <xref:System.AppDomainSetup> объект, передаваемый в вашу реализацию <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> метод: <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A>, <xref:System.AppDomainSetup.CachePath%2A>, <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A> , <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, <xref:System.AppDomainSetup.DynamicBase%2A>, <xref:System.AppDomainSetup.LoaderOptimization%2A>, <xref:System.AppDomainSetup.PrivateBinPath%2A>, <xref:System.AppDomainSetup.PrivateBinPathProbe%2A>, <xref:System.AppDomainSetup.ShadowCopyDirectories%2A>, и <xref:System.AppDomainSetup.ShadowCopyFiles%2A>.</span><span class="sxs-lookup"><span data-stu-id="39929-140">In addition to configuration information, you can change the following settings on the <xref:System.AppDomainSetup> object that is passed to your implementation of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method: <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A>, <xref:System.AppDomainSetup.CachePath%2A>, <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A>, <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, <xref:System.AppDomainSetup.DynamicBase%2A>, <xref:System.AppDomainSetup.LoaderOptimization%2A>, <xref:System.AppDomainSetup.PrivateBinPath%2A>, <xref:System.AppDomainSetup.PrivateBinPathProbe%2A>, <xref:System.AppDomainSetup.ShadowCopyDirectories%2A>, and <xref:System.AppDomainSetup.ShadowCopyFiles%2A>.</span></span>  
  
 <span data-ttu-id="39929-141">В качестве альтернативы использованию `<disableFusionUpdatesFromADManager>` элемент, можно отключить поведение по умолчанию, создав параметр реестра или задав переменную среды.</span><span class="sxs-lookup"><span data-stu-id="39929-141">As an alternative to using the `<disableFusionUpdatesFromADManager>` element, you can disable the default behavior by creating a registry setting or by setting an environment variable.</span></span> <span data-ttu-id="39929-142">В реестре, создайте параметр DWORD с именем `COMPLUS_disableFusionUpdatesFromADManager` под `HKCU\Software\Microsoft\.NETFramework` или `HKLM\Software\Microsoft\.NETFramework`и задайте значение 1.</span><span class="sxs-lookup"><span data-stu-id="39929-142">In the registry, create a DWORD value named `COMPLUS_disableFusionUpdatesFromADManager` under `HKCU\Software\Microsoft\.NETFramework` or `HKLM\Software\Microsoft\.NETFramework`, and set the value to 1.</span></span> <span data-ttu-id="39929-143">В командной строке, задайте переменную среды `COMPLUS_disableFusionUpdatesFromADManager` 1.</span><span class="sxs-lookup"><span data-stu-id="39929-143">At the command line, set the environment variable `COMPLUS_disableFusionUpdatesFromADManager` to 1.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39929-144">Пример</span><span class="sxs-lookup"><span data-stu-id="39929-144">Example</span></span>  
 <span data-ttu-id="39929-145">В следующем примере показано, как отключить возможность переопределения параметров Fusion с помощью `<disableFusionUpdatesFromADManager>` элемент.</span><span class="sxs-lookup"><span data-stu-id="39929-145">The following example shows how to disable the ability to override Fusion settings by using the `<disableFusionUpdatesFromADManager>` element.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableFusionUpdatesFromADManager enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="39929-146">См. также</span><span class="sxs-lookup"><span data-stu-id="39929-146">See also</span></span>
- [<span data-ttu-id="39929-147">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="39929-147">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="39929-148">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="39929-148">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="39929-149">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="39929-149">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
