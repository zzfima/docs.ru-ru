---
title: "Совместимость политики разграничения доступа кода и ее миграция"
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
helpviewer_keywords:
- policy migration, compatibility
- CLR poliicy migration
ms.assetid: 19cb4d39-e38a-4262-b507-458915303115
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9feb4553b1b9e013c5c299d867d74499a09e1434
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="code-access-security-policy-compatibility-and-migration"></a><span data-ttu-id="b479b-102">Совместимость политики разграничения доступа кода и ее миграция</span><span class="sxs-lookup"><span data-stu-id="b479b-102">Code Access Security Policy Compatibility and Migration</span></span>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="b479b-103">Политика разграничения доступа кода (CAS) является устаревшей в [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b479b-103">The policy portion of code access security (CAS) has been made obsolete in the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="b479b-104">В результате могут возникать предупреждения компиляции и исключения среды CLR при вызове устаревших типов политик и членов [явно](#explicit_use) или [неявно](#implicit_use) (через другие типы и члены).</span><span class="sxs-lookup"><span data-stu-id="b479b-104">As a result, you may encounter compilation warnings and runtime exceptions if you call the obsolete policy types and members [explicitly](#explicit_use) or [implicitly](#implicit_use) (through other types and members).</span></span>  
  
 <span data-ttu-id="b479b-105">Избежать появления таких предупреждений и ошибок можно следующими способами:</span><span class="sxs-lookup"><span data-stu-id="b479b-105">You can avoid the warnings and errors by either:</span></span>  
  
-   <span data-ttu-id="b479b-106">[Миграция](#migration) для [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] заменяющих устаревшие вызовы.</span><span class="sxs-lookup"><span data-stu-id="b479b-106">[Migrating](#migration) to the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] replacements for the obsolete calls.</span></span>  
  
     <span data-ttu-id="b479b-107">\- или -</span><span class="sxs-lookup"><span data-stu-id="b479b-107">\- or -</span></span>  
  
-   <span data-ttu-id="b479b-108">С помощью [элемента конфигурации < NetFx40_LegacySecurityPolicy >](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) для выбора политики разграничения доступа кода прежних версий.</span><span class="sxs-lookup"><span data-stu-id="b479b-108">Using the [<NetFx40_LegacySecurityPolicy> configuration element](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) to opt into the legacy CAS policy behavior.</span></span>  
  
 <span data-ttu-id="b479b-109">В этом разделе содержатся следующие подразделы.</span><span class="sxs-lookup"><span data-stu-id="b479b-109">This topic contains the following sections:</span></span>  
  
-   [<span data-ttu-id="b479b-110">Явное использование</span><span class="sxs-lookup"><span data-stu-id="b479b-110">Explicit Use</span></span>](#explicit_use)  
  
-   [<span data-ttu-id="b479b-111">Неявное использование</span><span class="sxs-lookup"><span data-stu-id="b479b-111">Implicit Use</span></span>](#implicit_use)  
  
-   [<span data-ttu-id="b479b-112">Ошибки и предупреждения</span><span class="sxs-lookup"><span data-stu-id="b479b-112">Errors and Warnings</span></span>](#errors_and_warnings)  
  
-   [<span data-ttu-id="b479b-113">Миграция: Замена устаревших вызовов</span><span class="sxs-lookup"><span data-stu-id="b479b-113">Migration: Replacement for Obsolete Calls</span></span>](#migration)  
  
-   [<span data-ttu-id="b479b-114">Совместимость: Использование политики разграничения доступа кода прежних версий</span><span class="sxs-lookup"><span data-stu-id="b479b-114">Compatibility: Using the CAS Policy Legacy Option</span></span>](#compatibility)  
  
<a name="explicit_use"></a>   
## <a name="explicit-use"></a><span data-ttu-id="b479b-115">Явное использование</span><span class="sxs-lookup"><span data-stu-id="b479b-115">Explicit Use</span></span>  
 <span data-ttu-id="b479b-116">Члены, которые непосредственно управляют политикой безопасности или требуют политики разграничения доступа кода для изоляции в "песочнице", являются устаревшими и по умолчанию вызывают ошибки.</span><span class="sxs-lookup"><span data-stu-id="b479b-116">Members that directly manipulate security policy or require CAS policy to sandbox are obsolete and will produce errors by default.</span></span>  
  
 <span data-ttu-id="b479b-117">Ниже приводятся некоторые примеры.</span><span class="sxs-lookup"><span data-stu-id="b479b-117">Examples of these are:</span></span>  
  
-   <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.HostSecurityManager.DomainPolicy%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.Policy.PolicyLevel.CreateAppDomainLevel%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.LoadPolicyLevelFromString%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.LoadPolicyLevelFromFile%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.ResolveSystemPolicy%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.ResolvePolicyGroups%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.PolicyHierarchy%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.SavePolicy%2A?displayProperty=nameWithType>  
  
<a name="implicit_use"></a>   
## <a name="implicit-use"></a><span data-ttu-id="b479b-118">Неявное использование</span><span class="sxs-lookup"><span data-stu-id="b479b-118">Implicit Use</span></span>  
 <span data-ttu-id="b479b-119">Несколько перегруженных методов загрузки сборки вызывают ошибки из-за неявного использования политики разграничения доступа кода.</span><span class="sxs-lookup"><span data-stu-id="b479b-119">Several assembly loading overloads produce errors because of their implicit use of CAS policy.</span></span> <span data-ttu-id="b479b-120">Эти перегруженные методы принимают параметр <xref:System.Security.Policy.Evidence>, разрешающий политику разграничения доступа кода, и предоставляют сборке набор разрешений.</span><span class="sxs-lookup"><span data-stu-id="b479b-120">These overloads take an <xref:System.Security.Policy.Evidence> parameter that is used to resolve CAS policy and provide a permission grant set for an assembly.</span></span>  
  
 <span data-ttu-id="b479b-121">Ниже приводятся некоторые примеры.</span><span class="sxs-lookup"><span data-stu-id="b479b-121">Here are some examples.</span></span> <span data-ttu-id="b479b-122">Устаревшие перегрузки — это перегрузки, принимающие в качестве параметра <xref:System.Security.Policy.Evidence>.</span><span class="sxs-lookup"><span data-stu-id="b479b-122">The obsolete overloads are those that take <xref:System.Security.Policy.Evidence> as a parameter:</span></span>  
  
-   <xref:System.Activator.CreateInstanceFrom%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.CreateInstanceFrom%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.CreateInstanceAndUnwrap%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.DefineDynamicAssembly%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.ExecuteAssemblyByName%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.Load%2A?displayProperty=nameWithType>  
  
-   <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>  
  
-   <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>  
  
-   <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>  
  
<a name="errors_and_warnings"></a>   
## <a name="errors-and-warnings"></a><span data-ttu-id="b479b-123">Ошибки и предупреждения</span><span class="sxs-lookup"><span data-stu-id="b479b-123">Errors and Warnings</span></span>  
 <span data-ttu-id="b479b-124">При использовании устаревших типов и членов возникают указанные ниже сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="b479b-124">The obsolete types and members produce the following error messages when they are used.</span></span> <span data-ttu-id="b479b-125">Обратите внимание, что сам тип <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> не является устаревшим.</span><span class="sxs-lookup"><span data-stu-id="b479b-125">Note that the <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> type itself is not obsolete.</span></span>  
  
 <span data-ttu-id="b479b-126">Предупреждение времени компиляции:</span><span class="sxs-lookup"><span data-stu-id="b479b-126">Compile-time warning:</span></span>  
  
 `warning CS0618: '<API Name>' is obsolete: 'This method is obsolete and will be removed in a future release of the .NET Framework. Please use <suggested alternate API>. See <link> for more information.'`  
  
 <span data-ttu-id="b479b-127">Исключение времени выполнения:</span><span class="sxs-lookup"><span data-stu-id="b479b-127">Run-time exception:</span></span>  
  
 <span data-ttu-id="b479b-128"><xref:System.NotSupportedException>: `This method uses CAS policy, which has been obsoleted by the .NET Framework. In order to enable CAS policy for compatibility reasons, please use the <NetFx40_LegacySecurityPolicy> configuration switch. Please see <link> for more information.`</span><span class="sxs-lookup"><span data-stu-id="b479b-128"><xref:System.NotSupportedException>: `This method uses CAS policy, which has been obsoleted by the .NET Framework. In order to enable CAS policy for compatibility reasons, please use the <NetFx40_LegacySecurityPolicy> configuration switch. Please see <link> for more information.`</span></span>  
  
<a name="migration"></a>   
## <a name="migration-replacement-for-obsolete-calls"></a><span data-ttu-id="b479b-129">Миграция: замена устаревших вызовов</span><span class="sxs-lookup"><span data-stu-id="b479b-129">Migration: Replacement for Obsolete Calls</span></span>  
  
### <a name="determining-an-assemblys-trust-level"></a><span data-ttu-id="b479b-130">Определение уровня доверия сборки</span><span class="sxs-lookup"><span data-stu-id="b479b-130">Determining an Assembly’s Trust Level</span></span>  
 <span data-ttu-id="b479b-131">Политика разграничения доступа кода часто используется для определения набора разрешений или уровня доверия, предоставляемых сборке или домену приложения.</span><span class="sxs-lookup"><span data-stu-id="b479b-131">CAS policy is often used to determine an assembly’s or application domain’s permission grant set or trust level.</span></span> <span data-ttu-id="b479b-132">Платформа [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] предоставляет следующие полезные свойства, не требующие разрешения политики безопасности:</span><span class="sxs-lookup"><span data-stu-id="b479b-132">The [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] exposes the following useful properties that do not need to resolve security policy:</span></span>  
  
-   <xref:System.Reflection.Assembly.PermissionSet%2A?displayProperty=nameWithType>  
  
-   <xref:System.Reflection.Assembly.IsFullyTrusted%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.PermissionSet%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.IsFullyTrusted%2A?displayProperty=nameWithType>  
  
### <a name="application-domain-sandboxing"></a><span data-ttu-id="b479b-133">Изолирование домена приложения</span><span class="sxs-lookup"><span data-stu-id="b479b-133">Application Domain Sandboxing</span></span>  
 <span data-ttu-id="b479b-134">Метод <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType>, как правило, используется для изолирования сборок в домене приложений.</span><span class="sxs-lookup"><span data-stu-id="b479b-134">The <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType> method is typically used for sandboxing the assemblies in an application domain.</span></span> <span data-ttu-id="b479b-135">[!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] Предоставляет члены, которые не должны использовать <xref:System.Security.Policy.PolicyLevel> для этой цели.</span><span class="sxs-lookup"><span data-stu-id="b479b-135">The [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] exposes members that do not have to use <xref:System.Security.Policy.PolicyLevel> for this purpose.</span></span> <span data-ttu-id="b479b-136">Дополнительные сведения см. в разделе [как: выполнение частично доверенного кода в изолированной среде](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md).</span><span class="sxs-lookup"><span data-stu-id="b479b-136">For more information, see [How to: Run Partially Trusted Code in a Sandbox](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md).</span></span>  
  
### <a name="determining-a-safe-or-reasonable-permission-set-for-partially-trusted-code"></a><span data-ttu-id="b479b-137">Определение безопасного или приемлемого набора разрешений для частично доверенного кода</span><span class="sxs-lookup"><span data-stu-id="b479b-137">Determining a Safe or Reasonable Permission Set for Partially Trusted Code</span></span>  
 <span data-ttu-id="b479b-138">Ведущим приложениям часто требуется определить разрешения, подходящие для изоляции кода, запускаемого из этих приложений.</span><span class="sxs-lookup"><span data-stu-id="b479b-138">Hosts often need to determine the permissions that are appropriate for sandboxing hosted code.</span></span> <span data-ttu-id="b479b-139">Прежде чем [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], политика разграничения доступа кода позволяет это сделать с помощью <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="b479b-139">Before the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], CAS policy provided a way to do this with the <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="b479b-140">Вместо этого [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] предоставляет <xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=nameWithType> метод, который возвращает безопасный стандартный набор разрешений для предоставленного свидетельства.</span><span class="sxs-lookup"><span data-stu-id="b479b-140">As a replacement, [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] provides the <xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=nameWithType> method, which returns a safe, standard permission set for the provided evidence.</span></span>  
  
### <a name="non-sandboxing-scenarios-overloads-for-assembly-loads"></a><span data-ttu-id="b479b-141">Сценарии без использования "песочницы": перегруженные методы для загрузки сборок</span><span class="sxs-lookup"><span data-stu-id="b479b-141">Non-Sandboxing Scenarios: Overloads for Assembly Loads</span></span>  
 <span data-ttu-id="b479b-142">Перегруженные методы загрузки сборок применяются, если вместо изоляции сборки в "песочнице" необходимо использовать параметры, которые недоступны иначе.</span><span class="sxs-lookup"><span data-stu-id="b479b-142">The reason for using an assembly load overload might be to use parameters that are not otherwise available, instead of sandboxing the assembly.</span></span> <span data-ttu-id="b479b-143">Начиная с [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], перегруженные методы загрузки сборки, не требующие <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> объект в качестве параметра, например, <xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.String%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Configuration.Assemblies.AssemblyHashAlgorithm%29?displayProperty=nameWithType>, реализовать этот сценарий.</span><span class="sxs-lookup"><span data-stu-id="b479b-143">Starting with the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], assembly load overloads that do not require a <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> object as a parameter, for example, <xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.String%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Configuration.Assemblies.AssemblyHashAlgorithm%29?displayProperty=nameWithType>, enable this scenario.</span></span>  
  
 <span data-ttu-id="b479b-144">Чтобы поместить сборку в изолированную среду, воспользуйтесь перегрузкой <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b479b-144">If you want to sandbox an assembly, use the <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType> overload.</span></span>  
  
<a name="compatibility"></a>   
## <a name="compatibility-using-the-cas-policy-legacy-option"></a><span data-ttu-id="b479b-145">Совместимость: использование политики разграничения доступа кода прежних версий</span><span class="sxs-lookup"><span data-stu-id="b479b-145">Compatibility: Using the CAS Policy Legacy Option</span></span>  
 <span data-ttu-id="b479b-146">[Элемента конфигурации < NetFx40_LegacySecurityPolicy >](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) позволяет указать, что процесс или библиотека использует политику разграничения доступа кода прежних версий.</span><span class="sxs-lookup"><span data-stu-id="b479b-146">The [<NetFx40_LegacySecurityPolicy> configuration element](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) lets you specify that a process or library uses legacy CAS policy.</span></span> <span data-ttu-id="b479b-147">При включении этого элемента политика и перегруженные объекты свидетельств будут работать как в предыдущих версиях платформы.</span><span class="sxs-lookup"><span data-stu-id="b479b-147">When you enable this element, the policy and evidence overloads will work as they did in previous versions of the framework.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b479b-148">Поведение политики разграничения доступа кода определяется для каждой версии среды выполнения, поэтому изменение этой политики для одной версии среды выполнения не повлияет на ее поведение в других версиях.</span><span class="sxs-lookup"><span data-stu-id="b479b-148">CAS policy behavior is specified on a runtime version basis, so modifying CAS policy for one runtime version does not affect the CAS policy of another version.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_LegacySecurityPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b479b-149">См. также</span><span class="sxs-lookup"><span data-stu-id="b479b-149">See Also</span></span>  
 [<span data-ttu-id="b479b-150">Практическое руководство. Выполнение не вполне безопасного кода в изолированной среде</span><span class="sxs-lookup"><span data-stu-id="b479b-150">How to: Run Partially Trusted Code in a Sandbox</span></span>](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)  
 [<span data-ttu-id="b479b-151">Правила написания безопасного кода</span><span class="sxs-lookup"><span data-stu-id="b479b-151">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
