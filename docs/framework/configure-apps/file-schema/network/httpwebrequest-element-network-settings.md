---
title: "&lt;httpWebRequest&gt; элемент (параметры сети)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/httpWebRequest
- http://schemas.microsoft.com/.NetConfiguration/v2.0#httpWebRequest
helpviewer_keywords:
- <httpWebRequest> element
- httpWebRequest element
ms.assetid: 52acd9d2-5bdc-4dc4-9c2a-f0a476ccbb31
caps.latest.revision: "18"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: dadb2d7635f132b44d6fca8c56f53b847ffb1ff9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
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
