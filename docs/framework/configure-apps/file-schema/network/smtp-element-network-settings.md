---
title: "&lt;SMTP&gt; элемент (параметры сети)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp
- http://schemas.microsoft.com/.NetConfiguration/v2.0#smtp
helpviewer_keywords:
- <smtp> element
- smtp element
ms.assetid: 220b0329-e384-4e0c-86b4-0945ad17efd9
caps.latest.revision: 
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: f5b2a3b7eec17fbdd12181c29f610d2b2ad32bd4
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2018
---
# <a name="ltsmtpgt-element-network-settings"></a>&lt;SMTP&gt; элемент (параметры сети)
Настраивает формат доставки инструкций, метод доставки и адрес отправителя для отправки сообщений электронной почты.  
  
 \<configuration>  
\<system.net>  
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
|`deliveryFormat`|Указывает формат доставки для исходящих сообщений электронной почты. Допустимые значения: SevenBit и International.|  
|`deliveryMethod`|Указывает способ доставки сообщений электронной почты. Допустимые значения: сеть, pickupDirectoryFromIis и specifiedPickupDirectory.|  
|`from`|Указывает адрес отправителя для исходящих сообщений электронной почты.|  
  
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
 Следующий пример указывает соответствующие параметры SMTP для отправки электронной почты, используя сетевые учетные данные по умолчанию.  
  
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
