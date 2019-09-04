---
title: Элемент <AppContextSwitchOverrides>
ms.custom: updateeachrelease
ms.date: 04/18/2019
helpviewer_keywords:
- AppContextSwitchOverrides
- compatibility switches
- configuration switches
- configuration
ms.assetid: 4ce07f47-7ddb-4d91-b067-501bd8b88752
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7fe354a929aad93ba4d4a6ea3cb43b2607be1f05
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252875"
---
# <a name="appcontextswitchoverrides-element"></a>\<Элемент > AppContextSwitchOverrides
Определяет один или несколько коммутаторов, используемых классом <xref:System.AppContext> для предоставления механизма отказа от новых функциональных возможностей.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> среды выполнения**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<AppContextSwitchOverrides >**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<AppContextSwitchOverrides value="name1=value1[[;name2=value2];...]" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`value`|Обязательный атрибут.<br /><br /> Определяет одно или несколько имен переключателей и связанных с ними логических значений.|  
  
### <a name="value-attribute"></a>Атрибут value  
  
|Значение|Описание|  
|-----------|-----------------|  
|"имя = значение"|Предопределенное имя коммутатора вместе со значением`true` ( `false`или). Несколько пар "имя-значение" переключателей разделяются точкой с запятой (";"). Список стандартных имен коммутаторов, поддерживаемых .NET Framework, см. в разделе "Примечания".|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|  
  
## <a name="remarks"></a>Примечания  
 Начиная с .NET Framework 4,6, `<AppContextSwitchOverrides>` элемент в файле конфигурации позволяет вызывающим объектам API определить, может ли их приложение использовать преимущества новых функциональных возможностей или сохранить совместимость с предыдущими версиями библиотеки. Например, если поведение API изменилось между двумя версиями библиотеки, `<AppContextSwitchOverrides>` элемент позволяет вызывающим объектам этого API отказаться от нового поведения в версиях библиотеки, поддерживающих новые функциональные возможности. Для приложений, которые вызывают интерфейсы API в .NET Framework, `<AppContextSwitchOverrides>` элемент может также разрешить вызывающим объектам, приложения которых нацелены на более раннюю версию .NET Framework, использовать новые функции, если их приложение выполняется в версии .NET Framework, включающей в себя возможности.  
  
 `value` Атрибут`<AppContextSwitchOverrides>` элемента состоит из одной строки, состоящей из одной или нескольких пар "имя-значение", разделенных точкой с запятой.  Каждое имя определяет переключатель совместимости, и его соответствующее значение является логическим (`true` или `false`), указывающим, задан ли параметр. По умолчанию параметр имеет `false`значение, а библиотеки предоставляют новые функциональные возможности. Они предоставляют только предыдущие функции, если задан параметр (то есть его значение `true`). Это позволяет библиотекам предоставлять новое поведение для существующего API, одновременно позволяя вызывающим объектам, которые зависят от предыдущего поведения, отказаться от новых функциональных возможностей.  
  
 .NET Framework поддерживает следующие параметры:  
  
|Имя коммутатора|Описание|Обеспечен|  
|-----------------|-----------------|----------------|  
|`Switch.MS.Internal.`<br/>`DoNotApplyLayoutRoundingToMarginsAndBorderThickness`|Определяет, использует ли Windows Presentation Foundation устаревший алгоритм для макета элемента управления. Дополнительные сведения см. в разделе [Устранение рисков. Макет](../../../migration-guide/mitigation-wpf-layout.md)WPF.|.NET Framework 4.6|  
|`Switch.MS.Internal.`<br/>`UseSha1AsDefaultHashAlgorithmForDigitalSignatures`|Определяет, используется ли алгоритм по умолчанию для подписывания частей пакета с помощью PackageDigitalSignatureManager — SHA1 или SHA256.<br>Из-за конфликта с SHA1 корпорация Майкрософт рекомендует использовать SHA256.|.NET Framework 4.7.1|
|`Switch.System.Activities.`<br/>`UseMD5CryptoServiceProviderForWFDebugger`|Если задано `false`значение, позволяет выполнять отладку проектов рабочих процессов на основе XAML с помощью Visual Studio, когда включен FIPS. Без него <xref:System.NullReferenceException> вызывается в вызовах методов в сборке System. activitys.|.NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseMD5ForWFDebugger`|Определяет, использует ли контрольная сумма для экземпляра рабочего процесса в отладчике MD5 или SHA1. | .NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseSHA1HashForDebuggerSymbols`|Определяет, использует ли хэширование контрольных сумм рабочего процесса алгоритм SHA1, представленный в качестве`true`значения по умолчанию в .NET Framework 4,7 (), или используется ли алгоритм SHA256 по умолчанию`false`в .NET Framework 4,8 ().<br>Из-за конфликта с SHA1 корпорация Майкрософт рекомендует использовать SHA256.|.NET Framework 4.8|
|`Switch.System.Diagnostics.`<br/>`IgnorePortablePDBsInStackTraces`|Определяет, получают ли трассировкы стека при использовании переносимых PDB, могут включать исходные сведения о файлах и строках. `false`, чтобы включить исходные сведения о файлах и строках. в противном случае —. `true`|.NET Framework 4.7.2|
|`Switch.System.Drawing.`<br/>`DontSupportPngFramesInIcons`|Определяет, <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> вызывает ли метод исключение, <xref:System.Drawing.Icon> если объект содержит кадры PNG. Дополнительные сведения см. в разделе [Устранение рисков. Кадры PNG в объектах](../../../migration-guide/mitigation-png-frames-in-icon-objects.md)значков.|.NET Framework 4.6|
|`Switch.System.Drawing.Text.`<br/>`DoNotRemoveGdiFontsResourcesFromFontCollection`|Определяет, <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType> должны ли объекты правильно удаляться при добавлении в коллекцию <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)?displayProperty=nameWithType> методом. `true`для поддержки устаревшего поведения; `false` удаление всех объектов частных шрифтов. |.NET Framework 4.7.2|
|`Switch.System.Drawing.Printing.`<br>`OptimizePrintPreview`|Определяет, оптимизирована ли производительность <xref:System.Windows.Forms.PrintPreviewDialog> для сетевых принтеров. Дополнительные сведения см. в разделе [Общие сведения об элементе управления PrintPreviewDialog](../../../winforms/controls/printpreviewdialog-control-overview-windows-forms.md).|.NET Framework 4.6|
|`Switch.System.Globalization.EnforceJapaneseEraYearRanges`|Определяет, применяется ли проверка диапазона лет для Эр в японском календаре. `true`для принудительного применения проверок диапазона лет `false` и их отключения (поведение по умолчанию). Дополнительные сведения см. в разделе [Работа с календарями](../../../../standard/datetime/working-with-calendars.md).|.NET Framework 4.6|
|`Switch.System.Globalization.EnforceLegacyJapaneseDateParsing`|Определяет, распознается ли только "1" как первый год японской эры в японском календаре в операциях синтаксического анализа. `true`для распознавания только "1"; `false` чтобы распознать значение "1" или ганнен (поведение по умолчанию). Дополнительные сведения см. в разделе [Работа с календарями](../../../../standard/datetime/working-with-calendars.md).|.NET Framework 4.6| 
|`Switch.System.Globalization.FormatJapaneseFirstYearAsANumber`|Определяет, представляется ли первый год японской эры календаря как "1" или Ганнен в операциях форматирования. `true`Чтобы отформатировать первый год эры как "1"; `false` чтобы отформатировать его как ганнен (поведение по умолчанию). Дополнительные сведения см. в разделе [Работа с календарями](../../../../standard/datetime/working-with-calendars.md).|.NET Framework 4.6|
|`Switch.System.Globalization.NoAsyncCurrentCulture`|Определяет, не поступают ли асинхронные операции из контекста вызывающего потока. Дополнительные сведения см. в разделе [потоки CurrentCulture и CurrentUICulture между задачами](../../../migration-guide/retargeting/4.5.2-4.6.md#currentculture-and-currentuiculture-flow-across-tasks).|.NET Framework 4.6|  
|`Switch.System.IdentityModel.`<br/>`DisableMultipleDNSEntriesInSANCertificate`|Определяет, <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> пытается ли метод сопоставить тип утверждения только с последней записью DNS. Дополнительные сведения см. в разделе [Устранение рисков. X509CertificateClaimSet. FindClaims,](../../../migration-guide/mitigation-x509certificateclaimset-findclaims-method.md)метод.|.NET Framework 4.6.1|  
|`Switch.System.IdentityModel.`<br/>`EnableCachedEmptyDefaultAuthorizationContext`|Определяет, разрешено ли значение AuthorizationContext. Empty для возврата изменяемого объекта.|.NET Framework 4.6|  
|`Switch.System.IO.BlockLongPaths`|Определяет, `MAX_PATH` <xref:System.IO.PathTooLongException>следует ли создавать пути длиннее (260 символов). Дополнительные сведения см. в разделе [Поддержка длинных путей](../../../migration-guide/retargeting/4.6.1-4.6.2.md#long-path-support).|.NET Framework 4.6.2|  
|`Switch.System.IO.Compression.`<br/>`DoNotUseNativeZipLibraryForDecompression`|Определяет, используются ли собственные подпрограммы ОС для распаковки <xref:System.IO.Compression.DeflateStream> классом. `false`для использования собственных API; `true` для<xref:System.IO.Compression.DeflateStream> использования реализации.|.NET Framework 4.7.2|
|`Switch.System.IO.Compression.ZipFile.`<br/>`UseBackslash`|Использует обратную косую\\черту (""), а не косую черту ("/") <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType> в качестве разделителя пути в свойстве. Дополнительные сведения см. в [разделе Устранение рисков. Разделитель](../../../migration-guide/mitigation-ziparchiveentry-fullname-path-separator.md)пути ZipArchiveEntry. FullName.|.NET Framework 4.6.1|  
|`Switch.System.IO.Ports.`<br/>`DoNotCatchSerialStreamThreadExceptions`|Определяет, завершают ли процессы исключения операционной системы, создаваемые в <xref:System.IO.Ports.SerialPort> фоновых потоках, созданных с помощью потоков.|.NET Framework 4.7.1| 
|`Switch.System.IO.`<br/>`UseLegacyPathHandling`|Определяет, используется ли нормализация устаревшего пути, а также <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> пути URI, поддерживаемые методами и. <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> Дополнительные сведения см. в разделе [Устранение рисков. Нормализация](../../../migration-guide/mitigation-path-normalization.md) путей и [их устранение: Проверки](../../../migration-guide/mitigation-path-colon-checks.md)двоеточия пути.|.NET Framework 4.6.2|
|`Switch.System.`<br/>`MemberDescriptorEqualsReturnsFalseIfEquivalent`|Определяет, сравнивает <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=nameWithType> ли проверка на равенство свойство одного объекта <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=nameWithType> со свойством второго объекта. Дополнительные сведения см. в разделе [неправильная реализация MemberDescriptor. Equals](../../../migration-guide/retargeting/4.6.1-4.6.2.md#incorrect-implementation-of-memberdescriptorequals).|.NET Framework 4.6.2|  
 `Switch.System.Net.`<br/>`DontCheckCertificateEKUs`|Отключает проверку идентификатора объекта расширенного использования ключа (EKU) сертификата. Расширение расширенного использования ключа (EKU) — это коллекция идентификаторов объекта (OID), которые указывают приложения, использующие ключ.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchSendAuxRecord`|Отключает использование браузера TLS 1.0 для защиты SSL/TLS (МОНСТРУ) путем отключения использования SCH_SEND_AUX_RECORD.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchUseStrongCrypto`|Определяет, могут <xref:System.Net.ServicePointManager?displayProperty=nameWithType> ли <xref:System.Net.Security.SslStream?displayProperty=nameWithType> классы и использовать протокол SSL 3,0. Дополнительные сведения см. в разделе [Устранение рисков. протоколами TLS](../../../migration-guide/mitigation-tls-protocols.md).|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSystemDefaultTlsVersions`|Отключает возврат версий Системдефаулт TLS по умолчанию для Tls12, Tls11, TLS.|.NET Framework 4.7|
|`Switch.System.Net.`<br/>`DontEnableTlsAlerts`|Отключает оповещения на стороне сервера SslStream TLS.|.NET Framework 4.7|
|`Switch.System.Runtime.InteropServices.`<br/>`DoNotMarshalOutByrefSafeArrayOnInvoke`|Управляет возможностью выполнения маршалинга параметров ByRef для событий COM-взаимодействия в машинный`false`код () или при отключении обратной передачи в машинный код (`true`).|.NET Framework 4.8|
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseECMAScriptV6EscapeControlCharacter` |Определяет, сериализует ли [DataContractJsonSerializer](xref:System.Runtime.Serialization.Json.DataContractJsonSerializer) некоторые управляющие символы на основе стандартов ECMAScript версии 6 и V8. Дополнительные сведения см. в разделе [Устранение рисков. Сериализация управляющих символов с помощью DataContractJsonSerializer](../../../migration-guide/mitigation-serialization-control-characters.md)| .NET Framework 4.7 |
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseTimeZoneInfo`|Определяет, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> поддерживает ли компонент несколько корректировок или только одну корректировку для часового пояса. Если `true`он <xref:System.TimeZone> использует тип для сериализации и десериализации данных даты и времени; в противном случае используется тип, который не поддерживает несколько правил коррекции. <xref:System.TimeZoneInfo>|.NET Framework 4.6.2|
|`Switch.System.Runtime.Serialization.UseNewMaxArraySize`|Определяет, <xref:System.Runtime.Serialization.ObjectManager?displayProperty=nameWithType> использует ли больший размер массива при сериализации и десериализации объектов. Установите этот переключатель `true` , чтобы повысить производительность сериализации и десериализации больших графов объектов по типам, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>например. |.NET Framework 4.7.2|
|`Switch.System.Security.ClaimsIdentity.`<br/>`SetActorAsReferenceWhenCopyingClaimsIdentity`|Определяет, задает <xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=nameWithType> ли конструктор <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=nameWithType> свойство нового объекта с существующей ссылкой на объект. Дополнительные сведения см. в разделе [Устранение рисков. Конструктор](../../../migration-guide/mitigation-claimsidentity-constructor.md)ClaimsIdentity.|.NET Framework 4.6.2|  
|`Switch.System.Security.Cryptography.`<br/>`AesCryptoServiceProvider.DontCorrectlyResetDecryptor`|Определяет, <xref:System.Security.Cryptography.AesCryptoServiceProvider> <xref:System.Security.Cryptography.CryptographicException>создает ли попытка повторного использования дешифратора. Дополнительные сведения см. [в разделе AesCryptoServiceProvider дешифратора — обеспечивает повторное использование преобразования](../../../migration-guide/retargeting/4.6.1-4.6.2.md#aescryptoserviceprovider-decryptor-provides-a-reusable-transform).|.NET Framework 4.6.2|
|`Switch.System.Security.Cryptography.`<br/>`DoNotAddrOfCspParentWindowHandle`|Определяет, является ли значение свойства [CspParameters. ParentWindowHandle](xref:System.Security.Cryptography.CspParameters.ParentWindowHandle) [IntPtr](xref:System.IntPtr) , представляющего место в памяти дескриптора окна, или является ли он дескриптором окна (HWND). Дополнительные сведения см. в разделе [Устранение рисков. CspParameters. ParentWindowHandle ждет HWND](../../../migration-guide/retargeting/4.6.2-4.7.md#cspparametersparentwindowhandle-now-expects-hwnd-value). |.NET Framework 4.7|   
|`Switch.System.Security.Cryptography.`<br/>`UseLegacyFipsThrow`|Определяет, будет ли использование управляемых криптографических классов в режиме FIPS выдать`true`исключение <xref:System.Security.Cryptography.CryptographicException> () или полагается на реализацию системных библиотек`false`().|.NET Framework 4.8|
|`Switch.System.Security.Cryptography.Pkcs.`<br/>`UseInsecureHashAlgorithms`|Определяет, используется ли по умолчанию для некоторых операций SignedCMS алгоритм SHA1 или SHA256.<br>Из-за конфликта с SHA1 корпорация Майкрософт рекомендует использовать SHA256.|.NET Framework 4.7.1|
|`Switch.System.Security.Cryptography.X509Certificates.`<br/>`ECDsaCertificateExtensions.UseLegacyPublicKeyReader`|Определяет, <xref:System.Security.Cryptography.X509Certificates.ECDsaCertificateExtensions.GetECDsaPublicKey%2A?displayProperty=nameWithType> правильно ли метод обрабатывает все именованные кривые, поддерживаемые операционной системой`false`(), или возвращается к поведению прежних версий.|.NET Framework 4.8|
|`Switch.System.Security.Cryptography.Xml.`<br/>`UseInsecureHashAlgorithms`|Определяет, используется ли по умолчанию для некоторых операций SignedXML алгоритм SHA1 или SHA256.<br>Из-за конфликта с SHA1 корпорация Майкрософт рекомендует использовать SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`AllowUnsignedToHeader`|Определяет, `TransportWithMessageCredential` допускает ли режим безопасности сообщения с неподписанным заголовком "to". Это параметр выбора. Дополнительные сведения см. [в разделе изменения среды выполнения в .NET Framework 4.6.1](../../../migration-guide/runtime/4.5.2-4.6.1.md#windows-communication-foundation-wcf).|.NET Framework 4.6.1| 
|`Switch.System.ServiceModel.`<br/>`DisableAddressHeaderCollectionValidation`>|Определяет, создает <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> ли конструктор исключение <xref:System.ArgumentException> , если один из элементов имеет `null`значение.|.NET Framework 4.7.1| 
|`Switch.System.ServiceModel.`<br />`DisableCngCertificates`|Определяет, возникает ли исключение при попытке использовать сертификаты X509 с поставщиком хранилища ключей CSG ВЫЗЫВАЛА. Дополнительные сведения см. в разделе [Безопасность транспорта WCF поддерживает сертификаты, хранимые с помощью CNG](../../../migration-guide/retargeting/4.6.1-4.6.2.md#wcf-transport-security-supports-certificates-stored-using-cng).|.NET Framework 4.6.1|
|`Switch.System.ServiceModel.`<br/>`DisableExplicitConnectionCloseHeader`|При использовании транспорта HTTP с резидентной службой Установка этого значения приводит к `true` тому, что WCF игнорирует приложение, `Connection: close` добавляя заголовок в заголовки ответа для запроса. Установка этого значения `false` позволяет `Connection: close` добавить заголовок в заголовки ответа, что приведет к закрытию соединителя запросов после отправки ответа.|.NET Framework 4.6|
|`Switch.System.ServiceModel.`<br/>`DisableOperationContextAsyncFlow`|Обрабатывает взаимоблокировки, которые являются следствием ограниченного количества экземпляров перенаправленной службы на один поток выполнения за раз.|.NET Framework 4.6.2|
|`Switch.System.ServiceModel.`<br/>`DisableUsingServicePointManagerSecurityProtocols`|Вместе с `Switch.System.Net.DontEnableSchUseStrongCrypto`параметр определяет, использует ли безопасность сообщений WCF TLS 1,1 и TLS 1,2.|.NET Framework 4.7 |    
|`Switch.System.ServiceModel.`<br/>`DontEnableSystemDefaultTlsVersions`|Значение `false` задает конфигурацию по умолчанию, чтобы разрешить операционной системе выбирать протокол. Значение по умолчанию `true` задает самый высокий доступный протокол. (Также доступно в ветви обслуживания предыдущих версий платформы)|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InMsmqEncryptionAlgorithm`|Определяет, является ли алгоритмом подписи сообщений по умолчанию для сообщений MSMQ в WCF значение SHA1 или SHA256.<br>Из-за конфликта с SHA1 корпорация Майкрософт рекомендует использовать SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InPipeConnectionGetHashAlgorithm`|Определяет, использует ли WCF хэш SHA1 или SHA256 для создания случайных имен для именованных каналов.<br>Из-за конфликта с SHA1 корпорация Майкрософт рекомендует использовать SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.Internals`<br/>`IncludeNullExceptionMessageInETWTrace`|Определяет, следует ли создавать исключение [NullReferenceException](xref:System.NullReferenceException) , если сообщение об исключении имеет значение null.|.NET Framework 4.7|  
|`Switch.System.ServiceProcess.`<br/>`DontThrowExceptionsOnStart`|Определяет, распространяются ли исключения, возникающие при запуске службы, в вызывающий <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> метод.|.NET Framework 4.7.1|
|`Switch.System.Threading.UseNetCoreTimer`|Определяет, <xref:System.Threading.Timer> пользуются ли экземпляры преимуществами повышения производительности в крупномасштабных средах. Если `true`значение равно, то улучшение производительности включено; `false` в противном случае они будут отключены.|.NET Framework 4.8|
|`Switch.System.Uri.`<br/>`DontEnableStrictRFC3986ReservedCharacterSets`|Определяет, будут ли закодированы определенные символы в кодировке процентов, которые иногда декодированы, в кодировке слева. Значение, если `true`они декодированы; в противном случае —. `false`|.NET Framework 4.7.2|
|`Switch.System.Uri.`<br/>`DontKeepUnicodeBidiFormattingCharacters`|Определяет обработку двунаправленных символов Юникода в URI. `true`, чтобы удалить их из URI; `false` для сохранения и их кодирования в процентах.|.NET Framework 4.7.2|
|`Switch.System.Windows.Controls.Grid.`<br/>`StarDefinitionsCanExceedAvailableSpace` |Определяет, применяет ли Windows Presentation Foundation старый`true`алгоритм () или новый алгоритм`false`() при выделении \*пространства для столбцов. Дополнительные сведения см. в разделе [Устранение рисков. Выделение пространства элемента управления Grid для типа «звезда](../../../migration-guide/retargeting/4.6.2-4.7.md#wpf-grid-allocation-of-space-to-star-columns)-столбцы». |.NET Framework 4.7 |
|`Switch.System.Windows.Controls.TabControl.`<br/>`SelectionPropertiesCanLagBehindSelectionChangedEvent`|Определяет, всегда ли обновляет значение выбранного свойства селектора или элемента управления "Вкладка" перед вызовом события изменения выбора.|.NET Framework 4.7.1|
|`Switch.System.Windows.Controls.Text.`<br/>`UseAdornerForTextboxSelectionRendering`|Определяет, доступна ли визуализация выбора на основе недекоративного элемента <xref:System.Windows.Controls.TextBox> для <xref:System.Windows.Controls.PasswordBox> элементов управления и, чтобы предотвратить`false`перекрыто текст () или отображение текста только в слое декоративных элементов (`true`).|.NET Framework 4.7.2|
|`Switch.System.Windows.Data.Binding.`<br/>`IListIndexerHidesCustomIndexer`|Определяет, используются ли неправильные индексаторы IList (`false`) или должным`true`образом () <xref:System.Windows.Data.Binding?displayProperty=nameWithType> классом.|.NET Framework 4.8|
|`Switch.System.Windows.DoNotScaleForDpiChanges`|Определяет, происходит ли изменение dpi для каждой системы (значение `false`) или для каждого отдельного монитора ( `true`значение).|.NET Framework 4.6.2|
|`Switch.System.Windows.`<br/>`DoNotUsePresentationDpiCapabilityTier2OrGreater`|Определяет, будут ли улучшены размеры элементов управления <xref:System.Windows.Interop.HwndHost?displayProperty=nameWithType> в при запуске WPF в режиме, поддерживающем монитор, отключены`true`() или включены`false`().|.NET Framework 4.8|
|`Switch.System.Windows.Forms.`<br/>`DomainUpDown.UseLegacyScrolling`|Определяет, нужно ли разработчику специально выполнять <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> действия при наличии текста элемента управления. `true`для решения <xref:System.Windows.Forms.DomainUpDown.UpButton> действия; для правильной синхронизации <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> действий и. <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> `false`|.NET Framework 4.7.2|
|`Switch.System.Windows.Forms.`<br />`DontSupportReentrantFilterMessage`|Истекает из кода, который позволяет пользовательской <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> реализации безопасно фильтровать сообщения без возникновения исключения <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> при вызове метода. Дополнительные сведения см. в разделе [Устранение рисков. Пользовательские реализации](../../../migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md)IMessageFilter. PreFilterMessage.|.NET Framework 4.6.1|  
|`Switch.System.Windows.Forms.`<br/>`UseLegacyContextMenuStripSourceControlValue`|Определяет, <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> возвращает ли свойство систему управления версиями, когда пользователь открывает меню из вложенного <xref:System.Windows.Forms.ToolStripMenuItem> элемента управления. `true`для возврата `null`— устаревшее поведение; `false` для возврата системы управления версиями.|.NET Framework 4.7.2|
|`Switch.System.Windows.Forms.UseLegacyToolTipDisplay`|Определяет, отключена ли поддержка вызова подсказки (`true`) или включена (`false`). Включение поддержки вызова подсказки также требует использования `Switch.UseLegacyAccessibilityFeatures`устаревших специальных возможностей, определенных, `Switch.UseLegacyAccessibilityFeatures.2`, `Switch.UseLegacyAccessibilityFeatures.3` и все они будут отключены `false`(задайте значение).|.NET Framework 4.8|
|`Switch.System.Windows.Input.Stylus.`<br/>`EnablePointerSupport`|Определяет, включен ли `WM_POINTER`необязательный стек касаний или пера в приложениях WPF. Дополнительные сведения см. в разделе [Устранение рисков. Поддержка сенсорного ввода и пера на основе указателя](../../../migration-guide/mitigation-pointer-based-touch-and-stylus-support.md)|.NET Framework 4.7|
|`Switch.System.Windows.Markup.`<br/>`DoNotUseSha256ForMarkupCompilerChecksumAlgorithm`|Определяет, используется ли алгоритм хэширования по умолчанию для контрольных`false`сумм: SHA256 (`true`) или SHA1 ().<br>Из-за конфликта с SHA1 корпорация Майкрософт рекомендует использовать SHA256.|.NET Framework 4.7.2|
|`Switch.System.Windows.Media.ImageSourceConverter.`<br/>`OverrideExceptionWithNullReferenceException`|Определяет, создается ли устаревшая [NullReferenceException](xref:System.NullReferenceException) , а не исключение, которое точнее указывает на причину исключения (например, [DirectoryNotFoundException](xref:System.IO.DirectoryNotFoundException) или [FileNotFoundException](xref:System.IO.FileNotFoundException)). Он предназначен для использования в коде, который зависит от обработки [NullReferenceException](xref:System.NullReferenceException). | .NET Framework 4.7 |
|`Switch.System.Workflow.ComponentModel.`<br/>`UseLegacyHashForXomlFileChecksum`|Определяет, используется ли для хэширования контрольной суммы файлов XOML в сборках проекта рабочего`true`процесса алгоритм MD5 () или используется ли алгоритм SHA256, представленный в качестве значения по умолчанию в .NET Framework 4,8.<br>Из-за конфликта с MD5 корпорация Майкрософт рекомендует использовать SHA256.|.NET Framework 4.8|
|`Switch.System.Workflow.Runtime.`<br/>`UseLegacyHashForSqlTrackingCacheKey`|Определяет, использует ли SqlTrackingService хэширование контрольных сумм в качестве хэш`true`-алгоритма () для кэшированных строк или используется ли алгоритм SHA256, представленный в качестве значения по умолчанию в .NET Framework 4,8.<br>Из-за конфликта с MD5 корпорация Майкрософт рекомендует использовать SHA256.|.NET Framework 4.8|
|`Switch.System.Workflow.Runtime.`<br/>`UseLegacyHashForWorkflowDefinitionDispenserCacheKey`|Определяет, использует ли хэширование контрольных сумм в среде выполнения рабочих процессов`true`алгоритм MD5 () для кэшированных определений рабочих процессов или используется ли алгоритм SHA256, представленный в качестве значения по умолчанию в .NET Framework 4,8.<br>Из-за конфликта с MD5 корпорация Майкрософт рекомендует использовать SHA256.|.NET Framework 4.8|
|`Switch.UseLegacyAccessibilityFeatures`|Определяет, включены или отключены специальные возможности, доступные начиная с .NET Framework 4.7.1. | .NET Framework 4.7.1 |
|`Switch.UseLegacyAccessibilityFeatures.2`|Определяет, включены ли функции специальных возможностей в .NET Framework 4.7.2 (`false`) или отключены`true`(). Если `true` `true` значение `Switch.UseLegacyAccessibilityFeatures` равно, необходимо также включить .NET Framework специальных возможностей 4.7.1.|.NET Framework 4.7.2|
|`Switch.UseLegacyAccessibilityFeatures.3`|Определяет, включены ли специальные возможности, появившиеся в .NET Framework`false`4,8 () или`true`Disabled (). Если `true`значение `Switch.UseLegacyAccessibilityFeatures` равно `Switch.UseLegacyAccessibilityFeatures.2` , а также `true`должно иметь значение.|.NET Framework 4.8|
|`Switch.UseLegacyToolTipDisplay`|Определяет, отображаются ли подсказки, когда пользователь наводит указатель мыши на элемент управления WPF (`true`) или они отображаются как на клавиатурном фокусе, так и через сочетание клавиш (`false`, поведение по умолчанию). Для приложений, работающих на .NET Framework 4,8, но предназначенных для предыдущих версий .NET Framework, включение поддержки фокуса клавиатуры и сочетаний клавиш `Switch.UseLegacyAccessibilityFeatures`требует `Switch.UseLegacyAccessibilityFeatures.2`, чтобы `Switch.UseLegacyAccessibilityFeatures.3` для `false`параметра, и было задано значение.|.NET Framework 4.8|
|`System.Xml.`<br /><br /> `IgnoreEmptyKeySequences`|Определяет, пропускаются ли пустые последовательности ключей в составных ключах при проверке схемы XSD. Дополнительные сведения см. в разделе [Устранение рисков. Проверка](../../../migration-guide/mitigation-xml-schema-validation.md)XML-схемы.|.NET Framework 4.6|  
  
> [!NOTE]
> `AppContextSwitchOverrides` Вместо добавления элемента в файл конфигурации приложения можно также задать параметры программным способом, `static` вызвав метод (in C#) или `Shared` (в Visual Basic) <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> .  
  
 Разработчики библиотек также могут определять пользовательские параметры, позволяющие вызывающим объектам отказаться от измененных функциональных возможностей, появившихся в более поздних версиях их библиотек. Дополнительные сведения см. в описании класса <xref:System.AppContext>.  
  
## <a name="switches-in-aspnet-applications"></a>Параметры в ASP.NET приложениях

Вы можете настроить приложение ASP.NET для использования параметров совместимости, добавив [ \<элемент Add >](../appsettings/add-element-for-appsettings.md) в [ \<раздел appSettings >](../appsettings/index.md) файла Web. config. 

В следующем примере `<add>` элемент используется для добавления двух параметров `<appSettings>` в раздел файла Web. config:

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="example"></a>Пример

 В следующем примере `AppContextSwitchOverrides` элемент используется для определения одного `Switch.System.Globalization.NoAsyncCurrentCulture`переключателя совместимости приложений, который предотвращает перетекание культур между потоками в асинхронных вызовах метода.  
  
```xml  
<configuration>  
   <runtime>  
      <AppContextSwitchOverrides value="Switch.System.Globalization.NoAsyncCurrentCulture=true" />  
   </runtime>  
</configuration>  
```  
  
 В следующем примере `AppContextSwitchOverrides` элемент используется для определения двух `Switch.System.Globalization.NoAsyncCurrentCulture` переключателей совместимости приложений и `Switch.System.IO.BlockLongPaths`. Обратите внимание, что две пары "имя-значение" разделяются точкой с запятой.  
  
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
- [\<Элемент > среды выполнения](runtime-element.md)
- [Элемент \<configuration>](../configuration-element.md)
