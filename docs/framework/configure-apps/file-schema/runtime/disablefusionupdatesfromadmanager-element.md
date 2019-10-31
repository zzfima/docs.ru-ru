---
title: Элемент <disableFusionUpdatesFromADManager>
ms.date: 03/30/2017
helpviewer_keywords:
- disableFusionUpdatesFromADManager element
- <disableFusionUpdatesFromADManager> element
ms.assetid: 58d2866c-37bd-4ffa-abaf-ff35926a2939
ms.openlocfilehash: 4e7375fddaa98b45766b29d911d555f773edcafa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73117442"
---
# <a name="disablefusionupdatesfromadmanager-element"></a><span data-ttu-id="e7f01-102">\<Дисаблефусионупдатесфромадманажер > элемент</span><span class="sxs-lookup"><span data-stu-id="e7f01-102">\<disableFusionUpdatesFromADManager> Element</span></span>
<span data-ttu-id="e7f01-103">Указывает, отключено ли поведение по умолчанию, которое разрешает хост-приложению среды выполнения переопределять параметры конфигурации для домена приложения.</span><span class="sxs-lookup"><span data-stu-id="e7f01-103">Specifies whether the default behavior, which is to allow the runtime host to override configuration settings for an application domain, is disabled.</span></span>  
  
<span data-ttu-id="e7f01-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e7f01-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e7f01-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="e7f01-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="e7f01-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<дисаблефусионупдатесфромадманажер >**</span><span class="sxs-lookup"><span data-stu-id="e7f01-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<disableFusionUpdatesFromADManager>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7f01-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e7f01-107">Syntax</span></span>  
  
```xml  
<disableFusionUpdatesFromADManager enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e7f01-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e7f01-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e7f01-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e7f01-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e7f01-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e7f01-110">Attributes</span></span>  
  
|<span data-ttu-id="e7f01-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e7f01-111">Attribute</span></span>|<span data-ttu-id="e7f01-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e7f01-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e7f01-113">enabled</span><span class="sxs-lookup"><span data-stu-id="e7f01-113">enabled</span></span>|<span data-ttu-id="e7f01-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="e7f01-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="e7f01-115">Указывает, отключена ли возможность по умолчанию переопределять параметры Fusion.</span><span class="sxs-lookup"><span data-stu-id="e7f01-115">Specifies whether the default ability to override Fusion settings is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="e7f01-116">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="e7f01-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="e7f01-117">значения</span><span class="sxs-lookup"><span data-stu-id="e7f01-117">Value</span></span>|<span data-ttu-id="e7f01-118">Описание</span><span class="sxs-lookup"><span data-stu-id="e7f01-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e7f01-119">0</span><span class="sxs-lookup"><span data-stu-id="e7f01-119">0</span></span>|<span data-ttu-id="e7f01-120">Не отключайте возможность переопределения параметров Fusion.</span><span class="sxs-lookup"><span data-stu-id="e7f01-120">Do not disable the ability to override Fusion settings.</span></span> <span data-ttu-id="e7f01-121">Это поведение по умолчанию, начиная с .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="e7f01-121">This is the default behavior, starting with the .NET Framework 4.</span></span>|  
|<span data-ttu-id="e7f01-122">1</span><span class="sxs-lookup"><span data-stu-id="e7f01-122">1</span></span>|<span data-ttu-id="e7f01-123">Отключить возможность переопределения параметров Fusion.</span><span class="sxs-lookup"><span data-stu-id="e7f01-123">Disable the ability to override Fusion settings.</span></span> <span data-ttu-id="e7f01-124">Это позволяет вернуться к поведению более ранних версий .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e7f01-124">This reverts to the behavior of earlier versions of the .NET Framework.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e7f01-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e7f01-125">Child Elements</span></span>  
 <span data-ttu-id="e7f01-126">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e7f01-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e7f01-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e7f01-127">Parent Elements</span></span>  
  
|<span data-ttu-id="e7f01-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="e7f01-128">Element</span></span>|<span data-ttu-id="e7f01-129">Описание</span><span class="sxs-lookup"><span data-stu-id="e7f01-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e7f01-130">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e7f01-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="e7f01-131">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="e7f01-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7f01-132">Заметки</span><span class="sxs-lookup"><span data-stu-id="e7f01-132">Remarks</span></span>  
 <span data-ttu-id="e7f01-133">Начиная с .NET Framework 4, поведение по умолчанию — разрешить объекту <xref:System.AppDomainManager> переопределять параметры конфигурации с помощью свойства <xref:System.AppDomainSetup.ConfigurationFile%2A> или метода <xref:System.AppDomainSetup.SetConfigurationBytes%2A> объекта <xref:System.AppDomainSetup>, который передается в реализацию метода <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType>. в подклассе <xref:System.AppDomainManager>.</span><span class="sxs-lookup"><span data-stu-id="e7f01-133">Starting with the .NET Framework 4, the default behavior is to allow the <xref:System.AppDomainManager> object to override configuration settings by using the <xref:System.AppDomainSetup.ConfigurationFile%2A> property or the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method of the <xref:System.AppDomainSetup> object that is passed to your implementation of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method, in your subclass of <xref:System.AppDomainManager>.</span></span> <span data-ttu-id="e7f01-134">Для домена приложения по умолчанию измененные параметры переопределяют параметры, заданные в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="e7f01-134">For the default application domain, the settings you change override the settings that were specified by the application configuration file.</span></span> <span data-ttu-id="e7f01-135">Для других доменов приложений они переопределяют параметры конфигурации, которые были переданы методу <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> или <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e7f01-135">For other application domains, they override the configuration settings that were passed to the <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> or <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="e7f01-136">Можно либо передать новые сведения о конфигурации, либо передать значение null (`Nothing` в Visual Basic), чтобы исключить переданные конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e7f01-136">You can either pass new configuration information, or pass null (`Nothing` in Visual Basic) to eliminate configuration information that was passed in.</span></span>  
  
 <span data-ttu-id="e7f01-137">Не следует передавать сведения о конфигурации как в свойство <xref:System.AppDomainSetup.ConfigurationFile%2A>, так и в метод <xref:System.AppDomainSetup.SetConfigurationBytes%2A>.</span><span class="sxs-lookup"><span data-stu-id="e7f01-137">Do not pass configuration information to both the <xref:System.AppDomainSetup.ConfigurationFile%2A> property and the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method.</span></span> <span data-ttu-id="e7f01-138">Если данные конфигурации передаются в оба значения, то данные, передаваемые в свойство <xref:System.AppDomainSetup.ConfigurationFile%2A>, игнорируются, так как метод <xref:System.AppDomainSetup.SetConfigurationBytes%2A> переопределяет сведения о конфигурации из файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="e7f01-138">If you pass configuration information to both, the information you pass to the <xref:System.AppDomainSetup.ConfigurationFile%2A> property is ignored, because the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method overrides configuration information from the application configuration file.</span></span> <span data-ttu-id="e7f01-139">При использовании свойства <xref:System.AppDomainSetup.ConfigurationFile%2A> можно передать NULL (`Nothing` в Visual Basic) методу <xref:System.AppDomainSetup.SetConfigurationBytes%2A>, чтобы исключить все байты конфигурации, указанные в вызове метода <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> или <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e7f01-139">If you use the <xref:System.AppDomainSetup.ConfigurationFile%2A> property, you can pass null (`Nothing` in Visual Basic) to the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method to eliminate any configuration bytes that were specified in the call to the <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> or <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="e7f01-140">Помимо сведений о конфигурации, можно изменить следующие параметры объекта <xref:System.AppDomainSetup>, который передается в реализацию метода <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType>: <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A>, <xref:System.AppDomainSetup.CachePath%2A>, <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A>, <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, <xref:System.AppDomainSetup.DynamicBase%2A>, <xref:System.AppDomainSetup.LoaderOptimization%2A>, <xref:System.AppDomainSetup.PrivateBinPath%2A>, <xref:System.AppDomainSetup.PrivateBinPathProbe%2A>, <xref:System.AppDomainSetup.ShadowCopyDirectories%2A>и <xref:System.AppDomainSetup.ShadowCopyFiles%2A>.</span><span class="sxs-lookup"><span data-stu-id="e7f01-140">In addition to configuration information, you can change the following settings on the <xref:System.AppDomainSetup> object that is passed to your implementation of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method: <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A>, <xref:System.AppDomainSetup.CachePath%2A>, <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A>, <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, <xref:System.AppDomainSetup.DynamicBase%2A>, <xref:System.AppDomainSetup.LoaderOptimization%2A>, <xref:System.AppDomainSetup.PrivateBinPath%2A>, <xref:System.AppDomainSetup.PrivateBinPathProbe%2A>, <xref:System.AppDomainSetup.ShadowCopyDirectories%2A>, and <xref:System.AppDomainSetup.ShadowCopyFiles%2A>.</span></span>  
  
 <span data-ttu-id="e7f01-141">В качестве альтернативы использованию элемента `<disableFusionUpdatesFromADManager>` можно отключить поведение по умолчанию, создав параметр реестра или задав переменную среды.</span><span class="sxs-lookup"><span data-stu-id="e7f01-141">As an alternative to using the `<disableFusionUpdatesFromADManager>` element, you can disable the default behavior by creating a registry setting or by setting an environment variable.</span></span> <span data-ttu-id="e7f01-142">В реестре создайте значение DWORD с именем `COMPLUS_disableFusionUpdatesFromADManager` в разделе `HKCU\Software\Microsoft\.NETFramework` или `HKLM\Software\Microsoft\.NETFramework`и установите значение 1.</span><span class="sxs-lookup"><span data-stu-id="e7f01-142">In the registry, create a DWORD value named `COMPLUS_disableFusionUpdatesFromADManager` under `HKCU\Software\Microsoft\.NETFramework` or `HKLM\Software\Microsoft\.NETFramework`, and set the value to 1.</span></span> <span data-ttu-id="e7f01-143">В командной строке задайте для переменной среды `COMPLUS_disableFusionUpdatesFromADManager` значение 1.</span><span class="sxs-lookup"><span data-stu-id="e7f01-143">At the command line, set the environment variable `COMPLUS_disableFusionUpdatesFromADManager` to 1.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7f01-144">Пример</span><span class="sxs-lookup"><span data-stu-id="e7f01-144">Example</span></span>  
 <span data-ttu-id="e7f01-145">В следующем примере показано, как отключить возможность переопределения параметров Fusion с помощью элемента `<disableFusionUpdatesFromADManager>`.</span><span class="sxs-lookup"><span data-stu-id="e7f01-145">The following example shows how to disable the ability to override Fusion settings by using the `<disableFusionUpdatesFromADManager>` element.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableFusionUpdatesFromADManager enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e7f01-146">См. также</span><span class="sxs-lookup"><span data-stu-id="e7f01-146">See also</span></span>

- [<span data-ttu-id="e7f01-147">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="e7f01-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e7f01-148">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="e7f01-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="e7f01-149">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="e7f01-149">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
