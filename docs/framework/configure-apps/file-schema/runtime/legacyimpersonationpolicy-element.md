---
title: Элемент <legacyImpersonationPolicy>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#legacyImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/legacyImpersonationPolicy
helpviewer_keywords:
- <legacyImpersonationPolicy> element
- legacyImpersonationPolicy element
ms.assetid: 6e00af10-42f3-4235-8415-1bb2db78394e
ms.openlocfilehash: 5e43ead278ecd4049014f4000a2f056b2190f7e5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154108"
---
# <a name="legacyimpersonationpolicy-element"></a>\<legacyImpersonationПолитика> Элемент
Указывает, что удостоверение Windows не проходит через асинхронные точки, независимо от параметров потока для контекста выполнения в текущем потоке.  
  
[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>выполнения**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyImpersonationПолитика>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<legacyImpersonationPolicy
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|attribute|Описание|  
|---------------|-----------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Уточняется, что <xref:System.Security.Principal.WindowsIdentity> не проходит через асинхронные точки, независимо от настроек <xref:System.Threading.ExecutionContext> потока на текущем потоке.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|`false`|<xref:System.Security.Principal.WindowsIdentity>потоки через асинхронные <xref:System.Threading.ExecutionContext> точки в зависимости от настроек потока для текущего потока. Это значение по умолчанию.|  
|`true`|<xref:System.Security.Principal.WindowsIdentity>не течет по асинхронным <xref:System.Threading.ExecutionContext> точкам, независимо от настроек потока на текущем потоке.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Remarks  
 В версиях .NET Framework 1.0 и <xref:System.Security.Principal.WindowsIdentity> 1.1 не протекают по каким-либо асинхронным точкам, определяемым пользователем. Начиная с версии .NET Framework 2.0, есть <xref:System.Threading.ExecutionContext> объект, который содержит информацию о исполняемом потоке, который в настоящее время выполняет сяочие, и он течет по асинхронным точкам в домене приложения. Включено <xref:System.Security.Principal.WindowsIdentity> в этот контекст исполнения и, следовательно, также течет через асинхронные точки, что означает, что если контекст олицетворения существует, он будет течь также.  
  
 Начиная с .NET Framework 2.0, `<legacyImpersonationPolicy>` можно использовать <xref:System.Security.Principal.WindowsIdentity> элемент, чтобы указать, что не течет по асинхронным точкам.  
  
> [!NOTE]
> Общее время выполнения языка (CLR) знает об операциях олицетворения, выполняемых только управляемым кодом, а не олицетворения, выполняемых вне управляемого кода, например, через платформу, ссылающихся на неуправляемый код или через прямые вызовы к функциям Win32. Только <xref:System.Security.Principal.WindowsIdentity> управляемые объекты могут течь через `alwaysFlowImpersonationPolicy` асинхронные`<alwaysFlowImpersonationPolicy enabled="true"/>`точки, если элемент не был установлен на истину ( ). Установка `alwaysFlowImpersonationPolicy` элемента на истину указывает на то, что инообразная личность Windows всегда течет по асинхронным точкам, независимо от того, как выполнялось олицетворение. Для получения дополнительной информации о потоковых неуправляемых олицетворение через асинхронные точки, см [ \<всегдаFlowImpersonationПолитика> элемент](alwaysflowimpersonationpolicy-element.md).  
  
 Вы можете изменить это поведение по умолчанию двумя другими способами:  
  
1. В управляемом коде на основе на поток.  
  
     Вы можете подавить поток на основе потока, <xref:System.Threading.ExecutionContext> <xref:System.Security.SecurityContext> изменяя и <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType> <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> настройки с помощью, или <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> метод.  
  
2. При вызове к неуправляемому интерфейсу хостинга для загрузки общего языка времени выполнения (CLR).  
  
     Если для загрузки CLR используется неуправляемый интерфейс хостинга (вместо простого управляемого исполнителя), можно указать специальный флаг в функции [CorBindToRuntimeEx.](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) Чтобы включить режим совместимости для всего процесса, установите `flags` параметр для [функции CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) STARTUP_LEGACY_IMPERSONATION.  
  
 Для получения дополнительной [ \<](alwaysflowimpersonationpolicy-element.md)информации, см>.  
  
## <a name="configuration-file"></a>Файл конфигурации  
 В приложении .NET Framework этот элемент может быть использован только в файле конфигурации приложения.  
  
 Для ASP.NET приложения поток олицетворения может быть настроен в файле aspnet.config, найденном в каталоге \<Windows Folder>-Microsoft.NET-Framework-vx.x.xxxx.  
  
 ASP.NET по умолчанию отменяет поток олицетворения в файле aspnet.config с помощью следующих настроек конфигурации:  
  
``` xml
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
 В следующем примере показано, как указать устаревающее поведение, которое не пропускает иноедело Windows через асинхронные точки.  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также раздел

- [Схема параметров среды выполнения](index.md)
- [Схема конфигурации файлов](../index.md)
- [\<всегдаFlowImpersonationПолитика> Элемент](alwaysflowimpersonationpolicy-element.md)
