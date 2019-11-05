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
ms.openlocfilehash: 06e91ea6989dcdf0b2a179e7d6ce79b8d9aaff03
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73118344"
---
# <a name="alwaysflowimpersonationpolicy-element"></a>\<Алвайсфловимперсонатионполици > элемент
Указывает, что удостоверение Windows всегда проходит через асинхронные точки, независимо от того, как было выполнено олицетворение.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) \
&nbsp;&nbsp;&nbsp;&nbsp; **\<алвайсфловимперсонатионполици >** \  
  
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
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, проходит ли идентификация Windows между асинхронными точками.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|значения|Описание|  
|-----------|-----------------|  
|`false`|Удостоверение Windows не передается через асинхронные точки, если олицетворение не выполняется с помощью управляемых методов, таких как <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>. Это значение по умолчанию.|  
|`true`|Удостоверение Windows всегда проходит через асинхронные точки независимо от того, как было выполнено олицетворение.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Заметки  
 В .NET Framework версиях 1,0 и 1,1 идентификатор Windows не проходит через асинхронные точки. В .NET Framework версии 2,0 имеется объект <xref:System.Threading.ExecutionContext>, содержащий сведения о выполняемом в данный момент потоке и перенаправляемый его между асинхронными точками в домене приложения. <xref:System.Security.Principal.WindowsIdentity> также передается как часть информации, которая проходит через асинхронные точки, при условии, что олицетворение достигается с помощью управляемых методов, таких как <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>, а не с помощью других средств, таких как вызов неуправляемого кода в машинные методы. Этот элемент позволяет указать, что удостоверение Windows выполняет потоковую передачу через асинхронные точки независимо от того, как было достигнуто олицетворение.  
  
 Это поведение по умолчанию можно изменить двумя способами.  
  
1. В управляемом коде на основе каждого потока.  
  
     Можно подавить поток на основе каждого потока, изменив параметры <xref:System.Threading.ExecutionContext> и <xref:System.Security.SecurityContext> с помощью метода <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>или <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType>.  
  
2. В вызове неуправляемого интерфейса размещения для загрузки среды CLR.  
  
     Если для загрузки среды CLR используется неуправляемый интерфейс размещения (вместо простого управляемого исполняемого файла), можно указать специальный флаг в вызове функции [функции CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) . Чтобы включить режим совместимости для всего процесса, задайте `flags` для параметра [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) функции значение `STARTUP_ALWAYSFLOW_IMPERSONATION`.  
  
## <a name="configuration-file"></a>Файл конфигурации  
 В приложении .NET Framework этот элемент можно использовать только в файле конфигурации приложения.  
  
 Для приложения ASP.NET поток олицетворения можно настроить в файле aspnet. config, который находится в папке \<Windows > Каталог \Микрософт.нет\фрамеворк\вкс.КС.кскскскс.  
  
 ASP.NET по умолчанию отключает поток олицетворения в файле aspnet. config, используя следующие параметры конфигурации:  
  
```xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 В ASP.NET, если требуется разрешить поток олицетворения, необходимо явно использовать следующие параметры конфигурации:  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как указать, что удостоверение Windows проходит через асинхронные точки, даже если олицетворение достигается через средства, отличные от управляемых методов.  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- [Схема параметров среды выполнения](index.md)
- [Схема файла конфигурации](../index.md)
- [\<Легациимперсонатионполици > элемент](legacyimpersonationpolicy-element.md)
