---
title: "&lt;securityTokenHandlerConfiguration&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# &lt;securityTokenHandlerConfiguration&gt;
Содержит настройки для коллекции обработчиков маркеров.  
  
## Синтаксис  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration saveBootstrapContext=xs:boolean  
          maximumClockSkew=TimeSpan>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние элементы и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|saveBootstrapContext|Указывает, включены ли загрузочный маркеров в маркер сеанса.  Также возможно установить значение на коллекции обработчик маркеров, задав `saveBootstrapContext` атрибут на [\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемент.  Значение в коллекцию обработчиков маркеров переопределяет значение, заданное на службу.|  
|maximumClockSkew|A <xref:System.TimeSpan> , определяющий максимальное разрешенные часы Наклон.  Управляет Наклон максимальное разрешенные часы при выполнении операций с учетом времени, такие как проверка время истечения срока действия сеанса входа.  Значение по умолчанию — 5 минут "00: 05".  Дополнительные сведения об указании <xref:System.TimeSpan> значения, см. [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_TimespanValues).  Также возможно установить Наклон максимального времени на уровне службы, задав `maximumClockSkew` атрибут на [\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемент.  Значение в коллекцию обработчиков маркеров переопределяет значение, заданное на службу.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<audienceUris\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)|Задает набор URI, допустимые идентификаторы требует доверяющая сторона.  Необязательный.|  
|[\<caches\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|Регистрирует кэши для обнаружения маркеров преобразования и маркеров сеансов.  Задается на уровне службы или на коллекцию обработчика маркера безопасности.  Необязательный.|  
|[\<certificateValidation\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|Управляет параметрами, обработчиков маркеров для проверки сертификатов.  Задается на уровне службы или на коллекцию обработчика маркера безопасности.  Эти параметры будут переопределены, если определенный обработчик настроен с помощью собственного проверяющего элемента управления.  Необязательный.|  
|[\<issuerNameRegistry\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|Настройка реестра имя поставщика, используемый в коллекцию обработчиков маркеров обработчики.  Необязательный.|  
|[\<issuerTokenResolver\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)|Регистрирует поставщика Распознавателю маркеров, используемые в коллекцию обработчиков маркеров обработчики.  Распознавателю маркеров поставщика используется для разрешения подписи маркера для входящих сообщений и лексем.  Необязательный.|  
|[\<serviceTokenResolver\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)|Регистрирует Распознавателю маркеров службы, используемые в коллекцию обработчиков маркеров обработчики.  Распознавателю маркеров службы используется для разрешения маркера шифрования на входящих токенов и сообщения.  Необязательный.|  
|[\<tokenReplayDetection\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|Включает маркера повторений и определяет срок действия маркеров.  Задается на уровне службы или на коллекцию обработчика маркера безопасности.  Необязательный.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<securityTokenHandlers\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|Указывает коллекции обработчиков маркеров безопасности, которые зарегистрированы с конечной точкой.|  
  
## Заметки  
 Этот раздел содержит значения свойств для <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> объект.  Параметры, настроенные в этом разделе переопределение настроены на службу.  Некоторые из этих параметров может в свою очередь, переопределены параметрами, указываются при добавлении обработчик в коллекцию обработчиков маркеров безопасности.  
  
## Пример  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>   
      <securityTokenHandlerConfiguration>  
  
        <audienceUris>  
          <clear/>  
          <add value="http://www.example.com/myapp/" />  
        </audienceUris>  
  
        <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel">  
          <trustedIssuers>  
            <add thumbprint="97249e1a … 4c9158de" name="contoso.com" />  
          </trustedIssuers>  
        </issuerNameRegistry>  
  
        <issuerTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
  
        <serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```