---
title: '&lt;webRequestModules&gt; элемент (параметры сети)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webRequestModules
helpviewer_keywords:
- webRequestModules element
- <webRequestModules> element
ms.assetid: 1263de11-3e0a-4f94-97c9-710b2ae53817
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 7454099d8af0f2d656296be55677c648cc0c36c9
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltwebrequestmodulesgt-element-network-settings"></a>&lt;webRequestModules&gt; элемент (параметры сети)
Задает модули, используемые для запроса данных от сетевых узлов.  
  
 \<configuration>  
\<System.NET >  
\<webRequestModules >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<webRequestModules>   
</webRequestModules>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[add](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-webrequestmodules-network-settings.md)|Добавляет в приложение пользовательский модуль веб-запросов.|  
|[clear](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-webrequestmodules-network-settings.md)|Удаляет все зарегистрированные модули веб-запросов из приложения.|  
|[remove](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-webrequestmodules-network-settings.md)|Удаляет пользовательский модуль веб-запросов из приложения.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[System.NET](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.|  
  
## <a name="remarks"></a>Примечания  
 Элемент `webRequestModules` регистрирует потомки класса <xref:System.Net.WebRequest>, чтобы обработать запросы информации к сетевым узлам. Модули веб-запросов необходимо реализовать <xref:System.Net.IWebRequestCreate> интерфейса.  
  
 Платформа .NET Framework включает модули веб-запросов для URI, который начинается с http://, https:// и file://. Модули по умолчанию можно переопределить только зарегистрировав пользовательский модуль в файле конфигурации.  
  
## <a name="configuration-files"></a>Файлы конфигурации  
 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="example"></a>Пример  
 В следующем примере регистрируется модуль HTTP по умолчанию. Следует заменить значения для Version и PublicKeyToken правильные значения для указанного модуля.  
  
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
 <xref:System.Net.WebRequest>  
 <xref:System.Net.IWebRequestCreate>  
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
