---
title: Элемент <alwaysFlowImpersonationPolicy>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/alwaysFlowImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#alwaysFlowImpersonationPolicy
helpviewer_keywords:
- alwaysFlowImpersonationPolicy element
- <alwaysFlowImpersonationPolicy> element
ms.assetid: ee622801-9e46-470b-85ab-88c4b1dd2ee1
ms.openlocfilehash: 7c8ac37932a528ff0f000cbaab49124dec51b88c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154487"
---
# <a name="alwaysflowimpersonationpolicy-element"></a><span data-ttu-id="73771-102">\<всегдаFlowImpersonationПолитика> Элемент</span><span class="sxs-lookup"><span data-stu-id="73771-102">\<alwaysFlowImpersonationPolicy> Element</span></span>
<span data-ttu-id="73771-103">Указывает, что удостоверение Windows всегда проходит через асинхронные точки, независимо от того, как было выполнено олицетворение.</span><span class="sxs-lookup"><span data-stu-id="73771-103">Specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>  
  
<span data-ttu-id="73771-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="73771-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="73771-105">&nbsp;&nbsp;[**\<>выполнения**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="73771-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="73771-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<всегдаFlowImpersonationПолитика>**</span><span class="sxs-lookup"><span data-stu-id="73771-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<alwaysFlowImpersonationPolicy>**</span></span>\  
  
## <a name="syntax"></a><span data-ttu-id="73771-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="73771-107">Syntax</span></span>  
  
```xml  
<alwaysFlowImpersonationPolicy
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73771-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="73771-108">Attributes and Elements</span></span>  
 <span data-ttu-id="73771-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="73771-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73771-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="73771-110">Attributes</span></span>  
  
|<span data-ttu-id="73771-111">attribute</span><span class="sxs-lookup"><span data-stu-id="73771-111">Attribute</span></span>|<span data-ttu-id="73771-112">Описание</span><span class="sxs-lookup"><span data-stu-id="73771-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="73771-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="73771-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="73771-114">Указывает, течет ли идентификация Windows по асинхронным точкам.</span><span class="sxs-lookup"><span data-stu-id="73771-114">Indicates whether the Windows identity flows across asynchronous points.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="73771-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="73771-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="73771-116">Значение</span><span class="sxs-lookup"><span data-stu-id="73771-116">Value</span></span>|<span data-ttu-id="73771-117">Описание</span><span class="sxs-lookup"><span data-stu-id="73771-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="73771-118">Идентификация Windows не проходит через асинхронные точки, если олицетворение <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>не выполняется с помощью управляемых методов, таких как .</span><span class="sxs-lookup"><span data-stu-id="73771-118">The Windows identity does not flow across asynchronous points, unless the impersonation is performed through managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.</span></span> <span data-ttu-id="73771-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="73771-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="73771-120">Идентификация Windows всегда течет по асинхронным точкам, независимо от того, как выполнялось олицетворение.</span><span class="sxs-lookup"><span data-stu-id="73771-120">The Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="73771-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="73771-121">Child Elements</span></span>  
 <span data-ttu-id="73771-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="73771-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="73771-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="73771-123">Parent Elements</span></span>  
  
|<span data-ttu-id="73771-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="73771-124">Element</span></span>|<span data-ttu-id="73771-125">Описание</span><span class="sxs-lookup"><span data-stu-id="73771-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="73771-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="73771-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="73771-127">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="73771-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73771-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="73771-128">Remarks</span></span>  
 <span data-ttu-id="73771-129">В версиях .NET Framework 1.0 и 1.1 идентификация Windows не проходит через асинхронные точки.</span><span class="sxs-lookup"><span data-stu-id="73771-129">In the .NET Framework versions 1.0 and 1.1, the Windows identity does not flow across asynchronous points.</span></span> <span data-ttu-id="73771-130">В версии 2.0 .NET Framework <xref:System.Threading.ExecutionContext> есть объект, который содержит информацию о исполняемом потоке, который в настоящее время выполняет сяочие, и перетекает в асинхронные точки в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="73771-130">In the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and flows it across asynchronous points within an application domain.</span></span> <span data-ttu-id="73771-131">Также <xref:System.Security.Principal.WindowsIdentity> течет как часть информации, которая течет через асинхронные точки, при <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> условии, что олицетворение было достигнуто с помощью управляемых методов, таких как, а не с помощью других средств, таких как платформа ссылаться на родные методы.</span><span class="sxs-lookup"><span data-stu-id="73771-131">The <xref:System.Security.Principal.WindowsIdentity> also flows as part of the information that flows across the asynchronous points, provided the impersonation was achieved using managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> and not through other means such as platform invoke to native methods.</span></span> <span data-ttu-id="73771-132">Этот элемент используется для указания того, что инообразная личность Windows действительно проходит через асинхронные точки, независимо от того, как было достигнуто олицетворение.</span><span class="sxs-lookup"><span data-stu-id="73771-132">This element is used to specify that the Windows identity does flow across asynchronous points, regardless of how the impersonation was achieved.</span></span>  
  
 <span data-ttu-id="73771-133">Вы можете изменить это поведение по умолчанию двумя другими способами:</span><span class="sxs-lookup"><span data-stu-id="73771-133">You can alter this default behavior in two other ways:</span></span>  
  
1. <span data-ttu-id="73771-134">В управляемом коде на основе на поток.</span><span class="sxs-lookup"><span data-stu-id="73771-134">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="73771-135">Вы можете подавить поток на основе потока, <xref:System.Threading.ExecutionContext> <xref:System.Security.SecurityContext> изменяя и <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType> <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>настройки <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> с помощью, или метод.</span><span class="sxs-lookup"><span data-stu-id="73771-135">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="73771-136">При вызове к неуправляемому интерфейсу хостинга для загрузки общего языка времени выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="73771-136">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="73771-137">Если для загрузки CLR используется неуправляемый интерфейс хостинга (вместо простого управляемого исполнителя), можно указать специальный флаг в функции [CorBindToRuntimeEx.](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)</span><span class="sxs-lookup"><span data-stu-id="73771-137">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="73771-138">Чтобы включить режим совместимости для всего процесса, установите `flags` параметр для `STARTUP_ALWAYSFLOW_IMPERSONATION` [функции CorBindToRuntimeEx.](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)</span><span class="sxs-lookup"><span data-stu-id="73771-138">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) to `STARTUP_ALWAYSFLOW_IMPERSONATION`.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="73771-139">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="73771-139">Configuration File</span></span>  
 <span data-ttu-id="73771-140">В приложении .NET Framework этот элемент может быть использован только в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="73771-140">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="73771-141">Для ASP.NET приложения поток олицетворения может быть настроен в файле aspnet.config, найденном в каталоге \<Windows Folder>-Microsoft.NET-Framework-vx.x.xxxx.</span><span class="sxs-lookup"><span data-stu-id="73771-141">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="73771-142">ASP.NET по умолчанию отменяет поток олицетворения в файле aspnet.config с помощью следующих настроек конфигурации:</span><span class="sxs-lookup"><span data-stu-id="73771-142">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
```xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="73771-143">В ASP.NET, если вместо этого требуется разрешить поток олицетворения, необходимо явно использовать следующие настройки конфигурации:</span><span class="sxs-lookup"><span data-stu-id="73771-143">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="73771-144">Пример</span><span class="sxs-lookup"><span data-stu-id="73771-144">Example</span></span>  
 <span data-ttu-id="73771-145">В следующем примере показано, как указать, что идентификация Windows течет по асинхронным точкам, даже если олицетворение достигается с помощью других средств, помимо управляемых методов.</span><span class="sxs-lookup"><span data-stu-id="73771-145">The following example shows how to specify that the Windows identity flows across asynchronous points, even when the impersonation is achieved through means other than managed methods.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="73771-146">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="73771-146">See also</span></span>

- [<span data-ttu-id="73771-147">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="73771-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="73771-148">Схема конфигурации файлов</span><span class="sxs-lookup"><span data-stu-id="73771-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="73771-149">\<legacyImpersonationПолитика> Элемент</span><span class="sxs-lookup"><span data-stu-id="73771-149">\<legacyImpersonationPolicy> Element</span></span>](legacyimpersonationpolicy-element.md)
