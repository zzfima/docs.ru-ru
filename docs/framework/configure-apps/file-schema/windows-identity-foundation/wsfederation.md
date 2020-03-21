---
title: <wsFederation>
ms.date: 03/30/2017
ms.assetid: c537f770-68bd-4f82-96ad-6424ad91369f
author: BrucePerlerMS
ms.openlocfilehash: 53f3943524c45a43ddb60553b8ff45f19df66b14
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152467"
---
# <a name="wsfederation"></a>\<wsFederation>
Обеспечивает конфигурацию <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> для (WSFAM).  
  
[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<федерацияКонфигурация>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsFederation>**  
  
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
  
|attribute|Описание|  
|---------------|-----------------|  
|authenticationType|Универсальный код ресурса (URI), указывающий тип аутентификации. Устанавливает параметр ws-Federation, вскакивая в wauth. Необязательный параметр. По умолчанию по умолчанию является пустой строкой, которая указывает, что параметр wauth не включен в запрос.|  
|Свежесть|Требуемая максимальная длительность запросов аутентификации в минутах. Задает параметр wfresh запроса входа запроса WS-Federation. Необязательный параметр. По умолчанию используется значение 0. Необязательный параметр. **Предупреждение:**  В следующем выпуске .NET Framework 4.5 `freshness` атрибут `xs:string` будет типа и `null`его значение по умолчанию будет .|  
|homeRealm|Домашняя сфера поставщика идентификационных данных (IdP) для использования для проверки подлинности. Задает параметр whr запроса входа запроса WS-Federation. Необязательный параметр. По умолчанию по умолчанию является пустой строкой, которая указывает, что параметр whr не включен в запрос.|  
|issuer|URI предполагаемого эмитента токенов. Устанавливает базовый URL запросов ws-Federation на регистрацию и запросы на регистрацию.|  
|persistentCookiesOnPassiveRedirects|Уточняется, выдаются ли постоянные файлы cookie при проверке подлинности. Необязательный параметр. По умолчанию является "ложным", файлы cookie не выдаются.|  
|пассивноеRedirectEnabled|Уточняется, включена ли WSFAM в автоматическое перенаправление несанкционированных запросов на СТС. Необязательный параметр. По умолчанию "истинен", несанкционированные запросы автоматически перенаправляются.|  
|policy|URL-адрес, означающие местоположение соответствующей политики для использования в запросах на входе. Значением по умолчанию является пустая строка. Задает параметр wp запроса входа запроса WS-Federation. Необязательный параметр. По умолчанию по умолчанию является пустой строкой, которая указывает, что параметр WP не включен в запрос.|  
|realm|URI запрашивающего realm. (URI, идентифицирующий полагающейся сторону (RP) службе маркеров безопасности (STS).) Устанавливает параметр запроса wtrealm WS-Federation, вскакиваемый в систему. Обязательный элемент.|  
|reply|URL-адрес, указывающий адрес, по которому приложение проверяющей стороны (RP) хотел бы получить ответы от службы токенов безопасности (STS). Устанавливает параметр запроса WS-Federation, вскакиваемый в систему. Необязательный параметр. По умолчанию по умолчанию является пустой строкой, которая указывает, что параметр wreply не включен в запрос.|  
|запрос|Запрос на выдачу токенов. Задает параметр wreq запроса входа запроса WS-Federation. Необязательный параметр. По умолчанию по умолчанию является пустой строкой, которая указывает, что параметр wreq не включен в запрос. Не включая wreq или wreqptr параметр в запросе означает, что СТС знает, какой маркер выдавать.|  
|запросPtr|URL-адрес, указывающий расположение запроса выдачи токена. Устанавливает параметр wreqptr запроса. Необязательный параметр. По умолчанию по умолчанию является пустой строкой, которая указывает, что параметр wreqptr не включен в запрос. Не включая wreq или wreqptr параметр в запросе означает, что СТС знает, какой маркер выдавать.|  
|requireHttps|Уточняется, должна ли связь с службой маркеров безопасности (STS) использовать протокол HTTPS. Необязательный параметр. По умолчанию является "истинным", HTTPS должны быть использованы.|  
|ресурс|Универсальный код ресурса (URI), определяющий ресурс, доступ к которому осуществлялся, проверяющую сторону (RP), для службы токенов безопасности (STS). Необязательный параметр. Устанавливает параметр входиного WS-Federation. Необязательный параметр. По умолчанию по умолчанию является пустой строкой, которая указывает, что параметр wres не включен в запрос. **Примечание:** wres является устаревшим параметром. Укажите `realm` атрибут, чтобы использовать параметр wtrealm вместо этого.|  
|signInqueryString|Обеспечивает точку расширяемости для указания параметров запроса приложения, определенных в URL-адресе запроса WS-Federation. Необязательный параметр. По умолчанию по умолчанию в запросе указывается, что дополнительные параметры не должны быть включены. Параметры указаны как фрагмент строки запроса, `"param1=value1&param2=value2&param3=value3"` используя следующую форму: и так далее. **Примечание:**  В файле конфигурации символ "&" в строке запроса `&`должен быть указан с помощью ссылки сущности.|  
|signOut-КериСтринг|Обеспечивает точку расширяемости для указания параметров запроса приложения, определенных в URL-адресе запроса WS-Federation. Необязательный параметр. По умолчанию по умолчанию в запросе указывается, что дополнительные параметры не должны быть включены. Параметры указаны как фрагмент строки запроса, `"param1=value1&param2=value2&param3=value3"` используя следующую форму: и так далее. **Примечание:**  В файле конфигурации символ "&" в строке запроса `&`должен быть указан с помощью ссылки сущности.|  
|signOutReply|Укажите URL-адрес, на который клиент должен быть перенаправлен службой маркеров безопасности (STS) во время пассивного выхода через протокол WS-Federation. Устанавливает параметр wreply в запросе на выписку WS-Federation. Необязательный параметр. По умолчанию по умолчанию в запросе указывается, что дополнительные параметры не должны быть включены.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 None  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<федерацияКонфигурация>](federationconfiguration.md)|Содержит настройки, настраивающие <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) <xref:System.IdentityModel.Services.SessionAuthenticationModule> и (SAM).|  
  
## <a name="remarks"></a>Remarks  
 Элемент можно `<wsFederation>` настроить параметры параметров WS-Federation по умолчанию и поведение по умолчанию для WSFAM. Параметры WS-Federation, определяемые под `<wsFederation>` <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> набором эквивалентных свойств элемента, выставленных классом. Эти свойства остаются неизменными для каждого запроса, выданного WSFAM. Параметры WS-Federation можно динамически изменять во время обработки запросов, добавляя обработчики событий для событий, выставленных WSFAM; например, <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectingToIdentityProvider> событие. Для получения дополнительной информации <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> ознакомьтесь с документацией для класса.  
  
 Элемент `<wsFederation>` представлен <xref:System.IdentityModel.Services.Configuration.WSFederationElement> классом. Сам объект конфигурации представлен <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration> классом. На <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration> объекте, <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> доступ к объекту, <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> который доступен через свойство, устанавливается единый экземпляр, который обеспечивает конфигурацию для WSFAM.  
  
## <a name="example"></a>Пример  
 Следующий XML `<wsFederation>` показывает элемент, определяющий настройки для WSFAM.  
  
> [!WARNING]
> В этом примере WSFAM не обязан использовать HTTPS. Это связано `requireHttps` с `<wsFederation>` тем, `false`что элемент на элементе установлен. Этот параметр не рекомендуется для большинства производственных сред, так как может представлять угрозу безопасности.  
  
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
  
## <a name="see-also"></a>См. также раздел

- <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>
- <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>
