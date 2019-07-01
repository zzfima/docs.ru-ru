---
title: Исключения IdentityModel
ms.date: 03/30/2017
ms.assetid: 4ef34497-8ff5-4621-b773-7731cc721231
ms.openlocfilehash: 4b8af2620b6179ce4cff59d7f9871377f06ffe5f
ms.sourcegitcommit: 2d42b7ae4252cfe1232777f501ea9ac97df31b63
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2019
ms.locfileid: "67486666"
---
# <a name="identitymodel-exceptions"></a>Исключения IdentityModel
В этом разделе перечислены все исключения, создаваемые IdentityModel.  
  
## <a name="exception-list"></a>Список исключений  
  
|Код ресурса|Текущая строка|  
|-------------------|--------------------|  
|ValueMustBeOf2Types|Значение этого аргумента должно быть одного из этих двух типов.|  
|SAMLSubjectNameIdentifierRequiresNameValue|"Name" для идентификатора SamlNameIdentifier не может иметь значение null или длину 0.|  
|TraceCodeIssuanceTokenProviderEndSecurityNegotiation|IssuanceTokenProvider завершил согласование безопасности.|  
|TraceCodeSecurityNewServerSessionKeyIssued|Сервер выдал новый сеансовый ключ безопасности.|  
|SAMLAttributeMissingNameAttributeOnRead|"Name" для считываемого атрибута SamlAttribute отсутствует или имеет длину 0.|  
|UnknownICryptoType|Реализация ICrypto не поддерживается.|  
|TraceCodeSecurityTokenProviderClosed|Поставщик маркера безопасности закрыт.|  
|SAMLUnableToLoadAdvice|Не удалось загрузить \<SAML: advice > элемента.|  
|SAMLAuthenticationStatementMissingAuthenticationMethodOnRead|Считываемый атрибут "AuthenticationMethod" для оператора SamlAuthenticationStatement отсутствует или имеет длину 0.|  
|UnsupportedTransformAlgorithm|Неподдерживаемое преобразование или алгоритм канонизации.|  
|SAMLAudienceRestrictionShouldHaveOneAudience|Условие SamlAudienceRestrictionCondition должно иметь хотя бы одну аудиторию (URI).|  
|SAMLEvidenceShouldHaveOneAssertion|SamlEvidence должно ссылаться хотя бы на одно утверждение SamlAssertion через идентификатор или ссылку.|  
|SAMLAudienceRestrictionInvalidAudienceValueOnRead|В считываемом условии SamlAudienceRestrictionCondition отсутствует значение элемента "Audience".|  
|X509ChainBuildFail|Сбой при создании указанной цепочки сертификатов X.509. Используемый сертификат имеет цепочку доверия, которую невозможно проверить. Замените сертификат или измените certificateValidationMode.|  
|XDCannotFindValueInDictionaryString|В строке словаря не найдено указанное значение идентификатора.|  
|TraceCodeImportSecurityChannelBindingEntry|Запуск Security ImportChannelBinding.|  
|PrivateKeyExchangeNotSupported|Закрытый ключ не поддерживает обмен KeySpec.|  
|TokenProviderUnableToGetToken|Указанный поставщик маркеров не предоставил маркер безопасности.|  
|SAMLEntityCannotBeNullOrEmpty|Указанный объект в утверждении SamlAssertion не может быть пустым или иметь значение null.|  
|SAMLAssertionRequireOneStatement|Утверждение SamlAssertion должно содержать хотя бы один оператор. Убедитесь, что в создаваемое SamlAssertion добавлен хотя бы один оператор SamlStatement.|  
|AESInvalidInputBlockSize|Размер входных данных должен быть кратен указанному количеству байт.|  
|AESCryptAcquireContextFailed|Не удалось получить CSP-контекст.|  
|SAMLAssertionRequireOneStatementOnRead|Считываемое утверждение SamlAssertion не содержит оператора SamlStatement. Утверждение SamlAssertion должно содержать хотя бы один оператор SamlStatement.|  
|TraceCodeSecuritySessionClosedFaultReceived|Сеанс безопасности клиента получил от сервера сообщение о сбое закрытия сеанса.|  
|TraceCodeIssuanceTokenProviderRedirectApplied|IssuanceTokenProvider применил заголовок перенаправления.|  
|TraceCodeSecuritySessionClosedFaultSendFailure|Произошла ошибка при отправлении клиенту сообщения об ошибке, вызывавшей закрытие сеанса безопасности.|  
|ValueMustBeZero|Значение этого аргумента должно быть 0.|  
|SAMLUnableToResolveSignatureKey|Не удалось разрешить идентификатор SecurityKeyIdentifier, найденный в сигнатуре SamlAssertion. Невозможно проверить сигнатуру SamlAssertion для указанного издателя.|  
|X509IsNotInTrustedStore|Указанный сертификат X.509 не принадлежит хранилищу "Доверенные лица".|  
|SAMLElementNotRecognized|Указанный элемент не поддерживается.|  
|SAMLAuthorizationDecisionStatementMissingResourceAttributeOnRead|Атрибут "Resource" для считываемого оператора SamlAuthorizationDecisionStatement отсутствует или имеет длину 0.|  
|SamlTokenMissingSignature|Утверждение SamlAssertion не подписано. Утверждения SamlAssertion можно подписывать путем задания учетных данных подписывания SigningCredentials.|  
|ExpectedElementMissing|Отсутствует ожидаемый элемент с указанным пространством имен.|  
|NoKeyIdentifierClauseFound|В SecurityKeyIdentifier не найдено предложение указанного типа.|  
|MissingPrivateKey|В сертификате X.509 отсутствует закрытый ключ.|  
|UnexpectedEOFFromReader|Непредвиденный символ конца файла от средства чтения XML.|  
|UnsupportedKeyDerivationAlgorithm|Указанный алгоритм создания производного ключа не поддерживается.|  
|TokenDoesNotSupportKeyIdentifierClauseCreation|Указанный маркер не поддерживает указанный критерий предложения идентификатора ключа.|  
|LastMessageNumberExceeded|Обнаружено нарушение протокола порядковых номеров.|  
|SymmetricKeyLengthTooShort|Указанная длина симметричного ключа слишком мала.|  
|SAMLAuthorityBindingMissingAuthorityKindOnRead|Обнаружено, что в считываемой привязке SamlAuthorityBinding отсутствует элемент «AuthorityKind» или его длина равна 0.  Это не допускается.|  
|XmlTokenBufferIsEmpty|Буфер XmlTokenBuffer пуст.|  
|InvalidXmlQualifiedName|Ожидалось полное имя Xml, а обнаружено недопустимое имя.|  
|SAMLAuthorityKindMissingName|Имя XmlQualifiedName, представляющее "AuthorityKind" в привязке SamlAuthorityBinding, не может иметь значение null или длину 0.|  
|AESCryptEncryptFailed|Сбой при шифровании указанных данных.|  
|AuthorizationContextCreated|Создается контекст авторизации с указанным идентификатором.|  
|SamlSerializerUnableToReadSecurityKeyIdentifier|SamlSerializer не содержит SecurityTokenSerializer, способный прочитать SecurityKeyIdentifier. Если используется пользовательский идентификатор SecurityKeyIdentifier, необходимо предоставить пользовательский сериализатор SecurityTokenSerializer.|  
|TraceCodeIssuanceTokenProviderServiceTokenCacheFull|IssuanceTokenProvider уменьшил кэш маркеров службы.|  
|TraceCodeSecurityTokenProviderOpened|Открыт поставщик маркера безопасности.|  
|PublicKeyNotRSA|Открытый ключ не является ключом RSA.|  
|InvalidReaderState|Указанное состояние недопустимо для предоставленного средства чтения входных данных.|  
|UnableToResolveReferenceUriForSignature|Невозможно разрешить указанный в сигнатуре универсальный код ресурса (URI) для вычисления дайджеста.|  
|EmptyBase64Attribute|Для имени и пространства имен обязательного атрибута в base64-кодировке найдено пустое значение.|  
|SAMLSubjectRequiresConfirmationMethodWhenConfirmationDataOrKeyInfoIsSpecified|Конструкция SAML SubjectConfirmation требует использования метода подтверждения Confirmation, если указаны данные Confirmation Data или KeyInfo.|  
|SAMLAudienceRestrictionShouldHaveOneAudienceOnRead|Считываемое условие SamlAudienceRestrictionCondition должно содержать как минимум одно значение "Audience". Ни одно не найдено.|  
|TokenProviderUnableToRenewToken|Указанный поставщик маркеров не смог обновить маркер безопасности.|  
|AESIVLengthNotSupported|Вектор IV указанной разрядности не поддерживается. Поддерживается только 128-разрядный IV.|  
|SAMLAuthorityBindingMissingAuthorityKind|Привязка SamlAuthorityBinding должна содержать "AuthorityKind", значение которого не равно null.|  
|TraceCodeSecuritySessionDemuxFailure|Входящее сообщение не является частью существующего сеанса безопасности.|  
|TokenRenewalNotSupported|Указанный поставщик маркеров не поддерживает обновление маркеров безопасности.|  
|AtLeastOneReferenceRequired|В сигнатуре должна быть по крайней мере одна ссылка.|  
|SAMLSignatureAlreadyRead|Сигнатура уже прочитана в утверждении SAML.|  
|AlgorithmAndPrivateKeyMisMatch|Указанный алгоритм и закрытый ключ не соответствуют друг другу.|  
|EmptyTransformChainNotSupported|Пустая цепочка преобразований не поддерживается.|  
|SspiWrapperEncryptDecryptAssert1|SSPIWrapper::EncryptDecryptHelper&#124;'offset' is out of range.|  
|SspiWrapperEncryptDecryptAssert2|Sspiwrapper:: Encryptdecrypthelper&#124;«size» выходит за пределы диапазона. SecurityTokenManagerCannotCreateAuthenticatorForRequirement=Диспетчер маркера безопасности не может создать структуру проверки подлинности для указанного требования.|  
|UnableToCreateKeyedHashAlgorithm|Не удалось создать алгоритм KeyedHashAlgorithm из указанного значения для указанного алгоритма сигнатуры.|  
|SAMLUnableToLoadAssertion|\<SAML: Assertion > не удалось загрузить элемент.|  
|X509FindValueMismatchMulti|Для указанного типа X509FindType требуется, чтобы аргумент findValue имел один из 2 типов. Аргумент findValue имеет другой тип.|  
|TraceCodeSecurityIdentityDeterminationSuccess|Для EndpointAddress была определена идентификация.|  
|UndefinedUseOfPrefixAtElement|У указанного префикса, использованного для элемента, не задано пространство имен.|  
|TraceCodeSecuritySessionResponderOperationFailure|Сбой операции сеанса безопасности на сервере.|  
|CannotFindCert|Не удалось найти сертификат X.509, с помощью указанных условий поиска: StoreName, StoreLocation, FindType, FindValue.|  
|X509InvalidUsageTime|Указанное время использования сертификата X.509 недопустимо. Время использования выходит за требуемые временные границы NotBefore и NotAfter.|  
|TraceCodeSecurityIdentityDeterminationFailure|Невозможно определить идентификацию для EndpointAddress.|  
|AsyncObjectAlreadyEnded|Для данного объекта асинхронного результата уже был вызван метод End.|  
|ExternalDictionaryDoesNotContainAllRequiredStrings|Внешний словарь содержит определения не для всех требуемых строк. Указанная строка отсутствует в удаленном словаре.|  
|TraceCodeSecuritySessionKeyRenewalFaultReceived|Сеанс безопасности клиента получил от сервера ошибку обновления ключа.|  
|SAMLActionNameRequired|Строка, представляющая действие SamlAction, не может иметь значение null или длину 0.|  
|SignatureVerificationFailed|Сбой проверки сигнатуры.|  
|TraceCodeSecurityContextTokenCacheFull|Кэш SecurityContextSecurityToken полон.|  
|SAMLAssertionMissingMajorVersionAttributeOnRead|Значение MajorVersion для считываемого утверждения SamlAssertion отсутствует или имеет длину 0.|  
|SamlAttributeClaimRightShouldBePossessProperty|Данный конструктор SamlAttribute требует, чтобы параметр Right утверждения Claim имел значение System.IdentityModel.Claims.Rights.PossessProperty.|  
|AuthorizationPolicyEvaluated|Политика с указанным ИД оценена.|  
|SAMLUnableToLoadCondtions<!-- the misspelling here is deliberate. -->|\<SAML: Conditions > не удалось загрузить элемент.|  
|AESKeyLengthNotSupported|Ключ указанной длины не поддерживается. Поддерживаются только 128-, 192- и 256-разрядные ключи.|  
|UserNameCannotBeEmpty|Имя пользователя не может быть пустым.|  
|AlgorithmAndPublicKeyMisMatch|Указанный алгоритм и открытый ключ не соответствуют друг другу.|  
|SAMLUnableToLoadCondtion<!-- the misspelling here is deliberate. -->|\<SAML: Conditions > не удалось загрузить элемент.|  
|SamlAssertionMissingSigningCredentials|SigningCredentials не заданы в SamlAssertion. Утверждения SamlAssertion должны быть подписаны, для продолжения задайте допустимые учетные данные SigningCredentials в утверждении SamlAssertion.|  
|SspiPayloadNotEncrypted|Двоичные данные не зашифрованы с контекстом безопасности SSPI.|  
|SAMLAuthorizationDecisionShouldHaveOneActionOnRead|Считываемый оператор SamlAuthorizationDecisionStatement не содержит ни одного действия SamlAction.|  
|TraceCodeSecurityBindingSecureOutgoingMessageFailure|Протокол безопасности не может обеспечить защиту исходящего сообщения.|  
|UndefinedUseOfPrefixAtAttribute|У указанного префикса, использованного для указанного атрибута, не задано пространство имен.|  
|NoInputIsSetForCanonicalization|Не заданы входные данные для записи канонизированных выходных данных.|  
|TraceCodeSecurityPendingServerSessionAdded|На сервер добавлен ожидающий сеанс безопасности.|  
|AsyncCallbackException|AsyncCallback выдал исключение.|  
|PrivateKeyNotRSA|Закрытый ключ не является ключом RSA.|  
|TraceCodeSecurityClientSessionKeyRenewed|Во время сеанса безопасности клиента сеансовый ключ был обновлен.|  
|SAMLAuthorizationDecisionStatementMissingDecisionAttributeOnRead|"Decision" для считываемого оператора SamlAuthorizationDecisionStatement отсутствует или имеет длину 0.|  
|SAMLAttributeNameAttributeRequired|Значение параметра "Name", заданное для SamlAttribute, не может быть null или иметь длину 0.|  
|SamlSerializerRequiresExternalSerializers|SamlSerializer требует SecurityTokenSerializer для сериализации идентификатора SecurityKeyIdentifier, имеющегося в маркере.|  
|UnableToResolveKeyReference|Распознаватель маркеров не может разрешить указанную ссылку ключа безопасности.|  
|UnsupportedKeyWrapAlgorithm|Указанный алгоритм оболочки ключа не поддерживается.|  
|SAMLAssertionMissingIssuerAttributeOnRead|Значение "Issuer" для считываемого утверждения SamlAssertion отсутствует или имеет длину 0.|  
|TraceCodeIssuanceTokenProviderUsingCachedToken|IssuanceTokenProvider использовал кэшированный маркер службы.|  
|AESCryptGetKeyParamFailed|Сбой при получении указанного параметра ключа.|  
|InvalidNamespaceForEmptyPrefix|Пространство имен недействительно для пустого префикса.|  
|AESCipherModeNotSupported|Указанный режим шифрования не поддерживается. Поддерживается только режим CBC.|  
|ArgumentCannotBeEmptyString|Аргумент должен быть непустой строкой.|  
|SAMLAssertionMissingMinorVersionAttributeOnRead|Значение MinorVersion для считываемого утверждения SamlAssertion отсутствует или имеет длину 0.|  
|SpecifiedStringNotAvailableInDictionary|Указанная строка не является записью в текущем словаре.|  
|KerberosApReqInvalidOrOutOfMemory|Недопустимый AP-REQ или в системе недостаточно памяти.|  
|FailLogonUser|Сбой LogonUser для указанного пользователя. Убедитесь, что у пользователя имеется допустимая учетная запись Windows.|  
|ValueMustBeNonNegative|Значение этого аргумента должно быть неотрицательным.|  
|X509ValidationFail|Сбой проверки указанного сертификата X.509.|  
|TraceCodeSecuritySessionRequestorOperationSuccess|Операция сеанса безопасности на стороне клиента успешно завершена.|  
|SAMLActionNameRequiredOnRead|Строка, считываемая для действия SamlAction, отсутствует или имеет длину 0.|  
|KerberosMultilegsNotSupported|Идентификация указана в виде имени участника-пользователя. Не поддерживается проверка подлинности в службе, запущенной в контексте учетной записи пользователя, которая требует Kerberos multilegs.|  
|SAMLAssertionIdRequired|Идентификатор "assertionId" для SamlAssertion не может иметь значение null или быть пустым.|  
|InvalidOperationForWriterState|Указанная операция недопустима в указанном состоянии XmlWriter.|  
|CannotValidateSecurityTokenType|Указанная структура проверки подлинности маркера безопасности не может проверять маркеры указанного типа.|  
|X509FindValueMismatch|Для указанного типа X509FindType требуется, чтобы тип аргумента findValue имел одно из указанных значений. Аргумент findValue имеет другой тип.|  
|TraceCodeSecurityClientSessionCloseSent|Сообщение Close было отправлено сеансом безопасности клиента.|  
|SuiteDoesNotAcceptAlgorithm|Указанный алгоритм не принят для указанной операции указанным набором алгоритмов.|  
|TraceCodeSecuritySessionRequestorOperationFailure|Сбой операции сеанса безопасности клиента.|  
|SAMLUnableToLoadStatement|Не удалось загрузить SamlStatement.|  
|InnerReaderMustBeAtElement|Внутренний модуль чтения должен быть в элементе.|  
|UnableToCreateTokenReference|Не удалось создать ссылку маркера безопасности.|  
|TraceCodeSecurityBindingIncomingMessageVerified|Протокол безопасности проверил входящее сообщение.|  
|ObjectIsReadOnly|Объект доступен только для чтения.|  
|TraceCodeSecurityClientSessionPreviousKeyDiscarded|Во время сеанса безопасности клиента предыдущий сеансовый ключ был удален.|  
|SAMLTokenTimeInvalid|Недопустимое время действия маркера SamlToken. Текущее время не находится в промежутке между временем начала и временем завершения срока действия маркера.|  
|TraceCodeSecurityIdentityVerificationSuccess|Проверка идентификации выполнена успешно.|  
|SigningTokenHasNoKeys|Указанный маркер подписывания не имеет ключей.|  
|TraceCodeSecurityIdentityVerificationFailure|Сбой проверки идентификации.|  
|AESCryptImportKeyFailed|Не удалось импортировать материал ключа.|  
|FailInitializeSecurityContext|Сбой InitializeSecurityContent. Убедитесь в правильности имени субъекта-службы.|  
|TraceCodeStreamSecurityUpgradeAccepted|Обновление безопасности потока успешно принято.|  
|SAMLAuthorityBindingRequiresLocation|Атрибут "Location", указанный для SamlAuthorityBinding, не может иметь значение null или длину 0.|  
|PublicKeyNotDSA|Открытый ключ не является ключом DSA.|  
|ImpersonationLevelNotSupported|Режимы проверки подлинности, использующие Kerberos, не поддерживают указанный уровень олицетворения. Укажите допустимый уровень идентификации или олицетворения.|  
|RequiredTargetNotSigned|Элемент с указанным идентификатором должен быть подписан, но подпись отсутствует.|  
|SAMLAuthenticationStatementMissingAuthenticationInstanceOnRead|Считываемый атрибут "AuthenticationInstant" для SamlAuthenticationStatement отсутствует или имеет длину 0.|  
|SAMLEvidenceShouldHaveOneAssertionOnRead|Считываемое свидетельство SamlEvidence не содержит ни встроенного утверждения SamlAssertion, ни ссылки на него.|  
|LengthOfArrayToConvertMustGreaterThanZero|Длина массива для преобразования в целое число должна быть больше 0.|  
|InvalidAsyncResult|Недопустимый AsyncResult.|  
|TraceCodeIssuanceTokenProviderRemovedCachedToken|IssuanceTokenProvider удалил маркер службы с истекшим сроком действия.|  
|IncorrectUserNameFormat|Имя пользователя имеет недопустимый формат. Имя пользователя должно быть в формате «имя пользователя "или" домен\\\username ".|  
|TraceCodeExportSecurityChannelBindingEntry|Запуск привязки безопасности ExportChannelBinding.|  
|UnsupportedInputTypeForTransform|Для преобразования не поддерживается указанный тип входных данных.|  
|CannotFindDocumentRoot|Невозможно найти корень документа.|  
|XmlBufferQuotaExceeded|Размер, необходимый для буферизации содержимого XML, превышает квоту буфера.|  
|TraceCodeSecuritySessionClosedResponseSendFailure|Сбой при отправлении клиенту ответного сообщения о закрытии сеанса безопасности.|  
|UnableToResolveReferenceInSamlSignature|Невозможно разрешить указанную ссылку в сигнатуре SAML с AssertionID.|  
|SAMLSubjectRequiresNameIdentifierOrConfirmationMethod|Для SamlSubject требуется, чтобы был указан параметр "NameIdentifier" или "ConfirmationMethod". Оба отсутствуют.|  
|SAMLAttributeMissingNamespaceAttributeOnRead|Значение параметра "Namespace" для считываемого атрибута SamlAttribute отсутствует или имеет длину 0.|  
|SAMLSubjectConfirmationClauseMissingConfirmationMethodOnRead|Не удалось найти "ConfirmationMethod" в считываемом подтверждении SamlSubjectConfirmation.|  
|SecurityTokenRequirementHasInvalidTypeForProperty|Требование маркера имеет непредусмотренный тип для указанного свойства. Ожидаемый тип свойства имеет другое значение.|  
|TraceCodeNegotiationTokenProviderAttached|Подсоединен NegotiationTokenProvider.|  
|TraceCodeSpnegoClientNegotiationCompleted|Завершено согласование SSPI с помощью SpnegoTokenProvider.|  
|SAMLUnableToLoadUnknownElement|Выбранный SamlSerializer не может десериализовать этот элемент. Зарегистрируйте пользовательский SamlSerializer для десериализации пользовательских элементов.|  
|CreateSequenceRefused|Запрос создания последовательности отклонен пунктом назначения надежного обмена сообщениями.|  
|TraceCodeSecuritySessionRedirectApplied|Сеанс безопасности клиента перенаправлен.|  
|SecurityTokenRequirementDoesNotContainProperty|Требование к маркеру не содержит указанное свойство.|  
|SAMLAttributeValueCannotBeNull|Одно из attributeValue, найденное в SamlAttribute, имеет значение null. При создании атрибута SamlAttribute списки должны быть ненулевыми.|  
|ValueMustBeGreaterThanZero|Значение этого аргумента должно быть больше 0.|  
|TraceCodeNegotiationAuthenticatorAttached|Подсоединен NegotiationTokenAuthenticator.|  
|ValueMustBePositive||  
|SAMLAuthorizationDecisionShouldHaveOneAction|Оператор SamlAuthorizationDecisionStatement должен содержать не менее одного SamlAction.|  
|TraceCodeSecurityTokenAuthenticatorClosed|Структура проверки подлинности маркеров безопасности закрыта.|  
|TraceCodeSecurityAuditWrittenSuccess|Журнал аудита безопасности записан успешно.|  
|PrivateKeyNotDSA|Закрытый ключ не является ключом DSA.|  
|MessageNumberRollover|Для этой последовательности превышен максимальный порядковый номер.|  
|AESPaddingModeNotSupported|Указанный режим заполнения не поддерживается. Поддерживаются только PKCS7 и ISO10126.|  
|SAMLSubjectRequiresNameIdentifierOrConfirmationMethodOnRead|В считываемой конструкции SamlSubject не найдены необходимые элементы "NameIdentifier" и "ConfirmationMethod".|  
|TraceCodeSecurityAuditWrittenFailure|Ошибка при выполнении записи в журнал аудита безопасности.|  
|UnsupportedCryptoAlgorithm|Указанный алгоритм шифрования не поддерживается в этом контексте.|  
|SigningTokenHasNoKeysSupportingTheAlgorithmSuite|Маркер сигнатуры не имеет ключа, поддерживающего указанный набор алгоритмов.|  
|SAMLNameIdentifierMissingIdentifierValueOnRead|В считываемом идентификаторе SamlNameIdentifier отсутствует строка "Identifier".|  
|SAMLSubjectStatementRequiresSubject|Для оператора SAML Subject необходимо, чтобы был указан субъект SAML.|  
|TraceCodeSslClientCertMissing|Удаленному SSL-клиенту не удалось предоставить требуемый сертификат.|  
|SAMLTokenVersionNotSupported|Указанные основной номер версии и дополнительный номер версии не поддерживаются.|  
|TraceCodeConfigurationIsReadOnly|Конфигурация доступна только для чтения.|  
|TraceCodeSecuritySessionRenewFaultSendFailure|Не удалось отправить клиенту сообщение о сбое при обновлении сеансового ключа безопасности.|  
|TraceCodeSecurityInactiveSessionFaulted|Сбой неактивного сеанса безопасности был вызван сервером.|  
|SAMLUnableToLoadAttribute|Не удалось загрузить атрибут SamlAttribute.|  
|Psha1KeyLengthInvalid|Указана недопустимая длина ключа PSHA1.|  
|KeyIdentifierCannotCreateKey|Этот SecurityKeyIdentifier не имеет предложения, позволяющего создать ключ.|  
|X509IsInUntrustedStore|Указанный сертификат X.509 находится в хранилище для сертификатов без доверия.|  
|UnexpectedXmlChildNode|Указанный дочерний узел XML указанного типа является неожиданным для указанного элемента.|  
|TokenDoesNotMeetKeySizeRequirements|Указанный маркер не соответствует требованиям к размеру ключа для указанного набора алгоритмов.|  
|TraceCodeSecuritySessionRequestorStartOperation|На клиенте запущен сеанс безопасности.|  
|InvalidHexString|Неправильный формат шестнадцатеричной строки.|  
|SamlAttributeClaimResourceShouldBeAString|Этот конструктор SamlAttribute требует, чтобы ресурс требования имел тип "string".|  
|SamlSigningTokenNotFound|Утверждение SamlAssertion подписано, но невозможно найти маркер, подписавший SamlAssertion. Убедитесь, что распознаватель маркеров SecurityTokenResolver содержит маркер, подписавший SamlAssertion.|  
|TraceCodeSecuritySpnToSidMappingFailure|ServicePrincipalName не может быть сопоставлен SecurityIdentifier.|  
|UnableToCreateSignatureFormatterFromAsymmetricCrypto|Не удалось создать модуль создания формата сигнатуры для указанного алгоритма из указанного асимметричного шифрования.|  
|TraceCodeSecurityServerSessionClosedFaultSent|Сеанс безопасности сервера отправил клиенту сообщение о сбое закрытия сеанса.|  
|UnableToFindPrefix|Не удается найти префикс для указанного явно используемого префикса в указанном элементе.|  
|TraceCodeSecurityTokenAuthenticatorOpened|Структура проверки подлинности маркеров безопасности открыта.|  
|RequiredAttributeMissing|Указанный атрибут требуется для указанного элемента.|  
|LocalIdCannotBeEmpty|Локальный идентификатор localId не может быть пустым. Укажите допустимый "localId".|  
|ValueMustBeInRange|Значение этого аргумента должно попадать в указанный интервал.|  
|TraceCodeIssuanceTokenProviderBeginSecurityNegotiation|IssuanceTokenProvider запустил новое согласование режима безопасности.|  
|InvalidNtMapping|Не удалось сопоставить указанный сертификат X.509 с учетной записью Windows. Требуется альтернативное имя темы UPN.|  
|AESCryptSetKeyParamFailed|Не удалось установить указанный параметр ключа.|  
|TraceCodeSecuritySessionClosedResponseReceived|Сеанс безопасности клиента получил от сервера ответное сообщение о закрытии.|  
|UnableToCreateSignatureDeformatterFromAsymmetricCrypto|Не удалось создать модуль удаления формата сигнатуры для указанного алгоритма из указанного асимметричного шифрования.|  
|TraceCodeIdentityModelAsyncCallbackThrewException|Асинхронный обратный вызов сгенерировал исключение.|  
|LengthMustBeGreaterThanZero|Длина этого аргумента должна быть больше 0.|  
|FoundMultipleCerts|Найдено несколько сертификатов X.509, с помощью условий поиска: StoreName, StoreLocation, FindType, FindValue. Укажите более точное значение.|  
|AtLeastOneTransformRequired|Элемент Transforms должен содержать хотя бы одно преобразование.|  
|SAMLTokenNotSerialized|Утверждение SamlAssertion не может быть сериализовано в XML. Подробнее см. в описании внутреннего исключения.|  
|TraceCodeSecurityBindingOutgoingMessageSecured|Протокол безопасности обеспечил защиту исходящего сообщения.|  
|KeyIdentifierClauseDoesNotSupportKeyCreation|Это предложение SecurityKeyIdentifierClause не поддерживает создание ключей.|  
|UnableToResolveTokenReference|Распознавателю маркеров не удалось разрешить ссылку на указанный маркер.|  
|UnsupportedEncryptionAlgorithm|Указанный алгоритм шифрования не поддерживается.|  
|SamlSerializerUnableToWriteSecurityKeyIdentifier|SamlSerializer не содержит сериализатора SecurityTokenSerializer, способного сериализовать указанный идентификатор SecurityKeyIdentifier. Если используется пользовательский идентификатор SecurityKeyIdentifier, необходимо предоставить пользовательский сериализатор SecurityTokenSerializer.|  
|SAMLAttributeShouldHaveOneValue|Не найдены значения атрибута. Атрибут SamlAttribute должен иметь хотя бы одно значение.|  
|TraceCodeSecurityBindingVerifyIncomingMessageFailure|Протоколу безопасности не удалось проверить входящее сообщение.|  
|SamlSigningTokenMissing|Утверждение SamlAssertion, переданное SamlSecurityTokenAuthenticator, не содержит маркера подписывания.|  
|NoPrivateKeyAvailable|Нет доступных закрытых ключей.|  
|ValueMustBeOne|Значение этого аргумента должно быть равно 1.|  
|TraceCodeSecurityPendingServerSessionRemoved|Ожидающий сеанс безопасности активирован сервером.|  
|TraceCodeImportSecurityChannelBindingExit|Завершена Security ImportChannelBinding.|  
|X509CertStoreLocationNotValid|StoreLocation должен иметь значение LocalMachine или CurrentUser.|  
|SettingdMayBeModifiedOnlyWhenTheWriterIsInStartState|Параметры модуля записи можно изменить, только когда он находится в состоянии запуска.|  
|ArgumentInvalidCertificate|Сертификат недействителен.|  
|DigestVerificationFailedForReference|Сбой проверки дайджеста для указанной ссылки.|  
|SAMLAuthorityBindingRequiresBinding|Атрибут "Binding", указанный в привязке SamlAuthorityBinding, не может иметь значение null или длину 0.|  
|AESInsufficientOutputBuffer|Размер буфера вывода должен быть больше указанного числа байтов.|  
|SAMLAuthorityBindingMissingBindingOnRead|Атрибут "Binding" для считываемой привязки SamlAuthorityBinding отсутствует или имеет длину 0.|  
|SAMLAuthorityBindingInvalidAuthorityKind|В считываемой привязке SamlAuthorityBinding указан неверный тип AuthorityKind. Формат AuthorityKind должен быть QName.|  
|ProvidedNetworkCredentialsForKerberosHasInvalidUserName|В сетевых учетных данных NetworkCredentials, предоставленных для маркера Kerberos, отсутствует допустимое имя пользователя.|  
|SSPIPackageNotSupported|Указанный SSPI-пакет не поддерживается.|  
|TokenCancellationNotSupported|Указанный поставщик маркера не поддерживает отмену маркеров.|  
|UnboundPrefixInQName|В указанном полном имени использован несвязанный префикс.|  
|SAMLAuthorizationDecisionResourceRequired|Атрибут "resource", указанный для оператора SamlAuthorizationDecisionStatement, не может иметь значение null или длину 0.|  
|TraceCodeSecurityNegotiationProcessingFailure|Сбой согласования безопасности службы.|  
|SAMLAssertionIssuerRequired|Имя поставщика "Issuer" для утверждения SamlAssertion не может иметь значение null или быть пустым.|  
|UnableToCreateHashAlgorithmFromAsymmetricCrypto|Не удалось создать HashAlgorithm для указанного алгоритма из указанного асимметричного шифрования.|  
|SamlUnableToExtractSubjectKey|Идентификатор SecurityKeyIdentifier, найденный в SamlSubject, не может быть разрешен в какой-либо маркер SecurityToken. Распознаватель маркеров SecurityTokenResolver должен содержать маркер SecurityToken, в который разрешается идентификатор SecurityKeyIdentifier.|  
|ChildNodeTypeMissing|Указанный XML-элемент не имеет дочернего элемента указанного типа.|  
|TraceCodeSecurityPendingServerSessionClosed|Ожидающий сеанс безопасности был закрыт сервером.|  
|TraceCodeSecuritySessionCloseResponseSent|Сеанс безопасности сервера отправил клиенту ответное сообщение закрытия.|  
|TraceCodeSecurityIdentityHostNameNormalizationFailure|Невозможно нормализовать часть HostName адреса конечной точки.|  
|FailAcceptSecurityContext|Сбой в AcceptSecurityContext.|  
|EmptyXmlElementError|Указанный элемент не может быть пустым.|  
|PrefixNotDefinedForNamespace|Префикс указанного пространства имен не определен в этом контексте и не может быть объявлен.|  
|SAMLAuthorizationDecisionHasMoreThanOneEvidence|В считываемом операторе SamlAuthorizationDecisionStatement указано несколько конструкций Evidence. Это не допускается.|  
|SamlTokenAuthenticatorCanOnlyProcessSamlTokens|SamlSecurityTokenAuthenticator может обрабатывать только маркеры SamlSecurityToken. Был получен маркер указанного типа SecurityTokenType.|  
|SAMLAttributeStatementMissingAttributeOnRead|Считываемый оператор SamlAttributeStatement не содержит элементов "SamlAttribute". Это не допускается.|  
|CouldNotFindNamespaceForPrefix|Не удалось выполнить поиск пространства имен для указанного префикса.|  
|TraceCodeExportSecurityChannelBindingExit|Завершена Security ExportChannelBinding.|  
|AESCryptDecryptFailed|Ошибка при расшифровке указанных данных.|  
|SAMLAttributeNamespaceAttributeRequired|"Namespace" для атрибута SamlAttribute не может иметь значение null или длину 0.|  
|TraceCodeSpnegoServiceNegotiationCompleted|Завершено согласование SSPI с помощью SpnegoTokenAuthenticator.|  
|TraceCodeSecurityServerSessionRenewalFaultSent|Сеанс безопасности сервера отправил клиенту сообщение о сбое обновления ключа.|  
|AlgorithmMismatchForTransform|Несоответствие алгоритма для преобразования.|  
|UserNameAuthenticationFailed|Проверка подлинности имени пользователя или пароля с помощью указанного механизма завершилась неудачно. Проверка подлинности пользователя не выполнена.|  
|SamlInvalidSigningToken|Утверждение SamlAssertion было подписано маркером, который не был проверен согласно протоколу. Если используются сертификаты X.509, необходимо убедиться в правильности семантики проверки.|  
|TraceCodeSecurityServerSessionKeyUpdated|Сеансовый ключ безопасности был обновлен сервером.|  
|TraceCodeSecurityServerSessionCloseReceived|Сеанс безопасности сервера получил от клиента сообщение закрытия.|  
|SAMLAuthenticationStatementMissingSubject|В операторе SamlAuthenticationStatement пропущен обязательный оператор SamlSubjectStatement.|  
|UnexpectedEndOfFile|Неожиданный конец файла.|  
|UnsupportedAlgorithmForCryptoOperation|Указанный алгоритм не поддерживается для указанной операции.|  
|XmlLangAttributeMissing|Отсутствует обязательный атрибут xml:lang.|  
|TraceCodeSecurityImpersonationSuccess|Олицетворение безопасности на сервере успешно реализовано.|  
|SAMLAuthorityBindingMissingLocationOnRead|Атрибут "Location" для считываемой привязки SamlAuthorityBinding отсутствует или имеет длину 0.|  
|SAMLAttributeStatementMissingSubjectOnRead|Отсутствует элемент "SamlSubject" для оператора SamlAttributeStatement.|  
|SAMLAuthorizationDecisionStatementMissingSubjectOnRead|Отсутствует элемент "SamlSubject" для считываемого оператора SamlAuthorizationDecisionStatement.|  
|SAMLBadSchema|При чтении утверждения SamlAssertion обнаружено, что указанный элемент не соответствует схеме.|  
|SAMLAssertionIDIsInvalid|Указанный идентификатор "assertionId" для утверждения SamlAssertion должен начинаться с буквы или символа подчеркивания "_".|  
|TraceCodeSecurityActiveServerSessionRemoved|Активный сеанс безопасности удален сервером.|  
|UnableToCreateKeyedHashAlgorithmFromSymmetricCrypto|Не удалось создать keyedHashAlgorithm для указанного алгоритма из указанного симметричного шифрования.|  
|SAMLAuthenticationStatementMissingAuthenticationMethod|Метод "AuthenticationMethod", указанный для оператора SamlAuthenticationStatement, не может иметь значение null или длину 0.|  
|TraceCodeSecurityImpersonationFailure|Ошибка олицетворения безопасности на сервере.|  
|Значение по умолчанию|(Значение по умолчанию)|  
|UnsupportedNodeTypeInReader|Указанный тип узла с указанным именем не поддерживается.|
