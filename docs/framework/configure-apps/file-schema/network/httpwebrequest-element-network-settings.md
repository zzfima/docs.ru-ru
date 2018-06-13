---
title: '&lt;httpWebRequest&gt; элемент (параметры сети)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/httpWebRequest
- http://schemas.microsoft.com/.NetConfiguration/v2.0#httpWebRequest
helpviewer_keywords:
- <httpWebRequest> element
- httpWebRequest element
ms.assetid: 52acd9d2-5bdc-4dc4-9c2a-f0a476ccbb31
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 1d1dce38e5188824ba1412d3f2a285bd2304f147
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32741972"
---
# <a name="lthttpwebrequestgt-element-network-settings"></a>&lt;httpWebRequest&gt; элемент (параметры сети)
Настраивает параметры веб-запроса.  
  
 \<configuration>  
\<System.NET >  
\<Параметры >  
\<httpWebRequest >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))|**Описание**|  
|-------------------|---------------------|  
|`maximumResponseHeadersLength`|Указывает максимальную длину заголовка ответа, в килобайтах. Значение по умолчанию — 64. Значение -1 указывает, что отсутствие ограничений размера накладывается на заголовки ответа.|  
|`maximumErrorResponseLength`|Указывает максимальную длину ответа об ошибке, в килобайтах. Значение по умолчанию — 64. Значение -1 указывает, что отсутствие ограничений размера накладывается на ответ на ошибку.|  
|`maximumUnauthorizedUploadLength`|Указывает максимальный объем данных, передаваемых в ответ на код ошибки доступа, в байтах. Значение по умолчанию — -1. Значение -1 указывает, что отсутствие ограничений размера накладывается на отправку.|  
|`useUnsafeHeaderParsing`|Указывает, включен ли разбор небезопасных заголовков. Значение по умолчанию — `false`.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[Параметры](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Настраивает основные параметры сети для пространства имен <xref:System.Net>.|  
  
## <a name="remarks"></a>Примечания  
 По умолчанию платформа .NET Framework обеспечивает строго RFC 2616 для синтаксического анализа URI. Некоторые ответы сервера могут содержать управляющие символы в запрещенных полях, которые могут вызвать <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> метод выдает исключение <xref:System.Net.WebException>. Если **useUnsafeHeaderParsing** равно **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> не возникнет, при этом, однако, приложение будет уязвимо для некоторых форм атак на разбор URI. Наилучшим решением является изменение сервера, чтобы ответ не содержать управляющие символы.  
  
## <a name="configuration-files"></a>Файлы конфигурации  
 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как задать большую чем обычно длину заголовка.  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <httpWebRequest  
        maximumResponseHeadersLength="128"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>  
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
