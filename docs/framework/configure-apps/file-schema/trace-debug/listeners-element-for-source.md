---
title: Элемент <listeners> для <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners
helpviewer_keywords:
- listeners element for <source>
- <listeners> element for <source>
ms.assetid: a2991f43-b4d3-4614-a8e7-da392de9697f
ms.openlocfilehash: 853bc94978218fd4d426e6070b3a36e20435cd6d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920495"
---
# <a name="listeners-element-for-source"></a>\<Listeners > элемент \<для исходного >
Добавляет или удаляет прослушиватели в <xref:System.Diagnostics.TraceSource.Listeners%2A> коллекции <xref:System.Diagnostics.TraceSource>для. Прослушиватель направляет выходные данные трассировки в соответствующий целевой объект, например журнал, окно или текстовый файл.  
  
 \<configuration>  
\<> System. Diagnostics  
\<источники >  
\<исходный >  
\<Listeners > элемент  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<listeners>   
  <add>...</add>  
  <remove ... />  
  <clear/>  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Нет.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<add>](add-element-for-listeners-for-source.md)|Добавляет прослушиватель в коллекцию `Listeners`.|  
|[\<remove>](remove-element-for-listeners-for-source.md)|Удаляет прослушиватель из `Listeners` коллекции.|  
|[\<clear>](clear-element-for-listeners-for-source.md)|Очищает коллекцию `Listeners` для источника трассировки.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.|  
|`sources`|Содержит источники трассировки, которые инициируют сообщения трассировки.|  
|`source`|Содержит источник трассировки, который инициирует сообщения трассировки.|  
  
## <a name="remarks"></a>Примечания  
  
## <a name="configuration-file"></a>Файл конфигурации  
 Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать `<listeners>` элемент для добавления прослушивателя трассировки консоли `mySource` в источник и для удаления прослушивателя трассировки по умолчанию.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"   
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener">  
            <filter type="System.Diagnostics.EventTypeFilter"   
              initializeData="Error"/>  
          </add>  
          <remove name="Default"/>  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Diagnostics.TraceListener>
- [Схема параметров трассировки и отладки](index.md)
- [Прослушиватели трассировки](../../../debug-trace-profile/trace-listeners.md)
