---
title: "Элемент &lt;alwaysFlowImpersonationPolicy&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/alwaysFlowImpersonationPolicy"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#alwaysFlowImpersonationPolicy"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<alwaysFlowImpersonationPolicy> - элемент"
  - "alwaysFlowImpersonationPolicy - элемент"
ms.assetid: ee622801-9e46-470b-85ab-88c4b1dd2ee1
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# Элемент &lt;alwaysFlowImpersonationPolicy&gt;
Указывает, что идентификация Windows всегда проходит через асинхронные точки, независимо от того, как было выполнено олицетворение.  
  
## Синтаксис  
  
```  
<alwaysFlowImpersonationPolicy    
  enabled="true|false"/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, проходит ли идентификация Windows через асинхронные точки.|  
  
## Атрибут enabled  
  
|Значение|Описание|  
|--------------|--------------|  
|`false`|Идентификация Windows не проходит через асинхронные точки, если олицетворение не выполняется управляемыми методами, такими как <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.  Это значение по умолчанию.|  
|`true`|Идентификация Windows всегда проходит через асинхронные точки, независимо от того, как было выполнено олицетворение.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`runtime`|Элемент, содержащий сведения о привязке сборок и сборке мусора.|  
  
## Заметки  
 В .NET Framework версии 1.0 и 1.1 идентификация Windows не проходит через асинхронные точки.  В .NET Framework версии 2.0 существует объект <xref:System.Threading.ExecutionContext>, содержащий информацию о текущем исполняемом потоке и проводящий его через асинхронные точки в домене приложения.  <xref:System.Security.Principal.WindowsIdentity> проходит также в составе информации, проходящей через асинхронные точки, если олицетворение было произведено с использованием управляемых методов, таких как <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>, а не другими способами, например путем вызова неуправляемого кода встроенных методов.  Этот элемент указывает, что идентификация Windows всегда проходит через асинхронные точки, независимо от того, как было выполнено олицетворение.  
  
 Это заданное по умолчанию поведение можно изменить двумя способами.  
  
1.  В управляемом коде для каждого потока.  
  
     Можно запретить прохождение для отдельного потока путем изменения значений <xref:System.Threading.ExecutionContext> и <xref:System.Security.SecurityContext>, используя методы <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=fullName>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=fullName> или <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=fullName>.  
  
2.  В вызове неуправляемого интерфейса размещения для загрузки среды CLR.  
  
     Если для загрузки среды CLR используется неуправляемый интерфейс размещения \(вместо простого управляемого исполняемого файла\), можно указать специальный флаг вызова функции [Функция CorBindToRuntimeEx](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md).  Чтобы включить режим совместимости для всего процесса, установите параметр `flags` для [Функция CorBindToRuntimeEx](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) равным STARTUP\_ALWAYSFLOW\_IMPERSONATION.  
  
## Файл конфигурации  
 Этот элемент может использоваться только в файле конфигурации приложения.  
  
## Пример  
 В следующем примере показывается, как задать прохождение идентификации Windows через асинхронные точки даже в том случае, если олицетворение производилось какими\-либо иными способами, помимо управляемых методов.  
  
```  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## См. также  
 [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Элемент \<legacyImpersonationPolicy\>](../../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)