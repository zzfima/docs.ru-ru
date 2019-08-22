---
title: Элемент <disableFusionUpdatesFromADManager>
ms.date: 03/30/2017
helpviewer_keywords:
- disableFusionUpdatesFromADManager element
- <disableFusionUpdatesFromADManager> element
ms.assetid: 58d2866c-37bd-4ffa-abaf-ff35926a2939
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a1923e70143ea2a158447eccdb35d347fe4f51ea
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663761"
---
# <a name="disablefusionupdatesfromadmanager-element"></a><span data-ttu-id="4199b-102">\<Элемент > Дисаблефусионупдатесфромадманажер</span><span class="sxs-lookup"><span data-stu-id="4199b-102">\<disableFusionUpdatesFromADManager> Element</span></span>
<span data-ttu-id="4199b-103">Указывает, отключено ли поведение по умолчанию, которое разрешает хост-приложению среды выполнения переопределять параметры конфигурации для домена приложения.</span><span class="sxs-lookup"><span data-stu-id="4199b-103">Specifies whether the default behavior, which is to allow the runtime host to override configuration settings for an application domain, is disabled.</span></span>  
  
 <span data-ttu-id="4199b-104">\<Элемент Configuration ></span><span class="sxs-lookup"><span data-stu-id="4199b-104">\<configuration> Element</span></span>  
<span data-ttu-id="4199b-105">\<Элемент > среды выполнения</span><span class="sxs-lookup"><span data-stu-id="4199b-105">\<runtime> Element</span></span>  
<span data-ttu-id="4199b-106">\<Дисаблефусионупдатесфромадманажер ></span><span class="sxs-lookup"><span data-stu-id="4199b-106">\<disableFusionUpdatesFromADManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4199b-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4199b-107">Syntax</span></span>  
  
```xml  
<disableFusionUpdatesFromADManager enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4199b-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4199b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4199b-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4199b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4199b-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4199b-110">Attributes</span></span>  
  
|<span data-ttu-id="4199b-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4199b-111">Attribute</span></span>|<span data-ttu-id="4199b-112">Описание</span><span class="sxs-lookup"><span data-stu-id="4199b-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4199b-113">enabled</span><span class="sxs-lookup"><span data-stu-id="4199b-113">enabled</span></span>|<span data-ttu-id="4199b-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="4199b-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="4199b-115">Указывает, отключена ли возможность по умолчанию переопределять параметры Fusion.</span><span class="sxs-lookup"><span data-stu-id="4199b-115">Specifies whether the default ability to override Fusion settings is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="4199b-116">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="4199b-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="4199b-117">Значение</span><span class="sxs-lookup"><span data-stu-id="4199b-117">Value</span></span>|<span data-ttu-id="4199b-118">Описание</span><span class="sxs-lookup"><span data-stu-id="4199b-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4199b-119">0</span><span class="sxs-lookup"><span data-stu-id="4199b-119">0</span></span>|<span data-ttu-id="4199b-120">Не отключайте возможность переопределения параметров Fusion.</span><span class="sxs-lookup"><span data-stu-id="4199b-120">Do not disable the ability to override Fusion settings.</span></span> <span data-ttu-id="4199b-121">Это поведение по умолчанию, начиная с .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="4199b-121">This is the default behavior, starting with the .NET Framework 4.</span></span>|  
|<span data-ttu-id="4199b-122">1</span><span class="sxs-lookup"><span data-stu-id="4199b-122">1</span></span>|<span data-ttu-id="4199b-123">Отключить возможность переопределения параметров Fusion.</span><span class="sxs-lookup"><span data-stu-id="4199b-123">Disable the ability to override Fusion settings.</span></span> <span data-ttu-id="4199b-124">Это позволяет вернуться к поведению более ранних версий .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4199b-124">This reverts to the behavior of earlier versions of the .NET Framework.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4199b-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4199b-125">Child Elements</span></span>  
 <span data-ttu-id="4199b-126">Нет.</span><span class="sxs-lookup"><span data-stu-id="4199b-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4199b-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4199b-127">Parent Elements</span></span>  
  
|<span data-ttu-id="4199b-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="4199b-128">Element</span></span>|<span data-ttu-id="4199b-129">Описание</span><span class="sxs-lookup"><span data-stu-id="4199b-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4199b-130">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4199b-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="4199b-131">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="4199b-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4199b-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="4199b-132">Remarks</span></span>  
 <span data-ttu-id="4199b-133">Начиная с .NET Framework 4, поведение по умолчанию заключается в том, <xref:System.AppDomainManager> чтобы разрешить объекту переопределять параметры конфигурации с <xref:System.AppDomainSetup.ConfigurationFile%2A> помощью свойства <xref:System.AppDomainSetup> или <xref:System.AppDomainSetup.SetConfigurationBytes%2A> метода объекта, который передается в вашу реализацию. метода в подклассе <xref:System.AppDomainManager>. <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="4199b-133">Starting with the .NET Framework 4, the default behavior is to allow the <xref:System.AppDomainManager> object to override configuration settings by using the <xref:System.AppDomainSetup.ConfigurationFile%2A> property or the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method of the <xref:System.AppDomainSetup> object that is passed to your implementation of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method, in your subclass of <xref:System.AppDomainManager>.</span></span> <span data-ttu-id="4199b-134">Для домена приложения по умолчанию измененные параметры переопределяют параметры, заданные в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="4199b-134">For the default application domain, the settings you change override the settings that were specified by the application configuration file.</span></span> <span data-ttu-id="4199b-135">Для других доменов приложений они переопределяют параметры конфигурации, переданные <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> в метод или. <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="4199b-135">For other application domains, they override the configuration settings that were passed to the <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> or <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="4199b-136">Можно либо передать новые сведения о конфигурации, либо передать значение NULL`Nothing` (в Visual Basic), чтобы исключить переданные конфигурации.</span><span class="sxs-lookup"><span data-stu-id="4199b-136">You can either pass new configuration information, or pass null (`Nothing` in Visual Basic) to eliminate configuration information that was passed in.</span></span>  
  
 <span data-ttu-id="4199b-137">Не следует передавать сведения о конфигурации как в <xref:System.AppDomainSetup.ConfigurationFile%2A> свойство, так <xref:System.AppDomainSetup.SetConfigurationBytes%2A> и в метод.</span><span class="sxs-lookup"><span data-stu-id="4199b-137">Do not pass configuration information to both the <xref:System.AppDomainSetup.ConfigurationFile%2A> property and the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method.</span></span> <span data-ttu-id="4199b-138">Если данные о конфигурации передаются в оба значения, то данные, <xref:System.AppDomainSetup.ConfigurationFile%2A> передаваемые в свойство, игнорируются, <xref:System.AppDomainSetup.SetConfigurationBytes%2A> так как метод переопределяет сведения о конфигурации из файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="4199b-138">If you pass configuration information to both, the information you pass to the <xref:System.AppDomainSetup.ConfigurationFile%2A> property is ignored, because the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method overrides configuration information from the application configuration file.</span></span> <span data-ttu-id="4199b-139">При <xref:System.AppDomainSetup.ConfigurationFile%2A> использовании свойства можно передать значение null (`Nothing` <xref:System.AppDomainSetup.SetConfigurationBytes%2A> в Visual Basic) методу, чтобы исключить все байты конфигурации <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> , указанные в вызове метода или <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="4199b-139">If you use the <xref:System.AppDomainSetup.ConfigurationFile%2A> property, you can pass null (`Nothing` in Visual Basic) to the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method to eliminate any configuration bytes that were specified in the call to the <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> or <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="4199b-140">Помимо сведений о конфигурации, можно изменить следующие параметры <xref:System.AppDomainSetup> объекта, который передается в реализацию <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> метода: <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A>, <xref:System.AppDomainSetup.CachePath%2A>,, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A> <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A> , <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, ,,<xref:System.AppDomainSetup.LoaderOptimization%2A>,, и<xref:System.AppDomainSetup.ShadowCopyDirectories%2A>. <xref:System.AppDomainSetup.PrivateBinPath%2A> <xref:System.AppDomainSetup.PrivateBinPathProbe%2A> <xref:System.AppDomainSetup.DynamicBase%2A> <xref:System.AppDomainSetup.ShadowCopyFiles%2A></span><span class="sxs-lookup"><span data-stu-id="4199b-140">In addition to configuration information, you can change the following settings on the <xref:System.AppDomainSetup> object that is passed to your implementation of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method: <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A>, <xref:System.AppDomainSetup.CachePath%2A>, <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A>, <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, <xref:System.AppDomainSetup.DynamicBase%2A>, <xref:System.AppDomainSetup.LoaderOptimization%2A>, <xref:System.AppDomainSetup.PrivateBinPath%2A>, <xref:System.AppDomainSetup.PrivateBinPathProbe%2A>, <xref:System.AppDomainSetup.ShadowCopyDirectories%2A>, and <xref:System.AppDomainSetup.ShadowCopyFiles%2A>.</span></span>  
  
 <span data-ttu-id="4199b-141">В качестве альтернативы использованию `<disableFusionUpdatesFromADManager>` элемента можно отключить поведение по умолчанию, создав параметр реестра или задав переменную среды.</span><span class="sxs-lookup"><span data-stu-id="4199b-141">As an alternative to using the `<disableFusionUpdatesFromADManager>` element, you can disable the default behavior by creating a registry setting or by setting an environment variable.</span></span> <span data-ttu-id="4199b-142">В реестре создайте значение DWORD с именем `COMPLUS_disableFusionUpdatesFromADManager` в разделе `HKCU\Software\Microsoft\.NETFramework` или `HKLM\Software\Microsoft\.NETFramework`и установите значение 1.</span><span class="sxs-lookup"><span data-stu-id="4199b-142">In the registry, create a DWORD value named `COMPLUS_disableFusionUpdatesFromADManager` under `HKCU\Software\Microsoft\.NETFramework` or `HKLM\Software\Microsoft\.NETFramework`, and set the value to 1.</span></span> <span data-ttu-id="4199b-143">В командной строке задайте для переменной `COMPLUS_disableFusionUpdatesFromADManager` среды значение 1.</span><span class="sxs-lookup"><span data-stu-id="4199b-143">At the command line, set the environment variable `COMPLUS_disableFusionUpdatesFromADManager` to 1.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4199b-144">Пример</span><span class="sxs-lookup"><span data-stu-id="4199b-144">Example</span></span>  
 <span data-ttu-id="4199b-145">В следующем примере показано, как отключить возможность переопределения параметров Fusion с помощью `<disableFusionUpdatesFromADManager>` элемента.</span><span class="sxs-lookup"><span data-stu-id="4199b-145">The following example shows how to disable the ability to override Fusion settings by using the `<disableFusionUpdatesFromADManager>` element.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableFusionUpdatesFromADManager enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4199b-146">См. также</span><span class="sxs-lookup"><span data-stu-id="4199b-146">See also</span></span>

- [<span data-ttu-id="4199b-147">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="4199b-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="4199b-148">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="4199b-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="4199b-149">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="4199b-149">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
