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
ms.openlocfilehash: 18a027bc09f2400a10a06efdc4c5355686bcb56d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116532"
---
# <a name="legacyimpersonationpolicy-element"></a><span data-ttu-id="44afd-102">\<Легациимперсонатионполици > элемент</span><span class="sxs-lookup"><span data-stu-id="44afd-102">\<legacyImpersonationPolicy> Element</span></span>
<span data-ttu-id="44afd-103">Указывает, что удостоверение Windows не проходит через асинхронные точки, независимо от параметров потока для контекста выполнения в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="44afd-103">Specifies that the Windows identity does not flow across asynchronous points, regardless of the flow settings for the execution context on the current thread.</span></span>  
  
<span data-ttu-id="44afd-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="44afd-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="44afd-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="44afd-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="44afd-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<легациимперсонатионполици >**</span><span class="sxs-lookup"><span data-stu-id="44afd-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyImpersonationPolicy>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44afd-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="44afd-107">Syntax</span></span>  
  
```xml  
<legacyImpersonationPolicy    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="44afd-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="44afd-108">Attributes and Elements</span></span>  
 <span data-ttu-id="44afd-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="44afd-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="44afd-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="44afd-110">Attributes</span></span>  
  
|<span data-ttu-id="44afd-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="44afd-111">Attribute</span></span>|<span data-ttu-id="44afd-112">Описание</span><span class="sxs-lookup"><span data-stu-id="44afd-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="44afd-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="44afd-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="44afd-114">Указывает, что <xref:System.Security.Principal.WindowsIdentity> не передается по асинхронным точкам, независимо от параметров потока <xref:System.Threading.ExecutionContext> в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="44afd-114">Specifies that the <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="44afd-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="44afd-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="44afd-116">значения</span><span class="sxs-lookup"><span data-stu-id="44afd-116">Value</span></span>|<span data-ttu-id="44afd-117">Описание</span><span class="sxs-lookup"><span data-stu-id="44afd-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="44afd-118"><xref:System.Security.Principal.WindowsIdentity> проходит через асинхронные точки в зависимости от параметров потока <xref:System.Threading.ExecutionContext> для текущего потока.</span><span class="sxs-lookup"><span data-stu-id="44afd-118"><xref:System.Security.Principal.WindowsIdentity> flows across asynchronous points depending upon the <xref:System.Threading.ExecutionContext> flow settings for the current thread.</span></span> <span data-ttu-id="44afd-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="44afd-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="44afd-120"><xref:System.Security.Principal.WindowsIdentity> не перетекает через асинхронные точки, независимо от параметров потока <xref:System.Threading.ExecutionContext> в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="44afd-120"><xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="44afd-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="44afd-121">Child Elements</span></span>  
 <span data-ttu-id="44afd-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="44afd-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="44afd-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="44afd-123">Parent Elements</span></span>  
  
|<span data-ttu-id="44afd-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="44afd-124">Element</span></span>|<span data-ttu-id="44afd-125">Описание</span><span class="sxs-lookup"><span data-stu-id="44afd-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="44afd-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="44afd-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="44afd-127">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="44afd-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="44afd-128">Заметки</span><span class="sxs-lookup"><span data-stu-id="44afd-128">Remarks</span></span>  
 <span data-ttu-id="44afd-129">В .NET Framework версиях 1,0 и 1,1 <xref:System.Security.Principal.WindowsIdentity> не проходит через определенные пользователем асинхронные точки.</span><span class="sxs-lookup"><span data-stu-id="44afd-129">In the .NET Framework versions 1.0 and 1.1, the <xref:System.Security.Principal.WindowsIdentity> does not flow across any user-defined asynchronous points.</span></span> <span data-ttu-id="44afd-130">Начиная с версии .NET Framework 2,0 существует объект <xref:System.Threading.ExecutionContext>, который содержит сведения о выполняемом в данный момент потоке и проходит через асинхронные точки в пределах домена приложения.</span><span class="sxs-lookup"><span data-stu-id="44afd-130">Starting with the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and it flows across asynchronous points within an application domain.</span></span> <span data-ttu-id="44afd-131"><xref:System.Security.Principal.WindowsIdentity> включается в этот контекст выполнения и, следовательно, проходит через асинхронные точки, что означает, что если контекст олицетворения существует, он также будет работать.</span><span class="sxs-lookup"><span data-stu-id="44afd-131">The <xref:System.Security.Principal.WindowsIdentity> is included in this execution context and therefore also flows across the asynchronous points, which means that if an impersonation context exists, it will flow as well.</span></span>  
  
 <span data-ttu-id="44afd-132">Начиная с .NET Framework 2,0 можно использовать элемент `<legacyImpersonationPolicy>`, чтобы указать, что <xref:System.Security.Principal.WindowsIdentity> не проходит через асинхронные точки.</span><span class="sxs-lookup"><span data-stu-id="44afd-132">Starting with the .NET Framework 2.0, you can use the `<legacyImpersonationPolicy>` element to specify that  <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="44afd-133">Общеязыковая среда выполнения (CLR) осведомлена об операциях олицетворения, выполняемых только с помощью управляемого кода, а не олицетворения, выполненных за пределами управляемого кода, например посредством вызова неуправляемого кода платформой или прямых вызовов функций Win32.</span><span class="sxs-lookup"><span data-stu-id="44afd-133">The common language runtime (CLR) is aware of impersonation operations performed using only managed code, not of impersonation performed outside of managed code, such as through platform invoke to unmanaged code or through direct calls to Win32 functions.</span></span> <span data-ttu-id="44afd-134">Только управляемые объекты <xref:System.Security.Principal.WindowsIdentity> могут передаваться по асинхронным точкам, если только элемент `alwaysFlowImpersonationPolicy` не имеет значение true (`<alwaysFlowImpersonationPolicy enabled="true"/>`).</span><span class="sxs-lookup"><span data-stu-id="44afd-134">Only managed <xref:System.Security.Principal.WindowsIdentity> objects can flow across asynchronous points, unless the `alwaysFlowImpersonationPolicy` element has been set to true (`<alwaysFlowImpersonationPolicy enabled="true"/>`).</span></span> <span data-ttu-id="44afd-135">Установка значения true для элемента `alwaysFlowImpersonationPolicy` указывает, что удостоверение Windows всегда проходит через асинхронные точки независимо от того, как было выполнено олицетворение.</span><span class="sxs-lookup"><span data-stu-id="44afd-135">Setting the `alwaysFlowImpersonationPolicy` element to true specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span> <span data-ttu-id="44afd-136">Дополнительные сведения о передаче неуправляемого олицетворения между асинхронными точками см. в разделе [\<алвайсфловимперсонатионполици > element](alwaysflowimpersonationpolicy-element.md).</span><span class="sxs-lookup"><span data-stu-id="44afd-136">For more information on flowing unmanaged impersonation across asynchronous points, see [\<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).</span></span>  
  
 <span data-ttu-id="44afd-137">Это поведение по умолчанию можно изменить двумя способами.</span><span class="sxs-lookup"><span data-stu-id="44afd-137">You can alter this default behavior in two other ways:</span></span>  
  
1. <span data-ttu-id="44afd-138">В управляемом коде на основе каждого потока.</span><span class="sxs-lookup"><span data-stu-id="44afd-138">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="44afd-139">Можно подавить поток на основе каждого потока, изменив параметры <xref:System.Threading.ExecutionContext> и <xref:System.Security.SecurityContext> с помощью метода <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> или <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="44afd-139">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="44afd-140">В вызове неуправляемого интерфейса размещения для загрузки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="44afd-140">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="44afd-141">Если для загрузки среды CLR используется неуправляемый интерфейс размещения (вместо простого управляемого исполняемого файла), можно указать специальный флаг в вызове функции [функции CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) .</span><span class="sxs-lookup"><span data-stu-id="44afd-141">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="44afd-142">Чтобы включить режим совместимости для всего процесса, задайте для параметра `flags` [функции CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) значение STARTUP_LEGACY_IMPERSONATION.</span><span class="sxs-lookup"><span data-stu-id="44afd-142">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) to STARTUP_LEGACY_IMPERSONATION.</span></span>  
  
 <span data-ttu-id="44afd-143">Дополнительные сведения см. в описании [элемента\<алвайсфловимперсонатионполици >](alwaysflowimpersonationpolicy-element.md).</span><span class="sxs-lookup"><span data-stu-id="44afd-143">For more information, see the [\<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="44afd-144">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="44afd-144">Configuration File</span></span>  
 <span data-ttu-id="44afd-145">В приложении .NET Framework этот элемент можно использовать только в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="44afd-145">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="44afd-146">Для приложения ASP.NET поток олицетворения можно настроить в файле aspnet. config, который находится в папке \<Windows > Каталог \Микрософт.нет\фрамеворк\вкс.КС.кскскскс.</span><span class="sxs-lookup"><span data-stu-id="44afd-146">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="44afd-147">ASP.NET по умолчанию отключает поток олицетворения в файле aspnet. config, используя следующие параметры конфигурации:</span><span class="sxs-lookup"><span data-stu-id="44afd-147">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
``` xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="44afd-148">В ASP.NET, если требуется разрешить поток олицетворения, необходимо явно использовать следующие параметры конфигурации:</span><span class="sxs-lookup"><span data-stu-id="44afd-148">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="44afd-149">Пример</span><span class="sxs-lookup"><span data-stu-id="44afd-149">Example</span></span>  
 <span data-ttu-id="44afd-150">В следующем примере показано, как задать устаревшее поведение, которое не пополняет удостоверение Windows в асинхронных точках.</span><span class="sxs-lookup"><span data-stu-id="44afd-150">The following example shows how to specify the legacy behavior that does not flow the Windows identity across asynchronous points.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="44afd-151">См. также</span><span class="sxs-lookup"><span data-stu-id="44afd-151">See also</span></span>

- [<span data-ttu-id="44afd-152">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="44afd-152">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="44afd-153">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="44afd-153">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="44afd-154">\<Алвайсфловимперсонатионполици > элемент</span><span class="sxs-lookup"><span data-stu-id="44afd-154">\<alwaysFlowImpersonationPolicy> Element</span></span>](alwaysflowimpersonationpolicy-element.md)
