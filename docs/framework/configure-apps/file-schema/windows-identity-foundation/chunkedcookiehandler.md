---
title: "&lt;chunkedCookieHandler&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
caps.latest.revision: 5
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 5
---
# &lt;chunkedCookieHandler&gt;
Настройка <xref:System.IdentityModel.Services.ChunkedCookieHandler>.  Этот элемент может быть представлен, только если `mode` атрибута `<cookieHandler>` является элемент «По умолчанию» или «Поблочного».  
  
## Синтаксис  
  
```  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Chunked||Default" >  
      <chunkedCookieHandler size=xs:int >  
      </chunkedCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние элементы и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|chunkSize|Максимальный размер в символах данных cookie HTTP для любого одного файла cookie HTTP.  Будьте внимательны, настраивая размер фрагмента данных.  Веб\-обозреватели имеют различные ограничения на размер файлов «cookie» и номер, приходящихся на каждый домен.  Например, исходная спецификация Netscape оговорено эти ограничения: 300 cookies всего 4096 байт в заголовке cookie \(включая метаданные, не только значения cookie\) и 20 файлов Сookie с одного домена.  Значение по умолчанию — 2000.  Обязательный.|  
  
### Дочерние элементы  
 None  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<cookieHandler\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|Настройка <xref:System.IdentityModel.Services.CookieHandler> , <xref:System.IdentityModel.Services.SessionAuthenticationModule> \(SAM\) используется для чтения и записи файлов cookie.|  
  
## Заметки  
 При указании <xref:System.IdentityModel.Services.ChunkedCookieHandler> , установив `mode` атрибута `<cookieHandler>` элемент «По умолчанию» или «Chunked» можно задать размер фрагмента данных, обработчик cookie используются для чтения и записи файлов «cookie», включая `<chunkedCookieHandler>` дочернего элемента и значение его `chunkSize` атрибут.  Если `<chunkedCookieHandler>` элемент отсутствует, используется размер блока по умолчанию 2000 байт.  Этот элемент не может быть указан при `mode` атрибут имеет значение «Custom».  
  
 `<chunkedCookieHandler>` Представленного элементом <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> класса.  
  
## Пример  
 В следующем примере настраивается обработчик частям файла cookie, который записывает файлы «cookie» фрагментами 3000 байт.  
  
```  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## См. также  
 <xref:System.IdentityModel.Services.ChunkedCookieHandler>