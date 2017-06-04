---
title: "Элемент &lt;legacyImpersonationPolicy&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#legacyImpersonationPolicy"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/legacyImpersonationPolicy"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<legacyImpersonationPolicy> - элемент"
  - "legacyImpersonationPolicy - элемент"
ms.assetid: 6e00af10-42f3-4235-8415-1bb2db78394e
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Элемент &lt;legacyImpersonationPolicy&gt;
Указывает, что удостоверение Windows не проходит через асинхронные точки, независимо от параметров потока для контекста выполнения в текущем потоке.  
  
## Синтаксис  
  
```  
<legacyImpersonationPolicy    
   enabled="true|false"/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, что <xref:System.Security.Principal.WindowsIdentity> не проходит через асинхронные точки, независимо от параметров потока <xref:System.Threading.ExecutionContext> в текущем потоке.|  
  
## Атрибут enabled  
  
|Значение|Описание|  
|--------------|--------------|  
|`false`|<xref:System.Security.Principal.WindowsIdentity> проходит через асинхронные точки в зависимости от параметров потока <xref:System.Threading.ExecutionContext> для текущего потока.  Это значение по умолчанию.|  
|`true`|<xref:System.Security.Principal.WindowsIdentity> не проходит через асинхронные точки независимо от параметров потока <xref:System.Threading.ExecutionContext> в текущем потоке.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`runtime`|Элемент, содержащий сведения о привязке сборок и сборке мусора.|  
  
## Заметки  
 В платформе .NET Framework версии 1.0 и 1.1 <xref:System.Security.Principal.WindowsIdentity> не проходит через определенные пользователем асинхронные точки.  В .NET Framework версии 2.0 существует объект <xref:System.Threading.ExecutionContext>, содержащий информацию о текущем исполняемом потоке и проводящий его через асинхронные точки в домене приложения.  <xref:System.Security.Principal.WindowsIdentity> также проходит как часть информации, проходящей через асинхронные точки. Это означает, что если имеется контекст олицетворения, то он также пройдет через асинхронные точки.  Этот элемент используется для указания, что <xref:System.Security.Principal.WindowsIdentity> не проходит через асинхронные точки.  
  
> [!NOTE]
>  Среда CLR учитывает операции олицетворения, выполняемые только с помощью управляемого кода, но не учитывает олицетворение, выполняемое за пределами управляемого кода, например с помощью вызова платформой неуправляемого кода или через прямое обращение к функциям Win32.  Только управляемые объекты <xref:System.Security.Principal.WindowsIdentity> могут проходить через асинхронные точки, при условии, что для элемента `alwaysFlowImpersonationPolicy` не установлено значение "true" \(`<alwaysFlowImpersonationPolicy enabled="true"/>`\).  Если же элемент `alwaysFlowImpersonationPolicy` имеет значение "true", то удостоверениеWindows всегда будет проходить через асинхронные точки, независимо от того, как было выполнено олицетворение.  Дополнительные сведения о прохождении неуправляемого олицетворения через асинхронные точки см. в разделе [Элемент \<alwaysFlowImpersonationPolicy\>](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).  
  
 Этот элемент может использоваться только в файле конфигурации приложения.  
  
 Это заданное по умолчанию поведение можно изменить двумя способами.  
  
1.  В управляемом коде для каждого потока.  
  
     Можно подавить прохождение в каждом потоке, изменив параметры <xref:System.Threading.ExecutionContext> и <xref:System.Security.SecurityContext> с помощью метода <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=fullName>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=fullName> или <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=fullName>.  
  
2.  В вызове неуправляемого интерфейса размещения для загрузки среды CLR.  
  
     Если для загрузки среды CLR используется неуправляемый интерфейс размещения \(вместо простого управляемого исполняемого файла\), можно указать специальный флаг вызова функции [Функция CorBindToRuntimeEx](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md).  Чтобы включить режим совместимости для всего процесса, установите для параметра `flags` для [Функция CorBindToRuntimeEx](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) значение "STARTUP\_LEGACY\_IMPERSONATION".  
  
## Пример  
 В следующем примере показано, как задать прежнее поведение, при котором удостоверение Windows не проходит через асинхронные точки.  
  
```  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## См. также  
 [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)