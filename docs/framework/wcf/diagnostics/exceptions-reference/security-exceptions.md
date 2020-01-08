---
title: Исключения безопасности
ms.date: 03/30/2017
ms.assetid: 76d5e5cd-e4f4-404f-9a5a-ec3522494ad8
ms.openlocfilehash: e96c317862867b9e461eb2d13dce6ede5b30cf13
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75348234"
---
# <a name="security-exceptions"></a>Исключения безопасности

В этом разделе перечислены все исключения безопасности.

## <a name="exception-list"></a>Список исключений

|Код ресурса|Строка ресурса|
|-------------------|---------------------|
|AnonymousLogonsAreNotAllowed|Эта служба не разрешает анонимный вход.|
|AtLeastOneContractOperationRequestRequiresProtectionLevelNotSupportedByBinding|Сообщение запроса должно быть защищено. Это требуется для операции указанного контракта. Защиту должна обеспечить указанная привязка.|
|AtLeastOneContractOperationResponseRequiresProtectionLevelNotSupportedByBinding|Сообщение ответа должно быть защищено. Это требуется для операции указанного контракта. Защиту должна обеспечить указанная привязка.|
|AtMostOnePrimarySignatureInReceiveSecurityHeader|В заголовке безопасности допускается только одна основная подпись.|
|BadContextTokenFaultReason|Недопустимый или просроченный маркер контекста безопасности. Сообщение не было обработано.|
|BadEncryptionState|EncryptedData или EncryptedKey находятся в недопустимом для этой операции состоянии.|
|BasicHttpMessageSecurityRequiresCertificate|Для обеспечения безопасности сообщений привязка BasicHttp требует эквивалентности BasicHttpBinding.Security.Message.ClientCredentialType и типа учетных данных BasicHttpMessageCredentialType. Выберите уровень защиты Transport или TransportWithMessageCredential для учетных данных UserName.|
|BasicTokenCannotBeWrittenWithoutEncryption|Базовый маркер не может быть записан без шифрования.|
|BindingDoesNotSupportProtectionForRst|Указанная привязка для указанного контракта настроена с помощью диалога SecureConversation, однако используемый режим проверки подлинности не способен обеспечить основанную на запросах-ответах целостность и конфиденциальность, требуемые для данного согласования.|
|BindingDoesNotSupportWindowsIdenityForImpersonation|В указанной операции контракта для автоматического олицетворения требуется удостоверение Windows. В указанной привязке для указанного контракта отсутствует удостоверение Windows, представляющее вызывающую сторону.|
|CachedNegotiationStateQuotaReached|Служба не может кэшировать состояние согласования, так как достигнута указанная емкость. Повторите запрос.|
|CacheQuotaReached|Не удается добавить элемент. Максимальный размер кэша равен указанному значению.|
|CannotDetermineSPNBasedOnAddress|Клиент не может определить имя службы-участника на основании имени в указанном конечном адресе для SspiNegotiation/Kerberos. Идентификатор целевого адреса должен быть удостоверением имени участника-пользователя (например, акмедомаин\\\алице) или удостоверением SPN (например, Host или bobs-Machine).|
|CannotFindCert|Не удается найти сертификат X.509 с помощью следующих условий поиска: StoreName, StoreLocation, FindType, FindValue.|
|CannotFindCertForTarget|Не удается найти сертификат X.509 с помощью следующих условий поиска: StoreName, StoreLocation, FindType, FindValue для указанного целевого объекта.|
|CannotFindCorrelationStateForApplyingSecurity|Не удается найти состояние корреляции для применения безопасности к ответу респондента.|
|CannotFindNegotiationState|Не удается найти состояние согласования для указанного контекста.|
|CannotFindSecuritySession|Не удается найти сеанс безопасности с указанным идентификатором.|
|CannotImportProtectionLevelForContract|Политике импорта процессов не удалось импортировать привязку для указанного контракта. Это вызвано несовместимостью требований защиты привязки с требованиями ранее импортированной привязки для данного контракта. Требуется повторная настройка привязки.|
|CannotImportSupportingTokensForOperationWithoutRequestAction|Сбой импорта политики безопасности. Политика безопасности включает в область определения операции требования к вспомогательному маркеру. Однако в описании контракта не указано действие для сообщения запроса, связанного с данной операцией.|
|CannotIssueRstTokenType|Не удается выпустить маркер указанного типа.|
|CannotObtainIssuedTokenKeySize|Не удается определить размер ключа выпущенного маркера.|
|CannotPerformImpersonationOnUsernameToken|Олицетворение на основе маркера клиента невозможно. Указанная привязка для указанного контракта использует маркер безопасности Username для проверки подлинности клиента с помощью зарегистрированного поставщика членства. Используйте для данного клиента другой тип маркера безопасности.|
|CannotPerformS4UImpersonationOnPlatform|Указанная привязка для указанного контракта поддерживает олицетворение только в Windows Server 2003 и более поздних версиях Windows. Используйте проверку подлинности SspiNegotiated и привязку с безопасным диалогом и возможностью отмены.|
|CannotReadKeyIdentifier|Не удается считать идентификатор KeyIdentifier из указанного элемента в указанном пространстве имен.|
|CannotReadToken|Не удается считать маркер из указанного элемента в указанном пространстве имен для маркера BinarySecretSecurityToken с указанным типом параметра ValueType. Чтобы данный элемент был допустимым, безопасность должна быть настроена на использование маркеров с указанным именем, пространством имен и типом параметра.|
|CertificateUnsupportedForHttpTransportCredentialOnly|Проверка подлинности клиентов на основе сертификатов не поддерживается в режиме безопасности TransportCredentialOnly. Выберите режим безопасности Transport.|
|ClaimTypeCannotBeEmpty|claimType не может быть пустой строкой.|
|ClientCertificateNotProvided|Сертификат клиента не предоставлен. Сертификат можно задать в ClientCredentials или ServiceCredentials.|
|ClientCredentialTypeMustBeSpecifiedForMixedMode|Объект ClientCredentialType.None недопустим в режиме безопасности TransportWithMessageCredential. Укажите тип учетных данных или используйте другой режим безопасности.|
|ConfigurationSchemaInsuffientForSecurityBindingElementInstance|Схема конфигурации недостаточна для описания нестандартной конфигурации следующего элемента привязки безопасности:|
|DerivedKeyTokenGenerationAndLengthTooHigh|Указанная генерация и длина производного ключа приводят к смещению производного ключа, превышающему максимально разрешенное смещение.|
|DnsIdentityCheckFailedForIncomingMessage|Сбой проверки идентификации входящего сообщения. Указан ожидаемый идентификатор DNS удаленной конечной точки. Удаленная конечная точка предоставила указанное DNS-имя. Если это надежная удаленная конечная точка, проблему можно устранить, явно указав идентификатор DNS в свойстве Identity элемента EndpointAddress при создании прокси для канала.|
|DnsIdentityCheckFailedForOutgoingMessage|Проверка удостоверения не пройдена для полученного сообщения. Удаленная конечная точка должна иметь указанное удостоверение системы доменных имен. Удаленная конечная точка указала DNS-имя. Если это надежная удаленная конечная точка, проблему можно устранить, явно указав идентификатор DNS в свойстве Identity элемента EndpointAddress при создании прокси для канала.|
|DuplicateIdInMessageToBeVerified|Указанный идентификатор дважды встречается в сообщении, указанном для проверки.|
|EmptyBase64Attribute|Найдено пустое значение имени обязательного атрибута base-64 и пространства имен.|
|ExportOfBindingWithAsymmetricAndTransportSecurityNotSupported|Ошибка экспорта политики безопасности. Привязка содержит элемент AsymmetricSecurityBindingElement и элемент привязки защищенного транспорта. Экспорт политики для такой привязки не поддерживается.|
|ExportOfBindingWithSymmetricAndTransportSecurityNotSupported|Ошибка экспорта политики безопасности. Привязка содержит элемент SymmetricSecurityBindingElement и элемент привязки защищенного транспорта. Экспорт политики для такой привязки не поддерживается.|
|ExportOfBindingWithTransportSecurityBindingElementAndNoTransportSecurityNotSupported|Ошибка экспорта политики безопасности. Привязка содержит элемент TransportSecurityBindingElement, но в ней отсутствует элемент привязки транспорта, реализующий ITransportTokenAssertionProvider. Экспорт политики для такой привязки не поддерживается. Убедитесь, что элемент привязки транспорта в данной привязке реализует интерфейс ITransportTokenAssertionProvider.|
|FoundMultipleCerts|С помощью указанных условий поиска StoreName, StoreLocation, FindType, FindValue найдено несколько сертификатов X.509. Укажите более точное значение.|
|FoundMultipleCertsForTarget|Несколько сертификатов X.509 найдено с помощью указанных условий StoreName, StoreLocation, FindType, FindValue для указанного целевого объекта. Укажите более точное значение.|
|HeaderDecryptionNotSupportedInWsSecurityJan2004|SecurityVersion.WSSecurityJan2004 не поддерживает описание заголовка. Используйте SecurityVersion.WsSecurityXXX2005 или более позднюю версию, либо безопасность транспорта, чтобы зашифровать все сообщение.|
|IdentityCheckFailedForIncomingMessage|Сбой проверки идентификации входящего сообщения. Ожидаемое имя указано для целевой конечной точки.|
|IdentityCheckFailedForOutgoingMessage|Сбой проверки идентификации исходящего сообщения. Ожидаемое имя указано для целевой конечной точки.|
|IncorrectSpnOrUpnSpecified|Сбой проверки подлинности интерфейса поставщика поддержки безопасности (SSPI). Возможно, сервер не запущен в контексте учетной записи с указанным именем. Если на сервере используется учетная запись службы (например, сетевой службы), укажите имя ServicePrincipalName (SPN) этой учетной записи в качестве имени в параметре EndpointAddress сервера. Если на сервере используется учетная запись пользователя, укажите в качестве имени имя UserPrincipalName этой учетной записи в параметре EndpointAddress сервера.|
|InvalidAttributeInSignedHeader|Указанный подписанный заголовок содержит указанный атрибут. Указан ожидаемый атрибут.|
|InvalidCloseResponseAction|Получено ответное сообщение закрытия сеанса безопасности с указанным недопустимым действием.|
|InvalidQName|Параметр QName недопустим.|
|InvalidRenewResponseAction|Получен ответ обновления сеанса безопасности с указанным недопустимым действием.|
|InvalidSspiNegotiation|Ошибка согласования SSPI.|
|IssuerBindingNotPresentInTokenRequirement|Диспетчеру маркеров безопасности требуется указать элемент привязки безопасности загрузки в требовании к маркеру, которое описывает безопасный диалог. Задано следующее требование к маркеру.|
|KeyLengthMustBeMultipleOfEight|Указанная длина ключа не кратна 8, как полагается для симметричных ключей.|
|LsaAuthorityNotContacted|Внутренняя ошибка SSL (подробнее см. код состояния Win32). Проверьте сертификат сервера, чтобы определить, поддерживает ли он обмен ключами.|
|MaximumPolicyRedirectionsExceeded|Достигнут предел выборки рекурсивной политики. Проверьте наличие петли в цепочке служб федерации.|
|MessagePartSpecificationMustBeImmutable|Спецификацию частей сообщения перед заданием необходимо сделать постоянной.|
|MissingCustomCertificateValidator|X509CertificateValidationMode.Custom требует CustomCertificateValidator. Задайте свойство CustomCertificateValidator.|
|MissingCustomUserNamePasswordValidator|UserNamePasswordValidationMode.Custom требует CustomUserNamePasswordValidator. Задайте свойство CustomUserNamePasswordValidator.|
|MissingMembershipProvider|UserNamePasswordValidationMode.MembershipProvider требует MembershipProvider. Задайте свойство MembershipProvider.|
|NoBinaryNegoToSend|Двоичное согласование не было отправлено другой стороне.|
|NoEncryptionPartsSpecified|Для сообщений с указанным действием не указаны части сообщения с шифрованием.|
|NoKeyInfoInEncryptedItemToFindDecryptingToken|В зашифрованном элементе не найдено значение KeyInfo для поиска маркера расшифровки.|
|NonceLengthTooShort|Указанный элемент слишком короток. Минимальная требуемая длина элемента равна 4 байтам.|
|NoOutgoingEndpointAddressAvailableForDoingIdentityCheck|Отсутствует адрес EndpointAddress для проверки идентификации отправляемого сообщения.|
|NoOutgoingEndpointAddressAvailableForDoingIdentityCheckOnReply|Отсутствует адрес EndpointAddress для проверки идентификации полученного ответа.|
|NoPartsOfMessageMatchedPartsToSign|Подпись не создана, так как нет частей сообщения, соответствующих предоставленной спецификации части сообщения.|
|NoPrincipalSpecifiedInAuthorizationContext|В контексте авторизации особый участник не указан.|
|NoSignatureAvailableInSecurityHeaderToDoReplayDetection|В заголовке безопасности нет доступных подписей, чтобы предоставить элемент nonce для определения ответа.|
|NoSignaturePartsSpecified|Для сообщений с указанным действием не заданы части сообщения с подписью.|
|NoSigningTokenAvailableToDoIncomingIdentityCheck|Отсутствует маркер подписи для проверки идентификации входящего сообщения.|
|NoTimestampAvailableInSecurityHeaderToDoReplayDetection|В заголовке безопасности отсутствует отметка времени для обнаружения воспроизведения.|
|NoTransportTokenAssertionProvided|Сбой экспорта политики безопасности. Предоставленное утверждение маркера транспорта указанного типа не создало утверждения маркера транспорта для включения в утверждение политики безопасности sp:TransportBinding.|
|OnlyOneOfEncryptedKeyOrSymmetricBindingCanBeSelected|Симметричный протокол безопасности можно настроить с помощью поставщика симметричного маркера и средства проверки подлинности симметричного маркера, либо поставщика асимметричного маркера, но не обоих одновременно.|
|OperationCannotBeDoneOnReceiverSideSecurityHeaders|Эту операцию нельзя применять к заголовкам безопасности на стороне получателя.|
|OperationDoesNotAllowImpersonation|Указанная операция службы, принадлежащая контракту с указанным именем и пространством имен, не разрешает олицетворение.|
|PolicyRequiresConfidentialityWithoutIntegrity|Политика безопасности сообщений требует для указанного действия конфиденциальности без целостности. Конфиденциальность без целостности не поддерживается.|
|PrimarySignatureIsRequiredToBeEncrypted|Основная подпись должна быть зашифрована.|
|PropertySettingErrorOnProtocolFactory|Обязательное свойство в производстве указанного протокола безопасности не задано или имеет недопустимое значение.|
|ProtocolFactoryCouldNotCreateProtocol|Производству протокола не удалось создать протокол.|
|PublicKeyNotRSA|Открытый ключ не является ключом RSA.|
|RequiredMessagePartNotEncrypted|Указанная обязательная часть сообщения не зашифрована.|
|RequiredMessagePartNotEncryptedNs|Указанная обязательная часть сообщения не зашифрована.|
|RequiredMessagePartNotSigned|Указанная обязательная часть сообщения не подписана.|
|RequiredMessagePartNotSignedNs|Указанная обязательная часть сообщения не подписана.|
|RequiredSecurityHeaderElementNotSigned|Указанный элемент заголовка безопасности с указанным ИДЕНТИФИКАТОРом должен быть подписан.|
|RequiredSecurityTokenNotEncrypted|Указанный маркер безопасности с указанным режимом вложения должен быть зашифрован.|
|RequiredSecurityTokenNotSigned|Указанный маркер безопасности с указанным режимом вложения должен быть подписан.|
|RequiredSignatureMissing|Подпись должна располагаться в заголовке безопасности.|
|RequireNonCookieMode|Указанная привязка с указанным пространством имен настроена для выдачи маркеров контекста безопасности cookie. Службы интеграции COM+ не поддерживают маркеры контекста безопасности cookie.|
|RevertingPrivilegeFailed|Сбой операции отката с указанным исключением.|
|RSTRAuthenticatorIncorrect|RequestSecurityTokenResponse CombinedHash является неправильным.|
|SecureConversationCancelNotAllowedFaultReason|Прекращение безопасного диалога не разрешается в этой привязке.|
|SecureConversationDriverVersionDoesNotSupportSession|Настроенная версия SecureConversation не поддерживает сеансы. Используйте WSSecureConversationFeb2005 или более позднюю версию.|
|SecureConversationRequiredByReliableSession|Не удается установить надежный сеанс без безопасного диалога. Включите поддержку безопасного диалога.|
|SecurityAuditFailToLoadDll|Не удалось загрузить указанную библиотеку DLL.|
|SecurityAuditNotSupportedOnChannelFactory|SecurityAuditBehavior не поддерживается в производстве каналов.|
|SecurityAuditPlatformNotSupported|На текущей платформе не поддерживается запись сообщений аудита в журнал безопасности. Сообщения аудита следует записывать в журнал приложений.|
|SecurityBindingElementCannotBeExpressedInConfig|Импортирована политика безопасности для данной конечной точки. В этой политике безопасности содержатся требования, которые не могут быть представлены в конфигурации Windows Communication Foundation. Найдите описание обязательных параметров SecurityBindingElement в созданном файле конфигурации. Создайте правильный элемент привязки с помощью кода. Конфигурация привязки в файле конфигурации не защищена.|
|SecurityBindingSupportsOneWayOnly|SecurityBinding для указанной привязки указанного контракта поддерживает только операцию OneWay.|
|SecurityContextDoesNotAllowImpersonation|Не удается начать олицетворение, так как SecurityContext для роли UltimateReceiver из сообщения запроса с указанным действием не сопоставляется с удостоверением Windows.|
|SecurityListenerClosing|Прослушиватель не принимает новые безопасные диалоги, так как он закрывается.|
|SecurityListenerClosingFaultReason|Сервер не принимает новые безопасные диалоги в текущий момент, так как он закрывается. Повторите попытку позже.|
|SecurityProtocolFactoryShouldBeSetBeforeThisOperation|Перед выполнением этой операции необходимо задать производство протокола безопасности.|
|SecuritySessionAbortedFaultReason|Сеанс безопасности прерван. Это может быть связано с тем, что во время сеанса слишком долго не поступали сообщения.|
|SecuritySessionKeyIsStale|Сеансовый ключ необходимо обновить, прежде чем его можно будет использовать для защиты сообщений приложений.|
|SecuritySessionLimitReached|Не удается создать сеанс безопасности. Повторите попытку позже.|
|SecuritySessionNotPending|Нет ожидающего сеанса безопасности с указанным ИДЕНТИФИКАТОРом.|
|SecurityTokenParametersHasIncompatibleInclusionMode|Указанная привязка настроена с использованием указанного параметра маркера безопасности, имеющего несовместимый режим включения маркеров безопасности. Укажите альтернативный режим включения маркеров безопасности.|
|SecurityVersionDoesNotSupportEncryptedKeyBinding|Указанная привязка для указанного контракта настроена с использованием несовместимой версии безопасности, которая не поддерживает неприкрепленные ссылки на EncryptedKeys. Используйте указанное или большее значение в качестве версии безопасности для этой привязки.|
|SecurityVersionDoesNotSupportSignatureConfirmation|Указанная версия SecurityVersion не поддерживает подтверждение подписи. Используйте более позднюю версию безопасности SecurityVersion.|
|SecurityVersionDoesNotSupportThumbprintX509KeyIdentifierClause|Указанная привязка для указанного контракта настроена с использованием версии безопасности, которая не поддерживает внешние ссылки на маркеры X.509 с помощью отпечатка сертификата. Используйте указанное или большее значение в качестве версии безопасности для этой привязки.|
|SenderSideSupportingTokensMustSpecifySecurityTokenParameters|Параметры маркеров безопасности должны быть указаны вместе с вспомогательными маркерами для каждого сообщения.|
|ServerCertificateNotProvided|Получатель не предоставил свой сертификат. Этот сертификат требуется протоколу TLS. Обе стороны должны иметь доступ к своим сертификатам.|
|SignatureConfirmationNotSupported|Данная конфигурация SecurityVersion не поддерживает подтверждение подписи. Используйте WSSecurityXXX2005 или более позднюю версию.|
|SignatureConfirmationRequiresRequestReply|Производство протокола должно поддерживать безопасность типа запрос-ответ, чтобы обеспечить подтверждение подписи.|
|SignatureNotExpected|Для данного сообщения подпись не ожидается.|
|SigningTokenHasNoKeys|Указанный маркер подписывания не имеет ключей. Маркер безопасности используется в контексте, требующем выполнения операций шифрования, но маркер не содержит ключей шифрования. Возможно, тип маркера не поддерживает операции шифрования, либо конкретный экземпляр маркера не содержит ключей шифрования. Проверьте конфигурацию, чтобы убедиться в том, что типы маркеров с отключенным шифрованием (например, UserNameSecurityToken) не указаны в контексте, требующем операций шифрования (например, подтверждающий вспомогательный маркер).|
|SpnegoImpersonationLevelCannotBeSetToNone|Интерфейс SSPI не поддерживает уровень олицетворения "None". Укажите уровень идентификации, олицетворения или делегирования.|
|SslClientCertMustHavePrivateKey|Указанный сертификат должен иметь закрытый ключ. Процесс должен иметь права доступа к этому закрытому ключу.|
|SslServerCertMustDoKeyExchange|Указанный сертификат должен иметь закрытый ключ, поддерживающий обмен ключами. Процесс должен иметь права доступа к этому закрытому ключу.|
|StandardsManagerCannotWriteObject|Сериализатор маркеров не может сериализовать указанный объект.  Если используется пользовательский тип, необходимо предоставить пользовательский сериализатор.|
|TimeStampHasCreationAheadOfExpiry|Отметка времени безопасности недействительна, так как ее время создания больше или равно времени истечения срока ее действия.|
|TimeStampHasCreationTimeInFuture|Отметка времени безопасности недействительна, так как время ее создания относится к будущему. Указаны текущее время и допустимая разница в показаниях часов.|
|TimeStampHasExpiryTimeInPast|Метка времени безопасности недействительна, так как время истечения срока ее действия относится к прошлому. Указаны текущее время и допустимая разница в показаниях часов.|
|TimeStampWasCreatedTooLongAgo|Метка времени безопасности просрочена, так как с времени ее создания прошло слишком много времени. Указаны текущее время, максимальное время жизни метки времени и допустимая разница в показаниях часов.|
|TokenProviderCannotGetTokensForTarget|Поставщику маркеров не удается получить маркеры для указанного целевого объекта.|
|TooManyIssuedSecurityTokenParameters|Участок федеративной цепочки безопасности содержит несколько параметров IssuedSecurityTokenParameters. Система InfoCard поддерживает только по одному параметру IssuedSecurityTokenParameters для каждого участка.|
|TransportDoesNotProtectMessage|Указанная привязка для указанного контракта настроена с режимом проверки подлинности, требующим целостности и конфиденциальности уровня транспорта. Однако транспорт не способен обеспечить целостность и конфиденциальность.|
|TrustApr2004DoesNotSupportCertainIssuedTokens|WSTrustApr2004 не поддерживает выпуск сертификатов X509 или EncryptedKeys. Используйте WsTrustFeb2005 или более позднюю версию.|
|TrustDriverVersionDoesNotSupportSession|Настроенная версия Trust не поддерживает сеансы. Используйте WSTrustFeb2005 или более позднюю версию.|
|UnableToCreateICryptoFromTokenForSignatureVerification|Не удается создать интерфейс ICrypto из указанного маркера для проверки подписи.|
|UnableToCreateSymmetricAlgorithmFromToken|Не удается создать указанный симметричный алгоритм из данного маркера.|
|UnableToDeriveKeyFromKeyInfoClause|Указанная конструкция KeyInfo разрешена в указанный маркер, не содержащий симметричного ключа, который может использоваться для наследования.|
|UnableToFindTokenAuthenticator|Не удается найти средство проверки подлинности маркера для указанного типа маркера. Маркеры этого типа не могут быть приняты в соответствии с текущими настройками безопасности.|
|UnableToLoadCertificateIdentity|Не удается загрузить сертификат X.509, указанный в конфигурации.|
|UnexpectedEmptyElementExpectingClaim|Указанный элемент из указанного пространства имен пуст и не определяет допустимое идентификационное утверждение.|
|UnknownEncodingInBinarySecurityToken|Нераспознанное кодирование при считывании двоичного маркера безопасности.|
|UnsecuredMessageFaultReceived|Незащищенное или неправильно защищенное сообщение об ошибке было получено от другой стороны. Код ошибки и описание см. во внутреннем исключении FaultException.|
|UnsupportedPasswordType|Неподдерживаемый тип пароля в указанном маркере имени пользователя.|
|UnsupportedSecureConversationBootstrapProtectionRequirements|Не удается импортировать политику безопасности. Требования защиты для привязки загрузки безопасного диалога не поддерживаются. Согласно требованиям защиты для привязки загрузки безопасного диалога, запрос и ответ должны быть подписаны и зашифрованы.|
|UnsupportedSecurityPolicyAssertion|При импорте указанной политики безопасности обнаружено неподдерживаемое утверждение политики безопасности.|
