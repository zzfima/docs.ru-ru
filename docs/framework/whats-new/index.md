---
title: "Новые возможности .NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "04/07/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "новые возможности [платформа .NET Framework]"
ms.assetid: 1d971dd7-10fc-4692-8dac-30ca308fc0fa
caps.latest.revision: 292
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 287
---
# Новые возможности .NET Framework
<a name="introduction"></a>В этой статье перечислены основные новые функции и усовершенствования в следующих версиях платформы .NET Framework.  
  
 [.NET framework 4.6.2](#v462)   
 [.NET framework 4.6.1](#v461)   
 [.NET 2015 и .NET Framework 4.6](#v46)   
 [.NET framework 4.5.2](#v452)   
 [.NET framework 4.5.1](#v451)   
 [.NET framework 4.5](#core)  
  
 Данная статья не содержит исчерпывающей информации обо всех новых возможностях и может быть изменена. Общие сведения о платформе .NET Framework см. в разделе [Приступая к работе](../../../docs/framework/get-started/index.md). Поддерживаемые платформы см. в разделе [требования к системе для](../../../docs/framework/get-started/system-requirements.md). Ссылки для загрузки и инструкции по установке см. в разделе [руководство по установке](../../../docs/framework/install/guide-for-developers.md).  
  
> [!NOTE]
>  Команда .NET Framework также выпускает компоненты аппаратного с NuGet для расширения поддержки платформы и добавления новых функциональных возможностей, таких как неизменяемого коллекции и типы векторов с поддержкой SIMD. Дополнительные сведения см. в разделе [дополнительные библиотеки классов и интерфейсов API](../../../ml/index.xml) и [.NET Framework и выпуски по каналу](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md). В разделе [полный список пакетов NuGet](http://blogs.msdn.com/b/dotnet/p/nugetpackages.aspx) для платформы .NET Framework или Подпишитесь на [наш веб-канал](https://nuget.org/api/v2/curated-feeds/dotnetframework/Packages/).  
  
<a name="v462"></a>   
## <a name="introducing-the-net-framework-462"></a>Знакомство с платформой .NET Framework 4.6.2  
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] построена на платформе .NET Framework 4.6 и 4.6.1 и включает много новых исправлений и несколько новых возможностей, оставаясь высокостабильным продуктом.  
  
### <a name="downloading-and-installing-the-net-framework-462"></a>Загрузка и установка .NET Framework 4.6.2  
 Вы можете загрузить [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] в следующих местах.  
  
-   [Веб-установщик .NET framework 4.6.2](http://go.microsoft.com/fwlink/?LinkId=780597)  
  
-   [NET Framework 4.6.2 автономный установщик](http://go.microsoft.com/fwlink/?LinkId=780601)  
  
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] можно установить на платформах Windows 10, Windows 8.1, Windows 7 и соответствующих серверных платформах, начиная с Windows Server 2008 R2 с пакетом обновления 1 (SP1). Вы можете установить [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], используя как веб-установщик, так и автономный установщик. Для большинства пользователей рекомендуется использовать веб-установщик.  
  
 Вы можете указать [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] в Visual Studio 2012 или более поздней версии, установив [пакет разработчика .NET Framework 4.6.2](http://go.microsoft.com/fwlink/?LinkId=780617).  
  
### <a name="whats-new-in-the-net-framework-462"></a>Новые возможности .NET Framework 4.6.2  
 В [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] появились новые возможности в следующих областях.  
  
-   [ASP.NET](#ASPNET462)  
  
-   [Категории символов](#Strings)  
  
-   [Криптография](#Crypto462)  
  
-   [SqlClient](#SQLClient)  
  
-   [Windows Communication Foundation](#WCF)  
  
-   [Windows Presentation Foundation (WPF)](#WPF462)  
  
-   [Windows Workflow Foundation (WF)](#WF462)  
  
-   [ClickOnce](#ClickOnce)  
  
-   [Преобразование приложения WPF и Windows Forms для приложений UWP](#UWPConvert)  
  
-   [Усовершенствования отладки](#Debug462)  
  
 Для списка новых интерфейсов API, добавленного к [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], в разделе [изменений в API .NET Framework 4.6.2](https://github.com/Microsoft/dotnet/blob/master/releases/net462/dotnet462-api-changes.md) на GitHub. Список улучшения функций и исправления ошибок в [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], в разделе [изменений в API .NET Framework 4.6.2](http://go.microsoft.com/fwlink/?LinkId=708778) на GitHub.  Дополнительные сведения см. в разделе [объявляет о .NET Framework 4.6.2](https://blogs.msdn.microsoft.com/dotnet/2016/08/02/announcing-net-framework-4-6-2/) в блоге .NET.  
  
<a name="ASPNET462"></a>   
### <a name="aspnet"></a>ASP.NET  
 В [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] в ASP.NET представлены следующие улучшения.  
  
 **Улучшенная поддержка локализованные сообщения об ошибках в заметки проверки данных**  
 Модули проверки заметок к данным позволяют выполнять проверки путем добавления одного или нескольких атрибутов к свойству класса. Атрибут <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=fullName> элемент определяет текст сообщения об ошибке, если проверка не пройдена. Начиная с [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], в ASP.NET упрощена локализация сообщений об ошибках. Локализация сообщений об ошибках происходит в указанных далее случаях.  
  
1.  <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=fullName> предоставляется в атрибут проверки.  
  
2.  Файл ресурсов хранится в папке App_LocalResources.  
  
3.  Имя файла локализованных ресурсов имеет форму `DataAnnotation.Localization.{` *имя*`}.resx`, где *имя* — это имя языка и региональных параметров в формате *languageCode*`-`*код страны/области* или *languageCode*.  
  
4.  Имя ключа ресурса является строкой, назначенный <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=fullName> атрибут и его значение является локализованное сообщение об ошибке.  
  
 Например следующий атрибут заметки данных определяет культуры по умолчанию сообщение об ошибке для недопустимый рейтинг.  
  
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
  
 Затем можно создать файл ресурсов DataAnnotation.Localization.fr.resx, ключ которого является строка сообщения об ошибке, значение которого локализованное сообщение об ошибке. Файл должен находиться в `App.LocalResources` папку. Например ниже приведен ключ и его значение в сообщение об ошибке локализованного языка французский (fr).  
  
|Имя|Значение|  
|----------|-----------|  
|Оценка должна быть от 1 до 10.|Примечание LA être вместо демонстрации составляют entre 1 и 10.|  
  
 Этот файл можно затем  
  
 Кроме того, локализация заметок к данным является расширяемой. Разработчики могут подключить поставщику локализатор строки путем реализации <xref:System.Web.Globalization.IStringLocalizerProvider> интерфейс для хранения строки локализации где-нибудь кроме в файле ресурсов.  
  
 **Поддержка асинхронного выполнения с помощью поставщиков хранилища состояния сеанса**  
 Теперь ASP.NET позволяет использовать методы, возвращающие задачи, с поставщиками хранилища состояния сеанса, тем самым разрешая приложениям ASP.NET реализовывать преимущества масштабируемости асинхронных операций. Чтобы поддерживает асинхронные операции с состоянием сеанса поставщики хранилищ, ASP.NET включает новый интерфейс, <xref:System.Web.SessionState.ISessionStateModule?displayProperty=fullName>, который наследует от <xref:System.Web.IHttpModule> и позволяет разработчикам реализовать свои собственные состояния сеанса модуля и async поставщиков хранилища сеанса. Интерфейс определяется следующим образом:  
  
```csharp  
  
public interface ISessionStateModule : IHttpModule {  
    void ReleaseSessionState(HttpContext context);  
    Task ReleaseSessionStateAsync(HttpContext context);  
}  
  
```  
  
 Кроме того <xref:System.Web.SessionState.SessionStateUtility> класс включает два новых метода <xref:System.Web.SessionState.SessionStateUtility.IsSessionStateReadOnly%2A> и <xref:System.Web.SessionState.SessionStateUtility.IsSessionStateRequired%2A>, который может использоваться для поддержки асинхронных операций.  
  
 **Поддержка асинхронного поставщиков кэша вывода**  
 Начиная с [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], возвращающие задачи методы могут использоваться с поставщиками кэша вывода для реализации преимуществ масштабируемости асинхронных операций.  Поставщики, реализующие эти методы, сокращают вероятность блокировок потоков на веб-сервере и улучшают масштабируемость службы ASP.NET.  
  
 Для поддержки поставщиков кэша асинхронного вывода были добавлены следующие API:  
  
-   <xref:System.Web.Caching.OutputCacheProviderAsync?displayProperty=fullName> класс, унаследованный от класса <xref:System.Web.Caching.OutputCacheProvider?displayProperty=fullName> и позволяет разработчикам реализовать асинхронный поставщик кэша вывода.  
  
-   <xref:System.Web.Caching.OutputCacheUtility> класс, который предоставляет вспомогательные методы для настройки кэша вывода.  
  
-   18 новые методы в <xref:System.Web.HttpCachePolicy?displayProperty=fullName>класса. К ним относятся <xref:System.Web.HttpCachePolicy.GetCacheability%2A>, <xref:System.Web.HttpCachePolicy.GetCacheExtensions%2A>, <xref:System.Web.HttpCachePolicy.GetETag%2A>, <xref:System.Web.HttpCachePolicy.GetETagFromFileDependencies%2A>, <xref:System.Web.HttpCachePolicy.GetMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetNoStore%2A>, <xref:System.Web.HttpCachePolicy.GetNoTransforms%2A>, <xref:System.Web.HttpCachePolicy.GetOmitVaryStar%2A>, <xref:System.Web.HttpCachePolicy.GetProxyMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetRevalidation%2A>, <xref:System.Web.HttpCachePolicy.GetUtcLastModified%2A>, <xref:System.Web.HttpCachePolicy.GetVaryByCustom%2A>, <xref:System.Web.HttpCachePolicy.HasSlidingExpiration%2A>, и <xref:System.Web.HttpCachePolicy.IsValidUntilExpires%2A>.  
  
-   2 новые методы в <xref:System.Web.HttpCacheVaryByContentEncodings?displayProperty=fullName> класса: <xref:System.Web.HttpCacheVaryByContentEncodings.GetContentEncodings%2A> и <xref:System.Web.HttpCacheVaryByContentEncodings.SetContentEncodings%2A>.  
  
-   2 новые методы в <xref:System.Web.HttpCacheVaryByHeaders?displayProperty=fullName> класса: <xref:System.Web.HttpCacheVaryByHeaders.GetHeaders%2A> и <xref:System.Web.HttpCacheVaryByHeaders.SetHeaders%2A>.  
  
-   2 новые методы в <xref:System.Web.HttpCacheVaryByParams?displayProperty=fullName> класса: <xref:System.Web.HttpCacheVaryByParams.GetParams%2A> и <xref:System.Web.HttpCacheVaryByParams.SetParams%2A>.  
  
-   В <xref:System.Web.Caching.AggregateCacheDependency?displayProperty=fullName> класс, <xref:System.Web.Caching.AggregateCacheDependency.GetFileDependencies%2A> метод.  
  
-   В <xref:System.Web.Caching.CacheDependency>, <xref:System.Web.Caching.CacheDependency.GetFileDependencies%2A> метод.  
  
<a name="Strings"></a>   
### <a name="character-categories"></a>Категории символов  
 Символы в [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] классифицируются по [стандарт Юникод, версия 8.0.0](http://www.unicode.org/versions/Unicode8.0.0/). В [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] и [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] символы классифицировались на основе категорий символов Юникода 6.3.  
  
 Поддержка Юникода 8.0 ограничена для классификации символов, <xref:System.Globalization.CharUnicodeInfo> класса и типы и методы, которые используют его. К ним относятся <xref:System.Globalization.StringInfo> класса перегруженных <xref:System.Char.GetUnicodeCategory%2A?displayProperty=fullName> метода и [классы символов](../../../docs/standard/base-types/character-classes-in-regular-expressions.md) распознаются обработчик регулярных выражений .NET Framework.  Это изменение не влияет на сравнение и сортировку символов и строк. Они по-прежнему зависят от базовой операционной системы или в системах Windows 7 от символьных данных, предоставляемых .NET Framework.  
  
 Изменения в категории символов Юникод 6.0 к 7.0 Юникода в разделе [Юникод, версия 7.0.0](http://www.unicode.org/versions/Unicode7.0.0/) на веб-узел консорциума Юникода. Изменения из Юникода 7.0 8.0 Юникода, см. [Юникод, версия 8.0.0](http://www.unicode.org/versions/Unicode8.0.0/) на веб-узел консорциума Юникода.  
  
<a name="Crypto462"></a>   
### <a name="cryptography"></a>Шифрование  
 **Поддержка X509 сертификаты содержащего DSA FIPS 186 3**  
 В [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] добавлена поддержка DSA сертификатов X509 сертификатов, ключи которых превышают 1024-разрядное ограничение FIPS 186-2.  
  
 В дополнение к поддержке больших размеров ключей FIPS 186-3 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] позволяет использовать вычисление подписей с семейством алгоритмов хэширования SHA-2 (SHA256, SHA384 и SHA512). FIPS 186 3 осуществляется с помощью нового <xref:System.Security.Cryptography.DSACng?displayProperty=fullName> класса.  
  
 Для отражения последних изменений <xref:System.Security.Cryptography.RSA> классов в .NET Framework 4.6 и <xref:System.Security.Cryptography.ECDsa> в .NET Framework 4.6.1, <xref:System.Security.Cryptography.DSA> абстрактного базового класса в [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] имеет дополнительные методы, чтобы вызывающие его использования без приведения. Можно вызвать <xref:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPrivateKey%2A?displayProperty=fullName> метод расширения для подписывания данных, как показано в следующем примере.  
  
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
  
 И вы можете вызвать <xref:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPublicKey%2A?displayProperty=fullName> метод расширения для проверки подписанных данных, как показано в следующем примере.  
  
```csharp  
  
public static bool VerifyDataDsaSha384(byte[] data, byte[] signature, X509Certificate2 cert)  
{  
    using (DSA dsa = cert.GetDSAPublicKey())  
    {  
        return dsa.VerifyData(data, signature, HashAlgorithmName.SHA384);  
    }  
}  
  
```  
  
```  
  
 Public Shared Function VerifyDataDsaSha384(data As Byte(), signature As Byte(), cert As X509Certificate2) As Boolean  
    Using dsa As DSA = cert.GetDSAPublicKey()  
        Return dsa.VerifyData(data, signature, HashAlgorithmName.SHA384)  
    End Using  
End Function  
  
```  
  
 **Четкое входов процедур производного ключа ECDiffieHellman**  
 В .NET Framework 3.5 добавлена поддержка соглашения о ключах Диффи-Хелмана на эллиптических кривых с тремя разными процедурами формирования ключа. Входные данные и процедуры, сами, были настроены с помощью свойства на <xref:System.Security.Cryptography.ECDiffieHellmanCng> объекта. Однако поскольку не все процедуры правильно считывали каждое входное свойство, часто возникала путаница.  
  
 Чтобы устранить это [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], были добавлены следующие три метода <xref:System.Security.Cryptography.ECDiffieHellman> базового класса для более четкого представления этих подпрограмм подается на вход и их входные данные:  
  
|Метод ECDiffieHellman|Описание|  
|----------------------------|-----------------|  
|[DeriveKeyFromHash (Byte ECDiffieHellmanPublicKey HashAlgorithmName,\[\], байтов\<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyFromHash%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Security.Cryptography.HashAlgorithmName%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|Получает материал ключа с помощью формулы<br /><br /> HASH(secretPrepend || *x* || secretAppend)<br /><br /> ХЭШ (secretPrepend OrElse *x* OrElse secretAppend)<br /><br /> где *x* является результатом вычисляемого алгоритм Диффи-Хелмана EC.|  
|[DeriveKeyFromHmac (Byte ECDiffieHellmanPublicKey HashAlgorithmName,\[\], байтов\[\], байтов\<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyFromHmac%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Security.Cryptography.HashAlgorithmName%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|Получает материал ключа с помощью формулы<br /><br /> Код HMAC (hmacKey secretPrepend || *x* || secretAppend)<br /><br /> Код HMAC (hmacKey secretPrepend OrElse *x* OrElse secretAppend)<br /><br /> где *x* является результатом вычисляемого алгоритм Диффи-Хелмана EC.|  
|[DeriveKeyTls (ECDiffieHellmanPublicKey, байтов\[\], байтов\<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyTls%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|Получает материал ключа с помощью алгоритма наследования псевдослучайной функции (PRF) TLS.|  
  
 **Поддержка сохранения ключ симметричного шифрования**  
 В библиотеку шифрования Windows (CNG) добавлена поддержка для хранения постоянных симметричных ключей и использования хранящихся в оборудовании симметричных ключей. Разработчики могут применять эти возможности благодаря [!INCLUDE[net_v462](../../../includes/net-v462-md.md)].  Поскольку понятие имен ключей и поставщиков ключей зависит от реализации, для применения этой функции требуется использовать конструктор конкретных типов реализации, а не предпочтительный метод (например, вызов `Aes.Create`).  
  
 Существует поддержка сохраняется ключ симметричного шифрования AES (<xref:System.Security.Cryptography.AesCng>) и 3DES (<xref:System.Security.Cryptography.TripleDESCng>) алгоритмы. Например:  
  
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
  
 **Поддержка SignedXml хеширования SHA-2**  
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] Добавляет поддержку для <xref:System.Security.Cryptography.Xml.SignedXml> класса для методов подписи RSA-SHA256, RSA SHA384 и RSA SHA512 PKCS&#1;, а ссылка SHA256, SHA384 и SHA512 алгоритмы дайджеста.  
  
 Константы URI, публикуются в <xref:System.Security.Cryptography.Xml.SignedXml>:  
  
|Поле SignedXml|Константа|  
|---------------------|--------------|  
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA256Url>|"http://www.w3.org/2001/04/xmlenc#sha256"|  
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA256Url>|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha256"|  
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA384Url>|"http://www.w3.org/2001/04/xmldsig-more#sha384"|  
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA384Url>|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha384"|  
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA512Url>|"http://www.w3.org/2001/04/xmlenc#sha512"|  
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA512Url>|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha512"|  
  
 Все программы, которые зарегистрированы пользовательский <xref:System.Security.Cryptography.SignatureDescription> обработчик в <xref:System.Security.Cryptography.CryptoConfig> для добавления поддержки эти алгоритмы будут работать как в прошлом, однако поскольку теперь платформы по умолчанию, <xref:System.Security.Cryptography.CryptoConfig> регистрации больше не требуется.  
  
<a name="SQLClient"></a>   
### <a name="sqlclient"></a>SqlClient  
 Поставщик данных .NET framework для SQL Server (<xref:System.Data.SqlClient?displayProperty=fullName>) включает следующие новые возможности в [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]:  
  
 **Организация пулов соединений и тайм-аутов с базами данных Azure SQL**  
 Если включено объединение подключений в пул и наступает время ожидания или возникает другая ошибка входа, происходит кэширование исключения. При последующих попытках подключения для следующих 5 секунд на 1 минуту создается кэшированное исключение.  Дополнительные сведения см. в разделе [SQL пулов соединений Server (ADO.NET)](../../../docs/framework/data/adonet/sql-server-connection-pooling.md).  
  
 Это поведение является нежелательным при подключении к базам данных SQL Azure, поскольку попытки соединения могут завершиться временными ошибками, которые обычно быстро исправляются. В целях максимальной оптимизации процедуры повторных попыток подключения поведение периода блокировки пула подключений удаляется при сбое соединений с базами данных SQL Azure.  
  
 За счет добавленного нового ключевого слова `PoolBlockingPeriod` вы можете выбирать период времени блокировки, лучше всего подходящий для вашего приложения. К этим значениям относятся следующие.  
  
 `Auto`  
 Период блокировки пула подключений для приложения, которое подключается к базе данных SQL Azure, отключается, а период блокировки пула подключений для приложения, которое подключается к другому экземпляру SQL Server, включается. Это значение по умолчанию. Если имя конечной точки сервера заканчивается любой из приведенных ниже строк, она считается базой данных SQL Azure.  
  
-   .database.windows.net  
  
-   .database.chinacloudapi.cn  
  
-   .database.usgovcloudapi.net  
  
-   .database.cloudapi.de  
  
 `AlwaysBlock`  
 Период блокировки пула подключений всегда включен.  
  
 `NeverBlock`  
 Период блокировки пула подключений всегда отключен.  
  
 **Усовершенствования для всегда зашифрованы.**  
 В SQLClient представлены два усовершенствования для функции Always Encrypted.  
  
-   Для повышения производительности параметризованных запросов к зашифрованным столбцам базы данных выполняется кэширование метаданных шифрования для параметров запроса. С <xref:System.Data.SqlClient.SqlConnection.ColumnEncryptionQueryMetadataCacheEnabled%2A?displayProperty=fullName> установлено значение `true` (это значение по умолчанию), если тот же запрос вызывается несколько раз, клиент получает метаданные параметров с сервера только один раз.  
  
-   Теперь столбец записи ключей шифрования в кэше ключа вытесняются истечении интервала времени можно настроить, с использованием <xref:System.Data.SqlClient.SqlConnection.ColumnEncryptionKeyCacheTtl%2A?displayProperty=fullName> свойство.  
  
<a name="WCF"></a>   
### <a name="windows-communication-foundation"></a>Windows Communication Foundation  
 В [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] Windows Communication Foundation содержит ряд улучшений в следующих областях.  
  
 **Поддержка безопасности транспорта WCF для сертификатов, сохраненные с помощью CNG**  
 Безопасность транспорта WCF поддерживает сертификаты, сохраненные с использованием библиотеки шифрования Windows (CNG). В [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] эта поддержка ограничивается использованием сертификатов с открытым ключом, длина экспоненты которого не превышает 32 бита. Если приложение предназначено для [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], эта функция включена по умолчанию.  
  
 Для приложений, предназначенных для [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] и ОС более ранних но [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], эту функцию можно включить, добавив следующую строку в [ <> \> ](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла app.config или web.config.  
  
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
  
 **Улучшенная поддержка нескольких правил коррекции для летнего времени с помощью класса DataContractJsonSerializer**  
 Клиенты могут использовать параметр конфигурации приложения, чтобы определить, является ли <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> класс поддерживает несколько правил коррекции для одного часового пояса. Это функция, включаемая пользователем. Чтобы ее включить, добавьте следующий параметр в файл app.config:  
  
```xml  
  
<runtime>  
     <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseTimeZoneInfo=false" />  
</runtime>  
  
```  
  
 Если эта функция включена, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> объектов используют <xref:System.TimeZoneInfo> введите вместо <xref:System.TimeZone> тип для десериализации данных даты и времени. <xref:System.TimeZoneInfo> поддерживает несколько правил коррекции, что позволяет работать с историческими данными часового пояса;   <xref:System.TimeZone> — нет.  
  
 Дополнительные сведения о <xref:System.TimeZoneInfo> структуры и коррекции часового пояса в разделе [Общие сведения о часовом поясе](../../../docs/standard/datetime/time-zone-overview.md).  
  
 **Время поддержки сохранения в формате UTC, когда сериализации и десериализации с помощью класса XMLSerializer**  
 Обычно, когда <xref:System.Xml.Serialization.XmlSerializer> класс используется для сериализации в формате UTC <xref:System.DateTime> значение, он создает строку сериализованного времени, сохраняет дату и время, но предполагается, что время является локальным.  Например, при создании даты и времени в формате UTC путем вызова следующего кода:  
  
```csharp  
DateTime utc = new DateTime(2016, 11, 07, 3, 0, 0, DateTimeKind.Utc);  
```  
  
```vb  
Dim utc As New Date(2016, 11, 07, 3, 0, 0, DateTimeKind.Utc)  
```  
  
 результатом является сериализованная строка времени "03:00:00.0000000-08:00" для системных восьми часов с отставанием от времени в формате UTC.  Сериализованные значения всегда десериализуются как значения местной даты и времени.  
  
 Параметр конфигурации приложения можно использовать для определения ли <xref:System.Xml.Serialization.XmlSerializer> сохраняет данные о часовом поясе UTC при сериализации и десериализации <xref:System.DateTime> значения:  
  
```xml  
  
<runtime>  
     <AppContextSwitchOverrides   
          value="Switch.System.Runtime.Serialization.DisableSerializeUTCDateTimeToTimeAndDeserializeUTCTimeToUTCDateTime=false" />  
</runtime>  
  
```  
  
 Если эта функция включена, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> объектов используют <xref:System.TimeZoneInfo> введите вместо <xref:System.TimeZone> тип для десериализации данных даты и времени. <xref:System.TimeZoneInfo> поддерживает несколько правил коррекции, что позволяет работать с историческими данными часового пояса;   <xref:System.TimeZone> — нет.  
  
 Дополнительные сведения о <xref:System.TimeZoneInfo> структуры и коррекции часового пояса в разделе [Общие сведения о часовом поясе](../../../docs/standard/datetime/time-zone-overview.md).  
  
 **Наилучшее соответствие NetNamedPipeBinding**  
 В WCF представлен новый параметр приложения, который может быть задан в клиентских приложениях для их постоянного подключения к службе, прослушивающей URI, наилучшим образом соответствующий запрошенному. С помощью этого параметра приложение `false` (по умолчанию), это возможно для клиентов, использующих <xref:System.ServiceModel.NetNamedPipeBinding> для попытки подключения к службе, прослушивание по URI, который является подстрокой запрошенный универсальный код.  
  
 Например, клиент пытается подключиться к службе, прослушивающей `net.pipe://localhost/Service1`, но другая служба на этом компьютере, запущенная с правами администратора, прослушивает `net.pipe://localhost`. Если этому параметру приложения задать значение `false`, клиент будет пытаться подключиться не к той службе. После установки значения `true` для параметра приложения клиент будет всегда подключаться к наиболее подходящей службе.  
  
> [!NOTE]
>  Клиенты, использующие <xref:System.ServiceModel.NetNamedPipeBinding> поиск служб, основанных на базовый адрес службы (если он существует), а не полный адрес конечной точки. Чтобы обеспечить постоянную работу этого параметра, служба должна использовать уникальный базовый адрес.  
  
 Для активации этого изменения добавьте следующий параметр в файл App.config или Web.config клиентского приложения:  
  
```xml  
  
<configuration>  
    <appSettings>  
        <add key="wcf:useBestMatchNamedPipeUri" value="true" />  
    </appSettings>  
</configuration>  
  
```  
  
 **По умолчанию протокол не SSL 3.0**  
 При использовании NetTcp для обеспечения безопасности транспорта и применении типа учетных данных сертификата SSL 3.0 больше не является протоколом по умолчанию для согласования безопасного соединения. В большинстве случаев существующие приложения не должны затрагиваться, поскольку TLS 1.0 входит в список протоколов для NetTcp. Все существующие клиенты должны иметь возможность согласовывать подключение с помощью хотя бы TLS 1.0.      Если требуется Ssl3, воспользуйтесь одним из указанных ниже механизмов конфигурации и добавьте его в список установленных протоколов.  
  
-   <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols%2A?displayProperty=fullName> свойство  
  
-   <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=fullName> свойство  
  
-   The [<>\>](../../../docs/framework/configure-apps/file-schema/wcf/transport-of-nettcpbinding.md) section of the [<>\>](../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) section  
  
-   The [<>\>](../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) section of the [<>\>](../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) section  
  
<a name="WPF462"></a>   
### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)  
 В [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] Windows Presentation Foundation содержит ряд улучшений в следующих областях.  
  
 **Сортировка по группам**  
 Приложение, использующее <xref:System.Windows.Data.CollectionView> объекта для группирования данных можно явно объявить порядок сортировки групп. Явная сортировка позволяет решить проблему неочевидного упорядочивания, которая возникает, когда приложение динамически добавляет или удаляет группы или когда оно изменяет значения свойств элементов, участвующих в группировании. Она также может повысить производительность процесса создания группы путем перемещения сравнений свойств группирования из сортировки полной коллекции в сортировку групп.  
  
 Для поддержки сортировки группы, новый <xref:System.ComponentModel.GroupDescription.SortDescriptions%2A?displayProperty=fullName> и <xref:System.ComponentModel.GroupDescription.CustomSort%2A?displayProperty=fullName> свойства описывают, как сортировать коллекцию групп, созданных <xref:System.ComponentModel.GroupDescription> объекта. Эта процедура аналогична способом, аналогичным названием <xref:System.Windows.Data.ListCollectionView> свойства описывают способ сортировки элементов данных.  
  
 Два новых статических свойств <xref:System.Windows.Data.PropertyGroupDescription> класс, <xref:System.Windows.Data.PropertyGroupDescription.CompareNameAscending%2A> и <xref:System.Windows.Data.PropertyGroupDescription.CompareNameDescending%2A>, можно использовать для наиболее распространенных случаев.  
  
 Например, следующий XAML группирует данные по возрасту, сортирует возрастные группы в порядке возрастания и группирует элементы в каждой возрастной группе по фамилии.  
  
```xaml  
  
<GroupDescriptions>  
     <PropertyGroupDescription   
         PropertyName=”Age”   
         CustomSort=   
              ”{x:Static PropertyGroupDescription.CompareNamesAscending}”/>  
     </PropertyGroupDescription>  
</GroupDescriptions>  
  
<SortDescriptions>  
     <SortDescription PropertyName=”LastName”/>  
</SortDescriptions>  
  
```  
  
 **Поддержка программируемой клавиатуры**  
 Поддержка программируемой клавиатуры позволяет отслеживать фокус в приложениях WPF путем автоматического вызова и отклонения новой программируемой клавиатуры в Windows 10 при получении элементом управления, который может принимать текстовые входные данные, сигнала о сенсорном вводе.  
  
 В предыдущих версиях платформы .NET Framework приложения WPF не использовали отслеживание фокуса без отключения поддержки пера и сенсорного ввода WPF.  В результате приложения WPF должны выбрать между полной поддержкой сенсорного ввода WPF или использованием мыши Windows.  
  
 **DPI каждого монитора**  
 В целях эксплуатации во множестве сред с высоким и смешанным разрешением для приложений WPF платформа WPF в [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] включает поддержку DPI для каждого монитора. В разделе [примеры и руководство для разработчиков](https://github.com/Microsoft/WPF-Samples/tree/master/PerMonitorDPI) на GitHub Дополнительные сведения о том, как включить ваше приложение WPF станет ДЮЙМ каждого монитора.  
  
 В предыдущих версиях платформы .NET Framework приложения WPF поддерживают DPI на уровне системы. Другими словами, ОС соответствующим образом масштабирует пользовательский интерфейс приложения в зависимости от разрешения экрана монитора, на котором отображается приложение. ,  
  
 Для приложений, работающих под управлением [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], DPI каждого монитора изменений в приложениях WPF можно отключить, добавив инструкцию конфигурации для [ <> \> ](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файле раздел конфигурации приложения, как показано ниже:  
  
```xml  
  
<runtime>  
   <AppContextSwitchOverrides value=”Switch.System.Windows.DoNotScaleForDpiChanges=false”/>  
</runtime>  
  
```  
  
<a name="WF462"></a>   
### <a name="windows-workflow-foundation-wf"></a>Windows Workflow Foundation (WF)  
 В [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] Windows Workflow Foundation содержит ряд улучшений в следующих областях.  
  
 **Поддержка выражений C# и в конструкторе WF Re-hosted IntelliSense**  
 Начиная с [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], WF поддерживает выражения C# в конструкторе Visual Studio и рабочих процессах кода. Повторно размещаемый конструктор рабочих процессов является ключевой возможностью WF, позволяющей размещать конструкторы рабочих процессов в приложении вне среды Visual Studio (например, в WPF).  Windows Workflow Foundation поддерживает выражения C# и IntelliSense в повторно размещаемом конструкторе рабочих процессов. Дополнительные сведения см. в разделе [блога Windows Workflow Foundation](http://go.microsoft.com/fwlink/?LinkID=809042&clcid=0x409).  
  
 `Availability of IntelliSense when a customer rebuilds a workflow project from Visual Studio`  
 В версиях .NET Framework, более ранних, чем [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], в случае перестроения проекта рабочего процесса из Visual Studio происходит нарушение работы IntelliSense конструктора WF. При успешной сборки проекта, типов рабочих процессов не найдены в конструкторе и предупреждения из IntelliSense для недостающих типов рабочего процесса отображаются в **список ошибок** окна. В [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] эта проблема решена и IntelliSense работает.  
  
 **Приложения V1 рабочего процесса с помощью отслеживания рабочего процесса на теперь работать в режиме FIPS**  
 Теперь на компьютерах с включенным режимом поддержки стандарта FIPS можно успешно запускать приложение Workflow версии 1 с функцией отслеживания рабочих процессов. Чтобы реализовать этот сценарий, необходимо внести следующее изменение в файл app.config:  
  
```xml  
<add key="microsoft:WorkflowRuntime:FIPSRequired" value="true" />  
```  
  
 Если этот сценарий не реализован, запущенное приложение продолжает создавать исключение с сообщением "Данная реализация не является частью протестированных криптографических алгоритмов Windows Platform FIPS".  
  
 **Усовершенствования рабочего процесса при использовании динамического обновления с помощью конструктора рабочих процессов Visual Studio**  
 Конструктор рабочих процессов, конструктор действия блок-схемы и другие конструкторы действий рабочего процесса теперь успешно загрузки и отображения рабочих процессов, которые были сохранены после вызова метода <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=fullName> метод. В версиях .NET Framework до [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], загрузке XAML-файла в Visual Studio для рабочего процесса, который был сохранен после вызова метода <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=fullName> можно привести следующие вопросы:  
  
-   Конструктор рабочих процессов не удается правильно загрузить XAML-файл (если <xref:System.Activities.Presentation.ViewState.ViewStateData.Id%2A?displayProperty=fullName> находится в конце строки).  
  
-   Конструктор действия FlowChart или другие конструкторы действий рабочих процессов могут отображать все объекты в их расположениях по умолчанию в отличие от значений вложенных свойств.  
  
<a name="ClickOnce"></a>   
### <a name="clickonce"></a>ClickOnce  
 Технология ClickOnce была обновлена для поддержки протоколов TLS 1.1 и TLS 1.2 наряду с уже поддерживаемой версией 1.0. ClickOnce автоматически определяет необходимый протокол. Для включения поддержки протоколов TLS 1.1 и 1.2 в приложении ClickOnce не требуется выполнять дополнительные действия.  
  
<a name="UWPConvert"></a>   
### <a name="converting-windows-forms-and-wpf-apps-to--uwp-apps"></a>Преобразование приложений Windows Forms и приложений WPF в приложения UWP  
 Теперь Windows предоставляет возможности переноса существующих классических приложений Windows, включая приложения WPF и Windows Forms, на универсальную платформу Windows (UWP). Эта технология играет роль моста, позволяя постепенно переносить существующую базу кода на платформу UWP, переводя, тем самым, приложения на все устройства Windows 10.  
  
 Преобразованное классическое приложение получает удостоверение, аналогичное удостоверению приложения платформы UWP, которое делает доступными интерфейсы API UWP для включения функций, таких как динамические плитки и уведомления. Приложение продолжает работать как раньше и функционирует как приложение полного доверия. После преобразования приложения к существующему процессу полного доверия можно добавить процесс контейнера приложения для подключения адаптивного пользовательского интерфейса. При перемещении всех функциональных возможностей в процесс контейнера приложения можно удалить процесс полного доверия и сделать новое приложение UWP доступным для всех устройств Windows 10.  
  
<a name="Debug462"></a>   
### <a name="debugging-improvements"></a>Усовершенствования отладки  
 *Неуправляемого API отладки* было усовершенствовано в [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] проводить дополнительный анализ при <xref:System.NullReferenceException> вызывается, чтобы определить, какие переменную в одной строке исходного кода можно `null`.   Для поддержки этого сценария в неуправляемый API отладки были добавлены следующие API.  
  
-   [ICorDebugCode4](../../../ocs/framework/unmanaged-api/debugging/icordebugcode4-interface.md), [ICorDebugVariableHome](../../../ocs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md), и [ICorDebugVariableHomeEnum](../../../ocs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) интерфейсы, предоставляющие собственный домах управляемых переменных. Это позволяет отладчики провести анализ потока кода при <xref:System.NullReferenceException> происходит обратной работы для определения управляемого переменную, которая соответствует местоположению собственного, и `null`.  
  
-   [ICorDebugType2::GetTypeID](../Topic/ICorDebugType2::GetTypeID%20Method.md) метод обеспечивает сопоставление для ICorDebugType для [COR_TYPEID](../../../ocs/framework/unmanaged-api/debugging/cor-typeid-structure.md), который позволяет отладчику получить [COR_TYPEID](../../../ocs/framework/unmanaged-api/debugging/cor-typeid-structure.md) без экземпляра ICorDebugType. Существующие API на [COR_TYPEID](../../../ocs/framework/unmanaged-api/debugging/cor-typeid-structure.md) можно использовать для определения макета класса типа.  
  
<a name="v461"></a>   
## <a name="whats-new-in-the-net-framework-461"></a>Новые возможности .NET Framework 4.6.1  
 В [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] появились новые возможности в следующих областях.  
  
-   [Криптография](#Crypto)  
  
-   [ADO.NET](#ADO.NET461)  
  
-   [Windows Presentation Foundation (WPF)](#WPF461)  
  
-   [Windows Workflow Foundation](#WWF461)  
  
-   [Профилирование](#Profile461)  
  
-   [NGen](#NGEN461)  
  
 Дополнительные сведения о [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] см. в следующих разделах.  
  
-   [.NET Framework 4.6.1 список изменений](http://go.microsoft.com/fwlink/?LinkId=622964)  
  
-   [Совместимость приложений в 4.6.1](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)  
  
-   [Интерфейс API .NET Framework diff](http://go.microsoft.com/fwlink/?LinkId=622989) (в GitHub)  
  
<a name="Crypto"></a>   
### <a name="cryptography-support-for-x509-certificates-containing-ecdsa"></a>Шифрование: поддержка сертификатов X509, содержащих ECDSA  
 В .NET Framework 4.6 добавлена поддержка RSACng сертификатов X509. В [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] добавляется поддержка ECDSA (алгоритма цифровых подписей на основе эллиптических кривых) сертификатов X509.  
  
 ECDSA обеспечивает более высокую производительность и является более безопасным алгоритмом шифрования, чем RSA, предоставляя лучший выбор, когда производительность и масштабируемость TLS представляет собой проблему. Реализация .NET Framework создает оболочку для вызовов существующих функциональных возможностей Windows.  
  
 В следующем примере кода показано, как легко можно создать подпись для байтового потока, используя новую поддержку сертификатов X&509; ECDSA, включенную в [!INCLUDE[net_v461](../../../includes/net-v461-md.md)].  
  
 [!code-csharp[whatsnew.461.crypto#1](../../../samples/snippets/csharp/VS_Snippets_CLR/whatsnew.461.crypto/cs/Code46.cs#1)]
 [!code-vb[whatsnew.461.crypto#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.461.crypto/vb/Code461.vb#1)]  
  
 Это обеспечивает заметное отличие от кода, необходимого для создания подписи в .NET Framework 4.6.  
  
 [!code-csharp[whatsnew.461.crypto#2](../../../samples/snippets/csharp/VS_Snippets_CLR/whatsnew.461.crypto/cs/Code46.cs#2)]
 [!code-vb[whatsnew.461.crypto#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.461.crypto/vb/Code46.vb#2)]  
  
<a name="ADO.NET461"></a>   
### <a name="adonet"></a>ADO.NET  
 В ADO.NET добавлены следующие возможности.  
  
 Поддержка Always Encrypted (постоянного шифрования) для аппаратно защищенных ключей.  
 Теперь ADO.NET поддерживает хранение главных ключей столбца Always Encrypted непосредственно в аппаратных модулях безопасности (HSM). Благодаря этому клиенты могут использовать асимметричные ключи, хранящиеся в аппаратных модулях безопасности, без необходимости написания специальных поставщиков хранилища главных ключей и их регистрации в приложениях.  
  
 Для доступа к постоянно зашифрованным данным, защищенным с помощью главных ключей столбца, хранящихся в аппаратном модуле безопасности, клиенты должны установить на серверах приложений или клиентских компьютерах предоставленный производителем аппаратного модуля безопасности поставщик служб шифрования или поставщики хранилища ключей CNG.  
  
 Улучшить <xref:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover%2A> поведение подключения для AlwaysOn  
 SqlClient теперь автоматически обеспечивает более быстрое подключение к группе доступности (AG) AlwaysOn. Он прозрачно определяет, подключается ли ваше приложение к группе доступности AlwaysOn в другой подсети, и быстро обнаруживает текущий активный сервер и обеспечивает подключение к этому серверу. В предыдущих версиях строка подключения приложения должна была включать `“MultisubnetFailover=true”` для указания, что это приложение подключается к группе доступности AlwaysOn. При подключении приложения к группе доступности AlwaysOn без установки значения `true` для этого ключевого слова подключения время ожидания может быть превышено. В этом выпуске приложение выполняет *не* нужно установить <xref:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover%2A> для `true` больше. Дополнительные сведения о поддержке SqlClient в группах доступности AlwaysOn см. в разделе [поддержка SqlClient для высокого уровня доступности и аварийного восстановления](../../../docs/framework/data/adonet/sql/sqlclient-support-for-high-availability-disaster-recovery.md).  
  
<a name="WPF461"></a>   
### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)  
 Windows Presentation Foundation содержит ряд улучшений и изменений.  
  
 Повышение производительности  
 В [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] была исправлена задержка при срабатывании событий касания. Кроме того, введя в <xref:System.Windows.Controls.RichTextBox> управления больше не связывает поток отрисовки во время быстрого ввода.  
  
 Улучшения проверки орфографии  
 В Windows 8.1 и последующих версиях проверка орфографии в WPF была обновлена, чтобы для проверки орфографии в дополнительных языках использовалась поддержка операционной системы.  В версиях Windows, предшествующих Windows 8.1, изменения этой функциональности отсутствуют.  
  
 Как в предыдущих версиях платформы .NET Framework, язык для <xref:System.Windows.Controls.TextBox> управления ora <xref:System.Windows.Controls.RichTextBox> блока определяется поиск данных в следующем порядке:  
  
-   `xml:lang`, если имеется;  
  
-   текущий язык ввода;  
  
-   язык и региональные параметры текущего потока.  
  
 Дополнительные сведения о языковой поддержке в WPF см. в разделе [WPF в блоге на компоненты .NET Framework 4.6.1](http://go.microsoft.com/fwlink/?LinkID=691819).  
  
 Дополнительная поддержка индивидуально настраиваемых словарей  
 В [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] WPF распознает настраиваемые словари, зарегистрированные глобально. Эта возможность доступна наряду с возможностью их регистрации на уровне элемента управления.  
  
 В предыдущих версиях WPF настраиваемые словари не распознавали исключенные слова и списки автозамены. Эти возможности поддерживаются в Windows 8.1 и Windows 10 благодаря использованию файлов, которые могут быть помещены в каталог `%AppData%\Microsoft\Spelling\<language tag>`.  К этим файлам применяются следующие правила.  
  
-   Файлы должны иметь расширения DIC (для добавленных слов), EXC (для исключенных слов) или ACL (для автозамены).  
  
-   Файлы должны представлять собой открытый текст в кодировке UTF-16 LE, который начинается с метки порядка байтов (BOM).  
  
-   Каждая строка должна состоять из слов (в список добавленных и исключенных слов) или пару автозамены слова, разделенные символом вертикальной черты («|») (в автозамены список слов).  
  
-   Эти файлы считаются доступными только для чтения и не изменяются системой.  
  
> [!NOTE]
>  Эти новые форматы файлов не поддерживаются непосредственно API-интерфейсами проверки орфографии WPF, и настраиваемые словари, передаваемые в WPF в приложениях, должны продолжать использовать LEX-файлы.  
  
 Примеры  
 Существует ряд [WPF-примеры](https://msdn.microsoft.com/library/ms771633.aspx) на сайте MSDN. Более 200 наиболее популярных образцов (в зависимости от их использования) будут перенесены в [откройте источник в github](https://github.com/Microsoft/WPF-Samples). Помогите нам улучшить наши примеры, отправив нам опрашивающего запроса или открытии [GitHub проблема](https://github.com/Microsoft/WPF-Samples/issues).  
  
 Расширения DirectX  
 WPF включает [пакет NuGet](http://go.microsoft.com/fwlink/?LinkID=691342) , предоставляет новые реализации <xref:System.Windows.Interop.D3DImage> также легко взаимодействовать с DX10 и Dx11 содержимого. Код для этого пакета был открыт исходный код и доступна [на GitHub](https://github.com/Microsoft/WPFDXInterop).  
  
<a name="WWF461"></a>   
### <a name="windows-workflow-foundation-transactions"></a>Windows Workflow Foundation: транзакции  
 <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A?displayProperty=fullName> метод теперь можно использовать для продвижения транзакции диспетчера распределенных транзакций, отличных от MSDTC. Это делается путем указания идентификатора GUID просто продавать транзакции в новый <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%28System.Transactions.IPromotableSinglePhaseNotification%2CSystem.Guid%29?displayProperty=fullName> перегрузки. В случае успешного выполнения операции на возможности транзакции накладываются определенные ограничения. После прикрепления просто продавать транзакции не MSDTC, следующие методы вызывать <xref:System.Transactions.TransactionPromotionException> , так как эти методы требуют повышения MSDTC:  
  
-   <xref:System.Transactions.Transaction.EnlistDurable%2A?displayProperty=fullName>  
  
-   <xref:System.Transactions.TransactionInterop.GetDtcTransaction%2A?displayProperty=fullName>  
  
-   <xref:System.Transactions.TransactionInterop.GetExportCookie%2A?displayProperty=fullName>  
  
-   <xref:System.Transactions.TransactionInterop.GetTransmitterPropagationToken%2A?displayProperty=fullName>  
  
 После прикрепления отличного от MSDTC диспетчера транзакций он должен использоваться для будущих долговременных прикреплений с использованием протоколов, которые он задает. <xref:System.Guid> транзакции просто продавать можно получить с помощью <xref:System.Transactions.Transaction.PromoterType%2A> свойство. Когда транзакция повышает уровень, просто продавать транзакций обеспечивает <xref:System.Byte> массив, представляющий маркер повышенного уровня. Приложение может получить токен транзакции не переходят к MSDTC с повышенным уровнем <xref:System.Transactions.Transaction.GetPromotedToken%2A> метод.  
  
 Пользователи нового <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%28System.Transactions.IPromotableSinglePhaseNotification%2CSystem.Guid%29?displayProperty=fullName> перегрузки должны соответствовать конкретным вызовом последовательности в порядке для успешного завершения операции повышения роли. Эти правила описаны в документации по данному методу.  
  
<a name="Profile461"></a>   
### <a name="profiling"></a>Профилирование  
 Неуправляемый API профилирования был улучшен следующим образом.  
  
 Улучшенная поддержка доступа PDB-файлы в [ICorProfilerInfo7](../../../ocs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md) интерфейс  
 В ASP.Net 5 сборки все чаще компилируются в памяти с помощью Roslyn. Для разработчиков средств профилирования это означает, что PDB-файлы, которые ранее были сериализованы на диске, могут больше не присутствовать. Средства профилирования часто используют PDB-файлы для сопоставления кода с исходными строками для таких задач, как анализ покрытия кода или построковый анализ производительности. [ICorProfilerInfo7](../../../ocs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md) интерфейс теперь включает два новых метода [ICorProfilerInfo7::GetInMemorySymbolsLength](../Topic/ICorProfilerInfo7::GetInMemorySymbolsLength%20Method.md) и [ICorProfilerInfo7::ReadInMemorySymbols](../Topic/ICorProfilerInfo7::ReadInMemorySymbols.md), для предоставления доступа к данным PDB в памяти, эти средства профилирования с помощью новых интерфейсов API, профилировщик может получить содержимое PDB в памяти в виде массива байтов и обработать его или его сериализации на диск.  
  
 Улучшено инструментирование с использованием интерфейса ICorProfiler.  
 Профилировщики, использующие функциональность ReJit API `ICorProfiler` для динамического инструментирования, теперь могут изменять некоторые метаданные. Ранее такие средства могли инструментировать IL в любое время, но метаданные могли изменяться только во время загрузки модуля. Поскольку IL ссылается на метаданные, это ограничивает типы инструментирования, которое может выполняться. Некоторые из этих ограничений ликвидируется, добавив [ICorProfilerInfo7::ApplyMetaData](../Topic/ICorProfilerInfo7::ApplyMetaData%20Method.md) метода поддерживает подмножество изменения метаданных после модуль загружается, в частности путем добавления нового `AssemblyRef`, `TypeRef`, `TypeSpec`, `MemberRef`, `MemberSpec`, и `UserString` записей. Это изменение существенно расширяет спектр возможного динамического инструментирования.  
  
<a name="NGEN461"></a>   
### <a name="native-image-generator-ngen-pdbs"></a>PDB-файлы генератора образов в машинном коде (NGEN)  
 Трассировка событий между компьютерами позволяет клиентам профилировать программу на компьютере А и просматривать данные профилирования с сопоставлением исходных строк на компьютере Б. Используя предыдущие версии .NET Framework, пользователь может копировать все модули и образы в машинном коде из профилируемого компьютера на компьютер анализа, содержащий PDB-файл IL, для создания сопоставления "источник-машинный код". Хотя этот процесс может хорошо работать в том случае, если файлы относительно невелики, например для телефонных приложений, на настольных системах эти файлы могут быть очень большими, и на их копирование потребуется значительное время.  
  
 С помощью PDB-файлов Ngen NGen может создать PDB-файл, содержащий сопоставления "IL-машинный код" без зависимости от PDB-файла IL. В нашем сценарии трассировки событий между компьютерами, все, что требуется — копирование образа в машинном коде PDB, создаваемый на компьютере A на компьютере B и использовать [отладки API интерфейса доступа](https://msdn.microsoft.com/en-us/library/ee8x173s.aspx) для чтения сопоставление источника для IL IL PDB и сопоставление IL в машинный PDB образов в машинном коде. Объединение обоих сопоставлений обеспечивает сопоставление "источник-машинный код". Поскольку PDB-файл образа в машинном коде PDB намного меньше, чем все модули и образы в машинном коде, процесс копирования с компьютера А на компьютер Б выполняется гораздо быстрее.  
  
<a name="v46"></a>   
## <a name="whats-new-in-net-2015"></a>Новые возможности .NET 2015  
 В .NET 2015 представлены [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] и .NET Core. Некоторые функции применяются к обеим версиям, а другие — только к [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] или только к [!INCLUDE[net_core](../../../includes/net-core-md.md)].  
  
-   **ASP.NET 5**  
  
     .NET 2015 включает ASP.NET 5 — экономичную платформу .NET для создания современных облачных приложений. Платформа является модульной, поэтому вы можете включить только те функции, которые нужны в приложении. Она может быть размещена в IIS или резидентно в пользовательском процессе, и вы можете запустить приложения с разными версиями .NET Framework на одном сервере. В нее входит новая система конфигурации среды, предназначенная для развертывания облака.  
  
     MVC, веб-API и веб-страницы объединены в одну платформу, которая называется MVC 6. Вы создаете приложения ASP.NET 5 с помощью новых средств в Visual Studio 2015. Существующие приложения будут работать на новой платформе .NET Framework; однако, чтобы создать приложение с MVC 6 или SignalR 3, нужно использовать систему проектов в Visual Studio 2015.  
  
     Сведения см. в разделе [ASP.NET 5](http://go.microsoft.com/fwlink/?LinkId=518238).  
  
-   **Обновления ASP.NET**  
  
    -   **API на основе задач для списания асинхронный ответ**  
  
         ASP.NET теперь предоставляет простой интерфейс API на основе задач для списания асинхронный ответ, <xref:System.Web.HttpResponse.FlushAsync%2A?displayProperty=fullName>, позволяющая ответов были записаны на диск асинхронно с помощью языка `async/await` поддержки.  
  
    -   `Model binding supports task-returning methods`  
  
         В [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] в ASP.NET добавлена функция привязки модели, которая обеспечивает расширяемый, ориентированный на код подход к операциям с данными CRUD на страницах веб-форм и пользовательских элементов управления. Система привязки модели теперь поддерживает <xref:System.Threading.Tasks.Task>-возврат методы привязки модели. Эта функция позволяет разработчикам веб-форм сочетать преимущества масштабируемости асинхронного программирования с простотой системы привязки данных при использовании более новых версий моделей ORM, включая Entity Framework.  
  
         Асинхронная привязка модели управляется параметром конфигурации `aspnet:EnableAsyncModelBinding`.  
  
        ```  
  
        <appSettings>  
           <add key=" aspnet:EnableAsyncModelBinding" value="true|false" />  
        </appSettings>  
  
        ```  
  
         Для приложений, предназначенных для [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], по умолчанию установлено значение `true`. Для приложений, выполняющихся в [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], предназначенных для более ранних версий .NET Framework, значение по умолчанию — `false`. Включить этот режим можно, задав для параметра конфигурации значение `true`.  
  
    -   **Поддержка HTTP/2 (Windows 10)**  
  
         [HTTP/2](http://www.wikipedia.org/wiki/HTTP/2) новую версию протокола HTTP, которая обеспечивает более эффективное подключение (меньшее число приемов-передач между клиентом и сервером), приводит к нижней задержки загрузке веб-страницы для пользователей.  HTTP/2 обеспечивает максимальное преимущество для веб-страниц (по сравнению со службами), так как оптимизирует запрос различных артефактов в ходе одной операции. Поддержка HTTP/2 добавлена в ASP.NET в .NET Framework 4.6. Так как сетевые функции существуют на нескольких уровнях, для новых компонентов в Windows, IIS и ASP.NET потребовалось включить HTTP/2. Для использования HTTP/2 с ASP.NET приложение должно выполняться в Windows 10.  
  
         HTTP/2, поддерживается также и на по умолчанию для Windows 10 универсальной Windows (UWP) приложений, использующих <xref:System.Net.Http.HttpClient?displayProperty=fullName> API.  
  
         Чтобы обеспечить возможность использования [PUSH_PROMISE](http://http2.github.io/http2-spec/#PUSH_PROMISE) функции в приложениях ASP.NET, новый метод с двумя перегрузками <xref:System.Web.HttpResponse.PushPromise%28System.String%29> и <xref:System.Web.HttpResponse.PushPromise%28System.String%2CSystem.String%2CSystem.Collections.Specialized.NameValueCollection%29>, будет добавлен <xref:System.Web.HttpResponse> класса.  
  
        > [!NOTE]
        >  Хотя ASP.NET 5 поддерживает HTTP/2, поддержка функции PUSH PROMISE еще не была добавлена.  
  
         Всю работу выполняют браузер и веб-сервер (IIS в Windows). Нет необходимости перекладывать нагрузку на пользователей.  
  
         Большинство [основных браузеров поддерживают HTTP/2](http://www.wikipedia.org/wiki/HTTP/2), поэтому вполне вероятно, что пользователи смогут воспользоваться преимуществами поддержки HTTP/2, если его поддерживает ваш сервер.  
  
    -   **Поддержка протокола привязки токенов**  
  
         Корпорация Майкрософт и Google сотрудничал на новый подход к проверке подлинности, называемого [протокол привязки токенов](https://github.com/TokenBinding/Internet-Drafts). Предполагается, что маркеры проверки подлинности (в кэше браузера) могут кражи и используемый преступниками для доступа к ресурсам защищенный (например вашему банковскому счету) без помощи пароля или других конфиденциальных сведений. Новый протокол предназначен для устранения этой проблемы.  
  
         Протокол привязки токенов будет реализован в Windows 10 в качестве компонента браузера. Приложения ASP.NET будут участвовать в протоколе для подтверждения действительности токенов проверки подлинности. Реализации клиента и сервера будут обеспечивать комплексную защиту, заданную этим протоколом.  
  
    -   **Алгоритмы хеширования случайную строку**  
  
         .NET Framework 4.5 появились [случайной строки хэш-алгоритма](https://msdn.microsoft.com/library/jj152924.aspx). Однако он не поддерживается ASP.NET, так как некоторые компоненты ASP.NET зависят от стабильного хэш-кода. В [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] алгоритмы случайного хэширования строк теперь поддерживаются. Чтобы включить эту функцию, используйте параметр конфигурации `aspnet:UseRandomizedStringHashAlgorithm`.  
  
        ```  
  
        <appSettings>  
           <add key="aspnet:UseRandomizedStringHashAlgorithm" value="true|false" />  
        </appSettings>  
  
        ```  
  
-   **ADO.NET**  
  
     ADO .NET теперь поддерживает функцию «Всегда зашифровано», которая доступна в CTP-версии 2 SQL Server 2016. Благодаря функции «Всегда зашифровано» SQL Server может выполнять операции с зашифрованными данными, и, что важнее всего, ключ шифрования хранится в самом приложении в доверенной среде клиента, а не на сервере. Функция «Всегда зашифровано» защищает данные клиента, поэтому администраторы базы данных не имеют доступа к данным в формате обычного текста. Шифрование и расшифровка данных происходит прозрачно на уровне драйвера, что сводит к минимуму изменения, которые должны быть выполнены для существующих приложений. Дополнительные сведения см. в разделе [(ядро СУБД), всегда шифруются](https://msdn.microsoft.com/library/mt163865\(v=sql.130\).aspx) и [(Разработка клиентских приложений), всегда шифруются](https://msdn.microsoft.com/library/mt147923\(v=sql.130\).aspx).  
  
-   **64-разрядный компилятор JIT для управляемого кода**  
  
     В .NET Framework 4.6 представлена новая версия 64-разрядного JIT-компилятора (первоначальное кодовое имя RyuJIT). Новый 64-разрядный компилятор имеет значительно большую производительность, чем предыдущий 64-разрядный JIT-компилятор. Новый 64-разрядный компилятор включен для 64-разрядных процессов, выполняющихся на основе .NET Framework 4.6. Приложение будет работать в 64-разрядном процессе, если оно скомпилировано как 64-разрядное или AnyCPU и выполняется в 64-разрядной операционной системе. Хотя приняты все необходимые меры, чтобы обеспечить как можно более прозрачный переход на новый компилятор, возможны изменения в поведении. Мы будем благодарны за любые отзывы о проблемах, возникших при использовании нового JIT-компилятора. Свяжитесь с нами через [Microsoft Connect](http://connect.microsoft.com/) Если возникла проблема, которая может быть связана с новой 64-разрядный компилятор JIT.  
  
     Новые 64-разрядный компилятор JIT также включает SIMD средства аппаратного ускорения в сочетании с поддержкой SIMD типы в <xref:System.Numerics> пространства имен, которые могут дать хорошей производительности.  
  
-   **Улучшения загрузчика сборок**  
  
     Загрузчик сборок теперь более эффективно использует память благодаря выгрузке сборок IL после загрузки соответствующего образа NGEN. Это изменение снижает использование виртуальной памяти, что особенно полезно для больших 32-разрядных приложений (например, Visual Studio); кроме того, оно обеспечивает экономию физической памяти.  
  
-   **Изменения библиотеки базовых классов**  
  
     В [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] были добавлены многие новые API, расширив число важных сценариев. Внесены следующие изменения и дополнения.  
  
    -   **IReadOnlyCollection<> \</> \> реализации**  
  
         Дополнительные коллекции реализуют <xref:System.Collections.Generic.IReadOnlyCollection%601> например <xref:System.Collections.Generic.Queue%601> и <xref:System.Collections.Generic.Stack%601>.  
  
    -   **CultureInfo.CurrentCulture и CultureInfo.CurrentUICulture**  
  
         <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> и <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> теперь доступны для чтения и записи, а не только для чтения. Если назначить новый <xref:System.Globalization.CultureInfo> объекта к этим свойствам, а текущая культура потока, определяемый `Thread.CurrentThread.CurrentCulture` свойство и текущего пользовательского интерфейса потока определяется языком и региональными параметрами `Thread.CurrentThread.CurrentUICulture` также изменяются.  
  
    -   **Усовершенствования сбора мусора (GC)**  
  
         <xref:System.GC> теперь включает класс <xref:System.GC.TryStartNoGCRegion%2A> и <xref:System.GC.EndNoGCRegion%2A> методы, которые позволяют запретить сбор мусора во время выполнения критического пути.  
  
         Новая перегрузка <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%2CSystem.Boolean%29?displayProperty=fullName> метод позволяет вам управлять кучу небольших объектов и кучу больших объектов, очистка и сжатие или только очистка.  
  
    -   **Типы с поддержкой SIMD**  
  
         <xref:System.Numerics> пространства имен теперь включает несколько типов с поддержкой SIMD, таких как <xref:System.Numerics.Matrix3x2>, <xref:System.Numerics.Matrix4x4>, <xref:System.Numerics.Plane>, <xref:System.Numerics.Quaternion>, <xref:System.Numerics.Vector2>, <xref:System.Numerics.Vector3>, и <xref:System.Numerics.Vector4>.  
  
         Поскольку новый 64-разрядный JIT-компилятор также включает функции аппаратного ускорения SIMD, особенно значительное повышение производительности обеспечивается при использовании типов с поддержкой SIMD с новым 64-разрядным JIT-компилятором.  
  
    -   **Обновления криптографии**  
  
         <xref:System.Security.Cryptography?displayProperty=fullName> API обновляется для поддержки [API-интерфейсов криптографии Windows CNG](https://msdn.microsoft.com/library/windows/desktop/aa376214.aspx). Предыдущие версии .NET Framework полагались на полностью [более ранней версии API-интерфейсов криптографии Windows](https://msdn.microsoft.com/library/windows/desktop/aa380255.aspx) основой для <xref:System.Security.Cryptography?displayProperty=fullName> реализации. Мы получали запросы для поддержки CNG API, так как он поддерживает [современные алгоритмы шифрования](https://msdn.microsoft.com/library/windows/desktop/bb204775.aspx#suite_b_support), что очень важно для некоторых категорий приложений.  
  
         Платформа .NET Framework 4.6 включает следующие новые усовершенствования для поддержки API-интерфейсов шифрования CNG Windows.  
  
        -   Набор методов расширения для сертификатов X509, `System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)` и `System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)`, которые возвращают реализацию на основе CNG, а не реализацию на основе CAPI (по возможности). (Некоторые смарт-карты и т. д. по-прежнему требуют CAPI, и API-интерфейсы обрабатывают резервный вариант.)  
  
        -   <xref:System.Security.Cryptography.RSACng?displayProperty=fullName> класс, который предоставляет реализацию CNG алгоритма RSA.  
  
        -   Улучшения API RSA, позволяющие отказаться от обязательного приведения общих действий. Например, шифрование данных с помощью <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> объекта требуется код, аналогичный следующему в предыдущих версиях платформы .NET Framework.  
  
             [!code-csharp[WhatsNew.Casting#1](../../../samples/snippets/csharp/VS_Snippets_CLR/whatsnew.casting/cs/program.cs#1)]
             [!code-vb[WhatsNew.Casting#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.casting/vb/module1.vb#1)]  
  
             Код, использующий новые API-интерфейсы шифрования в .NET Framework 4.6, можно переписать следующим образом, чтобы избежать приведения.  
  
             [!code-csharp[WhatsNew.Casting#2](../../../samples/snippets/csharp/VS_Snippets_CLR/whatsnew.casting/cs/program.cs#2)]
             [!code-vb[WhatsNew.Casting#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.casting/vb/module1.vb#2)]  
  
    -   **Для поддержки преобразования даты и времени для времени Unix и обратно**  
  
         Были добавлены следующие новые методы <xref:System.DateTimeOffset> структуры для поддержки преобразования значений даты и времени для времени Unix и обратно:  
  
        -   <xref:System.DateTimeOffset.FromUnixTimeSeconds%2A?displayProperty=fullName>  
  
        -   <xref:System.DateTimeOffset.FromUnixTimeMilliseconds%2A?displayProperty=fullName>  
  
        -   <xref:System.DateTimeOffset.ToUnixTimeSeconds%2A?displayProperty=fullName>  
  
        -   <xref:System.DateTimeOffset.ToUnixTimeMilliseconds%2A?displayProperty=fullName>  
  
    -   **Параметры совместимости**  
  
         Новый <xref:System.AppContext> класс добавляет новый компонент совместимости, который позволяет авторам библиотек предоставлять согласованный механизм отказаться от участия в новой функциональности для пользователей. Он устанавливает слабо связанный контракт между компонентами для передачи запроса на явный отказ. Эта возможность обычно важна при внесении изменений в существующие функции. В свою очередь, режим неявного согласия для новых функциональных возможностей уже существует.  
  
         С <xref:System.AppContext>, библиотеки определяют и предоставляют параметры совместимости, а код, который зависит от их можно устанавливать эти параметры, чтобы повлиять на поведение библиотек. По умолчанию библиотеки предоставляют новые функции и изменяют их (то есть предоставляют прежние функции) только в том случае, если установлен параметр.  
  
         Приложение (или библиотека) может объявить значение переключателя (который всегда имеет <xref:System.Boolean> значение), определяемое зависимой библиотекой. Параметр всегда имеет неявное значение `false`. Установка значения `true` для параметра включает его. Явно задание значения `false` для параметра определяет новое поведение.  
  
        ```csharp  
        AppContext.SetSwitch("Switch.AmazingLib.ThrowOnException", true);  
        ```  
  
         Библиотека должна проверить, объявил ли потребитель значение параметра, а затем выполнить соответствующие действия.  
  
        ```  
  
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
           else {  
              // new code  
           }  
        }  
  
        ```  
  
         Рекомендуется использовать согласованный формат параметров, так как они представляют собой формальный контракт, предоставляемый библиотекой. Ниже приведены два очевидных формата:  
  
        -   *Switch*.* пространство имен*.* switchname*  
  
        -   *Switch*.* library*.* switchname*  
  
    -   **Изменения в шаблон асинхронного на основе задач (TAP)**  
  
         Для приложений, предназначенных для [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], <xref:System.Threading.Tasks.Task> и <xref:System.Threading.Tasks.Task%601> объекты наследуют язык и региональные параметры пользовательского интерфейса вызывающего потока. Поведение приложений на предыдущих версиях платформы .NET Framework или без определенной версии .NET Framework не затрагивается. Дополнительные сведения см. в разделе «Язык и региональные параметры и асинхронные операции на основе задач» из <xref:System.Globalization.CultureInfo> разделе, посвященном классу.  
  
         <xref:System.Threading.AsyncLocal%601?displayProperty=fullName> класс позволяет представлять внешних данных, который является локальным для данного асинхронного потока управления, такие как `async` метод. Его можно использовать для сохранения данных в разных потоках. Можно также определить метод обратного вызова получает уведомление при каждом изменении внешних данных, либо из-за <xref:System.Threading.AsyncLocal%601.Value%2A?displayProperty=fullName> свойство было изменено явно, или из-за перехода контекста потока.  
  
         Три удобные методы <xref:System.Threading.Tasks.Task.CompletedTask%2A?displayProperty=fullName>, <xref:System.Threading.Tasks.Task.FromCanceled%2A?displayProperty=fullName>, и <xref:System.Threading.Tasks.Task.FromException%2A?displayProperty=fullName>, были добавлены задачи асинхронную модель на основе (TAP) для возврата завершенных задач в определенном состоянии.  
  
         <xref:System.IO.Pipes.NamedPipeClientStream> класс теперь поддерживает асинхронное взаимодействие с ее нового <xref:System.IO.Pipes.NamedPipeClientStream.ConnectAsync%2A>. метод.  
  
    -   **EventSource теперь поддерживает запись в журнал событий**  
  
         Теперь можно использовать <xref:System.Diagnostics.Tracing.EventSource> класс журнал административные или эксплуатационные сообщения в журнал событий в дополнение к существующим сеансам ETW, созданный на компьютере. Раньше для обеспечения этих функций приходилось использовать пакет Microsoft.Diagnostics.Tracing.EventSource NuGet. Эти функции теперь встроены в .NET Framework 4.6.  
  
         Обновления пакета NuGet и .NET Framework 4.6 включают следующие функции.  
  
        -   **Динамические события**  
  
             Возможность определения событий "на лету" без создания методов событий.  
  
        -   **Полезные данные в формате RTF**  
  
             Возможность передавать массивы и классы со специальными атрибутами, а также типы-примитивы в качестве полезных данных.  
  
        -   **Отслеживание операций**  
  
             События Start и Stop помечают возникающие между ними события идентификатором, который представляет все текущие активные действия.  
  
         Для поддержки этих функций, перегруженных <xref:System.Diagnostics.Tracing.EventSource.Write%2A> был добавлен метод <xref:System.Diagnostics.Tracing.EventSource> класса.  
  
-   **Windows Presentation Foundation (WPF)**  
  
    -   **Усовершенствования HDPI**  
  
         Более эффективная поддержка HDPI в WPF в [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]. В округление макетов внесены изменения для снижения числа вхождений обрезки в элементах управления с границами. По умолчанию эта функция включена только в том случае, если ваш <xref:System.Runtime.Versioning.TargetFrameworkAttribute> имеет значение .NET 4.6.  Приложения, которые выполняются на более ранних версий платформы [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] можно выбрать новое поведение, добавив следующую строку в [ <> \> ](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла app.config:  
  
        ```  
  
        <AppContextSwitchOverrides  
        value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false"  
        />  
  
        ```  
  
         Окна WPF, разнесенные на несколько мониторов с разными параметрами DPI (настройка нескольких параметров разрешения), теперь отображаются полностью, без черных областей. Можно отключить это новое поведение, добавив следующую строку в раздел `<appSettings>` файла app.config.  
  
        ```  
  
        <add key="EnableMultiMonitorDisplayClipping" value="true"/>  
  
        ```  
  
         Поддержка автоматически загружает вправо курсор по дюйм был добавлен <xref:System.Windows.Input.Cursor?displayProperty=fullName>.  
  
    -   **Лучше касания**  
  
         Клиент сообщает о [подключение](https://connect.microsoft.com/VisualStudio/feedback/details/903760/) , touch создает непредсказуемое поведение были разрешены в [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]. Пороговое значение двойного касания для приложений Магазина Windows и приложений WPF теперь одинаково в Windows 8.1 и более поздних версий.  
  
    -   **Поддержка прозрачные дочерние окна**  
  
         WPF в [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] поддерживает прозрачные дочерние окна в Windows 8.1 и более поздних версий. Это позволяет создавать непрямоугольные и прозрачные дочерние окна в окнах верхнего уровня. Эту функцию можно включить, установив <xref:System.Windows.Interop.HwndSourceParameters.UsesPerPixelTransparency%2A?displayProperty=fullName> свойства `true`.  
  
-   **Windows Communication Foundation (WCF)**  
  
    -   **Поддержка протокола SSL**  
  
         Теперь WCF помимо SSL 3.0 и TLS 1.0 поддерживает SSL-версии TLS 1.1 и TLS 1.2 при использовании NetTcp с безопасностью транспорта и проверкой подлинности клиента. Теперь можно выбрать, какой протокол использовать, или отключить старые менее безопасные протоколы. Это можно сделать путем задания <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A> свойства или, добавив в файл конфигурации.  
  
        ```  
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
  
    -   **Отправка сообщений с помощью различных HTTP-соединений**  
  
         WCF теперь позволяет пользователям отправлять некоторые сообщения с помощью разных базовых HTTP-подключений. Это можно сделать двумя способами.  
  
        -   **С помощью префикса имени группы подключений**  
  
             Пользователи могут указать строку, которую WCF будет использовать как префикс достижения для имени группы подключений. Два сообщения с разными префиксами отправляются с помощью разных базовых HTTP-подключений. Задайте префикс, добавив пару ключ значение в сообщение <xref:System.ServiceModel.Channels.Message.Properties%2A?displayProperty=fullName> свойство. Ключ — это «HttpTransportConnectionGroupNamePrefix»; значение — желаемый префикс.  
  
        -   **Используя различные фабрики каналов**  
  
             Пользователи могут также включить функцию, которая гарантирует, что сообщения, отправляемые по каналам, созданным разными фабриками каналов, будут отправляться с помощью разных базовых HTTP-подключений. Чтобы включить эту функцию, пользователи должны самостоятельно задать для следующего параметра `appSetting` значение `true`.  
  
            ```  
  
            <appSettings>  
               <add key="wcf:httpTransportBinding:useUniqueConnectionPoolPerFactory" value="true" />  
            </appSettings>  
  
            ```  
  
-   **Windows Workflow Foundation (WWF)**  
  
     Теперь можно указать интервал (в секундах) удержания службой рабочего процесса внеочередного запроса операции при наличии незавершенной закладки "без протокола" до истечения времени ожидания запроса. Закладка "без протокола" — это закладка, которая не связана с незавершенными действиями получения. Некоторые действия создают закладки без протокола в собственной реализации, поэтому не всегда очевидно, что закладка без протокола существует. К таким действиям относятся State и Pick. Соответственно, при наличии службы рабочего процесса, реализованной с помощью конечного автомата или содержащей действие Pick, вероятнее всего, имеются закладки без протокола. Укажите интервал, добавив строку следующего вида в раздел `appSettings` файла app.config.  
  
    ```  
    <add key="microsoft:WorkflowServices:FilterResumeTimeoutInSeconds" value="60"/>  
    ```  
  
     Значение по умолчанию — 60 секунд. Если `value` имеет значение 0, внеочередные запросы немедленно отклоняются с созданием ошибки с текстом, который выглядит следующим образом.  
  
    ```Output  
    Operation 'Request3|{http://tempuri.org/}IService' on service instance with identifier '2b0667b6-09c8-4093-9d02-f6c67d534292' cannot be performed at this time. Please ensure that the operations are performed in the correct order and that the binding in use provides ordered delivery guarantees.   
    ```  
  
     Это же сообщение отображается при получении сообщения о внеочередной операции в отсутствии закладок без протокола.  
  
     Если элемент `FilterResumeTimeoutInSeconds` имеет ненулевое значение, существуют закладки без протокола и истекает интервал времени ожидания, то происходит сбой операции с сообщением об истечении времени ожидания.  
  
-   **Транзакции**  
  
     Теперь можно включить идентификатор распределенной транзакции для транзакции, которая вызвала исключение, производного от <xref:System.Transactions.TransactionException> исключение. Это можно сделать, добавив следующий ключ в раздел `appSettings` файла app.config:  
  
    ```  
    <add key="Transactions:IncludeDistributedTransactionIdInExceptionMessage" value="true"/>   
    ```  
  
     Значение по умолчанию — `false`.  
  
-   **Сетевые подключения**  
  
    -   **Повторное использование сокета**  
  
         Windows 10 включает новый алгоритм сетевых подключений с высокой масштабируемостью, который повышает эффективность использования ресурсов компьютера путем повторного использования локальных портов для исходящих TCP-подключений. .NET Framework 4.6 поддерживает новый алгоритм, который позволяет приложениям .NET воспользоваться преимуществами нового режима работы. В предыдущих версиях Windows существовало искусственно заданное ограничение числа параллельных подключений (обычно 16 384, размер динамического диапазона портов по умолчанию), которое могло ограничивать масштабируемость службы, вызывая нехватку портов при высокой загрузке.  
  
         В [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] добавлены два новых API, которые обеспечивают повторное использование портов и эффективно снимают ограничение параллельных подключений в 64 000.  
  
        -   <xref:System.Net.Sockets.SocketOptionName?displayProperty=fullName> значение перечисления.  
  
        -   <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=fullName> свойство.  
  
         По умолчанию <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=fullName> свойство `false` Если `HWRPortReuseOnSocketBind` значение `HKLM\SOFTWARE\Microsoft\.NETFramework\v4.0.30319` раздел реестра имеет значение 0x1. Чтобы включить локальный порт повторное использование подключений HTTP, задайте <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=fullName> свойства `true`. В результате все исходящие подключения сокета TCP от <xref:System.Net.Http.HttpClient> и <xref:System.Net.HttpWebRequest> использовать новый параметр сокета Windows 10, [SO_REUSE_UNICASTPORT](https://msdn.microsoft.com/library/windows/desktop/ms740532.aspx), который позволяет повторно использовать локальный порт.  
  
         Можно указать только для сокетов приложений разработчики <xref:System.Net.Sockets.SocketOptionName?displayProperty=fullName> параметра при вызове метода, такие как <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=fullName> , чтобы исходящий сокеты повторно использовать локальные порты во время привязки.  
  
    -   **Поддержка международных доменных имен и PunyCode**  
  
         Новое свойство <xref:System.Uri.IdnHost%2A>, будет добавлен <xref:System.Uri> класса, чтобы улучшить поддержку международных доменных имен и PunyCode.  
  
-   **Изменение размеров элементов управления Windows Forms.**  
  
     Эта функция была расширена в [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] для включения <xref:System.Windows.Forms.DomainUpDown>, <xref:System.Windows.Forms.NumericUpDown>, <xref:System.Windows.Forms.DataGridViewComboBoxColumn>, <xref:System.Windows.Forms.DataGridViewColumn> и <xref:System.Windows.Forms.ToolStripSplitButton> типы и прямоугольник, задаваемый параметром <xref:System.Drawing.Design.PaintValueEventArgs.Bounds%2A> свойством, используемым при рисовании <xref:System.Drawing.Design.UITypeEditor>.  
  
     Это функция, включаемая пользователем. Чтобы ее включить, задайте для элемента `EnableWindowsFormsHighDpiAutoResizing` в файле конфигурации приложения (app.config) значение `true`:  
  
    ```  
  
    <appSettings>  
       <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />  
    </appSettings>  
  
    ```  
  
-   **Поддержка кодовых страниц**  
  
     [!INCLUDE[net_core](../../../includes/net-core-md.md)] в первую очередь поддерживает кодировки Юникод и по умолчанию предоставляет ограниченную поддержку для кодировок кодовых страниц. Можно добавить поддержку для кодировок кодовых страниц, доступных в .NET Framework, но не поддерживаются в [!INCLUDE[net_core](../../../includes/net-core-md.md)] путем регистрации кодировок кодовых страниц в <xref:System.Text.Encoding.RegisterProvider%2A?displayProperty=fullName> метод. Дополнительные сведения см. в разделе [System.Text.CodePagesEncodingProvider](https://msdn.microsoft.com/en-us/library/system.text.codepagesencodingprovider.aspx).  
  
-   **Машинный код .NET**  
  
     Приложения Windows для Windows 10, ориентированные на [!INCLUDE[net_core](../../../includes/net-core-md.md)] и написанные на языке C# или Visual Basic, могут воспользоваться преимуществами новой технологии, компилирующей приложения в машинный код, а не в IL-код. Они создают приложения, которым присуща более быстрая загрузка и время выполнения. Дополнительные сведения см. в разделе [компиляция приложений с помощью .NET Native](../../../docs/framework/net-native/index.md). Общие сведения о .NET Native рассмотрение его отличий от компиляции JIT и NGEN и означает для кода, в разделе [.NET Native и компиляция](../../../docs/framework/net-native/net-native-and-compilation.md).  
  
     Приложения компилируются в машинный код по умолчанию, если компиляция выполняется с помощью Visual Studio 2015. Дополнительные сведения см. в разделе [Приступая к работе с .NET Native](../../../docs/framework/net-native/getting-started-with-net-native.md).  
  
     Для поддержки отладки приложений .NET Native в  интерфейс API отладки неуправляемого кода добавлено несколько новых интерфейсов и перечислений. Дополнительные сведения см. в разделе [Отладка (ссылка неуправляемого API)](../../../ml/index.xml) раздела.  
  
-   **Пакеты .NET Framework с открытым исходным кодом**  
  
     [!INCLUDE[net_core](../../../includes/net-core-md.md)]пакетов, таких как неизменяемые коллекции [интерфейсы API SIMD](http://go.microsoft.com/fwlink/?LinkID=518639), и в сетевых API-интерфейсов, например <xref:System.Net.Http> пространства имен теперь доступны как пакеты с открытым исходным кодом на [GitHub](https://github.com/). Для доступа к коду, в разделе [NetFx на GitHub](http://go.microsoft.com/fwlink/?LinkID=518634). Дополнительные сведения и как пакетов см. [.NET Core с открытым исходным кодом](../../../docs/framework/get-started/net-core-and-open-source.md), [Домашняя страница .NET на GitHub](http://go.microsoft.com/fwlink/?LinkID=518635).  
  
 [В начало](#introduction)  
  
<a name="v452"></a>   
## <a name="whats-new-in-the-net-framework-452"></a>Новые возможности .NET Framework 4.5.2  
  
-   **Новые API для приложений ASP.NET.** Новый <xref:System.Web.HttpResponse.AddOnSendingHeaders%2A?displayProperty=fullName> и <xref:System.Web.HttpResponseBase.AddOnSendingHeaders%2A?displayProperty=fullName> методы позволяют проверять и изменять коды состояния и заголовки ответов при передаче ответа в клиентское приложение. Рассмотрите возможность использования этих методов вместо <xref:System.Web.HttpApplication.PreSendRequestHeaders> и <xref:System.Web.HttpApplication.PreSendRequestContent> события; они являются более эффективным и надежным.  
  
     <xref:System.Web.Hosting.HostingEnvironment.QueueBackgroundWorkItem%2A?displayProperty=fullName> позволяет планировать небольшие фоновые рабочие элементы. ASP.NET отслеживает эти элементы и блокирует резкое прерывание службами IIS рабочего процесса до выполнения всех фоновых рабочих элементов. Этот метод нельзя вызвать за пределами управляемого домена приложений ASP.NET.  
  
     Новый <xref:System.Web.HttpResponse.HeadersWritten?displayProperty=fullName> и <xref:System.Web.HttpResponseBase.HeadersWritten?displayProperty=fullName> свойства возвращают логические значения, которые указывают, были ли записаны заголовки ответа. Можно использовать эти свойства чтобы убедиться, что вызовы API, такие как <xref:System.Web.HttpResponse.StatusCode%2A?displayProperty=fullName> (создает исключения, если заголовки записаны) будет выполнена успешно.  
  
-   **Изменение размеров элементов управления Windows Forms.** Эта функция была расширена. Теперь системный параметр DPI можно использовать для изменения размера компонентов следующих дополнительных элементов управления (например, стрелки, раскрывающей поле со списком):  
  
     <xref:System.Windows.Forms.ComboBox>   
     <xref:System.Windows.Forms.ToolStripComboBox>   
     <xref:System.Windows.Forms.ToolStripMenuItem>   
     <xref:System.Windows.Forms.Cursor>   
     <xref:System.Windows.Forms.DataGridView>   
     <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
  
     Это функция, включаемая пользователем. Чтобы ее включить, задайте для элемента `EnableWindowsFormsHighDpiAutoResizing` в файле конфигурации приложения (app.config) значение `true`:  
  
    ```  
    <appSettings>  
       <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />  
    </appSettings>  
    ```  
  
-   **Новая функция рабочего процесса.** Диспетчер ресурсов, который использует <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A> метод (и следовательно, реализующий <xref:System.Transactions.IPromotableSinglePhaseNotification> интерфейс) может использовать новый <xref:System.Transactions.Transaction.PromoteAndEnlistDurable%2A?displayProperty=fullName> метод для запроса следующих:  
  
    -   повышение транзакции до уровня "координатор распределенных транзакций (Майкрософт)" (MSDTC);  
  
    -   Замените <xref:System.Transactions.IPromotableSinglePhaseNotification> с <xref:System.Transactions.ISinglePhaseNotification>, который является устойчивым перечислением, поддерживающим однофазной фиксации.  
  
     Эту операцию можно выполнить в том же домене приложения; для повышения уровня не требуется написание дополнительного неуправляемого кода для взаимодействия с MSDTC. Новый метод может вызываться только при наличии ожидающего выполнения вызова от <xref:System.Transactions?displayProperty=fullName> для <xref:System.Transactions.IPromotableSinglePhaseNotification> `Promote` метода, который реализован, поддерживающим повышение уровня.  
  
-   **Усовершенствования профилирования.** Следующие новые неуправляемые API профилирования обеспечивают более надежное профилирование:  
  
     [Структура COR_PRF_ASSEMBLY_REFERENCE_INFO](../../../ocs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md)   
     [Перечисление COR_PRF_HIGH_MONITOR](../../../ocs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md)   
     [Метод GetAssemblyReferences](../Topic/ICorProfilerCallback6::GetAssemblyReferences%20Method.md)   
     [Метод GetEventMask2](../Topic/ICorProfilerInfo5::GetEventMask2%20Method.md)   
     [Метод SetEventMask2](../Topic/ICorProfilerInfo5::SetEventMask2%20Method.md)   
     [Метод AddAssemblyReference](../Topic/ICorProfilerAssemblyReferenceProvider::AddAssemblyReference%20Method.md)  
  
     Предыдущие реализации `ICorProfiler` поддерживали отложенную загрузку зависимых сборок. Новые API профилирования требуют немедленной доступности для загрузки вставляемых профилировщиком зависимых сборок вместо их загрузки после полной инициализации приложения. Это изменение не влияет на пользователей существующих API `ICorProfiler`.  
  
-   **Усовершенствования отладки.** Следующие новые интерфейсы API отладки неуправляемого кода обеспечивают более эффективную интеграцию с профилировщиком. Теперь можно получить доступ к метаданным, вставленным профилировщиком, а также к локальным переменным и коду, созданным запросами компилировщика ReJIT во время отладки дампа.  
  
     [Метод SetWriteableMetadataUpdateMode](../Topic/ICorDebugProcess7::SetWriteableMetadataUpdateMode%20Method.md)   
     [Метод EnumerateLocalVariablesEx](../Topic/ICorDebugILFrame4::EnumerateLocalVariablesEx%20Method.md)   
     [Метод GetLocalVariableEx](../Topic/ICorDebugILFrame4::GetLocalVariableEx%20Method.md)   
     [Метод GetCodeEx](../Topic/ICorDebugILFrame4::GetCodeEx%20Method.md)   
     [Метод GetActiveReJitRequestILCode](../Topic/ICorDebugFunction3::GetActiveReJitRequestILCode%20Method.md)   
     [Метод GetInstrumentedILMap](../Topic/ICorDebugILCode2::GetInstrumentedILMap%20Method.md)  
  
-   **Изменения трассировки событий.** Платформа .NET Framework 4.5.2 поддерживает внепроцессную трассировку действий, основанную на трассировке событий Windows (ETW), для более крупных контактных зон. Это позволяет поставщикам решений автоматического управления питанием (АРМ) предлагать облегченные средства, точно отслеживающие стоимость отдельных запросов и действий в разных потоках.  Эти события вызываются только при включении их контроллерами ETW. Таким образом, изменения не влияют на ранее написанный код ETW или код, который выполняется при отключенной трассировке ETW.  
  
-   **Повышение транзакции и преобразования его в долговременное присоединение**  
  
     <xref:System.Transactions.Transaction.PromoteAndEnlistDurable%2A?displayProperty=fullName> новый интерфейс API добавляется к .NET Framework 4.5.2 и 4.6:  
  
    ```  
  
    [System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]  
    public Enlistment PromoteAndEnlistDurable(Guid resourceManagerIdentifier,  
                                              IPromotableSinglePhaseNotification promotableNotification,  
                                              ISinglePhaseNotification enlistmentNotification,  
                                              EnlistmentOptions enlistmentOptions)  
  
    ```  
  
     Метод может использоваться прикрепления, ранее созданные <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A?displayProperty=fullName> в ответ на <xref:System.Transactions.ITransactionPromoter.Promote%2A?displayProperty=fullName> метод. Он запрашивает у `System.Transactions` повышение уровня транзакции до транзакции MSDTC и "преобразование" зачисления, допускающего повышение уровня, в зачисление устойчивых ресурсов. После успешного завершения этого метода <xref:System.Transactions.IPromotableSinglePhaseNotification> интерфейс больше не ссылаются по `System.Transactions`, и все будущие уведомления будут доставлены на указанных <xref:System.Transactions.ISinglePhaseNotification> интерфейса. Рассматриваемое зачисление должно работать как зачисление устойчивых ресурсов, поддерживая ведение журнала транзакций и восстановления. Обратитесь к <xref:System.Transactions.Transaction.EnlistDurable%2A?displayProperty=fullName> подробные сведения. Кроме того, должен поддерживать перечисления <xref:System.Transactions.ISinglePhaseNotification>.  Этот метод может *только* вызываться во время обработки <xref:System.Transactions.ITransactionPromoter.Promote%2A?displayProperty=fullName> вызова. Если это не так, <xref:System.Transactions.TransactionException> исключения.  
  
 [В начало](#introduction)  
  
<a name="v451"></a>   
## <a name="whats-new-in-the-net-framework-451"></a>Новые возможности .NET Framework 4.5.1  
 **Обновления апреля 2014**:  
  
-   [Visual Studio 2013 обновление 2](http://go.microsoft.com/fwlink/p/?LinkId=393658) содержит обновленные шаблоны переносимой библиотеки классов для поддержки следующих сценариев:  
  
    -   Возможность использовать API среды выполнения Windows в переносимых библиотеках, предназначенных для Windows 8.1, Windows Phone 8.1 и Windows Phone Silverlight 8.1.  
  
    -   возможность включить XAML-код (типы Windows.UI.XAML) в переносимые библиотеки, предназначенные для Windows 8.1 или Windows Phone 8.1. Поддерживаются следующие шаблоны XAML: "Пустая страница", "Словарь ресурсов", "Шаблонный элемент управления" и "Пользовательский элемент управления".  
  
    -   Можно создать переносной компонент среды выполнения Windows (WINMD-файл) для использования в приложениях магазинов, предназначенных для Windows 8.1 и Windows Phone 8.1.  
  
    -   Можно изменить целевую платформу библиотеки классов Магазина Windows или Магазина Windows Phone, такой как переносимая библиотека классов.  
  
     Дополнительные сведения об этих изменениях см. в разделе [переносимой библиотеки классов](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md).  
  
-   Набор содержимого .NET Framework теперь включает документацию для [!INCLUDE[net_native](../../../includes/net-native-md.md)], технологии предварительной компиляции для сборки и развертывания приложений Windows. [!INCLUDE[net_native](../../../includes/net-native-md.md)] компилирует приложения напрямую в машинный код, а не в промежуточный язык (IL), что повышает производительность. Дополнительные сведения см. в разделе [компиляция приложений с помощью .NET Native](../../../docs/framework/net-native/index.md).  
  
-   [.NET Framework Reference Source](http://referencesource.microsoft.com/) предоставляет новые возможности навигации и расширенные возможности. Теперь можно просматривать исходный код .NET Framework в Интернете, [справочник](http://referencesource.microsoft.com/download.html) для автономного просмотра и пошагово просматривать источники (включая исправления и обновления) во время отладки. Дополнительные сведения см. в записи блога [новый внешний вид .NET Reference Source](http://blogs.msdn.com/b/dotnet/archive/2014/02/24/a-new-look-for-net-reference-source.aspx).  
  
 Основные новые функции и улучшения в .NET Framework 4.5.1 включают следующие:  
  
-   Автоматическая переадресация привязки для сборок. Начиная с [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)], при компиляции приложения, ориентированного на [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], в файл конфигурации приложения можно добавить переадресации привязок, если приложение или его компоненты ссылаются на несколько версий одной и той же сборки. Включить эту функцию также можно для проектов, предназначенных для более ранних версий платформы .NET Framework. Дополнительные сведения см. в разделе [Практическое руководство: Включение и отключение автоматического перенаправления привязки](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md).  
  
-   Возможность сбора диагностической информации, чтобы помочь разработчикам повысить производительность серверных и облачных приложений. Дополнительные сведения см. в разделе <xref:System.Diagnostics.Tracing.EventSource.WriteEventWithRelatedActivityId%2A> и <xref:System.Diagnostics.Tracing.EventSource.WriteEventWithRelatedActivityIdCore%2A> методы в <xref:System.Diagnostics.Tracing.EventSource> класса.  
  
-   Возможность явно уплотнять кучу больших объектов во время сборки мусора. Дополнительные сведения см. в разделе <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=fullName> свойство.  
  
-   Дополнительные улучшения производительности, например приостановка приложений ASP.NET, усовершенствования многоядерного JIT и более быстрый запуск приложений после обновления платформы .NET Framework. Дополнительные сведения см. в разделе [.NET Framework 4.5.1 объявления](http://blogs.msdn.com/b/dotnet/archive/2013/06/26/announcing-the-net-framework-4-5-1-preview.aspx) и [приостановки приложения ASP.NET](http://blogs.msdn.com/b/dotnet/archive/2013/10/09/asp-net-app-suspend-responsive-shared-net-web-hosting.aspx) записи блога.  
  
 Усовершенствования в Windows Forms включают следующие:  
  
-   Изменение размеров элементов управления Windows Forms. Системный параметр DPI можно использовать для изменения размера компонентов элементов управления (например, значков, которые отображаются в сетке свойств) путем явного включения с помощью записи в файле конфигурации приложения (app.config) нужного приложения. Эта функция в настоящее время поддерживается для следующих элементов управления Windows Forms:  
  
     <xref:System.Windows.Forms.PropertyGrid>   
     <xref:System.Windows.Forms.TreeView>   
     Некоторые аспекты <xref:System.Windows.Forms.DataGridView> (см. [новых возможностях 4.5.2](#v452) поддерживается дополнительных элементов управления)  
  
     Чтобы включить эту функцию, добавьте новый <> \> элемент в файл конфигурации (app.config) и задайте `EnableWindowsFormsHighDpiAutoResizing` элемент `true`:  
  
    ```  
    <appSettings>  
       <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />  
    </appSettings>  
    ```  
  
 В число улучшений в области отладки приложений .NET Framework в [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] входят следующие:  
  
-   Возвращаемые значения в отладчике Visual Studio. При отладке управляемого приложения в [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] в окне "Видимые" отображаются возвращаемые типы и значения для методов. Эти сведения доступны для приложений для настольных систем, приложений для Магазина Windows и приложений Windows Phone. Дополнительные сведения см. в разделе [изучите возвращаемых значений из вызовов методов](http://msdn.microsoft.com/library/e3245b37-8e2e-4200-ba84-133726e95f1f\(v=vs.120\).aspx) в библиотеке MSDN.  
  
-   "Изменить и продолжить" для 64-разрядных приложений. [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] поддерживает команду "Изменить и продолжить" для 64-разрядных управляемых приложений для настольных систем, приложений Магазина Windows и приложений Windows Phone. Существующие ограничения остаются в силе для 32-разрядных и 64-разрядных приложений (см. последний раздел [поддерживаемые изменения кода (C#)](http://msdn.microsoft.com/library/ms164927\(v=vs.120\).aspx) статьи).  
  
-   Отладка с поддержкой асинхронности. Чтобы упростить отладку асинхронных приложений в [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)], в стеке вызовов скрывается код инфраструктуры, предоставляемый компиляторами для поддержки асинхронного программирования, а также цепочки логических родительских кадров, что упрощает прослеживание логики выполнения программы. В окне "Задачи", которое заменяет собой окно "Параллельные задачи", отображаются задачи, относящиеся к определенной точке останова, а также все другие задачи, которые в данный момент активны или запланированы в приложении. Можно прочитать об этой функции в разделе «Async отладка с поддержкой» [.NET Framework 4.5.1 объявления](http://blogs.msdn.com/b/dotnet/archive/2013/06/26/announcing-the-net-framework-4-5-1-preview.aspx).  
  
-   Усовершенствованная поддержка исключений для компонентов среды выполнения Windows. В [!INCLUDE[win81](../../../includes/win81-md.md)] исключения, возникающие в приложениях для Магазина Windows, сохраняют сведения об ошибке, которая вызвала исключение, даже при переходе через границу языка. Об этой функции в разделе «Разработка приложений для магазина Windows» можно прочитать [.NET Framework 4.5.1 объявления](http://blogs.msdn.com/b/dotnet/archive/2013/06/26/announcing-the-net-framework-4-5-1-preview.aspx).  
  
 Начиная с [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)], можно использовать [управляемых средство профильной оптимизации (Mpgo.exe)](../../../docs/framework/tools/mpgo-exe-managed-profile-guided-optimization-tool.md) для оптимизации [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] приложений, а также настольных приложений.  
  
 Новые возможности ASP.NET 4.5.1 см. [ASP.NET 4.5.1 и Visual Studio 2013](http://go.microsoft.com/fwlink/?LinkID=309094) на веб-сайте ASP.NET.  
  
 [В начало](#introduction)  
  
<a name="core"></a>   
## <a name="whats-new-in-the-net-framework-45"></a>Новые возможности .NET Framework 4.5  
  
### <a name="core-new-features-and-improvements"></a>Основные новые функции и усовершенствования  
  
-   Возможность уменьшения количества перезапусков системы путем обнаружения и закрытия приложений .NET Framework 4 во время развертывания. В разделе [уменьшение числа перезагрузок при установке .NET Framework 4.5](../../../docs/framework/deployment/reducing-system-restarts.md).  
  
-   Поддержка массивов, размер которых превышает 2 ГБ, на 64-разрядных платформах. Эту функцию можно включить в файле конфигурации приложения. В разделе [ <> \> элемент](../../../docs/framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md), в котором также перечислены другие ограничения на размер объекта и размер массива.  
  
-   Улучшенная производительность благодаря фоновой сборке мусора для серверов. При использовании серверной сборки мусора в [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] фоновая сборка мусора включается автоматически. В разделе фоновая сборка мусора сервера [основы сборки мусора](../../../docs/standard/garbage-collection/fundamentals.md) раздела.  
  
-   Фоновая компиляция по требованию (JIT), которая доступна по выбору на многоядерных процессорах для повышения производительности приложения. В разделе <xref:System.Runtime.ProfileOptimization>.  
  
-   Возможность ограничения времени, в течение которого обработчик регулярных выражений будет пытаться разрешить регулярное выражение до истечения срока действия выражения. В разделе <xref:System.Text.RegularExpressions.Regex.MatchTimeout%2A?displayProperty=fullName> свойство.  
  
-   Возможность определить язык и региональные параметры по умолчанию для домена приложения. В разделе <xref:System.Globalization.CultureInfo> класса.  
  
-   Консольная поддержка кодировки Юникод (UTF-16). В разделе <xref:System.Console> класса.  
  
-   Поддержка управления версиями данных сортировки и сравнения строк, зависящих от языка и региональных параметров. В разделе <xref:System.Globalization.SortVersion> класса.  
  
-   Улучшенная производительность при извлечении ресурсов. В разделе [упаковка и развертывание ресурсов](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md).  
  
-   Усовершенствования в области сжатия ZIP, позволяющие уменьшить размер сжатого файла. В разделе <xref:System.IO.Compression?displayProperty=fullName> пространства имен.  
  
-   Возможность настраивать контекст отражения для переопределения поведения отражения по умолчанию с помощью <xref:System.Reflection.Context.CustomReflectionContext> класса.  
  
-   Поддержка версии 2008 интернационализированных доменных имен в приложениях (IDNA) Если стандартная <xref:System.Globalization.IdnMapping?displayProperty=fullName> класс используется на [!INCLUDE[win8](../../../includes/win8-md.md)].  
  
-   Делегирование сравнения строк операционной системе, которая реализует Юникод 6.0, при использовании .NET Framework в [!INCLUDE[win8](../../../includes/win8-md.md)]. При работе на других платформах .NET Framework включает собственные данные сравнения строк, которые реализуют Юникод 5.x. В разделе <xref:System.String> класс и «примечания» <xref:System.Globalization.SortVersion> класса.  
  
-   Возможность вычисления хэш-кодов для строк для каждого домена приложения. See [<>\> Element](../../../docs/framework/configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md).  
  
-   Разделить между поддержка отражения типов <xref:System.Type> и <xref:System.Reflection.TypeInfo> классы. В разделе [отражение в .NET Framework для магазина Windows](../../../docs/framework/reflection-and-codedom/reflection-for-windows-store-apps.md).  
  
### <a name="managed-extensibility-framework-mef"></a>Managed Extensibility Framework (MEF)  
 В [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] в Managed Extensibility Framework (MEF) предусмотрены следующие новые возможности:  
  
-   Поддержка универсальных типов.  
  
-   Модель программирования на основе соглашений, позволяющая создавать части на основе соглашений об именах, а не на основе атрибутов.  
  
-   Множественные области действия.  
  
-   Подмножество MEF, которое можно использовать при создании приложений [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]. Это подмножество доступно как [загружаемый пакет](http://go.microsoft.com/fwlink/?LinkId=256238) из галереи NuGet. Чтобы установить пакет, откройте проект в Visual Studio, выберите **управление пакетами NuGet** из **проекта** меню и выполните поиск `Microsoft.Composition` пакета.  
  
 Дополнительные сведения см. в разделе [Managed Extensibility Framework (MEF)](../../../docs/framework/mef/index.md).  
  
### <a name="asynchronous-file-operations"></a>Асинхронные операции с файлами  
 В [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] в языки C# и Visual Basic были добавлены новые асинхронные возможности. Эти возможности представляют собой модель на основе задач для выполнения асинхронных операций. Для использования этой новой модели используйте асинхронные методы в классах ввода-вывода. В разделе [асинхронных операций файлового ввода-вывода](../../../docs/standard/io/асинхронный-файловый-ввод-вывод.md).  
  
<a name="tools"></a>   
### <a name="tools"></a>Инструменты  
 В [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] генератор файлов ресурсов (Resgen.exe) позволяет создать RESW-файл для использования в приложениях [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] из RESOURCES-файла, внедренного в сборку .NET Framework. Дополнительные сведения см. в разделе [Resgen.exe (генератор файлов ресурсов)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md).  
  
 Средство управляемой оптимизации с использованием профиля (Mpgo.exe) позволяет сократить время запуска приложения, улучшить использование памяти (размер рабочего множества) и пропускную способность путем оптимизации сборок машинных образов. Этот инструмент командной строки формирует данные профилирования для сборок машинного образа приложения. В разделе [Mpgo.exe (управляемые средство профильной оптимизации)](../../../docs/framework/tools/mpgo-exe-managed-profile-guided-optimization-tool.md). Начиная с [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)], можно использовать средство Mpgo.exe для оптимизации приложений [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], а также приложений для настольных систем.  
  
<a name="parallel"></a>   
### <a name="parallel-computing"></a>Параллельные вычисления  
 В [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] предусмотрено несколько новых возможностей и усовершенствований для параллельных вычислений. К ним относятся повышение производительности, повышение управляемости, улучшенная поддержка асинхронного программирования, новая библиотека потоков данных и улучшенная поддержка параллельной отладки и анализа производительности. См. в записи [новые возможности для параллелизма в .NET 4.5](http://go.microsoft.com/fwlink/?LinkId=235061) в параллельному программированию в блоге .NET.  
  
<a name="web"></a>   
### <a name="web"></a>Интернет  
 В ASP.NET 4.5 и 4.5.1 добавилась привязка модели для Web Forms, поддержка WebSocket, асинхронные обработчики, усовершенствования для повышения производительности и многие другие возможности. Дополнительные сведения см. в следующих ресурсах:  
  
-   [ASP.NET 4.5 и Visual Studio 2012](../Topic/ASP.NET%20Core%20and%20Visual%20Studio%202015.md) в библиотеке MSDN.  
  
-   [ASP.NET 4.5.1 и Visual Studio 2013](http://go.microsoft.com/fwlink/?LinkID=309094) на веб-сайте ASP.NET.  
  
<a name="networking"></a>   
### <a name="networking"></a>Сеть  
 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] предоставляет новый интерфейс программирования для приложений HTTP. Дополнительные сведения см. в разделе новый <xref:System.Net.Http?displayProperty=fullName> и <xref:System.Net.Http.Headers?displayProperty=fullName> пространства имен.  
  
 Поддержка нового интерфейса программирования для приема и взаимодействия с соединением WebSocket с помощью существующего предусмотрен <xref:System.Net.HttpListener> и связанных классов. Дополнительные сведения см. в разделе новый <xref:System.Net.WebSockets> пространства имен и <xref:System.Net.HttpListener> класса.  
  
 Кроме того, в [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] предусмотрены следующие усовершенствования в плане сетевого взаимодействия:  
  
-   RFC-совместимая поддержка URI. Дополнительные сведения см. в разделе <xref:System.Uri> и связанных классов.  
  
-   Поддержка синтаксического анализа интернационализированных доменных имен (Internationalized Domain Name, IDN). Дополнительные сведения см. в разделе <xref:System.Uri> и связанных классов.  
  
-   Поддержка интернационализации адресов электронной почты (Email Address Internationalization, EAI). Дополнительные сведения см. в разделе <xref:System.Net.Mail> пространства имен.  
  
-   Улучшенная поддержка протокола IPv6. Дополнительные сведения см. в разделе <xref:System.Net.NetworkInformation> пространства имен.  
  
-   Поддержка сокета с двойным режимом. Дополнительные сведения см. в разделе <xref:System.Net.Sockets.Socket> и <xref:System.Net.Sockets.TcpListener> классы.  
  
<a name="client"></a>   
### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)  
 В [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] Windows Presentation Foundation (WPF) содержит изменения и усовершенствования в следующих областях:  
  
-   Новый <xref:System.Windows.Controls.Ribbon.Ribbon> элемента управления, который позволяет реализовать пользовательский интерфейс ленты, в которой размещаются панель быстрого доступа, меню приложения и вкладки.  
  
-   Новый <xref:System.ComponentModel.INotifyDataErrorInfo> интерфейс, который поддерживает синхронные и асинхронные данных проверку.  
  
-   Новые возможности для <xref:System.Windows.Controls.VirtualizingPanel> и <xref:System.Windows.Threading.Dispatcher> классы.  
  
-   Повышение производительности при отображении больших наборов сгруппированных данных, а также за счет доступа к коллекциям в потоках вне пользовательского интерфейса.  
  
-   Привязка данных к статическим свойствам, привязка данных к пользовательским типы, реализующие <xref:System.Reflection.ICustomTypeProvider> интерфейс и получения сведений о привязке данных из выражения привязки.  
  
-   Изменение расположения данных по мере изменение значений (формирование данных в реальном времени).  
  
-   Возможность проверить, отсоединен ли контекст данных для контейнера элемента.  
  
-   Возможность задать количество времени, которое должно пройти между операциями изменения свойств и обновления источника данных.  
  
-   Улучшенная поддержка реализации шаблонов слабых событий. Кроме того, события теперь могут принимать расширения разметки.  
  
<a name="windows_communication_foundation"></a>   
### <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)  
 В [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] были добавлены следующие возможности, чтобы упростить создание и обслуживание приложений Windows Communication Foundation (WCF):  
  
-   Упрощение создаваемых файлов конфигурации.  
  
-   Поддержка разработки в соответствии с парадигмой "сначала контракт".  
  
-   Упрощение настройки режима совместимости ASP.NET.  
  
-   Изменения значений свойств транспорта по умолчанию для уменьшения вероятности необходимости их настройки.  
  
-   Обновление <xref:System.Xml.XmlDictionaryReaderQuotas> класса, чтобы снизить вероятность того, что требуется вручную настраивать квоты для читателей словаря XML.  
  
-   Проверка файлов конфигурации WCF силами Visual Studio в рамках процесса сборки, позволяющая выявить ошибки в конфигурации до запуска приложения.  
  
-   Новая поддержка асинхронной потоковой передачи.  
  
-   Новое сопоставление протокола HTTPS, облегчающее предоставление конечной точки по HTTPS с помощью служб IIS.  
  
-   Возможность создавать метаданные в одном документе WSDL путем добавления `?singleWSDL` к URL-адресу службы.  
  
-   Поддержка Websockets, обеспечивающая истинно двунаправленный обмен данными через порты 80 и 443 с показателями производительности, схожими с характеристиками TCP-транспорта.  
  
-   Поддержка настройки служб в коде.  
  
-   Всплывающие подсказки в редакторе XML.  
  
-   <xref:System.ServiceModel.ChannelFactory> поддержка кэширования.  
  
-   Поддержка сжатия двоичного кодировщика.  
  
-   Поддержка UDP-транспорта, которая позволяет разработчикам писать службы, использующие обмен сообщениями по принципу "отправить и забыть". Клиент отправляет сообщение службе, но не ожидает от нее ответа.  
  
-   Возможность поддерживать несколько режимов аутентификации в одной конечной точке WCF при использовании HTTP-транспорта и безопасности транспорта.  
  
-   Поддержка служб WCF, использующих интернационализированные доменные имена (IDN).  
  
 Дополнительные сведения см. в разделе [новые возможности в Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkId=228173).  
  
<a name="windows_workflow_foundation"></a>   
### <a name="windows-workflow-foundation-wf"></a>Windows Workflow Foundation (WF)  
 В Windows Workflow Foundation (WF) в [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] было добавлено несколько новых возможностей, в том числе следующие:  
  
-   Конечного автомата, которые впервые появились в составе .NET Framework 4.0.1 ([1 обновления платформы .NET Framework 4](http://go.microsoft.com/fwlink/?LinkID=215092)). В это обновление вошло несколько новых классов и действий, позволивших разработчикам создавать рабочие процессы конечного автомата. В [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] эти классы и действия были обновлены и теперь включают в себя следующие возможности:  
  
    -   Возможность установки точек останова на состояниях.  
  
    -   Возможность копирования и вставки переходов в конструкторе рабочих процессов.  
  
    -   Поддержка создания в конструкторе переходов с общим триггером.  
  
    -   Действия для создания конечного автомата, включая: <xref:System.Activities.Statements.StateMachine>, <xref:System.Activities.Statements.State>, и <xref:System.Activities.Statements.Transition>.  
  
-   Расширенные возможности конструктора рабочих процессов, например следующие:  
  
    -   Расширенные возможности поиска рабочих процессов в Visual Studio, включая **быстрый поиск** и **поиск в файлах**.  
  
    -   Возможность автоматически создавать действие Sequence, когда к действию-контейнеру добавляется второе действие — дочерний элемент, и включать оба действия в действие Sequence.  
  
    -   Поддержка панорамирования, которая позволяет изменять видимую часть рабочего процесса без использования полос прокрутки.  
  
    -   Новый **Структура документа** представление, в котором отображаются компоненты рабочего процесса в виде структуры дерева с возможностью выбора компонента в **Структура документа** представления.  
  
    -   Возможность добавлять примечаний к действиям.  
  
    -   Возможность определять и использовать делегаты действий с помощью конструктора рабочих процессов.  
  
    -   Автоматическое соединение и автоматическая вставка для действий и переходов в рабочих процессах блок-схемы и конечного автомата.  
  
-   Хранение данных о состоянии представления для рабочего процесса в одном элементе в XAML-файле, чтобы данные о состоянии представления можно было легко находить и редактировать.  
  
-   Действие-контейнер NoPersistScope для предотвращения сохранения дочерних действий.  
  
-   Поддержка выражений C#:  
  
    -   Проекты рабочих процессов, в которых используется Visual Basic, будут использовать выражения Visual Basic, а проекты рабочих процессов C# будут использовать выражения C#.  
  
    -   Проекты рабочих процессов C#, созданные в Visual Studio 2010 и содержащие выражения Visual Basic, совместимы с проектами рабочих процессов C#, в которых используются выражения C#.  
  
-   Усовершенствования управления версиями:  
  
    -   Новый <xref:System.Activities.WorkflowIdentity> класс, который обеспечивает сопоставление экземпляр сохраненного рабочего процесса и его определением рабочего процесса.  
  
    -   Side-by-side выполнение нескольких версий рабочего процесса в том же узле, включая <xref:System.ServiceModel.Activities.WorkflowServiceHost>.  
  
    -   В динамическом обновлении это возможность изменять определение сохраненного экземпляра рабочего процесса.  
  
-   Разработка служб рабочего процесса в соответствии с парадигмой "сначала контракт", что обеспечивает поддержку автоматического создания действий в соответствии с существующим контрактом службы.  
  
 Дополнительные сведения см. в разделе [новые возможности в Windows Workflow Foundation](http://go.microsoft.com/fwlink/?LinkId=228176).  
  
<a name="tailored"></a>   
### [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]  
 Приложения [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] разрабатываются для конкретных форм-факторов и в полной мере используют возможности операционной системы Windows. Подмножество [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] или 4.5.1 доступно для разработки приложений [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] для Windows с использованием C# или Visual Basic. Это подмножество называется [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] и рассматривается в [Обзор](http://go.microsoft.com/fwlink/?LinkId=228491) в центре разработчиков Windows.  
  
<a name="portable"></a>   
### <a name="portable-class-libraries"></a>Переносимые библиотеки классов  
 Проект "Переносимая библиотека классов" в [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)] (и более поздних версиях) позволяет писать и собирать управляемые сборки, работающие на нескольких платформах .NET Framework. Используя проект "Переносимая библиотека классов", можно выбирать платформы для ориентирования (например, Windows Phone и [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]). Доступные типы и члены в проекте автоматически ограничиваются типами и членами, общими для этих платформ. Дополнительные сведения см. в разделе [переносимой библиотеки классов](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md).  
  
## <a name="see-also"></a>См. также  
 [.NET Framework и выпуски по каналу](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)   
 [Новые возможности Visual Studio 2013](http://msdn.microsoft.com/library/bb386063\(v=vs.120\).aspx)   
 [ASP.NET 4.5.1 и веб-средства для Visual Studio 2013](http://go.microsoft.com/fwlink/?LinkID=309094)   
 [ASP.NET и Visual Studio для веб-узла](../Topic/ASP.NET%20and%20Visual%20Studio%20for%20Web.md)   
 [Новые возможности в Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkId=228173)   
 [Новые возможности в Windows Workflow Foundation](http://go.microsoft.com/fwlink/?LinkId=228176)   
 [Новые возможности Visual C++](http://msdn.microsoft.com/library/hh409293\(v=vs.120\).aspx)