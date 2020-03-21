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
# <a name="alwaysflowimpersonationpolicy-element"></a>\<всегдаFlowImpersonationПолитика> Элемент
Указывает, что удостоверение Windows всегда проходит через асинхронные точки, независимо от того, как было выполнено олицетворение.  
  
[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>выполнения**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<всегдаFlowImpersonationПолитика>**\  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<alwaysFlowImpersonationPolicy
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|attribute|Описание|  
|---------------|-----------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, течет ли идентификация Windows по асинхронным точкам.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|`false`|Идентификация Windows не проходит через асинхронные точки, если олицетворение <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>не выполняется с помощью управляемых методов, таких как . Это значение по умолчанию.|  
|`true`|Идентификация Windows всегда течет по асинхронным точкам, независимо от того, как выполнялось олицетворение.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Remarks  
 В версиях .NET Framework 1.0 и 1.1 идентификация Windows не проходит через асинхронные точки. В версии 2.0 .NET Framework <xref:System.Threading.ExecutionContext> есть объект, который содержит информацию о исполняемом потоке, который в настоящее время выполняет сяочие, и перетекает в асинхронные точки в домене приложения. Также <xref:System.Security.Principal.WindowsIdentity> течет как часть информации, которая течет через асинхронные точки, при <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> условии, что олицетворение было достигнуто с помощью управляемых методов, таких как, а не с помощью других средств, таких как платформа ссылаться на родные методы. Этот элемент используется для указания того, что инообразная личность Windows действительно проходит через асинхронные точки, независимо от того, как было достигнуто олицетворение.  
  
 Вы можете изменить это поведение по умолчанию двумя другими способами:  
  
1. В управляемом коде на основе на поток.  
  
     Вы можете подавить поток на основе потока, <xref:System.Threading.ExecutionContext> <xref:System.Security.SecurityContext> изменяя и <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType> <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>настройки <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> с помощью, или метод.  
  
2. При вызове к неуправляемому интерфейсу хостинга для загрузки общего языка времени выполнения (CLR).  
  
     Если для загрузки CLR используется неуправляемый интерфейс хостинга (вместо простого управляемого исполнителя), можно указать специальный флаг в функции [CorBindToRuntimeEx.](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) Чтобы включить режим совместимости для всего процесса, установите `flags` параметр для `STARTUP_ALWAYSFLOW_IMPERSONATION` [функции CorBindToRuntimeEx.](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)  
  
## <a name="configuration-file"></a>Файл конфигурации  
 В приложении .NET Framework этот элемент может быть использован только в файле конфигурации приложения.  
  
 Для ASP.NET приложения поток олицетворения может быть настроен в файле aspnet.config, найденном в каталоге \<Windows Folder>-Microsoft.NET-Framework-vx.x.xxxx.  
  
 ASP.NET по умолчанию отменяет поток олицетворения в файле aspnet.config с помощью следующих настроек конфигурации:  
  
```xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 В ASP.NET, если вместо этого требуется разрешить поток олицетворения, необходимо явно использовать следующие настройки конфигурации:  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как указать, что идентификация Windows течет по асинхронным точкам, даже если олицетворение достигается с помощью других средств, помимо управляемых методов.  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также раздел

- [Схема параметров среды выполнения](index.md)
- [Схема конфигурации файлов](../index.md)
- [\<legacyImpersonationПолитика> Элемент](legacyimpersonationpolicy-element.md)
