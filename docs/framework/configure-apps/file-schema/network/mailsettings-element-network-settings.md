---
title: '&lt;mailSettings&gt; (сетевые параметры)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mailSettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings
helpviewer_keywords:
- mailSettings element
- <mailSettings> element
ms.assetid: 54f0f153-17e5-4f49-afdc-deadb940c9c1
ms.openlocfilehash: 954755c7576e0ca4dd7946926c77e1e7e18055e5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54713958"
---
# <a name="ltmailsettingsgt-element-network-settings"></a>&lt;mailSettings&gt; (сетевые параметры)
Настраивает параметры отправки сообщений.  

\<configuration>  
\<system.net>  
\<mailSettings >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<mailSettings>
  <smtp>...</smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Атрибут|Описание:|  
|---------------|-----------------|  
|[\<SMTP > (сетевые параметры)](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|Служит для настройки параметров простой протокол транспорта почты.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[Элемент \<system.Net> (сетевые параметры)](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.|  
  
## <a name="example"></a>Пример  
 Следующий пример указывает соответствующие параметры SMTP для отправки электронной почты, используя сетевые учетные данные по умолчанию.  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network">  
        <network  
          host="localhost"  
          port="25"  
          defaultCredentials="true"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также
- <xref:System.Net.Mail.SmtpClient>
- [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
