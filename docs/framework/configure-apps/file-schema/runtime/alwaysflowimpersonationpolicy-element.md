---
title: '&lt;alwaysFlowImpersonationPolicy&gt; элемент'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/alwaysFlowImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#alwaysFlowImpersonationPolicy
helpviewer_keywords:
- alwaysFlowImpersonationPolicy element
- <alwaysFlowImpersonationPolicy> element
ms.assetid: ee622801-9e46-470b-85ab-88c4b1dd2ee1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5cc704bbf8631936dbbeb3539ea5ed0d8499f378
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltalwaysflowimpersonationpolicygt-element"></a>&lt;alwaysFlowImpersonationPolicy&gt; элемент
Указывает, что удостоверение Windows всегда проходит через асинхронные точки, независимо от того, как было выполнено олицетворение.  
  
 \<configuration>  
\<Среда выполнения >  
\<alwaysFlowImpersonationPolicy>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<alwaysFlowImpersonationPolicy    
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, является ли удостоверение Windows проходит через асинхронные точки.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|`false`|Удостоверение не проходит через асинхронные точки, если олицетворение осуществляется с помощью Windows управляемые методы, такие как <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>. Это значение по умолчанию.|  
|`true`|Идентификация Windows всегда проходит через асинхронные точки, независимо от того, как было выполнено олицетворение.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Примечания  
 В .NET Framework версий 1.0 и 1.1 удостоверение Windows не проходит через асинхронные точки. В платформе .NET Framework версии 2.0 имеется <xref:System.Threading.ExecutionContext> объект, который содержит сведения о текущей выполняемой потока и он проходит через асинхронные точки в домене приложения. <xref:System.Security.Principal.WindowsIdentity> Также потоки как часть сведений, который проходит через асинхронные точки, если было выполнено олицетворение с помощью управляемых методы, такие как <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> и не через другие средства, такие как платформы неуправляемого кода для собственных методов. Этот элемент используется для указания, что удостоверение Windows проходит через асинхронные точки, независимо от того, как было выполнено олицетворение.  
  
 Можно изменить это поведение по умолчанию двумя способами:  
  
1.  В управляемом коде для каждого потока.  
  
     Поток для каждого потока можно отключить, изменив <xref:System.Threading.ExecutionContext> и <xref:System.Security.SecurityContext> параметры с помощью <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, или <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> метод.  
  
2.  В вызове неуправляемого интерфейса размещения для загрузки общеязыковой среды выполнения (CLR).  
  
     Если неуправляемый интерфейс размещения (вместо простого управляемого исполняемого файла) используется для загрузки среды CLR, можно указать специальный флаг в вызове [функция CorBindToRuntimeEx](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) функции. Чтобы включить режим совместимости для всего процесса, задайте `flags` параметр [функция CorBindToRuntimeEx](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) для `STARTUP_ALWAYSFLOW_IMPERSONATION`.  
  
## <a name="configuration-file"></a>Файл конфигурации  
 В приложениях .NET Framework этот элемент может использоваться только в файле конфигурации приложения.  
  
 Для приложения ASP.NET поток олицетворения можно настраивать в файле aspnet.config в \<папка Windows > \Microsoft.NET\Framework\vx.x.xxxx каталога.  
  
 ASP.NET по умолчанию отключает поток олицетворения в файле aspnet.config, используя следующие параметры конфигурации:  
  
```xml
<configuration>  
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
 Приведенный ниже показано, как указать, что удостоверение Windows проходит через асинхронные точки, даже в том случае, если олицетворение достигается с помощью средств, отличных от управляемых методов.  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
 [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [\<legacyImpersonationPolicy > элемент](../../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)
