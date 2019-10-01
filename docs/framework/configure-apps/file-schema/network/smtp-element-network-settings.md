---
title: Элемент <smtp> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp
- http://schemas.microsoft.com/.NetConfiguration/v2.0#smtp
helpviewer_keywords:
- <smtp> element
- smtp element
ms.assetid: 220b0329-e384-4e0c-86b4-0945ad17efd9
ms.openlocfilehash: 2105a6dd25a7f6e5e4c1ce286be7f60beae1dca0
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697612"
---
# <a name="smtp-element-network-settings"></a>Элемент > @no__t 0smtp (параметры сети)
Настраивает формат доставки, метод доставки и адрес отправителя для отправки сообщений электронной почты.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp; @ no__t-1[ **@no__t -4system. NET >** ](system-net-element-network-settings.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<mailSettings >** ](mailsettings-element-network-settings.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<smtp >**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<smtp  
  deliveryFormat="format"  
  deliveryMethod="method"  
  from="from address">
    <specifiedPickupDirectory>...</specifiedPickupDirectory>  
    <network>...</network>  
</smtp>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`deliveryFormat`|Указывает формат доставки исходящих сообщений электронной почты. Допустимые значения: SevenBit и International.|  
|`deliveryMethod`|Указывает метод доставки сообщений электронной почты. Допустимые значения: Network, Пиккупдиректорифромиис и СпеЦифиедпиккупдиректори.|  
|`from`|Указывает адрес отсылаемых сообщений электронной почты.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|Настраивает локальный каталог для SMTP-сервера.|  
|`network`|Настраивает параметры сети для внешнего SMTP-сервера.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[Элемент \<mailSettings> (параметры сети)](mailsettings-element-network-settings.md)|Настраивает параметры отправки почты.|  
  
## <a name="example"></a>Пример  
 В следующем примере задаются соответствующие параметры SMTP для отправки электронной почты с использованием сетевых учетных данных по умолчанию.  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network" deliveryFormat="SevenBit"  from="ben@contoso.com">  
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

- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpDeliveryFormat>
- <xref:System.Net.Mail.SmtpDeliveryMethod>
- [Схема параметров сети](index.md)
