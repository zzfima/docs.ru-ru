---
title: Элемент <remove> для connectionManagement (параметры сети)
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
ms.openlocfilehash: 39ce85c3c15a2d4bdfce801a35e9ca088bd5091b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154742"
---
# <a name="remove-element-for-connectionmanagement-network-settings"></a>\<удалить элемент> для управления подключением (Настройки сети)
Удаляет IP-адрес или имя DNS из списка управления подключением.  

[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<подключениеУправление>**](connectionmanagement-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<удалить>**

## <a name="syntax"></a>Синтаксис  
  
```xml  
<remove
  address="server name or IP address"
/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|**Атрибут**|**Описание**|  
|-------------------|---------------------|  
|`address`|IP-адрес или имя DNS.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[connectionManagement](connectionmanagement-element-network-settings.md)|Задает максимальное число подключений к сетевому узлу.|  
  
## <a name="remarks"></a>Remarks  
 Элемент `remove` удаляет запись списка управления подключением для указанного сервера.  
  
 Значение атрибута `address` должно быть действительным IP-адресом или именем хоста.  
  
## <a name="configuration-files"></a>Файлы конфигурации  
 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="example"></a>Пример  
 Следующий пример удаляет любые записи списка `www.adventure-works.com` управления подключением для сервера, а `www.contoso.com` затем настраивает приложение на использование четырех подключений к серверу и двух подключений ко всем другим серверам.  
  
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
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [Схема настройки сети](index.md)
