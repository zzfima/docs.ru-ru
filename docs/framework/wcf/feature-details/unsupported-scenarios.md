---
title: Неподдерживаемые сценарии
ms.date: 03/30/2017
ms.assetid: 72027d0f-146d-40c5-9d72-e94392c8bb40
ms.openlocfilehash: a963b46d22f2103cddcc8fd080feefc39070690c
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901266"
---
# <a name="unsupported-scenarios"></a>Неподдерживаемые сценарии

По различным причинам Windows Communication Foundation (WCF) не поддерживает некоторые конкретные сценарии безопасности. Например, [!INCLUDE[wxp](../../../../includes/wxp-md.md)] Home Edition не реализует протоколы проверки подлинности SSPI или Kerberos, поэтому WCF не поддерживает запуск службы с проверкой подлинности Windows на этой платформе. Другие механизмы проверки подлинности, такие как имя пользователя и пароль и встроенная проверка подлинности HTTP/HTTPS, поддерживаются при запуске WCF в Windows XP Home Edition.

## <a name="impersonation-scenarios"></a>Сценарии олицетворения

### <a name="impersonated-identity-might-not-flow-when-clients-make-asynchronous-calls"></a>Олицетворенная идентификация может не поступать, когда клиенты выполняют асинхронные вызовы
 Если клиент WCF выполняет асинхронные вызовы службы WCF, используя проверку подлинности Windows при олицетворении, может иметь место проверка подлинности с удостоверением клиентского процесса, а не олицетворенным удостоверением.

### <a name="windows-xp-and-secure-context-token-cookie-enabled"></a>Windows XP и файл cookie токена защищенного контекста включены

WCF не поддерживает олицетворение, и при выполнении следующих условий возникает <xref:System.InvalidOperationException>.

- Операционной системой является [!INCLUDE[wxp](../../../../includes/wxp-md.md)].

- Режим проверки подлинности имеет результатом удостоверение Windows.

- Свойству <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> класса <xref:System.ServiceModel.OperationBehaviorAttribute> присваивается значение <xref:System.ServiceModel.ImpersonationOption.Required>.

- Создан маркер контекста безопасности с отслеживанием состояния (SCT) (по умолчанию создание отключено).

 Маркер SCT с отслеживанием состояния создается только с использованием пользовательской привязки. Дополнительные сведения см. [в разделе инструкции. Создание маркера контекста безопасности для безопасного сеанса](how-to-create-a-security-context-token-for-a-secure-session.md). В коде маркер включается путем создания элемента привязки безопасности (<xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> или <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>) с помощью <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSspiNegotiationBindingElement%28System.Boolean%29?displayProperty=nameWithType> или метода <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%28System.ServiceModel.Channels.SecurityBindingElement%2CSystem.Boolean%29?displayProperty=nameWithType> и установки для параметра `requireCancellation` значения `false`. Параметр относится к кэшированию маркера SCT. Задание значения `false` включает функцию маркера SCT с отслеживанием состояния.

 Кроме того, в конфигурации маркер включается путем создания <`customBinding`>, добавления <`security`> и присвоения атрибуту `authenticationMode` значения SecureConversation, а `requireSecurityContextCancellation` — `true`.

> [!NOTE]
> Эти требования зависят от конкретной ситуации. Например, метод <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A> создает элемент привязки, который имеет результатом удостоверение Windows, однако не устанавливает маркер SCT. Поэтому его можно использовать с параметром `Required` в ОС [!INCLUDE[wxp](../../../../includes/wxp-md.md)].

### <a name="possible-aspnet-conflict"></a>Возможный конфликт ASP.NET

WCF и ASP.NET могут включать и отключать олицетворение. Когда ASP.NET размещает приложение WCF, между параметрами конфигурации WCF и ASP.NET может существовать конфликт. В случае конфликта параметру WCF присваивается приоритет, если только свойство <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> не имеет значение <xref:System.ServiceModel.ImpersonationOption.NotAllowed>. в этом случае параметр олицетворения ASP.NET имеет приоритет.

### <a name="assembly-loads-may-fail-under-impersonation"></a>Загрузка сборок может завершиться ошибкой при олицетворении

Если олицетворенный контекст не имеет прав доступа для загрузки сборки и если это первая попытка загрузки этой сборки в среде CLR для этого домена приложения, в <xref:System.AppDomain> кэшируется ошибка. Последующие попытки загрузки сборки (или сборок) также окажутся неудачными, даже если олицетворение отменено, а восстановленный контекст имеет права доступа для загрузки сборки. Это обусловлено тем, что среда CLR не выполняет повторную загрузку после изменения контекста пользователя. Для восстановления после сбоя необходимо повторно запустить домен приложения.

> [!NOTE]
> Свойство <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> класса <xref:System.ServiceModel.Security.WindowsClientCredential> имеет значение по умолчанию <xref:System.Security.Principal.TokenImpersonationLevel.Identification>. В большинстве случаев контекст олицетворения уровня идентификации не имеет прав на загрузку дополнительных сборок. Это значение по умолчанию, поэтому необходимо учитывать это очень распространенное условие. Олицетворение на уровне идентификации также происходит, когда процесс олицетворения не имеет привилегии `SeImpersonate`. Дополнительные сведения см. в разделе [Делегирование и олицетворение](delegation-and-impersonation-with-wcf.md).

### <a name="delegation-requires-credential-negotiation"></a>Делегирование требует согласования учетных данных

Для использования протокола проверки подлинности Kerberos с делегированием необходимо реализовать протокол Kerberos с согласованием учетных данных (иногда называется многоступенчатой проверкой подлинности Kerberos). Если проверка подлинности Kerberos реализована без согласования учетных данных (иногда называется одноступенчатой проверкой подлинности Kerberos), возникает исключение. Дополнительные сведения о реализации согласования учетных данных см. в разделе [Отладка ошибок проверки подлинности Windows](debugging-windows-authentication-errors.md).

## <a name="cryptography"></a>Шифрование

### <a name="sha-256-supported-only-for-symmetric-key-usages"></a>SHA-256 поддерживается только для использования симметричных ключей

WCF поддерживает различные алгоритмы создания шифрования и дайджеста подписи, которые можно указать с помощью набора алгоритмов в привязках, предоставляемых системой. Для повышения безопасности WCF поддерживает алгоритмы SHA 2, в частности SHA-256, для создания хэшей дайджеста подписи. Этот выпуск поддерживает алгоритм SHA-256 только для симметричных ключей (например, ключей Kerberos) и случаев, когда сертификат X.509 не используется для подписи сообщения. WCF не поддерживает подписи RSA (используемые в сертификатах X. 509) с помощью хэша SHA-256 из-за текущего отсутствия поддержки RSA-SHA256 в WinFX.

### <a name="fips-compliant-sha-256-hashes-not-supported"></a>Хэши SHA-256, совместимые с FIPS, не поддерживаются

WCF не поддерживает хэши SHA-256, совместимые с FIPS, поэтому наборы алгоритмов, использующие SHA-256, не поддерживаются WCF в системах, где требуется использовать алгоритмы, совместимые с FIPS.

### <a name="fips-compliant-algorithms-may-fail-if-registry-is-edited"></a>Алгоритмы, совместимые с FIPS, могут завершиться ошибкой, если изменяется реестр

Включать и отключать FIPS-совместимые алгоритмы можно с помощью оснастки «Локальные параметры безопасности» консоли управления (MMC). Кроме того, можно получить доступ к этому параметру в реестре. Однако обратите внимание, что WCF не поддерживает использование реестра для сброса параметра. Задание значения, отличного от 1 или 0, может привести к противоречивым результатам в среде CLR и операционной системе.

### <a name="fips-compliant-aes-encryption-limitation"></a>Ограничение FIPS-совместимого шифрования AES

Шифрование AES, совместимое с FIPS, не работает в дуплексных обратных вызовах в рамках олицетворения на уровне идентификации.

### <a name="cngksp-certificates"></a>Сертификаты CNG и KSP

*API шифрования: следующее поколение (CNG)* — это долгосрочная замена интерфейса CryptoAPI. Этот API доступен в неуправляемом коде в Windows Vista, Windows Server 2008 и более поздних версиях Windows.

 .NET Framework 4.6.1 и более ранние версии не поддерживают эти сертификаты, так как они используют устаревший интерфейс CryptoAPI для работы с сертификатами CNG и KSP. Использование этих сертификатов с .NET Framework 4.6.1 и более ранними версиями вызовет исключение.

 Узнать, используется ли в сертификате KSP, можно двумя способами.

- Сделайте платформозависимый вызов `p/invoke` функции `CertGetCertificateContextProperty` и проверьте свойство `dwProvType` возвращенного объекта `CertGetCertificateContextProperty`.

- Используйте команду `certutil` из командной строки для запроса сертификатов. Дополнительные сведения см. в [статье certutil Tasks for устранение неполадок сертификатов](https://docs.microsoft.com/previous-versions/orphan-topics/ws.10/cc772619(v=ws.10)).

## <a name="message-security-fails-if-using-aspnet-impersonation-and-aspnet-compatibility-is-required"></a>Не удается установить защиту сообщения, если требуется использовать олицетворение ASP.NET и совместимость ASP.NET

WCF не поддерживает следующие сочетания параметров, так как они могут препятствовать проверке подлинности клиента:

- ASP.NET олицетворение включено. Это можно сделать в файле Web. config, установив атрибут `impersonate` элемента <`identity`> в значение `true`.

- Режим совместимости ASP.NET включается путем установки атрибута `aspNetCompatibilityEnabled` [\<serviceHostingEnvironment >](../../configure-apps/file-schema/wcf/servicehostingenvironment.md) `true`.

- Используется режим безопасности сообщения.

Обходной обходной проблемы — отключение режима совместимости ASP.NET. Или, если требуется режим совместимости ASP.NET, отключите функцию олицетворения ASP.NET и используйте вместо этого олицетворение, предоставленное WCF. Дополнительные сведения см. в разделе [Делегирование и олицетворение](delegation-and-impersonation-with-wcf.md).

## <a name="ipv6-literal-address-failure"></a>Ошибка литерального адреса IPv6

Если клиент и служба находятся на одном компьютере, а для службы используются литеральные адреса IPv6, происходит сбой запросов безопасности.

 Литеральные адреса IPv6 можно использовать, если служба и клиент находятся на разных компьютерах.

## <a name="wsdl-retrieval-failures-with-federated-trust"></a>Сбои при получении WSDL с федеративным доверием

WCF требует ровно один документ WSDL для каждого узла в Федеративной цепочке доверия. Следует быть внимательным, чтобы не создать замкнутый цикл при задании конечных точек. Например, замкнутый цикл появляется при использовании загрузки WSDL федеративной цепи доверия с несколькими ссылками в одном документе WSDL. Типичной ситуацией, в которой может возникать эта проблема, служит федеративная служба, в которой сервер маркера безопасности и служба находятся в одном узле ServiceHost.

 Ниже приведен пример службы с тремя адресами конечных точек:

- `http://localhost/CalculatorService/service` (служба)

- `http://localhost/CalculatorService/issue_ticket` (STS)

- `http://localhost/CalculatorService/mex` (конечная точка метаданных)

 В этом случае создается исключение.

 Чтобы этот сценарий работал, необходимо разместить конечную точку `issue_ticket` в каком-либо другом месте.

## <a name="wsdl-import-attributes-can-be-lost"></a>Атрибуты импорта WSDL могут быть потеряны

WCF теряет атрибуты элемента `<wst:Claims>` в шаблоне `RST` при выполнении импорта WSDL. Это происходит при импорте WSDL, если `<Claims>` заданы непосредственно в `WSFederationHttpBinding.Security.Message.TokenRequestParameters` или `IssuedSecurityTokenRequestParameters.AdditionalRequestParameters` вместо использования коллекций типов утверждений.  Вследствие потери атрибутов при импорте привязка не выполняет надлежащим образом полный цикл через WSDL и поэтому является неверной на стороне клиента.

 Для устранения этой проблемы необходимо изменить привязку непосредственно в клиенте после выполнения импорта.

## <a name="see-also"></a>См. также:

- [Вопросы безопасности](security-considerations-in-wcf.md)
- [Раскрытие информации](information-disclosure.md)
- [Повышение привилегий](elevation-of-privilege.md)
- [Отказ в обслуживании](denial-of-service.md)
- [Подделка](tampering.md)
- [Атаки с повторением](replay-attacks.md)
