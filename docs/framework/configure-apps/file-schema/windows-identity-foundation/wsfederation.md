---
title: <wsFederation>
ms.date: 03/30/2017
ms.assetid: c537f770-68bd-4f82-96ad-6424ad91369f
author: BrucePerlerMS
ms.openlocfilehash: 276f552767897729bf58c6a803669f39c96f09e3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59135139"
---
# <a name="wsfederation"></a>\<wsFederation >
Предоставляет конфигурацию для <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM).  
  
\<system.identityModel.services>  
\<federationConfiguration>  
\<wsFederation >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml
<system.identityModel.services>  
  <federationConfiguration>  
    <wsFederation authenticationType=xs:string (URI)  
                  freshness=xs:decimal  
                  homerealm=xs:string (URI)  
                  issuer=xs:string (URI)  
                  persistentCookiesOnPassiveRedirects=xs:boolean  
                  passiveRedirectEnabled=xs:boolean  
                  policy=xs:string (URI)  
                  realm=xs:string (URI)  
                  reply=xs:string (URI)  
                  request=xs:string (URI)  
                  requestPtr=xs:string (URI)  
                  requireHttps=xs:boolean  
                  resource=xs:string (URI)  
                  signInQueryString=xs:string  
                  signOutQueryString=xs:string  
                  signOutReply=xs:string (URL)  
    </wsFederation>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|authenticationType|URI, указывающий тип проверки подлинности. Задает параметр wauth запроса входа запроса WS-Federation. Необязательный параметр. Значение по умолчанию является пустой строкой, который указывает, что параметр wauth не включен в запрос.|  
|актуальность|Требуемая Максимальная длительность запросов аутентификации в минутах. Задает параметр wfresh запроса входа запроса WS-Federation. Необязательный параметр. По умолчанию используется значение ноль. Необязательный параметр. **Предупреждение.**  В следующем выпуске платформы .NET Framework 4.5 `freshness` атрибут будет иметь тип `xs:string` и его значение по умолчанию будет `null`.|  
|homeRealm|Домашней области поставщика удостоверений (IdP), используемый для проверки подлинности. Задает параметр whr запроса входа запроса WS-Federation. Необязательный параметр. Значение по умолчанию является пустой строкой, который указывает, что параметр whr не включен в запрос.|  
|issuer|URI предполагаемого издателя токена. Задает базовый URL-адрес из WS-Federation в запросах входа и выхода запросов требуется.|  
|persistentCookiesOnPassiveRedirects|Указывает, выпускаются ли постоянные файлы cookie для проверки подлинности. Необязательный параметр. Значение по умолчанию — «false», файлы cookie не выдаются.|  
|passiveRedirectEnabled|Указывает, включена ли WSFAM автоматически перенаправлять неавторизованные запросы в службу STS. Необязательный параметр. Значение по умолчанию — «true», неавторизованные запросы автоматически перенаправляются.|  
|policy|URL-адрес, указывающий расположение соответствующей политики на запросы на вход. Значение по умолчанию - пустая строка. Задает параметр wp запроса входа запроса WS-Federation. Необязательный параметр. Значение по умолчанию является пустой строкой, который указывает, что параметр wp не включен в запрос.|  
|realm|URI запрашиваемой области. (URI, определяющий проверяющую сторону (RP) для службы маркеров безопасности (STS).) Задает параметр wtrealm входа WS-Federation запроса запроса. Обязательный.|  
|reply|URL-адрес, который определяет адрес, по которому приложение проверяющей стороны (RP) хотели бы получать ответы от службы (Маркеров безопасности). Задает параметр wreply запроса входа запроса WS-Federation. Необязательный параметр. Значение по умолчанию является пустой строкой, которая указывает, что параметр wreply не включены в запрос.|  
|Запрос|Запрос выдачи токена. Задает параметр wreq запроса входа запроса WS-Federation. Необязательный параметр. Значение по умолчанию является пустой строкой, который указывает, что параметр wreq не включен в запрос. Не включая wreq и параметр wreqptr в запросе, это означает, что STS знает, какой тип маркера для выдачи.|  
|requestPtr|URL-адрес, указывающий расположение запроса выдачи токена. Задает параметр wreqptr запроса. Необязательный параметр. Значение по умолчанию является пустой строкой, который указывает, что параметр wreqptr не включен в запрос. Не включая wreq и параметр wreqptr в запросе, это означает, что STS знает, какой тип маркера для выдачи.|  
|requireHttps|Указывает, должен ли обмен данными со службой маркеров безопасности (STS) использовать протокол HTTPS. Необязательный параметр. Значение по умолчанию — «true», должен использоваться протокол HTTPS.|  
|ресурс|URI, определяющий ресурс осуществлялся, проверяющую сторону (RP), в службе маркеров безопасности (STS). Необязательный параметр. Задает параметр wres запроса входа запроса WS-Federation. Необязательный параметр. Значение по умолчанию является пустой строкой, который указывает, что параметр wres не включен в запрос. **Примечание:** wres — это устаревший параметр. Укажите `realm` атрибут, чтобы вместо этого используйте параметр wtrealm.|  
|signInQueryString|Предоставляет точку расширения для указания параметров запроса, определенных приложением в URL-адрес запроса входа запроса WS-Federation. Необязательный параметр. Значение по умолчанию является пустой строкой, которая указывает, что никаких дополнительных параметров должны быть включены в запросе. Параметры задаются в виде фрагмента строки запроса, в следующем формате: `"param1=value1&param2=value2&param3=value3"` и т. д. **Примечание.**  В файле конфигурации "&» символа в строке запроса должен быть указан с помощью его ссылку на сущность `&`.|  
|signOutQueryString|Предоставляет точку расширения для указания параметров запроса, определенных приложением в URL-адрес запроса входа запроса WS-Federation. Необязательный параметр. Значение по умолчанию является пустой строкой, которая указывает, что никаких дополнительных параметров должны быть включены в запросе. Параметры задаются в виде фрагмента строки запроса, в следующем формате: `"param1=value1&param2=value2&param3=value3"` и т. д. **Примечание.**  В файле конфигурации "&» символа в строке запроса должен быть указан с помощью его ссылку на сущность `&`.|  
|signOutReply|Указывает URL-адрес, к которому должна перенаправлять клиент службы маркеров безопасности (STS) во время пассивного выхода через протокол WS-Federation. Задает параметр wreply запроса выхода WS-Federation. Необязательный параметр. Значение по умолчанию является пустой строкой, которая указывает, что никаких дополнительных параметров должны быть включены в запросе.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|Содержит параметры, определяющие <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) и <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).|  
  
## <a name="remarks"></a>Примечания  
 Можно использовать `<wsFederation>` элемент для настройки параметров по умолчанию WS-Federation и поведение по умолчанию для WSFAM. Настройки параметров WS-Federation, определенные в разделе `<wsFederation>` элемента задано эквивалентные свойства, предоставляемые <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> класса. Эти свойства не изменяются для каждого запроса, выданные WSFAM. Можно изменить параметры WS-Federation динамически во время обработки путем добавления обработчиков событий для события, представляемые WSFAM; запросов например <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectingToIdentityProvider> событий. Дополнительные сведения см. в документации по <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> класса.  
  
 `<wsFederation>` Элемент, представленный объектом <xref:System.IdentityModel.Services.Configuration.WSFederationElement> класса. Сам объект конфигурации представленного <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration> класса. Один <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration> экземпляр устанавливается на <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> объекта, к которому осуществляется через <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> свойство и предоставляет конфигурацию для WSFAM.  
  
## <a name="example"></a>Пример  
 Следующий код XML показывает `<wsFederation>` элемент, который задает настройки для WSFAM.  
  
> [!WARNING]
>  В этом примере WSFAM не требуется для использования протокола HTTPS. Это обусловлено `requireHttps` атрибут `<wsFederation>` элемента `false`. Этот параметр не рекомендуется для большинства рабочих сред, как он может представлять угрозу безопасности.  
  
```xml
<wsFederation passiveRedirectEnabled="true"   
              issuer="http://localhost:15839/wsFederationSTS/Issue"   
              realm="http://localhost:50969/"   
              reply="http://localhost:50969/"   
              requireHttps="false"   
              signOutReply="http://localhost:50969/SignedOutPage.html"   
              signOutQueryString="Param1=value2&Param2=value2"   
              persistentCookiesOnPassiveRedirects="true" />
```  
  
## <a name="see-also"></a>См. также

- <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>
- <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>
