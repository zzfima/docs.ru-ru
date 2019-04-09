---
title: <AppContextSwitchOverrides> Элемент
ms.custom: updateeachrelease
ms.date: 03/07/2019
helpviewer_keywords:
- AppContextSwitchOverrides
- compatibility switches
- configuration switches
- configuration
ms.assetid: 4ce07f47-7ddb-4d91-b067-501bd8b88752
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1bc4cd94d3acd37244e1d5b882612e4b1da91b90
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136465"
---
# <a name="appcontextswitchoverrides-element"></a>\<AppContextSwitchOverrides > элемент
Определяет один или несколько коммутаторов, используемых классом <xref:System.AppContext> для предоставления механизма отказа от новых функциональных возможностей.  
  
 \<configuration>  
 \<Среда выполнения >  
\<AppContextSwitchOverrides>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<AppContextSwitchOverrides value="name1=value1[[;name2=value2];...]" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`value`|Обязательный атрибут.<br /><br /> Определяет один или несколько имен параметров и связанных с ними логических значений.|  
  
### <a name="value-attribute"></a>значение атрибута  
  
|Значение|Описание|  
|-----------|-----------------|  
|«имя = значение»|Имя коммутатора предопределенные вместе с его значением (`true` или `false`). Несколько пар имя значение параметра разделяются точками с запятой («;»). Список имен предопределенных коммутатора, поддерживаемые платформой .NET Framework см. в разделе "Примечания".|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|  
  
## <a name="remarks"></a>Примечания  
 Начиная с .NET Framework 4.6, `<AppContextSwitchOverrides>` элемент в файле конфигурации разрешает вызывать API-Интерфейс для определения собственных приложений можно воспользоваться преимуществами новых функциональных возможностей или сохранения совместимости с предыдущими версиями библиотеки. Например, если изменилось поведение интерфейса API между двумя версиями библиотеки `<AppContextSwitchOverrides>` элемент разрешает вызывать этот API, чтобы отказаться от нового поведения в версиях библиотеки, которые поддерживают новые функции. Для приложений, которые вызывают API-интерфейсов в .NET Framework `<AppContextSwitchOverrides>` элемент также можно разрешить вызывающим объектам, которых приложения ориентированы на более ранней версии платформы .NET Framework можно согласиться на новые функциональные возможности, если их приложение работает на версии .NET Framework, который включает в себя функциональные возможности.  
  
 `value` Атрибут `<AppContextSwitchOverrides>` элемент состоит из одну строку, которая состоит из одного или нескольких пар имен и значений, разделенных точкой с запятой.  Каждое имя идентифицирует переключатель совместимости, и его соответствующее значение является логическим (`true` или `false`), указывающее, установлен ли переключатель. По умолчанию является параметром `false`, и библиотеки предоставляют новые функции. Они только предоставляют прежние функции, если задано значение (то есть его значение равно `true`). Это позволяет библиотекам предоставлять новое поведение для существующих API, что позволяет вызывающим объектам, которые зависят от предыдущего поведения, чтобы отказаться от новых функциональных возможностей.  
  
 .NET Framework поддерживает следующие параметры:  
  
|Имя коммутатора|Описание|Представленные|  
|-----------------|-----------------|----------------|  
|`Switch.MS.Internal.`<br/>`DoNotApplyLayoutRoundingToMarginsAndBorderThickness`|Определяет, использует ли Windows Presentation Foundation это алгоритм для прежних версий для макета элемента управления. Дополнительные сведения см. в разделе [Устранение рисков. Макет WPF](../../../migration-guide/mitigation-wpf-layout.md).|.NET Framework 4.6|  
|`Switch.MS.Internal.`<br/>`UseSha1AsDefaultHashAlgorithmForDigitalSignatures`|Определяет, является ли алгоритм по умолчанию, используемый для подписывания частей пакетов PackageDigitalSignatureManager SHA1 или SHA256.<br>Из-за конфликта с SHA1 корпорация Майкрософт рекомендует использовать SHA256.|.NET Framework 4.7.1|
|`Switch.System.Activities.`<br/>`UseMD5CryptoServiceProviderForWFDebugger`|Если задано значение `false`, позволяет выполнить отладку проектов рабочего процесса на основе XAML с помощью Visual Studio, когда система FIPS включена. Без него <xref:System.NullReferenceException> в вызовы методов в сборке System.Activities создается исключение.|.NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseMD5ForWFDebugger`|Определяет, использует ли контрольная сумма для экземпляра рабочего процесса в отладчике MD5 или SHA1. | .NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseSHA1HashForDebuggerSymbols`|Определяет, использует ли хэширования контрольной суммы рабочего процесса алгоритма SHA1, представленного как значение по умолчанию в .NET Framework 4.7 (`true`), или использование алгоритма SHA256 по умолчанию, представленного как значение по умолчанию в .NET Framework 4.8 (`false`).<br>Из-за конфликта с SHA1 корпорация Майкрософт рекомендует использовать SHA256.|.NET framework 4.8|
|`Switch.System.Diagnostics.`<br/>`IgnorePortablePDBsInStackTraces`|Элементы управления ли получить трассировки стека, при использовании переносимых PDB-файлов можно включить сведения о файле и строке источника. `false` Чтобы включить сведения о файле и строке источника; в противном случае `true`.|.NET Framework 4.7.2|
|`Switch.System.Drawing.`<br/>`DontSupportPngFramesInIcons`|Элементы управления ли <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> метод вызывает исключение при <xref:System.Drawing.Icon> наличии кадров PNG в объекте. Дополнительные сведения см. в разделе [Устранение рисков. Кадры PNG в объектах Icon](../../../migration-guide/mitigation-png-frames-in-icon-objects.md).|.NET Framework 4.6|
|`Switch.System.Drawing.Text.`<br/>`DoNotRemoveGdiFontsResourcesFromFontCollection`|Определяет, является ли <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType> должным образом при добавлении в коллекцию путем удаления объектов <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)?displayProperty=nameWithType> метод. `true` для поддержания устаревшее поведение; `false` для удаления всех объектов частной. |.NET Framework 4.7.2|
|`Switch.System.Drawing.Printing.`<br>`OptimizePrintPreview`|Элементы управления ли производительность <xref:System.Windows.Forms.PrintPreviewDialog> оптимизирован для сетевых принтеров. Дополнительные сведения см. в разделе [Обзор элемента управления PrintPreviewDialog](../../../winforms/controls/printpreviewdialog-control-overview-windows-forms.md).|.NET Framework 4.6|
|`Switch.System.Globalization.EnforceJapaneseEraYearRanges`|Определяет, проверяет ли диапазон лет для японского календаря, которые применяются эры. `true` для принудительного применения диапазон лет проверки, и `false` отключить их (поведение по умолчанию). Дополнительные сведения см. в разделе [работа с календарями](../../../../standard/datetime/working-with-calendars.md).|.NET Framework 4.6|
|`Switch.System.Globalization.EnforceLegacyJapaneseDateParsing`|Управляет ли только «1» распознается в качестве первого года эры японского календаря в операциях синтаксического анализа. `true` для распознавания только «1»; `false` для распознавания «1» или Ганнэн (поведение по умолчанию). Дополнительные сведения см. в разделе [работа с календарями](../../../../standard/datetime/working-with-calendars.md).|.NET Framework 4.6| 
|`Switch.System.Globalization.FormatJapaneseFirstYearAsANumber`|Управляет ли первый год эры японского календаря представляется как «1» или Ганнэн в операциях форматирования. `true` для форматирования первого года эры как «1». `false` отформатировать его как Ганнэн (поведение по умолчанию). Дополнительные сведения см. в разделе [работа с календарями](../../../../standard/datetime/working-with-calendars.md).|.NET Framework 4.6|
|`Switch.System.Globalization.NoAsyncCurrentCulture`|Управляет ли асинхронные операции не проходят из контекста вызывающего потока. Дополнительные сведения см. в разделе [поток CurrentCulture и CurrentUICulture между задачами](../../../migration-guide/retargeting/4.5.2-4.6.md#currentculture-and-currentuiculture-flow-across-tasks).|.NET Framework 4.6|  
|`Switch.System.IdentityModel.`<br/>`DisableMultipleDNSEntriesInSANCertificate`|Элементы управления ли <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> метод пытается сопоставить тип утверждения только с последней записью DNS. Дополнительные сведения см. в разделе [Устранение рисков. Метод X509CertificateClaimSet.FindClaims](../../../migration-guide/mitigation-x509certificateclaimset-findclaims-method.md).|.NET Framework 4.6.1|  
|`Switch.System.IdentityModel.`<br/>`EnableCachedEmptyDefaultAuthorizationContext`|Определяет, следует ли разрешить AuthorizationContext.Empty для возврата изменяемого объекта.|.NET Framework 4.6|  
|`Switch.System.IO.BlockLongPaths`|Элементы управления ли пути длиной более `MAX_PATH` throw (260 символов) <xref:System.IO.PathTooLongException>. Дополнительные сведения см. в разделе [поддержка длинных путей](../../../migration-guide/retargeting/4.6.1-4.6.2.md#long-path-support).|.NET Framework 4.6.2|  
|`Switch.System.IO.Compression.`<br/>`DoNotUseNativeZipLibraryForDecompression`|Указывает, используются ли собственные процедуры ОС для распаковки с <xref:System.IO.Compression.DeflateStream> класса. `false` Чтобы использовать собственный API; `true` использовать <xref:System.IO.Compression.DeflateStream> реализации.|.NET Framework 4.7.2|
|`Switch.System.IO.Compression.ZipFile.`<br/>`UseBackslash`|Использует обратную косую черту (»\\«) вместо косой черты («/») в качестве разделителя пути в <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType> свойство. Дополнительные сведения см. в разделе [устранение рисков: Разделитель пути ZipArchiveEntry.FullName](../../../migration-guide/mitigation-ziparchiveentry-fullname-path-separator.md).|.NET Framework 4.6.1|  
|`Switch.System.IO.Ports.`<br/>`DoNotCatchSerialStreamThreadExceptions`|Управляет ли операционная система исключений, которые вызываются в фоновых потоках, созданных с помощью <xref:System.IO.Ports.SerialPort> потоки завершить процесс.|.NET Framework 4.7.1| 
|`Switch.System.IO.`<br/>`UseLegacyPathHandling`|Управляет ли нормализация путей прежних версий используется и поддерживаемых путях URI <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> и <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> методы. Дополнительные сведения см. в разделе [Устранение рисков. Нормализация путей](../../../migration-guide/mitigation-path-normalization.md) и [устранение рисков: Проверки двоеточий в путях](../../../migration-guide/mitigation-path-colon-checks.md).|.NET Framework 4.6.2|
|`Switch.System.`<br/>`MemberDescriptorEqualsReturnsFalseIfEquivalent`|Управляет ли тест для проверки на равенство сравнивает <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=nameWithType> свойство одного объекта с <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=nameWithType> свойство значения второго объекта. Дополнительные сведения см. в разделе [неправильная реализация MemberDescriptor.Equals](../../../migration-guide/retargeting/4.6.1-4.6.2.md#incorrect-implementation-of-memberdescriptorequals).|.NET Framework 4.6.2|  
 `Switch.System.Net.`<br/>`DontCheckCertificateEKUs`|Отключает сертификатов проверки идентификатор (OID) расширенного использования ключа (EKU) объектов. Расширение расширенного использования ключа (EKU) — это коллекция идентификаторов объекта (OID), которые указывают приложения, использующие ключ.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchSendAuxRecord`|Отключение TLS 1.0 браузера воспользоваться от SSL/TLS (BEAST) по устранению рисков, отключив использование SCH_SEND_AUX_RECORD.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchUseStrongCrypto`|Элементы управления ли <xref:System.Net.ServicePointManager?displayProperty=nameWithType> и <xref:System.Net.Security.SslStream?displayProperty=nameWithType> классы могут использовать протокол SSL 3.0. Дополнительные сведения см. в разделе [Устранение рисков. протоколами TLS](../../../migration-guide/mitigation-tls-protocols.md).|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSystemDefaultTlsVersions`|Отключает версии SystemDefault TLS, возврат к Tls12, Tls11, Tls по умолчанию.|.NET Framework 4.7|
|`Switch.System.Net.`<br/>`DontEnableTlsAlerts`|Отключает оповещения на стороне сервера SslStream TLS.|.NET Framework 4.7|
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseECMAScriptV6EscapeControlCharacter` |Элементы управления ли [DataContractJsonSerializer](xref:System.Runtime.Serialization.Json.DataContractJsonSerializer) сериализует некоторые управляющие символы, основанные на стандартах ECMAScript версий 6 и 8. Дополнительные сведения см. в разделе [Устранение рисков. Сериализация управляющих символов с помощью DataContractJsonSerializer](../../../migration-guide/mitigation-serialization-control-characters.md)| .NET Framework 4.7 |
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseTimeZoneInfo`|Элементы управления ли <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> поддерживает несколько корректировки или только одного набора для часового пояса. Если `true`, он использует <xref:System.TimeZoneInfo> введите для сериализации и десериализации данных даты и времени; в противном случае используется <xref:System.TimeZone> тип, который не поддерживает несколько правил коррекции.|.NET Framework 4.6.2|
|`Switch.System.Runtime.Serialization.UseNewMaxArraySize`|Элементы управления ли <xref:System.Runtime.Serialization.ObjectManager?displayProperty=nameWithType> использует больший размер массива во время сериализации и десериализации объектов. Установите этот переключатель, `true` для повышения производительности при сериализации и десериализации больших графов объектов, типы, такие как <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>. |.NET Framework 4.7.2|
|`Switch.System.Security.ClaimsIdentity.`<br/>`SetActorAsReferenceWhenCopyingClaimsIdentity`|Элементы управления ли <xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=nameWithType> конструктор задает новый объект <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=nameWithType> свойство со ссылкой на существующий объект. Дополнительные сведения см. в разделе [Устранение рисков. Конструктор ClaimsIdentity](../../../migration-guide/mitigation-claimsidentity-constructor.md).|.NET Framework 4.6.2|  
|`Switch.System.Security.Cryptography.`<br/>`AesCryptoServiceProvider.DontCorrectlyResetDecryptor`|Элементы управления ли попытка повторно использовать <xref:System.Security.Cryptography.AesCryptoServiceProvider> выдает дешифратор <xref:System.Security.Cryptography.CryptographicException>. Дополнительные сведения см. в разделе [дешифратор AesCryptoServiceProvider предоставляет преобразование для повторного использования](../../../migration-guide/retargeting/4.6.1-4.6.2.md#aescryptoserviceprovider-decryptor-provides-a-reusable-transform).|.NET Framework 4.6.2|
|`Switch.System.Security.Cryptography.`<br/>`DoNotAddrOfCspParentWindowHandle`|Элементы управления ли значение [CspParameters.ParentWindowHandle](xref:System.Security.Cryptography.CspParameters.ParentWindowHandle) свойство [IntPtr](xref:System.IntPtr) что представляет область памяти окна обработки, или это дескриптор окна (HWND). Дополнительные сведения см. в разделе [Устранение рисков. CspParameters.ParentWindowHandle ожидает HWND](../../../migration-guide/retargeting/4.6.2-4.7.md#cspparametersparentwindowhandle-now-expects-hwnd-value). |.NET Framework 4.7|   
|`Switch.System.Security.Cryptography.Pkcs.`<br/>`UseInsecureHashAlgorithms`|Определяет, является ли значение по умолчанию для некоторых операций SignedCMS SHA1 или SHA256.<br>Из-за конфликта с SHA1 корпорация Майкрософт рекомендует использовать SHA256.|.NET Framework 4.7.1|
|`Switch.System.Security.Cryptography.Xml.`<br/>`UseInsecureHashAlgorithms`|Определяет, является ли значение по умолчанию для некоторых операций SignedXML SHA1 или SHA256.<br>Из-за конфликта с SHA1 корпорация Майкрософт рекомендует использовать SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`AllowUnsignedToHeader`|Определяет, является ли `TransportWithMessageCredential` режим безопасности разрешает сообщения с неподписанным заголовком «to». Это параметр согласием. Дополнительные сведения см. в разделе [изменения среды выполнения в .NET Framework 4.6.1](../../../migration-guide/runtime/4.5.2-4.6.1.md#windows-communication-foundation-wcf).|.NET Framework 4.6.1| 
|`Switch.System.ServiceModel.`<br/>`DisableAddressHeaderCollectionValidation`>|Элементы управления ли <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> конструктор вызывает <xref:System.ArgumentException> Если один из элементов является `null`.|.NET Framework 4.7.1| 
|`Switch.System.ServiceModel.`<br />`DisableCngCertificates`|Определяет, вызывает ли попытка использовать X509 сертификатов с помощью поставщика хранилища ключей CSG исключение. Дополнительные сведения см. в разделе [безопасность транспорта WCF поддерживает сертификаты, сохраненные с помощью CNG](../../../migration-guide/retargeting/4.6.1-4.6.2.md#wcf-transport-security-supports-certificates-stored-using-cng).|.NET Framework 4.6.1|
|`Switch.System.ServiceModel.`<br/>`DisableExplicitConnectionCloseHeader`|При использовании транспорта HTTP с резидентной службы, установка этого значения в `true` заставляет игнорировать Добавление приложения WCF `Connection: close` заголовок, чтобы заголовки ответа для запроса. Установка этого значения в `false` включает добавление `Connection: close` заголовка для заголовков ответа, что приводит к закрытие сокета запроса после отправки ответа.|.NET Framework 4.6|
|`Switch.System.ServiceModel.`<br/>`DisableOperationContextAsyncFlow`|Обрабатывает взаимоблокировок, возникающих вследствие ограничения экземпляров реентерабельной службе к одному потоку выполнения за раз.|.NET Framework 4.6.2|
|`Switch.System.ServiceModel.`<br/>`DisableUsingServicePointManagerSecurityProtocols`|Вместе с `Switch.System.Net.DontEnableSchUseStrongCrypto`, определяет, использует ли безопасность сообщений WCF TLS 1.1 и TLS 1.2.|.NET Framework 4.7 |    
|`Switch.System.ServiceModel.`<br/>`DontEnableSystemDefaultTlsVersions`|Значение `false` в конфигурации по умолчанию, чтобы разрешить операционной системе выбирать протокол. Значение `true` задаются по умолчанию последняя доступная версия протокола. (Также доступно на ветвь предыдущих версий framework обслуживания)|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InMsmqEncryptionAlgorithm`|Определяет, является ли сообщение по умолчанию, алгоритм для сообщения MSMQ в WCF подписи SHA1 или SHA256.<br>Из-за конфликта с SHA1 корпорация Майкрософт рекомендует использовать SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InPipeConnectionGetHashAlgorithm`|Определяет, использует ли WCF, SHA1 или хэш SHA256 для формирования случайных имен для именованных каналов.<br>Из-за конфликта с SHA1 корпорация Майкрософт рекомендует использовать SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.Internals`<br/>`IncludeNullExceptionMessageInETWTrace`|Определяет, следует ли создавать [NullReferenceException](xref:System.NullReferenceException) когда сообщение об исключении принимает значение null.|.NET Framework 4.7|  
|`Switch.System.ServiceProcess.`<br/>`DontThrowExceptionsOnStart`|Управляет ли исключения, возникшие при запуске службы передаются вызывающему объекту <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> метод.|.NET Framework 4.7.1|
|`Switch.System.Uri.`<br/>`DontEnableStrictRFC3986ReservedCharacterSets`|Определяет, является ли определенные символы, закодированные процентами, которые иногда декодировались теперь всегда остаются закодированными. Если `true`, они являются декодированный; в противном случае `false`.|.NET Framework 4.7.2|
|`Switch.System.Uri.`<br/>`DontKeepUnicodeBidiFormattingCharacters`|Определяет обработку двунаправленных символов Юникода в URI. `true` Чтобы убрать их из URI; `false` для сохранения и процентов закодировать их.|.NET Framework 4.7.2|
|`Switch.System.Windows.Controls.Grid.`<br/>`StarDefinitionsCanExceedAvailableSpace` |Определяет, применяется ли Windows Presentation Foundation старый алгоритм (`true`) или новый алгоритм (`false`) в выделении пространства для \*-столбцов. Дополнительные сведения см. в разделе [Устранение рисков. Выделение пространства элемента управления сетки для столбцов со звездочкой](../../../migration-guide/retargeting/4.6.2-4.7.md#wpf-grid-allocation-of-space-to-star-columns). |.NET Framework 4.7 |
|`Switch.System.Windows.Controls.TabControl.`<br/>`SelectionPropertiesCanLagBehindSelectionChangedEvent`|События изменения ли селектора или вкладку управления всегда обновляет значение своего свойства выбранное значение перед порождением выделение элементов управления.|.NET Framework 4.7.1|
|`Switch.System.Windows.Controls.Text.`<br/>`UseAdornerForTextboxSelectionRendering`|Определяет, доступен ли выбор на основе не графический элемент отрисовки для <xref:System.Windows.Controls.TextBox> и <xref:System.Windows.Controls.PasswordBox> элементы управления для предотвращения перекрыто текст (`false`), текст выводится только в слое графических элементов или (`true`).|.NET Framework 4.7.2|
|`Switch.System.Windows.Data.Binding.`<br/>`IListIndexerHidesCustomIndexer`|Указывает, используются ли пользовательский интерфейс IList индексаторы неправильно (`false`) или правильно (`true`) по <xref:System.Windows.Data.Binding?displayProperty=nameWithtype> класса.|.NET framework 4.8|
|`Switch.System.Windows.DoNotScaleForDpiChanges`|Определяет, происходят ли изменения DPI в системе (значение `false`) или для каждого монитора (значение `true`).|.NET Framework 4.6.2|
|`Switch.System.Windows.`<br/>`DoNotUsePresentationDpiCapabilityTier2OrGreater`|Элементы управления ли увеличение размера элементов управления в <xref:System.Windows.Interop.HwndHost?displayProperty=nameWithType> отключены, когда WPF выполняется в режиме учитывать для каждого монитора (`true`) или включена (`false`).|.NET framework 4.8|
|`Switch.System.Windows.Forms.`<br/>`DomainUpDown.UseLegacyScrolling`|Определяет, должен ли разработчик особым образом обрабатывать <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> действие, если присутствует текст элемента управления. `true` для обработки <xref:System.Windows.Forms.DomainUpDown.UpButton> действия; `false` для <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> и <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> действия должны быть правильно синхронизированы.|.NET Framework 4.7.2|
|`Switch.System.Windows.Forms.`<br />`DontSupportReentrantFilterMessage`|Отказ от код, который позволяет использовать настраиваемый <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> реализацию, чтобы безопасно фильтровать сообщения без создания исключения при <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> вызывается метод. Дополнительные сведения см. в разделе [Устранение рисков. Пользовательские реализации IMessageFilter.PreFilterMessage](../../../migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).|.NET Framework 4.6.1|  
|`Switch.System.Windows.Forms.`<br/>`UseLegacyContextMenuStripSourceControlValue`|Определяет, является ли <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> свойство возвращает систему управления версиями, когда пользователь открывает меню из вложенных <xref:System.Windows.Forms.ToolStripMenuItem> элемента управления. `true` для возврата `null`, устаревшее поведение; `false` для возврата системы управления версиями.|.NET Framework 4.7.2|
|`Switch.System.Windows.Forms.UseLegacyToolTipDisplay`|Определяет, отключено ли поддержка вызова подсказки (`true`) или включена (`false`). Для включения поддержки вызова подсказки также требуются прежние функции специальных возможностей определяется `Switch.UseLegacyAccessibilityFeatures`, `Switch.UseLegacyAccessibilityFeatures.2`, и `Switch.UseLegacyAccessibilityFeatures.3` все отключена (значение `false`).|.NET framework 4.8|
|`Switch.System.Windows.Input.Stylus.`<br/>`EnablePointerSupport`|Определяет, является ли необязательным `WM_POINTER`-stack на основе сенсорного управления или пера включено в приложениях WPF. Дополнительные сведения см. в разделе [Устранение рисков. Перо поддержка сенсорного управления на основе указателя и](../../../migration-guide/mitigation-pointer-based-touch-and-stylus-support.md)|.NET Framework 4.7|
|`Switch.System.Windows.Markup.`<br/>`DoNotUseSha256ForMarkupCompilerChecksumAlgorithm`|Определяет, является ли алгоритм хэширования по умолчанию, используемый для контрольные суммы SHA256 (`false`) или SHA1 (`true`).<br>Из-за конфликта с SHA1 корпорация Майкрософт рекомендует использовать SHA256.|.NET Framework 4.7.2|
|`Switch.System.Windows.Media.ImageSourceConverter.`<br/>`OverrideExceptionWithNullReferenceException`|Управляет ли прежних версий [NullReferenceException](xref:System.NullReferenceException) возникает исключение вместо исключения, которые точнее указывают на причину исключения (например, [DirectoryNotFoundException](xref:System.IO.DirectoryNotFoundException) или [ FileNotFoundException](xref:System.IO.FileNotFoundException). Он предназначен для использования кода, который зависит от обработки [NullReferenceException](xref:System.NullReferenceException). | .NET Framework 4.7 |
|`Switch.System.Workflow.ComponentModel.`<br/>`UseLegacyHashForXomlFileChecksum`|Элементы управления ли хэширования контрольной суммы файлов XOML в проект рабочего процесса построения, используют алгоритм MD5 (`true`), либо использовать алгоритма SHA256, представленного как значение по умолчанию в .NET Framework 4.8.<br>Из-за конфликта проблем с MD5 Корпорация Майкрософт рекомендует SHA256.|.NET framework 4.8|
|`Switch.System.Workflow.Runtime.`<br/>`UseLegacyHashForSqlTrackingCacheKey`|Определяет, использует ли хэширования контрольной суммы, службы SqlTrackingService алгоритм MD5 (`true`) для кэшированных строк или того, использует ли он был представлен как по умолчанию в .NET Framework 4.8 алгоритма SHA256.<br>Из-за конфликта проблем с MD5 Корпорация Майкрософт рекомендует SHA256.|.NET framework 4.8|
|`Switch.System.Workflow.Runtime.`<br/>`UseLegacyHashForWorkflowDefinitionDispenserCacheKey`|Управляет ли хэширования контрольной суммы средой выполнения рабочего процесса использует алгоритм MD5 (`true`) для определения кэшированных рабочих процессов, или использование алгоритма SHA256, представленного как значение по умолчанию в .NET Framework 4.8.<br>Из-за конфликта проблем с MD5 Корпорация Майкрософт рекомендует SHA256.|.NET framework 4.8|
|`Switch.UseLegacyAccessibilityFeatures`|Элементы управления ли специальные возможности доступны начиная с .NET Framework 4.7.1 включены или отключены. | .NET Framework 4.7.1 |
|`Switch.UseLegacyAccessibilityFeatures.2`|Элементы управления, включены ли специальные возможности служб .NET Framework 4.7.2 (`false`) или отключена (`true`). Если `true`, `Switch.UseLegacyAccessibilityFeatures` также должны быть `true` включить специальные возможности .NET Framework 4.7.1.|.NET Framework 4.7.2|
|`Switch.UseLegacyAccessibilityFeatures.3`|Элементы управления, включены ли специальные возможности, представленные в .NET Framework 4.8 (`false`) или отключена (`true`). Если `true`, `Switch.UseLegacyAccessibilityFeatures` и `Switch.UseLegacyAccessibilityFeatures.2` также должны быть `true`.|.NET framework 4.8|
|`Switch.UseLegacyToolTipDisplay`|Элементы управления ли подсказки должны displaed, когда пользователь наводит курсор мыши над элементом управления WPF (`true`), или они отображаются ли фокус клавиатуры и с помощью сочетания клавиш (`false`, поведение по умолчанию). Для приложений на .NET Framework 4.8, но предназначенные для предыдущих версий платформы .NET Framework, что позволяет фокус ввода с клавиатуры и требуется поддержка ключа контекстное `Switch.UseLegacyAccessibilityFeatures`, `Switch.UseLegacyAccessibilityFeatures.2`, и `Switch.UseLegacyAccessibilityFeatures.3` и установите `false`.|.NET framework 4.8|
|`System.Xml.`<br /><br /> `IgnoreEmptyKeySequences`|Определяет, игнорируются ли пустые последовательности ключей в составные ключи проверки XSD-схемы. Дополнительные сведения см. в разделе [Устранение рисков. Проверка схемы XML](../../../migration-guide/mitigation-xml-schema-validation.md).|.NET Framework 4.6|  
  
> [!NOTE]
>  Вместо добавления `AppContextSwitchOverrides` элемент файла конфигурации приложения, можно также задать параметры программным образом путем вызова `static` (в C#) или `Shared` (в Visual Basic) <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> метод.  
  
 Разработчики библиотек можно также определить настраиваемые параметры, которые вызывающие методы могли отказаться от измененные функции, появившиеся в более поздних версиях их библиотеки. Дополнительные сведения см. в описании класса <xref:System.AppContext>.  
  
## <a name="switches-in-aspnet-applications"></a>Параметры в приложениях ASP.NET

Можно настроить приложение ASP.NET для использования параметров совместимости, добавив [ \<Добавить >](../../../configure-apps/file-schema/appsettings/add-element-for-appsettings.md) элемент [ \<appSettings >](../../../configure-apps/file-schema/appsettings/index.md) раздел файла web.config. 

В следующем примере используется `<add>` элемент, чтобы добавить два параметра для `<appSettings>` раздел файла web.config:

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="example"></a>Пример

 В следующем примере используется `AppContextSwitchOverrides` для определения переключатель совместимости одного приложения, `Switch.System.Globalization.NoAsyncCurrentCulture`, язык и региональные параметры, препятствующая из потока между потоками в асинхронных вызовах методов.  
  
```xml  
<configuration>  
   <runtime>  
      <AppContextSwitchOverrides value="Switch.System.Globalization.NoAsyncCurrentCulture=true" />  
   </runtime>  
</configuration>  
```  
  
 В следующем примере используется `AppContextSwitchOverrides` для определения двух переключатели совместимости приложений, `Switch.System.Globalization.NoAsyncCurrentCulture` и `Switch.System.IO.BlockLongPaths`. Обратите внимание на то, что точки с запятой разделяет две пары имя/значение.  
  
```xml  
<configuration>  
    <runtime>  
       <AppContextSwitchOverrides   
          value="Switch.System.Globalization.NoAsyncCurrentCulture=true;Switch.System.IO.BlockLongPaths=true" />  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.AppContext?displayProperty=nameWithType>
- [\<Среда выполнения > элемент](runtime-element.md)
- [\<Конфигурация > элемент](../configuration-element.md)
