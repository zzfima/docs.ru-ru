---
title: "Неподдерживаемые сценарии | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 72027d0f-146d-40c5-9d72-e94392c8bb40
caps.latest.revision: 43
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 39
---
# Неподдерживаемые сценарии
По различным причинам [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] не поддерживает некоторые сценарии безопасности. Например, в операционной системе [!INCLUDE[wxp](../../../../includes/wxp-md.md)] не реализованы протоколы проверки подлинности SSPI и Kerberos, поэтому [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не поддерживает на этой платформе выполнение служб с проверкой подлинности Windows. При использовании [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в ОС Windows XP Home Edition поддерживаются другие механизмы проверки подлинности, такие как проверка имени пользователя и пароля и встроенная проверка подлинности HTTP\/HTTPS.  
  
## Сценарии олицетворения  
  
### Олицетворенное удостоверение может не работать, если клиенты совершают асинхронные вызовы  
 Если клиент WCF выполняет асинхронные вызовы службы WCF, используя проверку подлинности Windows при олицетворении, может иметь место проверка подлинности с удостоверением клиентского процесса, а не олицетворенным удостоверением.  
  
### Windows XP и включенные файлы Cookie маркера контекста безопасности  
 При выполнении следующих условий [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не поддерживает олицетворение, и выдается исключение <xref:System.InvalidOperationException>.  
  
-   Операционной системой является [!INCLUDE[wxp](../../../../includes/wxp-md.md)].  
  
-   Режим проверки подлинности имеет результатом удостоверение Windows.  
  
-   Свойству <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> класса <xref:System.ServiceModel.OperationBehaviorAttribute> присваивается значение <xref:System.ServiceModel.ImpersonationOption>.  
  
-   Создан маркер контекста безопасности с отслеживанием состояния \(SCT\) \(по умолчанию создание отключено\).  
  
 Маркер SCT с отслеживанием состояния создается только с использованием пользовательской привязки.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Как создать маркер контекста безопасности с отслеживанием состояния для безопасного сеанса](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).\) В коде маркер включается путем создания элемента привязки безопасности \(<xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> или <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>\) с помощью метода <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSspiNegotiationBindingElement%28System.Boolean%29?displayProperty=fullName> или <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%28System.ServiceModel.Channels.SecurityBindingElement%2CSystem.Boolean%29?displayProperty=fullName> и присвоения параметру `requireCancellation` значения `false`. Параметр относится к кэшированию маркера SCT. Задание значения `false` включает функцию маркера SCT с отслеживанием состояния.  
  
 Аналогично, маркер включается в конфигурации путем создания привязки \<`customBinding`\>, последующего добавления элемента \<`security`\>, присвоения атрибуту `authenticationMode` значения SecureConversation и присвоения атрибуту `requireSecurityContextCancellation` значения `true`.  
  
> [!NOTE]
>  Эти требования зависят от конкретной ситуации. Например, метод <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A> создает элемент привязки, который имеет результатом удостоверение Windows, однако не устанавливает маркер SCT. Поэтому его можно использовать с параметром `Required` в ОС [!INCLUDE[wxp](../../../../includes/wxp-md.md)].  
  
### Возможный конфликт ASP.NET  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] позволяют включать и отключать олицетворение. Если в [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] размещается приложение [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], может возникнуть конфликт между параметрами конфигурации [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]. В случае конфликта приоритет имеет параметр [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] за исключением ситуации, когда свойству <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> присвоено значение <xref:System.ServiceModel.ImpersonationOption>. В этом случае приоритет имеет параметр олицетворения [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].  
  
### Возможный сбой загрузки сборки при олицетворении  
 Если олицетворенный контекст не имеет прав доступа для загрузки сборки и если это первая попытка загрузки этой сборки в среде CLR для этого домена приложения, в <xref:System.AppDomain> кэшируется ошибка. Последующие попытки загрузки сборки \(или сборок\) также окажутся неудачными, даже если олицетворение отменено, а восстановленный контекст имеет права доступа для загрузки сборки. Это обусловлено тем, что в среде CLR не производится повторная попытка загрузки после изменения контекста пользователя. Для восстановления после сбоя необходимо повторно запустить домен приложения.  
  
> [!NOTE]
>  Свойство <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> класса <xref:System.ServiceModel.Security.WindowsClientCredential> имеет значение по умолчанию <xref:System.Security.Principal.TokenImpersonationLevel>. В большинстве случаев контекст олицетворения уровня идентификации не имеет прав на загрузку дополнительных сборок. Это значение по умолчанию, поэтому необходимо учитывать это очень распространенное условие. Олицетворение на уровне идентификации также происходит, когда процесс олицетворения не имеет привилегии `SeImpersonate`.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Делегирование и олицетворение](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md).  
  
### Для делегирования требуется согласование учетных данных  
 Для использования протокола проверки подлинности Kerberos с делегированием необходимо реализовать протокол Kerberos с согласованием учетных данных \(иногда называется многоступенчатой проверкой подлинности Kerberos\). Если проверка подлинности Kerberos реализована без согласования учетных данных \(иногда называется одноступенчатой проверкой подлинности Kerberos\), возникает исключение.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] том, как реализовать согласование учетных данных, см. в разделе [Отладка ошибок проверки подлинности Windows](../../../../docs/framework/wcf/feature-details/debugging-windows-authentication-errors.md).  
  
## Шифрование  
  
### Алгоритм SHA\-256 поддерживается только для симметричных ключей  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает различные алгоритмы шифрования и создания дайджеста подписи, которые можно указать с помощью набора алгоритмов в привязках, предоставляемых системой. С целью повышения уровня безопасности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает алгоритмы SHA 2 \(Secure Hash Algorithm\), в частности алгоритм SHA\-256, для создания хэшей дайджестов подписи. Этот выпуск поддерживает алгоритм SHA\-256 только для симметричных ключей \(например, ключей Kerberos\) и случаев, когда сертификат X.509 не используется для подписи сообщения.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не поддерживает сигнатуры RSA \(используемые в сертификатах X.509\) с использованием хэша SHA\-256 из\-за отсутствия текущей поддержки RSA\-SHA256 в [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)].  
  
### FIPS\-совместимые хэши SHA\-256 не поддерживаются  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не поддерживает FIPS\-совместимые хэши SHA\-256, поэтому наборы алгоритмов, использующие SHA\-256, не поддерживаются в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в тех системах, в которых требуется применять FIPS\-совместимые алгоритмы.  
  
### Возможен сбой FIPS\-совместимых алгоритмов в случае изменения реестра  
 Включать и отключать FIPS\-совместимые алгоритмы можно с помощью оснастки «Локальные параметры безопасности» консоли управления \(MMC\). Кроме того, можно получить доступ к этому параметру в реестре. Однако следует обратить внимание на то, что [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не поддерживает задание параметра путем изменения реестра. Задание значения, отличного от 1 или 0, может привести к противоречивым результатам в среде CLR и операционной системе.  
  
### Ограничение FIPS\-совместимого алгоритма шифрования AES  
 FIPS\-совместимый алгоритм шифрования AES не работает в дуплексных обратных вызовах при олицетворении на уровне идентификации.  
  
### Сертификаты CNG\/KSP в ОС Windows Server 2008  
 *API криптографии следующего поколения \(CNG\)* служит долгосрочной заменой CryptoAPI. Этот API доступен в неуправляемом коде в ОС [!INCLUDE[wv](../../../../includes/wv-md.md)] и [!INCLUDE[lserver](../../../../includes/lserver-md.md)].  
  
 В операционных системах предыдущих версий \([!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] и [!INCLUDE[wxp](../../../../includes/wxp-md.md)]\) платформа .NET Framework 2.0 не распознает этот протокол и использует вместо него для обработки сертификатов CNG\/KSP устаревший интерфейс *CryptoApi*. В ОС [!INCLUDE[lserver](../../../../includes/lserver-md.md)] и [!INCLUDE[wv](../../../../includes/wv-md.md)] платформа .NET Framework 3.5 не поддерживает такие сертификаты \- при их использовании возникает исключение.  
  
 Узнать, используется ли в сертификате KSP, можно двумя способами.  
  
-   Сделайте платформозависимый вызов `p/invoke` функции `CertGetCertificateContextProperty` и проверьте свойство `dwProvType` возвращенного объекта `CertGetCertificateContextProperty`.  
  
-   Выполните команду `certutil` в командной строке для запроса сертификатов.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][устранение неполадок, связанных с сертификатами, с помощью Certutil](http://go.microsoft.com/fwlink/?LinkId=120056).  
  
## Сбой безопасности сообщений при использовании олицетворения ASP.NET и режима совместимости ASP.NET  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не поддерживает следующую комбинацию параметров, поскольку в этом случае может не выполняться проверка подлинности клиента.  
  
-   Включено олицетворение [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]. Для этого в файле Web.config атрибуту `impersonate` элемента \<`identity`\> присвоено значение `true`.  
  
-   Включен режим совместимости [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] путем присвоения атрибуту `aspNetCompatibilityEnabled` элемента [\<serviceHostingEnvironment\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) значения `true`.  
  
-   Используется режим безопасности сообщения.  
  
 Временное решение \- отключить режим совместимости [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]. Либо, если требуется режим совместимости [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], отключить функцию олицетворения [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] и использовать вместо нее олицетворение, предусмотренное в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Делегирование и олицетворение](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md).  
  
## Ошибка литерального адреса IPv6  
 Если клиент и служба находятся на одном компьютере, а для службы используются литеральные адреса IPv6, происходит сбой запросов безопасности.  
  
 Литеральные адреса IPv6 можно использовать, если служба и клиент находятся на разных компьютерах.  
  
## Ошибка извлечения WSDL с федеративным доверием  
 В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] требуется, чтобы для каждого узла в федеративной цепи доверия был точно один документ WSDL. Следует быть внимательным, чтобы не создать замкнутый цикл при задании конечных точек. Например, замкнутый цикл появляется при использовании загрузки WSDL федеративной цепи доверия с несколькими ссылками в одном документе WSDL. Типичной ситуацией, в которой может возникать эта проблема, служит федеративная служба, в которой сервер маркера безопасности и служба находятся в одном узле ServiceHost.  
  
 Ниже приведен пример службы с тремя адресами конечных точек:  
  
-   http:\/\/localhost\/CalculatorService\/service \(служба\)  
  
-   http:\/\/localhost\/CalculatorService\/issue\_ticket \(служба маркеров безопасности\)  
  
-   http:\/\/localhost\/CalculatorService\/mex \(конечная точка метаданных\)  
  
 В этом случае создается исключение.  
  
 Чтобы этот сценарий работал, необходимо разместить конечную точку `issue_ticket` в каком\-либо другом месте.  
  
## Возможная потеря атрибутов импорта WSDL  
 WCF теряет атрибуты элемента `<wst:Claims>` в шаблоне `RST` при выполнении импорта WSDL. Это происходит при импорте WSDL, если `<Claims>` заданы непосредственно в `WSFederationHttpBinding.Security.Message.TokenRequestParameters` или `IssuedSecurityTokenRequestParameters.AdditionalRequestParameters` вместо использования коллекций типов утверждений.  Вследствие потери атрибутов при импорте привязка не выполняет надлежащим образом полный цикл через WSDL и поэтому является неверной на стороне клиента.  
  
 Для устранения этой проблемы необходимо изменить привязку непосредственно в клиенте после выполнения импорта.  
  
## См. также  
 [Вопросы безопасности](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)   
 [Раскрытие информации](../../../../docs/framework/wcf/feature-details/information-disclosure.md)   
 [Повышение прав доступа](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)   
 [Отказ в обслуживании](../../../../docs/framework/wcf/feature-details/denial-of-service.md)   
 [Подделка](../../../../docs/framework/wcf/feature-details/tampering.md)   
 [Атаки с повторением](../../../../docs/framework/wcf/feature-details/replay-attacks.md)