---
title: <remove>Элемент для <listeners> для<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
ms.openlocfilehash: edd27dd262004aead7db4d81db8ecab0e831dac1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926997"
---
# <a name="remove-element-for-listeners-for-source"></a>\<Удаление > элемента для \<прослушивателей, \<> для исходного >
Удаляет прослушиватель из коллекции `Listeners` для источника трассировки.  
  
 \<configuration>  
\<> System. Diagnostics  
\<источники >  
\<исходный >  
\<прослушиватели >  
\<Удалить >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`name`|Обязательный атрибут.<br /><br /> Имя прослушивателя, который необходимо удалить из `Listeners` коллекции.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.|  
|`sources`|Содержит источники трассировки, которые инициируют сообщения трассировки.|  
|`source`|Содержит источник трассировки, который инициирует сообщения трассировки.|  
|`listeners`|Указывает прослушиватели, собирающие, хранящие и направляющие сообщения.|  
  
## <a name="remarks"></a>Примечания  
 Элемент удаляет указанный прослушиватель `Listeners` из коллекции для источника трассировки. `<remove>`  
  
 Можно удалить элемент `Listeners` из коллекции для источника трассировки программным путем, <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> вызвав метод <xref:System.Diagnostics.TraceSource> для <xref:System.Diagnostics.TraceSource.Listeners%2A> свойства экземпляра.  
  
 Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.  
  
## <a name="example"></a>Пример  
 В следующем примере `<remove>` показано, как использовать элемент перед `<add>` использованием элемента, чтобы `Listeners` добавить прослушиватель `console` в коллекцию для источника `TraceSourceApp`трассировки.  
  
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

- <xref:System.Diagnostics.TraceSource.Listeners%2A>
- <xref:System.Diagnostics.TraceSource>
- [Схема параметров трассировки и отладки](index.md)
- [\<clear>](clear-element-for-listeners-for-source.md)
- [Прослушиватели трассировки](../../../debug-trace-profile/trace-listeners.md)
