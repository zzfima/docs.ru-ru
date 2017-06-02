---
title: "Code Access Security Policy Compatibility and Migration | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "policy migration, compatibility"
  - "CLR poliicy migration"
ms.assetid: 19cb4d39-e38a-4262-b507-458915303115
caps.latest.revision: 15
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# Code Access Security Policy Compatibility and Migration
Политика разграничения доступа кода \(CAS\) является устаревшей в [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)].  В результате при вызове устаревших типов политик и членов [явным](#explicit_use) или [неявным](#implicit_use) \(через другие типы и члены\) образом могут возникать предупреждения компиляции и исключения среды выполнения.  
  
 Избежать появления таких предупреждений и ошибок можно следующими способами:  
  
-   [перейти](#migration) на использование вызовов [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], заменяющих устаревшие вызовы;  
  
     \-или\-  
  
-   использовать элемент конфигурации [\<NetFx40\_LegacySecurityPolicy\>](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) для выбора политики разграничения доступа кода прежних версий.  
  
 В этом разделе содержатся следующие подразделы.  
  
-   [Явное использование](#explicit_use)  
  
-   [Неявное использование](#implicit_use)  
  
-   [Ошибки и предупреждения](#errors_and_warnings)  
  
-   [Миграция: замена устаревших вызовов](#migration)  
  
-   [Совместимость: использование политики разграничения доступа кода прежних версий](#compatibility)  
  
> [!CAUTION]
>  Управление доступом для кода и частично доверенный код  
>   
>  Платформа .NET Framework предоставляет механизм для принудительного применения различных уровней доверия к разным частям кода, выполняемым в одном и том же приложении. Этот механизм называется управлением доступом для кода.  Управление доступом для кода в .NET Framework не следует использовать в качестве средства безопасности при работе с частично доверенным кодом, особенно кодом неизвестного происхождения.  Мы не рекомендуем загружать и выполнять код из неизвестных источников, не предприняв дополнительные меры безопасности.  
>   
>  Эта политика действует в отношении всех версий платформы .NET Framework, кроме платформы .NET Framework в составе Silverlight.  
  
<a name="explicit_use"></a>   
## Явное использование  
 Члены, которые непосредственно управляют политикой безопасности или требуют политики разграничения доступа кода для изоляции в "песочнице", являются устаревшими и по умолчанию вызывают ошибки.  
  
 Ниже приводятся некоторые примеры.  
  
-   <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=fullName>  
  
-   <xref:System.Security.HostSecurityManager.DomainPolicy%2A?displayProperty=fullName>  
  
-   <xref:System.Security.Policy.PolicyLevel.CreateAppDomainLevel%2A?displayProperty=fullName>  
  
-   <xref:System.Security.SecurityManager.LoadPolicyLevelFromString%2A?displayProperty=fullName>  
  
-   <xref:System.Security.SecurityManager.LoadPolicyLevelFromFile%2A?displayProperty=fullName>  
  
-   <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=fullName>  
  
-   <xref:System.Security.SecurityManager.ResolveSystemPolicy%2A?displayProperty=fullName>  
  
-   <xref:System.Security.SecurityManager.ResolvePolicyGroups%2A?displayProperty=fullName>  
  
-   <xref:System.Security.SecurityManager.PolicyHierarchy%2A?displayProperty=fullName>  
  
-   <xref:System.Security.SecurityManager.SavePolicy%2A?displayProperty=fullName>  
  
<a name="implicit_use"></a>   
## Неявное использование  
 Несколько перегруженных методов загрузки сборки вызывают ошибки из\-за неявного использования политики разграничения доступа кода.  Эти перегруженные методы принимают параметр <xref:System.Security.Policy.Evidence>, разрешающий политику разграничения доступа кода, и предоставляют сборке набор разрешений.  
  
 Ниже приводятся некоторые примеры.  Устаревшие перегрузки — это перегрузки, принимающие в качестве параметра <xref:System.Security.Policy.Evidence>.  
  
-   <xref:System.Activator.CreateInstanceFrom%2A?displayProperty=fullName>  
  
-   <xref:System.AppDomain.CreateInstanceFrom%2A?displayProperty=fullName>  
  
-   <xref:System.AppDomain.CreateInstanceAndUnwrap%2A?displayProperty=fullName>  
  
-   <xref:System.AppDomain.DefineDynamicAssembly%2A?displayProperty=fullName>  
  
-   <xref:System.AppDomain.ExecuteAssemblyByName%2A?displayProperty=fullName>  
  
-   <xref:System.AppDomain.Load%2A?displayProperty=fullName>  
  
-   <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName>  
  
-   <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>  
  
-   <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName>  
  
<a name="errors_and_warnings"></a>   
## Ошибки и предупреждения  
 При использовании устаревших типов и членов возникают указанные ниже сообщения об ошибках.  Обратите внимание, что сам тип <xref:System.Security.Policy.Evidence?displayProperty=fullName> не является устаревшим.  
  
 Предупреждение времени компиляции:  
  
 `warning CS0618: '<API Name>' is obsolete: 'This method is obsolete and will be removed in a future release of the .NET Framework.  Please use <suggested alternate API>.  See <link> for more information.'`  
  
 Исключение времени выполнения:  
  
 <xref:System.NotSupportedException>: `This method uses CAS policy, which has been obsoleted by the .NET Framework. In order to enable CAS policy for compatibility reasons, please use the <NetFx40_LegacySecurityPolicy> configuration switch. Please see <link> for more information.`  
  
<a name="migration"></a>   
## Миграция: замена устаревших вызовов  
  
### Определение уровня доверия сборки  
 Политика разграничения доступа кода часто используется для определения набора разрешений или уровня доверия, предоставляемых сборке или домену приложения.  Платформа [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] предоставляет следующие полезные свойства, не требующие разрешения политики безопасности:  
  
-   <xref:System.Reflection.Assembly.PermissionSet%2A?displayProperty=fullName>  
  
-   <xref:System.Reflection.Assembly.IsFullyTrusted%2A?displayProperty=fullName>  
  
-   <xref:System.AppDomain.PermissionSet%2A?displayProperty=fullName>  
  
-   <xref:System.AppDomain.IsFullyTrusted%2A?displayProperty=fullName>  
  
### Изолирование домена приложения  
 Метод <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=fullName>, как правило, используется для изолирования сборок в домене приложений.  [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] предоставляет члены, которые не должны использовать <xref:System.Security.Policy.PolicyLevel> для этой цели. Подробнее см. в разделе [How to: Run Partially Trusted Code in a Sandbox](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md).  
  
### Определение безопасного или приемлемого набора разрешений для частично доверенного кода  
 Основным приложениям часто требуется определить разрешения, подходящие для изоляции кода, запускаемого из этих приложений.  До выпуска версии [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] политика разграничения доступа кода выполняла эту функцию с помощью метода <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=fullName>.  Вместо этого [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] предоставляет метод <xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=fullName>, который возвращает безопасный стандартный набор разрешений для предоставленного свидетельства.  
  
### Сценарии без использования "песочницы": перегруженные методы для загрузки сборок  
 Перегруженные методы загрузки сборок применяются, если вместо изоляции сборки в "песочнице" необходимо использовать параметры, которые недоступны иначе.  Начиная с [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] этот сценарий возможен при работе с перегруженными методами загрузки сборок, не использующими в качестве параметра объект <xref:System.Security.Policy.Evidence?displayProperty=fullName>, например с методом [AppDomain.ExecuteAssembly\(String, String\[\], Byte\<xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.String%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Configuration.Assemblies.AssemblyHashAlgorithm%29?displayProperty=fullName>.  
  
 Чтобы поместить сборку в изолированную среду, воспользуйтесь перегрузкой [AppDomain.CreateDomain\(String, Evidence, AppDomainSetup, PermissionSet, StrongName\<xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=fullName>.  
  
<a name="compatibility"></a>   
## Совместимость: использование политики разграничения доступа кода прежних версий  
 Элемент конфигурации [\<NetFx40\_LegacySecurityPolicy\>](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) позволяет указать, что процесс или библиотека использует политику разграничения доступа кода прежних версий.  При включении этого элемента политика и перегруженные объекты свидетельств будут работать как в предыдущих версиях платформы.  
  
> [!NOTE]
>  Поведение политики разграничения доступа кода определяется для каждой версии среды выполнения, поэтому изменение этой политики для одной версии среды выполнения не повлияет на ее поведение в других версиях.  
  
```  
<configuration>  
   <runtime>  
      <NetFx40_LegacySecurityPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## См. также  
 [How to: Run Partially Trusted Code in a Sandbox](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)