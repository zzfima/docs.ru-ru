---
title: Элемент <add> для webRequestModules (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <webRequestModules>, add element
- webRequestModules, add element
- add element, webRequestModules
- <add> element, webRequestModules
ms.assetid: 47ec4adc-f39f-4bcd-8680-1ec21fd26890
ms.openlocfilehash: f4edce948033478aab59a2aff61abadc55a327ce
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155028"
---
# <a name="add-element-for-webrequestmodules-network-settings"></a>\<добавить элемент> для webRequestModules (Настройки сети)
Добавляет пользовательский модуль веб-запроса в приложение.  

[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<добавить>**

## <a name="syntax"></a>Синтаксис  
  
```xml  
<add
  prefix="URI prefix"
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|**Атрибут**|**Описание**|  
|-------------------|---------------------|  
|`prefix`|Префикс URI для запросов, обрабатываемых этим модулем веб-запросов.|  
|`type`|Полностью квалифицированное имя <xref:System.Type.FullName%2A> типа (указано свойством) <xref:System.Reflection.Assembly.FullName%2A> и имя сборки (указанное свойством), разделенное запятой, которая реализует этот модуль веб-запроса.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[webRequestModules](webrequestmodules-element-network-settings.md)|Определяет модули для использования для запроса информации у сетевых хостов.|  
  
## <a name="remarks"></a>Remarks  
 Атрибут `prefix` определяет префикс URI, который использует указанный модуль веб-запроса. Модули веб-запросов обычно регистрируются для обработки определенного протокола, например HTTP или FTP, но могут быть зарегистрированы для обработки запроса на конкретный сервер или путь на сервере.  
  
 Модуль веб-запроса создается, когда приставка <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> URI, соответствующая, передается методу.  
  
 Значение атрибута `prefix` должно быть ведущими символами действительного URI. Например, `http` или `http://www.contoso.com`.
  
 Значение для `type` атрибута должно быть действительным именем типа и соответствующим именем сборки, разделенным запятой.
  
## <a name="configuration-files"></a>Файлы конфигурации  
 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="example"></a>Пример  
 В следующем примере регистрируется пользовательский модуль веб-запросов для HTTP. Необходимо заменить значения для версии и PublicKeyToken правильными значениями для указанного модуля.  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Net.WebRequest>
- [Схема настройки сети](index.md)
