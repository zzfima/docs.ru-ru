---
title: <filter> Элемент для <add> для <listeners> для <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#filter
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- <filter> element for <add> for <listeners> for <source>
- filter element for <add> for <listeners> for <source>
ms.assetid: 15808b80-4579-4c25-b385-178cfdf154ba
ms.openlocfilehash: 3abfd0bdd40f98a9e4774677fc2cd5068c14333f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186736"
---
# <a name="filter-element-for-add-for-listeners-for-source"></a>\<Фильтр > элемент для \<Добавить > для \<прослушиватели > для \<источника >
Добавляет фильтр к прослушивателю в коллекции `Listeners` для источника трассировки.  
  
 \<configuration>  
\<system.diagnostics>  
\<источники >  
\<Источник >  
\<прослушиватели >  
\<add>  
\<Фильтр >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`type`|Обязательный атрибут.<br /><br /> Указывает тип фильтра, который должен быть производным от <xref:System.Diagnostics.TraceFilter> класса. Можно использовать имя с указанием пространства имен типа, который соответствует типу <xref:System.Type.FullName%2A> свойство, или можно использовать полное имя, включая сведения о сборке, которая соответствует <xref:System.Type.AssemblyQualifiedName%2A> свойство. Сведения о полных имен типов, см. в разделе [Указание полных имен типов](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Необязательный атрибут.<br /><br /> Строка, передаваемая в конструктор для заданного класса фильтра.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.|  
|`sources`|Содержит источники трассировки, которые инициируют сообщения трассировки.|  
|`source`|Содержит источник трассировки, который инициирует сообщения трассировки.|  
|`listeners`|Содержит прослушиватели, сбора, хранения и маршрутизации сообщений. Прослушиватели направляют выходные данные трассировки соответствующему целевому объекту.|  
|`add`|Добавляет прослушиватель в коллекцию `Listeners` для источника трассировки.|  
  
## <a name="remarks"></a>Примечания  
 `<filter>` Элемент должен быть включен в `<add>` элемент прослушиватель трассировки источника, который указывает тип прослушивателя, не только имя прослушивателя, определенное в [ \<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md). Если прослушиватель определен в [ \<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md), фильтр для этого прослушивателя, должен быть определен в этом элементе.  
  
 Этот элемент может использоваться в файле конфигурации компьютера (Machine.config) и файле конфигурации приложения.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать `<filter>` элемент, чтобы добавить фильтр к прослушивателю `console` в `Listeners` коллекции для источника трассировки `myTraceSource`, указывающие уровень фильтра событий как `Error`.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" switchName="SourceSwitch"   
        switchType="System.Diagnostics.SourceSwitch"  >  
        <listeners>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener" >  
            <filter type="System.Diagnostics.EventTypeFilter"   
              initializeData="Error" />  
          </add>  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="SourceSwitch" value="Warning" />  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [Схема параметров трассировки и отладки](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
