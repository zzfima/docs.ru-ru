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
ms.openlocfilehash: f99c5b0dc7eab57d4e3e86f49dbbb3228c7b7d8b
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664221"
---
# <a name="add-element-for-webrequestmodules-network-settings"></a>\<Добавление элемента > для webRequestModules (параметры сети)
Добавляет пользовательский модуль веб-запросов в приложение.  
  
 \<configuration>  
\<> System. NET  
\<webRequestModules >  
\<add>  
  
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
  
|**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))|**Описание**|  
|-------------------|---------------------|  
|`prefix`|Префикс URI для запросов, обрабатываемых этим модулем веб-запросов.|  
|`type`|Полное имя типа (обозначенное <xref:System.Type.FullName%2A> свойством) и имя сборки (обозначенное <xref:System.Reflection.Assembly.FullName%2A> свойством), разделенные запятыми, которые реализуют этот модуль веб-запросов.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[webRequestModules](webrequestmodules-element-network-settings.md)|Указывает модули, используемые для запроса сведений от сетевых узлов.|  
  
## <a name="remarks"></a>Примечания  
 `prefix` Атрибут определяет префикс URI, который использует указанный модуль веб-запросов. Модули веб-запросов обычно регистрируются для работы с конкретным протоколом, например HTTP или FTP, но могут быть зарегистрированы, чтобы обрабатывать запросы к определенному серверу или пути на сервере.  
  
 Модуль веб-запросов создается, когда в <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> метод передается соответствующий префикс URI.  
  
 Значение `prefix` атрибута должно быть начальными символами допустимого URI. Например, `http` или `http://www.contoso.com`.
  
 Значением `type` атрибута должно быть допустимое имя типа и соответствующее имя сборки, разделенные запятыми.
  
## <a name="configuration-files"></a>Файлы конфигурации  
 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="example"></a>Пример  
 В следующем примере регистрируется пользовательский модуль веб-запросов для HTTP. Необходимо заменить значения для Version и PublicKeyToken правильными значениями для указанного модуля.  
  
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
  
## <a name="see-also"></a>См. также

- <xref:System.Net.WebRequest>
- [Схема параметров сети](index.md)
