---
title: AppContextSwitchOverrides, элемент
ms.custom: updateeachrelease
ms.date: 04/18/2019
helpviewer_keywords:
- AppContextSwitchOverrides
- compatibility switches
- configuration switches
- configuration
ms.assetid: 4ce07f47-7ddb-4d91-b067-501bd8b88752
ms.openlocfilehash: 2495ddbc89caf0b72cfc0e6a1647e8f2da291778
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347186"
---
# <a name="appcontextswitchoverrides-element"></a>\<AppContextSwitchOverrides > элемент

Определяет один или несколько коммутаторов, используемых классом <xref:System.AppContext> для предоставления механизма отказа от новых функциональных возможностей.

[ **\<configuration>** ](../configuration-element.md)\
[ **> среды выполнения\<** ](runtime-element.md) &nbsp;&nbsp;\
&nbsp;&nbsp;&nbsp;&nbsp; **\<AppContextSwitchOverrides >**

## <a name="syntax"></a>Синтаксис

```xml
<AppContextSwitchOverrides value="name1=value1[[;name2=value2];...]" />
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы
 Следующие разделы описывают атрибуты, дочерние элементы и родительские элементы.

### <a name="attributes"></a>Атрибуты

|Атрибут|Описание|
|---------------|-----------------|
|`value`|Обязательный атрибут.<br /><br /> Определяет одно или несколько имен переключателей и связанных с ними логических значений.|

### <a name="value-attribute"></a>Атрибут value

|{2&gt;Value&lt;2}|Описание|
|-----------|-----------------|
|"имя = значение"|Предопределенное имя коммутатора вместе со значением (`true` или `false`). Несколько пар "имя-значение" переключателей разделяются точкой с запятой (";"). Список стандартных имен коммутаторов, поддерживаемых .NET Framework, см. в разделе "Примечания".|

### <a name="child-elements"></a>Дочерние элементы
 Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|

## <a name="remarks"></a>Заметки
 Начиная с .NET Framework 4,6, элемент `<AppContextSwitchOverrides>` в файле конфигурации позволяет вызывающим объектам API определить, может ли их приложение использовать преимущества новых функциональных возможностей или сохранить совместимость с предыдущими версиями библиотеки. Например, если поведение API изменилось между двумя версиями библиотеки, элемент `<AppContextSwitchOverrides>` позволяет вызывающим объектам этого API отказаться от нового поведения в версиях библиотеки, поддерживающих новые функциональные возможности. Для приложений, которые вызывают интерфейсы API в .NET Framework, элемент `<AppContextSwitchOverrides>` может также разрешить вызывающим объектам, приложения которых нацелены на более раннюю версию .NET Framework, использовать новые функции, если их приложение выполняется в версии .NET Framework, которая включает эти функции.

 Атрибут `value` элемента `<AppContextSwitchOverrides>` состоит из одной строки, состоящей из одной или нескольких пар "имя-значение", разделенных точкой с запятой.  Каждое имя определяет переключатель совместимости, и его соответствующее значение является логическим (`true` или `false`), которое указывает, задан ли параметр. По умолчанию параметр имеет значение `false`, а библиотеки предоставляют новые функциональные возможности. Они предоставляют только предыдущие функции, если задан параметр (то есть его значение `true`). Это позволяет библиотекам предоставлять новое поведение для существующего API, одновременно позволяя вызывающим объектам, которые зависят от предыдущего поведения, отказаться от новых функциональных возможностей.

 .NET Framework поддерживает следующие параметры:

|Имя коммутатора|Описание|Операционные системы, в которых впервые появилась эта политика|
|-----------------|-----------------|----------------|
|`Switch.MS.Internal.`<br/>`DoNotApplyLayoutRoundingToMarginsAndBorderThickness`|Определяет, использует ли Windows Presentation Foundation устаревший алгоритм для макета элемента управления. Дополнительные сведения см. в разделе [Устранение рисков. Макет WPF](../../../migration-guide/mitigation-wpf-layout.md).|.NET Framework 4.6|
|`Switch.MS.Internal.`<br/>`UseSha1AsDefaultHashAlgorithmForDigitalSignatures`|Определяет, используется ли алгоритм по умолчанию для подписывания частей пакета с помощью PackageDigitalSignatureManager — SHA1 или SHA256.<br>Из-за конфликта с SHA1 корпорация Майкрософт рекомендует использовать SHA256.|.NET Framework 4.7.1|
|`Switch.System.Activities.`<br/>`UseMD5CryptoServiceProviderForWFDebugger`|Если задано значение `false`, позволяет выполнять отладку проектов рабочих процессов на основе XAML с помощью Visual Studio, когда включен FIPS. Без него <xref:System.NullReferenceException> создается в вызовах методов в сборке System. Activitys.|.NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseMD5ForWFDebugger`|Определяет, использует ли контрольная сумма для экземпляра рабочего процесса в отладчике MD5 или SHA1. | .NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseSHA1HashForDebuggerSymbols`|Определяет, использует ли хэш контрольной суммы рабочего процесса алгоритм SHA1, представленный в качестве значения по умолчанию в .NET Framework 4,7 (`true`), или используется ли алгоритм SHA256 по умолчанию в .NET Framework 4,8 (`false`).<br>Из-за конфликта с SHA1 корпорация Майкрософт рекомендует использовать SHA256.|.NET Framework 4.8|
|`Switch.System.Diagnostics.`<br/>`IgnorePortablePDBsInStackTraces`|Определяет, получают ли трассировкы стека при использовании переносимых PDB, могут включать исходные сведения о файлах и строках. `false` включить сведения о файле и строке исходного кода; в противном случае `true`.|.NET Framework 4.7.2|
|`Switch.System.Drawing.`<br/>`DontSupportPngFramesInIcons`|Определяет, вызывает ли метод <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> исключение, когда объект <xref:System.Drawing.Icon> содержит кадры PNG. Дополнительные сведения см. в разделе [Устранение рисков: кадры PNG кадров в объектах Icon](../../../migration-guide/mitigation-png-frames-in-icon-objects.md).|.NET Framework 4.6|
|`Switch.System.Drawing.Text.`<br/>`DoNotRemoveGdiFontsResourcesFromFontCollection`|Определяет, должны ли <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType> объекты правильно удаляться при добавлении в коллекцию методом <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)?displayProperty=nameWithType>. `true` для поддержки устаревшего поведения; `false` удалить все объекты частных шрифтов. |.NET Framework 4.7.2|
|`Switch.System.Drawing.Printing.`<br>`OptimizePrintPreview`|Определяет, оптимизирована ли производительность <xref:System.Windows.Forms.PrintPreviewDialog> для сетевых принтеров. Дополнительные сведения см. в разделе [Общие сведения об элементе управления PrintPreviewDialog](../../../winforms/controls/printpreviewdialog-control-overview-windows-forms.md).|.NET Framework 4.6|
|`Switch.System.Globalization.EnforceJapaneseEraYearRanges`|Определяет, применяется ли проверка диапазона лет для Эр в японском календаре. `true` для принудительного применения проверок диапазона лет и `false` их отключения (поведение по умолчанию). Дополнительные сведения см. в разделе [Работа с календарями](../../../../standard/datetime/working-with-calendars.md).|.NET Framework 4.6|
|`Switch.System.Globalization.EnforceLegacyJapaneseDateParsing`|Определяет, распознается ли только "1" как первый год японской эры в японском календаре в операциях синтаксического анализа. `true` распознать только "1"; `false`, чтобы распознать значение "1" или Ганнен (поведение по умолчанию). Дополнительные сведения см. в разделе [Работа с календарями](../../../../standard/datetime/working-with-calendars.md).|.NET Framework 4.6|
|`Switch.System.Globalization.FormatJapaneseFirstYearAsANumber`|Определяет, представляется ли первый год японской эры календаря как "1" или Ганнен в операциях форматирования. `true` чтобы отформатировать первый год эры как "1"; `false`, чтобы отформатировать его как Ганнен (поведение по умолчанию). Дополнительные сведения см. в разделе [Работа с календарями](../../../../standard/datetime/working-with-calendars.md).|.NET Framework 4.6|
|`Switch.System.Globalization.NoAsyncCurrentCulture`|Определяет, не поступают ли асинхронные операции из контекста вызывающего потока. Дополнительные сведения см. в разделе [потоки CurrentCulture и CurrentUICulture между задачами](../../../migration-guide/retargeting/4.5.2-4.6.md#currentculture-and-currentuiculture-flow-across-tasks).|.NET Framework 4.6|
|`Switch.System.IdentityModel.`<br/>`DisableMultipleDNSEntriesInSANCertificate`|Определяет, пытается ли метод <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> сопоставлять тип утверждения только с последней записью DNS. Дополнительные сведения см. в разделе [Устранение рисков: метод X509CertificateClaimSet.FindClaims](../../../migration-guide/mitigation-x509certificateclaimset-findclaims-method.md).|.NET Framework 4.6.1|
|`Switch.System.IdentityModel.`<br/>`EnableCachedEmptyDefaultAuthorizationContext`|Определяет, разрешено ли значение AuthorizationContext. Empty для возврата изменяемого объекта.|.NET Framework 4.6|
|`Switch.System.IO.BlockLongPaths`|Управляет тем, что пути длиннее, чем `MAX_PATH` (260 символов), вызывают <xref:System.IO.PathTooLongException>. Дополнительные сведения см. в разделе [Поддержка длинных путей](../../../migration-guide/retargeting/4.6.1-4.6.2.md#long-path-support).|.NET Framework 4.6.2|
|`Switch.System.IO.Compression.`<br/>`DoNotUseNativeZipLibraryForDecompression`|Определяет, используются ли собственные подпрограммы ОС для распаковки классом <xref:System.IO.Compression.DeflateStream>. `false` использовать собственные API; `true` использовать реализацию <xref:System.IO.Compression.DeflateStream>.|.NET Framework 4.7.2|
|`Switch.System.IO.Compression.ZipFile.`<br/>`UseBackslash`|Использует обратную косую черту ("\\"), а не косую черту ("/") в качестве разделителя пути в свойстве <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType>. Дополнительные сведения см. в разделе [Устранение рисков: разделитель пути ZipArchiveEntry. FullName](../../../migration-guide/mitigation-ziparchiveentry-fullname-path-separator.md).|.NET Framework 4.6.1|
|`Switch.System.IO.Ports.`<br/>`DoNotCatchSerialStreamThreadExceptions`|Определяет, прерываются ли исключения операционной системы, создаваемые в фоновых потоках, созданных с <xref:System.IO.Ports.SerialPort> потоками.|.NET Framework 4.7.1|
|`Switch.System.IO.`<br/>`UseLegacyPathHandling`|Определяет, используется ли нормализация устаревшего пути, а также использование путей URI в методах <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> и <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType>. Дополнительные сведения см. в разделе [Устранение рисков: нормализация пути](../../../migration-guide/mitigation-path-normalization.md) и [Устранение рисков: проверки двоеточия пути](../../../migration-guide/mitigation-path-colon-checks.md).|.NET Framework 4.6.2|
|`Switch.System.`<br/>`MemberDescriptorEqualsReturnsFalseIfEquivalent`|Определяет, сравнивает ли проверка на равенство свойство <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=nameWithType> одного объекта со свойством <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=nameWithType> второго объекта. Дополнительные сведения см. в разделе [неправильная реализация MemberDescriptor. Equals](../../../migration-guide/retargeting/4.6.1-4.6.2.md#incorrect-implementation-of-memberdescriptorequals).|.NET Framework 4.6.2|
 `Switch.System.Net.`<br/>`DontCheckCertificateEKUs`|Отключает проверку идентификатора объекта расширенного использования ключа (EKU) сертификата. Расширение расширенного использования ключа (EKU) — это коллекция идентификаторов объекта (OID), которые указывают приложения, использующие ключ.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchSendAuxRecord`|Отключает использование браузера TLS 1.0 для защиты SSL/TLS (МОНСТРУ) путем отключения использования SCH_SEND_AUX_RECORD.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchUseStrongCrypto`|Определяет, могут ли классы <xref:System.Net.ServicePointManager?displayProperty=nameWithType> и <xref:System.Net.Security.SslStream?displayProperty=nameWithType> использовать протокол SSL 3,0. Дополнительные сведения см. в разделе [Устранение рисков. Протоколы TLS](../../../migration-guide/mitigation-tls-protocols.md).|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSystemDefaultTlsVersions`|Отключает возврат версий Системдефаулт TLS по умолчанию для Tls12, Tls11, TLS.|.NET Framework 4.7|
|`Switch.System.Net.`<br/>`DontEnableTlsAlerts`|Отключает оповещения на стороне сервера SslStream TLS.|.NET Framework 4.7|
|`Switch.System.Runtime.InteropServices.`<br/>`DoNotMarshalOutByrefSafeArrayOnInvoke`|Определяет, отключен ли параметр ByRef параметров SafeArray для событий COM-взаимодействия с машинным кодом (`false`) или недоступен ли маршалинг обратно в машинный код (`true`).|.NET Framework 4.8|
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseECMAScriptV6EscapeControlCharacter` |Определяет, сериализует ли [DataContractJsonSerializer](xref:System.Runtime.Serialization.Json.DataContractJsonSerializer) некоторые управляющие символы на основе стандартов ECMAScript версии 6 и V8. Дополнительные сведения см. в статье [Устранение рисков. Сериализация управляющих символов с помощью DataContractJsonSerializer](../../../migration-guide/mitigation-serialization-control-characters.md)| .NET Framework 4.7 |
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseTimeZoneInfo`|Определяет, поддерживает ли <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> несколько корректировок или только одну корректировку для часового пояса. Если `true`, для сериализации и десериализации данных даты и времени используется тип <xref:System.TimeZoneInfo>. в противном случае используется тип <xref:System.TimeZone>, который не поддерживает несколько правил коррекции.|.NET Framework 4.6.2|
|`Switch.System.Runtime.Serialization.UseNewMaxArraySize`|Определяет, использует ли <xref:System.Runtime.Serialization.ObjectManager?displayProperty=nameWithType> больший размер массива при сериализации и десериализации объектов. Присвойте этому параметру значение `true`, чтобы повысить производительность сериализации и десериализации больших графов объектов по типам, например <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>. |.NET Framework 4.7.2|
|`Switch.System.Security.ClaimsIdentity.`<br/>`SetActorAsReferenceWhenCopyingClaimsIdentity`|Определяет, задает ли конструктор <xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=nameWithType> свойство <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=nameWithType> нового объекта с существующей ссылкой на объект. Дополнительные сведения см. в разделе [Устранение рисков. Конструктор ClaimsIdentity](../../../migration-guide/retargeting/4.6.1-4.6.2.md).|.NET Framework 4.6.2|
|`Switch.System.Security.Cryptography.`<br/>`AesCryptoServiceProvider.DontCorrectlyResetDecryptor`|Определяет, будет ли попытка повторного использования <xref:System.Security.Cryptography.AesCryptoServiceProvider> дешифратора выдать исключение <xref:System.Security.Cryptography.CryptographicException>. Дополнительные сведения см. [в разделе AesCryptoServiceProvider дешифратора — обеспечивает повторное использование преобразования](../../../migration-guide/retargeting/4.6.1-4.6.2.md#aescryptoserviceprovider-decryptor-provides-a-reusable-transform).|.NET Framework 4.6.2|
|`Switch.System.Security.Cryptography.`<br/>`DoNotAddrOfCspParentWindowHandle`|Определяет, является ли значение свойства [CspParameters. ParentWindowHandle](xref:System.Security.Cryptography.CspParameters.ParentWindowHandle) [IntPtr](xref:System.IntPtr) , представляющего место в памяти дескриптора окна, или является ли он дескриптором окна (HWND). Дополнительные сведения см. в статье [Mitigation: CspParameters.ParentWindowHandle Expects an HWND](../../../migration-guide/retargeting/4.6.2-4.7.md#cspparametersparentwindowhandle-now-expects-hwnd-value) (Устранение рисков. CspParameters.ParentWindowHandle ожидает HWND). |.NET Framework 4.7|
|`Switch.System.Security.Cryptography.`<br/>`UseLegacyFipsThrow`|Определяет, будет ли использование управляемых криптографических классов в режиме FIPS выдать исключение <xref:System.Security.Cryptography.CryptographicException> (`true`) или полагается на реализацию системных библиотек (`false`).|.NET Framework 4.8|
|`Switch.System.Security.Cryptography.Pkcs.`<br/>`UseInsecureHashAlgorithms`|Определяет, используется ли по умолчанию для некоторых операций SignedCMS алгоритм SHA1 или SHA256.<br>Из-за конфликта с SHA1 корпорация Майкрософт рекомендует использовать SHA256.|.NET Framework 4.7.1|
|`Switch.System.Security.Cryptography.X509Certificates.`<br/>`ECDsaCertificateExtensions.UseLegacyPublicKeyReader`|Управляет тем, правильно ли метод <xref:System.Security.Cryptography.X509Certificates.ECDsaCertificateExtensions.GetECDsaPublicKey%2A?displayProperty=nameWithType> обрабатывает все именованные кривые, поддерживаемые операционной системой (`false`), или возвращает к прежнему поведению.|.NET Framework 4.8|
|`Switch.System.Security.Cryptography.Xml.`<br/>`UseInsecureHashAlgorithms`|Определяет, используется ли по умолчанию для некоторых операций SignedXML алгоритм SHA1 или SHA256.<br>Из-за конфликта с SHA1 корпорация Майкрософт рекомендует использовать SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`AllowUnsignedToHeader`|Определяет, допускает ли режим безопасности `TransportWithMessageCredential` сообщения с неподписанным заголовком "to". Это параметр выбора. Дополнительные сведения см. [в разделе изменения среды выполнения в .NET Framework 4.6.1](../../../migration-guide/runtime/4.5.2-4.6.1.md#windows-communication-foundation-wcf).|.NET Framework 4.6.1|
|`Switch.System.ServiceModel.`<br/>`DisableAddressHeaderCollectionValidation`>|Определяет, создает ли конструктор <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> <xref:System.ArgumentException>, если один из элементов `null`.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br />`DisableCngCertificates`|Определяет, возникает ли исключение при попытке использовать сертификаты X509 с поставщиком хранилища ключей CSG ВЫЗЫВАЛА. Дополнительные сведения см. в разделе [Безопасность транспорта WCF поддерживает сертификаты, хранимые с помощью CNG](../../../migration-guide/retargeting/4.6.1-4.6.2.md#wcf-transport-security-supports-certificates-stored-using-cng).|.NET Framework 4.6.1|
|`Switch.System.ServiceModel.`<br/>`DisableExplicitConnectionCloseHeader`|При использовании транспорта HTTP с резидентной службой Установка этого значения в `true` приводит к тому, что WCF игнорирует приложение, добавляя заголовок `Connection: close` в заголовки ответа для запроса. Установка этого значения в `false` позволяет добавлять заголовок `Connection: close` к заголовкам ответа, что приводит к закрытию соединителя запросов после отправки ответа.|.NET Framework 4.6|
|`Switch.System.ServiceModel.`<br/>`DisableOperationContextAsyncFlow`|Обрабатывает взаимоблокировки, которые являются следствием ограниченного числа экземпляров повторного входа службы на один поток выполнения за раз.|.NET Framework 4.6.2|
|`Switch.System.ServiceModel.`<br/>`DisableUsingServicePointManagerSecurityProtocols`|Вместе с `Switch.System.Net.DontEnableSchUseStrongCrypto`определяет, использует ли безопасность сообщений WCF TLS 1,1 и TLS 1,2.|.NET Framework 4.7 |
|`Switch.System.ServiceModel.`<br/>`DontEnableSystemDefaultTlsVersions`|Значение `false` задает конфигурацию по умолчанию, разрешающую операционной системе выбирать протокол. Значение `true` задает по умолчанию самый высокий доступный протокол. (Также доступно в ветви обслуживания предыдущих версий платформы)|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InMsmqEncryptionAlgorithm`|Определяет, является ли алгоритмом подписи сообщений по умолчанию для сообщений MSMQ в WCF значение SHA1 или SHA256.<br>Из-за конфликта с SHA1 корпорация Майкрософт рекомендует использовать SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InPipeConnectionGetHashAlgorithm`|Определяет, использует ли WCF хэш SHA1 или SHA256 для создания случайных имен для именованных каналов.<br>Из-за конфликта с SHA1 корпорация Майкрософт рекомендует использовать SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.Internals`<br/>`IncludeNullExceptionMessageInETWTrace`|Определяет, следует ли создавать исключение [NullReferenceException](xref:System.NullReferenceException) , если сообщение об исключении имеет значение null.|.NET Framework 4.7|
|`Switch.System.ServiceProcess.`<br/>`DontThrowExceptionsOnStart`|Определяет, распространяются ли исключения, возникающие при запуске службы, в вызывающий метод <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType>.|.NET Framework 4.7.1|
|`Switch.System.Threading.UseNetCoreTimer`|Определяет, использует ли <xref:System.Threading.Timer> экземпляров преимущества повышения производительности в крупномасштабных средах. Если `true`, улучшение производительности включено; Если `false` (значение по умолчанию), они отключены.|.NET Framework 4.8|
|`Switch.System.Uri.`<br/>`DontEnableStrictRFC3986ReservedCharacterSets`|Определяет, будут ли закодированы определенные символы в кодировке процентов, которые иногда декодированы, в кодировке слева. Если `true`, они декодированы; в противном случае `false`.|.NET Framework 4.7.2|
|`Switch.System.Uri.`<br/>`DontKeepUnicodeBidiFormattingCharacters`|Определяет обработку двунаправленных символов Юникода в URI. `true`, чтобы удалить их из URI; `false` для сохранения и процента кодирования.|.NET Framework 4.7.2|
|`Switch.System.Windows.Controls.Grid.`<br/>`StarDefinitionsCanExceedAvailableSpace` |Определяет, применяет ли Windows Presentation Foundation старый алгоритм (`true`) или новый алгоритм (`false`) при выделении пространства для \*-столбцов. Дополнительные сведения см. в статье [Mitigation: Grid Control's Space Allocation to Star-columns](../../../migration-guide/retargeting/4.6.2-4.7.md#wpf-grid-allocation-of-space-to-star-columns) (Устранение рисков. Выделение пространства элемента управления "сетка" для столбцов со звездочкой). |.NET Framework 4.7 |
|`Switch.System.Windows.Controls.TabControl.`<br/>`SelectionPropertiesCanLagBehindSelectionChangedEvent`|Определяет, всегда ли обновляет значение выбранного свойства селектора или элемента управления "Вкладка" перед вызовом события изменения выбора.|.NET Framework 4.7.1|
|`Switch.System.Windows.Controls.Text.`<br/>`UseAdornerForTextboxSelectionRendering`|Определяет, доступна ли визуализация выбора на основе недекоративного элемента для элементов управления <xref:System.Windows.Controls.TextBox> и <xref:System.Windows.Controls.PasswordBox>, чтобы предотвратить перекрыто текст (`false`) или отображение текста только в слое декоративных элементов (`true`).|.NET Framework 4.7.2|
|`Switch.System.Windows.Data.Binding.`<br/>`IListIndexerHidesCustomIndexer`|Определяет, используются ли пользовательские индексаторы IList неправильно (`true`) или правильно (`false`) классом <xref:System.Windows.Data.Binding?displayProperty=nameWithType>.|.NET Framework 4.8|
|`Switch.System.Windows.DoNotScaleForDpiChanges`|Определяет, происходит ли изменение DPI на уровне системы (значение `false`) или на уровне каждого монитора (значение `true`).|.NET Framework 4.6.2|
|`Switch.System.Windows.`<br/>`DoNotUsePresentationDpiCapabilityTier2OrGreater`|Определяет, улучшается ли размер элементов управления в <xref:System.Windows.Interop.HwndHost?displayProperty=nameWithType> при запуске WPF в режиме, поддерживающем монитор, отключен (`true`) или включен (`false`).|.NET Framework 4.8|
|`Switch.System.Windows.Forms.`<br/>`DomainUpDown.UseLegacyScrolling`|Определяет, нужно ли разработчику специально управлять действием <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> при наличии текста элемента управления. `true`, обрабатывающее действие <xref:System.Windows.Forms.DomainUpDown.UpButton>; `false` для правильной синхронизации действий <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> и <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>.|.NET Framework 4.7.2|
|`Switch.System.Windows.Forms.`<br />`DontSupportReentrantFilterMessage`|Истекает из кода, который позволяет пользовательской реализации <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> безопасно фильтровать сообщения без возникновения исключения при вызове метода <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>. Дополнительные сведения см. в разделе [Устранение рисков: пользовательские реализации IMessageFilter.PreFilterMessage](../../../migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).|.NET Framework 4.6.1|
|`Switch.System.Windows.Forms.`<br/>`UseLegacyContextMenuStripSourceControlValue`|Определяет, возвращает ли свойство <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> систему управления версиями, когда пользователь открывает меню из вложенного элемента управления <xref:System.Windows.Forms.ToolStripMenuItem>. `true`, чтобы вернуть `null`, поведение прежних версий; `false`, чтобы вернуть систему управления версиями.|.NET Framework 4.7.2|
|`Switch.System.Windows.Forms.UseLegacyToolTipDisplay`|Определяет, отключена ли поддержка вызова подсказки (`true`) или включено (`false`). Включение поддержки вызова подсказки также требует использования устаревших функций специальных возможностей, определенных `Switch.UseLegacyAccessibilityFeatures`, `Switch.UseLegacyAccessibilityFeatures.2`, а `Switch.UseLegacyAccessibilityFeatures.3` все они будут отключены (значение `false`).|.NET Framework 4.8|
|`Switch.System.Windows.Input.Stylus.`<br/>`EnablePointerSupport`|Определяет, включен ли в приложениях WPF необязательный стек касаний или планшета на основе `WM_POINTER`. Дополнительные сведения см. в разделе [Устранение рисков. Поддержка сенсорного ввода и пера на основе указателя.](../../../migration-guide/mitigation-pointer-based-touch-and-stylus-support.md)|.NET Framework 4.7|
|`Switch.System.Windows.Markup.`<br/>`DoNotUseSha256ForMarkupCompilerChecksumAlgorithm`|Определяет, используется ли алгоритм хэширования по умолчанию для контрольных сумм: SHA256 (`false`) или SHA1 (`true`).<br>Из-за конфликта с SHA1 корпорация Майкрософт рекомендует использовать SHA256.|.NET Framework 4.7.2|
|`Switch.System.Windows.Media.ImageSourceConverter.`<br/>`OverrideExceptionWithNullReferenceException`|Определяет, создается ли устаревшая [NullReferenceException](xref:System.NullReferenceException) , а не исключение, которое точнее указывает на причину исключения (например, [DirectoryNotFoundException](xref:System.IO.DirectoryNotFoundException) или [FileNotFoundException](xref:System.IO.FileNotFoundException)). Он предназначен для использования в коде, который зависит от обработки [NullReferenceException](xref:System.NullReferenceException). | .NET Framework 4.7 |
|`Switch.System.Workflow.ComponentModel.`<br/>`UseLegacyHashForXomlFileChecksum`|Определяет, используется ли для хэширования контрольной суммы файлов XOML в сборках проекта рабочего процесса алгоритм MD5 (`true`) или используется ли алгоритм SHA256, представленный в качестве значения по умолчанию в .NET Framework 4,8.<br>Из-за конфликта с MD5 корпорация Майкрософт рекомендует использовать SHA256.|.NET Framework 4.8|
|`Switch.System.Workflow.Runtime.`<br/>`UseLegacyHashForSqlTrackingCacheKey`|Определяет, использует ли SqlTrackingService хэширование контрольных сумм (`true`) для кэшированных строк или используется ли алгоритм SHA256, представленный в качестве значения по умолчанию в .NET Framework 4,8.<br>Из-за конфликта с MD5 корпорация Майкрософт рекомендует использовать SHA256.|.NET Framework 4.8|
|`Switch.System.Workflow.Runtime.`<br/>`UseLegacyHashForWorkflowDefinitionDispenserCacheKey`|Определяет, использует ли хэширование контрольных сумм в среде выполнения рабочих процессов алгоритм MD5 (`true`) для кэшированных определений рабочих процессов или используется ли алгоритм SHA256, представленный в качестве значения по умолчанию в .NET Framework 4,8.<br>Из-за конфликта с MD5 корпорация Майкрософт рекомендует использовать SHA256.|.NET Framework 4.8|
|`Switch.UseLegacyAccessibilityFeatures`|Определяет, включены или отключены специальные возможности, доступные начиная с .NET Framework 4.7.1. | .NET Framework 4.7.1 |
|`Switch.UseLegacyAccessibilityFeatures.2`|Определяет, включены ли специальные возможности, доступные в .NET Framework 4.7.2 (`false`) или отключены (`true`). Если `true`, `Switch.UseLegacyAccessibilityFeatures` также необходимо `true` для включения специальных возможностей .NET Framework 4.7.1.|.NET Framework 4.7.2|
|`Switch.UseLegacyAccessibilityFeatures.3`|Определяет, включены ли специальные возможности, появившиеся в .NET Framework 4,8 (`false`) или отключены (`true`). Если `true`, `Switch.UseLegacyAccessibilityFeatures` и `Switch.UseLegacyAccessibilityFeatures.2` также должны быть `true`.|.NET Framework 4.8|
|`Switch.UseLegacyToolTipDisplay`|Определяет, отображаются ли подсказки, когда пользователь наводит указатель мыши на элемент управления WPF (`true`) или они отображаются как на клавиатурном фокусе, так и через сочетание клавиш (`false`, поведение по умолчанию). Для приложений, работающих на .NET Framework 4,8, но предназначенных для предыдущих версий .NET Framework, включение поддержки фокуса клавиатуры и клавиши быстрого вызова требует, чтобы `Switch.UseLegacyAccessibilityFeatures`, `Switch.UseLegacyAccessibilityFeatures.2`и `Switch.UseLegacyAccessibilityFeatures.3` были установлены в `false`.|.NET Framework 4.8|
|`Switch.System.Xml.`<br />`IgnoreEmptyKeySequences`|Определяет, пропускаются ли пустые последовательности ключей в составных ключах при проверке схемы XSD. Дополнительные сведения см. в разделе [Устранение рисков. Проверка схемы XML](../../../migration-guide/mitigation-xml-schema-validation.md).|.NET Framework 4.6|

> [!NOTE]
> Вместо добавления элемента `AppContextSwitchOverrides` в файл конфигурации приложения можно также задать параметры программным способом, вызвав метод `static` (in C#) или `Shared` (in Visual Basic) <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>.

 Разработчики библиотек также могут определять пользовательские параметры, позволяющие вызывающим объектам отказаться от измененных функциональных возможностей, появившихся в более поздних версиях их библиотек. Дополнительную информацию смотрите в классе <xref:System.AppContext>.

## <a name="switches-in-aspnet-applications"></a>Параметры в ASP.NET приложениях

Вы можете настроить приложение ASP.NET для использования параметров совместимости, добавив [\<добавить >](../appsettings/add-element-for-appsettings.md) элемент в раздел [\<appSettings >](../appsettings/index.md) файла Web. config.

В следующем примере элемент `<add>` используется для добавления двух параметров в раздел `<appSettings>` файла Web. config:

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="example"></a>Пример

 В следующем примере элемент `AppContextSwitchOverrides` используется для определения одного переключателя совместимости приложений, `Switch.System.Globalization.NoAsyncCurrentCulture`, который предотвращает перетекание культур между потоками в асинхронных вызовах метода.

```xml
<configuration>
   <runtime>
      <AppContextSwitchOverrides value="Switch.System.Globalization.NoAsyncCurrentCulture=true" />
   </runtime>
</configuration>
```

 В следующем примере элемент `AppContextSwitchOverrides` используется для определения двух переключателей совместимости приложений, `Switch.System.Globalization.NoAsyncCurrentCulture` и `Switch.System.IO.BlockLongPaths`. Две пары "имя-значение" разделяются точкой с запятой.

```xml
<configuration>
    <runtime>
       <AppContextSwitchOverrides
          value="Switch.System.Globalization.NoAsyncCurrentCulture=true;Switch.System.IO.BlockLongPaths=true" />
    </runtime>
</configuration>
```

## <a name="see-also"></a>См. также:

- <xref:System.AppContext?displayProperty=nameWithType>
- [Элемент > среды выполнения \<](runtime-element.md)
- [Элемент \<configuration>](../configuration-element.md)
