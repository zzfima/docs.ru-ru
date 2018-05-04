---
title: '&lt;cookieHandler&gt;'
ms.date: 03/30/2017
ms.assetid: bfdc127f-8d94-4566-8bef-f583c6ae7398
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 7fcdf1e89c3b68daa36ee80fe7234737c61a5a3c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltcookiehandlergt"></a>&lt;cookieHandler&gt;
Настраивает <xref:System.IdentityModel.Services.CookieHandler> , <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) используется для чтения и записи файлов cookie.  
  
 \<system.identityModel.services >  
\<federationConfiguration >  
\<cookieHandler >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
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
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|имя|Определяет базовое имя для записываемых файлов cookie. Значение по умолчанию — «FedAuth».|  
|путем|Указывает значение пути для записываемых файлов cookie. Значение по умолчанию — «HttpRuntime.AppDomainAppVirtualPath».|  
|режим|Один из <xref:System.IdentityModel.Services.CookieHandlerMode> значений, определяющий вид создаваемого обработчик куки-файл, используемый SAM. Могут использоваться следующие значения:<br /><br /> -«Default» — то же, что «Chunked».<br />-Шифрование «фрагментированной» – используется экземпляр <xref:System.IdentityModel.Services.ChunkedCookieHandler> класса. Этот файл cookie обработчик гарантирует, что отдельные файлы cookie не превышает максимальный размер набора. Это делается путем потенциально «фрагментация» один логический файл cookie на несколько файлов "cookie" на лету.<br />-«Custom» — используется экземпляр пользовательского класса, производного от <xref:System.IdentityModel.Services.CookieHandler>. Производный класс ссылается `<customCookieHandler>` дочерний элемент.<br /><br /> Значение по умолчанию — «Default».|  
|persistentSessionLifetime|Задает время существования постоянные сеансы. Если значение равно нулю, всегда используются временные сеансы. Значение по умолчанию — «0:0:0», который указывает временного сеанса. Максимальное значение равно «365:0:0», который определяет сеанс 365 дней. Значение должно быть указано в соответствии с следующее ограничение: `<xs:pattern value="([0-9.]+:){0,1}([0-9]+:){0,1}[0-9.]+" />`, где самое левое значение указывает дни, часы указывает среднее значение (при его наличии) и самое правое значение (при его наличии) указывает минуты.|  
|RequireSsl|Указывает, создается ли флаг «Безопасность» для записываемых файлов cookie. Если это значение задано, файлы cookie сеанса входа в систему будет доступна только по протоколу HTTPS. Значение по умолчанию - "true".|  
|hideFromScript|Определяет, создается ли флаг «HttpOnly» для записываемых файлов cookie. Некоторые веб-браузеры учитывают этот флаг, оставив установленным клиентским сценариям доступ значение файла cookie. Значение по умолчанию - "true".|  
|домен|Значение домена для записываемых файлов cookie. По умолчанию используется значение "".|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<chunkedCookieHandler >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/chunkedcookiehandler.md)|Настраивает <xref:System.IdentityModel.Services.ChunkedCookieHandler>. Этот элемент может быть представлен, только если `mode` атрибут `<cookieHandler>` «Default» или «Фрагментированным».|  
|[\<customCookieHandler >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/customcookiehandler.md)|Задает тип обработчика пользовательского файла cookie. Этот элемент должен присутствовать при `mode` атрибут `<cookieHandler>` элемента является «Custom». Он не может присутствовать для других значений параметра `mode` атрибута. Пользовательский тип должен быть производным от <xref:System.IdentityModel.Services.CookieHandler> класса.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|Содержит параметры, настроенные <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) и <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).|  
  
## <a name="remarks"></a>Примечания  
 <xref:System.IdentityModel.Services.CookieHandler> Отвечает за чтение и запись необработанных файлов cookie HTTP-протокола уровня. Можно настроить либо <xref:System.IdentityModel.Services.ChunkedCookieHandler> или обработчик пользовательского файла cookie, производный от <xref:System.IdentityModel.Services.CookieHandler> класса.  
  
 Чтобы настроить обработчик блочный файл cookie, задайте значение атрибута mode «Chunked» или «Default». Размер блока по умолчанию равен 2000 байтам, но можно указать размер различных фрагмента, включая `<chunkedCookieHandler>` дочерний элемент.  
  
 Чтобы настроить обработчик пользовательского файла cookie, установите режим атрибута значение «Custom». Необходимо также указать `<customCookieHandler>` дочерний элемент, который ссылается на тип пользовательского обработчика.  
  
 `<cookieHandler>` Представлен <xref:System.IdentityModel.Services.CookieHandlerElement> класса. Обработчик куки-файл, который был указан в конфигурации можно получить из <xref:System.IdentityModel.Services.Configuration.FederationConfiguration.CookieHandler%2A> свойство <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> на объект на <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> свойство.  
  
## <a name="example"></a>Пример  
 Следующий XML-КОДЕ показано `<cookieHandler>` элемента. В этом примере поскольку `mode` атрибут не указан, обработчик куки-файл по умолчанию будет использоваться SAM. Это является экземпляром класса <xref:System.IdentityModel.Services.ChunkedCookieHandler> класса. Поскольку `<chunkedCookieHandler>` дочерний элемент не указан, будет использоваться размер блока по умолчанию. Так как HTTPS не будет обязательным `requireSsl` установлен атрибут `false`.  
  
> [!WARNING]
>  В этом примере для записи файлов cookie сеанса не требуется протокол HTTPS. Это вызвано `requireSsl` атрибут `<cookieHandler>` задан равным `false`. Этот параметр не рекомендуется для большинства рабочих сред, как он может представлять угрозу безопасности.  
  
```xml  
<cookieHandler requireSsl="false" />  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.IdentityModel.Services.CookieHandler>  
 <xref:System.IdentityModel.Services.ChunkedCookieHandler>  
 <xref:System.IdentityModel.Services.SessionAuthenticationModule>
