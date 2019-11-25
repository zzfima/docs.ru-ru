---
title: Элемент <source>
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
ms.openlocfilehash: b59144f4772c940f8c7e6ca19aa21666069b4b55
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088830"
---
# <a name="source-element"></a>\<исходный > элемент
Содержит источник трассировки, который инициирует сообщения трассировки.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. diagnostics >** ](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<sources >** ](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**source >**

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
|`switchName`|Необязательный атрибут.<br /><br /> Задает имя экземпляра переключателя трассировки в приложении. Если параметр не определен в элементе `<switches>`, значение указывает уровень для переключателя.|  
|`switchType`|Необязательный атрибут.<br /><br /> Указывает тип переключателя трассировки. При наличии тип должен быть допустимым именем класса и не может быть пустой строкой.|  
|`extraAttribute`|Необязательный атрибут.<br /><br /> Задает значение для атрибута, зависящего от источника трассировки, определяемого методом <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> для этого источника трассировки.|  
  
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
  
## <a name="remarks"></a>Заметки  
 Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать элемент `<source>`, чтобы добавить источник трассировки `mySource` и задать уровень для коммутатора источника с именем `sourceSwitch`. Добавляется прослушиватель трассировки консоли, который записывает данные трассировки на консоль.  
  
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
