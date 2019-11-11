---
title: <wsFederation>
ms.date: 03/30/2017
ms.assetid: c537f770-68bd-4f82-96ad-6424ad91369f
author: BrucePerlerMS
ms.openlocfilehash: 0e3e33d5ba8c21738bdea11bd24a025d44919863
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251731"
---
# <a name="wsfederation"></a>\<wsFederation >
Предоставляет конфигурацию для <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM).  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. identityModel. Services**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<federationConfiguration >** ](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<wsFederation >**  
  
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
|authenticationType|URI, указывающий тип проверки подлинности. Задает параметр wauth для запроса на вход WS-Federation. Необязательный параметр. Значение по умолчанию — пустая строка, указывающая, что параметр wauth не включен в запрос.|  
|freshness|Требуемый максимальный возраст запросов проверки подлинности в минутах. Задает параметр wfresh для запроса на вход WS-Federation. Необязательный параметр. По умолчанию используется значение ноль. Необязательный параметр. **Предупреждение.**  В следующем выпуске .NET Framework 4,5 `freshness` атрибут будет иметь тип `xs:string` , а `null`его значение по умолчанию будет.|  
|homeRealm|Домашняя область поставщика удостоверений (IdP), используемая для проверки подлинности. Задает параметр запроса на вход WS-Federation. Необязательный параметр. Значение по умолчанию — пустая строка, указывающая, что параметр Втч не включен в запрос.|  
|issuer|Универсальный код ресурса (URI) предполагаемого издателя маркера. Задает базовый URL-адрес для запросов входа WS-Federation и запросов выхода.|  
|persistentCookiesOnPassiveRedirects|Указывает, выдаются ли постоянные файлы cookie при проверке подлинности. Необязательный параметр. Значение по умолчанию — false, а файлы cookie не выдаются.|  
|passiveRedirectEnabled|Указывает, включена ли WSFAM для автоматического перенаправления неавторизованных запросов STS. Необязательный параметр. Значение по умолчанию — true, неавторизованные запросы автоматически перенаправляются.|  
|policy|URL-адрес, указывающий расположение соответствующей политики для использования при запросах на вход. Значение по умолчанию — пустая строка. Задает параметр WP запроса на вход WS-Federation. Необязательный параметр. Значение по умолчанию — пустая строка, которая указывает, что параметр WP не включен в запрос.|  
|realm|Универсальный код ресурса (URI) области запроса. (URI, определяющий проверяющую сторону (RP) для службы маркеров безопасности (STS).) Задает параметр запроса на вход wtrealm WS-Federation. Обязательный.|  
|reply|URL-адрес, определяющий адрес, по которому приложение проверяющей стороны должно получить ответы от службы маркеров безопасности (STS). Задает параметр wreply для запроса на вход WS-Federation. Необязательный параметр. Значение по умолчанию — пустая строка, указывающая, что параметр wreply не включен в запрос.|  
|request|Запрос на выдачу маркера. Задает параметр wreq для запроса на вход WS-Federation. Необязательный параметр. Значение по умолчанию — пустая строка, указывающая, что параметр wreq не включен в запрос. Не включая wreq или параметр wreqptr в запросе, подразумевает, что STS знает, какой тип маркера следует выдавать.|  
|requestPtr|URL-адрес, указывающий расположение запроса на выдачу маркера. Задает параметр запроса wreqptr. Необязательный параметр. Значение по умолчанию — пустая строка, указывающая, что параметр wreqptr не включен в запрос. Не включая wreq или параметр wreqptr в запросе, подразумевает, что STS знает, какой тип маркера следует выдавать.|  
|requireHttps|Указывает, должен ли обмен данными со службой маркеров безопасности (STS) использовать протокол HTTPS. Необязательный параметр. Значение по умолчанию — true, необходимо использовать протокол HTTPS.|  
|resource|Универсальный код ресурса (URI), определяющий ресурс, к которому осуществляется доступ, проверяющая сторона (RP) в службе маркеров безопасности (STS). Необязательный параметр. Задает параметр врес для запроса на вход WS-Federation. Необязательный параметр. Значение по умолчанию — пустая строка, указывающая, что параметр врес не включен в запрос. **Примечание.** врес является устаревшим параметром. `realm` Укажите атрибут, чтобы использовать вместо него параметр wtrealm.|  
|signInQueryString|Предоставляет точку расширения для указания параметров запроса, определенных приложением, в URL-адресе запроса на вход WS-Federation. Необязательный параметр. Значение по умолчанию — пустая строка, которая указывает, что в запрос не должны включаться дополнительные параметры. Параметры указываются в виде фрагмента строки запроса в следующей форме: `"param1=value1&param2=value2&param3=value3"` и т. д. **Примечание.**  В файле конфигурации символ "&" в строке запроса должен быть указан с помощью ссылки на сущность, `&`.|  
|signOutQueryString|Предоставляет точку расширения для указания параметров запроса, определенных приложением, в URL-адресе запроса на вход WS-Federation. Необязательный параметр. Значение по умолчанию — пустая строка, которая указывает, что в запрос не должны включаться дополнительные параметры. Параметры указываются в виде фрагмента строки запроса в следующей форме: `"param1=value1&param2=value2&param3=value3"` и т. д. **Примечание.**  В файле конфигурации символ "&" в строке запроса должен быть указан с помощью ссылки на сущность, `&`.|  
|signOutReply|Указывает URL-адрес, на который служба маркеров безопасности должна перенаправлять клиент во время пассивного выхода через протокол WS-Federation. Задает параметр wreply в запросе выхода WS-Federation. Необязательный параметр. Значение по умолчанию — пустая строка, которая указывает, что в запрос не должны включаться дополнительные параметры.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствуют  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<federationConfiguration>](federationconfiguration.md)|Содержит параметры, которые настраивают <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> свойства (WSFAM) <xref:System.IdentityModel.Services.SessionAuthenticationModule> и (SAM).|  
  
## <a name="remarks"></a>Примечания  
 `<wsFederation>` Элемент можно использовать для настройки параметров WS-Federation по умолчанию и поведения по умолчанию для WSFAM. Параметры WS-Federation, `<wsFederation>` определенные в наборе элементов эквивалентные свойства, предоставляемые <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> классом. Эти свойства остаются одинаковыми для каждого запроса, выданного WSFAM. Параметры WS-Federation можно изменить динамически во время обработки запроса, добавив обработчики событий для событий, предоставляемых WSFAM; Например, <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectingToIdentityProvider> событие. Дополнительные сведения см. в документации <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> по классу.  
  
 `<wsFederation>` Элемент представлен<xref:System.IdentityModel.Services.Configuration.WSFederationElement> классом. Сам объект конфигурации представлен <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration> классом. Один <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration> экземпляр задается <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> для объекта <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> , доступ к которому осуществляется через свойство и обеспечивает конфигурацию для WSFAM.  
  
## <a name="example"></a>Пример  
 В следующем XML-коде `<wsFederation>` показан элемент, указывающий параметры для WSFAM.  
  
> [!WARNING]
> В этом примере WSFAM не требуется для использования HTTPS. Это связано с тем `requireHttps` , что атрибут `<wsFederation>` элемента задан `false`. Этот параметр не рекомендуется для большинства рабочих сред, так как может представлять угрозу безопасности.  
  
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
