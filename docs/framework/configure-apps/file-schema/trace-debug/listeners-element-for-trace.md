---
title: Элемент <listeners> для <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners
helpviewer_keywords:
- <listeners> element
- listeners element
ms.assetid: 1394c2c3-6304-46db-87c1-8e8b16f5ad5b
ms.openlocfilehash: fd12be1b775d7611ef3f16d23147470313bf9866
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153377"
---
# <a name="listeners-element-for-trace"></a>\<слушатели> \<Элемент для следа>
Определяет слушателя, который собирает, хранит и направляет сообщения. Слушатели направляют результаты отслеживания на соответствующую цель.  

[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<след>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<слушатели>**

## <a name="syntax"></a>Синтаксис  
  
```xml  
<listeners>
  <add>...</add>  
  <clear/>  
  <remove ... />  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Нет.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<добавить>](add-element-for-listeners-for-trace.md)|Добавляет прослушиватель в коллекцию `Listeners`.|  
|[\<ясно>](clear-element-for-listeners-for-trace.md)|Очищает коллекцию `Listeners` для трассировки.|  
|[\<удалить>](remove-element-for-listeners-for-trace.md)|Удаляет слушателя из `Listeners` коллекции.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`system.diagnostics`|Задает корневой элемент для раздела конфигурации ASP.NET.|  
|`trace`|Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.|  
  
## <a name="remarks"></a>Remarks  
 <xref:System.Diagnostics.Debug> Классы <xref:System.Diagnostics.Trace> и классы имеют одну и ту же коллекцию **Слушателей.** Если вы добавляете объект слушателя в коллекцию в одном из этих классов, другой класс использует тот же самый слушатель. Классы слушателя, поставляемые с помощью <xref:System.Diagnostics.TraceListener> рамочной программы .NET, происходят из класса.  
  
## <a name="configuration-file"></a>Файл конфигурации  
 Этот элемент может быть использован в файле конфигурации машины (Machine.config) и файле конфигурации приложения.  
  
## <a name="example"></a>Пример  
 Ниже приводится следующий пример, как использовать `MyListener` ** \<слушателей>** элемент для добавления слушателей и `MyEventListener` коллекции **Слушателей.** `MyListener`создает вызванный `MyListener.log` файл и записывает вывод в файл. `MyEventListener`создает запись в журнале событий.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="true" indentsize="0">  
      <listeners>  
        <add name="myListener"
          type="System.Diagnostics.TextWriterTraceListener,
            system, version=1.0.3300.0, Culture=neutral,
            PublicKeyToken=b77a5c561934e089"
          initializeData="c:\myListener.log" />  
        <add name="MyEventListener"  
          type="System.Diagnostics.EventLogTraceListener,
            system, version=1.0.3300.0, Culture=neutral,
            PublicKeyToken=b77a5c561934e089"  
          initializeData="MyConfigEventLog"/>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Diagnostics.TraceListener>
- [Схема настроек трассировки и отпараги](index.md)
