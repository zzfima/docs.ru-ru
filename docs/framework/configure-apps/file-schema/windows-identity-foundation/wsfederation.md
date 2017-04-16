---
title: "&lt;wsFederation&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c537f770-68bd-4f82-96ad-6424ad91369f
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# &lt;wsFederation&gt;
Содержит настройки для <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> \(WSFAM\).  
  
## Синтаксис  
  
```  
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
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние элементы и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|authenticationType|URI, который указывает тип проверки подлинности.  Задает для параметра wauth WS\-Federation запрос на вход.  Необязательный.  По умолчанию используется пустая строка, которая указывает, что параметр wauth не включаются в запрос.|  
|актуальности|Требуемый максимальный срок хранения запросов проверки подлинности в минутах.  Задает для параметра wfresh WS\-Federation запрос на вход.  Необязательный.  По умолчанию используется значение ноль.  Необязательный. **Warning:**  В следующем выпуске.NET Framework 4.5 `freshness` будет иметь атрибут типа `xs:string` , и его значение по умолчанию будет `null`.|  
|homeRealm|Домашней сфере поставщика удостоверений \(IP\) для проверки подлинности.  Задает параметр whr WS\-Federation запрос на вход.  Необязательный.  По умолчанию используется пустая строка, которая указывает, что параметр whr не включаются в запрос.|  
|issuer|URI предполагаемого поставщика маркера.  Устанавливает базовый URL\-адрес из WS\-Federation вход запросов и необходимости выхода из системы запросов.|  
|persistentCookiesOnPassiveRedirects|Указывает, выдаются ли постоянные файлы cookie для проверки подлинности.  Необязательный.  Значение по умолчанию — «false», "cookie" не выдаются.|  
|passiveRedirectEnabled|Указывает, включена ли WSFAM автоматически перенаправлять запросы на несанкционированный STS.  Необязательный.  По умолчанию используется значение «true», автоматически перенаправляются несанкционированных запросов.|  
|политика|URL\-адрес, указывающий на местоположение соответствующей политики на запросы на вход.  Значение по умолчанию — пустая строка.  Задает для параметра ВЧ WS\-Federation запрос на вход.  Необязательный.  По умолчанию используется пустая строка, которая указывает, что параметр ВЧ не включаются в запрос.|  
|realm|URI запроса сферы.  \(URI, определяющий доверяющей стороне \(RP\) службы маркеров безопасности \(STS\).\) Задает для параметра запроса wtrealm вход WS\-Federation запрос.  Обязательный.|  
|reply|URL\-адрес, который определяет адрес, по которому приложение доверяющей стороной \(RP\) хотели бы получать ответы от маркеров безопасности службы \(STS\).  Задает для параметра wreply WS\-Federation запрос на вход.  Необязательный.  По умолчанию используется пустая строка, которая указывает, что параметр wreply не включаются в запрос.|  
|request|Запрос маркера.  Задает для параметра wreq WS\-Federation запрос на вход.  Необязательный.  По умолчанию используется пустая строка, которая указывает, что параметр wreq не включаются в запрос.  Не включая в запрос параметр wreqptr или wreq означает, что STS знает, какой тип маркера для выдачи.|  
|requestPtr|URL\-адрес, указывающий на местоположение запрос маркера.  Задает для параметра wreqptr запроса.  Необязательный.  По умолчанию используется пустая строка, которая указывает, что параметр wreqptr не включаются в запрос.  Не включая в запрос параметр wreqptr или wreq означает, что STS знает, какой тип маркера для выдачи.|  
|requireHttps|Указывает, будет ли связь со службой маркеров безопасности \(STS\) необходимо использовать протокол HTTPS.  Необязательный.  По умолчанию используется значение «true», необходимо использовать HTTPS.|  
|ресурс|URI, который идентифицирует ресурс, к которому обращается, доверяющей стороне \(RP\) для службы маркеров безопасности \(STS\).  Необязательный.  Задает для параметра wres WS\-Federation запрос на вход.  Необязательный.  По умолчанию используется пустая строка, которая указывает, что параметр wres не включаются в запрос. **Note:**  wres — устаревший параметр.  Укажите `realm` атрибут, используйте параметр wtrealm.|  
|signInQueryString|Предоставляет точку расширения среды для указания приложения определены параметры запроса в URL\-АДРЕСЕ WS\-Federation запрос на вход.  Необязательный.  По умолчанию используется пустая строка, которая указывает, что дополнительные параметры должны быть включены в запрос.  Параметры задаются как фрагмент строки запроса, используя следующую форму: `“param1=value1&param2=value2&param3=value3”` и т. д. **Note:**  В файле конфигурации "&" символа в строке запроса должен быть указан с помощью ссылки на сущность его `&`.|  
|signOutQueryString|Предоставляет точку расширения среды для указания приложения определены параметры запроса в URL\-АДРЕСЕ WS\-Federation запрос на вход.  Необязательный.  По умолчанию используется пустая строка, которая указывает, что дополнительные параметры должны быть включены в запрос.  Параметры задаются как фрагмент строки запроса, используя следующую форму: `“param1=value1&param2=value2&param3=value3”` и т. д. **Note:**  В файле конфигурации "&" символа в строке запроса должен быть указан с помощью ссылки на сущность его `&`.|  
|signOutReply|Задает URL\-адрес, к которому следует перенаправлять клиента, служба маркеров безопасности \(STS\) во время выхода из системы через протокол WS\-Federation пассивный.  Задает для параметра wreply на запрос WS\-Federation выхода из системы.  Необязательный.  По умолчанию используется пустая строка, которая указывает, что дополнительные параметры должны быть включены в запрос.|  
  
### Дочерние элементы  
 None  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<federationConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|Содержит параметры, <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> \(WSFAM\) и <xref:System.IdentityModel.Services.SessionAuthenticationModule> \(SAM\).|  
  
## Заметки  
 Можно использовать `<wsFederation>` элемент настройки WS\-Federation параметр параметры по умолчанию и поведение по умолчанию для WSFAM.  WS\-Federation параметров, определенных в разделе `<wsFederation>` элемента набор эквивалентных свойств, предоставленных <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> класса.  Эти свойства будут одинаковыми для всех запросов, выданных WSFAM.  Динамическое изменение параметров WS\-Federation во время обработки путем добавления обработчиков событий для событий, предоставленных WSFAM; например <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectingToIdentityProvider> событий.  Дополнительные сведения см. в документации по классу <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>.  
  
 `<wsFederation>` Представленного элементом <xref:System.IdentityModel.Services.Configuration.WSFederationElement> класса.  Представленный самого объекта конфигурации <xref:System.IdentityModel.Services.Configuration.WSFederationConfiguration> класса.  Один <xref:System.IdentityModel.Services.Configuration.WSFederationConfiguration> экземпляр устанавливается на <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> объекта, к которому осуществляется через <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=fullName> свойства, а также настройки для WSFAM.  
  
## Пример  
 Это показано в следующем XML `<wsFederation>` элемент, который определяет параметры для WSFAM.  
  
> [!WARNING]
>  В этом примере WSFAM не требуется использовать протокол HTTPS.  Это происходит потому, что `requireHttps` атрибут на `<wsFederation>` элемента `false`.  Этот параметр не рекомендуется для большинства рабочих средах, как он может представлять угрозу безопасности.  
  
```  
<wsFederation passiveRedirectEnabled="true"   
  issuer="http://localhost:15839/wsFederationSTS/Issue"   
  realm="http://localhost:50969/"   
  reply="http://localhost:50969/"   
  requireHttps="false"   
  signOutReply="http://localhost:50969/SignedOutPage.html"   
  signOutQueryString="Param1=value2&Param2=value2"   
  persistentCookiesOnPassiveRedirects="true" />  
  
```  
  
## См. также  
 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>   
 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=fullName>