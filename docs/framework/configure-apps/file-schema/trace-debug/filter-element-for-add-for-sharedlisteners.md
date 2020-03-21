---
title: <filter>Элемент <add> для<sharedListeners>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add/filter
helpviewer_keywords:
- filter element for <add> for <sharedListeners>
- initializeData attribute
- <filter> element for <add> for <sharedListeners>
- filters, trace listeners
- trace listeners, filters
ms.assetid: 7d4e7faa-2e4e-4379-ac76-f6cd7f2f8fac
ms.openlocfilehash: 6fb52cdfa5792ab6059b60d8dbb91c107cd666ca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153457"
---
# <a name="filter-element-for-add-for-sharedlisteners"></a>\<фильтр> \<элемент амва для добавления> для \<> общей слушателей
Добавляет фильтр к прослушивателю в коллекции `sharedListeners`.  

[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<общиеслушатели>**](sharedlisteners-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<добавить>**](add-element-for-sharedlisteners.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<фильтр>**

## <a name="syntax"></a>Синтаксис  
  
```xml  
<filter type="System.Diagnostics.EventTypeFilter"
  initializeData="Warning" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|attribute|Описание|  
|---------------|-----------------|  
|**тип**|Обязательный атрибут.<br /><br /> Определяет тип фильтра. Вы можете использовать только полное имя типа (в формате <xref:System.Type.FullName%2A?displayProperty=nameWithType> свойства), или вы можете использовать полностью квалифицированное имя типа, включая информацию о сборке (в формате <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> свойства). Для получения информации о создании полностью квалифицированного имени типа [см.](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)|  
|**инициализацияДанны**|Необязательный атрибут.<br /><br /> Строка перешла к конструктору для указанного класса.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.|  
|`sharedListeners`|Коллекция слушателей, на которую может ссылаться любой источник или элемент микро- информации.|  
|`add`|Добавляет слушателя в коллекцию **sharedListeners.**|  
  
## <a name="remarks"></a>Remarks  
 Если слушатель определен в `<add>` элементе `<sharedListeners>` элемента, фильтр для этого слушателя `<filter>` должен быть определен `<add>` в элементе, который является ребенком элемента.  
  
 Этот элемент может быть использован в файле конфигурации машины (Machine.config) и файле конфигурации приложения.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать `<filter>` элемент для `console` добавления фильтра к слушателю трассировки в коллекции. `sharedListeners`  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" >  
        <listeners>  
          <add name="console" />  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="console"
        type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"
          initializeData="Error" />  
      </add>  
    </sharedListeners>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Diagnostics.TraceFilter>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceSource>
- [Схема настроек трассировки и отпараги](index.md)
