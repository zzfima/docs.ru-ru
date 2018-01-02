---
title: "&lt;SMTP&gt; элемент (параметры сети)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp
- http://schemas.microsoft.com/.NetConfiguration/v2.0#smtp
helpviewer_keywords:
- <smtp> element
- smtp element
ms.assetid: 220b0329-e384-4e0c-86b4-0945ad17efd9
caps.latest.revision: "13"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 598fe3dc2a49187e923cd689f863d0a3327e735f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltsmtpgt-element-network-settings"></a>&lt;SMTP&gt; элемент (параметры сети)
Настраивает формат и способ доставки и адрес отправителя для отправки сообщений электронной почты.  
  
 \<configuration>  
\<System.NET >  
\<mailSettings >  
\<SMTP >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
      <smtp  
        deliveryFormat="format"   
        deliveryMethod="method"   
        from="from address">
          <specifiedPickupDirectory> … </ specifiedPickupDirectory >  
          <network> … </network>  
      </smtp>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание:|  
|---------------|-----------------|  
|`deliveryFormat`|Определяет формат доставки для исходящих сообщений электронной почты. Допустимые значения: SevenBit и International.|  
|`deliveryMethod`|Указывает способ доставки сообщений электронной почты. Допустимые значения: сеть, pickupDirectoryFromIis и specifiedPickupDirectory.|  
|`from`|Задает адрес отправителя для исходящих сообщений электронной почты.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Атрибут|Описание:|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|Настраивает локальный каталог для сервера Simple Mail Transport Protocol (SMTP).|  
|`network`|Настройка сетевых параметров для внешнего сервера SMTP.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[Элемент \<mailSettings> (параметры сети)](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|Настраивает параметры отправки сообщений.|  
  
## <a name="example"></a>Пример  
 Следующий пример указывает соответствующие параметры SMTP для отправки электронной почты с помощью сетевые учетные данные по умолчанию.  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="network" deliveryFormat="SevenBit"  from="ben@contoso.com">  
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
 <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpDeliveryFormat>  
 <xref:System.Net.Mail.SmtpDeliveryMethod>  
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
