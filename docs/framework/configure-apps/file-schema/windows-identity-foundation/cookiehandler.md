---
title: <cookieHandler>
ms.date: 03/30/2017
ms.assetid: bfdc127f-8d94-4566-8bef-f583c6ae7398
author: BrucePerlerMS
ms.openlocfilehash: dc0613bb727f9ed061c3b5d494bdc279515b56e9
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55285869"
---
# <a name="cookiehandler"></a>\<cookieHandler >
Настраивает <xref:System.IdentityModel.Services.CookieHandler> , <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) используется для чтения и записи файлов cookie.  
  
 \<system.identityModel.services>  
\<federationConfiguration>  
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
|имя|Указывает базовое имя для записываемых файлов cookie. Значение по умолчанию — «FedAuth».|  
|путем|Указывает значение пути для записываемых файлов cookie. Значение по умолчанию — «HttpRuntime.AppDomainAppVirtualPath».|  
|режим|Один из <xref:System.IdentityModel.Services.CookieHandlerMode> значений, указывающее тип обработчика файлов cookie, используемый SAM. Могут использоваться следующие значения:<br /><br /> -«Default» — так же, как «Chunked».<br />-Шифрование «фрагментированной» – используется экземпляр <xref:System.IdentityModel.Services.ChunkedCookieHandler> класса. Этот обработчик файлов cookie гарантирует, что отдельные файлы cookie не превышает заданный максимальный размер. Он делает это, потенциально «фрагментация» один логический файл cookie на несколько файлов cookie на лету.<br />-«Custom» – используется экземпляр пользовательского класса, производного от <xref:System.IdentityModel.Services.CookieHandler>. Производный класс ссылается `<customCookieHandler>` дочерний элемент.<br /><br /> По умолчанию используется «Default».|  
|persistentSessionLifetime|Указывает время существования постоянных сеансов. Если значение равно нулю, всегда используются временные сеансы. Значение по умолчанию — «помечает», который указывает временный сеанс. Максимальное значение равно «365:0:0», который указывает сеанс 365 дней. Значение должно быть указано в соответствии с следующее ограничение: `<xs:pattern value="([0-9.]+:){0,1}([0-9]+:){0,1}[0-9.]+" />`, где самое левое значение указывает дни, среднее значение (при его наличии) указывает часы и самое правое значение (при его наличии) указывает минуты.|  
|RequireSsl|Указывает, создается ли флаг «Безопасно» для записываемых файлов cookie. Если это значение задано, файлы cookie сеанса входа доступна только по протоколу HTTPS. Значение по умолчанию - "true".|  
|hideFromScript|Определяет, создается ли флаг «HttpOnly» для записываемых файлов cookie. Некоторые веб-браузеры учитывает этот флаг, оставив скрипт на стороне клиента доступ к значение файла cookie. Значение по умолчанию - "true".|  
|домен|Значение домена для записываемых файлов cookie. По умолчанию используется значение "".|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<chunkedCookieHandler >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/chunkedcookiehandler.md)|Настраивает <xref:System.IdentityModel.Services.ChunkedCookieHandler>. Этот элемент может быть представлен, только если `mode` атрибут `<cookieHandler>` элемент является «Default» или шифрование «фрагментированной».|  
|[\<customCookieHandler >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/customcookiehandler.md)|Задает тип обработчика пользовательских файлов cookie. Этот элемент должен присутствовать Если `mode` атрибут `<cookieHandler>` элемент является «Custom». Он не может присутствовать для других значений параметра `mode` атрибута. Пользовательский тип должен быть производным от <xref:System.IdentityModel.Services.CookieHandler> класса.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|Содержит параметры, определяющие <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) и <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).|  
  
## <a name="remarks"></a>Примечания  
 <xref:System.IdentityModel.Services.CookieHandler> Отвечает за чтение и запись необработанных файлов cookie HTTP-протокола уровня. Возможность настроить <xref:System.IdentityModel.Services.ChunkedCookieHandler> или пользовательский обработчик файлов cookie, производный от <xref:System.IdentityModel.Services.CookieHandler> класса.  
  
 Чтобы настроить фрагментированный обработчик cookie, устанавливают атрибут режима «Chunked» или «Default». Размер блока по умолчанию равен 2000 байтам, но можно указать размер блоков разного, включив `<chunkedCookieHandler>` дочерний элемент.  
  
 Чтобы настроить пользовательский обработчик файлов cookie, устанавливают атрибут режима на «Custom». Необходимо также указать `<customCookieHandler>` дочерний элемент, ссылающийся на тип пользовательского обработчика.  
  
 `<cookieHandler>` Элемент, представленный объектом <xref:System.IdentityModel.Services.CookieHandlerElement> класса. Обработчик файлов cookie, который был указан в конфигурации доступен из <xref:System.IdentityModel.Services.Configuration.FederationConfiguration.CookieHandler%2A> свойство <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> на набор объектов <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> свойство.  
  
## <a name="example"></a>Пример  
 Следующий код XML показывает `<cookieHandler>` элемент. В этом примере так как `mode` атрибут не указан, обработчик файлов cookie по умолчанию будет использоваться SAM. Это экземпляр <xref:System.IdentityModel.Services.ChunkedCookieHandler> класса. Так как `<chunkedCookieHandler>` дочерний элемент не указан, будет использоваться размер блока по умолчанию. HTTPS не требуется, так как `requireSsl` атрибут имеет значение `false`.  
  
> [!WARNING]
>  В этом примере HTTPS не требуется для записи файлов cookie сеанса. Это обусловлено `requireSsl` атрибут `<cookieHandler>` элементу присваивается `false`. Этот параметр не рекомендуется для большинства рабочих сред, как он может представлять угрозу безопасности.  
  
```xml  
<cookieHandler requireSsl="false" />  
```  
  
## <a name="see-also"></a>См. также
- <xref:System.IdentityModel.Services.CookieHandler>
- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
- <xref:System.IdentityModel.Services.SessionAuthenticationModule>
