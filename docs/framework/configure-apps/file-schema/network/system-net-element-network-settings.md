---
title: Элемент <system.Net> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.Net
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.Net
helpviewer_keywords:
- system.Net element
- <system.Net> element
ms.assetid: 52de4d6c-b24d-44aa-ba7d-6b5061f1357e
ms.openlocfilehash: 88098f2afaad9728e38c4f9935b45f45826a0ca9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154560"
---
# <a name="systemnet-element-network-settings"></a>Элемент \<system.Net> (сетевые параметры)
Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.  
  
[**\<конфигурация>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.net>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.net>
</system.net>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Нет.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[authenticationModules](authenticationmodules-element-network-settings.md)|Определяет модули, используемые для проверки подлинности запросов в Интернете.|  
|[connectionManagement](connectionmanagement-element-network-settings.md)|Определяет максимальное количество подключений к интернет-хостам.|  
|[defaultProxy](defaultproxy-element-network-settings.md)|Настраивает прокси-сервер протокола передачи гипертекста (HTTP).|  
|[mailSettings](mailsettings-element-network-settings.md)|Настраивает опции отправки почты Simple Mail Transport Protocol (SMTP).|  
|[requestCaching](requestcaching-element-network-settings.md)|Контролирует механизм кэширования для сетевых запросов.|  
|[настройки](settings-element-network-settings.md)|Настраивает основные сетевые <xref:System.Net> параметры для классов в и связанных с ними областях имен детей.|  
|[webRequestModules](webrequestmodules-element-network-settings.md)|Определяет модули для использования для запроса информации у интернет-хостов.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[Конфигурация](../configuration-element.md)|Содержит настройки для всех областей имен.|  
  
## <a name="remarks"></a>Remarks  
 Элемент [ \<system.net>](system-net-element-network-settings.md) содержит настройки <xref:System.Net> для классов в и связанных с ними областях имен ребенка. Настройки настраивают модули аутентификации, управление подключением, настройки почты, прокси-сервер и модули запросов Интернета для получения информации от интернет-хостов.  
  
## <a name="example"></a>Пример  
 В следующем примере показана <xref:System.Net> типичная конфигурация, используемая классами.  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type="System.Net.DigestClient" />  
      <add type="System.Net.NegotiateClient" />  
      <add type="System.Net.KerberosClient" />  
      <add type="System.Net.NtlmClient" />  
      <add type="System.Net.BasicClient" />  
    </authenticationModules>  
    <connectionManagement>  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="https"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="file"  
           type="System.Net.FileWebRequestCreator"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также раздел

- [Схема настройки сети](index.md)
