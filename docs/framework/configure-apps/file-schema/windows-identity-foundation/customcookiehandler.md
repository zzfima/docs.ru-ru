---
title: "&lt;customCookieHandler&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 6
---
# &lt;customCookieHandler&gt;
Задает тип обработчика пользовательского файла cookie.  Этот элемент может быть представлен, только если `mode` атрибута `<cookieHandler>` элемент является «Пользовательский».  Пользовательский тип должен быть производным от <xref:System.IdentityModel.Services.CookieHandler> класса.  
  
## Синтаксис  
  
```  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode=”Custom”>  
      <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" >  
      </customCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние элементы и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|type|Задает пользовательский тип, производный от <xref:System.IdentityModel.Services.CookieHandler> класса.  Дополнительные сведения об указании `type` атрибута см [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_CustomTypeReferences).|  
  
### Дочерние элементы  
 None  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<cookieHandler\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|Настройка <xref:System.IdentityModel.Services.CookieHandler> , <xref:System.IdentityModel.Services.SessionAuthenticationModule> используется для чтения и записи файлов cookie.|  
  
## Заметки  
 При указании обработчика пользовательского файла cookie, установив `mode` атрибута `<cookieHandler>` элемент «Custom», необходимо указать тип обработчика пользовательского файла cookie, включая `<customCookieHandler>` дочерний элемент, который ссылается на тип обработчика файлов cookie.  Этот элемент не может быть указан при `mode` значение атрибута «Chunked» или «По умолчанию».  Обработчики пользовательских файлов cookie должен быть производным от <xref:System.IdentityModel.Services.CookieHandler> класса.  
  
 `<customCookieHandler>` Представленного элементом <xref:System.IdentityModel.Configuration.CustomTypeElement> класса.  
  
## Пример  
 В следующем примере настраивается SAM использовать обработчик пользовательского файла cookie типа `MyNamespace.MyCustomCookieHandler`.  
  
```  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## См. также  
 <xref:System.IdentityModel.Services.CookieHandler>