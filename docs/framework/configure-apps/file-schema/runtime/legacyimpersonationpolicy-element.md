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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da01d0dac2e67d6c0131a2b5965472bbd19213fe
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927319"
---
# <a name="legacyimpersonationpolicy-element"></a><span data-ttu-id="83ae0-102">\<Элемент > Легациимперсонатионполици</span><span class="sxs-lookup"><span data-stu-id="83ae0-102">\<legacyImpersonationPolicy> Element</span></span>
<span data-ttu-id="83ae0-103">Указывает, что удостоверение Windows не проходит через асинхронные точки, независимо от параметров потока для контекста выполнения в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="83ae0-103">Specifies that the Windows identity does not flow across asynchronous points, regardless of the flow settings for the execution context on the current thread.</span></span>  
  
 <span data-ttu-id="83ae0-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="83ae0-104">\<configuration></span></span>  
<span data-ttu-id="83ae0-105">\<> среды выполнения</span><span class="sxs-lookup"><span data-stu-id="83ae0-105">\<runtime></span></span>  
<span data-ttu-id="83ae0-106">\<Легациимперсонатионполици ></span><span class="sxs-lookup"><span data-stu-id="83ae0-106">\<legacyImpersonationPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83ae0-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83ae0-107">Syntax</span></span>  
  
```xml  
<legacyImpersonationPolicy    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="83ae0-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="83ae0-108">Attributes and Elements</span></span>  
 <span data-ttu-id="83ae0-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="83ae0-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="83ae0-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="83ae0-110">Attributes</span></span>  
  
|<span data-ttu-id="83ae0-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="83ae0-111">Attribute</span></span>|<span data-ttu-id="83ae0-112">Описание</span><span class="sxs-lookup"><span data-stu-id="83ae0-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="83ae0-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="83ae0-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="83ae0-114">Указывает, что <xref:System.Security.Principal.WindowsIdentity> объект не передается по асинхронным точкам, <xref:System.Threading.ExecutionContext> независимо от параметров потока в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="83ae0-114">Specifies that the <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="83ae0-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="83ae0-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="83ae0-116">Значение</span><span class="sxs-lookup"><span data-stu-id="83ae0-116">Value</span></span>|<span data-ttu-id="83ae0-117">Описание</span><span class="sxs-lookup"><span data-stu-id="83ae0-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="83ae0-118"><xref:System.Security.Principal.WindowsIdentity>проходит через асинхронные точки в зависимости от <xref:System.Threading.ExecutionContext> параметров потока для текущего потока.</span><span class="sxs-lookup"><span data-stu-id="83ae0-118"><xref:System.Security.Principal.WindowsIdentity> flows across asynchronous points depending upon the <xref:System.Threading.ExecutionContext> flow settings for the current thread.</span></span> <span data-ttu-id="83ae0-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="83ae0-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="83ae0-120"><xref:System.Security.Principal.WindowsIdentity>не перетекает через асинхронные точки, независимо от <xref:System.Threading.ExecutionContext> параметров потока в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="83ae0-120"><xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="83ae0-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="83ae0-121">Child Elements</span></span>  
 <span data-ttu-id="83ae0-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="83ae0-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="83ae0-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="83ae0-123">Parent Elements</span></span>  
  
|<span data-ttu-id="83ae0-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="83ae0-124">Element</span></span>|<span data-ttu-id="83ae0-125">Описание</span><span class="sxs-lookup"><span data-stu-id="83ae0-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="83ae0-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="83ae0-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="83ae0-127">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="83ae0-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83ae0-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="83ae0-128">Remarks</span></span>  
 <span data-ttu-id="83ae0-129">В .NET Framework версиях 1,0 и 1,1, объект <xref:System.Security.Principal.WindowsIdentity> не проходит через определенные пользователем асинхронные точки.</span><span class="sxs-lookup"><span data-stu-id="83ae0-129">In the .NET Framework versions 1.0 and 1.1, the <xref:System.Security.Principal.WindowsIdentity> does not flow across any user-defined asynchronous points.</span></span> <span data-ttu-id="83ae0-130">Начиная с версии .NET Framework 2,0, существует <xref:System.Threading.ExecutionContext> объект, который содержит сведения о выполняющемся в данный момент потоке и проходит через асинхронные точки в пределах домена приложения.</span><span class="sxs-lookup"><span data-stu-id="83ae0-130">Starting with the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and it flows across asynchronous points within an application domain.</span></span> <span data-ttu-id="83ae0-131"><xref:System.Security.Principal.WindowsIdentity> Включается в этот контекст выполнения и, следовательно, проходит через асинхронные точки, что означает, что если контекст олицетворения существует, он также будет работать.</span><span class="sxs-lookup"><span data-stu-id="83ae0-131">The <xref:System.Security.Principal.WindowsIdentity> is included in this execution context and therefore also flows across the asynchronous points, which means that if an impersonation context exists, it will flow as well.</span></span>  
  
 <span data-ttu-id="83ae0-132">Начиная с .NET Framework 2,0, можно использовать `<legacyImpersonationPolicy>` элемент, чтобы указать, что <xref:System.Security.Principal.WindowsIdentity> не передается через асинхронные точки.</span><span class="sxs-lookup"><span data-stu-id="83ae0-132">Starting with the .NET Framework 2.0, you can use the `<legacyImpersonationPolicy>` element to specify that  <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="83ae0-133">Общеязыковая среда выполнения (CLR) осведомлена об операциях олицетворения, выполняемых только с помощью управляемого кода, а не олицетворения, выполненных за пределами управляемого кода, например посредством вызова неуправляемого кода платформой или прямых вызовов функций Win32.</span><span class="sxs-lookup"><span data-stu-id="83ae0-133">The common language runtime (CLR) is aware of impersonation operations performed using only managed code, not of impersonation performed outside of managed code, such as through platform invoke to unmanaged code or through direct calls to Win32 functions.</span></span> <span data-ttu-id="83ae0-134">Только управляемые <xref:System.Security.Principal.WindowsIdentity> объекты могут передаваться по асинхронным точкам, `alwaysFlowImpersonationPolicy` если только элемент не имеет`<alwaysFlowImpersonationPolicy enabled="true"/>`значение true ().</span><span class="sxs-lookup"><span data-stu-id="83ae0-134">Only managed <xref:System.Security.Principal.WindowsIdentity> objects can flow across asynchronous points, unless the `alwaysFlowImpersonationPolicy` element has been set to true (`<alwaysFlowImpersonationPolicy enabled="true"/>`).</span></span> <span data-ttu-id="83ae0-135">Если задать для элемента значение true, удостоверение Windows всегда проходит через асинхронные точки независимо от того, как было выполнено олицетворение. `alwaysFlowImpersonationPolicy`</span><span class="sxs-lookup"><span data-stu-id="83ae0-135">Setting the `alwaysFlowImpersonationPolicy` element to true specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span> <span data-ttu-id="83ae0-136">Дополнительные сведения о передаче неуправляемого олицетворения через асинхронные точки см. в разделе [ \<алвайсфловимперсонатионполици > Element](alwaysflowimpersonationpolicy-element.md).</span><span class="sxs-lookup"><span data-stu-id="83ae0-136">For more information on flowing unmanaged impersonation across asynchronous points, see [\<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).</span></span>  
  
 <span data-ttu-id="83ae0-137">Это поведение по умолчанию можно изменить двумя способами.</span><span class="sxs-lookup"><span data-stu-id="83ae0-137">You can alter this default behavior in two other ways:</span></span>  
  
1. <span data-ttu-id="83ae0-138">В управляемом коде на основе каждого потока.</span><span class="sxs-lookup"><span data-stu-id="83ae0-138">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="83ae0-139">Можно <xref:System.Threading.ExecutionContext> подавить поток на основе каждого потока, изменив параметры и <xref:System.Security.SecurityContext> с помощью <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>метода, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> или <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="83ae0-139">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="83ae0-140">В вызове неуправляемого интерфейса размещения для загрузки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="83ae0-140">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="83ae0-141">Если для загрузки среды CLR используется неуправляемый интерфейс размещения (вместо простого управляемого исполняемого файла), можно указать специальный флаг в вызове функции [функции CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) .</span><span class="sxs-lookup"><span data-stu-id="83ae0-141">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="83ae0-142">Чтобы включить режим совместимости для всего процесса, задайте `flags` для параметра [CorBindToRuntimeEx функции](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) значение STARTUP_LEGACY_IMPERSONATION.</span><span class="sxs-lookup"><span data-stu-id="83ae0-142">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) to STARTUP_LEGACY_IMPERSONATION.</span></span>  
  
 <span data-ttu-id="83ae0-143">Дополнительные сведения см. в [ \<описании элемента алвайсфловимперсонатионполици >](alwaysflowimpersonationpolicy-element.md).</span><span class="sxs-lookup"><span data-stu-id="83ae0-143">For more information, see the [\<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="83ae0-144">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="83ae0-144">Configuration File</span></span>  
 <span data-ttu-id="83ae0-145">В приложении .NET Framework этот элемент можно использовать только в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="83ae0-145">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="83ae0-146">Для приложения ASP.NET поток олицетворения можно настроить в файле aspnet. config, который \<находится в папке Windows > \микрософт.нет\фрамеворк\вкс.КС.кскскскс.</span><span class="sxs-lookup"><span data-stu-id="83ae0-146">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="83ae0-147">ASP.NET по умолчанию отключает поток олицетворения в файле aspnet. config, используя следующие параметры конфигурации:</span><span class="sxs-lookup"><span data-stu-id="83ae0-147">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
``` xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="83ae0-148">В ASP.NET, если требуется разрешить поток олицетворения, необходимо явно использовать следующие параметры конфигурации:</span><span class="sxs-lookup"><span data-stu-id="83ae0-148">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="83ae0-149">Пример</span><span class="sxs-lookup"><span data-stu-id="83ae0-149">Example</span></span>  
 <span data-ttu-id="83ae0-150">В следующем примере показано, как задать устаревшее поведение, которое не пополняет удостоверение Windows в асинхронных точках.</span><span class="sxs-lookup"><span data-stu-id="83ae0-150">The following example shows how to specify the legacy behavior that does not flow the Windows identity across asynchronous points.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="83ae0-151">См. также</span><span class="sxs-lookup"><span data-stu-id="83ae0-151">See also</span></span>

- [<span data-ttu-id="83ae0-152">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="83ae0-152">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="83ae0-153">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="83ae0-153">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="83ae0-154">\<Элемент > Алвайсфловимперсонатионполици</span><span class="sxs-lookup"><span data-stu-id="83ae0-154">\<alwaysFlowImpersonationPolicy> Element</span></span>](alwaysflowimpersonationpolicy-element.md)
