---
title: '&lt;wsFederation&gt;'
ms.date: 03/30/2017
ms.assetid: c537f770-68bd-4f82-96ad-6424ad91369f
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: de7be463403b675e5f03786e85807e6685348680
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltwsfederationgt"></a>&lt;wsFederation&gt;
Обеспечивает настройку для <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM).  
  
\<system.identityModel.services >  
\<federationConfiguration >  
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
|authenticationType|URI, указывающий тип проверки подлинности. Задает для параметра wauth запрос входа WS-Federation. Необязательный. Значение по умолчанию — пустая строка, которая указывает, что параметр wauth не включены в запрос.|  
|актуальность|Требуемый максимальный срок действия запросов проверки подлинности в минутах. Задает для параметра wfresh запрос входа WS-Federation. Необязательный. По умолчанию используется значение ноль. Необязательный. **Предупреждение:** в следующей версии .NET Framework 4.5 `freshness` атрибута будет иметь тип `xs:string` будет иметь значение по умолчанию `null`.|  
|homeRealm|Домашней области поставщика удостоверений (IP), используемый для проверки подлинности. Задает параметр whr запрос входа WS-Federation. Необязательный. Значение по умолчанию — пустая строка, которая указывает, что параметр whr не включены в запрос.|  
|issuer|URI предполагаемого издателя маркера. Задает базовый URL-адрес для WS-Federation запросов на вход в и необходимые запросах на выход.|  
|persistentCookiesOnPassiveRedirects|Указывает, выполняется ли сохраняемые файлы cookie для проверки подлинности. Необязательный. Значение по умолчанию — «false», файлы cookie не выдаются.|  
|passiveRedirectEnabled|Указывает, включен ли WSFAM автоматического перенаправления неавторизованных запросов маркеров безопасности. Необязательный. Значение по умолчанию — «true», автоматически перенаправляются неавторизованных запросов.|  
|policy|URL-адрес, который указывает расположение для использования на запросов на вход в нужную политику. Значение по умолчанию - пустая строка. Задает параметр wp запрос входа WS-Federation. Необязательный. Значение по умолчанию — пустая строка, которая указывает, что параметр wp не включены в запрос.|  
|realm|URI области запроса. (URI, определяющий проверяющей стороны (RP) для службы маркеров безопасности (STS).) Задает для параметра запроса wtrealm вход WS-Federation запроса. Обязательно.|  
|reply|URL-адрес, который определяет адрес, по которому приложение проверяющей стороны (RP) вы хотите получать ответы из маркеров безопасности службы (STS). Задает для параметра wreply запрос входа WS-Federation. Необязательный. Значение по умолчанию — пустая строка, которая указывает, что параметр wreply не включены в запрос.|  
|Запрос|Запрос на выпуск маркера. Задает для параметра wreq запрос входа WS-Federation. Необязательный. Значение по умолчанию — пустая строка, которая указывает, что параметр wreq не включены в запрос. Не включая wreq или wreqptr параметр в запросе, это означает, что STS знает тип маркера для выдачи.|  
|requestPtr|URL-адрес, указывающий расположение запроса маркера. Задает параметр wreqptr запроса. Необязательный. Значение по умолчанию — пустая строка, которая указывает, что параметр wreqptr не включены в запрос. Не включая wreq или wreqptr параметр в запросе, это означает, что STS знает тип маркера для выдачи.|  
|requireHttps|Указывает, является ли обмен данными со службой маркеров безопасности (STS) необходимо использовать протокол HTTPS. Необязательный. Значение по умолчанию — «true», необходимо использовать протокол HTTPS.|  
|ресурс|URI, идентифицирующий ресурс, к которому выполняется доступ, проверяющей стороны (RP) к службе маркеров безопасности (STS). Необязательный. Задает для параметра wres запрос входа WS-Federation. Необязательный. Значение по умолчанию — пустая строка, которая указывает, что параметр wres не включены в запрос. **Примечание:** wres — это устаревший параметр. Укажите `realm` атрибут для использования вместо параметра wtrealm.|  
|signInQueryString|Предоставляет точку расширения для указания параметров запроса в приложение, определенное в URL-АДРЕСЕ запроса входа WS-Federation. Необязательный. Значение по умолчанию — пустая строка, которая указывает, что никаких дополнительных параметров должны быть включены в запрос. Параметры задаются в виде фрагмента строки запроса, в следующем формате: `"param1=value1&param2=value2&param3=value3"` и т. д. **Примечание:** в файле конфигурации "&» символа в строке запроса должен быть указан с помощью его ссылки сущности `&`.|  
|signOutQueryString|Предоставляет точку расширения для указания параметров запроса в приложение, определенное в URL-АДРЕСЕ запроса входа WS-Federation. Необязательный. Значение по умолчанию — пустая строка, которая указывает, что никаких дополнительных параметров должны быть включены в запрос. Параметры задаются в виде фрагмента строки запроса, в следующем формате: `"param1=value1&param2=value2&param3=value3"` и т. д. **Примечание:** в файле конфигурации "&» символа в строке запроса должен быть указан с помощью его ссылки сущности `&`.|  
|signOutReply|Указывает URL-адрес, к которому следует перенаправлять клиента службой маркеров безопасности (STS) во время выхода по протоколу WS-Federation пассивный. Задает параметр wreply запроса выхода в WS-Federation. Необязательный. Значение по умолчанию — пустая строка, которая указывает, что никаких дополнительных параметров должны быть включены в запрос.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|Содержит параметры, настроенные <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) и <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).|  
  
## <a name="remarks"></a>Примечания  
 Можно использовать `<wsFederation>` элемента для настройки параметров WS-Federation по умолчанию и поведение по умолчанию для WSFAM. Настройки параметров WS-Federation, определенный в `<wsFederation>` элемента задано эквивалентные свойства, предоставляемые <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> класса. Эти свойства остаются неизменными для всех запросов, выданных WSFAM. Можно изменять параметры WS-Federation динамически во время обработки путем добавления обработчиков событий для события, представляемые WSFAM; запроса например <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectingToIdentityProvider> событие. Дополнительные сведения см. в документации для <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> класса.  
  
 `<wsFederation>` Представлен <xref:System.IdentityModel.Services.Configuration.WSFederationElement> класса. Сам объект конфигурации представленного <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration> класса. Один <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration> набор экземпляров на <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> объект, который доступен через <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> свойства и обеспечивает настройку для WSFAM.  
  
## <a name="example"></a>Пример  
 Следующий XML-КОДЕ показано `<wsFederation>` элемент, который задает параметры для WSFAM.  
  
> [!WARNING]
>  В этом примере WSFAM не требуется для использования протокола HTTPS. Это вызвано `requireHttps` атрибут `<wsFederation>` задать элемент `false`. Этот параметр не рекомендуется для большинства рабочих сред, как он может представлять угрозу безопасности.  
  
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
 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>  
 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>
