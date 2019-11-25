---
title: Новые возможности .NET Framework
ms.custom: updateeachrelease
ms.date: 04/18/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- what's new [.NET Framework]
ms.assetid: 1d971dd7-10fc-4692-8dac-30ca308fc0fa
ms.openlocfilehash: ffcb288995975433bdd915362fccca03f345b5f5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74281651"
---
# <a name="whats-new-in-the-net-framework"></a>Новые возможности .NET Framework

В этой статье кратко рассматриваются основные новые возможности и усовершенствования в следующих версиях .NET Framework:

- [.NET Framework 4.8](#v48)
- [.NET Framework 4.7.2](#v472)
- [.NET Framework 4.7.1](#v471)
- [.NET Framework 4.7](#v47)
- [.NET Framework 4.6.2](#v462)
- [.NET Framework 4.6.1](#v461)
- [.NET 2015 и .NET Framework 4.6](#v46)
- [.NET Framework 4.5.2](#v452)
- [.NET Framework 4.5.1](#v451)
- [.NET Framework 4.5](#v45)

Данная статья не содержит исчерпывающей информации обо всех новых возможностях и может быть изменена. Общие сведения о .NET Framework см. в разделе [Начало работы с .NET Framework](../get-started/index.md). Поддерживаемые платформы см. в разделе [Требования к системе](../get-started/system-requirements.md). Ссылки для загрузки и инструкции по установке см. в разделе [Руководство по установке](../install/guide-for-developers.md).

> [!NOTE]
> Команда .NET Framework также выпускает компоненты в виде внештатных выпусков совместно с NuGet для расширения поддержки и введения новых возможностей (таких как неизменяемые коллекции и векторные типы с поддержкой SIMD). Дополнительные сведения см. в разделах [Дополнительные библиотеки классов и интерфейсы API](../additional-apis/index.md) и [.NET Framework и внештатные выпуски](../get-started/the-net-framework-and-out-of-band-releases.md).
> См. [полный список пакетов NuGet](https://www.nuget.org/profiles/dotnetframework) для .NET Framework.

<a name="v48" />

## <a name="introducing-net-framework-48"></a>Знакомство с платформой .NET Framework 4.8

Версия .NET Framework 4.8 основана на предыдущих выпусках .NET Framework 4.x. Она включает много исправлений и несколько новых функций, а также характеризуется очень стабильной работой.

### <a name="downloading-and-installing-net-framework-48"></a>Скачивание и установка .NET Framework 4.8

Ссылки для скачивания .NET Framework 4.8:

- [веб-установщик .NET Framework 4.8](https://go.microsoft.com/fwlink/?LinkId=2085155);

- [автономный установщик .NET Framework 4.8](https://go.microsoft.com/fwlink/?linkid=2088631).

.NET Framework 4.8 можно установить на платформах Windows 10, Windows 8.1 и Windows 7 с пакетом обновления 1 (SP1), а также на соответствующих серверных платформах, начиная с Windows Server 2008 R2 с пакетом обновления 1 (SP1). .NET Framework 4.8 можно установить с помощью веб-установщика или автономного установщика. Для большинства пользователей рекомендуется использовать веб-установщик.

Вы можете использовать .NET Framework 4.8 как целевую платформу в Visual Studio 2012 (или более поздних версиях), установив [.NET Framework 4.8 Developer Pack](https://go.microsoft.com/fwlink/?LinkId=2085167).

### <a name="whats-new-in-net-framework-48"></a>Новые возможности .NET Framework 4.8

.NET Framework 4.8 включает новые функции в следующих областях:

- [Базовые классы](#core48)
- [Windows Communication Foundation (WCF)](#wcf48)
- [Windows Presentation Foundation (WPF)](#wpf48)
- [Среда CLR](#clr48)

Основной акцент в .NET Framework 4.8, как и прежде, сделан на улучшении специальных возможностей, что позволяет приложению предоставлять соответствующие функции целевой аудитории. См. подробнее об [улучшениях специальных возможностей в .NET Framework 4.8](whats-new-in-accessibility.md).

<a name="core48" />

#### <a name="base-classes"></a>базовых классов;

**Ослабление влияния FIPS на шифрование**. В предыдущих версиях .NET Framework управляемые классы поставщиков служб шифрования, такие как <xref:System.Security.Cryptography.SHA256Managed>, выдавали исключение <xref:System.Security.Cryptography.CryptographicException> во время настройки системных библиотек шифрования в режиме FIPS. Это происходит из-за того, что, в отличие от системных библиотек шифрования, сертификация FIPS 140-2 не выполнялась для управляемых версий классов поставщиков служб шифрования. Некоторые разработчики используют виртуальные машины разработки в режиме FIPS, поэтому такие исключения обычно выдаются в рабочих системах.

По умолчанию в приложениях, работающих с .NET Framework 4.8, следующие управляемые криптографические классы больше не вызывают исключение <xref:System.Security.Cryptography.CryptographicException> в этом случае:

- <xref:System.Security.Cryptography.MD5Cng>
- <xref:System.Security.Cryptography.MD5CryptoServiceProvider>
- <xref:System.Security.Cryptography.RC2CryptoServiceProvider>
- <xref:System.Security.Cryptography.RijndaelManaged>
- <xref:System.Security.Cryptography.RIPEMD160Managed>
- <xref:System.Security.Cryptography.SHA256Managed>

Вместо этого такие классы перенацеливают криптографические операции на системную библиотеку шифрования. Это изменение эффективно устраняет возможное заблуждение относительно различий между средами разработки и рабочими средами, применяя к собственным и управляемым компонентам одну и ту же политику шифрования. Прежнее поведение приложений, работа которых зависит от этих исключений, можно восстановить, установив для параметра AppContext `Switch.System.Security.Cryptography.UseLegacyFipsThrow` значение `true`. См. подробнее об [управляемых криптографических классах, которые не вызывают исключение CryptographyException в режиме FIPS](../migration-guide/retargeting/4.7.2-4.8.md#managed-cryptography-classes-do-not-throw-a-cryptographyexception-in-fips-mode).

**Использование обновленной версии ZLib**

Начиная с .NET Framework 4.5, сборка clrcompression.dll использует [ZLib](https://www.zlib.net) — собственную внешнюю библиотеку для сжатия данных, предоставляя реализацию для алгоритма deflate. В .NET Framework 4.8 сборка clrcompression.dll обновлена для поддержки ZLib версии 1.2.11 c несколькими ключевыми улучшениями и исправлениями.

<a name="wcf48" />

#### <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)

**Знакомство с ServiceHealthBehavior**

Конечные точки работоспособности широко используются средствами оркестрации для управления службами на основе состояния их работоспособности. Проверки работоспособности также могут использоваться средствами мониторинга для отслеживания и создания уведомлений о доступности и производительности службы.

**ServiceHealthBehavior** — это поведение службы WCF, которое расширяет <xref:System.ServiceModel.Description.IServiceBehavior>.  При добавлении в коллекцию <xref:System.ServiceModel.Description.ServiceDescription.Behaviors?displayProperty=nameWithType> поведение службы отвечает за следующие действия:

- Возвращает состояние работоспособности службы с кодами откликов HTTP. Эти коды можно указать в строке запроса для проверки работоспособности HTTP/GET.

- Публикует сведения о работоспособности службы. Это сведения о службе, включая данные о состоянии службы и емкости, а также счетчики регулирования, можно отобразить с помощью запроса HTTP/GET в строке запроса `?health`. Простота доступа к такой информации необходима при устранении неполадок с неправильным поведением службы WCF.

Есть два способа, чтобы предоставить конечную точку работоспособности и опубликовать сведения о работоспособности службы WCF:

- С помощью кода. Например:

  ```csharp
  ServiceHost host = new ServiceHost(typeof(Service1),
                     new Uri("http://contoso:81/Service1"));
  ServiceHealthBehavior healthBehavior =
      host.Description.Behaviors.Find<ServiceHealthBehavior>();
  healthBehavior ??= new ServiceHealthBehavior();
  host.Description.Behaviors.Add(healthBehavior);
  ```

  ```vb
  Dim host As New ServiceHost(GetType(Service1),
              New Uri("http://contoso:81/Service1"))
  Dim healthBehavior As ServiceHealthBehavior =
     host.Description.Behaviors.Find(Of ServiceHealthBehavior)()
  If healthBehavior Is Nothing Then
     healthBehavior = New ServiceHealthBehavior()
  End If
  host.Description.Behaviors.Add(healthBehavior)
  ```

- С помощью файла конфигурации. Например:

  ```xml
  <behaviors>
    <serviceBehaviors>
      <behavior name="DefaultBehavior">
        <serviceHealth httpsGetEnabled="true"/>
      </behavior>
    </serviceBehaviors>
  </behaviors>
  ```

Состояние работоспособности службы можно запросить, используя такие параметры запроса, как `OnServiceFailure`, `OnDispatcherFailure`, `OnListenerFailure`, `OnThrottlePercentExceeded`. При этом код отклика HTTP можно указать для каждого параметра запроса. Если для параметра запроса не указан код отклика HTTP, по умолчанию используется код HTTP 503. Например:

- OnServiceFailure: `https://contoso:81/Service1?health&OnServiceFailure=450`

  Код состояния отклика HTTP 450 возвращается, если значение [ServiceHost.State](xref:System.ServiceModel.Channels.CommunicationObject.State) больше чем <xref:System.ServiceModel.CommunicationState.Opened?displayProperty=nameWithType>.
Параметры запроса и примеры:

- OnDispatcherFailure: `https://contoso:81/Service1?health&OnDispatcherFailure=455`

  Код состояния отклика HTTP 455 возвращается, если состояние любого из диспетчеров каналов больше чем <xref:System.ServiceModel.CommunicationState.Opened?displayProperty=nameWithType>.

- OnListenerFailure: `https://contoso:81/Service1?health&OnListenerFailure=465`

  Код состояния отклика HTTP 465 возвращается, если состояние любого из прослушивателей каналов больше чем <xref:System.ServiceModel.CommunicationState.Opened?displayProperty=nameWithType>.

- OnThrottlePercentExceeded: `https://contoso:81/Service1?health&OnThrottlePercentExceeded= 70:350,95:500`

  Указывает процент (1–100), который активирует отклик и соответствующий код отклика HTTP (200–599). В этом примере:

  - Если процент больше чем 95, возвращается код отклика HTTP 500.

  - Если это значение находится в диапазоне между 70 и 95, возвращается код отклика 350.

  - В противном случае возвращается код отклика 200.

Состояние работоспособности службы может отображаться в формате HTML (если указана такая строка запроса, как `https://contoso:81/Service1?health`) или в формате XML (если указана такая строка запроса, как `https://contoso:81/Service1?health&Xml`). Такая строка запроса, как `https://contoso:81/Service1?health&NoContent`, возвращает пустую HTML-страницу.

<a name="wpf48" />

#### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

**Улучшения высокого разрешения**

В .NET Framework 4.8 WPF добавлена поддержка DPI для каждого монитора версии 2 и масштабирование DPI в смешанном режиме. См. подробнее о [разработке классических приложений с поддержкой высокого разрешения в Windows](/windows/win32/hidpi/high-dpi-desktop-application-development-on-windows).

В .NET Framework 4.8 улучшена поддержка взаимодействия между размещенными HWND и Windows Forms в приложениях WPF с поддержкой высокого разрешения на платформах, которые поддерживают масштабирование DPI в смешанном режиме (начиная с обновления Windows 10 за апрель 2018 г.). Элементы управления размещенных HWND или Windows Forms, создаваемые в качестве окон с масштабированием DPI в смешанном режиме путем вызова [SetThreadDpiHostingBehavior](/windows/desktop/api/winuser/nf-winuser-setthreaddpihostingbehavior) и [SetThreadDpiAwarenessContext](/windows/desktop/api/winuser/nf-winuser-setthreaddpiawarenesscontext), могут размещаться в приложении WPF с поддержкой DPI для каждого монитора версии 2 с правильными размером и масштабом. Такое размещенное содержимое не отображается в собственном высоком разрешении. Вместо этого операционная система масштабирует размещенное содержимое до соответствующего размера. Включение режима поддержки DPI для каждого монитора версии 2 также позволяет размещать элементы управления WPF (родительские) в собственном окне в приложении с поддержкой высокого разрешения.

Чтобы включить поддержку масштабирования высокого разрешения в смешанном режиме, можно настроить следующие параметры [AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в файле конфигурации приложения:

```xml
<runtime>
   <AppContextSwitchOverrides value = "Switch.System.Windows.DoNotScaleForDpiChanges=false; Switch.System.Windows.DoNotUsePresentationDpiCapabilityTier2OrGreater=false"/>
</runtime>
```

<a name="clr48" />

#### <a name="common-language-runtime"></a>Среда CLR

Среда выполнения в .NET Framework 4.8 включает следующие новые функции и улучшения:

**Улучшения JIT-компилятора**. Компилятор Just-in-time (JIT) в .NET Framework 4.8 основан на JIT-компиляторе .NET Core 2.1. Многие оптимизации и все исправления, внесенные в JIT-компилятор .NET Core 2.1, включены в JIT-компилятор .NET Framework 4.8.

**Улучшения NGEN**. В среде выполнения улучшено управление памятью для образов [генератора образов в машинном коде](../tools/ngen-exe-native-image-generator.md), чтобы данные, полученные из таких образов, не были резидентными. Это сокращает контактную зону для атак с попытками выполнить произвольный код путем изменения соответствующей памяти.

**Сканирование на наличие вредоносных программ для всех сборок**. В предыдущих версиях .NET Framework среда выполнения просматривает все сборки, загруженные с диска, с помощью Защитника Windows или стороннего антивредоносного ПО. При этом сборки, загруженные из других источников, например с помощью метода <xref:System.Reflection.Assembly.Load(System.Byte[])?displayProperty=nameWithType>, не просматриваются, следовательно, они могут содержать не обнаруженное вредоносное ПО. Начиная с .NET Framework 4.8, при выполнении в Windows 10 среда выполнения запускает сканирование с помощью решений для защиты от вредоносных программ, которые реализуют [интерфейс сканирования антивредоносного ПО (AMSI)](/windows/desktop/AMSI/antimalware-scan-interface-portal).

<a name="v472" />

## <a name="whats-new-in-net-framework-472"></a>Новые возможности .NET Framework 4.7.2

.NET Framework 4.7.2 включает новые функции в следующих областях:

- [Базовые классы](#core-472)
- [ASP.NET](#asp-net472)
- [Сеть](#net472)
- [SQL](#sql472)
- [WPF](#wpf472)
- [ClickOnce](#clickonce)

Основной акцент в .NET Framework 4.7.2, как и прежде, сделан на улучшении специальных возможностей, что позволяет приложению предоставлять соответствующие функции целевой аудитории. См. подробнее об [улучшениях специальных возможностей в .NET Framework 4.7.2](whats-new-in-accessibility.md).

<a name="core-472" />

#### <a name="base-classes"></a>базовых классов;

В .NET Framework 4.7.2 значительно усовершенствовано шифрование, улучшена поддержка распаковки ZIP-архивов и включена дополнительная коллекция API.

**Новые перегрузки RSA.Create и DSA.Create**

С помощью методов <xref:System.Security.Cryptography.DSA.Create(System.Security.Cryptography.DSAParameters)?displayProperty=nameWithType> и <xref:System.Security.Cryptography.RSA.Create(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType> вы можете указывать параметры ключа при создании экземпляра ключа <xref:System.Security.Cryptography.DSA> или <xref:System.Security.Cryptography.RSA>. Они позволяют заменить код, подобный этому:

```csharp
// Before .NET Framework 4.7.2
using (RSA rsa = RSA.Create())
{
   rsa.ImportParameters(rsaParameters);
   // Other code to execute using the RSA instance.
}
```

```vb
' Before .NET Framework 4.7.2
Using rsa = RSA.Create()
   rsa.ImportParameters(rsaParameters)
   ' Other code to execute using the rsa instance.
End Using
```

на код, подобный этому:

```csharp
// Starting with .NET Framework 4.7.2
using (RSA rsa = RSA.Create(rsaParameters))
{
   // Other code to execute using the rsa instance.
}
```

```vb
' Starting with .NET Framework 4.7.2
Using rsa = RSA.Create(rsaParameters)
   ' Other code to execute using the rsa instance.
End Using
```

Методы <xref:System.Security.Cryptography.DSA.Create(System.Int32)?displayProperty=nameWithType> и <xref:System.Security.Cryptography.RSA.Create(System.Int32)?displayProperty=nameWithType> позволяют создавать новые ключи <xref:System.Security.Cryptography.DSA> или <xref:System.Security.Cryptography.RSA> с указанным размером. Например:

```csharp
using (DSA dsa = DSA.Create(2048))
{
   // Other code to execute using the dsa instance.
}
```

```vb
Using dsa = DSA.Create(2048)
   ' Other code to execute using the dsa instance.
End Using
```

**Конструкторы Rfc2898DeriveBytes принимают имя хэш-алгоритма**

Класс <xref:System.Security.Cryptography.Rfc2898DeriveBytes> содержит три новых конструктора с параметром <xref:System.Security.Cryptography.HashAlgorithmName>, который определяет алгоритм HMAC для использования при создании производных ключей. Вместо SHA-1 разработчикам следует использовать HMAC на основе SHA-2, например SHA-256, как показано в следующем примере:

```csharp
private static byte[] DeriveKey(string password, out int iterations, out byte[] salt,
                                out HashAlgorithmName algorithm)
{
   iterations = 100000;
   algorithm = HashAlgorithmName.SHA256;

   const int SaltSize = 32;
   const int DerivedValueSize = 32;

   using (Rfc2898DeriveBytes pbkdf2 = new Rfc2898DeriveBytes(password, SaltSize,
                                                             iterations, algorithm))
   {
      salt = pbkdf2.Salt;
      return pbkdf2.GetBytes(DerivedValueSize);
   }
}
```

```vb
Private Shared Function DeriveKey(password As String, ByRef iterations As Integer,
                                  ByRef salt AS Byte(), ByRef algorithm As HashAlgorithmName) As Byte()
   iterations = 100000
   algorithm = HashAlgorithmName.SHA256

   Const SaltSize As Integer = 32
   Const  DerivedValueSize As Integer = 32

   Using pbkdf2 = New Rfc2898DeriveBytes(password, SaltSize, iterations, algorithm)
      salt = pbkdf2.Salt
      Return pbkdf2.GetBytes(DerivedValueSize)
   End Using
End Function
```

**Поддержка временных ключей**

При импорте PFX-файла можно загрузить закрытые ключи непосредственно из памяти, минуя жесткий диск. Если в конструкторе <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> или в одной из перегрузок метода <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.Import%2A?displayProperty=nameWithType> указан новый флаг <xref:System.Security.Cryptography.X509Certificates.X509KeyStorageFlags.EphemeralKeySet?displayProperty=nameWithType>, закрытые ключи будут загружены в качестве временных ключей. Благодаря этому ключи невидимы на диске. Но:

- поскольку ключи не сохраняются на диске, сертификаты, загруженные с этим флагом, не являются подходящими кандидатами для добавления в X509Store.

- Ключи, загруженные таким образом, почти всегда загружаются через Windows CNG. Поэтому вызывающие объекты должны получить закрытый ключ путем вызова методов расширения, таких как [cert.GetRSAPrivateKey()](xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey%2A). Свойство <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> не работает.

- Поскольку свойство <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> из прежних версий не работает с сертификатами, разработчики должны выполнить тщательное тестирование перед переключением на временные ключи.

**Программное создание запросов подписи сертификата PKCS#10 и сертификатов открытого ключа X.509**

Начиная с версии .NET Framework 4.7.2, рабочие нагрузки могут создавать запросы подписи сертификата (CSR), чтобы запросы на сертификат можно было создавать в существующих средствах. Это бывает удобно при тестировании.

Дополнительные сведения и примеры кода см. в разделе "Программное создание запросов подписи сертификата PKCS#10 и сертификатов открытого ключа X.509" в [блоге .NET](https://devblogs.microsoft.com/dotnet/net-framework-4-7-2-developer-pack-early-access-build-3056-is-available/).

**Новые элементы SignerInfo**

Начиная с .NET Framework 4.7.2, класс <xref:System.Security.Cryptography.Pkcs.SignerInfo> предоставляет дополнительные сведения о подписи. Вы можете извлечь значение свойства <xref:System.Security.Cryptography.Pkcs.SignerInfo.SignatureAlgorithm?displayProperty=fullName>, чтобы определить алгоритм подписи, который использовался подписывающим объектом. Вы можете вызвать <xref:System.Security.Cryptography.Pkcs.SignerInfo.GetSignature%2A?displayProperty=nameWithType>, чтобы получить копию криптографической подписи для этого подписывающего объекта.

**Упакованный поток остается открытым после удаления CryptoStream**

Начиная с .NET Framework 4.7.2, класс <xref:System.Security.Cryptography.CryptoStream> имеет дополнительный конструктор, благодаря которому <xref:System.Security.Cryptography.CryptoStream.Dispose%2A> не закрывает упакованный поток. Чтобы оставить упакованный поток открытым после удаления экземпляра <xref:System.Security.Cryptography.CryptoStream>, вызовите новый конструктор <xref:System.Security.Cryptography.CryptoStream> следующим образом:

```csharp
var cStream = new CryptoStream(stream, transform, mode, leaveOpen: true);
```

```vb
Dim cStream = New CryptoStream(stream, transform, mode, leaveOpen:=true)
```

**Изменения распаковки в DeflateStream**

Начиная с .NET Framework 4.7.2, реализация операций распаковки в классе <xref:System.IO.Compression.DeflateStream> была изменена и теперь использует собственные API Windows по умолчанию. Как правило, это приводит к значительному повышению производительности.

Поддержка распаковки с помощью API Windows включена по умолчанию для приложений, нацеленных на .NET Framework 4.7.2. Для приложений, которые предназначены для более ранних версий .NET Framework, но выполняются в .NET Framework 4.7.2, новое поведение можно активировать отдельно, добавив следующий [переключатель AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в файл конфигурации приложений:

```xml
<AppContextSwitchOverrides value="Switch.System.IO.Compression.DoNotUseNativeZipLibraryForDecompression=false" />
```

**Дополнительные коллекции API**

В .NET Framework 4.7.2 добавлено несколько новых API для типов <xref:System.Collections.Generic.SortedSet%601> и <xref:System.Collections.Generic.HashSet%601>. Сюда входит следующее.

- Методы `TryGetValue`, которые делают шаблон try, используемый в других типах коллекций, доступным для этих двух типов. Вот эти методы:

  - [public bool HashSet\<T>.TryGetValue(T equalValue, out T actualValue)](xref:System.Collections.Generic.SortedSet%601.TryGetValue%2A)
  - [public bool SortedSet\<T>.TryGetValue(T equalValue, out T actualValue)](xref:System.Collections.Generic.SortedSet%601.TryGetValue%2A)

- Методы расширения `Enumerable.To*`, которые преобразуют коллекцию в <xref:System.Collections.Generic.HashSet%601>:

  - [public static HashSet\<TSource> ToHashSet\<TSource>(this IEnumerable\<TSource> source)](xref:System.Linq.Enumerable.ToHashSet%2A)
  - [public static HashSet\<TSource> ToHashSet\<TSource>(this IEnumerable\<TSource> source, IEqualityComparer\<TSource> comparer)](xref:System.Linq.Enumerable.ToHashSet%2A)

- Новые конструкторы <xref:System.Collections.Generic.HashSet%601>, которые позволяют задать емкость коллекции и повысить производительность, если размер <xref:System.Collections.Generic.HashSet%601> известен заранее:

  - [public HashSet(int capacity)](xref:System.Collections.Generic.HashSet%601.%23ctor(System.Int32))
  - [public HashSet(int capacity, IEqualityComparer\<T> comparer)](xref:System.Collections.Generic.HashSet%601.%23ctor(System.Int32,System.Collections.Generic.IEqualityComparer%7B%600%7D))

Класс <xref:System.Collections.Concurrent.ConcurrentDictionary%602> включает новые перегрузки методов <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A> и <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A>, чтобы извлечь значение из словаря или добавить его, если оно не найдено, а также добавить значение в словарь или обновить его, если оно уже существует.

```csharp
public TValue AddOrUpdate<TArg>(TKey key, Func<TKey, TArg, TValue> addValueFactory, Func<TKey, TValue, TArg, TValue> updateValueFactory, TArg factoryArgument)

public TValue GetOrAdd<TArg>(TKey key, Func<TKey, TArg, TValue> valueFactory, TArg factoryArgument)
```

```vb
Public AddOrUpdate(Of TArg)(key As TKey, addValueFactory As Func(Of TKey, TArg, TValue), updateValueFactory As Func(Of TKey, TValue, TArg, TValue), factoryArgument As TArg) As TValue

Public GetOrAdd(Of TArg)(key As TKey, valueFactory As Func(Of TKey, TArg, TValue), factoryArgument As TArg) As TValue
```

<a name="asp-net472" />

#### <a name="aspnet"></a>ASP.NET

**Поддержка внедрения зависимостей в веб-формах**

[Внедрение зависимостей (DI)](/aspnet/core/fundamentals/dependency-injection#overview-of-dependency-injection) разрывает связь объектов и их зависимостей, чтобы код объекта не пришлось менять только потому, что изменилась зависимость. При разработке приложений ASP.NET, предназначенных для использования с .NET Framework 4.7.2, вы можете:

- Использовать внедрение на базе метода задания, интерфейса или конструктора в [обработчиках и модулях](https://docs.microsoft.com/previous-versions/aspnet/bb398986(v=vs.100)), [экземплярах страницы](xref:System.Web.UI.Page) и [пользовательских элементах управления](https://docs.microsoft.com/previous-versions/aspnet/y6wb1a0e(v=vs.100)) из проектов веб-приложений ASP.NET.

- Использовать внедрение на базе метода задания и интерфейса в [обработчиках и модулях](https://docs.microsoft.com/previous-versions/aspnet/bb398986(v=vs.100)), [экземплярах страницы](xref:System.Web.UI.Page) и [пользовательских элементах управления](https://docs.microsoft.com/previous-versions/aspnet/y6wb1a0e(v=vs.100)) из проектов веб-сайтов ASP.NET.

- Подключать другие платформы внедрения зависимостей.

**Поддержка файлов cookie SameSite**

[SameSite](https://tools.ietf.org/html/draft-west-first-party-cookies-07) запрещает браузеру отправлять файл cookie вместе с межсайтовым запросом. В .NET Framework 4.7.2 добавлено свойство <xref:System.Web.HttpCookie.SameSite?displayProperty=nameWithType>, значение которого является членом перечисления <xref:System.Web.SameSiteMode?displayProperty=nameWithType>. Если его значение равно <xref:System.Web.SameSiteMode.Strict?displayProperty=nameWithType> или <xref:System.Web.SameSiteMode.Lax?displayProperty=nameWithType>, ASP.NET добавляет атрибут `SameSite` в заголовок set-cookie. Поддержка SameSite действует для объектов <xref:System.Web.HttpCookie>, а также для файлов cookie <xref:System.Web.Security.FormsAuthentication> и <xref:System.Web.SessionState>.

Вы можете задать SameSite для объекта <xref:System.Web.HttpCookie> следующим образом:

```csharp
var c = new HttpCookie("secureCookie", "same origin");
c.SameSite = SameSiteMode.Lax;
```

```vb
Dim c As New HttpCookie("secureCookie", "same origin")
c.SameSite = SameSiteMode.Lax
```

Файлы cookie SameSite также можно настроить на уровне приложения, изменив файл web.config:

```xml
<system.web>
   <httpCookies sameSite="Strict" />
</system.web>
```

Вы можете добавить SameSite для файлов cookie <xref:System.Web.Security.FormsAuthentication> и <xref:System.Web.SessionState>, изменив файл веб-конфигурации:

```xml
<system.web>
   <authentication mode="Forms">
      <forms cookieSameSite="Lax">
         <!-- ...   -->
      </forms>
   <authentication />
   <sessionState cookieSameSite="Lax"></sessionState>
</system.web>
```

<a name="net472" />

#### <a name="networking"></a>Сети

**Реализация свойств HttpClientHandler**

В .NET Framework 4.7.1 добавлены восемь свойств класса <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType>. Но два из них вызывали исключение <xref:System.PlatformNotSupportedException>. Платформа .NET Framework 4.7.2 теперь предоставляет реализацию этих свойств. Это следующие свойства:

- <xref:System.Net.Http.HttpClientHandler.CheckCertificateRevocationList>
- <xref:System.Net.Http.HttpClientHandler.SslProtocols>

<a name="sql472" />

#### <a name="sqlclient"></a>SQLClient

**Поддержка универсальной и многофакторной проверки подлинности Azure Active Directory**

В соответствии с более строгими требованиями к безопасности и соблюдению норм многим клиентам приходится использовать многофакторную проверку подлинности (MFA). Кроме того, в настоящее время не рекомендуется включать пароли пользователей непосредственно в строки подключения. В связи с этими изменениями в .NET Framework 4.7.2 [строки подключения SQLClient](xref:System.Data.SqlClient.SqlConnection.ConnectionString) теперь имеют новое значение Active Directory Interactive для существующего ключевого слова "Проверка подлинности", чтобы обеспечить MFA и [аутентификацию Azure AD](/azure/sql-database/sql-database-aad-authentication-configure). Новый интерактивный метод поддерживает собственных и федеративных пользователей Azure AD, а также гостевых пользователей Azure AD. При использовании этого метода многофакторная проверка подлинности, требуемая Azure AD, поддерживается для баз данных SQL. Кроме того, процесс проверки подлинности запрашивает у пользователя пароль в соответствии с рекомендациями по обеспечению безопасности.

В предыдущих версиях платформы .NET Framework подключение SQL поддерживало только параметры <xref:System.Data.SqlClient.SqlAuthenticationMethod.ActiveDirectoryPassword?displayProperty=nameWithType> и <xref:System.Data.SqlClient.SqlAuthenticationMethod.ActiveDirectoryIntegrated?displayProperty=nameWithType>. Оба параметра входят в неинтерактивный [протокол ADAL](/azure/active-directory/develop/active-directory-authentication-libraries), который не поддерживает многофакторную проверку подлинности. С новым параметром <xref:System.Data.SqlClient.SqlAuthenticationMethod.ActiveDirectoryInteractive?displayProperty=nameWithType> подключение SQL поддерживает многофакторную проверку подлинности, а также существующие методы проверки подлинности (пароль и встроенная проверка подлинности), что позволяет пользователям вводить пароли в интерактивном режиме без их сохранения в строке подключения.

Дополнительные сведения и пример см. в разделе "Поддержка универсальной и многофакторной проверки подлинности SQL — Azure AD" в [блоге о .NET](https://devblogs.microsoft.com/dotnet/net-framework-4-7-2-developer-pack-early-access-build-3056-is-available/).

**Поддержка Always Encrypted версии 2**

В NET Framework 4.7.2 добавлена поддержка Always Encrypted на основе анклава. Исходная версия Always Encrypted — это технология шифрования на стороне клиента, в рамках которой ключи шифрования никогда не покидали клиента. В Always Encrypted на основе анклава клиент может при необходимости отправлять ключи шифрования в безопасный анклав, который является защищенным вычислительным объектом и может считаться частью SQL Server, но код SQL Server не может его изменить. Чтобы обеспечить поддержку Always Encrypted на основе анклава, в .NET Framework 4.7.2 добавлены следующие типы и члены для пространства имен <xref:System.Data.SqlClient>:

- <xref:System.Data.SqlClient.SqlConnectionStringBuilder.EnclaveAttestationUrl?displayProperty=nameWithType> — указывает URI для Always Encrypted на основе анклава.

- <xref:System.Data.SqlClient.SqlColumnEncryptionEnclaveProvider> — абстрактный класс, из которого происходят все поставщики анклавов.

- <xref:System.Data.SqlClient.SqlEnclaveSession> — инкапсулирует состояние определенного сеанса анклава.

- <xref:System.Data.SqlClient.SqlEnclaveAttestationParameters> — предоставляет параметры подтверждения, используемые SQL Server для получения сведений, необходимых для выполнения определенного протокола подтверждения.

Файл конфигурации приложения указывает конкретную реализацию абстрактного класса <xref:System.Data.SqlClient.SqlColumnEncryptionEnclaveProvider?displayProperty=nameWithType>, который предоставляет функциональные возможности для поставщика анклава. Например:

```xml
<configuration>
  <configSections>
    <section name="SqlColumnEncryptionEnclaveProviders" type="System.Data.SqlClient.SqlColumnEncryptionEnclaveProviderConfigurationSection,System.Data,Version=4.0.0.0,Culture=neutral,PublicKeyToken=b77a5c561934e089"/> 
  </configSections>
  <SqlColumnEncryptionEnclaveProviders>
    <providers>
      <add name="Azure" type="Microsoft.SqlServer.Management.AlwaysEncrypted.AzureEnclaveProvider,MyApp"/>
      <add name="HGS" type="Microsoft.SqlServer.Management.AlwaysEncrypted.HGSEnclaveProvider,MyApp" />
    </providers>
  </SqlColumnEncryptionEnclaveProviders >
</configuration>
```

Базовый поток Always Encrypted на основе анклава:

1. Пользователь создает подключение AlwaysEncrypted к SQL Server с поддержкой Always Encrypted на основе анклава. Драйвер обращается в службу аттестации, чтобы обеспечить подключение к нужному анклаву.

1. После аттестации анклава драйвер устанавливает защищенный канал с безопасным анклавом, размещенным на SQL Server.

1. Драйвер использует ключи шифрования, авторизованные клиентом, совместно с безопасным анклавом в течение всего соединения SQL.

<a name="wpf472" />

#### <a name="windows-presentation-foundation"></a>Windows Presentation Foundation

**Поиск ResourceDictionary по источнику**

Начиная с .NET Framework 4.7.2, помощник по диагностике может находить словари  <xref:System.Windows.Xps.Packaging.IXpsFixedPageReader.ResourceDictionaries>, созданные из указанного URI источника. (Эта функция предназначена для использования помощником по диагностике, а не приложением в производственной среде.) Помощник по диагностике, например средство "Изменить и продолжить" в Visual Studio, позволяет пользователям редактировать ResourceDictionary с целью применить изменения к запущенному приложению. Шагом к достижению этого является поиск всех ResourceDictionary, созданных запущенным приложением из редактируемого словаря. Например, приложение может объявить ResourceDictionary, содержимое которого копируется из определенного источника URI:

```xml
<ResourceDictionary Source="MyRD.xaml">
```

Помощник по диагностике, который изменяет исходную разметку в *MyRD.xaml* , может использовать новую функцию для поиска словаря. Эта функция реализуется новым статическим методом <xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics.GetResourceDictionariesForSource%2A?displayProperty=nameWithType>. Помощник по диагностике вызывает новый метод с помощью абсолютного URI, который определяет исходную разметку, как показано в следующем примере кода:

```csharp
IEnumerable<ResourceDictionary> dictionaries = ResourceDictionaryDiagnostics.GetResourceDictionariesForSource(new Uri("pack://application:,,,/MyApp;component/MyRD.xaml"));
```

```vb
Dim dictionaries As IEnumerable(Of ResourceDictionary) = ResourceDictionaryDiagnostics.GetResourceDictionariesForSource(New Uri("pack://application:,,,/MyApp;component/MyRD.xaml"))
```

Метод возвращает пустое перечисляемое значение, если не включен класс <xref:System.Windows.Diagnostics.VisualDiagnostics> и не указана переменная среды [`ENABLE_XAML_DIAGNOSTICS_SOURCE_INFO`](xref:System.Windows.Diagnostics.VisualDiagnostics.GetXamlSourceInfo%2A) .

**Поиск владельцев ResourceDictionary**

Начиная с .NET Framework 4.7.2, помощник по диагностике может находить владельцев определенного словаря <xref:Windows.UI.Xaml.ResourceDictionary>. (Эта функция предназначена для помощников по диагностике, а не приложений в производственной среде.) При каждом изменении <xref:Windows.UI.Xaml.ResourceDictionary> WPF автоматически обнаруживает все ссылки [DynamicResource](../wpf/advanced/dynamicresource-markup-extension.md), на которые может повлиять изменение.

Помощник по диагностике, например средство "Изменить и продолжить" в Visual Studio, может в том числе обрабатывать ссылки [StaticResource](../wpf/advanced/staticresource-markup-extension.md). Первым этапом этого процесса является поиск владельцев словаря; то есть поиск всех объектов, свойство `Resources` которых ссылается на словарь (напрямую или косвенно через свойство <xref:System.Windows.ResourceDictionary.MergedDictionaries?displayProperty=nameWithType>). В поддержку этого этапа в классе <xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics?displayProperty=nameWithType> реализовано три новых статических метода, по одному для каждого базового типа со свойством `Resources`:

- [`public static IEnumerable<FrameworkElement> GetFrameworkElementOwners(ResourceDictionary dictionary);`](xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics.GetFrameworkElementOwners%2A)

- [`public static IEnumerable<FrameworkContentElement> GetFrameworkContentElementOwners(ResourceDictionary dictionary);`](xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics.GetFrameworkContentElementOwners%2A)

- [`public static IEnumerable<Application> GetApplicationOwners(ResourceDictionary dictionary);`](xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics.GetApplicationOwners%2A)

Эти методы возвращают пустое перечисляемое значение, если не включен класс <xref:System.Windows.Diagnostics.VisualDiagnostics> и не указана переменная среды [`ENABLE_XAML_DIAGNOSTICS_SOURCE_INFO`](xref:System.Windows.Diagnostics.VisualDiagnostics.GetXamlSourceInfo%2A) .

**Поиск ссылок StaticResource**

Помощник по диагностике теперь может получать уведомление при разрешении ссылки [StaticResource](../wpf/advanced/staticresource-markup-extension.md). (Эта функция предназначена для помощников по диагностике, а не приложений в производственной среде.) Помощник по диагностике, например средство "Изменить и продолжить" в Visual Studio, может обновить все случаи использования ресурса, когда его значение в <xref:Windows.UI.Xaml.ResourceDictionary> меняется. WPF выполняет это автоматически для ссылок [DynamicResource](../wpf/advanced/dynamicresource-markup-extension.md), но специально не делает этого для ссылок [StaticResource](../wpf/advanced/staticresource-markup-extension.md). Начиная с .NET Framework 4.7.2, помощник по диагностике может использовать эти уведомления для поиска случаев использования статического ресурса.

Уведомление реализуется новым событием <xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics.StaticResourceResolved?displayProperty=nameWithType>:

```csharp
public static event EventHandler<StaticResourceResolvedEventArgs> StaticResourceResolved;
```

```vb
Public Shared Event StaticResourceResolved As EventHandler(Of StaticResourceResolvedEventArgs)
```

Это событие возникает каждый раз, когда среда выполнения разрешает ссылку [StaticResource](../wpf/advanced/staticresource-markup-extension.md). Аргументы <xref:System.Windows.Diagnostics.StaticResourceResolvedEventArgs> описывают разрешение и ключ, используемый для разрешения, а также указывают объект и свойство, в котором указаны ссылка [StaticResource](../wpf/advanced/staticresource-markup-extension.md) и словарь <xref:Windows.UI.Xaml.ResourceDictionary>:

```csharp
public class StaticResourceResolvedEventArgs : EventArgs
{
   public Object TargetObject { get; }

   public Object TargetProperty { get; }

   public ResourceDictionary ResourceDictionary { get; }

   public object ResourceKey { get; }
}
```

```vb
Public Class StaticResourceResolvedEventArgs : Inherits EventArgs
   Public ReadOnly Property TargetObject As Object
   Public ReadOnly Property TargetProperty As Object
   Public ReadOnly Property ResourceDictionary As ResourceDictionary
   Public ReadOnly Property ResourceKey As Object
End Class
```

Событие не происходит (и метод доступа `add` игнорируется), если не включен класс  <xref:System.Windows.Diagnostics.VisualDiagnostics> и не задана переменная среды [`ENABLE_XAML_DIAGNOSTICS_SOURCE_INFO`](xref:System.Windows.Diagnostics.VisualDiagnostics.GetXamlSourceInfo%2A) .

#### <a name="clickonce"></a>ClickOnce

Приложения, совместимые с HDPI, для Windows Forms, Windows Presentation Foundation (WPF) и Visual Studio Tools для Office (VSTO) можно развернуть с помощью ClickOnce. Если в манифесте приложения обнаружена следующая запись, развертывание в .NET Framework 4.7.2 будет успешным:

```xml
<windowsSettings>
   <dpiAware xmlns="http://schemas.microsoft.com/SMI/2005/WindowsSettings">true</dpiAware>
</windowsSettings>
```

Для приложения Windows Forms использовавшийся ранее обходной путь установки поддержки определения DPI в файле конфигурации приложения вместо манифеста приложения больше не требуется для успешного развертывания ClickOnce.

<a name="v471" />

## <a name="whats-new-in-net-framework-471"></a>Новые возможности .NET Framework 4.7.1

.NET Framework 4.7.1 включает новые функции в следующих областях:

- [Базовые классы](#core471)
- [Среда CLR](#clr)
- [Сеть](#net471)
- [ASP.NET](#asp-net471)

Основной акцент в .NET Framework 4.7.1, как и прежде, сделан на улучшении специальных возможностей, что позволяет приложению предоставлять соответствующие функции целевой аудитории. См. подробнее об [улучшениях специальных возможностей в .NET Framework 4.7.1](whats-new-in-accessibility.md).

<a name="core471" />

#### <a name="base-classes"></a>базовых классов;

**Поддержка .NET Standard 2.0**

[.NET Standard](../../standard/net-standard.md) определяет набор интерфейсов API, которые должны быть доступны в каждой реализации .NET, поддерживающей эту версию стандарта. .NET Framework 4.7.1 полностью поддерживает .NET Standard 2.0 и предлагает [около 200 API](https://github.com/dotnet/standard/blob/master/netstandard/src/ApiCompatBaseline.net461.txt), которые определены в .NET Standard 2.0 и отсутствуют в .NET Framework версий 4.6.1, 4.6.2 и 4.7. (Обратите внимание, что эти версии .NET Framework поддерживают .NET Standard 2.0 только в том случае, если дополнительные файлы поддержки .NET Standard также развертываются в целевой системе.) Дополнительные сведения см. в разделе о поддержке .NET Standard 2.0 в записи блога [.NET Framework 4.7.1 Runtime and Compiler Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-runtime-and-compiler-features/) (Возможности среды выполнения .NET Framework 4.7.1 и компилятора).

**Поддержка построителей конфигурации**

Построители конфигурации позволяют разработчикам внедрять и динамически создавать параметры конфигурации для приложения во время выполнения. Пользовательские построители конфигурации можно использовать для изменения существующих данных в разделе конфигурации или для создания раздела конфигурации с нуля. Без построителей конфигурации файлы .config являются статическими, а их параметры определяются за некоторое время до запуска приложения.

Чтобы создать пользовательский построитель конфигурации, следует наследовать построитель от абстрактного класса <xref:System.Configuration.ConfigurationBuilder> и переопределить его <xref:System.Configuration.ConfigurationBuilder.ProcessConfigurationSection%2A?displayProperty=nameWithType> и <xref:System.Configuration.ConfigurationBuilder.ProcessRawXml%2A?displayProperty=nameWithType>. Кроме того, построители можно определить в файле конфигурации. Дополнительные сведения см. в разделе о построителях конфигурации в записи блога [.NET Framework 4.7.1 ASP.NET and Configuration Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-asp-net-and-configuration-features/) (Возможности .NET Framework 4.7.1 ASP.NET и конфигурации).

**Обнаружение функций во время выполнения**

Класс <xref:System.Runtime.CompilerServices.RuntimeFeature?displayProperty=nameWithType> предоставляет механизм, позволяющий определить, поддерживается ли предопределенная функция в данной реализации .NET во время компиляции или во время выполнения. Во время компиляции компилятор может проверить наличие указанного поля, чтобы определить, поддерживается ли эта функция. Если да, он может вывести код, использующий эту функцию. Во время выполнения приложение может вызвать метод <xref:System.Runtime.CompilerServices.RuntimeFeature.IsSupported%2A?displayProperty=nameWithType> до создания кода. Дополнительные сведения см. в статье [Добавление вспомогательного метода для описания функций, поддерживаемых средой выполнения](https://github.com/dotnet/corefx/issues/17116).

**Типы кортежей значений являются сериализуемыми**

Начиная с .NET Framework 4.7.1, <xref:System.ValueTuple?displayProperty=nameWithType> и связанные универсальные типы помечаются как [сериализуемые](xref:System.SerializableAttribute), что обеспечивает двоичную сериализацию. Эта возможность должна упростить миграцию типов кортежей, таких как <xref:System.Tuple%603> и <xref:System.Tuple%604>, в типы кортежей значений. Дополнительные сведения см. в разделе о сериализации ValueTuple в записи блога [.NET Framework 4.7.1 Runtime and Compiler Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-runtime-and-compiler-features/) (Возможности среды выполнения .NET Framework 4.7.1 и компилятора).

**Поддержка ссылок только для чтения**

.NET Framework 4.7.1 включает <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute?displayProperty=nameWithType>. Этот атрибут используется компиляторами языка для пометки членов, имеющих типы возвращаемые ссылочные значения (или параметры) только для чтения. Дополнительные сведения см. в разделе о поддержке ReadOnlyReferences в записи блога [.NET Framework 4.7.1 Runtime and Compiler Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-runtime-and-compiler-features/) (Возможности среды выполнения .NET Framework 4.7.1 и компилятора). Сведения о возвращаемых ссылочных значениях см. в разделах [Возвращаемые ссылочные значения и ссылочные локальные переменные (справочник по C#)](../../csharp/programming-guide/classes-and-structs/ref-returns.md) и [Возвращаемые ссылочные значения (Visual Basic)](../../visual-basic/programming-guide/language-features/procedures/ref-return-values.md).

<a name="clr" />

#### <a name="common-language-runtime-clr"></a>Среда CLR

**Повышение производительности сборки мусора**

Изменения функции сборки мусора (GC) в .NET Framework 4.7.1 повышают общую производительность, особенно для распределений кучи больших объектов (LOH). В .NET Framework 4.7.1 для распределений куч больших (LOH) и малых (SOH) объектов используются отдельные блокировки, что позволяет выполнять распределение кучи больших объектов, когда фоновый сборщик мусора очищает кучу малых объектов. В результате в приложениях с большим количеством операций выделения LOH сократится число конфликтов при блокировках выделений и улучшится производительность. Дополнительные сведения см. в разделе о повышении производительности сборки мусора в записи блога [.NET Framework 4.7.1 Runtime and Compiler Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-runtime-and-compiler-features/) (Возможности среды выполнения .NET Framework 4.7.1 и компилятора).

<a name="net471"/>

#### <a name="networking"></a>Сети

**Поддержка SHA-2 Message.HashAlgorithm**

В .NET Framework 4.7 и более ранних версиях свойство <xref:System.Messaging.Message.HashAlgorithm%2A?displayProperty=nameWithType> поддерживало только значения <xref:System.Messaging.HashAlgorithm.Md5?displayProperty=nameWithType> и <xref:System.Messaging.HashAlgorithm.Sha?displayProperty=nameWithType>. Начиная с .NET Framework 4.7.1, также поддерживаются значения <xref:System.Messaging.HashAlgorithm.Sha256?displayProperty=nameWithType>, <xref:System.Messaging.HashAlgorithm.Sha384?displayProperty=nameWithType> и <xref:System.Messaging.HashAlgorithm.Sha512?displayProperty=nameWithType>. Будет ли это значение использоваться на самом деле, зависит от MSMQ, поскольку сам экземпляр <xref:System.Messaging.Message> не выполняет хэширование, а просто передает значения в MSMQ. Дополнительные сведения см. в разделе поддержке о SHA-2 для Message.HashAlgorithm в записи блога [.NET Framework 4.7.1 ASP.NET and Configuration features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-asp-net-and-configuration-features/) (Возможности .NET Framework 4.7.1 ASP.NET и конфигурации).

<a name="asp-net471" />

#### <a name="aspnet"></a>ASP.NET

**Действия выполнения в приложениях ASP.NET**

ASP.NET обрабатывает запросы в предопределенном конвейере, который содержит 23 события. ASP.NET выполняет каждый обработчик событий как действие выполнения. В версиях ASP.NET до .NET Framework 4.7 платформа ASP.NET не может использовать контекст выполнения из-за переключений между собственным и управляемым потоками. Вместо этого ASP.NET выборочно выполняет только <xref:System.Web.HttpContext>. Начиная с .NET Framework 4.7.1, метод <xref:System.Web.HttpApplication.OnExecuteRequestStep(System.Action{System.Web.HttpContextBase,System.Action})?displayProperty=nameWithType> также позволяет использовать модули для восстановления внешних данных. Эта функция предназначена для библиотек, связанных с трассировкой, профилированием, диагностикой или транзакциями, например для тех, которые учитывают поток работы приложения. Дополнительные сведения см. в разделе о действии выполнения ASP.NET в записи блога [.NET Framework 4.7.1 ASP.NET and Configuration Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-asp-net-and-configuration-features/) (Возможности .NET Framework 4.7.1 ASP.NET и конфигурации).

**Синтаксический анализ HttpCookie ASP.NET**

В .NET Framework 4.7.1 добавлен новый метод <xref:System.Web.HttpCookie.TryParse%2A?displayProperty=nameWithType>, который обеспечивает стандартный способ создания объекта <xref:System.Web.HttpCookie> из строки и позволяет точно назначать значения cookie, такие как дата окончания срока действия и путь. Дополнительные сведения см. в разделе о синтаксическом анализе HttpCookie ASP.NET в записи блога [.NET Framework 4.7.1 ASP.NET and Configuration Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-asp-net-and-configuration-features/) (Возможности .NET Framework 4.7.1 ASP.NET и конфигурации).

**Функции хэширования SHA-2 для учетных данных проверки подлинности форм ASP.NET**

В .NET Framework 4.7 и более ранних версиях разработчики ASP.NET могли хранить учетные данные пользователей с паролями, хэшированными с помощью MD5 или SHA1, в файлах конфигурации. Начиная с .NET Framework 4.7.1, ASP.NET также поддерживает новые безопасные функции алгоритма SHA-2, такие как SHA256, SHA384 и SHA512. SHA1 остается алгоритмом по умолчанию, а нестандартный хэш-алгоритм можно определить в файле веб-конфигурации. Например:

```xml
<system.web>
    <authentication mode="Forms">
        <forms loginUrl="~/login.aspx">
          <credentials passwordFormat="SHA512">
            <user name="jdoe" password="6D003E98EA1C7F04ABF8FCB375388907B7F3EE06F278DB966BE960E7CBBD103DF30CA6D61F7E7FD981B2E4E3A64D43C836A4BEDCA165C33B163E6BCDC538A664" />
          </credentials>
        </forms>
    </authentication>
</system.web>
```

<a name="v47" />

## <a name="whats-new-in-net-framework-47"></a>Новые возможности .NET Framework 4.7

.NET Framework 4.7 включает новые функции в следующих областях:

- [Базовые классы](#Core47)
- [Сеть](#net47)
- [ASP.NET](#ASP-NET47)
- [Windows Communication Foundation (WCF)](#wcf47)
- [Windows Forms](#wf47)
- [Windows Presentation Foundation (WPF)](#WPF47)

См. подробнее об [изменениях списка API в .NET Framework 4.7](https://github.com/Microsoft/dotnet/blob/master/releases/net47/dotnet47-api-changes.md) на сайте GitHub. См. подробнее об [улучшенных функциях и исправленных ошибках в .NET Framework 4.7](https://github.com/Microsoft/dotnet/blob/master/releases/net47/dotnet47-changes.md) на сайте GitHub.  Дополнительные сведения см. в записи блога .NET, посвященной [объявлению о выпуске .NET Framework 4.7](https://devblogs.microsoft.com/dotnet/announcing-the-net-framework-4-7/).

<a name="Core47" />

#### <a name="base-classes"></a>базовых классов;

.NET Framework 4.7 улучшает сериализацию, используя <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>:

**Дополнительные функциональные возможности на основе эллиптической криптографии (ECC)** *

В .NET Framework 4.7 добавлены методы `ImportParameters(ECParameters)` в классы <xref:System.Security.Cryptography.ECDsa> и <xref:System.Security.Cryptography.ECDiffieHellman>, которые позволяют объекту представлять уже установленный ключ. Также добавлен метод `ExportParameters(Boolean)` для экспорта ключа с явными параметрами кривой.

В .NET Framework 4.7 также добавлена поддержка дополнительных кривых (включая пакет кривых Brainpool) и стандартные определения для упрощения создания с помощью новых фабричных методов <xref:System.Security.Cryptography.ECDsa.Create%2A> и <xref:System.Security.Cryptography.ECDiffieHellman.Create%2A>.

На GitHub вы найдете [пример криптографических улучшений в .NET Framework 4.7](https://gist.github.com/richlander/5a182899895a87a296c21ada97f7a54e).

**Улучшенная поддержка управляющих символов для DataContractJsonSerializer**

В .NET Framework 4.7 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> сериализует управляющие символы в соответствии со стандартом ECMAScript 6. Это поведение включено по умолчанию для приложений, предназначенных для использования с .NET Framework 4.7, и предлагается в качестве дополнительной функции для приложений, которые выполняются в среде .NET Framework 4.7, но предназначены для использования с предыдущими версиями .NET Framework. Дополнительные сведения см. в статье [Изменения целевой платформы в .NET Framework 4.7](../migration-guide/retargeting-changes-in-the-net-framework-4-7.md).

<a name="net47" />

#### <a name="networking"></a>Сети

В .NET Framework 4.7 добавлена следующая сетевая функция:

**Поддержка операционной системы по умолчанию для протоколов TLS***

Стек TLS, который используется в <xref:System.Net.Security.SslStream?displayProperty=nameWithType> и других компонентах, расположенных в стеке над ним (например, HTTP, FTP и SMTP), позволяет разработчикам использовать протоколы TLS по умолчанию, поддерживаемые операционной системой. Разработчики теперь не обязаны жестко указывать версию TLS.

<a name="ASP-NET47" />

#### <a name="aspnet"></a>ASP.NET

В ASP.NET в .NET Framework 4.7 добавлены следующие новые функции:

**Расширяемость кэша объектов**

Начиная с .NET Framework 4.7 в ASP.NET добавлен новый набор API, которые позволяют разработчикам заменить стандартные реализации ASP.NET для кэширования объектов в памяти и мониторинга использования памяти. Разработчики могут переопределить любой из следующих трех компонентов, если их не устраивает стандартная реализация ASP.NET.

- **Хранилище кэша объектов**. В новом разделе конфигурации поставщиков кэша разработчик может подключить новую реализацию кэша объектов для приложения ASP.NET с помощью нового интерфейса **ICacheStoreProvider**.

- **Мониторинг памяти**. Стандартный монитор памяти ASP.NET уведомляет приложения о том, что они приближаются к настроенному для процесса лимиту байтов исключительного пользования, а также о нехватке общей доступной физической памяти на компьютере. Уведомление срабатывает незадолго до достижения ограничения. Для некоторых приложений эти уведомления поступают слишком поздно и не позволяют предпринять никаких разумных действий. Разработчики могут использовать собственные мониторы памяти, чтобы заменить значение по умолчанию с помощью свойства <xref:System.Web.Hosting.ApplicationMonitors.MemoryMonitor%2A?displayProperty=nameWithType>.

- **Реакции на достижение лимита памяти**. По умолчанию ASP.NET пытается обрезать кэш объектов, периодически вызывая функцию <xref:System.GC.Collect%2A?displayProperty=nameWithType> при приближении к лимиту байтов исключительного пользования для процесса. Для некоторых приложений частота вызовов <xref:System.GC.Collect%2A?displayProperty=nameWithType> или размер кэша после обрезки не позволяют обеспечить эффективность работы. Теперь разработчик может изменить или дополнить поведение по умолчанию, назначив собственную реализацию **IObserver** в качестве монитора памяти для приложения.

<a name="wcf47" />

#### <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)

В Windows Communication Foundation (WCF) добавлены следующие функции и изменения:

**Возможность настраивать параметры безопасности сообщений по умолчанию для TLS 1.1 или TLS 1.2**

Начиная с .NET Framework 4.7, WCF позволяет настраивать в качестве протокола безопасности сообщений по умолчанию протоколы TSL 1.1 и TLS 1.2, а не только SSL 3.0 и TSL 1.0. Эту возможность нужно дополнительно активировать, добавив следующую запись в файл конфигурации приложения:

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;Switch.System.Net.DontEnableSchUseStrongCrypto=false" />
</runtime>
```

**Повышенная надежность приложений WCF и сериализации WCF**

Для WCF внесены несколько изменений кода, которые позволяют избежать состояний гонки, повышая таким образом производительность и надежность методов сериализации. Сюда входит следующее.

- Улучшение поддержки для совместного использования асинхронного и синхронного кода в вызовах **SocketConnection.BeginRead** и **SocketConnection.Read**.
- Повышение надежности при разрыве подключения с **SharedConnectionListener** и **DuplexChannelBinder**.
- Повышение надежности операций сериализации при вызове метода <xref:System.Runtime.Serialization.FormatterServices.GetSerializableMembers%28System.Type%29?displayProperty=nameWithType>.
- Повышение надежности при удалении обслуживающего потока путем вызова метода **ChannelSynchronizer.RemoveWaiter**.

<a name="wf47" />

#### <a name="windows-forms"></a>Windows Forms

В .NET Framework 4.7 для Windows Forms улучшена поддержка мониторов с высоким разрешением.

**Поддержка высокого разрешения**

Начиная с приложений, предназначенных для использования с .NET Framework 4.7, в .NET Framework поддерживается высокое разрешение и динамическое разрешение для приложений Windows Forms. Поддержка высокого разрешения улучшает расположение и внешний вид форм и элементов управления на мониторах с высокой плотностью точек на дюйм. Функция динамического разрешения изменяет расположение и внешний вид формы и элементов управления, когда пользователь изменяет разрешение монитора или масштаб отображения при запущенном приложении.

Поддержку высокого разрешения нужно активировать дополнительно, определив раздел [\<System.Windows.Forms.ConfigurationSection>](../configure-apps/file-schema/winforms/index.md) в файле конфигурации приложения. Дополнительные сведения об активации поддержки высокого разрешения и динамического разрешения для приложений Windows Forms вы можете найти в статье [Поддержка высокого DPI в Windows Forms](../winforms/high-dpi-support-in-windows-forms.md).

<a name="WPF47" />

#### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

В .NET Framework 4.7 добавлены следующие улучшения WPF:

**Поддержка стека для управления касанием или пером, основанного на сообщениях Windows WM_POINTER**

Теперь вы можете использовать стек управления касанием или пером на основе сообщений [WM_POINTER](https://docs.microsoft.com/previous-versions/windows/desktop/InputMsg/messages) вместо платформы служб рукописного ввода Windows (WISP). Эту функцию нужно отдельно активировать в .NET Framework. Дополнительные сведения см. в статье [Изменения целевой платформы в .NET Framework 4.7](../migration-guide/retargeting-changes-in-the-net-framework-4-7.md).

**Новая реализация интерфейсов API WPF для печати**

API-интерфейсы WPF для печати в классе <xref:System.Printing.PrintQueue?displayProperty=nameWithType> вызывают [API пакета печати документа](/windows/desktop/printdocs/tailored-app-printing-api) Windows вместо устаревших [API печати XPS](/windows/desktop/printdocs/xps-printing). Влияние этого изменения на совместимость приложений можно изучить в статье [Изменения целевой платформы в .NET Framework 4.7](../migration-guide/retargeting-changes-in-the-net-framework-4-7.md).

<a name="v462" />

## <a name="whats-new-in-net-framework-462"></a>Новые возможности .NET Framework 4.6.2

Версия .NET Framework 4.6.2 включает новые функции в следующих областях:

- [ASP.NET](#ASPNET462)

- [Категории символов](#Strings)

- [Шифрование](#Crypto462)

- [SqlClient](#SQLClient)

- [Windows Communication Foundation](#WCF)

- [Windows Presentation Foundation (WPF)](#WPF462)

- [Windows Workflow Foundation (WF)](#WF462)

- [ClickOnce](#clickonce-1)

- [Преобразование приложений Windows Forms и WPF в приложения UWP](#UWPConvert)

- [Усовершенствования отладки](#Debug462)

См. подробнее об [изменениях списка API в .NET Framework 4.6.2](https://github.com/Microsoft/dotnet/blob/master/releases/net462/dotnet462-api-changes.md) на сайте GitHub. См. подробнее об [улучшенных функциях и исправленных ошибках в .NET Framework 4.6.2](https://go.microsoft.com/fwlink/?LinkId=708778) на сайте GitHub.  Дополнительные сведения см. в разделе [Объявление о выпуске .NET Framework 4.6.2](https://devblogs.microsoft.com/dotnet/announcing-net-framework-4-6-2/) в блоге .NET.

<a name="ASPNET462" />

### <a name="aspnet"></a>ASP.NET

ASP.NET в .NET Framework 4.6.2 включает следующие улучшения.

**Улучшена поддержка локализованных сообщений об ошибках в проверяющих элементах управления заметок к данным.**

Модули проверки заметок к данным позволяют выполнять проверки путем добавления одного или нескольких атрибутов к свойству класса. Элемент <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=nameWithType> атрибута определяет текст сообщения об ошибке, если проверка не пройдена. Начиная с .NET Framework 4.6.2 в ASP.NET упрощена локализация сообщений об ошибках. Локализация сообщений об ошибках происходит в указанных далее случаях.

1. В атрибуте проверки указан <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=nameWithType>.

2. Файл ресурсов хранится в папке App_LocalResources.

3. Имя локализованного файла ресурсов имеет форму `DataAnnotation.Localization.{`*имя*`}.resx`, где *имя* — это имя языка и региональных параметров в формате *languageCode*`-`*country/regionCode* или *languageCode*.

4. Имя ключа ресурса является строкой, назначенной атрибуту <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=nameWithType>, а его значением является локализованное сообщение об ошибке.

Например, следующий атрибут заметки к данным задает сообщение об ошибке для неверной оценки в рамках языка и региональных параметров по умолчанию.

```csharp
public class RatingInfo
{
   [Required(ErrorMessage = "The rating must be between 1 and 10.")]
   [Display(Name = "Your Rating")]
   public int Rating { get; set; }
}
```

```vb
Public Class RatingInfo
   <Required(ErrorMessage = "The rating must be between 1 and 10.")>
   <Display(Name = "Your Rating")>
   Public Property Rating As Integer = 1
End Class
```

Затем можно создать файл ресурсов DataAnnotation.Localization.fr.resx, ключом в котором является строка сообщения об ошибке, а значением — локализованное сообщение об ошибке. Этот файл должен находиться в папке `App.LocalResources`. Например, ниже приведен ключ и его значение в сообщении об ошибке, локализованном в рамках французского языка и региональных параметров (French (fr)).

| name                                 | Значение                                     |
| ------------------------------------ | ----------------------------------------- |
| The rating must be between 1 and 10. | La note doit être comprise entre 1 et 10. |

 Кроме того, локализация заметок к данным является расширяемой. Разработчики могут подключить собственный поставщик локализатора строк путем реализации интерфейса <xref:System.Web.Globalization.IStringLocalizerProvider> для хранения строки локализации в месте, отличном от файла ресурсов.

 **Поддержка асинхронного выполнения с поставщиками хранилищ состояния сеансов**

 Теперь ASP.NET позволяет использовать методы, возвращающие задачи, с поставщиками хранилища состояния сеанса, тем самым разрешая приложениям ASP.NET реализовывать преимущества масштабируемости асинхронных операций. Для поддержки асинхронных операций с поставщиками хранилищ состояния сеансов ASP.NET предлагает новый интерфейс <xref:System.Web.SessionState.ISessionStateModule?displayProperty=nameWithType>, который наследует от <xref:System.Web.IHttpModule> и позволяет разработчикам реализовывать их собственные модули состояния сеансов и асинхронные поставщики хранилищ сеансов. Интерфейс определяется следующим образом:

```csharp
public interface ISessionStateModule : IHttpModule {
    void ReleaseSessionState(HttpContext context);
    Task ReleaseSessionStateAsync(HttpContext context);
}
```

```vb
Public Interface ISessionStateModule : Inherits IHttpModule
   Sub ReleaseSessionState(context As HttpContext)
   Function ReleaseSessionStateAsync(context As HttpContext) As Task
End Interface
```

 Кроме того, класс <xref:System.Web.SessionState.SessionStateUtility> включает два новых метода (<xref:System.Web.SessionState.SessionStateUtility.IsSessionStateReadOnly%2A> и <xref:System.Web.SessionState.SessionStateUtility.IsSessionStateRequired%2A>), которые можно использоваться для поддержки асинхронных операций.

 **Поддержка асинхронного выполнения поставщиков кэша вывода**

 Начиная с .NET Framework 4.6.2 с поставщиками кэша вывода можно использовать методы, возвращающие задачи, чтобы воспользоваться преимуществами асинхронных операций по масштабируемости.  Поставщики, реализующие эти методы, сокращают вероятность блокировок потоков на веб-сервере и улучшают масштабируемость службы ASP.NET.

 Для поддержки поставщиков кэша асинхронного вывода были добавлены следующие API:

- Класс <xref:System.Web.Caching.OutputCacheProviderAsync?displayProperty=nameWithType>, который наследует от <xref:System.Web.Caching.OutputCacheProvider?displayProperty=nameWithType> и позволяет разработчикам реализовать поставщик кэша асинхронного вывода.

- Класс <xref:System.Web.Caching.OutputCacheUtility>, который предоставляет вспомогательные методы для настройки кэша вывода.

- 18 новых методов в классе <xref:System.Web.HttpCachePolicy?displayProperty=nameWithType>. К ним относятся <xref:System.Web.HttpCachePolicy.GetCacheability%2A>, <xref:System.Web.HttpCachePolicy.GetCacheExtensions%2A>, <xref:System.Web.HttpCachePolicy.GetETag%2A>, <xref:System.Web.HttpCachePolicy.GetETagFromFileDependencies%2A>, <xref:System.Web.HttpCachePolicy.GetMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetNoStore%2A>, <xref:System.Web.HttpCachePolicy.GetNoTransforms%2A>, <xref:System.Web.HttpCachePolicy.GetOmitVaryStar%2A>, <xref:System.Web.HttpCachePolicy.GetProxyMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetRevalidation%2A>, <xref:System.Web.HttpCachePolicy.GetUtcLastModified%2A>, <xref:System.Web.HttpCachePolicy.GetVaryByCustom%2A>, <xref:System.Web.HttpCachePolicy.HasSlidingExpiration%2A> и <xref:System.Web.HttpCachePolicy.IsValidUntilExpires%2A>.

- 2 новых метода в классе <xref:System.Web.HttpCacheVaryByContentEncodings?displayProperty=nameWithType>: <xref:System.Web.HttpCacheVaryByContentEncodings.GetContentEncodings%2A> и <xref:System.Web.HttpCacheVaryByContentEncodings.SetContentEncodings%2A>.

- 2 новых метода в классе <xref:System.Web.HttpCacheVaryByHeaders?displayProperty=nameWithType>: <xref:System.Web.HttpCacheVaryByHeaders.GetHeaders%2A> и <xref:System.Web.HttpCacheVaryByHeaders.SetHeaders%2A>.

- 2 новых метода в классе <xref:System.Web.HttpCacheVaryByParams?displayProperty=nameWithType>: <xref:System.Web.HttpCacheVaryByParams.GetParams%2A> и <xref:System.Web.HttpCacheVaryByParams.SetParams%2A>.

- В классе <xref:System.Web.Caching.AggregateCacheDependency?displayProperty=nameWithType> метод <xref:System.Web.Caching.AggregateCacheDependency.GetFileDependencies%2A>.

- В классе <xref:System.Web.Caching.CacheDependency> метод <xref:System.Web.Caching.CacheDependency.GetFileDependencies%2A>.

<a name="Strings" />

### <a name="character-categories"></a>Категории символов

Символы в .NET Framework 4.6.2 классифицируются на основе [стандарта Юникод версии 8.0.0](https://www.unicode.org/versions/Unicode8.0.0/). В .NET Framework 4.6 и .NET Framework 4.6.1 символы классифицировались на основе категорий символов Юникода 6.3.

Поддержка Юникода 8.0 ограничена классификацией символов по классу <xref:System.Globalization.CharUnicodeInfo> и связанными типами и методами. К ним относятся класс <xref:System.Globalization.StringInfo>, перегруженный метод <xref:System.Char.GetUnicodeCategory%2A?displayProperty=nameWithType> и [классы символов](../../standard/base-types/character-classes-in-regular-expressions.md), распознаваемые обработчиком регулярных выражений .NET Framework.  Это изменение не влияет на сравнение и сортировку символов и строк. Они по-прежнему зависят от базовой операционной системы или в системах Windows 7 от символьных данных, предоставляемых .NET Framework.

Сведения об изменениях в категориях символов Юникода 6.0–7.0 см. в статье [The Unicode Standard, Version 7.0.0](https://www.unicode.org/versions/Unicode7.0.0/) на веб-сайте консорциума Юникода. Сведения об изменениях в категориях символов Юникода 7.0–8.0 см. в статье [The Unicode Standard, Version 8.0.0](https://www.unicode.org/versions/Unicode8.0.0/) на веб-сайте Консорциума Юникода.

<a name="Crypto462" />

### <a name="cryptography"></a>Шифрование

**Поддержка сертификатов X509, содержащих FIPS 186-3 DSA**

В .NET Framework 4.6.2 добавлена поддержка сертификатов X509 с алгоритмом DSA, ключи которых превышают 1024-разрядное ограничение FIPS 186-2.

В дополнение к поддержке ключей FIPS 186-3 больших размеров, .NET Framework 4.6.2 позволяет вычислять подписи с использованием семейства алгоритмов хэширования SHA-2 (SHA256, SHA384 и SHA512). Поддержка FIPS 186 3 осуществляется с помощью нового класса <xref:System.Security.Cryptography.DSACng?displayProperty=nameWithType>.

Чтобы обеспечить соответствие последним изменениям в классе <xref:System.Security.Cryptography.RSA> в .NET Framework 4.6 и классе <xref:System.Security.Cryptography.ECDsa> в .NET Framework 4.6.1, абстрактный базовый класс <xref:System.Security.Cryptography.DSA> в .NET Framework 4.6.2 включает дополнительные методы, позволяющие вызывающим сторонам использовать эту функцию без приведения. Можно вызвать метод расширения <xref:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPrivateKey%2A?displayProperty=nameWithType> для подписывания данных, как показано в следующем примере.

```csharp
public static byte[] SignDataDsaSha384(byte[] data, X509Certificate2 cert)
{
    using (DSA dsa = cert.GetDSAPrivateKey())
    {
        return dsa.SignData(data, HashAlgorithmName.SHA384);
    }
}
```

```vb
Public Shared Function SignDataDsaSha384(data As Byte(), cert As X509Certificate2) As Byte()
    Using DSA As DSA = cert.GetDSAPrivateKey()
        Return DSA.SignData(data, HashAlgorithmName.SHA384)
    End Using
End Function
```

Можно также вызвать метод расширения <xref:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPublicKey%2A?displayProperty=nameWithType> для проверки подписанных данных, как показано в следующем примере.

```csharp
public static bool VerifyDataDsaSha384(byte[] data, byte[] signature, X509Certificate2 cert)
{
    using (DSA dsa = cert.GetDSAPublicKey())
    {
        return dsa.VerifyData(data, signature, HashAlgorithmName.SHA384);
    }
}
```

```vb
 Public Shared Function VerifyDataDsaSha384(data As Byte(), signature As Byte(), cert As X509Certificate2) As Boolean
    Using dsa As DSA = cert.GetDSAPublicKey()
        Return dsa.VerifyData(data, signature, HashAlgorithmName.SHA384)
    End Using
End Function
```

**Повышенная четкость входных данных для процедур формирования ключа ECDiffieHellman**

В .NET Framework 3.5 добавлена поддержка соглашения о ключах Диффи — Хелмана на эллиптических кривых с тремя разными процедурами формирования ключа. Входные данные для процедур и сами процедуры настраивались с помощью свойств объекта <xref:System.Security.Cryptography.ECDiffieHellmanCng>. Однако поскольку не все процедуры правильно считывали каждое входное свойство, часто возникала путаница.

В .NET Framework 4.6.2 для решения этой проблемы в базовый класс <xref:System.Security.Cryptography.ECDiffieHellman> были добавлены следующие три метода, предназначенные для более четкого представления этих подпрограмм функций формирования ключа и их входных данных.

|Метод ECDiffieHellman|ОПИСАНИЕ|
|----------------------------|-----------------|
|<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyFromHash%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Security.Cryptography.HashAlgorithmName%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|Получает материал ключа с помощью формулы<br /><br /> HASH(secretPrepend &#124;&#124; *x* &#124;&#124; secretAppend)<br /><br /> HASH(secretPrepend OrElse *x* OrElse secretAppend)<br /><br /> здесь *x* является вычисляемым результатом алгоритма Диффи-Хелмана на эллиптических кривых.|
|<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyFromHmac%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Security.Cryptography.HashAlgorithmName%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|Получает материал ключа с помощью формулы<br /><br /> HMAC(hmacKey, secretPrepend &#124;&#124; *x* &#124;&#124; secretAppend)<br /><br /> HMAC(hmacKey, secretPrepend OrElse *x* OrElse secretAppend)<br /><br /> здесь *x* является вычисляемым результатом алгоритма Диффи-Хелмана на эллиптических кривых.|
|<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyTls%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|Получает материал ключа с помощью алгоритма наследования псевдослучайной функции (PRF) TLS.|

**Поддержка симметричного шифрования с помощью постоянного ключа**

В библиотеку шифрования Windows (CNG) добавлена поддержка хранения постоянных симметричных ключей и использования хранящихся в оборудовании симметричных ключей. Разработчики могут применять эти возможности начиная с версии .NET Framework 4.6.2.  Поскольку понятие имен ключей и поставщиков ключей зависит от реализации, для применения этой функции требуется использовать конструктор конкретных типов реализации, а не предпочтительный метод (например, вызов `Aes.Create`).

Поддержка симметричного шифрования с помощью постоянных ключей доступна для алгоритмов AES (<xref:System.Security.Cryptography.AesCng>) и 3DES (<xref:System.Security.Cryptography.TripleDESCng>). Например:

```csharp
public static byte[] EncryptDataWithPersistedKey(byte[] data, byte[] iv)
{
    using (Aes aes = new AesCng("AesDemoKey", CngProvider.MicrosoftSoftwareKeyStorageProvider))
    {
        aes.IV = iv;

        // Using the zero-argument overload is required to make use of the persisted key
        using (ICryptoTransform encryptor = aes.CreateEncryptor())
        {
            if (!encryptor.CanTransformMultipleBlocks)
            {
                throw new InvalidOperationException("This is a sample, this case wasn’t handled...");
            }

            return encryptor.TransformFinalBlock(data, 0, data.Length);
        }
    }
}
```

```vb
Public Shared Function EncryptDataWithPersistedKey(data As Byte(), iv As Byte()) As Byte()
    Using Aes As Aes = New AesCng("AesDemoKey", CngProvider.MicrosoftSoftwareKeyStorageProvider)
        Aes.IV = iv

        ' Using the zero-argument overload Is required to make use of the persisted key
        Using encryptor As ICryptoTransform = Aes.CreateEncryptor()
            If Not encryptor.CanTransformMultipleBlocks Then
                Throw New InvalidOperationException("This is a sample, this case wasn’t handled...")
            End If
            Return encryptor.TransformFinalBlock(data, 0, data.Length)
        End Using
    End Using
End Function
```

**Поддержка SignedXml для хэширования SHA-2**

В .NET Framework 4.6.2 добавлена поддержка класса <xref:System.Security.Cryptography.Xml.SignedXml> для методов подписи RSA-SHA256, RSA-SHA384 и RSA-SHA512 PKCS#1 и алгоритмов выборки SHA256, SHA384 и SHA512.

Константы URI представлены в <xref:System.Security.Cryptography.Xml.SignedXml>:

|Поле SignedXml|Константа|
|---------------------|--------------|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA256Url>|"http://www.w3.org/2001/04/xmlenc#sha256"|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA256Url>|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha256"|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA384Url>|"http://www.w3.org/2001/04/xmldsig-more#sha384"|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA384Url>|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha384"|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA512Url>|"http://www.w3.org/2001/04/xmlenc#sha512"|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA512Url>|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha512"|

 Программы, которые зарегистрировали пользовательский обработчик <xref:System.Security.Cryptography.SignatureDescription> в <xref:System.Security.Cryptography.CryptoConfig> для дополнительной поддержки этих алгоритмов, будут работать, как и раньше, однако поскольку теперь существуют платформы по умолчанию, регистрировать <xref:System.Security.Cryptography.CryptoConfig> больше не требуется.

<a name="SQLClient" />

### <a name="sqlclient"></a>SqlClient

Поставщик данных .NET Framework для SQL Server (<xref:System.Data.SqlClient?displayProperty=nameWithType>) предлагает следующие новые возможности в .NET Framework 4.6.2.

**Объединение подключений в пул и использование времени ожидания в базах данных SQL Azure**

Если включено объединение подключений в пул и наступает время ожидания или возникает другая ошибка входа, происходит кэширование исключения. При последующих попытках подключения для следующих 5 секунд на 1 минуту создается кэшированное исключение.  Дополнительные сведения см. в разделе [Объединение подключений в пул (ADO.NET)](../data/adonet/sql-server-connection-pooling.md).

Это поведение является нежелательным при подключении к базам данных SQL Azure, поскольку попытки соединения могут завершиться временными ошибками, которые обычно быстро исправляются. В целях максимальной оптимизации процедуры повторных попыток подключения поведение периода блокировки пула подключений удаляется при сбое соединений с базами данных SQL Azure.

За счет добавленного нового ключевого слова `PoolBlockingPeriod` вы можете выбирать период времени блокировки, лучше всего подходящий для вашего приложения. К этим значениям относятся следующие.

<xref:System.Data.SqlClient.PoolBlockingPeriod.Auto>

Период блокировки пула подключений для приложения, которое подключается к базе данных SQL Azure, отключается, а период блокировки пула подключений для приложения, которое подключается к другому экземпляру SQL Server, включается. Это значение по умолчанию. Если имя конечной точки сервера заканчивается любой из приведенных ниже строк, она считается базой данных SQL Azure.

- .database.windows.net

- .database.chinacloudapi.cn

- .database.usgovcloudapi.net

- .database.cloudapi.de

<xref:System.Data.SqlClient.PoolBlockingPeriod.AlwaysBlock>

Период блокировки пула подключений всегда включен.

<xref:System.Data.SqlClient.PoolBlockingPeriod.NeverBlock>

Период блокировки пула подключений всегда отключен.

**Усовершенствования функции Always Encrypted**

В SQLClient представлены два усовершенствования для функции Always Encrypted.

- Для повышения производительности параметризованных запросов к зашифрованным столбцам базы данных выполняется кэширование метаданных шифрования для параметров запроса. Если свойству <xref:System.Data.SqlClient.SqlConnection.ColumnEncryptionQueryMetadataCacheEnabled%2A?displayProperty=nameWithType> задано значение `true` (это значение по умолчанию) и один и тот же запрос вызывается несколько раз, клиент получает метаданные параметров с сервера только один раз.

- Теперь записи ключей шифрования столбцов в кэше ключа вытесняются по истечении интервала времени, настроенного с помощью свойства <xref:System.Data.SqlClient.SqlConnection.ColumnEncryptionKeyCacheTtl%2A?displayProperty=nameWithType>.

<a name="WCF" />

### <a name="windows-communication-foundation"></a>Windows Communication Foundation

В.NET Framework 4.6.2 Windows Communication Foundation получила ряд улучшений в следующих областях.

**Поддержка безопасности транспорта WCF для сертификатов, сохраненных с помощью CNG**

Безопасность транспорта WCF поддерживает сертификаты, сохраненные с использованием библиотеки шифрования Windows (CNG). В .NET Framework 4.6.2 эта поддержка ограничивается использованием сертификатов с открытым ключом, длина экспоненты которого не превышает 32 бита. Если приложение предназначено для .NET Framework 4.6.2, эта функция включена по умолчанию.

Для приложений, которые предназначены для .NET Framework 4.6.1 и более ранних версий, но работают в .NET Framework 4.6.2, эту функцию можно включить отдельно, добавив указанную ниже строку в раздел [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) файла app.config или web.config.

```xml
<AppContextSwitchOverrides
    value="Switch.System.ServiceModel.DisableCngCertificates=false"
/>
```

Это также можно сделать программно с помощью следующего кода:

```csharp
private const string DisableCngCertificates = @"Switch.System.ServiceModel.DisableCngCertificates";
AppContext.SetSwitch(disableCngCertificates, false);
```

```vb
Const DisableCngCertificates As String = "Switch.System.ServiceModel.DisableCngCertificates"
AppContext.SetSwitch(disableCngCertificates, False)
```

**Улучшенная поддержка нескольких правил коррекции летнего времени с помощью класса DataContractJsonSerializer**

Клиенты могут использовать параметр конфигурации приложения для определения того, поддерживает ли класс <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> несколько правил коррекции для одного часового пояса. Это функция, включаемая пользователем. Чтобы ее включить, добавьте следующий параметр в файл app.config:

```xml
<runtime>
     <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseTimeZoneInfo=false" />
</runtime>
```

Если эта возможность включена, объект <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> использует тип <xref:System.TimeZoneInfo> вместо типа <xref:System.TimeZone> для десериализации данных даты и времени. <xref:System.TimeZoneInfo> поддерживает несколько правил коррекции, что позволяет работать с историческими данными часового пояса, а <xref:System.TimeZone> — не поддерживает.

Дополнительные сведения о структуре <xref:System.TimeZoneInfo> и коррекциях часового пояса см. в статье [Общие сведения о часовых поясах](../../standard/datetime/time-zone-overview.md).

**Наилучшее соответствие NetNamedPipeBinding**

В WCF представлен новый параметр приложения, который может быть задан в клиентских приложениях для их постоянного подключения к службе, прослушивающей URI, наилучшим образом соответствующий запрошенному. Если этот параметр приложения имеет значение `false` (по умолчанию), клиенты могут использовать <xref:System.ServiceModel.NetNamedPipeBinding> для подключения к службе, прослушивающей URI, который является подстрокой запрошенного URI.

Например, клиент пытается подключиться к службе, прослушивающей `net.pipe://localhost/Service1`, но другая служба на этом компьютере, запущенная с правами администратора, прослушивает `net.pipe://localhost`. Если этому параметру приложения задать значение `false`, клиент будет пытаться подключиться не к той службе. После установки значения `true` для параметра приложения клиент будет всегда подключаться к наиболее подходящей службе.

> [!NOTE]
> Клиенты, использующие <xref:System.ServiceModel.NetNamedPipeBinding>, находят службы на основе их базового адреса (если он существует), а не на основе полного адреса конечной точки. Чтобы обеспечить постоянную работу этого параметра, служба должна использовать уникальный базовый адрес.

Для активации этого изменения добавьте следующий параметр в файл App.config или Web.config клиентского приложения:

```xml
<configuration>
    <appSettings>
        <add key="wcf:useBestMatchNamedPipeUri" value="true" />
    </appSettings>
</configuration>
```

**SSL 3.0 не является протоколом по умолчанию**

При использовании NetTcp для обеспечения безопасности транспорта и применении типа учетных данных сертификата SSL 3.0 больше не является протоколом по умолчанию для согласования безопасного соединения. В большинстве случаев существующие приложения не должны затрагиваться, поскольку TLS 1.0 входит в список протоколов для NetTcp. Все существующие клиенты должны иметь возможность согласовывать подключение с помощью хотя бы TLS 1.0. Если требуется Ssl3, воспользуйтесь одним из указанных ниже механизмов конфигурации и добавьте его в список установленных протоколов.

- Свойство <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols%2A?displayProperty=nameWithType>.

- Свойство <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=nameWithType>.

- Раздел [\<transport>](../configure-apps/file-schema/wcf/transport-of-nettcpbinding.md) раздела [\<netTcpBinding>](../configure-apps/file-schema/wcf/nettcpbinding.md)

- Раздел [\<sslStreamSecurity>](../configure-apps/file-schema/wcf/sslstreamsecurity.md) раздела [\<customBinding>](../configure-apps/file-schema/wcf/custombinding.md)

<a name="WPF462" />

### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

В.NET Framework 4.6.2 Windows Presentation Foundation получила ряд улучшений в следующих областях.

**Сортировка групп**

Приложение, использующее объект <xref:System.Windows.Data.CollectionView> для группирования данных, теперь может явно объявлять порядок сортировки групп. Явная сортировка позволяет решить проблему неочевидного упорядочивания, которая возникает, когда приложение динамически добавляет или удаляет группы или когда оно изменяет значения свойств элементов, участвующих в группировании. Она также может повысить производительность процесса создания группы путем перемещения сравнений свойств группирования из сортировки полной коллекции в сортировку групп.

Для поддержки сортировки групп новые свойства <xref:System.ComponentModel.GroupDescription.SortDescriptions%2A?displayProperty=nameWithType> и <xref:System.ComponentModel.GroupDescription.CustomSort%2A?displayProperty=nameWithType> описывают способ сортировки коллекции групп, созданной объектом <xref:System.ComponentModel.GroupDescription>. Эта процедура аналогична способу, которым свойства <xref:System.Windows.Data.ListCollectionView> с аналогичными именами описывают принцип сортировки элементов данных.

В наиболее распространенных случаях можно использовать два новых статических свойства класса <xref:System.Windows.Data.PropertyGroupDescription> — <xref:System.Windows.Data.PropertyGroupDescription.CompareNameAscending%2A> и <xref:System.Windows.Data.PropertyGroupDescription.CompareNameDescending%2A>.

Например, следующий XAML группирует данные по возрасту, сортирует возрастные группы в порядке возрастания и группирует элементы в каждой возрастной группе по фамилии.

```xaml
<GroupDescriptions>
     <PropertyGroupDescription
         PropertyName="Age"
         CustomSort=
              "{x:Static PropertyGroupDescription.CompareNamesAscending}"/>
     </PropertyGroupDescription>
</GroupDescriptions>

<SortDescriptions>
     <SortDescription PropertyName="LastName"/>
</SortDescriptions>
```

**Поддержка программируемой клавиатуры**

Поддержка программируемой клавиатуры позволяет отслеживать фокус в приложениях WPF путем автоматического вызова и отклонения новой программируемой клавиатуры в Windows 10 при получении элементом управления, который может принимать текстовые входные данные, сигнала о сенсорном вводе.

В предыдущих версиях платформы .NET Framework приложения WPF не использовали отслеживание фокуса без отключения поддержки пера и сенсорного ввода WPF.  В результате приложения WPF должны выбрать между полной поддержкой сенсорного ввода WPF или использованием мыши Windows.

**DPI для каждого монитора**

Для поддержки современных сред с высоким и смешанным разрешением платформа WPF в .NET Framework 4.6.2 включает для приложений WPF поддержку DPI для каждого монитора. Дополнительные сведения о включении в приложении WPF поддержки DPI для каждого монитора см. в [примерах и в руководстве разработчика](https://github.com/Microsoft/WPF-Samples/tree/master/PerMonitorDPI) на сайте GitHub.

В предыдущих версиях платформы .NET Framework приложения WPF поддерживают DPI на уровне системы. Другими словами, ОС соответствующим образом масштабирует пользовательский интерфейс приложения в зависимости от разрешения экрана монитора, на котором отображается приложение.

Для приложений, работающих под управлением .NET Framework 4.6.2, можно отключить изменения DPI для каждого монитора в приложениях WPF, добавив соответствующую инструкцию в раздел [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения, как показано ниже.

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.Windows.DoNotScaleForDpiChanges=false"/>
</runtime>
```

<a name="WF462" />

### <a name="windows-workflow-foundation-wf"></a>Windows Workflow Foundation (WF)

В .NET Framework 4.6.2 Windows Workflow Foundation содержит ряд улучшений в следующих областях.

**Поддержка выражений C# и IntelliSense в повторно размещаемом конструкторе WF**

Начиная с .NET Framework 4.5 WF поддерживает выражения C# в конструкторе Visual Studio и рабочих процессах кода. Повторно размещаемый конструктор рабочих процессов является ключевой возможностью WF, позволяющей размещать конструкторы рабочих процессов в приложении вне среды Visual Studio (например, в WPF).  Windows Workflow Foundation поддерживает выражения C# и IntelliSense в повторно размещаемом конструкторе рабочих процессов. Дополнительные сведения см. в [блоге по Windows Workflow Foundation](https://go.microsoft.com/fwlink/?LinkID=809042&clcid=0x409).

`Availability of IntelliSense when a customer rebuilds a workflow project from Visual Studio` В версиях .NET Framework до версии 4.6.2 в случае перестроения проекта рабочего процесса из Visual Studio происходит нарушение работы IntelliSense конструктора WF. Несмотря на успешное построение проекта, типы рабочих процессов отсутствуют в конструкторе, и в окне **Список ошибок** отображаются предупреждения из IntelliSense о недостающих типах рабочего процесса. В .NET Framework 4.6.2 эта проблема решена и IntelliSense работает.

**Приложения Workflow версии 1 с функцией отслеживания рабочего процесса теперь работают в режиме FIPS**

Теперь на компьютерах с включенным режимом поддержки стандарта FIPS можно успешно запускать приложение Workflow версии 1 с функцией отслеживания рабочих процессов. Чтобы реализовать этот сценарий, необходимо внести следующее изменение в файл app.config:

```xml
<add key="microsoft:WorkflowRuntime:FIPSRequired" value="true" />
```

Если этот сценарий не реализован, запущенное приложение продолжает создавать исключение с сообщением "Данная реализация не является частью протестированных криптографических алгоритмов Windows Platform FIPS".

**Усовершенствования рабочего процесса при использовании динамического обновления с конструктором рабочих процессов Visual Studio**

Теперь конструктор рабочих процессов, конструктор действия FlowChart и другие конструкторы действий успешно загружают и отображают рабочие процессы, которые были сохранены после вызова метода <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType>. В версиях .NET Framework, предшествующих .NET Framework 4.6.2, загрузка XAML-файла в Visual Studio для рабочего процесса, который был сохранен после вызова метода <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType>, может вызвать следующие проблемы:

- Конструктор рабочих процессов не может правильно загрузить XAML-файл (если <xref:System.Activities.Presentation.ViewState.ViewStateData.Id%2A?displayProperty=nameWithType> находится в конце строки).

- Конструктор действия FlowChart или другие конструкторы действий рабочих процессов могут отображать все объекты в их расположениях по умолчанию в отличие от значений вложенных свойств.

<a name="clickonce-1" />

### <a name="clickonce"></a>ClickOnce

Технология ClickOnce была обновлена для поддержки протоколов TLS 1.1 и TLS 1.2 наряду с уже поддерживаемой версией 1.0. ClickOnce автоматически определяет необходимый протокол. Для включения поддержки протоколов TLS 1.1 и 1.2 в приложении ClickOnce не требуется выполнять дополнительные действия.

<a name="UWPConvert" />

### <a name="converting-windows-forms-and-wpf-apps-to--uwp-apps"></a>Преобразование приложений Windows Forms и приложений WPF в приложения UWP

Теперь Windows предоставляет возможности переноса существующих классических приложений Windows, включая приложения WPF и Windows Forms, на универсальную платформу Windows (UWP). Эта технология играет роль моста, позволяя постепенно переносить существующую базу кода на платформу UWP, переводя, тем самым, приложения на все устройства Windows 10.

Преобразованное классическое приложение получает удостоверение, аналогичное удостоверению приложения платформы UWP, которое делает доступными интерфейсы API UWP для включения функций, таких как динамические плитки и уведомления. Приложение продолжает работать как раньше и функционирует как приложение полного доверия. После преобразования приложения к существующему процессу полного доверия можно добавить процесс контейнера приложения для подключения адаптивного пользовательского интерфейса. При перемещении всех функциональных возможностей в процесс контейнера приложения можно удалить процесс полного доверия и сделать новое приложение UWP доступным для всех устройств Windows 10.

<a name="Debug462" />

### <a name="debugging-improvements"></a>Усовершенствования отладки

*API неуправляемой отладки* был усовершенствован в .NET Framework 4.6.2 для выполнения дополнительного анализа при возникновении <xref:System.NullReferenceException>, чтобы определить, какая переменная в одной строке исходного кода является `null`.   Для поддержки этого сценария в неуправляемый API отладки были добавлены следующие API.

- Интерфейсы [ICorDebugCode4](../unmanaged-api/debugging/icordebugcode4-interface.md), [ICorDebugVariableHome](../unmanaged-api/debugging/icordebugvariablehome-interface.md) и [ICorDebugVariableHomeEnum](../unmanaged-api/debugging/icordebugvariablehomeenum-interface.md), предоставляющие собственные начальные расположения управляемых переменных. Это позволяет отладчикам выполнять анализ потока кода при возникновении <xref:System.NullReferenceException> и работать в обратном порядке для определения управляемой переменной, соответствующей собственному расположению, которым был `null`.

- Метод [ICorDebugType2::GetTypeID](../unmanaged-api/debugging/icordebugtype2-gettypeid-method.md) обеспечивает сопоставление ICorDebugType с [COR_TYPEID](../unmanaged-api/debugging/cor-typeid-structure.md), что позволяет отладчику получить [COR_TYPEID](../unmanaged-api/debugging/cor-typeid-structure.md) без экземпляра ICorDebugType. Существующие API в [COR_TYPEID](../unmanaged-api/debugging/cor-typeid-structure.md) можно использовать для определения макета класса типа.

<a name="v461" />

## <a name="whats-new-in-net-framework-461"></a>Новые возможности .NET Framework 4.6.1

Версия .NET Framework 4.6.1 включает новые функции в следующих областях:

- [Шифрование](#Crypto)

- [ADO.NET](#ADO.NET461)

- [Windows Presentation Foundation (WPF)](#WPF461)

- [Windows Workflow Foundation](#WWF461)

- [Профилирование](#Profile461)

- [NGen](#NGEN461)

Дополнительные сведения о версии .NET Framework 4.6.1 приведены в следующих статьях:

- [Список изменений в .NET Framework 4.6.1](https://go.microsoft.com/fwlink/?LinkId=622964)

- [Совместимость приложений в 4.6.1](../migration-guide/application-compatibility.md)

- [Различия между API .NET Framework](https://go.microsoft.com/fwlink/?LinkId=622989) (GitHub)

<a name="Crypto" />

### <a name="cryptography-support-for-x509-certificates-containing-ecdsa"></a>Криптография: Поддержка сертификатов X509, содержащих ECDSA

В .NET Framework 4.6 добавлена поддержка RSACng сертификатов X509. В .NET Framework 4.6.1 добавлена поддержка сертификатов X509 с алгоритмом ECDSA (цифровых подписей на основе эллиптических кривых).

ECDSA обеспечивает более высокую производительность и является более безопасным алгоритмом шифрования, чем RSA, предоставляя лучший выбор, когда производительность и масштабируемость TLS представляет собой проблему. Реализация .NET Framework создает оболочку для вызовов существующих функциональных возможностей Windows.

В следующем примере кода показано, как легко создать подпись для байтового потока, используя новую поддержку сертификатов X 509 ECDSA, включенную в .NET Framework 4.6.1.

[!code-csharp[whatsnew.461.crypto#1](~/samples/snippets/csharp/VS_Snippets_CLR/whatsnew.461.crypto/cs/Code46.cs#1)]
[!code-vb[whatsnew.461.crypto#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.461.crypto/vb/Code461.vb#1)]

Это обеспечивает заметное отличие от кода, необходимого для создания подписи в .NET Framework 4.6.

[!code-csharp[whatsnew.461.crypto#2](~/samples/snippets/csharp/VS_Snippets_CLR/whatsnew.461.crypto/cs/Code46.cs#2)]
[!code-vb[whatsnew.461.crypto#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.461.crypto/vb/Code46.vb#2)]

<a name="ADO.NET461" />

### <a name="adonet"></a>ADO.NET

В ADO.NET добавлены следующие возможности.

**Поддержка Always Encrypted (постоянного шифрования) для аппаратно защищенных ключей**

Теперь ADO.NET поддерживает хранение главных ключей столбца Always Encrypted непосредственно в аппаратных модулях безопасности (HSM). Благодаря этому клиенты могут использовать асимметричные ключи, хранящиеся в аппаратных модулях безопасности, без необходимости написания специальных поставщиков хранилища главных ключей и их регистрации в приложениях.

Для доступа к постоянно зашифрованным данным, защищенным с помощью главных ключей столбца, хранящихся в аппаратном модуле безопасности, клиенты должны установить на серверах приложений или клиентских компьютерах предоставленный производителем аппаратного модуля безопасности поставщик служб шифрования или поставщики хранилища ключей CNG.

**Улучшенное поведение при подключении <xref:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover%2A> для AlwaysOn**

SqlClient теперь автоматически обеспечивает более быстрое подключение к группе доступности (AG) AlwaysOn. Он прозрачно определяет, подключается ли ваше приложение к группе доступности AlwaysOn в другой подсети, и быстро обнаруживает текущий активный сервер и обеспечивает подключение к этому серверу. В предыдущих версиях строка подключения приложения должна была включать `"MultisubnetFailover=true"` для указания, что это приложение подключается к группе доступности AlwaysOn. При подключении приложения к группе доступности AlwaysOn без установки значения `true` для этого ключевого слова подключения время ожидания может быть превышено. В этом выпуске больше *не* требуется, чтобы приложение устанавливало <xref:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover%2A> в значение `true`. Дополнительные сведения о поддержке SqlClient для групп доступности Always On см. в разделе [Поддержка SqlClient для высокого уровня доступности и аварийного восстановления](../data/adonet/sql/sqlclient-support-for-high-availability-disaster-recovery.md).

<a name="WPF461" />

### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

Windows Presentation Foundation содержит ряд улучшений и изменений.

**Улучшена производительность**

В .NET Framework 4.6.1 была исправлена задержка при срабатывании событий касания. Кроме того, ввод в элементе управления <xref:System.Windows.Controls.RichTextBox> больше не препятствует обрабатывающему потоку при быстром вводе данных.

**Улучшения проверки орфографии**

В Windows 8.1 и последующих версиях проверка орфографии в WPF была обновлена, чтобы для проверки орфографии в дополнительных языках использовалась поддержка операционной системы.  В версиях Windows, предшествующих Windows 8.1, изменения этой функциональности отсутствуют.

Как и в предыдущих версиях .NET Framework, язык для блока <xref:System.Windows.Controls.RichTextBox> элемента управления <xref:System.Windows.Controls.TextBox> определяется путем поиска информации в следующем порядке:

- `xml:lang`, если имеется;

- текущий язык ввода;

- язык и региональные параметры текущего потока.

Дополнительные сведения о языковой поддержке в WPF см. в [публикации в блоге WPF, посвященной компонентам .NET Framework 4.6.1](https://go.microsoft.com/fwlink/?LinkID=691819).

**Дополнительная поддержка индивидуально настраиваемых словарей**

В .NET Framework 4.6.1 WPF распознает настраиваемые словари, зарегистрированные глобально. Эта возможность доступна наряду с возможностью их регистрации на уровне элемента управления.

В предыдущих версиях WPF настраиваемые словари не распознавали исключенные слова и списки автозамены. Эти возможности поддерживаются в Windows 8.1 и Windows 10 благодаря использованию файлов, которые могут быть помещены в каталог `%AppData%\Microsoft\Spelling\<language tag>`.  К этим файлам применяются следующие правила.

- Файлы должны иметь расширения DIC (для добавленных слов), EXC (для исключенных слов) или ACL (для автозамены).

- Файлы должны представлять собой открытый текст в кодировке UTF-16 LE, который начинается с метки порядка байтов (BOM).

- Каждая строка должна состоять из слова (в списках добавленных или исключенных слов) или пары автозамены, в которой слова разделены вертикальной чертой ("&#124;") (в списке автозамены).

- Эти файлы считаются доступными только для чтения и не изменяются системой.

> [!NOTE]
> Эти новые форматы файлов не поддерживаются непосредственно API-интерфейсами проверки орфографии WPF, и настраиваемые словари, передаваемые в WPF в приложениях, должны продолжать использовать LEX-файлы.

**Примеры**

Ряд примеров для WPF доступен в GitHub-репозитории [Microsoft/WPF-Samples](https://github.com/Microsoft/WPF-Samples). Помогите нам улучшить наши примеры, отправив нам запрос на включение внесенных изменений или открыв [вопрос GitHub](https://github.com/Microsoft/WPF-Samples/issues).

**Расширения DirectX**

WPF включает [пакет NuGet](https://go.microsoft.com/fwlink/?LinkID=691342), предоставляющий новые реализации <xref:System.Windows.Interop.D3DImage>, которые упрощают взаимодействие с содержимым DX10 и Dx11. Код для этого пакета открыт и доступен [на GitHub](https://github.com/Microsoft/WPFDXInterop).

<a name="WWF461" />

### <a name="windows-workflow-foundation-transactions"></a>Windows Workflow Foundation: Транзакции

Метод <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A?displayProperty=nameWithType> теперь может использовать для повышения уровня транзакции диспетчер распределенных транзакций, отличный от MSDTC. Это делается путем указания идентификатора GUID диспетчера транзакций в новую перегрузку <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%28System.Transactions.IPromotableSinglePhaseNotification%2CSystem.Guid%29?displayProperty=nameWithType>. В случае успешного выполнения операции на возможности транзакции накладываются определенные ограничения. После прикрепления отличного от MSDTC диспетчера транзакций следующие методы вызывают исключение <xref:System.Transactions.TransactionPromotionException>, так как эти методы требуют повышения до MSDTC.

- <xref:System.Transactions.Transaction.EnlistDurable%2A?displayProperty=nameWithType>

- <xref:System.Transactions.TransactionInterop.GetDtcTransaction%2A?displayProperty=nameWithType>

- <xref:System.Transactions.TransactionInterop.GetExportCookie%2A?displayProperty=nameWithType>

- <xref:System.Transactions.TransactionInterop.GetTransmitterPropagationToken%2A?displayProperty=nameWithType>

После прикрепления отличного от MSDTC диспетчера транзакций он должен использоваться для будущих долговременных прикреплений с использованием протоколов, которые он задает. Идентификатор <xref:System.Guid> диспетчера транзакций можно получить с помощью свойства <xref:System.Transactions.Transaction.PromoterType%2A>. Когда выполняется повышение уровня транзакции, диспетчер транзакций предоставляет массив <xref:System.Byte>, представляющий токен повышенного уровня. Приложение может получить этот токен повышенного уровня для транзакции, уровень которой повышается отличным от MSDTC диспетчером транзакций, с помощью метода <xref:System.Transactions.Transaction.GetPromotedToken%2A>.

Пользователи новой перегрузки <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%28System.Transactions.IPromotableSinglePhaseNotification%2CSystem.Guid%29?displayProperty=nameWithType> должны придерживаться определенной последовательности вызовов для успешного завершения операции повышения уровня. Эти правила описаны в документации по данному методу.

<a name="Profile461" />

### <a name="profiling"></a>Профилирование

В API-интерфейс неуправляемого профилирования внесены следующие изменения.

- Улучшена поддержка доступа к PDB-файлам в интерфейсе [ICorProfilerInfo7](../unmanaged-api/profiling/icorprofilerinfo7-interface.md).

  В ASP.NET Core сборки все чаще компилируются в памяти с использованием Roslyn. Для разработчиков средств профилирования это означает, что PDB-файлы, которые ранее были сериализованы на диске, могут больше не присутствовать. Средства профилирования часто используют PDB-файлы для сопоставления кода с исходными строками для таких задач, как анализ покрытия кода или построковый анализ производительности. Интерфейс [ICorProfilerInfo7](../unmanaged-api/profiling/icorprofilerinfo7-interface.md) теперь включает два новых метода, [ICorProfilerInfo7::GetInMemorySymbolsLength](../unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md) и [ICorProfilerInfo7::ReadInMemorySymbols](../unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md), для предоставления этим средствам профилирования доступа к данным PDB-файлов в памяти. С помощью новых API профилировщик может получить содержимое PDB-файлов в памяти в виде массива байтов, а затем обработать его или сериализовать на диск.

- Улучшено инструментирование с использованием интерфейса ICorProfiler.

  Профилировщики, использующие функциональность ReJit API `ICorProfiler` для динамического инструментирования, теперь могут изменять некоторые метаданные. Ранее такие средства могли инструментировать IL в любое время, но метаданные могли изменяться только во время загрузки модуля. Поскольку IL ссылается на метаданные, это ограничивает типы инструментирования, которое может выполняться. Мы отменили некоторые из этих ограничений, добавив метод [ICorProfilerInfo7::ApplyMetaData](../unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md) для поддержки подмножества правок метаданных после загрузки модуля, в частности путем добавления новых записей `AssemblyRef`, `TypeRef`, `TypeSpec`, `MemberRef`, `MemberSpec` и `UserString`. Это изменение существенно расширяет спектр возможного динамического инструментирования.

<a name="NGEN461" />

### <a name="native-image-generator-ngen-pdbs"></a>PDB-файлы генератора образов в машинном коде (NGEN)

Трассировка событий между компьютерами позволяет клиентам профилировать программу на компьютере А и просматривать данные профилирования с сопоставлением исходных строк на компьютере Б. Используя предыдущие версии .NET Framework, пользователь может копировать все модули и образы в машинном коде из профилируемого компьютера на компьютер анализа, содержащий PDB-файл IL, для создания сопоставления "источник-машинный код". Хотя этот процесс может хорошо работать в том случае, если файлы относительно невелики, например для телефонных приложений, на настольных системах эти файлы могут быть очень большими, и на их копирование потребуется значительное время.

С помощью PDB-файлов Ngen NGen может создать PDB-файл, содержащий сопоставления "IL-машинный код" без зависимости от PDB-файла IL. В нашем сценарии трассировки событий между компьютерами все, что требуется, — это скопировать PDB-файл образа в машинном коде, созданный на компьютере А, на компьютер Б, а затем использовать [API доступа к интерфейсу отладки](/visualstudio/debugger/debug-interface-access/debug-interface-access-sdk-reference) для чтения сопоставления "машинный код-IL" PDB-файла IL и сопоставления "IL-машинный код" PDB-файла образа в машинном коде. Объединение обоих сопоставлений обеспечивает сопоставление "источник-машинный код". Поскольку PDB-файл образа в машинном коде PDB намного меньше, чем все модули и образы в машинном коде, процесс копирования с компьютера А на компьютер Б выполняется гораздо быстрее.

<a name="v46" />

## <a name="whats-new-in-net-2015"></a>Новые возможности .NET 2015

.NET 2015 включает .NET Framework 4.6 и .NET Core. Некоторые функции применяются к обеим версиям, а некоторые только к .NET Framework 4.6 или .NET Core.

- **ASP.NET Core**

  .NET 2015 включает ASP.NET Core — экономичную реализацию .NET для создания современных облачных приложений. Платформа ASP.NET Core является модульной, поэтому вы можете включить только те функции, которые нужны в вашем приложении. Она может быть размещена в IIS или резидентно в пользовательском процессе, и вы можете запустить приложения с разными версиями .NET Framework на одном сервере. В нее входит новая система конфигурации среды, предназначенная для развертывания облака.

  MVC, веб-API и веб-страницы объединены в одну платформу, которая называется MVC 6. Сборка приложений ASP.NET Core выполняется с помощью инструментов Visual Studio 2015 или более поздних версий. Уже существующие приложения будут работать на новой платформе .NET Framework, однако для сборки приложения, использующего MVC 6 или SignalR 3, необходима система проектов Visual Studio 2015 и последующих выпусков.

  См. дополнительные сведения об [ASP.NET Core](/aspnet/core/).

- **Обновления ASP.NET**

  - **API на основе задач для асинхронной очистки ответов**

    ASP.NET теперь предоставляет простой API на основе задач для асинхронной очистки ответов, <xref:System.Web.HttpResponse.FlushAsync%2A?displayProperty=nameWithType>, который позволяет асинхронно сбрасывать ответы, используя поддержку операторов `async/await` языка программирования.

  - **Привязка модели поддерживает методы, возвращающие задачи**

    В версии .NET Framework 4.5 в ASP.NET добавлена функция привязки модели, которая обеспечивает расширяемый, ориентированный на код подход к операциям с данными CRUD на страницах веб-форм и пользовательских элементов управления. Система привязки модели теперь поддерживает возвращающие <xref:System.Threading.Tasks.Task> методы привязки модели. Эта функция позволяет разработчикам веб-форм сочетать преимущества масштабируемости асинхронного программирования с простотой системы привязки данных при использовании более новых версий моделей ORM, включая Entity Framework.

    Асинхронная привязка модели управляется параметром конфигурации `aspnet:EnableAsyncModelBinding`.

    ```xml
    <appSettings>
        <add key=" aspnet:EnableAsyncModelBinding" value="true|false" />
    </appSettings>
    ```

    Для приложений, предназначенных для .NET Framework 4.6, по умолчанию используется значение `true`. Для приложений, выполняющихся в .NET Framework 4.6, но предназначенных для более ранних версий .NET Framework, по умолчанию используется значение `false`. Включить этот режим можно, задав для параметра конфигурации значение `true`.

  - **Поддержка HTTP/2 (Windows 10)**

    [HTTP/2](https://www.wikipedia.org/wiki/HTTP/2) — это новая версия протокола HTTP, которая обеспечивает более эффективное подключение (меньшее число круговых путей между клиентом и сервером) и уменьшение задержки при загрузке веб-страницы для пользователей.  HTTP/2 обеспечивает максимальное преимущество для веб-страниц (по сравнению со службами), так как оптимизирует запрос различных артефактов в ходе одной операции. В .NET Framework 4.6 добавлена поддержка HTTP/2 в ASP.NET. Так как сетевые функции существуют на нескольких уровнях, для новых компонентов в Windows, IIS и ASP.NET потребовалось включить HTTP/2. Для использования HTTP/2 с ASP.NET приложение должно выполняться в Windows 10.

    Протокол HTTP/2 также поддерживается и включен по умолчанию для приложений универсальной платформы Windows (UWP) для Windows 10, использующих API <xref:System.Net.Http.HttpClient?displayProperty=nameWithType>.

    Чтобы обеспечить способ использования компонента [PUSH_PROMISE](https://http2.github.io/http2-spec/#PUSH_PROMISE) в приложениях ASP.NET, в класс <xref:System.Web.HttpResponse> добавлен новый метод с двумя перегрузками, <xref:System.Web.HttpResponse.PushPromise%28System.String%29> и <xref:System.Web.HttpResponse.PushPromise%28System.String%2CSystem.String%2CSystem.Collections.Specialized.NameValueCollection%29>.

    > [!NOTE]
    > Хотя ASP.NET Core поддерживает HTTP/2, поддержка функции PUSH PROMISE пока не добавлена.

    Всю работу выполняют браузер и веб-сервер (IIS в Windows). Нет необходимости перекладывать нагрузку на пользователей.

    Большинство [основных браузеров поддерживает HTTP/2](https://www.wikipedia.org/wiki/HTTP/2), поэтому вполне вероятно, что пользователи смогут воспользоваться преимуществами протокола HTTP/2, если его поддерживает ваш сервер.

  - **Поддержка протокола привязки токенов**

    Корпорация Майкрософт и Google совместно работают над созданием нового подхода к проверке подлинности, называемого протоколом привязки токенов, или [Token Binding Protocol](https://github.com/TokenBinding/Internet-Drafts). Предполагается, что токены проверки подлинности (в кэше браузера) могут быть украдены и использованы злоумышленниками для получения доступа к защищенным в иных обстоятельствах ресурсам (например, к вашему банковскому счету) без помощи пароля или других конфиденциальных сведений. Новый протокол предназначен для устранения этой проблемы.

    Протокол привязки токенов будет реализован в Windows 10 в качестве компонента браузера. Приложения ASP.NET будут участвовать в протоколе для подтверждения действительности токенов проверки подлинности. Реализации клиента и сервера будут обеспечивать комплексную защиту, заданную этим протоколом.

  - **Алгоритм случайного хэширования строк**

    В .NET Framework 4.5 добавлен [алгоритм случайного хэширования строк](../configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md). Однако он не поддерживается ASP.NET, так как некоторые компоненты ASP.NET зависят от стабильного хэш-кода. В .NET Framework 4.6 теперь поддерживаются алгоритмы случайного хэширования строк. Чтобы включить эту функцию, используйте параметр конфигурации `aspnet:UseRandomizedStringHashAlgorithm`.

    ```xml
    <appSettings>
        <add key="aspnet:UseRandomizedStringHashAlgorithm" value="true|false" />
    </appSettings>
    ```

- **ADO.NET**

  ADO .NET теперь поддерживает функцию «Всегда зашифровано», которая доступна в CTP-версии 2 SQL Server 2016. Благодаря функции «Всегда зашифровано» SQL Server может выполнять операции с зашифрованными данными, и, что важнее всего, ключ шифрования хранится в самом приложении в доверенной среде клиента, а не на сервере. Функция «Всегда зашифровано» защищает данные клиента, поэтому администраторы базы данных не имеют доступа к данным в формате обычного текста. Шифрование и расшифровка данных происходит прозрачно на уровне драйвера, что сводит к минимуму изменения, которые должны быть выполнены для существующих приложений. Дополнительные сведения см. в разделах [Always Encrypted (ядро СУБД)](/sql/relational-databases/security/encryption/always-encrypted-database-engine) и [Постоянное шифрование (разработка клиентских приложений)](/sql/relational-databases/security/encryption/always-encrypted-client-development).

- **64-разрядный компилятор JIT для управляемого кода**

  В .NET Framework 4.6 представлена новая версия 64-разрядного JIT-компилятора (исходное кодовое имя — RyuJIT). Новый 64-разрядный компилятор имеет значительно большую производительность, чем предыдущий 64-разрядный JIT-компилятор. Новый 64-разрядный компилятор включен для 64-разрядных процессов, выполняющихся на основе .NET Framework 4.6. Приложение будет работать в 64-разрядном процессе, если оно скомпилировано как 64-разрядное или AnyCPU и выполняется в 64-разрядной операционной системе. Хотя приняты все необходимые меры, чтобы обеспечить как можно более прозрачный переход на новый компилятор, возможны изменения в поведении. Мы будем благодарны за любые отзывы о проблемах, возникших при использовании нового JIT-компилятора. Свяжитесь с нами через сайт [Microsoft Connect](https://connect.microsoft.com/) в случае возникновения проблемы, которая может быть связана с новым 64-разрядным JIT-компилятором.

  Новый 64-разрядный JIT-компилятор также включает функции аппаратного ускорения SIMD при работе с типами с поддержкой SIMD в пространстве имен <xref:System.Numerics>, что может обеспечить неплохое повышение производительности.

- **Усовершенствования загрузчика сборок**

  Загрузчик сборок теперь более эффективно использует память благодаря выгрузке сборок IL после загрузки соответствующего образа NGEN. Это изменение снижает использование виртуальной памяти, что особенно полезно для больших 32-разрядных приложений (например, Visual Studio); кроме того, оно обеспечивает экономию физической памяти.

- **Изменения библиотеки с базовым классом**

  В .NET Framework 4.6 были добавлены многие новые API для поддержки важных сценариев. Внесены следующие изменения и дополнения.

  - **Реализации IReadOnlyCollection\<T>**

    Дополнительные коллекции реализуют <xref:System.Collections.Generic.IReadOnlyCollection%601>, например <xref:System.Collections.Generic.Queue%601> и <xref:System.Collections.Generic.Stack%601>.

  - **CultureInfo.CurrentCulture и CultureInfo.CurrentUICulture**

    Свойства <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> и <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> теперь доступны для чтения и записи, а не только для чтения. При назначении нового объекта <xref:System.Globalization.CultureInfo> этим свойствам язык и региональные параметры текущего потока, определенные свойством `Thread.CurrentThread.CurrentCulture`, и язык и региональные параметры текущего потока пользовательского интерфейса, определенные свойствами `Thread.CurrentThread.CurrentUICulture`, также изменяются.

  - **Усовершенствования сборки мусора**

    Класс <xref:System.GC> теперь включает методы <xref:System.GC.TryStartNoGCRegion%2A> и <xref:System.GC.EndNoGCRegion%2A>, которые позволяют запретить сбор мусора во время выполнения критического пути.

    Новая перегрузка метода <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%2CSystem.Boolean%29?displayProperty=nameWithType> позволяет контролировать, выполняется ли очистка и сжатие кучи мелких объектов и кучи больших объектов или только очистка.

  - **Типы с поддержкой SIMD**

    Пространство имен <xref:System.Numerics> теперь включает различные типы с поддержкой SIMD, например <xref:System.Numerics.Matrix3x2>, <xref:System.Numerics.Matrix4x4>, <xref:System.Numerics.Plane>, <xref:System.Numerics.Quaternion>, <xref:System.Numerics.Vector2>, <xref:System.Numerics.Vector3> и <xref:System.Numerics.Vector4>.

    Поскольку новый 64-разрядный JIT-компилятор также включает функции аппаратного ускорения SIMD, особенно значительное повышение производительности обеспечивается при использовании типов с поддержкой SIMD с новым 64-разрядным JIT-компилятором.

  - **Обновления шифрования**

    API <xref:System.Security.Cryptography?displayProperty=nameWithType> обновляется для поддержки [API шифрования CNG Windows](/windows/desktop/SecCNG/cng-reference). Предыдущие версии .NET Framework полностью зависели от [более ранних версий API шифрования Windows](/windows/desktop/SecCrypto/cryptography-portal) для реализации <xref:System.Security.Cryptography?displayProperty=nameWithType>. Мы получали много запросов на реализацию поддержки API CNG, так как он поддерживает [современные алгоритмы шифрования](/windows/desktop/SecCNG/cng-features#suite-b-support), что очень важно для некоторых категорий приложений.

    В .NET Framework 4.6 добавлены следующие новые улучшения для поддержки API шифрования CNG Windows:

    - Набор методов расширения для сертификатов X509, `System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)` и `System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)`, которые возвращают реализацию на основе CNG, а не реализацию на основе CAPI (по возможности). (Некоторые смарт-карты и т. д. по-прежнему требуют CAPI, и API-интерфейсы обрабатывают резервный вариант.)

    - Класс <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType>, который обеспечивает реализацию CNG алгоритма RSA.

    - Улучшения API RSA, позволяющие отказаться от обязательного приведения общих действий. Например, для шифрования данных с помощью объекта <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> в предыдущих версиях платформы .NET Framework требуется код, аналогичный следующему.

      [!code-csharp[WhatsNew.Casting#1](~/samples/snippets/csharp/VS_Snippets_CLR/whatsnew.casting/cs/program.cs#1)]
      [!code-vb[WhatsNew.Casting#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.casting/vb/module1.vb#1)]

      Код, использующий новые API шифрования в .NET Framework 4.6, можно переписать следующим образом, чтобы избежать приведения.

      [!code-csharp[WhatsNew.Casting#2](~/samples/snippets/csharp/VS_Snippets_CLR/whatsnew.casting/cs/program.cs#2)]
      [!code-vb[WhatsNew.Casting#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.casting/vb/module1.vb#2)]

  - **Поддержка преобразования даты и времени в формат времени Unix и обратно**

    Следующие новые методы были добавлены в структуру <xref:System.DateTimeOffset> для поддержки преобразования значений даты и времени в формат Unix или из него.

    - <xref:System.DateTimeOffset.FromUnixTimeSeconds%2A?displayProperty=nameWithType>

    - <xref:System.DateTimeOffset.FromUnixTimeMilliseconds%2A?displayProperty=nameWithType>

    - <xref:System.DateTimeOffset.ToUnixTimeSeconds%2A?displayProperty=nameWithType>

    - <xref:System.DateTimeOffset.ToUnixTimeMilliseconds%2A?displayProperty=nameWithType>

  - **Параметры совместимости**

    Новый класс <xref:System.AppContext> добавляет новый компонент совместимости, который позволяет авторам библиотек предоставлять согласованный механизм явного отказа для новых функциональных возможностей. Он устанавливает слабо связанный контракт между компонентами для передачи запроса на явный отказ. Эта возможность обычно важна при внесении изменений в существующие функции. В свою очередь, режим неявного согласия для новых функциональных возможностей уже существует.

    В <xref:System.AppContext> библиотеки определяют и предоставляют параметры совместимости, а код, который от них зависит, может устанавливать эти параметры для влияния на поведение библиотек. По умолчанию библиотеки предоставляют новые функции и изменяют их (то есть предоставляют прежние функции) только в том случае, если установлен параметр.

    Приложение (или библиотека) может объявить значение параметра (который всегда имеет значение <xref:System.Boolean>), определяемое зависимой библиотекой. Параметр всегда имеет неявное значение `false`. Установка значения `true` для параметра включает его. Явно задание значения `false` для параметра определяет новое поведение.

    ```csharp
    AppContext.SetSwitch("Switch.AmazingLib.ThrowOnException", true);
    ```

    ```vb
    AppContext.SetSwitch("Switch.AmazingLib.ThrowOnException", True)
    ```

    Библиотека должна проверить, объявил ли потребитель значение параметра, а затем выполнить соответствующие действия.

    ```csharp
    if (!AppContext.TryGetSwitch("Switch.AmazingLib.ThrowOnException", out shouldThrow))
    {
        // This is the case where the switch value was not set by the application.
        // The library can choose to get the value of shouldThrow by other means.
        // If no overrides nor default values are specified, the value should be 'false'.
        // A false value implies the latest behavior.
    }

    // The library can use the value of shouldThrow to throw exceptions or not.
    if (shouldThrow)
    {
        // old code
    }
    else
    {
        // new code
    }
    ```

    ```vb
    If Not AppContext.TryGetSwitch("Switch.AmazingLib.ThrowOnException", shouldThrow) Then
        ' This is the case where the switch value was not set by the application.
        ' The library can choose to get the value of shouldThrow by other means.
        ' If no overrides nor default values are specified, the value should be 'false'.
        ' A false value implies the latest behavior.
    End If

    ' The library can use the value of shouldThrow to throw exceptions or not.
    If shouldThrow Then
        ' old code
    Else
        ' new code
    End If
    ```

    Рекомендуется использовать согласованный формат параметров, так как они представляют собой формальный контракт, предоставляемый библиотекой. Ниже приведены два очевидных формата:

    - *параметр*.*пространство_имен* *имя_параметра*

    - *параметр*.*библиотека*.*имя_параметра*

  - **Изменения асинхронной модели на основе задач**

    Для приложений, предназначенных для .NET Framework 4.6, объекты <xref:System.Threading.Tasks.Task> и <xref:System.Threading.Tasks.Task%601> наследуют язык и региональные параметры, а также язык и региональные параметры интерфейса пользователя вызывающего потока. Поведение приложений на предыдущих версиях платформы .NET Framework или без определенной версии .NET Framework не затрагивается. Дополнительные сведения см. в подразделе "Язык и региональные параметры в асинхронных операциях на основе задач" раздела, посвященного классу <xref:System.Globalization.CultureInfo>.

    Класс <xref:System.Threading.AsyncLocal%601?displayProperty=nameWithType> позволяет представлять внешние данные, локальные для данного асинхронного потока управления, такие как метод `async`. Его можно использовать для сохранения данных в разных потоках. Кроме того, можно определить метод обратного вызова, который получает уведомление при каждом изменении внешних данных из-за явного изменения свойства <xref:System.Threading.AsyncLocal%601.Value%2A?displayProperty=nameWithType> или из-за перехода контекста в потоке.

    Три удобных метода, <xref:System.Threading.Tasks.Task.CompletedTask%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Task.FromCanceled%2A?displayProperty=nameWithType> и <xref:System.Threading.Tasks.Task.FromException%2A?displayProperty=nameWithType>, добавлены в асинхронную модель на основе задач (TAP) для возврата завершенных задач в определенном состоянии.

    Теперь класс <xref:System.IO.Pipes.NamedPipeClientStream> поддерживает асинхронное взаимодействие с новым методом <xref:System.IO.Pipes.NamedPipeClientStream.ConnectAsync%2A>. метод.

  - **EventSource теперь поддерживает запись в журнал событий**

    Теперь класс <xref:System.Diagnostics.Tracing.EventSource> можно использовать для регистрации в журнале событий административных сообщений или рабочих сообщений в дополнение ко всем существующим сеансам трассировки событий Windows, созданным на компьютере. Раньше для обеспечения этих функций приходилось использовать пакет Microsoft.Diagnostics.Tracing.EventSource NuGet. Эта функция теперь встроена в .NET Framework 4.6.

    Обновления пакета NuGet и .NET Framework 4.6 включают следующие функции:

    - **Динамические события**

      Возможность определения событий "на лету" без создания методов событий.

    - **Разнородные полезные данные**

      Возможность передавать массивы и классы со специальными атрибутами, а также типы-примитивы в качестве полезных данных.

    - **Отслеживание действий**

      События Start и Stop помечают возникающие между ними события идентификатором, который представляет все текущие активные действия.

    Для поддержки этих функций перегруженный метод <xref:System.Diagnostics.Tracing.EventSource.Write%2A> был добавлен в класс <xref:System.Diagnostics.Tracing.EventSource>.

- **Windows Presentation Foundation (WPF)**

  - **Усовершенствования HDPI**

    В .NET Framework 4.6 улучшена поддержка HDPI в WPF. В округление макетов внесены изменения для снижения числа вхождений обрезки в элементах управления с границами. По умолчанию эта функция включена, только если для атрибута <xref:System.Runtime.Versioning.TargetFrameworkAttribute> задано значение .NET 4.6.  Для приложений, которые предназначены для более ранних версий платформы, но выполняются в .NET Framework 4.6, новое поведение можно активировать отдельно, добавив следующую строку в раздел [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) файла app.config:

    ```xml
    <AppContextSwitchOverrides
    value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false"
    />
    ```

    Окна WPF, разнесенные на несколько мониторов с разными параметрами DPI (настройка нескольких параметров разрешения), теперь отображаются полностью, без черных областей. Можно отключить это новое поведение, добавив следующую строку в раздел `<appSettings>` файла app.config.

    ```xml
    <add key="EnableMultiMonitorDisplayClipping" value="true"/>
    ```

    Поддержка автоматической загрузки правого курсора в зависимости от параметров DPI добавлена в <xref:System.Windows.Input.Cursor?displayProperty=nameWithType>.

  - **Улучшено касание**

    В .NET Framework 4.6 решена проблема с касанием, приводившим к непредсказуемому поведению, о которой сообщает клиент на веб-сайте [Connect](https://connect.microsoft.com/VisualStudio/feedback/details/903760/). Пороговое значение двойного касания для приложений Магазина Windows и приложений WPF теперь одинаково в Windows 8.1 и более поздних версий.

  - **Поддержка прозрачных дочерних окон**

    WPF в .NET Framework 4.6 поддерживает прозрачные дочерние окна в Windows 8.1 и более поздних версий. Это позволяет создавать непрямоугольные и прозрачные дочерние окна в окнах верхнего уровня. Чтобы включить эту функцию, необходимо задать для свойства <xref:System.Windows.Interop.HwndSourceParameters.UsesPerPixelTransparency%2A?displayProperty=nameWithType> значение `true`.

- **Windows Communication Foundation (WCF)**

  - **Поддержка SSL**

    Теперь WCF помимо SSL 3.0 и TLS 1.0 поддерживает SSL-версии TLS 1.1 и TLS 1.2 при использовании NetTcp с безопасностью транспорта и проверкой подлинности клиента. Теперь можно выбрать, какой протокол использовать, или отключить старые менее безопасные протоколы. Это можно сделать, задав свойство <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A> или добавив следующие данные в файл конфигурации.

    ```xml
    <netTcpBinding>
        <binding>
          <security mode= "None|Transport|Message|TransportWithMessageCredential" >
              <transport clientCredentialType="None|Windows|Certificate"
                        protectionLevel="None|Sign|EncryptAndSign"
                        sslProtocols="Ssl3|Tls1|Tls11|Tls12">
                </transport>
          </security>
        </binding>
    </netTcpBinding>
    ```

  - **Отправка сообщений с помощью разных подключений HTTP**

    WCF теперь позволяет пользователям отправлять некоторые сообщения с помощью разных базовых HTTP-подключений. Это можно сделать двумя способами.

    - **С помощью префикса имени группы подключений**

      Пользователи могут указать строку, которую WCF будет использовать как префикс для имени группы подключений. Два сообщения с разными префиксами отправляются с помощью разных базовых HTTP-подключений. Префикс задается путем добавления пары "ключ-значение" в свойство <xref:System.ServiceModel.Channels.Message.Properties%2A?displayProperty=nameWithType> сообщения. Ключ — это "HttpTransportConnectionGroupNamePrefix"; значение — желаемый префикс.

    - **С помощью разных фабрик каналов**

      Пользователи могут также включить функцию, которая гарантирует, что сообщения, отправляемые по каналам, созданным разными фабриками каналов, будут отправляться с помощью разных базовых HTTP-подключений. Чтобы включить эту функцию, пользователи должны самостоятельно задать для следующего параметра `appSetting` значение `true`.

      ```xml
      <appSettings>
          <add key="wcf:httpTransportBinding:useUniqueConnectionPoolPerFactory" value="true" />
      </appSettings>
      ```

- **Windows Workflow Foundation (WWF)**

  Теперь можно указать интервал (в секундах) удержания службой рабочего процесса внеочередного запроса операции при наличии незавершенной закладки "без протокола" до истечения времени ожидания запроса. Закладка "без протокола" — это закладка, которая не связана с незавершенными действиями получения. Некоторые действия создают закладки без протокола в собственной реализации, поэтому не всегда очевидно, что закладка без протокола существует. К таким действиям относятся State и Pick. Соответственно, при наличии службы рабочего процесса, реализованной с помощью конечного автомата или содержащей действие Pick, вероятнее всего, имеются закладки без протокола. Укажите интервал, добавив строку следующего вида в раздел `appSettings` файла app.config.

  ```xml
  <add key="microsoft:WorkflowServices:FilterResumeTimeoutInSeconds" value="60"/>
  ```

  Значение по умолчанию — 60 секунд. Если `value` имеет значение 0, внеочередные запросы немедленно отклоняются с созданием ошибки с текстом, который выглядит следующим образом.

  ```console
  Operation 'Request3|{http://tempuri.org/}IService' on service instance with identifier '2b0667b6-09c8-4093-9d02-f6c67d534292' cannot be performed at this time. Please ensure that the operations are performed in the correct order and that the binding in use provides ordered delivery guarantees.
  ```

  Это же сообщение отображается при получении сообщения о внеочередной операции в отсутствии закладок без протокола.

  Если элемент `FilterResumeTimeoutInSeconds` имеет ненулевое значение, существуют закладки без протокола и истекает интервал времени ожидания, то происходит сбой операции с сообщением об истечении времени ожидания.

- **Транзакции**

  Теперь можно включить идентификатор распределенной транзакции для транзакций, вызвавших создание исключения, производного от <xref:System.Transactions.TransactionException>. Это можно сделать, добавив следующий ключ в раздел `appSettings` файла app.config:

  ```xml
  <add key="Transactions:IncludeDistributedTransactionIdInExceptionMessage" value="true"/>
  ```

  Значение по умолчанию — `false`.

- **Сеть**

  - **Повторное использование сокета**

    Windows 10 включает новый алгоритм сетевых подключений с высокой масштабируемостью, который повышает эффективность использования ресурсов компьютера путем повторного использования локальных портов для исходящих TCP-подключений. .NET Framework 4.6 поддерживает новый алгоритм, который позволяет приложениям .NET использовать преимущества нового поведения. В предыдущих версиях Windows существовало искусственно заданное ограничение числа параллельных подключений (обычно 16 384, размер динамического диапазона портов по умолчанию), которое могло ограничивать масштабируемость службы, вызывая нехватку портов при высокой загрузке.

    В .NET Framework 4.6 добавлены два новых API, которые обеспечивают повторное использование портов и эффективно снимают ограничение на 64 000 одновременных подключения.

    - Значение перечисления <xref:System.Net.Sockets.SocketOptionName?displayProperty=nameWithType>.

    - Свойство <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=nameWithType>.

    По умолчанию свойство <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=nameWithType> имеет значение `false`, если в качестве значения `HWRPortReuseOnSocketBind` раздела реестра `HKLM\SOFTWARE\Microsoft\.NETFramework\v4.0.30319` не задано 0x1. Чтобы включить повторное использование локальных портов для HTTP-подключений, задайте для свойства <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=nameWithType> значение `true`. В результате все исходящие подключения сокета TCP от <xref:System.Net.Http.HttpClient> и <xref:System.Net.HttpWebRequest> будут использовать новый параметр сокета Windows 10, [SO_REUSE_UNICASTPORT](/windows/desktop/WinSock/sol-socket-socket-options), который обеспечивает повторное использование локальных портов.

    Разработчики, создающие приложения, работающие только с сокетами, могут указать параметр <xref:System.Net.Sockets.SocketOptionName?displayProperty=nameWithType> при вызове такого метода, как <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=nameWithType>, чтобы исходящие сокеты повторно использовали локальные порты во время привязки.

  - **Поддержка международных доменных имен и PunyCode**

    В класс <xref:System.Uri> добавлено новое свойство <xref:System.Uri.IdnHost%2A>, обеспечивающее более эффективную поддержку международных доменных имен и PunyCode.

- **Изменение размеров элементов управления Windows Forms.**

  Эта функция была расширена в .NET Framework 4.6 и включает типы <xref:System.Windows.Forms.DomainUpDown>, <xref:System.Windows.Forms.NumericUpDown>, <xref:System.Windows.Forms.DataGridViewComboBoxColumn>, <xref:System.Windows.Forms.DataGridViewColumn> и <xref:System.Windows.Forms.ToolStripSplitButton>, а также прямоугольник, указанный свойством <xref:System.Drawing.Design.PaintValueEventArgs.Bounds%2A>, используемым при рисовании <xref:System.Drawing.Design.UITypeEditor>.

  Это функция, включаемая пользователем. Чтобы ее включить, задайте для элемента `EnableWindowsFormsHighDpiAutoResizing` в файле конфигурации приложения (app.config) значение `true`:

  ```xml
  <appSettings>
      <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />
  </appSettings>
  ```

- **Поддержка кодировок кодовых страниц**

  .NET Core в первую очередь поддерживает кодировки Юникод и по умолчанию предоставляет ограниченную поддержку для кодировок кодовых страниц. Вы можете добавить поддержку кодировок кодовых страниц, доступных в .NET Framework, но не поддерживаемых в .NET Core, зарегистрировав эти кодировки в методе <xref:System.Text.Encoding.RegisterProvider%2A?displayProperty=nameWithType>. Дополнительные сведения можно найти по адресу: <xref:System.Text.CodePagesEncodingProvider?displayProperty=nameWithType>.

- **.NET Native**

  Приложения Windows для Windows 10, ориентированные на .NET Core и написанные на языке C# или Visual Basic, могут использовать новую технологию компиляции приложения в машинный код вместо кода IL. Они создают приложения, которым присуща более быстрая загрузка и время выполнения. Дополнительные сведения см. в разделе [Компиляция приложений с помощью .NET Native](../net-native/index.md). Общие сведения о .NET Native и рассмотрение отличий такой компиляции от компиляции JIT и NGEN, а также ее влияние на код см. в разделе [.NET Native и компиляция](../net-native/net-native-and-compilation.md).

  Приложения по умолчанию компилируются в машинный код при компиляции в Visual Studio 2015 и более поздних версиях. Дополнительные сведения см. в разделе [Начало работы с .NET Native](../net-native/getting-started-with-net-native.md).

  Для поддержки отладки приложений .NET Native в  интерфейс API отладки неуправляемого кода добавлено несколько новых интерфейсов и перечислений. Дополнительные сведения см. в разделе [Отладка (справочник по неуправляемым API)](../unmanaged-api/debugging/index.md).

- **Пакеты .NET Framework с открытым исходным кодом**

  Пакеты .NET Core, такие как неизменяемые коллекции, [API SIMD](https://go.microsoft.com/fwlink/?LinkID=518639) и API-интерфейсы сетевых подключений, например из пространства имен <xref:System.Net.Http>, теперь доступны в виде пакетов с открытым исходным кодом на сайте [GitHub](https://github.com/). Сведения о доступе к этому коду см. в разделе [CoreFx на GitHub](https://github.com/dotnet/corefx). Дополнительные сведения и инструкции, как принять участие в этих пакетах, см. в разделе [Ядро .NET и открытый исходный код](../get-started/net-core-and-open-source.md)[домашней странице .NET на GitHub](https://github.com/dotnet/home).

<a name="v452" />

## <a name="whats-new-in-net-framework-452"></a>Новые возможности .NET Framework 4.5.2

- **Новые API для приложений ASP.NET.** Новые методы <xref:System.Web.HttpResponse.AddOnSendingHeaders%2A?displayProperty=nameWithType> и <xref:System.Web.HttpResponseBase.AddOnSendingHeaders%2A?displayProperty=nameWithType> позволяют проверять и изменять коды состояния и заголовки ответов при передаче ответа в клиентское приложение. Эти методы можно использовать вместо событий <xref:System.Web.HttpApplication.PreSendRequestHeaders> и <xref:System.Web.HttpApplication.PreSendRequestContent>; они более эффективны и надежны.

  Метод <xref:System.Web.Hosting.HostingEnvironment.QueueBackgroundWorkItem%2A?displayProperty=nameWithType> позволяет планировать небольшие фоновые рабочие элементы. ASP.NET отслеживает эти элементы и блокирует резкое прерывание службами IIS рабочего процесса до выполнения всех фоновых рабочих элементов. Этот метод нельзя вызвать за пределами управляемого домена приложений ASP.NET.

  Новые свойства <xref:System.Web.HttpResponse.HeadersWritten?displayProperty=nameWithType> и <xref:System.Web.HttpResponseBase.HeadersWritten?displayProperty=nameWithType> возвращают логические значения, которые указывают, были ли записаны заголовки ответов. Эти свойства можно использовать, чтобы гарантировать, что вызовы API, например <xref:System.Web.HttpResponse.StatusCode%2A?displayProperty=nameWithType> (создает исключения, если заголовки записаны), будут выполняться успешно.

- **Изменение размеров элементов управления Windows Forms.** Эта функция была расширена. Теперь системный параметр DPI можно использовать для изменения размера компонентов следующих дополнительных элементов управления (например, стрелки, раскрывающей поле со списком):

  - <xref:System.Windows.Forms.ComboBox>
  - <xref:System.Windows.Forms.ToolStripComboBox>
  - <xref:System.Windows.Forms.ToolStripMenuItem>
  - <xref:System.Windows.Forms.Cursor>
  - <xref:System.Windows.Forms.DataGridView>
  - <xref:System.Windows.Forms.DataGridViewComboBoxColumn>

  Это функция, включаемая пользователем. Чтобы ее включить, задайте для элемента `EnableWindowsFormsHighDpiAutoResizing` в файле конфигурации приложения (app.config) значение `true`:

  ```xml
  <appSettings>
      <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />
  </appSettings>
  ```

- **Новая функция рабочего процесса.** Диспетчер ресурсов, использующий метод <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A> (и, следовательно, реализующий интерфейс <xref:System.Transactions.IPromotableSinglePhaseNotification>), может использовать новый метод <xref:System.Transactions.Transaction.PromoteAndEnlistDurable%2A?displayProperty=nameWithType> для запроса следующих операций:

  - повышение транзакции до уровня "координатор распределенных транзакций (Майкрософт)" (MSDTC);

  - замена <xref:System.Transactions.IPromotableSinglePhaseNotification> перечислением<xref:System.Transactions.ISinglePhaseNotification>, которое является устойчивым перечислением, поддерживающим одноэтапные фиксации.

  Эту операцию можно выполнить в том же домене приложения; для повышения уровня не требуется написание дополнительного неуправляемого кода для взаимодействия с MSDTC. Новый метод можно вызвать только при наличии ожидающего выполнения вызова из <xref:System.Transactions?displayProperty=nameWithType> к методу <xref:System.Transactions.IPromotableSinglePhaseNotification>`Promote`, который реализуется перечислением, поддерживающим повышение уровня.

- **Усовершенствования профилирования.** Следующие новые неуправляемые API профилирования обеспечивают более надежное профилирование:

  - [Структура COR_PRF_ASSEMBLY_REFERENCE_INFO](../unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md)
  - [Перечисление COR_PRF_HIGH_MONITOR](../unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md)
  - [Метод GetAssemblyReferences](../unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)
  - [Метод GetEventMask2](../unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)
  - [Метод SetEventMask2](../unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
  - [Метод AddAssemblyReference](../unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)

  Предыдущие реализации `ICorProfiler` поддерживали отложенную загрузку зависимых сборок. Новые API профилирования требуют немедленной доступности для загрузки вставляемых профилировщиком зависимых сборок вместо их загрузки после полной инициализации приложения. Это изменение не влияет на пользователей существующих API `ICorProfiler`.

- **Усовершенствования отладки.** Следующие новые интерфейсы API отладки неуправляемого кода обеспечивают более эффективную интеграцию с профилировщиком. Теперь можно получить доступ к метаданным, вставленным профилировщиком, а также к локальным переменным и коду, созданным запросами компилировщика ReJIT во время отладки дампа.

  - [Метод SetWriteableMetadataUpdateMode](../unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md)
  - [Метод EnumerateLocalVariablesEx](../unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md)
  - [Метод GetLocalVariableEx](../unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md)
  - [Метод GetCodeEx](../unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md)
  - [Метод GetActiveReJitRequestILCode](../unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md)
  - [Метод GetInstrumentedILMap](../unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md)

- **Изменения трассировки событий.** .NET Framework 4.5.2 поддерживает внепроцессную трассировку действий, основанную на трассировке событий Windows (ETW), для более крупных контактных зон. Это позволяет поставщикам решений автоматического управления питанием (АРМ) предлагать облегченные средства, точно отслеживающие стоимость отдельных запросов и действий в разных потоках.  Эти события вызываются только при включении их контроллерами ETW. Таким образом, изменения не влияют на ранее написанный код ETW или код, который выполняется при отключенной трассировке ETW.

- **Повышение уровня транзакции и преобразование ее в устойчивое зачисление**

  <xref:System.Transactions.Transaction.PromoteAndEnlistDurable%2A?displayProperty=nameWithType> — это новый API, добавленный в .NET Framework версий 4.5.2 и 4.6.

  ```csharp
  [System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]
  public Enlistment PromoteAndEnlistDurable(Guid resourceManagerIdentifier,
                                            IPromotableSinglePhaseNotification promotableNotification,
                                            ISinglePhaseNotification enlistmentNotification,
                                            EnlistmentOptions enlistmentOptions)
  ```

  ```vb
  <System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust")>
  public Function PromoteAndEnlistDurable(resourceManagerIdentifier As Guid,
                                          promotableNotification As IPromotableSinglePhaseNotification,
                                          enlistmentNotification As ISinglePhaseNotification,
                                          enlistmentOptions As EnlistmentOptions) As Enlistment
  ```

  Метод может использоваться зачислением, ранее созданным <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A?displayProperty=nameWithType> в ответ на метод <xref:System.Transactions.ITransactionPromoter.Promote%2A?displayProperty=nameWithType>. Он запрашивает у `System.Transactions` повышение уровня транзакции до транзакции MSDTC и "преобразование" зачисления, допускающего повышение уровня, в зачисление устойчивых ресурсов. После успешного завершения этого метода `System.Transactions` больше не будет ссылаться на интерфейс <xref:System.Transactions.IPromotableSinglePhaseNotification>, и все будущие уведомления будут поступать в предоставленном интерфейсе <xref:System.Transactions.ISinglePhaseNotification>. Рассматриваемое зачисление должно работать как зачисление устойчивых ресурсов, поддерживая ведение журнала транзакций и восстановления. Подробные сведения см. в разделе <xref:System.Transactions.Transaction.EnlistDurable%2A?displayProperty=nameWithType>. Кроме того, зачисление должно поддерживать <xref:System.Transactions.ISinglePhaseNotification>.  Этот метод может вызываться *только* во время обработки вызова <xref:System.Transactions.ITransactionPromoter.Promote%2A?displayProperty=nameWithType>. Если это не так, создается исключение <xref:System.Transactions.TransactionException>.

<a name="v451" />

## <a name="whats-new-in-net-framework-451"></a>Новые возможности .NET Framework 4.5.1

**Обновления апреля 2014 г.** :

- [Обновление 2 для Visual Studio 2013](https://go.microsoft.com/fwlink/p/?LinkId=393658) включает обновления для шаблонов переносимой библиотеки классов для поддержки следующих сценариев:

  - Возможность использовать API среды выполнения Windows в переносимых библиотеках, предназначенных для Windows 8.1, Windows Phone 8.1 и Windows Phone Silverlight 8.1.

  - возможность включить XAML-код (типы Windows.UI.XAML) в переносимые библиотеки, предназначенные для Windows 8.1 или Windows Phone 8.1. Поддерживаются следующие шаблоны XAML:  "Пустая страница", "Словарь ресурсов", "Элемент управления-шаблон" и "Пользовательский элемент управления".

  - Можно создать переносной компонент среды выполнения Windows (WINMD-файл) для использования в приложениях магазинов, предназначенных для Windows 8.1 и Windows Phone 8.1.

  - Можно изменить целевую платформу библиотеки классов Магазина Windows или Магазина Windows Phone, такой как переносимая библиотека классов.

  Дополнительные сведения об этих изменениях см. в разделе [Переносимая библиотека классов](../../standard/cross-platform/cross-platform-development-with-the-portable-class-library.md).

- Набор содержимого .NET Framework теперь включает документацию для .NET Native. Это технология предварительной компиляции для сборки и развертывания приложений Windows. .NET Native компилирует приложения напрямую в машинный код, а не в промежуточный язык (IL), что повышает производительность. Подробные сведения см. в разделе [Компиляция приложений с помощью .NET Native](../net-native/index.md).

- На странице [.NET Framework Reference Source](https://referencesource.microsoft.com/) предоставляются новые возможности навигации и расширенные функции. Теперь можно искать исходный код .NET Framework в Интернете, [загрузить справочник](https://referencesource.microsoft.com/download.html) для автономной работы и пошагово просматривать источники (включая исправления и обновления) во время отладки. Дополнительные сведения см. в записи блога [Новый облик .NET Reference Source](https://devblogs.microsoft.com/dotnet/a-new-look-for-net-reference-source/).

Новые функции и улучшения базовых классов в .NET Framework 4.5.1 включают следующее:

- Автоматическая переадресация привязки для сборок. Начиная с версии Visual Studio 2013 при компиляции приложения, ориентированного на .NET Framework 4.5.1, в файл конфигурации приложения можно добавить переадресации привязок, если приложение или его компоненты ссылаются на несколько версий одной и той же сборки. Включить эту функцию также можно для проектов, предназначенных для более ранних версий платформы .NET Framework. Дополнительные сведения см. в разделе [Практическое руководство. Включение и отключение автоматического перенаправления привязки](../configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md).

- Возможность сбора диагностической информации, чтобы помочь разработчикам повысить производительность серверных и облачных приложений. Дополнительные сведения см. в описании методов <xref:System.Diagnostics.Tracing.EventSource.WriteEventWithRelatedActivityId%2A> и <xref:System.Diagnostics.Tracing.EventSource.WriteEventWithRelatedActivityIdCore%2A> класса <xref:System.Diagnostics.Tracing.EventSource>.

- Возможность явно уплотнять кучу больших объектов во время сборки мусора. Дополнительные сведения см. в описании свойства <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType>.

- Дополнительные улучшения производительности, например приостановка приложений ASP.NET, усовершенствования многоядерного JIT и более быстрый запуск приложений после обновления платформы .NET Framework. Дополнительные сведения см. в [объявлении о выходе .NET Framework 4.5.1](https://devblogs.microsoft.com/dotnet/announcing-the-net-framework-4-5-1-preview/) и в публикации в блоге [о приостановке приложения ASP.NET](https://devblogs.microsoft.com/dotnet/asp-net-app-suspend-responsive-shared-net-web-hosting/).

Усовершенствования в Windows Forms включают следующие:

- Изменение размеров элементов управления Windows Forms. Системный параметр DPI можно использовать для изменения размера компонентов элементов управления (например, значков, которые отображаются в сетке свойств) путем явного включения с помощью записи в файле конфигурации приложения (app.config) нужного приложения. Эта функция в настоящее время поддерживается для следующих элементов управления Windows Forms:

  - <xref:System.Windows.Forms.PropertyGrid>
  - <xref:System.Windows.Forms.TreeView>
  - Поддерживаются некоторые аспекты <xref:System.Windows.Forms.DataGridView> (дополнительные поддерживаемые элементы управления см. в разделе о [новых возможностях в версии 4.5.2](#v452))

  Чтобы включить эту функцию, добавьте новый элемент \<appSettings> в файл конфигурации (app.config) и задайте для элемента `EnableWindowsFormsHighDpiAutoResizing` значение `true`:

  ```xml
  <appSettings>
      <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />
  </appSettings>
  ```

В процесс отладки приложений .NET Framework в Visual Studio 2013 внесены следующие улучшения.

- Возвращаемые значения в отладчике Visual Studio. При отладке управляемого приложения в Visual Studio 2013 в окне "Видимые" отображаются возвращаемые типы и значения для методов. Эти сведения доступны для приложений для настольных систем, приложений для Магазина Windows и приложений Windows Phone. Дополнительные сведения см. в статье [Анализ значений, возвращаемых из вызовов методов](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/dn323257(v=vs.120)).

- "Изменить и продолжить" для 64-разрядных приложений. Visual Studio 2013 поддерживает действие "Изменить и продолжить" для 64-разрядных управляемых приложений для настольных систем, приложений для Магазина Windows и приложений для Windows Phone. Существующие ограничения остаются действующими и для 32-разрядных, и для 64-разрядных приложений (см. последний раздел статьи [Поддерживаемые изменения кода (C#)](/visualstudio/debugger/supported-code-changes-csharp)).

- Отладка с поддержкой асинхронности. Чтобы упростить отладку асинхронных приложений в Visual Studio 2013, стеке вызовов скрывает код инфраструктуры, предоставляемый компиляторами для поддержки асинхронного программирования, а также цепочки логических родительских кадров, что упрощает прослеживание логики выполнения программы. В окне "Задачи", которое заменяет собой окно "Параллельные задачи", отображаются задачи, относящиеся к определенной точке останова, а также все другие задачи, которые в данный момент активны или запланированы в приложении. Вы можете прочесть об этой возможности в разделе "Отладка с поддержкой асинхронности" [объявления о выходе .NET Framework 4.5.1](https://devblogs.microsoft.com/dotnet/announcing-the-net-framework-4-5-1-preview/).

- Усовершенствованная поддержка исключений для компонентов среды выполнения Windows. В [!INCLUDE[win81](../../../includes/win81-md.md)] исключения, возникающие в приложениях для Магазина Windows, сохраняют сведения об ошибке, которая вызвала исключение, даже при переходе через границу языка. Вы можете прочесть об этой возможности в разделе "Разработка приложений для Магазина Windows" [объявления о выходе .NET Framework 4.5.1](https://devblogs.microsoft.com/dotnet/announcing-the-net-framework-4-5-1-preview/).

Начиная с Visual Studio 2013 вы можете использовать [Управляемое средство профильной оптимизации (Mpgo.exe)](../tools/mpgo-exe-managed-profile-guided-optimization-tool.md) для оптимизации приложений для Магазина Windows 8.x и для настольных систем.

См. новые возможности ASP.NET 4.5.1 в статье [Заметки о выпуске ASP.NET and Web Tools для Visual Studio 2013](/aspnet/visual-studio/overview/2013/release-notes).

<a name="v45" />

## <a name="whats-new-in-net-framework-45"></a>Новые возможности .NET Framework 4.5

### <a name="base-classes"></a>базовых классов;

- Возможность уменьшения количества перезапусков системы путем обнаружения и закрытия приложений .NET Framework 4 во время развертывания. См. раздел [Уменьшение числа перезагрузок при установке платформы .NET Framework 4.5](../deployment/reducing-system-restarts.md).

- Поддержка массивов, размер которых превышает 2 ГБ, на 64-разрядных платформах. Эту функцию можно включить в файле конфигурации приложения. См. описание [элемента \<gcAllowVeryLargeObjects>](../configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md), в котором также перечислены другие ограничения на размер объекта и размер массива.

- Улучшенная производительность благодаря фоновой сборке мусора для серверов. Если вы используете серверную сборку мусора в .NET Framework 4.5, фоновая сборка мусора включается автоматически. Сведения см. в разделе "Фоновая сборка мусора сервера" статьи [Основы сборки мусора](../../standard/garbage-collection/fundamentals.md).

- Фоновая компиляция по требованию (JIT), которая доступна по выбору на многоядерных процессорах для повышения производительности приложения. См. раздел <xref:System.Runtime.ProfileOptimization>.

- Возможность ограничения времени, в течение которого обработчик регулярных выражений будет пытаться разрешить регулярное выражение до истечения срока действия выражения. См. свойство <xref:System.Text.RegularExpressions.Regex.MatchTimeout%2A?displayProperty=nameWithType>.

- Возможность определить язык и региональные параметры по умолчанию для домена приложения. См. класс <xref:System.Globalization.CultureInfo>.

- Консольная поддержка кодировки Юникод (UTF-16). См. класс <xref:System.Console>.

- Поддержка управления версиями данных сортировки и сравнения строк, зависящих от языка и региональных параметров. См. класс <xref:System.Globalization.SortVersion>.

- Улучшенная производительность при извлечении ресурсов. См. раздел [Упаковка и развертывание ресурсов](../resources/packaging-and-deploying-resources-in-desktop-apps.md).

- Усовершенствования в области сжатия ZIP, позволяющие уменьшить размер сжатого файла. См. пространство имен <xref:System.IO.Compression?displayProperty=nameWithType>.

- Возможность настраивать контекст отражения для переопределения поведения отражения по умолчанию с помощью класса <xref:System.Reflection.Context.CustomReflectionContext>.

- Поддержка версии 2008 стандарта интернационализированных доменных имен в приложениях (Internationalized Domain Names in Applications, IDNA) при использовании класса <xref:System.Globalization.IdnMapping?displayProperty=nameWithType> в [!INCLUDE[win8](../../../includes/win8-md.md)].

- Делегирование сравнения строк операционной системе, которая реализует Юникод 6.0, при использовании .NET Framework в [!INCLUDE[win8](../../../includes/win8-md.md)]. При работе на других платформах .NET Framework включает собственные данные сравнения строк, которые реализуют Юникод 5.x. См. класс <xref:System.String> и раздел "Примечания" в описании класса <xref:System.Globalization.SortVersion>.

- Возможность вычисления хэш-кодов для строк для каждого домена приложения. См. раздел [Элемент \<UseRandomizedStringHashAlgorithm>](../configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md).

- Поддержка отражения типов, разделенная между классами <xref:System.Type> и <xref:System.Reflection.TypeInfo>. См. раздел [Отражение в .NET Framework для приложений Магазина Windows](../reflection-and-codedom/reflection-for-windows-store-apps.md).

### <a name="managed-extensibility-framework-mef"></a>Managed Extensibility Framework (MEF)

В .NET Framework 4.5 для Managed Extensibility Framework (MEF) предоставлены следующие новые возможности.

- Поддержка универсальных типов.

- Модель программирования на основе соглашений, позволяющая создавать части на основе соглашений об именах, а не на основе атрибутов.

- Множественные области действия.

- Подмножество MEF, которое можно использовать при создании приложений для Магазина Windows 8.x. Это подмножество доступно как [загружаемый пакет](https://go.microsoft.com/fwlink/?LinkId=256238) из коллекции NuGet. Чтобы установить пакет, откройте проект в Visual Studio, выберите **Управление пакетами NuGet** в меню **Проект** и выполните поиск пакета `Microsoft.Composition` в Интернете.

Дополнительные сведения см. в разделе [Managed Extensibility Framework](../mef/index.md).

### <a name="asynchronous-file-operations"></a>Асинхронные операции с файлами

В .NET Framework 4.5 добавлены новые асинхронные возможности в языки C# и Visual Basic. Эти возможности представляют собой модель на основе задач для выполнения асинхронных операций. Для использования этой новой модели используйте асинхронные методы в классах ввода-вывода. См. раздел [Асинхронные операции файлового ввода-вывода](../../standard/io/asynchronous-file-i-o.md).

<a name="tools" />

### <a name="tools"></a>Инструменты

В .NET Framework 4.5 генератор файлов ресурсов (Resgen.exe) позволяет преобразовать RESOURCES-файл, внедренный в сборку .NET Framework, в RESW-файл для использования в приложениях Магазина Windows 8.x. Дополнительные сведения см. в разделе [Resgen.exe (генератор файлов ресурсов)](../tools/resgen-exe-resource-file-generator.md).

Средство управляемой оптимизации с использованием профиля (Mpgo.exe) позволяет сократить время запуска приложения, улучшить использование памяти (размер рабочего множества) и пропускную способность путем оптимизации сборок машинных образов. Этот инструмент командной строки формирует данные профилирования для сборок машинного образа приложения. См. раздел [Mpgo.exe (инструмент управляемой оптимизации с использованием профиля)](../tools/mpgo-exe-managed-profile-guided-optimization-tool.md). Начиная с Visual Studio 2013 вы можете использовать средство Mpgo.exe для оптимизации приложений для Магазина Windows 8.x и для настольных систем.

<a name="parallel" />

### <a name="parallel-computing"></a>Параллельные вычисления

В .NET Framework 4.5 предусмотрено несколько новых возможностей и усовершенствований для параллельных вычислений. К ним относятся повышение производительности, повышение управляемости, улучшенная поддержка асинхронного программирования, новая библиотека потоков данных и улучшенная поддержка параллельной отладки и анализа производительности. См. запись [Новые возможности параллелизма в .NET 4.5](https://go.microsoft.com/fwlink/?LinkId=235061) в блоге, посвященном параллельному программированию в .NET.

<a name="web" />

### <a name="web"></a>Интернет

В ASP.NET 4.5 и 4.5.1 добавилась привязка модели для Web Forms, поддержка WebSocket, асинхронные обработчики, усовершенствования для повышения производительности и многие другие возможности. Дополнительные сведения см. в следующих ресурсах:

- [ASP.NET 4.5 и Visual Studio 2012](https://docs.microsoft.com/previous-versions/aspnet/hh420390(v=vs.110))

- [Заметки о выпуске ASP.NET and Web Tools для Visual Studio 2013](/aspnet/visual-studio/overview/2013/release-notes)

### <a name="networking-a-namenetworking-"></a>Сеть <a name="networking" />

.NET Framework 4.5 предоставляет новый интерфейс программирования для приложений HTTP. Дополнительные сведения см. в описании новых пространств имен <xref:System.Net.Http?displayProperty=nameWithType> и <xref:System.Net.Http.Headers?displayProperty=nameWithType>.

Также предусмотрена поддержка нового интерфейса программирования для приема и взаимодействия с соединением WebSocket с помощью существующего класса <xref:System.Net.HttpListener> и связанных с ним классов. Дополнительные сведения см. в описании нового пространства имен <xref:System.Net.WebSockets> и класса <xref:System.Net.HttpListener>.

Кроме того, в .NET Framework 4.5 улучшено сетевое взаимодействие.

- RFC-совместимая поддержка URI. Дополнительные сведения см. в описании <xref:System.Uri> и соответствующих классов.

- Поддержка синтаксического анализа интернационализированных доменных имен (Internationalized Domain Name, IDN). Дополнительные сведения см. в описании <xref:System.Uri> и соответствующих классов.

- Поддержка интернационализации адресов электронной почты (Email Address Internationalization, EAI). Дополнительные сведения см. в описании пространства имен <xref:System.Net.Mail>.

- Улучшенная поддержка протокола IPv6. Дополнительные сведения см. в описании пространства имен <xref:System.Net.NetworkInformation>.

- Поддержка сокета с двойным режимом. Дополнительные сведения см. в описаниях классов <xref:System.Net.Sockets.Socket> и <xref:System.Net.Sockets.TcpListener>.

<a name="client" />

### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

В .NET Framework 4.5 для Windows Presentation Foundation (WPF) добавлены изменения и усовершенствования в следующих областях.

- Новый элемент управления <xref:System.Windows.Controls.Ribbon.Ribbon>, позволяющий реализовать пользовательский интерфейс в виде ленты, на которой размещаются панель быстрого доступа, меню приложения и вкладки.

- Новый интерфейс <xref:System.ComponentModel.INotifyDataErrorInfo>, который поддерживает синхронную и асинхронную проверку данных.

- Новые возможности для классов <xref:System.Windows.Controls.VirtualizingPanel> и <xref:System.Windows.Threading.Dispatcher>.

- Повышение производительности при отображении больших наборов сгруппированных данных, а также за счет доступа к коллекциям в потоках вне пользовательского интерфейса.

- Привязка данных к статическим свойствам, привязка данных к пользовательским типам, реализующим интерфейс <xref:System.Reflection.ICustomTypeProvider>, а также извлечение сведений о привязке данных из выражения привязки.

- Изменение расположения данных по мере изменение значений (формирование данных в реальном времени).

- Возможность проверить, отсоединен ли контекст данных для контейнера элемента.

- Возможность задать количество времени, которое должно пройти между операциями изменения свойств и обновления источника данных.

- Улучшенная поддержка реализации шаблонов слабых событий. Кроме того, события теперь могут принимать расширения разметки.

<a name="windows_communication_foundation" />

### <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)

В .NET Framework 4.5 добавлены следующие возможности, чтобы упростить создание и обслуживание приложений Windows Communication Foundation (WCF).

- Упрощение создаваемых файлов конфигурации.

- Поддержка разработки в соответствии с парадигмой "сначала контракт".

- Упрощение настройки режима совместимости ASP.NET.

- Изменения значений свойств транспорта по умолчанию для уменьшения вероятности необходимости их настройки.

- Обновления класса <xref:System.Xml.XmlDictionaryReaderQuotas> для уменьшения вероятности того, что потребуется вручную настраивать квоты для читателей словаря XML.

- Проверка файлов конфигурации WCF силами Visual Studio в рамках процесса сборки, позволяющая выявить ошибки в конфигурации до запуска приложения.

- Новая поддержка асинхронной потоковой передачи.

- Новое сопоставление протокола HTTPS, облегчающее предоставление конечной точки по HTTPS с помощью служб IIS.

- Возможность создавать метаданные в одном документе WSDL путем добавления `?singleWSDL` к URL-адресу службы.

- Поддержка Websockets, обеспечивающая истинно двунаправленный обмен данными через порты 80 и 443 с показателями производительности, схожими с характеристиками TCP-транспорта.

- Поддержка настройки служб в коде.

- Всплывающие подсказки в редакторе XML.

- Поддержка кэширования <xref:System.ServiceModel.ChannelFactory>.

- Поддержка сжатия двоичного кодировщика.

- Поддержка UDP-транспорта, которая позволяет разработчикам писать службы, использующие обмен сообщениями по принципу "отправить и забыть". Клиент отправляет сообщение службе, но не ожидает от нее ответа.

- Возможность поддерживать несколько режимов аутентификации в одной конечной точке WCF при использовании HTTP-транспорта и безопасности транспорта.

- Поддержка служб WCF, использующих интернационализированные доменные имена (IDN).

Дополнительные сведения см. в разделе [Новые возможности в Windows Communication Foundation](https://go.microsoft.com/fwlink/?LinkId=228173).

<a name="windows_workflow_foundation" />

### <a name="windows-workflow-foundation-wf"></a>Windows Workflow Foundation (WF)

В .NET Framework 4.5 для Windows Workflow Foundation (WF) добавлено несколько новых возможностей, в том числе следующие.

- Рабочие процессы конечного автомата, впервые добавленные в .NET Framework 4.0.1 ([обновление 1 для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkID=215092)). В это обновление вошло несколько новых классов и действий, позволивших разработчикам создавать рабочие процессы конечного автомата. В .NET Framework 4.5 эти классы и действия были обновлены и теперь включают в себя следующие возможности.

  - Возможность установки точек останова на состояниях.

  - Возможность копирования и вставки переходов в конструкторе рабочих процессов.

  - Поддержка создания в конструкторе переходов с общим триггером.

  - Действия для создания рабочих процессов конечного автомата, в том числе <xref:System.Activities.Statements.StateMachine>, <xref:System.Activities.Statements.State> и <xref:System.Activities.Statements.Transition>.

- Расширенные возможности конструктора рабочих процессов, например следующие:

  - Расширенные возможности поиска рабочих процессов в Visual Studio, включая **быстрый поиск** и **поиск в файлах**.

  - Возможность автоматически создавать действие Sequence, когда к действию-контейнеру добавляется второе действие — дочерний элемент, и включать оба действия в действие Sequence.

  - Поддержка панорамирования, которая позволяет изменять видимую часть рабочего процесса без использования полос прокрутки.

  - Новое представление **Структура документа**, в котором компоненты рабочего процесса отображаются в виде древовидной структуры с возможностью выбора компонента в представлении **Структура документа**.

  - Возможность добавлять примечаний к действиям.

  - Возможность определять и использовать делегаты действий с помощью конструктора рабочих процессов.

  - Автоматическое соединение и автоматическая вставка для действий и переходов в рабочих процессах блок-схемы и конечного автомата.

- Хранение данных о состоянии представления для рабочего процесса в одном элементе в XAML-файле, чтобы данные о состоянии представления можно было легко находить и редактировать.

- Действие-контейнер NoPersistScope для предотвращения сохранения дочерних действий.

- Поддержка выражений C#:

  - Проекты рабочих процессов, в которых используется Visual Basic, будут использовать выражения Visual Basic, а проекты рабочих процессов C# будут использовать выражения C#.

  - Проекты рабочих процессов C#, созданные в Visual Studio 2010 и содержащие выражения Visual Basic, совместимы с проектами рабочих процессов C#, в которых используются выражения C#.

- Усовершенствования управления версиями:

  - Новый класс <xref:System.Activities.WorkflowIdentity>, который обеспечивает сопоставление между хранимым экземпляром рабочего процесса и его определением рабочего процесса.

  - Параллельное выполнение нескольких версий рабочего процесса в одном и том же узле, в том числе <xref:System.ServiceModel.Activities.WorkflowServiceHost>.

  - В динамическом обновлении это возможность изменять определение сохраненного экземпляра рабочего процесса.

- Разработка служб рабочего процесса в соответствии с парадигмой "сначала контракт", что обеспечивает поддержку автоматического создания действий в соответствии с существующим контрактом службы.

Дополнительные сведения см. в разделе [Новые возможности Windows Workflow Foundation](https://go.microsoft.com/fwlink/?LinkId=228176).

<a name="tailored" />

### [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]

Приложения для Магазина Windows 8.x разрабатываются для конкретных форм-факторов и в полной мере используют возможности операционной системы Windows. Предоставляется подмножество .NET Framework 4.5 или 4.5.1 для разработки приложений для Магазина Windows 8.x с использованием C# или Visual Basic. Это подмножество называется [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] и рассматривается в [обзорной статье](https://go.microsoft.com/fwlink/?LinkId=228491) в Центре разработки для Windows.

### <a name="portable-class-libraries-a-nameportable-"></a>Переносимые библиотеки классов <a name="portable" />

Проект "Переносимая библиотека классов" для Visual Studio 2012 (и более поздних версий) позволяет писать и собирать управляемые сборки, работающие на нескольких платформах .NET Framework. Используя проект "Переносимая библиотека классов", можно выбирать платформы для ориентирования (например, Windows Phone и [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]). Доступные типы и члены в проекте автоматически ограничиваются типами и членами, общими для этих платформ. Дополнительные сведения см. в статье [Переносимая библиотека классов](../../standard/cross-platform/cross-platform-development-with-the-portable-class-library.md).

## <a name="see-also"></a>См. также

- [.NET Framework и отдельные выпуски](../get-started/the-net-framework-and-out-of-band-releases.md)
- [Улучшения специальных возможностей в .NET Framework](whats-new-in-accessibility.md)
- [Новые возможности Visual Studio 2017](/visualstudio/ide/whats-new-visual-studio-2017)
- [ASP.NET](/aspnet)
- [Новые возможности C++ в Visual Studio](/cpp/what-s-new-for-visual-cpp-in-visual-studio)
