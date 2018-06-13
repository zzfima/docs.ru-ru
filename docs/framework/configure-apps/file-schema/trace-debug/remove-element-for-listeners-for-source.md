---
title: '&lt;Удалить&gt; элемент для &lt;прослушиватели&gt; для &lt;источника&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: cc6772e7a9b98f09df21fd1acf24f578b66ae51e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32754279"
---
# <a name="ltremovegt-element-for-ltlistenersgt-for-ltsourcegt"></a>&lt;Удалить&gt; элемент для &lt;прослушиватели&gt; для &lt;источника&gt;
Удаляет прослушиватель из коллекции `Listeners` для источника трассировки.  
  
 \<configuration>  
\<System.Diagnostics >  
\<источники >  
\<Источник >  
\<прослушиватели >  
\<Удалите >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`name`|Обязательный атрибут.<br /><br /> Имя прослушивателя для удаления из `Listeners` коллекции.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.|  
|`sources`|Содержит источники трассировки, которые инициируют сообщения трассировки.|  
|`source`|Содержит источник трассировки, который инициирует сообщения трассировки.|  
|`listeners`|Задает прослушиватели для сбора, хранения и маршрутизации сообщений.|  
  
## <a name="remarks"></a>Примечания  
 `<remove>` Элемент Удаляет заданный прослушиватель из `Listeners` коллекции для источника трассировки.  
  
 Можно удалить элемент из `Listeners` коллекции для источника трассировки программно, вызвав <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> метод <xref:System.Diagnostics.TraceSource.Listeners%2A> свойство <xref:System.Diagnostics.TraceSource> экземпляра.  
  
 Этот элемент может использоваться в файле конфигурации компьютера (Machine.config) и файл конфигурации приложения.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать `<remove>` элемент перед использованием `<add>` элемент для добавления прослушивателя `console` для `Listeners` коллекции для источника трассировки `TraceSourceApp`.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"   
         switchType="System.Diagnostics.SourceSwitch" >  
         <listeners>  
           <remove name="Default"/>  
           <add name="console"   
             type="System.Diagnostics.ConsoleTraceListener" />  
         </listeners>  
      </source>  
    </sources>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Diagnostics.TraceSource.Listeners%2A>  
 <xref:System.Diagnostics.TraceSource>  
 [Схема параметров трассировки и отладки](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [\<clear>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-source.md)  
 [Прослушиватели трассировки](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
