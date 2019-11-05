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
ms.openlocfilehash: 18a027bc09f2400a10a06efdc4c5355686bcb56d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116532"
---
# <a name="legacyimpersonationpolicy-element"></a>\<Легациимперсонатионполици > элемент
Указывает, что удостоверение Windows не проходит через асинхронные точки, независимо от параметров потока для контекста выполнения в текущем потоке.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) \
&nbsp;&nbsp;&nbsp;&nbsp; **\<легациимперсонатионполици >**  
  
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
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, что <xref:System.Security.Principal.WindowsIdentity> не передается по асинхронным точкам, независимо от параметров потока <xref:System.Threading.ExecutionContext> в текущем потоке.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|значения|Описание|  
|-----------|-----------------|  
|`false`|<xref:System.Security.Principal.WindowsIdentity> проходит через асинхронные точки в зависимости от параметров потока <xref:System.Threading.ExecutionContext> для текущего потока. Это значение по умолчанию.|  
|`true`|<xref:System.Security.Principal.WindowsIdentity> не перетекает через асинхронные точки, независимо от параметров потока <xref:System.Threading.ExecutionContext> в текущем потоке.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Заметки  
 В .NET Framework версиях 1,0 и 1,1 <xref:System.Security.Principal.WindowsIdentity> не проходит через определенные пользователем асинхронные точки. Начиная с версии .NET Framework 2,0 существует объект <xref:System.Threading.ExecutionContext>, который содержит сведения о выполняемом в данный момент потоке и проходит через асинхронные точки в пределах домена приложения. <xref:System.Security.Principal.WindowsIdentity> включается в этот контекст выполнения и, следовательно, проходит через асинхронные точки, что означает, что если контекст олицетворения существует, он также будет работать.  
  
 Начиная с .NET Framework 2,0 можно использовать элемент `<legacyImpersonationPolicy>`, чтобы указать, что <xref:System.Security.Principal.WindowsIdentity> не проходит через асинхронные точки.  
  
> [!NOTE]
> Общеязыковая среда выполнения (CLR) осведомлена об операциях олицетворения, выполняемых только с помощью управляемого кода, а не олицетворения, выполненных за пределами управляемого кода, например посредством вызова неуправляемого кода платформой или прямых вызовов функций Win32. Только управляемые объекты <xref:System.Security.Principal.WindowsIdentity> могут передаваться по асинхронным точкам, если только элемент `alwaysFlowImpersonationPolicy` не имеет значение true (`<alwaysFlowImpersonationPolicy enabled="true"/>`). Установка значения true для элемента `alwaysFlowImpersonationPolicy` указывает, что удостоверение Windows всегда проходит через асинхронные точки независимо от того, как было выполнено олицетворение. Дополнительные сведения о передаче неуправляемого олицетворения между асинхронными точками см. в разделе [\<алвайсфловимперсонатионполици > element](alwaysflowimpersonationpolicy-element.md).  
  
 Это поведение по умолчанию можно изменить двумя способами.  
  
1. В управляемом коде на основе каждого потока.  
  
     Можно подавить поток на основе каждого потока, изменив параметры <xref:System.Threading.ExecutionContext> и <xref:System.Security.SecurityContext> с помощью метода <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> или <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType>.  
  
2. В вызове неуправляемого интерфейса размещения для загрузки среды CLR.  
  
     Если для загрузки среды CLR используется неуправляемый интерфейс размещения (вместо простого управляемого исполняемого файла), можно указать специальный флаг в вызове функции [функции CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) . Чтобы включить режим совместимости для всего процесса, задайте для параметра `flags` [функции CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) значение STARTUP_LEGACY_IMPERSONATION.  
  
 Дополнительные сведения см. в описании [элемента\<алвайсфловимперсонатионполици >](alwaysflowimpersonationpolicy-element.md).  
  
## <a name="configuration-file"></a>Файл конфигурации  
 В приложении .NET Framework этот элемент можно использовать только в файле конфигурации приложения.  
  
 Для приложения ASP.NET поток олицетворения можно настроить в файле aspnet. config, который находится в папке \<Windows > Каталог \Микрософт.нет\фрамеворк\вкс.КС.кскскскс.  
  
 ASP.NET по умолчанию отключает поток олицетворения в файле aspnet. config, используя следующие параметры конфигурации:  
  
``` xml
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
 В следующем примере показано, как задать устаревшее поведение, которое не пополняет удостоверение Windows в асинхронных точках.  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- [Схема параметров среды выполнения](index.md)
- [Схема файла конфигурации](../index.md)
- [\<Алвайсфловимперсонатионполици > элемент](alwaysflowimpersonationpolicy-element.md)
