---
title: "&lt;cookieHandler&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bfdc127f-8d94-4566-8bef-f583c6ae7398
caps.latest.revision: 5
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 5
---
# &lt;cookieHandler&gt;
Настройка <xref:System.IdentityModel.Services.CookieHandler> , <xref:System.IdentityModel.Services.SessionAuthenticationModule> \(SAM\) используется для чтения и записи файлов cookie.  
  
## Синтаксис  
  
```  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler name=xs:string  
        path=Path  
        mode="Chunked||Custom||Default"  
        persistentSessionLifetime=xs:string  
        hideFromScript=xs:boolean  
        requireSSL=xs:boolean  
        domain=xs:string  
      <chunkedCookieHandler size=xs:int />  
      <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние элементы и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|имя|Задает базовое имя для файлов cookie, все записи.  Значение по умолчанию — «FedAuth».|  
|путь|Указывает значение пути все файлы cookie записываются.  Значение по умолчанию — «HttpRuntime.AppDomainAppVirtualPath».|  
|mode|Один из <xref:System.IdentityModel.Services.CookieHandlerMode> значения, которое указывает тип обработчика cookie, используемый SAM.  Могут использоваться следующие значения:<br /><br /> -   «По умолчанию», так же, как «Chunked».<br />-   «Поблочного» — используется экземпляр класса <xref:System.IdentityModel.Services.ChunkedCookieHandler> класса.  Этот обработчик файлов cookie обеспечивает отдельных файлов cookie не превышает максимальный размер набора.  Это достигается путем потенциально «фрагментации» один логический файл cookie на количество файлов cookie на проводной.<br />-   «Пользовательские» — используется экземпляр пользовательского класса, производного от <xref:System.IdentityModel.Services.CookieHandler>.  Ссылки на производный класс в `<customCookieHandler>` дочернего элемента.<br /><br /> Значение по умолчанию — «По умолчанию».|  
|persistentSessionLifetime|Задает время жизни постоянные сеансов.  Если значение равно нулю, всегда используются временные сеансы.  Значение по умолчанию — "0:0:0", указывает временный сеанса.  Максимальное значение — «365:0:0», который определяет сеанс 365 дней.  Значения должны быть указаны в соответствии со следующим ограничением: `<xs:pattern value="([0-9.]+:){0,1}([0-9]+:){0,1}[0-9.]+" />`, где слева указывает дни, среднего значения \(если есть\) определяет часы и правое значение \(если есть\) указывает минуты.|  
|requireSsl|Указывает, выдается ли флаг «Безопасно» для любых файлов cookie записываются.  Если это значение задано, файлы «cookie» сеанса входа будет доступна только по протоколу HTTPS.  По умолчанию используется значение «true».|  
|hideFromScript|Определяет, выдается ли флаг «HttpOnly» для любых файлов cookie записываются.  Некоторые веб\-обозреватели соблюдать этот флаг, обеспечивая доступ значения cookie сценарий на стороне клиента.  По умолчанию используется значение «true».|  
|домен|Значение все файлы cookie записываются домен.  По умолчанию используется значение "".|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<chunkedCookieHandler\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/chunkedcookiehandler.md)|Настройка <xref:System.IdentityModel.Services.ChunkedCookieHandler>.  Этот элемент может быть представлен, только если `mode` атрибута `<cookieHandler>` является элемент «По умолчанию» или «Поблочного».|  
|[\<customCookieHandler\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/customcookiehandler.md)|Задает тип обработчика пользовательского файла cookie.  Этот элемент должен присутствовать при `mode` атрибута `<cookieHandler>` элемент является «Пользовательский».  Он не может присутствовать значения параметра `mode` атрибут.  Пользовательский тип должен быть производным от <xref:System.IdentityModel.Services.CookieHandler> класса.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<federationConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|Содержит параметры, <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> \(WSFAM\) и <xref:System.IdentityModel.Services.SessionAuthenticationModule> \(SAM\).|  
  
## Заметки  
 <xref:System.IdentityModel.Services.CookieHandler> Отвечает за чтение и запись необработанных файлов "cookie" HTTP\-протокол уровня.  Можно настроить либо <xref:System.IdentityModel.Services.ChunkedCookieHandler> или обработчик пользовательского файла cookie производным от <xref:System.IdentityModel.Services.CookieHandler> класса.  
  
 Чтобы настроить обработчик частям файла cookie, задайте значение атрибута mode «Chunked» или «По умолчанию».  Размер блока по умолчанию — 2000 байт, но при необходимости можно задать другой размер фрагмента данных, включая `<chunkedCookieHandler>` дочернего элемента.  
  
 Настройка cookie пользовательский обработчик, задайте значение атрибута mode на «Пользовательский».  Необходимо также указать `<customCookieHandler>` дочерний элемент, который ссылается на тип пользовательского обработчика.  
  
 `<cookieHandler>` Представленного элементом <xref:System.IdentityModel.Services.CookieHandlerElement> класса.  Обработчик файлов cookie, указанный в конфигурации из <xref:System.IdentityModel.Services.Configuration.FederationConfiguration.CookieHandler%2A> свойства <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> объекта, на <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=fullName> свойства.  
  
## Пример  
 Это показано в следующем XML `<cookieHandler>` элемент.  В этом примере так как `mode` атрибут не указан, файл cookie обработчик по умолчанию будет использоваться SAM.  Это является экземпляром класса <xref:System.IdentityModel.Services.ChunkedCookieHandler> класса.  Так как `<chunkedCookieHandler>` дочерний элемент не указан, будет использован размер блока по умолчанию.  HTTPS не потребуется из\-за `requireSsl` значение атрибута `false`.  
  
> [!WARNING]
>  В этом примере HTTPS не требуется писать файлы «cookie» сеанса.  Это происходит потому, что `requireSsl` атрибут на `<cookieHandler>` элемента `false`.  Этот параметр не рекомендуется для большинства рабочих средах, как он может представлять угрозу безопасности.  
  
```  
<cookieHandler requireSsl="false" />  
```  
  
## См. также  
 <xref:System.IdentityModel.Services.CookieHandler>   
 <xref:System.IdentityModel.Services.ChunkedCookieHandler>   
 <xref:System.IdentityModel.Services.SessionAuthenticationModule>