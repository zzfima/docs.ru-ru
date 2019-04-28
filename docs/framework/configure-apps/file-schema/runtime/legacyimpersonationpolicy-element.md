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
ms.openlocfilehash: c39ee551dde19d87a75403f3db7433d1ef829f3b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704639"
---
# <a name="legacyimpersonationpolicy-element"></a><span data-ttu-id="4ab88-102">\<legacyImpersonationPolicy > элемент</span><span class="sxs-lookup"><span data-stu-id="4ab88-102">\<legacyImpersonationPolicy> Element</span></span>
<span data-ttu-id="4ab88-103">Указывает, что удостоверение Windows не проходит через асинхронные точки, независимо от параметров потока для контекста выполнения в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="4ab88-103">Specifies that the Windows identity does not flow across asynchronous points, regardless of the flow settings for the execution context on the current thread.</span></span>  
  
 <span data-ttu-id="4ab88-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4ab88-104">\<configuration></span></span>  
<span data-ttu-id="4ab88-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="4ab88-105">\<runtime></span></span>  
<span data-ttu-id="4ab88-106">\<legacyImpersonationPolicy ></span><span class="sxs-lookup"><span data-stu-id="4ab88-106">\<legacyImpersonationPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ab88-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4ab88-107">Syntax</span></span>  
  
```xml  
<legacyImpersonationPolicy    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4ab88-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4ab88-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4ab88-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4ab88-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4ab88-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4ab88-110">Attributes</span></span>  
  
|<span data-ttu-id="4ab88-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4ab88-111">Attribute</span></span>|<span data-ttu-id="4ab88-112">Описание</span><span class="sxs-lookup"><span data-stu-id="4ab88-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="4ab88-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="4ab88-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="4ab88-114">Указывает, что <xref:System.Security.Principal.WindowsIdentity> не проходит через асинхронные точки, вне зависимости от <xref:System.Threading.ExecutionContext> настройки в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="4ab88-114">Specifies that the <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="4ab88-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="4ab88-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="4ab88-116">Значение</span><span class="sxs-lookup"><span data-stu-id="4ab88-116">Value</span></span>|<span data-ttu-id="4ab88-117">Описание</span><span class="sxs-lookup"><span data-stu-id="4ab88-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="4ab88-118"><xref:System.Security.Principal.WindowsIdentity> проходит через асинхронные точки, в зависимости от <xref:System.Threading.ExecutionContext> настройки для текущего потока.</span><span class="sxs-lookup"><span data-stu-id="4ab88-118"><xref:System.Security.Principal.WindowsIdentity> flows across asynchronous points depending upon the <xref:System.Threading.ExecutionContext> flow settings for the current thread.</span></span> <span data-ttu-id="4ab88-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4ab88-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="4ab88-120"><xref:System.Security.Principal.WindowsIdentity> не проходит через асинхронные точки, вне зависимости от <xref:System.Threading.ExecutionContext> настройки в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="4ab88-120"><xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4ab88-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4ab88-121">Child Elements</span></span>  
 <span data-ttu-id="4ab88-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="4ab88-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4ab88-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4ab88-123">Parent Elements</span></span>  
  
|<span data-ttu-id="4ab88-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="4ab88-124">Element</span></span>|<span data-ttu-id="4ab88-125">Описание</span><span class="sxs-lookup"><span data-stu-id="4ab88-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4ab88-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4ab88-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="4ab88-127">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="4ab88-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ab88-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="4ab88-128">Remarks</span></span>  
 <span data-ttu-id="4ab88-129">В .NET Framework версий 1.0 и 1.1 <xref:System.Security.Principal.WindowsIdentity> не проходит через асинхронные точки все определяемые пользователем.</span><span class="sxs-lookup"><span data-stu-id="4ab88-129">In the .NET Framework versions 1.0 and 1.1, the <xref:System.Security.Principal.WindowsIdentity> does not flow across any user-defined asynchronous points.</span></span> <span data-ttu-id="4ab88-130">Начиная с .NET Framework версии 2.0, имеется <xref:System.Threading.ExecutionContext> , содержащий сведения о текущем потоке и он проходит через асинхронные точки в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="4ab88-130">Starting with the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and it flows across asynchronous points within an application domain.</span></span> <span data-ttu-id="4ab88-131"><xref:System.Security.Principal.WindowsIdentity> Включается в этот контекст выполнения и таким образом, также проходит через асинхронные точки, это означает, что если существует контекст олицетворения, то оно будет доставлено также.</span><span class="sxs-lookup"><span data-stu-id="4ab88-131">The <xref:System.Security.Principal.WindowsIdentity> is included in this execution context and therefore also flows across the asynchronous points, which means that if an impersonation context exists, it will flow as well.</span></span>  
  
 <span data-ttu-id="4ab88-132">Начиная с .NET Framework 2.0, можно использовать `<legacyImpersonationPolicy>` элемент, чтобы указать, что <xref:System.Security.Principal.WindowsIdentity> не проходит через асинхронные точки.</span><span class="sxs-lookup"><span data-stu-id="4ab88-132">Starting with the .NET Framework 2.0, you can use the `<legacyImpersonationPolicy>` element to specify that  <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ab88-133">Среда CLR (CLR) известно олицетворения операции, выполняемые только с помощью управляемого кода, не олицетворения, выполняемое за пределами управляемого кода, например с помощью платформы вызова неуправляемого кода или через прямое обращение к функции Win32.</span><span class="sxs-lookup"><span data-stu-id="4ab88-133">The common language runtime (CLR) is aware of impersonation operations performed using only managed code, not of impersonation performed outside of managed code, such as through platform invoke to unmanaged code or through direct calls to Win32 functions.</span></span> <span data-ttu-id="4ab88-134">Только для управляемого <xref:System.Security.Principal.WindowsIdentity> объектов можно проходит через асинхронные точки, если не `alwaysFlowImpersonationPolicy` было установлено значение true (`<alwaysFlowImpersonationPolicy enabled="true"/>`).</span><span class="sxs-lookup"><span data-stu-id="4ab88-134">Only managed <xref:System.Security.Principal.WindowsIdentity> objects can flow across asynchronous points, unless the `alwaysFlowImpersonationPolicy` element has been set to true (`<alwaysFlowImpersonationPolicy enabled="true"/>`).</span></span> <span data-ttu-id="4ab88-135">Параметр `alwaysFlowImpersonationPolicy` элемент значение true указывает, что удостоверение Windows всегда проходит через асинхронные точки, независимо от того, как было выполнено олицетворение.</span><span class="sxs-lookup"><span data-stu-id="4ab88-135">Setting the `alwaysFlowImpersonationPolicy` element to true specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span> <span data-ttu-id="4ab88-136">Дополнительные сведения о прохождении неуправляемого олицетворения через асинхронные точки, см. в разделе [ \<alwaysFlowImpersonationPolicy > элемента](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).</span><span class="sxs-lookup"><span data-stu-id="4ab88-136">For more information on flowing unmanaged impersonation across asynchronous points, see [\<alwaysFlowImpersonationPolicy> Element](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).</span></span>  
  
 <span data-ttu-id="4ab88-137">Можно изменить это поведение по умолчанию двумя способами:</span><span class="sxs-lookup"><span data-stu-id="4ab88-137">You can alter this default behavior in two other ways:</span></span>  
  
1. <span data-ttu-id="4ab88-138">В управляемом коде для каждого потока.</span><span class="sxs-lookup"><span data-stu-id="4ab88-138">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="4ab88-139">Поток для каждого потока можно отключить, изменив <xref:System.Threading.ExecutionContext> и <xref:System.Security.SecurityContext> параметры с помощью <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> или <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="4ab88-139">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="4ab88-140">В вызове неуправляемого интерфейса размещения для загрузки общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="4ab88-140">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="4ab88-141">Если неуправляемый интерфейс размещения (вместо простой управляемый исполняемый файл) используется для загрузки среды CLR, можно указать специальный флаг в вызове [функция CorBindToRuntimeEx](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="4ab88-141">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="4ab88-142">Чтобы включить режим совместимости для всего процесса, задайте `flags` параметр для [функция CorBindToRuntimeEx](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) для STARTUP_LEGACY_IMPERSONATION.</span><span class="sxs-lookup"><span data-stu-id="4ab88-142">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) to STARTUP_LEGACY_IMPERSONATION.</span></span>  
  
 <span data-ttu-id="4ab88-143">Дополнительные сведения см. в разделе [ \<alwaysFlowImpersonationPolicy > элемента](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).</span><span class="sxs-lookup"><span data-stu-id="4ab88-143">For more information, see the [\<alwaysFlowImpersonationPolicy> Element](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="4ab88-144">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="4ab88-144">Configuration File</span></span>  
 <span data-ttu-id="4ab88-145">В приложении .NET Framework этот элемент может использоваться только в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="4ab88-145">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="4ab88-146">Для приложения ASP.NET поток олицетворения можно настроить в файле aspnet.config в \<папка Windows > \Microsoft.NET\Framework\vx.x.xxxx каталога.</span><span class="sxs-lookup"><span data-stu-id="4ab88-146">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="4ab88-147">ASP.NET по умолчанию отключает поток олицетворения в файле aspnet.config, используя следующие параметры конфигурации:</span><span class="sxs-lookup"><span data-stu-id="4ab88-147">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
``` xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="4ab88-148">В ASP.NET Если вы хотите разрешить поток олицетворения, вместо этого необходимо явно использовать следующие параметры конфигурации:</span><span class="sxs-lookup"><span data-stu-id="4ab88-148">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="4ab88-149">Пример</span><span class="sxs-lookup"><span data-stu-id="4ab88-149">Example</span></span>  
 <span data-ttu-id="4ab88-150">В следующем примере показано задание устаревшее поведение, которое не проходит через асинхронные точки удостоверение Windows.</span><span class="sxs-lookup"><span data-stu-id="4ab88-150">The following example shows how to specify the legacy behavior that does not flow the Windows identity across asynchronous points.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4ab88-151">См. также</span><span class="sxs-lookup"><span data-stu-id="4ab88-151">See also</span></span>

- [<span data-ttu-id="4ab88-152">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="4ab88-152">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="4ab88-153">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="4ab88-153">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="4ab88-154">\<alwaysFlowImpersonationPolicy > элемента</span><span class="sxs-lookup"><span data-stu-id="4ab88-154">\<alwaysFlowImpersonationPolicy> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)
