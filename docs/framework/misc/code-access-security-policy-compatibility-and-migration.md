---
title: Совместимость политики разграничения доступа кода и ее миграция
ms.date: 03/30/2017
helpviewer_keywords:
- policy migration, compatibility
- CLR policy migration
ms.assetid: 19cb4d39-e38a-4262-b507-458915303115
ms.openlocfilehash: 949739b3336a9182eef583cc405e60e09d7ec09d
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217150"
---
# <a name="code-access-security-policy-compatibility-and-migration"></a><span data-ttu-id="573ee-102">Совместимость политики разграничения доступа кода и ее миграция</span><span class="sxs-lookup"><span data-stu-id="573ee-102">Code Access Security Policy Compatibility and Migration</span></span>

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

<span data-ttu-id="573ee-103">Часть политики разграничения доступа кода (CAS) стала устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="573ee-103">The policy portion of code access security (CAS) has been made obsolete in the .NET Framework 4.</span></span> <span data-ttu-id="573ee-104">В результате вы можете столкнуться с предупреждениями компиляции и исключениями среды выполнения, если вы вызываете устаревшие типы и члены [явно](#explicit_use) или [неявно](#implicit_use) (через другие типы и члены).</span><span class="sxs-lookup"><span data-stu-id="573ee-104">As a result, you may encounter compilation warnings and runtime exceptions if you call the obsolete policy types and members [explicitly](#explicit_use) or [implicitly](#implicit_use) (through other types and members).</span></span>

<span data-ttu-id="573ee-105">Избежать появления таких предупреждений и ошибок можно следующими способами:</span><span class="sxs-lookup"><span data-stu-id="573ee-105">You can avoid the warnings and errors by either:</span></span>

- <span data-ttu-id="573ee-106">[Переход](#migration) на .NET Framework 4 замен для устаревших вызовов.</span><span class="sxs-lookup"><span data-stu-id="573ee-106">[Migrating](#migration) to the .NET Framework 4 replacements for the obsolete calls.</span></span>

   <span data-ttu-id="573ee-107">\- или -</span><span class="sxs-lookup"><span data-stu-id="573ee-107">\- or -</span></span>

- <span data-ttu-id="573ee-108">Использование [элемента конфигурации\<NetFx40_LegacySecurityPolicy >](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) для выбора устаревшей политики РАЗГРАНИЧЕНИЯ доступа кода.</span><span class="sxs-lookup"><span data-stu-id="573ee-108">Using the [\<NetFx40_LegacySecurityPolicy> configuration element](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) to opt into the legacy CAS policy behavior.</span></span>

<span data-ttu-id="573ee-109">В этом разделе содержатся следующие подразделы:</span><span class="sxs-lookup"><span data-stu-id="573ee-109">This topic contains the following sections:</span></span>

- [<span data-ttu-id="573ee-110">Явное использование</span><span class="sxs-lookup"><span data-stu-id="573ee-110">Explicit Use</span></span>](#explicit_use)

- [<span data-ttu-id="573ee-111">Неявное использование</span><span class="sxs-lookup"><span data-stu-id="573ee-111">Implicit Use</span></span>](#implicit_use)

- [<span data-ttu-id="573ee-112">Ошибки и предупреждения</span><span class="sxs-lookup"><span data-stu-id="573ee-112">Errors and Warnings</span></span>](#errors_and_warnings)

- [<span data-ttu-id="573ee-113">Миграция: замена устаревших вызовов</span><span class="sxs-lookup"><span data-stu-id="573ee-113">Migration: Replacement for Obsolete Calls</span></span>](#migration)

- [<span data-ttu-id="573ee-114">Совместимость. использование устаревшей политики CAS</span><span class="sxs-lookup"><span data-stu-id="573ee-114">Compatibility: Using the CAS Policy Legacy Option</span></span>](#compatibility)

<a name="explicit_use"></a>

## <a name="explicit-use"></a><span data-ttu-id="573ee-115">Явное использование</span><span class="sxs-lookup"><span data-stu-id="573ee-115">Explicit Use</span></span>

<span data-ttu-id="573ee-116">Члены, которые непосредственно управляют политикой безопасности или требуют политики разграничения доступа кода для изоляции в "песочнице", являются устаревшими и по умолчанию вызывают ошибки.</span><span class="sxs-lookup"><span data-stu-id="573ee-116">Members that directly manipulate security policy or require CAS policy to sandbox are obsolete and will produce errors by default.</span></span>

<span data-ttu-id="573ee-117">Примеры:</span><span class="sxs-lookup"><span data-stu-id="573ee-117">Examples of these are:</span></span>

- <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType>

- <xref:System.Security.HostSecurityManager.DomainPolicy%2A?displayProperty=nameWithType>

- <xref:System.Security.Policy.PolicyLevel.CreateAppDomainLevel%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.LoadPolicyLevelFromString%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.LoadPolicyLevelFromFile%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.ResolveSystemPolicy%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.ResolvePolicyGroups%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.PolicyHierarchy%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.SavePolicy%2A?displayProperty=nameWithType>

<a name="implicit_use"></a>

## <a name="implicit-use"></a><span data-ttu-id="573ee-118">Неявное использование</span><span class="sxs-lookup"><span data-stu-id="573ee-118">Implicit Use</span></span>

<span data-ttu-id="573ee-119">Несколько перегруженных методов загрузки сборки вызывают ошибки из-за неявного использования политики разграничения доступа кода.</span><span class="sxs-lookup"><span data-stu-id="573ee-119">Several assembly loading overloads produce errors because of their implicit use of CAS policy.</span></span> <span data-ttu-id="573ee-120">Эти перегруженные методы принимают параметр <xref:System.Security.Policy.Evidence>, разрешающий политику разграничения доступа кода, и предоставляют сборке набор разрешений.</span><span class="sxs-lookup"><span data-stu-id="573ee-120">These overloads take an <xref:System.Security.Policy.Evidence> parameter that is used to resolve CAS policy and provide a permission grant set for an assembly.</span></span>

<span data-ttu-id="573ee-121">Ниже приведены некоторые примеры.</span><span class="sxs-lookup"><span data-stu-id="573ee-121">Here are some examples.</span></span> <span data-ttu-id="573ee-122">Устаревшие перегрузки — это перегрузки, принимающие в качестве параметра <xref:System.Security.Policy.Evidence>.</span><span class="sxs-lookup"><span data-stu-id="573ee-122">The obsolete overloads are those that take <xref:System.Security.Policy.Evidence> as a parameter:</span></span>

- <xref:System.Activator.CreateInstanceFrom%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.CreateInstanceFrom%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.CreateInstanceAndUnwrap%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.DefineDynamicAssembly%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.ExecuteAssemblyByName%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.Load%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>

<a name="errors_and_warnings"></a>

## <a name="errors-and-warnings"></a><span data-ttu-id="573ee-123">Ошибки и предупреждения</span><span class="sxs-lookup"><span data-stu-id="573ee-123">Errors and Warnings</span></span>

<span data-ttu-id="573ee-124">При использовании устаревших типов и членов возникают указанные ниже сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="573ee-124">The obsolete types and members produce the following error messages when they are used.</span></span> <span data-ttu-id="573ee-125">Обратите внимание, что сам тип <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> не является устаревшим.</span><span class="sxs-lookup"><span data-stu-id="573ee-125">Note that the <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> type itself is not obsolete.</span></span>

<span data-ttu-id="573ee-126">Предупреждение времени компиляции:</span><span class="sxs-lookup"><span data-stu-id="573ee-126">Compile-time warning:</span></span>

`warning CS0618: '<API Name>' is obsolete: 'This method is obsolete and will be removed in a future release of the .NET Framework. Please use <suggested alternate API>. See <link> for more information.'`

<span data-ttu-id="573ee-127">Исключение времени выполнения:</span><span class="sxs-lookup"><span data-stu-id="573ee-127">Run-time exception:</span></span>

<span data-ttu-id="573ee-128"><xref:System.NotSupportedException>: `This method uses CAS policy, which has been obsoleted by the .NET Framework. In order to enable CAS policy for compatibility reasons, please use the <NetFx40_LegacySecurityPolicy> configuration switch. Please see <link> for more information.`</span><span class="sxs-lookup"><span data-stu-id="573ee-128"><xref:System.NotSupportedException>: `This method uses CAS policy, which has been obsoleted by the .NET Framework. In order to enable CAS policy for compatibility reasons, please use the <NetFx40_LegacySecurityPolicy> configuration switch. Please see <link> for more information.`</span></span>

<a name="migration"></a>

## <a name="migration-replacement-for-obsolete-calls"></a><span data-ttu-id="573ee-129">Миграция: замена устаревших вызовов</span><span class="sxs-lookup"><span data-stu-id="573ee-129">Migration: Replacement for Obsolete Calls</span></span>

### <a name="determining-an-assemblys-trust-level"></a><span data-ttu-id="573ee-130">Определение уровня доверия сборки</span><span class="sxs-lookup"><span data-stu-id="573ee-130">Determining an Assembly’s Trust Level</span></span>

<span data-ttu-id="573ee-131">Политика разграничения доступа кода часто используется для определения набора разрешений или уровня доверия, предоставляемых сборке или домену приложения.</span><span class="sxs-lookup"><span data-stu-id="573ee-131">CAS policy is often used to determine an assembly’s or application domain’s permission grant set or trust level.</span></span> <span data-ttu-id="573ee-132">.NET Framework 4 предоставляет следующие полезные свойства, не требующие разрешения политики безопасности.</span><span class="sxs-lookup"><span data-stu-id="573ee-132">The .NET Framework 4 exposes the following useful properties that do not need to resolve security policy:</span></span>

- <xref:System.Reflection.Assembly.PermissionSet%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.IsFullyTrusted%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.PermissionSet%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.IsFullyTrusted%2A?displayProperty=nameWithType>

### <a name="application-domain-sandboxing"></a><span data-ttu-id="573ee-133">Изолирование домена приложения</span><span class="sxs-lookup"><span data-stu-id="573ee-133">Application Domain Sandboxing</span></span>

<span data-ttu-id="573ee-134">Метод <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType>, как правило, используется для изолирования сборок в домене приложений.</span><span class="sxs-lookup"><span data-stu-id="573ee-134">The <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType> method is typically used for sandboxing the assemblies in an application domain.</span></span> <span data-ttu-id="573ee-135">.NET Framework 4 предоставляет члены, которые не используют <xref:System.Security.Policy.PolicyLevel> для этой цели.</span><span class="sxs-lookup"><span data-stu-id="573ee-135">The .NET Framework 4 exposes members that do not have to use <xref:System.Security.Policy.PolicyLevel> for this purpose.</span></span> <span data-ttu-id="573ee-136">Дополнительные сведения см. [в разделе инструкции. Запуск частично доверенного кода в песочнице](how-to-run-partially-trusted-code-in-a-sandbox.md).</span><span class="sxs-lookup"><span data-stu-id="573ee-136">For more information, see [How to: Run Partially Trusted Code in a Sandbox](how-to-run-partially-trusted-code-in-a-sandbox.md).</span></span>

### <a name="determining-a-safe-or-reasonable-permission-set-for-partially-trusted-code"></a><span data-ttu-id="573ee-137">Определение безопасного или приемлемого набора разрешений для частично доверенного кода</span><span class="sxs-lookup"><span data-stu-id="573ee-137">Determining a Safe or Reasonable Permission Set for Partially Trusted Code</span></span>

<span data-ttu-id="573ee-138">Основным приложениям часто требуется определить разрешения, подходящие для изоляции кода, запускаемого из этих приложений.</span><span class="sxs-lookup"><span data-stu-id="573ee-138">Hosts often need to determine the permissions that are appropriate for sandboxing hosted code.</span></span> <span data-ttu-id="573ee-139">Прежде чем приступить к работе с .NET Framework 4, политика CAS предоставила способ сделать это с помощью метода <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="573ee-139">Before the .NET Framework 4, CAS policy provided a way to do this with the <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="573ee-140">В качестве замены .NET Framework 4 предоставляет метод <xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=nameWithType>, который возвращает надежный стандартный набор разрешений для предоставленного свидетельства.</span><span class="sxs-lookup"><span data-stu-id="573ee-140">As a replacement, .NET Framework 4 provides the <xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=nameWithType> method, which returns a safe, standard permission set for the provided evidence.</span></span>

### <a name="non-sandboxing-scenarios-overloads-for-assembly-loads"></a><span data-ttu-id="573ee-141">Сценарии без использования "песочницы": перегруженные методы для загрузки сборок</span><span class="sxs-lookup"><span data-stu-id="573ee-141">Non-Sandboxing Scenarios: Overloads for Assembly Loads</span></span>

<span data-ttu-id="573ee-142">Перегруженные методы загрузки сборок применяются, если вместо изоляции сборки в "песочнице" необходимо использовать параметры, которые недоступны иначе.</span><span class="sxs-lookup"><span data-stu-id="573ee-142">The reason for using an assembly load overload might be to use parameters that are not otherwise available, instead of sandboxing the assembly.</span></span> <span data-ttu-id="573ee-143">Начиная с .NET Framework 4, перегрузки загрузки сборок, не требующие <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> объекта в качестве параметра, например <xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.String%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Configuration.Assemblies.AssemblyHashAlgorithm%29?displayProperty=nameWithType>, следует включить этот сценарий.</span><span class="sxs-lookup"><span data-stu-id="573ee-143">Starting with the .NET Framework 4, assembly load overloads that do not require a <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> object as a parameter, for example, <xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.String%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Configuration.Assemblies.AssemblyHashAlgorithm%29?displayProperty=nameWithType>, enable this scenario.</span></span>

<span data-ttu-id="573ee-144">Чтобы поместить сборку в изолированную среду, воспользуйтесь перегрузкой <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="573ee-144">If you want to sandbox an assembly, use the <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType> overload.</span></span>

<a name="compatibility"></a>

## <a name="compatibility-using-the-cas-policy-legacy-option"></a><span data-ttu-id="573ee-145">Совместимость: использование политики разграничения доступа кода прежних версий</span><span class="sxs-lookup"><span data-stu-id="573ee-145">Compatibility: Using the CAS Policy Legacy Option</span></span>

<span data-ttu-id="573ee-146">[Элемент конфигурации\<NetFx40_LegacySecurityPolicy >](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) позволяет указать, что процесс или библиотека использует устаревшую политику РАЗГРАНИЧЕНИЯ доступа кода.</span><span class="sxs-lookup"><span data-stu-id="573ee-146">The [\<NetFx40_LegacySecurityPolicy> configuration element](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) lets you specify that a process or library uses legacy CAS policy.</span></span> <span data-ttu-id="573ee-147">При включении этого элемента политика и перегруженные объекты свидетельств будут работать как в предыдущих версиях платформы.</span><span class="sxs-lookup"><span data-stu-id="573ee-147">When you enable this element, the policy and evidence overloads will work as they did in previous versions of the framework.</span></span>

> [!NOTE]
> <span data-ttu-id="573ee-148">Поведение политики разграничения доступа кода определяется для каждой версии среды выполнения, поэтому изменение этой политики для одной версии среды выполнения не повлияет на ее поведение в других версиях.</span><span class="sxs-lookup"><span data-stu-id="573ee-148">CAS policy behavior is specified on a runtime version basis, so modifying CAS policy for one runtime version does not affect the CAS policy of another version.</span></span>

```xml
<configuration>
   <runtime>
      <NetFx40_LegacySecurityPolicy enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="573ee-149">См. также:</span><span class="sxs-lookup"><span data-stu-id="573ee-149">See also</span></span>

- [<span data-ttu-id="573ee-150">Практическое руководство. Выполнение не вполне безопасного кода в изолированной среде</span><span class="sxs-lookup"><span data-stu-id="573ee-150">How to: Run Partially Trusted Code in a Sandbox</span></span>](how-to-run-partially-trusted-code-in-a-sandbox.md)
- [<span data-ttu-id="573ee-151">Правила написания безопасного кода</span><span class="sxs-lookup"><span data-stu-id="573ee-151">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
