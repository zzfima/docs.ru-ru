---
title: "&lt;mailSettings&gt; элемент (параметры сети)"
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mailSettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings
helpviewer_keywords:
- mailSettings element
- <mailSettings> element
ms.assetid: 54f0f153-17e5-4f49-afdc-deadb940c9c1
caps.latest.revision: 
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: ce7ec8bea57436ebd184cf0d593870999405f72f
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2018
---
# <a name="ltmailsettingsgt-element-network-settings"></a>&lt;mailSettings&gt; элемент (параметры сети)
Настраивает параметры отправки сообщений.  

\<configuration>  
\<system.net>  
\<mailSettings >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<mailSettings>
  <smtp> … </smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Атрибут|Описание:|  
|---------------|-----------------|  
|[\<SMTP > Element (Network Settings)](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|Настраивает параметры простой протокол передачи почты.|  
  
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
      <smtp deliveryMethod="network">  
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
 <xref:System.Net.Mail.SmtpClient>  
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
