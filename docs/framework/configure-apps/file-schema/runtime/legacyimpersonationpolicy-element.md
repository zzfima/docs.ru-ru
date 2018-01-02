---
title: "&lt;legacyImpersonationPolicy&gt; элемент"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#legacyImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/legacyImpersonationPolicy
helpviewer_keywords:
- <legacyImpersonationPolicy> element
- legacyImpersonationPolicy element
ms.assetid: 6e00af10-42f3-4235-8415-1bb2db78394e
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: caeede11d8128af00beb5b1b3426e8c4a5406520
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltlegacyimpersonationpolicygt-element"></a>&lt;legacyImpersonationPolicy&gt; элемент
Указывает, что удостоверение Windows не проходит через асинхронные точки, независимо от параметров потока для контекста выполнения в текущем потоке.  
  
 \<configuration>  
\<Среда выполнения >  
\<legacyImpersonationPolicy >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<legacyImpersonationPolicy    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, что <xref:System.Security.Principal.WindowsIdentity> не проходит через асинхронные точки, независимо от <xref:System.Threading.ExecutionContext> потока параметры в текущем потоке.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание:|  
|-----------|-----------------|  
|`false`|<xref:System.Security.Principal.WindowsIdentity>потоки через асинхронные точки, в зависимости от <xref:System.Threading.ExecutionContext> потока параметры для текущего потока. Это значение по умолчанию.|  
|`true`|<xref:System.Security.Principal.WindowsIdentity>не проходит через асинхронные точки, независимо от <xref:System.Threading.ExecutionContext> потока параметры в текущем потоке.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Примечания  
 В .NET Framework версий 1.0 и 1.1 <xref:System.Security.Principal.WindowsIdentity> не проходит через все асинхронные точки, определяемой пользователем. Начиная с .NET Framework версии 2.0, имеется <xref:System.Threading.ExecutionContext> объект, содержащий сведения о текущий выполняемый поток, который проходит через асинхронные точки в домене приложения. <xref:System.Security.Principal.WindowsIdentity> Включается в этот контекст выполнения и поэтому проходит через асинхронные точки, это означает, что если существует контекст олицетворения, он будет проходить также.  
  
 Начиная с .NET Framework 2.0, можно использовать `<legacyImpersonationPolicy>` элемент, чтобы указать, что <xref:System.Security.Principal.WindowsIdentity> не проходит через асинхронные точки.  
  
> [!NOTE]
>  Общеязыковая среда выполнения (CLR) учитывает операции олицетворения, выполняемые с помощью только управляемого кода, не олицетворение, выполняемое за пределами управляемого кода, например с помощью платформы вызова неуправляемого кода или через прямое обращение к функции Win32. Только управляемые <xref:System.Security.Principal.WindowsIdentity> объектов могут проходить через асинхронные точки, если не `alwaysFlowImpersonationPolicy` было установлено значение true (`<alwaysFlowImpersonationPolicy enabled="true"/>`). Параметр `alwaysFlowImpersonationPolicy` элемент значение true указывает, что удостоверение Windows всегда проходит через асинхронные точки, независимо от того, как было выполнено олицетворение. Дополнительные сведения о прохождении неуправляемого олицетворения через асинхронные точки см. в разделе [ \<alwaysFlowImpersonationPolicy > элемент](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).  
  
 Можно изменить это поведение по умолчанию двумя способами:  
  
1.  В управляемом коде для каждого потока.  
  
     Поток для каждого потока можно отключить, изменив <xref:System.Threading.ExecutionContext> и <xref:System.Security.SecurityContext> параметры с помощью <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> или <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> метод.  
  
2.  В вызове неуправляемого интерфейса размещения для загрузки общеязыковой среды выполнения (CLR).  
  
     Если неуправляемый интерфейс размещения (вместо простого управляемого исполняемого файла) используется для загрузки среды CLR, можно указать специальный флаг в вызове [функция CorBindToRuntimeEx](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) функции. Чтобы включить режим совместимости для всего процесса, задайте `flags` параметр [функция CorBindToRuntimeEx](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) для STARTUP_LEGACY_IMPERSONATION.  
  
 Дополнительные сведения см. в разделе [ \<alwaysFlowImpersonationPolicy > элемент](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).  
  
## <a name="configuration-file"></a>Файл конфигурации  
 В приложениях .NET Framework этот элемент может использоваться только в файле конфигурации приложения.  
  
 Для приложения ASP.NET поток олицетворения можно настраивать в файле aspnet.config в \<папка Windows > \Microsoft.NET\Framework\vx.x.xxxx каталога.  
  
 ASP.NET по умолчанию отключает поток олицетворения в файле aspnet.config, используя следующие параметры конфигурации:  
  
```  
configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 В ASP.NET Если вы хотите разрешить поток олицетворения, вместо этого необходимо явно использовать следующие параметры конфигурации:  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a>Пример  
 Приведенный ниже показано, как задать прежнее поведение, удостоверение Windows не проходит через асинхронные точки.  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
 [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [\<alwaysFlowImpersonationPolicy > элемент](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)
