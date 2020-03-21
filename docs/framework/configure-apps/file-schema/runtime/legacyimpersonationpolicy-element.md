---
title: Элемент <legacyImpersonationPolicy>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#legacyImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/legacyImpersonationPolicy
helpviewer_keywords:
- <legacyImpersonationPolicy> element
- legacyImpersonationPolicy element
ms.assetid: 6e00af10-42f3-4235-8415-1bb2db78394e
ms.openlocfilehash: 5e43ead278ecd4049014f4000a2f056b2190f7e5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154108"
---
# <a name="legacyimpersonationpolicy-element"></a><span data-ttu-id="92e9c-102">\<legacyImpersonationПолитика> Элемент</span><span class="sxs-lookup"><span data-stu-id="92e9c-102">\<legacyImpersonationPolicy> Element</span></span>
<span data-ttu-id="92e9c-103">Указывает, что удостоверение Windows не проходит через асинхронные точки, независимо от параметров потока для контекста выполнения в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="92e9c-103">Specifies that the Windows identity does not flow across asynchronous points, regardless of the flow settings for the execution context on the current thread.</span></span>  
  
<span data-ttu-id="92e9c-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="92e9c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="92e9c-105">&nbsp;&nbsp;[**\<>выполнения**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="92e9c-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="92e9c-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyImpersonationПолитика>**</span><span class="sxs-lookup"><span data-stu-id="92e9c-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyImpersonationPolicy>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92e9c-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="92e9c-107">Syntax</span></span>  
  
```xml  
<legacyImpersonationPolicy
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="92e9c-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="92e9c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="92e9c-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="92e9c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="92e9c-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="92e9c-110">Attributes</span></span>  
  
|<span data-ttu-id="92e9c-111">attribute</span><span class="sxs-lookup"><span data-stu-id="92e9c-111">Attribute</span></span>|<span data-ttu-id="92e9c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="92e9c-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="92e9c-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="92e9c-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="92e9c-114">Уточняется, что <xref:System.Security.Principal.WindowsIdentity> не проходит через асинхронные точки, независимо от настроек <xref:System.Threading.ExecutionContext> потока на текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="92e9c-114">Specifies that the <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="92e9c-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="92e9c-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="92e9c-116">Значение</span><span class="sxs-lookup"><span data-stu-id="92e9c-116">Value</span></span>|<span data-ttu-id="92e9c-117">Описание</span><span class="sxs-lookup"><span data-stu-id="92e9c-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="92e9c-118"><xref:System.Security.Principal.WindowsIdentity>потоки через асинхронные <xref:System.Threading.ExecutionContext> точки в зависимости от настроек потока для текущего потока.</span><span class="sxs-lookup"><span data-stu-id="92e9c-118"><xref:System.Security.Principal.WindowsIdentity> flows across asynchronous points depending upon the <xref:System.Threading.ExecutionContext> flow settings for the current thread.</span></span> <span data-ttu-id="92e9c-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="92e9c-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="92e9c-120"><xref:System.Security.Principal.WindowsIdentity>не течет по асинхронным <xref:System.Threading.ExecutionContext> точкам, независимо от настроек потока на текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="92e9c-120"><xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="92e9c-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="92e9c-121">Child Elements</span></span>  
 <span data-ttu-id="92e9c-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="92e9c-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="92e9c-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="92e9c-123">Parent Elements</span></span>  
  
|<span data-ttu-id="92e9c-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="92e9c-124">Element</span></span>|<span data-ttu-id="92e9c-125">Описание</span><span class="sxs-lookup"><span data-stu-id="92e9c-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="92e9c-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="92e9c-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="92e9c-127">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="92e9c-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="92e9c-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="92e9c-128">Remarks</span></span>  
 <span data-ttu-id="92e9c-129">В версиях .NET Framework 1.0 и <xref:System.Security.Principal.WindowsIdentity> 1.1 не протекают по каким-либо асинхронным точкам, определяемым пользователем.</span><span class="sxs-lookup"><span data-stu-id="92e9c-129">In the .NET Framework versions 1.0 and 1.1, the <xref:System.Security.Principal.WindowsIdentity> does not flow across any user-defined asynchronous points.</span></span> <span data-ttu-id="92e9c-130">Начиная с версии .NET Framework 2.0, есть <xref:System.Threading.ExecutionContext> объект, который содержит информацию о исполняемом потоке, который в настоящее время выполняет сяочие, и он течет по асинхронным точкам в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="92e9c-130">Starting with the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and it flows across asynchronous points within an application domain.</span></span> <span data-ttu-id="92e9c-131">Включено <xref:System.Security.Principal.WindowsIdentity> в этот контекст исполнения и, следовательно, также течет через асинхронные точки, что означает, что если контекст олицетворения существует, он будет течь также.</span><span class="sxs-lookup"><span data-stu-id="92e9c-131">The <xref:System.Security.Principal.WindowsIdentity> is included in this execution context and therefore also flows across the asynchronous points, which means that if an impersonation context exists, it will flow as well.</span></span>  
  
 <span data-ttu-id="92e9c-132">Начиная с .NET Framework 2.0, `<legacyImpersonationPolicy>` можно использовать <xref:System.Security.Principal.WindowsIdentity> элемент, чтобы указать, что не течет по асинхронным точкам.</span><span class="sxs-lookup"><span data-stu-id="92e9c-132">Starting with the .NET Framework 2.0, you can use the `<legacyImpersonationPolicy>` element to specify that  <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="92e9c-133">Общее время выполнения языка (CLR) знает об операциях олицетворения, выполняемых только управляемым кодом, а не олицетворения, выполняемых вне управляемого кода, например, через платформу, ссылающихся на неуправляемый код или через прямые вызовы к функциям Win32.</span><span class="sxs-lookup"><span data-stu-id="92e9c-133">The common language runtime (CLR) is aware of impersonation operations performed using only managed code, not of impersonation performed outside of managed code, such as through platform invoke to unmanaged code or through direct calls to Win32 functions.</span></span> <span data-ttu-id="92e9c-134">Только <xref:System.Security.Principal.WindowsIdentity> управляемые объекты могут течь через `alwaysFlowImpersonationPolicy` асинхронные`<alwaysFlowImpersonationPolicy enabled="true"/>`точки, если элемент не был установлен на истину ( ).</span><span class="sxs-lookup"><span data-stu-id="92e9c-134">Only managed <xref:System.Security.Principal.WindowsIdentity> objects can flow across asynchronous points, unless the `alwaysFlowImpersonationPolicy` element has been set to true (`<alwaysFlowImpersonationPolicy enabled="true"/>`).</span></span> <span data-ttu-id="92e9c-135">Установка `alwaysFlowImpersonationPolicy` элемента на истину указывает на то, что инообразная личность Windows всегда течет по асинхронным точкам, независимо от того, как выполнялось олицетворение.</span><span class="sxs-lookup"><span data-stu-id="92e9c-135">Setting the `alwaysFlowImpersonationPolicy` element to true specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span> <span data-ttu-id="92e9c-136">Для получения дополнительной информации о потоковых неуправляемых олицетворение через асинхронные точки, см [ \<всегдаFlowImpersonationПолитика> элемент](alwaysflowimpersonationpolicy-element.md).</span><span class="sxs-lookup"><span data-stu-id="92e9c-136">For more information on flowing unmanaged impersonation across asynchronous points, see [\<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).</span></span>  
  
 <span data-ttu-id="92e9c-137">Вы можете изменить это поведение по умолчанию двумя другими способами:</span><span class="sxs-lookup"><span data-stu-id="92e9c-137">You can alter this default behavior in two other ways:</span></span>  
  
1. <span data-ttu-id="92e9c-138">В управляемом коде на основе на поток.</span><span class="sxs-lookup"><span data-stu-id="92e9c-138">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="92e9c-139">Вы можете подавить поток на основе потока, <xref:System.Threading.ExecutionContext> <xref:System.Security.SecurityContext> изменяя и <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType> <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> настройки с помощью, или <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="92e9c-139">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="92e9c-140">При вызове к неуправляемому интерфейсу хостинга для загрузки общего языка времени выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="92e9c-140">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="92e9c-141">Если для загрузки CLR используется неуправляемый интерфейс хостинга (вместо простого управляемого исполнителя), можно указать специальный флаг в функции [CorBindToRuntimeEx.](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)</span><span class="sxs-lookup"><span data-stu-id="92e9c-141">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="92e9c-142">Чтобы включить режим совместимости для всего процесса, установите `flags` параметр для [функции CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) STARTUP_LEGACY_IMPERSONATION.</span><span class="sxs-lookup"><span data-stu-id="92e9c-142">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) to STARTUP_LEGACY_IMPERSONATION.</span></span>  
  
 <span data-ttu-id="92e9c-143">Для получения дополнительной [ \<](alwaysflowimpersonationpolicy-element.md)информации, см>.</span><span class="sxs-lookup"><span data-stu-id="92e9c-143">For more information, see the [\<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="92e9c-144">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="92e9c-144">Configuration File</span></span>  
 <span data-ttu-id="92e9c-145">В приложении .NET Framework этот элемент может быть использован только в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="92e9c-145">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="92e9c-146">Для ASP.NET приложения поток олицетворения может быть настроен в файле aspnet.config, найденном в каталоге \<Windows Folder>-Microsoft.NET-Framework-vx.x.xxxx.</span><span class="sxs-lookup"><span data-stu-id="92e9c-146">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="92e9c-147">ASP.NET по умолчанию отменяет поток олицетворения в файле aspnet.config с помощью следующих настроек конфигурации:</span><span class="sxs-lookup"><span data-stu-id="92e9c-147">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
``` xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="92e9c-148">В ASP.NET, если вместо этого требуется разрешить поток олицетворения, необходимо явно использовать следующие настройки конфигурации:</span><span class="sxs-lookup"><span data-stu-id="92e9c-148">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="92e9c-149">Пример</span><span class="sxs-lookup"><span data-stu-id="92e9c-149">Example</span></span>  
 <span data-ttu-id="92e9c-150">В следующем примере показано, как указать устаревающее поведение, которое не пропускает иноедело Windows через асинхронные точки.</span><span class="sxs-lookup"><span data-stu-id="92e9c-150">The following example shows how to specify the legacy behavior that does not flow the Windows identity across asynchronous points.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="92e9c-151">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="92e9c-151">See also</span></span>

- [<span data-ttu-id="92e9c-152">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="92e9c-152">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="92e9c-153">Схема конфигурации файлов</span><span class="sxs-lookup"><span data-stu-id="92e9c-153">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="92e9c-154">\<всегдаFlowImpersonationПолитика> Элемент</span><span class="sxs-lookup"><span data-stu-id="92e9c-154">\<alwaysFlowImpersonationPolicy> Element</span></span>](alwaysflowimpersonationpolicy-element.md)
