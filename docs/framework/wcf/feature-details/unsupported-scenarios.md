---
title: Неподдерживаемые сценарии
ms.date: 03/30/2017
ms.assetid: 72027d0f-146d-40c5-9d72-e94392c8bb40
ms.openlocfilehash: 884349739730510c356e1efc1f866d146f6ed946
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2019
ms.locfileid: "65959964"
---
# <a name="unsupported-scenarios"></a>Неподдерживаемые сценарии
По различным причинам Windows Communication Foundation (WCF) не поддерживает некоторые сценарии безопасности. Например [!INCLUDE[wxp](../../../../includes/wxp-md.md)] Home Edition не реализует протоколы проверки подлинности SSPI и Kerberos, и поэтому WCF не поддерживает запуск службы с проверкой подлинности Windows на этой платформе. При выполнении WCF под Windows XP Home Edition, поддерживаются другие механизмы проверки подлинности, такие как имя пользователя и пароль и встроенная проверка подлинности HTTP/HTTPS.  
  
## <a name="impersonation-scenarios"></a>Сценарии олицетворения  
  
### <a name="impersonated-identity-might-not-flow-when-clients-make-asynchronous-calls"></a>Олицетворенное удостоверение может не работать, если клиенты совершают асинхронные вызовы  
 Если клиент WCF выполняет асинхронные вызовы службы WCF, используя проверку подлинности Windows при олицетворении, может иметь место проверка подлинности с удостоверением клиентского процесса, а не олицетворенным удостоверением.  
  
### <a name="windows-xp-and-secure-context-token-cookie-enabled"></a>Windows XP и включенные файлы Cookie маркера контекста безопасности  
 WCF не поддерживает олицетворение и <xref:System.InvalidOperationException> возникает исключение при выполнении следующих условий:  
  
- Операционной системой является [!INCLUDE[wxp](../../../../includes/wxp-md.md)].  
  
- Режим проверки подлинности имеет результатом удостоверение Windows.  
  
- Свойству <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> класса <xref:System.ServiceModel.OperationBehaviorAttribute> присваивается значение <xref:System.ServiceModel.ImpersonationOption.Required>.  
  
- Создан маркер контекста безопасности с отслеживанием состояния (SCT) (по умолчанию создание отключено).  
  
 Маркер SCT с отслеживанием состояния создается только с использованием пользовательской привязки. Дополнительные сведения см. в разделе [Практическое руководство. Создайте контекст безопасности маркера для безопасного сеанса](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).) В коде маркер включается путем создания элемента привязки безопасности (<xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> или <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>) с помощью метода <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSspiNegotiationBindingElement%28System.Boolean%29?displayProperty=nameWithType> или <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%28System.ServiceModel.Channels.SecurityBindingElement%2CSystem.Boolean%29?displayProperty=nameWithType> и присвоения параметру `requireCancellation` значения `false`. Параметр относится к кэшированию маркера SCT. Задание значения `false` включает функцию маркера SCT с отслеживанием состояния.  
  
 Кроме того, в конфигурации, маркер включается путем создания <`customBinding`>, добавив <`security`> и задав `authenticationMode` атрибут SecureConversation и `requireSecurityContextCancellation` атрибут `true`.  
  
> [!NOTE]
>  Эти требования зависят от конкретной ситуации. Например, метод <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A> создает элемент привязки, который имеет результатом удостоверение Windows, однако не устанавливает маркер SCT. Поэтому его можно использовать с параметром `Required` в ОС [!INCLUDE[wxp](../../../../includes/wxp-md.md)].  
  
### <a name="possible-aspnet-conflict"></a>Возможный конфликт ASP.NET  
 WCF и ASP.NET можно как включать и отключать олицетворение. Когда ASP.NET размещает приложение WCF, может возникнуть конфликт между параметрами конфигурации WCF и ASP.NET. В случае конфликта WCF параметра имеет приоритет, если <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> свойству <xref:System.ServiceModel.ImpersonationOption.NotAllowed>, в этом случае параметр олицетворения ASP.NET имеет приоритет.  
  
### <a name="assembly-loads-may-fail-under-impersonation"></a>Возможный сбой загрузки сборки при олицетворении  
 Если олицетворенный контекст не имеет прав доступа для загрузки сборки и если это первая попытка загрузки этой сборки в среде CLR для этого домена приложения, в <xref:System.AppDomain> кэшируется ошибка. Последующие попытки загрузки сборки (или сборок) также окажутся неудачными, даже если олицетворение отменено, а восстановленный контекст имеет права доступа для загрузки сборки. Это обусловлено тем, что в среде CLR не производится повторная попытка загрузки после изменения контекста пользователя. Для восстановления после сбоя необходимо повторно запустить домен приложения.  
  
> [!NOTE]
>  Свойство <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> класса <xref:System.ServiceModel.Security.WindowsClientCredential> имеет значение по умолчанию <xref:System.Security.Principal.TokenImpersonationLevel.Identification>. В большинстве случаев контекст олицетворения уровня идентификации не имеет прав на загрузку дополнительных сборок. Это значение по умолчанию, поэтому необходимо учитывать это очень распространенное условие. Олицетворение на уровне идентификации также происходит, когда процесс олицетворения не имеет привилегии `SeImpersonate`. Дополнительные сведения см. в разделе [делегирование и олицетворение](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md).  
  
### <a name="delegation-requires-credential-negotiation"></a>Для делегирования требуется согласование учетных данных  
 Для использования протокола проверки подлинности Kerberos с делегированием необходимо реализовать протокол Kerberos с согласованием учетных данных (иногда называется многоступенчатой проверкой подлинности Kerberos). Если проверка подлинности Kerberos реализована без согласования учетных данных (иногда называется одноступенчатой проверкой подлинности Kerberos), возникает исключение. Дополнительные сведения о том, как реализовать согласование учетных данных см. в разделе [Отладка ошибок проверки подлинности Windows](../../../../docs/framework/wcf/feature-details/debugging-windows-authentication-errors.md).  
  
## <a name="cryptography"></a>Шифрование  
  
### <a name="sha-256-supported-only-for-symmetric-key-usages"></a>Алгоритм SHA-256 поддерживается только для симметричных ключей  
 WCF поддерживает широкий набор алгоритмов шифрования и подписи хэш-кода создания, которые можно указать с помощью набор алгоритмов в привязках, предоставляемых системой. В целях безопасности WCF поддерживает алгоритмы Secure Hash Algorithm (SHA) 2, в частности алгоритм SHA-256, для создания хэш-кодов подписи. Этот выпуск поддерживает алгоритм SHA-256 только для симметричных ключей (например, ключей Kerberos) и случаев, когда сертификат X.509 не используется для подписи сообщения. WCF не поддерживает сигнатуры RSA (используемые в сертификатах X.509) с использованием хэша SHA-256 из-за отсутствия текущей поддержки RSA-SHA256 в WinFX.  
  
### <a name="fips-compliant-sha-256-hashes-not-supported"></a>FIPS-совместимые хэши SHA-256 не поддерживаются  
 WCF не поддерживает SHA-256 FIPS-совместимые хэши, поэтому наборы алгоритмов, использующие SHA-256 не поддерживаются платформой WCF в системах, где требуется использовать FIPS-совместимые алгоритмы.  
  
### <a name="fips-compliant-algorithms-may-fail-if-registry-is-edited"></a>Возможен сбой FIPS-совместимых алгоритмов в случае изменения реестра  
 Включать и отключать FIPS-совместимые алгоритмы можно с помощью оснастки «Локальные параметры безопасности» консоли управления (MMC). Кроме того, можно получить доступ к этому параметру в реестре. Обратите внимание, что WCF не поддерживает использование параметра реестра. Задание значения, отличного от 1 или 0, может привести к противоречивым результатам в среде CLR и операционной системе.  
  
### <a name="fips-compliant-aes-encryption-limitation"></a>Ограничение FIPS-совместимого алгоритма шифрования AES  
 FIPS-совместимый алгоритм шифрования AES не работает в дуплексных обратных вызовах при олицетворении на уровне идентификации.  
  
### <a name="cngksp-certificates"></a>Сертификаты CNG/KSP  
 *Интерфейс API криптографии: Next Generation (CNG)* является долгосрочной заменой CryptoAPI. Этот API доступен в неуправляемом коде на [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[lserver](../../../../includes/lserver-md.md)] и более поздних версиях Windows.  
  
 .NET framework 4.6.1 и более ранних версий не поддерживают эти сертификаты, потому что они используют устаревшие CryptoAPI для обработки сертификатов CNG/KSP. Использование сертификатов с помощью .NET Framework 4.6.1 и более ранних версий вызовет исключение.  
  
 Узнать, используется ли в сертификате KSP, можно двумя способами.  
  
- Сделайте платформозависимый вызов `p/invoke` функции `CertGetCertificateContextProperty` и проверьте свойство `dwProvType` возвращенного объекта `CertGetCertificateContextProperty`.  
  
- Используйте `certutil` команду из командной строки для запроса сертификатов. Дополнительные сведения см. в разделе [Задачи Certutil для устранения неполадок сертификатов](https://go.microsoft.com/fwlink/?LinkId=120056).  
  
## <a name="message-security-fails-if-using-aspnet-impersonation-and-aspnet-compatibility-is-required"></a>Сбой безопасности сообщений при использовании олицетворения ASP.NET и режима совместимости ASP.NET  
 WCF не поддерживает следующую комбинацию параметров, так как они могут помешать выполняться проверка подлинности клиента:  
  
- Включено олицетворение ASP.NET. Это делается в файле Web.config, задав `impersonate` атрибут <`identity`> элемент `true`.  
  
- Режим совместимости с ASP.NET можно включить, задав `aspNetCompatibilityEnabled` атрибут [ \<serviceHostingEnvironment >](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) для `true`.  
  
- Используется режим безопасности сообщения.  
  
 Обходным путем является для отключения режима совместимости ASP.NET. Или, если требуется режим совместимости с ASP.NET, отключить возможность олицетворения ASP.NET и вместо этого используйте олицетворение, предоставляемую платформой WCF. Дополнительные сведения см. в разделе [делегирование и олицетворение](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md).  
  
## <a name="ipv6-literal-address-failure"></a>Ошибка литерального адреса IPv6  
 Если клиент и служба находятся на одном компьютере, а для службы используются литеральные адреса IPv6, происходит сбой запросов безопасности.  
  
 Литеральные адреса IPv6 можно использовать, если служба и клиент находятся на разных компьютерах.  
  
## <a name="wsdl-retrieval-failures-with-federated-trust"></a>Ошибка извлечения WSDL с федеративным доверием  
 WCF требуется ровно один документ WSDL для каждого узла в федеративной цепи доверия. Следует быть внимательным, чтобы не создать замкнутый цикл при задании конечных точек. Например, замкнутый цикл появляется при использовании загрузки WSDL федеративной цепи доверия с несколькими ссылками в одном документе WSDL. Типичной ситуацией, в которой может возникать эта проблема, служит федеративная служба, в которой сервер маркера безопасности и служба находятся в одном узле ServiceHost.  
  
 Ниже приведен пример службы с тремя адресами конечных точек:  
  
- `http://localhost/CalculatorService/service` (служба)  
  
- `http://localhost/CalculatorService/issue_ticket` (STS)  
  
- `http://localhost/CalculatorService/mex` (конечная точка метаданных)  
  
 В этом случае создается исключение.  
  
 Чтобы этот сценарий работал, необходимо разместить конечную точку `issue_ticket` в каком-либо другом месте.  
  
## <a name="wsdl-import-attributes-can-be-lost"></a>Возможная потеря атрибутов импорта WSDL  
 WCF теряет атрибуты элемента `<wst:Claims>` в шаблоне `RST` при выполнении импорта WSDL. Это происходит при импорте WSDL, если `<Claims>` заданы непосредственно в `WSFederationHttpBinding.Security.Message.TokenRequestParameters` или `IssuedSecurityTokenRequestParameters.AdditionalRequestParameters` вместо использования коллекций типов утверждений.  Вследствие потери атрибутов при импорте привязка не выполняет надлежащим образом полный цикл через WSDL и поэтому является неверной на стороне клиента.  
  
 Для устранения этой проблемы необходимо изменить привязку непосредственно в клиенте после выполнения импорта.  
  
## <a name="see-also"></a>См. также

- [Вопросы безопасности](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)
- [Раскрытие информации](../../../../docs/framework/wcf/feature-details/information-disclosure.md)
- [Повышение привилегий](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)
- [Отказ в обслуживании](../../../../docs/framework/wcf/feature-details/denial-of-service.md)
- [Подделка](../../../../docs/framework/wcf/feature-details/tampering.md)
- [Атаки с повторением](../../../../docs/framework/wcf/feature-details/replay-attacks.md)
