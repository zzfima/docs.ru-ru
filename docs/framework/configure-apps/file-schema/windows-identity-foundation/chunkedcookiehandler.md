---
title: '&lt;chunkedCookieHandler&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
caps.latest.revision: "5"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 906a9e7cafca14dc4ee13dcb9eb9e59736464fd9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltchunkedcookiehandlergt"></a>&lt;chunkedCookieHandler&gt;
Настраивает <xref:System.IdentityModel.Services.ChunkedCookieHandler>. Этот элемент может быть представлен, только если `mode` атрибут `<cookieHandler>` «Default» или «Фрагментированным».  
  
 \<system.identityModel.services >  
\<federationConfiguration >  
\<cookieHandler >  
\<chunkedCookieHandler >  
  
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
|размер фрагмента данных|Максимальный размер в символах данных файлов cookie HTTP для любого отдельного файла cookie HTTP. Будьте внимательны, чтобы при корректировке размер фрагмента данных. Веб-браузеры имеют различные ограничения на размер файлов cookie и номер, приходящихся на каждый домен. Например, Netscape спецификацию исходных оговорено этих ограничений: 300 файлы cookie всего 4096 байт на заголовке cookie (включая метаданные, не только значение файла cookie) и 20 файлов cookies для каждого домена. Значение по умолчанию — 2000. Обязательный.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<cookieHandler >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|Настраивает <xref:System.IdentityModel.Services.CookieHandler> , <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) используется для чтения и записи файлов cookie.|  
  
## <a name="remarks"></a>Примечания  
 При указании <xref:System.IdentityModel.Services.ChunkedCookieHandler> , установив `mode` атрибут `<cookieHandler>` элемент «Default» или «Chunked» можно указать размер фрагмента данных, используемого обработчиком куки-файл для чтения и записи, включая файлы cookie `<chunkedCookieHandler>` дочерний элемент и Установка его `chunkSize` атрибута. Если `<chunkedCookieHandler>` элемент отсутствует, используется размер блока по умолчанию 2000 байтов. Этот элемент не может быть указано при `mode` атрибута задано значение «Custom».  
  
 `<chunkedCookieHandler>` Представлен <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> класса.  
  
## <a name="example"></a>Пример  
 В следующем примере настраивается обработчик блочный файл cookie, который записывает файлы cookie фрагментами 3000 байт.  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.IdentityModel.Services.ChunkedCookieHandler>
