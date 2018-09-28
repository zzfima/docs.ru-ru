---
title: '&lt;Удалить&gt; элемент для connectionManagement (параметры сети)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- connectionManagement, remove element
- <remove> element, connectionManagement
- <connectionManagement>, remove element
- remove element, connectionManagement
ms.assetid: 94b81775-5a22-4975-8c47-8620c40c3f35
author: mcleblanc
ms.author: markl
ms.openlocfilehash: d249cc412a1638e62b57b4976adc23fdf8f36e80
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2018
ms.locfileid: "47425801"
---
# <a name="ltremovegt-element-for-connectionmanagement-network-settings"></a>&lt;Удалить&gt; элемент для connectionManagement (параметры сети)
Удаляет IP-адрес или DNS-имя из списка управления подключениями.  
  
 \<configuration>  
\<System.NET >  
\<connectionManagement >  
\<Удалить >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<remove   
  address="server name or IP address"   
/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))|**Описание**|  
|-------------------|---------------------|  
|`address`|IP-адрес или DNS-имя.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[connectionManagement](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|Задает максимальное число подключений к сетевому узлу.|  
  
## <a name="remarks"></a>Примечания  
 `remove` Элемент удаляет запись списка управления подключением для указанного сервера.  
  
 Значение `address` атрибут должен быть допустимым IP-адресом или именем.  
  
## <a name="configuration-files"></a>Файлы конфигурации  
 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="example"></a>Пример  
 В следующем примере удаляет все записи списка управления подключением www.adventure-works.com сервера и затем настраивает приложение для использования четырех подключений к серверу www.contoso.com и двух подключений ко всем остальным серверам.  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <remove address="http://www.adventure-works.com" />  
      <add address="http://www.contoso.com" maxconnection="4" />  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Net.ServicePoint>  
 <xref:System.Net.ServicePointManager>  
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
