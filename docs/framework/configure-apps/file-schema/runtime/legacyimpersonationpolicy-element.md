---
title: '&lt;legacyImpersonationPolicy&gt; элемент'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#legacyImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/legacyImpersonationPolicy
helpviewer_keywords:
- <legacyImpersonationPolicy> element
- legacyImpersonationPolicy element
ms.assetid: 6e00af10-42f3-4235-8415-1bb2db78394e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c0d71bef4ad68c2fea63cec413e8bd17b78df1d0
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2018
ms.locfileid: "53614364"
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
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, что <xref:System.Security.Principal.WindowsIdentity> не проходит через асинхронные точки, вне зависимости от <xref:System.Threading.ExecutionContext> настройки в текущем потоке.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание:|  
|-----------|-----------------|  
|`false`|<xref:System.Security.Principal.WindowsIdentity> проходит через асинхронные точки, в зависимости от <xref:System.Threading.ExecutionContext> настройки для текущего потока. Это значение по умолчанию.|  
|`true`|<xref:System.Security.Principal.WindowsIdentity> не проходит через асинхронные точки, вне зависимости от <xref:System.Threading.ExecutionContext> настройки в текущем потоке.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Примечания  
 В .NET Framework версий 1.0 и 1.1 <xref:System.Security.Principal.WindowsIdentity> не проходит через асинхронные точки все определяемые пользователем. Начиная с .NET Framework версии 2.0, имеется <xref:System.Threading.ExecutionContext> , содержащий сведения о текущем потоке и он проходит через асинхронные точки в домене приложения. <xref:System.Security.Principal.WindowsIdentity> Включается в этот контекст выполнения и таким образом, также проходит через асинхронные точки, это означает, что если существует контекст олицетворения, то оно будет доставлено также.  
  
 Начиная с .NET Framework 2.0, можно использовать `<legacyImpersonationPolicy>` элемент, чтобы указать, что <xref:System.Security.Principal.WindowsIdentity> не проходит через асинхронные точки.  
  
> [!NOTE]
>  Среда CLR (CLR) известно олицетворения операции, выполняемые только с помощью управляемого кода, не олицетворения, выполняемое за пределами управляемого кода, например с помощью платформы вызова неуправляемого кода или через прямое обращение к функции Win32. Только для управляемого <xref:System.Security.Principal.WindowsIdentity> объектов можно проходит через асинхронные точки, если не `alwaysFlowImpersonationPolicy` было установлено значение true (`<alwaysFlowImpersonationPolicy enabled="true"/>`). Параметр `alwaysFlowImpersonationPolicy` элемент значение true указывает, что удостоверение Windows всегда проходит через асинхронные точки, независимо от того, как было выполнено олицетворение. Дополнительные сведения о прохождении неуправляемого олицетворения через асинхронные точки, см. в разделе [ \<alwaysFlowImpersonationPolicy > элемента](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).  
  
 Можно изменить это поведение по умолчанию двумя способами:  
  
1.  В управляемом коде для каждого потока.  
  
     Поток для каждого потока можно отключить, изменив <xref:System.Threading.ExecutionContext> и <xref:System.Security.SecurityContext> параметры с помощью <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> или <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> метод.  
  
2.  В вызове неуправляемого интерфейса размещения для загрузки общеязыковой среды выполнения (CLR).  
  
     Если неуправляемый интерфейс размещения (вместо простой управляемый исполняемый файл) используется для загрузки среды CLR, можно указать специальный флаг в вызове [функция CorBindToRuntimeEx](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) функции. Чтобы включить режим совместимости для всего процесса, задайте `flags` параметр для [функция CorBindToRuntimeEx](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) для STARTUP_LEGACY_IMPERSONATION.  
  
 Дополнительные сведения см. в разделе [ \<alwaysFlowImpersonationPolicy > элемента](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).  
  
## <a name="configuration-file"></a>Файл конфигурации  
 В приложении .NET Framework этот элемент может использоваться только в файле конфигурации приложения.  
  
 Для приложения ASP.NET поток олицетворения можно настроить в файле aspnet.config в \<папка Windows > \Microsoft.NET\Framework\vx.x.xxxx каталога.  
  
 ASP.NET по умолчанию отключает поток олицетворения в файле aspnet.config, используя следующие параметры конфигурации:  
  
``` xml
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
 В следующем примере показано задание устаревшее поведение, которое не проходит через асинхронные точки удостоверение Windows.  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
- [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
- [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)  
- [\<alwaysFlowImpersonationPolicy > элемента](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)
