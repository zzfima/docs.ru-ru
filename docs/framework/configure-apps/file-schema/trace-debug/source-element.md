---
title: Элемент <source>
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
ms.openlocfilehash: 55120e292ac2a2c822c5510563d1aa167ca921e4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920453"
---
# <a name="source-element"></a>\<Элемент Source >
Содержит источник трассировки, который инициирует сообщения трассировки.  
  
 \<configuration>  
\<> System. Diagnostics  
\<источники >  
\<исходный >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<source>   
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`name`|Необязательный атрибут.<br /><br /> Задает имя источника трассировки.|  
|`switchName`|Необязательный атрибут.<br /><br /> Задает имя экземпляра переключателя трассировки в приложении. Если параметр не определен в `<switches>` элементе, значение указывает уровень для переключателя.|  
|`switchType`|Необязательный атрибут.<br /><br /> Указывает тип переключателя трассировки. При наличии тип должен быть допустимым именем класса и не может быть пустой строкой.|  
|`extraAttribute`|Необязательный атрибут.<br /><br /> Задает значение для атрибута, зависящего от источника трассировки, определяемого <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> методом для этого источника трассировки.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<listeners>](listeners-element-for-source.md)|Содержит прослушиватели, собирающие, сохраняющие и направляющие сообщения.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.|  
|`sources`|Содержит источники трассировки, которые инициируют сообщения трассировки.|  
  
## <a name="remarks"></a>Примечания  
 Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как с помощью `<source>` элемента добавить источник `mySource` трассировки и задать уровень для коммутатора источника с именем `sourceSwitch`. Добавляется прослушиватель трассировки консоли, который записывает данные трассировки на консоль.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch" switchType="System.Diagnostics.SourceSwitch"  >  
        <listeners>  
          <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
            <filter type="System.Diagnostics.EventTypeFilter" initializeData="Error" />  
          </add>  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
        <switches>  
           <add name="sourceSwitch" value="Warning" />  
        </switches>    
  </system.diagnostics>   
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- [Схема параметров трассировки и отладки](index.md)
- [Переключатели трассировки](../../../debug-trace-profile/trace-switches.md)
