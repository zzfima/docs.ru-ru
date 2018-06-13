---
title: '&lt;alwaysFlowImpersonationPolicy&gt; элемент'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/alwaysFlowImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#alwaysFlowImpersonationPolicy
helpviewer_keywords:
- alwaysFlowImpersonationPolicy element
- <alwaysFlowImpersonationPolicy> element
ms.assetid: ee622801-9e46-470b-85ab-88c4b1dd2ee1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5cc704bbf8631936dbbeb3539ea5ed0d8499f378
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32752277"
---
# <a name="ltalwaysflowimpersonationpolicygt-element"></a><span data-ttu-id="6276f-102">&lt;alwaysFlowImpersonationPolicy&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="6276f-102">&lt;alwaysFlowImpersonationPolicy&gt; Element</span></span>
<span data-ttu-id="6276f-103">Указывает, что удостоверение Windows всегда проходит через асинхронные точки, независимо от того, как было выполнено олицетворение.</span><span class="sxs-lookup"><span data-stu-id="6276f-103">Specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>  
  
 <span data-ttu-id="6276f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="6276f-104">\<configuration></span></span>  
<span data-ttu-id="6276f-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="6276f-105">\<runtime></span></span>  
<span data-ttu-id="6276f-106">\<alwaysFlowImpersonationPolicy></span><span class="sxs-lookup"><span data-stu-id="6276f-106">\<alwaysFlowImpersonationPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6276f-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6276f-107">Syntax</span></span>  
  
```xml  
<alwaysFlowImpersonationPolicy    
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6276f-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6276f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6276f-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6276f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6276f-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6276f-110">Attributes</span></span>  
  
|<span data-ttu-id="6276f-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6276f-111">Attribute</span></span>|<span data-ttu-id="6276f-112">Описание</span><span class="sxs-lookup"><span data-stu-id="6276f-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="6276f-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="6276f-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="6276f-114">Указывает, является ли удостоверение Windows проходит через асинхронные точки.</span><span class="sxs-lookup"><span data-stu-id="6276f-114">Indicates whether the Windows identity flows across asynchronous points.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="6276f-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="6276f-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="6276f-116">Значение</span><span class="sxs-lookup"><span data-stu-id="6276f-116">Value</span></span>|<span data-ttu-id="6276f-117">Описание</span><span class="sxs-lookup"><span data-stu-id="6276f-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="6276f-118">Удостоверение не проходит через асинхронные точки, если олицетворение осуществляется с помощью Windows управляемые методы, такие как <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.</span><span class="sxs-lookup"><span data-stu-id="6276f-118">The Windows identity does not flow across asynchronous points, unless the impersonation is performed through managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.</span></span> <span data-ttu-id="6276f-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6276f-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="6276f-120">Идентификация Windows всегда проходит через асинхронные точки, независимо от того, как было выполнено олицетворение.</span><span class="sxs-lookup"><span data-stu-id="6276f-120">The Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6276f-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6276f-121">Child Elements</span></span>  
 <span data-ttu-id="6276f-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="6276f-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6276f-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6276f-123">Parent Elements</span></span>  
  
|<span data-ttu-id="6276f-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="6276f-124">Element</span></span>|<span data-ttu-id="6276f-125">Описание</span><span class="sxs-lookup"><span data-stu-id="6276f-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="6276f-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6276f-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="6276f-127">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="6276f-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6276f-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="6276f-128">Remarks</span></span>  
 <span data-ttu-id="6276f-129">В .NET Framework версий 1.0 и 1.1 удостоверение Windows не проходит через асинхронные точки.</span><span class="sxs-lookup"><span data-stu-id="6276f-129">In the .NET Framework versions 1.0 and 1.1, the Windows identity does not flow across asynchronous points.</span></span> <span data-ttu-id="6276f-130">В платформе .NET Framework версии 2.0 имеется <xref:System.Threading.ExecutionContext> объект, который содержит сведения о текущей выполняемой потока и он проходит через асинхронные точки в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="6276f-130">In the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and flows it across asynchronous points within an application domain.</span></span> <span data-ttu-id="6276f-131"><xref:System.Security.Principal.WindowsIdentity> Также потоки как часть сведений, который проходит через асинхронные точки, если было выполнено олицетворение с помощью управляемых методы, такие как <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> и не через другие средства, такие как платформы неуправляемого кода для собственных методов.</span><span class="sxs-lookup"><span data-stu-id="6276f-131">The <xref:System.Security.Principal.WindowsIdentity> also flows as part of the information that flows across the asynchronous points, provided the impersonation was achieved using managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> and not through other means such as platform invoke to native methods.</span></span> <span data-ttu-id="6276f-132">Этот элемент используется для указания, что удостоверение Windows проходит через асинхронные точки, независимо от того, как было выполнено олицетворение.</span><span class="sxs-lookup"><span data-stu-id="6276f-132">This element is used to specify that the Windows identity does flow across asynchronous points, regardless of how the impersonation was achieved.</span></span>  
  
 <span data-ttu-id="6276f-133">Можно изменить это поведение по умолчанию двумя способами:</span><span class="sxs-lookup"><span data-stu-id="6276f-133">You can alter this default behavior in two other ways:</span></span>  
  
1.  <span data-ttu-id="6276f-134">В управляемом коде для каждого потока.</span><span class="sxs-lookup"><span data-stu-id="6276f-134">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="6276f-135">Поток для каждого потока можно отключить, изменив <xref:System.Threading.ExecutionContext> и <xref:System.Security.SecurityContext> параметры с помощью <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, или <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="6276f-135">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2.  <span data-ttu-id="6276f-136">В вызове неуправляемого интерфейса размещения для загрузки общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="6276f-136">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="6276f-137">Если неуправляемый интерфейс размещения (вместо простого управляемого исполняемого файла) используется для загрузки среды CLR, можно указать специальный флаг в вызове [функция CorBindToRuntimeEx](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="6276f-137">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="6276f-138">Чтобы включить режим совместимости для всего процесса, задайте `flags` параметр [функция CorBindToRuntimeEx](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) для `STARTUP_ALWAYSFLOW_IMPERSONATION`.</span><span class="sxs-lookup"><span data-stu-id="6276f-138">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) to `STARTUP_ALWAYSFLOW_IMPERSONATION`.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="6276f-139">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="6276f-139">Configuration File</span></span>  
 <span data-ttu-id="6276f-140">В приложениях .NET Framework этот элемент может использоваться только в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="6276f-140">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="6276f-141">Для приложения ASP.NET поток олицетворения можно настраивать в файле aspnet.config в \<папка Windows > \Microsoft.NET\Framework\vx.x.xxxx каталога.</span><span class="sxs-lookup"><span data-stu-id="6276f-141">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="6276f-142">ASP.NET по умолчанию отключает поток олицетворения в файле aspnet.config, используя следующие параметры конфигурации:</span><span class="sxs-lookup"><span data-stu-id="6276f-142">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
```xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="6276f-143">В ASP.NET Если вы хотите разрешить поток олицетворения, вместо этого необходимо явно использовать следующие параметры конфигурации:</span><span class="sxs-lookup"><span data-stu-id="6276f-143">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="6276f-144">Пример</span><span class="sxs-lookup"><span data-stu-id="6276f-144">Example</span></span>  
 <span data-ttu-id="6276f-145">Приведенный ниже показано, как указать, что удостоверение Windows проходит через асинхронные точки, даже в том случае, если олицетворение достигается с помощью средств, отличных от управляемых методов.</span><span class="sxs-lookup"><span data-stu-id="6276f-145">The following example shows how to specify that the Windows identity flows across asynchronous points, even when the impersonation is achieved through means other than managed methods.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6276f-146">См. также</span><span class="sxs-lookup"><span data-stu-id="6276f-146">See Also</span></span>  
 [<span data-ttu-id="6276f-147">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="6276f-147">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="6276f-148">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="6276f-148">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="6276f-149">\<legacyImpersonationPolicy > элемент</span><span class="sxs-lookup"><span data-stu-id="6276f-149">\<legacyImpersonationPolicy> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)
