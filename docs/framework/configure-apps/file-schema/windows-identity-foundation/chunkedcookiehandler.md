---
title: <chunkedCookieHandler>
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
ms.openlocfilehash: d9c81d5de7bea343f0d67fa00037763fbae7b8c5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120787"
---
# <a name="chunkedcookiehandler"></a>\<chunkedCookieHandler>
Настраивает <xref:System.IdentityModel.Services.ChunkedCookieHandler>. Этот элемент может быть представлен, только если `mode` атрибут `<cookieHandler>` элемент является «Default» или шифрование «фрагментированной».  
  
 \<system.identityModel.services>  
\<federationConfiguration>  
\<cookieHandler >  
\<chunkedCookieHandler>  
  
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
|размер фрагмента данных|Максимальный размер в символах данные файла cookie HTTP для любого отдельного файла cookie HTTP. Будьте внимательны, настраивая размер фрагмента данных. Веб-браузеры имеют различные ограничения на размер файлов cookie и номер, приходящихся на каждый домен. Например исходная спецификация Netscape оговорено эти ограничения: Общее 300 файлы cookie, 4096 байт в заголовок файла cookie (включая метаданные, не только значение файла cookie) и 20 файлов cookies для каждого домена. Значение по умолчанию — 2000. Обязательный.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<cookieHandler >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|Настраивает <xref:System.IdentityModel.Services.CookieHandler> , <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) используется для чтения и записи файлов cookie.|  
  
## <a name="remarks"></a>Примечания  
 При указании <xref:System.IdentityModel.Services.ChunkedCookieHandler> , задав `mode` атрибут `<cookieHandler>` элемент «Default» или «Chunked» можно указать размер фрагмента данных, который использует обработчик файлов cookie для чтения и записи файлов cookie, включив `<chunkedCookieHandler>` дочерний элемент и Установка его `chunkSize` атрибута. Если `<chunkedCookieHandler>` элемент отсутствует, используется размер блока по умолчанию 2000 байтов. Этот элемент не может быть указан при `mode` атрибут имеет значение «Custom».  
  
 `<chunkedCookieHandler>` Элемент, представленный объектом <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> класса.  
  
## <a name="example"></a>Пример  
 В следующем примере настраивается фрагментированный обработчик файлов cookie, записывает файлы cookie в виде фрагментов 3000 байтов.  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
