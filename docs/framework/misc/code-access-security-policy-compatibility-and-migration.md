---
title: Совместимость политики разграничения доступа кода и ее миграция
ms.date: 03/30/2017
helpviewer_keywords:
- policy migration, compatibility
- CLR policy migration
ms.assetid: 19cb4d39-e38a-4262-b507-458915303115
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9563dae9ba5d144300549e7f33f5f5a9feb1d410
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205632"
---
# <a name="code-access-security-policy-compatibility-and-migration"></a>Совместимость политики разграничения доступа кода и ее миграция

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

Часть политики разграничения доступа кода (CAS) стала устаревшей в .NET Framework 4. В результате вы можете столкнуться с предупреждениями компиляции и исключениями среды выполнения, если вы вызываете устаревшие типы и члены [явно](#explicit_use) или [неявно](#implicit_use) (через другие типы и члены).

Избежать появления таких предупреждений и ошибок можно следующими способами:

- [Переход](#migration) на .NET Framework 4 замен для устаревших вызовов.

   \- или -

- Использование [элемента конфигурации NetFx40_LegacySecurityPolicy>длявыбораустаревшейполитикиразграничениядоступакода.\<](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md)

В этом разделе содержатся следующие подразделы.

- [Явное использование](#explicit_use)

- [Неявное использование](#implicit_use)

- [Ошибки и предупреждения](#errors_and_warnings)

- [Преобразования Замена устаревших вызовов](#migration)

- [См Использование устаревшей политики CAS](#compatibility)

<a name="explicit_use"></a>

## <a name="explicit-use"></a>Явное использование

Члены, которые непосредственно управляют политикой безопасности или требуют политики разграничения доступа кода для изоляции в "песочнице", являются устаревшими и по умолчанию вызывают ошибки.

Ниже приводятся некоторые примеры.

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

## <a name="implicit-use"></a>Неявное использование

Несколько перегруженных методов загрузки сборки вызывают ошибки из-за неявного использования политики разграничения доступа кода. Эти перегруженные методы принимают параметр <xref:System.Security.Policy.Evidence>, разрешающий политику разграничения доступа кода, и предоставляют сборке набор разрешений.

Ниже приведены некоторые примеры. Устаревшие перегрузки — это перегрузки, принимающие в качестве параметра <xref:System.Security.Policy.Evidence>.

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

## <a name="errors-and-warnings"></a>Ошибки и предупреждения

При использовании устаревших типов и членов возникают указанные ниже сообщения об ошибках. Обратите внимание, что сам тип <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> не является устаревшим.

Предупреждение времени компиляции:

`warning CS0618: '<API Name>' is obsolete: 'This method is obsolete and will be removed in a future release of the .NET Framework. Please use <suggested alternate API>. See <link> for more information.'`

Исключение времени выполнения:

<xref:System.NotSupportedException>: `This method uses CAS policy, which has been obsoleted by the .NET Framework. In order to enable CAS policy for compatibility reasons, please use the <NetFx40_LegacySecurityPolicy> configuration switch. Please see <link> for more information.`

<a name="migration"></a>

## <a name="migration-replacement-for-obsolete-calls"></a>Преобразования Замена устаревших вызовов

### <a name="determining-an-assemblys-trust-level"></a>Определение уровня доверия сборки

Политика разграничения доступа кода часто используется для определения набора разрешений или уровня доверия, предоставляемых сборке или домену приложения. .NET Framework 4 предоставляет следующие полезные свойства, не требующие разрешения политики безопасности.

- <xref:System.Reflection.Assembly.PermissionSet%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.IsFullyTrusted%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.PermissionSet%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.IsFullyTrusted%2A?displayProperty=nameWithType>

### <a name="application-domain-sandboxing"></a>Изолирование домена приложения

Метод <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType>, как правило, используется для изолирования сборок в домене приложений. .NET Framework 4 предоставляет члены, которые не должны использоваться <xref:System.Security.Policy.PolicyLevel> для этой цели. Дополнительные сведения см. в разделе [Практическое руководство. Выполнение не вполне безопасного кода в изолированной среде](how-to-run-partially-trusted-code-in-a-sandbox.md).

### <a name="determining-a-safe-or-reasonable-permission-set-for-partially-trusted-code"></a>Определение безопасного или приемлемого набора разрешений для частично доверенного кода

Основным приложениям часто требуется определить разрешения, подходящие для изоляции кода, запускаемого из этих приложений. Прежде чем приступить к работе с .NET Framework 4, политика CAS предоставила <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType> способ сделать это с помощью метода. В качестве замены .NET Framework 4 предоставляет <xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=nameWithType> метод, который возвращает надежный стандартный набор разрешений для предоставленного свидетельства.

### <a name="non-sandboxing-scenarios-overloads-for-assembly-loads"></a>Сценарии без "песочницы": Перегрузки для загрузки сборок

Перегруженные методы загрузки сборок применяются, если вместо изоляции сборки в "песочнице" необходимо использовать параметры, которые недоступны иначе. Начиная с .NET Framework 4, перегрузки загрузки сборок, не требующие <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> объекта в качестве параметра, <xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.String%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Configuration.Assemblies.AssemblyHashAlgorithm%29?displayProperty=nameWithType>следует включить этот сценарий.

Чтобы поместить сборку в изолированную среду, воспользуйтесь перегрузкой <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType>.

<a name="compatibility"></a>

## <a name="compatibility-using-the-cas-policy-legacy-option"></a>См Использование устаревшей политики CAS

[Элемент конфигурации NetFx40_LegacySecurityPolicy>позволяетуказать,чтопроцессилибиблиотекаиспользуетустаревшуюполитикуразграничениядоступакода.\<](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) При включении этого элемента политика и перегруженные объекты свидетельств будут работать как в предыдущих версиях платформы.

> [!NOTE]
> Поведение политики разграничения доступа кода определяется для каждой версии среды выполнения, поэтому изменение этой политики для одной версии среды выполнения не повлияет на ее поведение в других версиях.

```xml
<configuration>
   <runtime>
      <NetFx40_LegacySecurityPolicy enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>См. также

- [Практическое руководство. Выполнение не вполне безопасного кода в изолированной среде](how-to-run-partially-trusted-code-in-a-sandbox.md)
- [Правила написания безопасного кода](../../standard/security/secure-coding-guidelines.md)
