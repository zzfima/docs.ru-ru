---
title: Элемент <specifiedPickupDirectory> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#specifiedPickupDirectory
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/specifiedPickupDirectory
helpviewer_keywords:
- specifiedPickupDirectory element
- <specifiedPickupDirectory> element
ms.assetid: 0121f49d-bff2-4bc6-af06-f1628dcd61f1
ms.openlocfilehash: 6abee1b01e690633dabfd225b30fcb9b8b408dad
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55270827"
---
# <a name="specifiedpickupdirectory-element-network-settings"></a>\<specifiedPickupDirectory > (сетевые параметры)
Настраивает локальный каталог для сервера транспортного протокола SMTP (Simple Mail).  
  
 \<configuration>  
\<system.net>  
\<mailSettings >  
\<SMTP >  
\<specifiedPickupDirectory >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"   
/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|Каталог, в которой приложения сохраняют сообщения электронной почты для последующей обработки SMTP-сервером.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<SMTP > (сетевые параметры)](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|Настраивает параметры отправки сообщений транспортного протокола SMTP (Simple Mail).|  
  
## <a name="remarks"></a>Примечания  
 Атрибут `specifiedPickupDirectory` задает каталог, в который приложения сохраняют сообщения электронной почты для их последующей обработки SMTP-сервером.  
  
## <a name="example"></a>Пример  
 Следующий пример определяет c:\maildrop как каталог раскладки почты.  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="SpecifiedPickupDirectory">  
        <specifiedPickupDirectory  
          pickupDirectoryLocation="c:\maildrop"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
