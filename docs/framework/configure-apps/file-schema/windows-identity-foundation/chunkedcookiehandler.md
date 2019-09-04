---
title: <chunkedCookieHandler>
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
ms.openlocfilehash: 6aad95033b99f1472284f838f3ede2e74ea8324c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252107"
---
# <a name="chunkedcookiehandler"></a>\<Чункедкукиехандлер >
Настраивает <xref:System.IdentityModel.Services.ChunkedCookieHandler>. Этот элемент может присутствовать только в `mode` том случае, если атрибут `<cookieHandler>` элемента имеет значение "default" или "фрагментированный".  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. identityModel. Services**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<federationConfiguration >** ](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Кукиехандлер >** ](cookiehandler.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Чункедкукиехандлер >**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Chunked||Default" >  
      <chunkedCookieHandler size=xs:int >  
      </chunkedCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|chunkSize|Максимальный размер (в символах) данных cookie HTTP для одного файла cookie HTTP. При изменении размера фрагмента данных необходимо соблюдать осторожность. Веб-браузеры имеют разные ограничения на размер файлов cookie и число допустимых для каждого домена. Например, исходная спецификация Netscape заменяет эти ограничения: 300 файлов cookie Total, 4096 байт на каждый заголовок файла cookie (включая метаданные, а не только значение cookie) и 20 файлов cookie на домен. Значение по умолчанию — 2000. Обязательный.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствуют  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Кукиехандлер >](cookiehandler.md)|Настраивает <xref:System.IdentityModel.Services.CookieHandler> <xref:System.IdentityModel.Services.SessionAuthenticationModule> , что (SAM) использует для чтения и записи файлов cookie.|  
  
## <a name="remarks"></a>Примечания  
 При указании <xref:System.IdentityModel.Services.ChunkedCookieHandler> с помощью `mode` присвоения атрибуту `<cookieHandler>` элемента значения "по умолчанию" или "фрагментированного" можно указать размер фрагмента, используемый обработчиком файлов cookie `<chunkedCookieHandler>` для чтения и записи файлов cookie, включая дочерний элемент и `chunkSize` задание атрибута. `<chunkedCookieHandler>` Если элемент отсутствует, используется размер фрагмента по умолчанию (2000 байт). Этот элемент не может быть указан, `mode` если для атрибута задано значение Custom.  
  
 `<chunkedCookieHandler>` Элемент представлен<xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> классом.  
  
## <a name="example"></a>Пример  
 В следующем примере настраивается обработчик фрагментированных файлов cookie, который записывает файлы cookie в фрагменты 3000 байт.  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
