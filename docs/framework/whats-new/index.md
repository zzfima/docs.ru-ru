---
title: "Новые возможности .NET Framework | Документы Microsoft"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework-4.6
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- what's new [.NET Framework]
ms.assetid: 1d971dd7-10fc-4692-8dac-30ca308fc0fa
caps.latest.revision: 292
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9460c8b6ca8db927af4064e3567eca34c1bf5c91
ms.openlocfilehash: 56bf5905fc9e4c676e2cf681c9135fddf88e5c89
ms.lasthandoff: 04/08/2017

---
# <a name="what39s-new-in-the-net-framework"></a>Новые возможности .NET Framework
<a name="introduction"></a>В этой статье кратко излагаются ключевые новые возможности и усовершенствования в следующих версиях .NET Framework:  
  
 [.NET Framework 4.7](#v47)   
 [.NET Framework 4.6.2](#v462)   
 [.NET Framework 4.6.1](#v461)   
 [.NET 2015 и .NET Framework 4.6](#v46)   
 [.NET Framework 4.5.2](#v452)   
 [.NET Framework 4.5.1](#v451)   
 [.NET Framework 4.5](#core)  
  
 Данная статья не содержит исчерпывающей информации обо всех новых возможностях и может быть изменена. Общие сведения о .NET Framework см. в разделе [Начало работы с .NET Framework](http://msdn.microsoft.com/library/c693fd34-88fe-4d90-b332-19eeadf3b7e7). Поддерживаемые платформы см. в разделе [Требования к системе](~/docs/framework/get-started/system-requirements.md). Ссылки для загрузки и инструкции по установке см. в разделе [Руководство по установке](../../../docs/framework/install/guide-for-developers.md).  
  
> [!NOTE]
>  Команда .NET Framework также выпускает компоненты в виде внештатных выпусков совместно с NuGet для расширения поддержки и введения новых возможностей (таких как неизменяемые коллекции и векторные типы с поддержкой SIMD). Дополнительные сведения см. в разделах [Дополнительные библиотеки классов и интерфейсы API](http://msdn.microsoft.com/library/cf2d9006-b631-4e5d-81cd-20aab78c60f1) и [.NET Framework и внештатные выпуски](~/docs/framework/get-started/the-net-framework-and-out-of-band-releases.md). См. [полный список пакетов NuGet](http://blogs.msdn.com/b/dotnet/p/nugetpackages.aspx) для .NET Framework или подпишитесь на [наш веб-канал](https://nuget.org/api/v2/curated-feeds/dotnetframework/Packages/).  
  
<a name="v47"></a>   
## <a name="introducing-the-net-framework-47"></a>Знакомство с платформой .NET Framework 4.7  
 Версия .NET Framework 4.7 является следующим шагом развития версий .NET Framework 4.6, 4.6.1 и 4.6.2. Она включает много исправлений и несколько новых возможностей, сохраняя при этом высокую стабильность работы.  

> [!NOTE]
> Версия .NET Framework 4.7 предустановлена на всех системах с ОС Windows 10 Creators Update. Ее нельзя скачать или установить в других операционных системах Windows.  

## <a name="whats-new-in-the-net-framework-47"></a>Новые возможности .NET Framework 4.7

.NET Framework 4.7 включает новые функции в следующих областях:

- [Ядро](#Core47)
- [Сеть](#net47)
- [ASP.NET](#ASP-NET47)
- [Windows Communication Foundation (WCF)](#wcf47)
- [Windows Forms](#wf47)
- [Windows Presentation Foundation (WPF)](#WPF47)

<a name="Core47" />
### <a name="core"></a>Ядро ###

В .NET Framework 4.7 улучшена сериализация <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>:

**Дополнительные функциональные возможности на основе эллиптической криптографии (ECC)***

В .NET Framework 4.7 добавлены методы `ImportParameters(ECParameters)` в классы <xref:System.Security.Cryptography.ECDsa> и <xref:System.Security.Cryptography.ECDiffieHellman>, что позволяет представлять в объектах уже настроенный ключ. Также добавлен метод `ExportParameters(Boolean)` для экспорта ключа с явными параметрами кривой.

В .NET Framework 4.7 также добавлена поддержка дополнительных кривых (включая пакет кривых Brainpool) и стандартные определения для упрощения создания при помощи новых методов <xref:System.Security.Cryptography.ECDsa.Create%2A> и <xref:System.Security.Cryptography.ECDiffieHellman.Create%2A>.

На GitHub вы найдете [пример криптографических улучшений в .NET Framework 4.7](https://gist.github.com/richlander/5a182899895a87a296c21ada97f7a54e).

**Улучшенная поддержка управляющих символов для DataContractJsonSerializer**

В .NET Framework 4.7 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> сериализует управляющие символы в соответствии со стандартом ECMAScript 6. Это поведение включено по умолчанию для приложений, предназначенных для .NET Framework 4.7, и предлагается в качестве дополнительной функции для приложений, которые выполняются в среде .NET Framework 4.7, но предназначены для предыдущих версий платформы .NET Framework. Дополнительные сведения см. в статье [Изменения целевой платформы в .NET Framework 4.7](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md).

<a name="net47" />
### <a name="networking"></a>Сеть ###

В .NET Framework 4.7 добавлена следующая сетевая возможность.

**Поддержка операционной системы по умолчанию для протоколов TLS***

Стек TLS, который используется в <xref:System.Net.Security.SslStream?displayProperty=fullName> и других компонентах, расположенных в стеке над ним (например, HTTP, FTP и SMTP), позволяет разработчикам использовать протоколы TLS по умолчанию, поддерживаемые операционной системой. Разработчики теперь не обязаны жестко указывать версию TLS.

<a name="ASP-NET47" />
### <a name="aspnet"></a>ASP.NET ###

ASP.NET в .NET Framework 4.7 включает следующие новые функции:

**Расширяемость кэша объектов**

Начиная с .NET Framework 4.7 в ASP.NET добавляется новый набор интерфейсов API, которые позволяют разработчикам заменить стандартные механизмы кэширования объектов в памяти и мониторинга за использованием памяти в ASP.NET. Разработчики могут переопределить любой из следующих трех компонентов, если их не устраивает стандартная реализация ASP.NET.

- **Хранилище кэша объектов**. В новом разделе конфигурации поставщиков кэша разработчик может подключить новую реализацию кэша объектов для приложения ASP.NET с помощью нового интерфейса **ICacheStoreProvider**.
 
- **Мониторинг памяти**. Стандартный монитор памяти ASP.NET уведомляет приложения о том, что они приближаются к настроенному для процесса лимиту байтов исключительного пользования, а также о нехватке общей доступной физической памяти на компьютере. Уведомление срабатывает незадолго до достижения ограничения. Для некоторых приложений эти уведомления поступают слишком поздно и не позволяют предпринять никаких разумных действий. Разработчики могут использовать свои собственные механизмы мониторинга памяти, заменив стандартную реализацию с помощью свойства <xref:System.Web.Hosting.ApplicationMonitors.MemoryMonitor%2A?displayProperty=fullName>.

- **Реакции на достижение лимита памяти**. По умолчанию ASP.NET пытается обрезать кэш объектов, периодически вызывая функцию <xref:System.GC.Collect%2A?displayProperty=fullName> при приближении к лимиту байтов исключительного пользования для процесса. Для некоторых приложений частота вызовов <xref:System.GC.Collect%2A?displayProperty=fullName> или размер кэша после обрезки не позволяют обеспечить эффективность работы. Теперь разработчик может изменить или дополнить поведение по умолчанию, назначив собственную реализацию **IObserver** в качестве монитора памяти для приложения.

<a name="wcf47" />
### <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF) ###

В Windows Communication Foundation (WFC) добавлены следующие функции и изменения.

**Возможность настраивать параметры безопасности сообщений по умолчанию для TLS 1.1 или TLS 1.2**

Начиная с .NET Framework 4.7 WCF позволяет настраивать в качестве протокола безопасности сообщений по умолчанию протоколы TSL 1.1 и TLS 1.2, а не только SSL 3.0 и TSL 1.0. Эту возможность нужно дополнительно активировать, добавив следующую запись в файл конфигурации приложения:

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;Switch.System.Net.DontEnableSchUseStrongCrypto=false" /> 
</runtime>
```

**Повышенная надежность приложений WCF и сериализации WCF**

Для WCF внесены несколько изменений кода, которые позволяют избежать состояний гонки, повышая таким образом производительность и надежность методов сериализации. Сюда входит следующее.

- Улучшение поддержки для совместного использования асинхронного и синхронного кода в вызовах **SocketConnection.BeginRead** и **SocketConnection.Read**.
- Повышение надежности при разрыве подключения с **SharedConnectionListener** и **DuplexChannelBinder**.
- Повышение надежности операций сериализации при вызове метода [FormatterServices.GetSerializableMembers] (assetId:///System.Runtime.Serialization.FormatterServices.GetSerializableMembers(System.Type??qualifyHint=True&autoUpgrade=False).
- Повышение надежности при удалении обслуживающего потока путем вызова метода **ChannelSynchronizer.RemoveWaiter**.  

<a name="wf47" />
### <a name="windows-forms"></a>Windows Forms ###

В .NET Framework 4.7 для Windows Forms улучшена поддержка мониторов высоким разрешением.

**Поддержка высокого разрешения**

Начиная с приложений, ориентированных на .NET Framework 4.7, в .NET Framework поддерживается высокое разрешение и динамическое разрешение для приложений Windows Forms. Поддержка высокого разрешения улучшает расположение и внешний вид форм и элементов управления на мониторах с высокой плотностью точек на дюйм. Функция динамического разрешения изменяет расположение и внешний вид формы и элементов управления, когда пользователь изменяет разрешение монитора или масштаб отображения при запущенном приложении.

Поддержку высокого разрешения нужно активировать дополнительно, определив раздел [\<System.Windows.Forms.ConfigurationSection>](Windows%20Forms%20Configuration%20Section.md) в файле конфигурации приложения. Дополнительные сведения об активации поддержки высокого разрешения и динамического разрешения для приложений Windows Forms вы можете найти в статье [Поддержка высокого DPI в Windows Forms](High%20DPI%20Support%20In%20Windows%20Forms.md).  

<a name="WPF47"></a>   
### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

В .NET Framework 4.7 добавлены следующие улучшения для WPF.

**Поддержка стека для управления касанием или пером, основанного на сообщениях Windows WM_POINTER**

Теперь вы можете использовать стек управления касанием или пером на основе сообщений [WM_POINTER](https://msdn.microsoft.com/library/windows/desktop/hh454903(v=vs.85).aspx) вместо платформы служб рукописного ввода Windows (WISP). Эту функцию нужно отдельно активировать в .NET Framework. Дополнительные сведения см. в статье [Изменения целевой платформы в .NET Framework 4.7](Retargeting%20Changes%20in%20the%20.NET%20Framework%204.7.md).

**Новая реализация интерфейсов API WPF для печати**

API-интерфейсы WPF для печати в классе [System.Printing.PrintQueue](assetId:///T:System.Printing.PrintQueue?qualifyHint=True&autoUpgrade=True) вызывают [API пакета печати документа](https://msdn.microsoft.com/library/windows/desktop/hh448418(v=vs.85).aspx) Windows вместо устаревших [API печати XPS](https://msdn.microsoft.com/library/windows/desktop/ff686814(v=vs.85).aspx). Влияние этого изменения на совместимость приложений можно изучить в статье [Изменения целевой платформы в .NET Framework 4.7](Retargeting%20Changes%20in%20the%20.NET%20Framework%204.7.md). 

<a name="v462"></a>   
## <a name="whats-new-in-the-net-framework-462"></a>Новые возможности .NET Framework 4.6.2  
Версия .NET Framework 4.6.2 включает новые функции в следующих областях:  
  
-   [ASP.NET](#ASPNET462)  
  
-   [Категории символов](#Strings)  
  
-   [Шифрование](#Crypto462)  
  
-   [SqlClient](#SQLClient)  
  
-   [Windows Communication Foundation](#WCF)  
  
-   [Windows Presentation Foundation (WPF)](#WPF462)  
  
-   [Windows Workflow Foundation (WF)](#WF462)  
  
-   [ClickOnce](#ClickOnce)  
  
-   [Преобразование приложений Windows Forms и WPF в приложения UWP](#UWPConvert)  
  
-   [Усовершенствования отладки](#Debug462)  
  
 Список новых интерфейсов API, добавленных в .NET Framework 4.6.2, см. в статье [об изменениях API в .NET Framework 4.6.2](https://github.com/Microsoft/dotnet/blob/master/releases/net462/dotnet462-api-changes.md) на сайте GitHub. Список улучшений функций и исправлений ошибок в .NET Framework 4.6.2 см. в статье [об изменениях API в .NET Framework 4.6.2](http://go.microsoft.com/fwlink/?LinkId=708778) на сайте GitHub.  Дополнительные сведения см. в разделе [Объявление о выпуске .NET Framework 4.6.2](https://blogs.msdn.microsoft.com/dotnet/2016/08/02/announcing-net-framework-4-6-2/) в блоге .NET.  
  
<a name="ASPNET462"></a>   
### <a name="aspnet"></a>ASP.NET  
 ASP.NET в .NET Framework 4.6.2 включает следующие улучшения.  
  
 **Улучшена поддержка локализованных сообщений об ошибках в проверяющих элементах управления заметок к данным.**  
 Модули проверки заметок к данным позволяют выполнять проверки путем добавления одного или нескольких атрибутов к свойству класса. Элемент [ValidationAttribute.ErrorMessage](assetId:///P:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage?qualifyHint=True&autoUpgrade=True) для атрибута определяет текст сообщения об ошибке, если проверка не пройдена. Начиная с .NET Framework 4.6.2 в ASP.NET упрощена локализация сообщений об ошибках. Локализация сообщений об ошибках происходит в указанных далее случаях.  
  
1.  В атрибуте проверки предоставляется [ValidationAttribute.ErrorMessage](assetId:///P:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage?qualifyHint=True&autoUpgrade=True).  
  
2.  Файл ресурсов хранится в папке App_LocalResources.  
  
3.  Имя локализованного файла ресурсов имеет форму `DataAnnotation.Localization.{`*имя*`}.resx`, где *имя* — это имя языка и региональных параметров в формате *languageCode*`-`*country/regionCode* или *languageCode*.  
  
4.  Имя ключа ресурса является строкой, назначенной атрибуту [ValidationAttribute.ErrorMessage](assetId:///P:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage?qualifyHint=True&autoUpgrade=True), а его значением является локализованное сообщение об ошибке.  
  
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
   \<Required(ErrorMessage = "The rating must be between 1 and 10.")>  
   \<Display(Name = "Your Rating")>  
   Public Property Rating As Integer = 1  
End Class  
  
```  
  
 Затем можно создать файл ресурсов DataAnnotation.Localization.fr.resx, ключом в котором является строка сообщения об ошибке, а значением — локализованное сообщение об ошибке. Этот файл должен находиться в папке `App.LocalResources`. Например, ниже приведен ключ и его значение в сообщении об ошибке, локализованном в рамках французского языка и региональных параметров (French (fr)).  
  
|Имя|Значение|  
|----------|-----------|  
|The rating must be between 1 and 10.|La note doit être comprise entre 1 et 10.|  
  
 Затем этот файл можно  
  
 Кроме того, локализация заметок к данным является расширяемой. Разработчики могут подключить собственный поставщик локализатора строк путем реализации интерфейса [IStringLocalizerProvider](assetId:///T:System.Web.Globalization.IStringLocalizerProvider?qualifyHint=False&autoUpgrade=True) для хранения строки локализации в месте, отличном от файла ресурсов.  
  
 **Поддержка асинхронного выполнения с поставщиками хранилищ состояния сеансов**  
 Теперь ASP.NET позволяет использовать методы, возвращающие задачи, с поставщиками хранилища состояния сеанса, тем самым разрешая приложениям ASP.NET реализовывать преимущества масштабируемости асинхронных операций. Для поддержки асинхронных операций с поставщиками хранилищ состояния сеансов ASP.NET предлагает новый интерфейс [System.Web.SessionState.ISessionStateModule](assetId:///T:System.Web.SessionState.ISessionStateModule?qualifyHint=True&autoUpgrade=True), который наследует от [IHttpModule](assetId:///T:System.Web.IHttpModule?qualifyHint=False&autoUpgrade=True) и позволяет разработчикам реализовывать их собственные модули состояния сеансов и асинхронные поставщики хранилищ сеансов. Интерфейс определяется следующим образом:  
  
```csharp  
  
public interface ISessionStateModule : IHttpModule {  
    void ReleaseSessionState(HttpContext context);  
    Task ReleaseSessionStateAsync(HttpContext context);  
}  
  
```  
  
 Кроме того, класс [SessionStateUtility](assetId:///T:System.Web.SessionState.SessionStateUtility?qualifyHint=False&autoUpgrade=True) включает два новых метода: [IsSessionStateReadOnly](assetId:///M:System.Web.SessionState.SessionStateUtility.IsSessionStateReadOnly(System.Web.HttpContext)?qualifyHint=False&autoUpgrade=True) и [IsSessionStateRequired](assetId:///M:System.Web.SessionState.SessionStateUtility.IsSessionStateRequired(System.Web.HttpContext)?qualifyHint=False&autoUpgrade=True). Они позволяют организовать поддержку асинхронных операций.  
  
 **Поддержка асинхронного выполнения поставщиков кэша вывода**  
 Начиная с .NET Framework 4.6.2 с поставщиками кэша вывода можно использовать методы, возвращающие задачи, чтобы воспользоваться преимуществами асинхронных операций по масштабируемости.  Поставщики, реализующие эти методы, сокращают вероятность блокировок потоков на веб-сервере и улучшают масштабируемость службы ASP.NET.  
  
 Для поддержки поставщиков кэша асинхронного вывода были добавлены следующие API:  
  
-   Класс [System.Web.Caching.OutputCacheProviderAsync](assetId:///T:System.Web.Caching.OutputCacheProviderAsync?qualifyHint=True&autoUpgrade=True), который наследует от [System.Web.Caching.OutputCacheProvider](assetId:///T:System.Web.Caching.OutputCacheProvider?qualifyHint=True&autoUpgrade=True) и позволяет разработчикам реализовывать поставщик асинхронного кэша вывода.  
  
-   Класс [OutputCacheUtility](assetId:///T:System.Web.Caching.OutputCacheUtility?qualifyHint=False&autoUpgrade=True), который предоставляет вспомогательные методы для настройки кэша вывода.  
  
-   18 новых методов в классе [System.Web.HttpCachePolicy](assetId:///T:System.Web.HttpCachePolicy?qualifyHint=True&autoUpgrade=True). К ним относятся [GetCacheability](assetId:///M:System.Web.HttpCachePolicy.GetCacheability?qualifyHint=False&autoUpgrade=True), [GetCacheExtensions](assetId:///M:System.Web.HttpCachePolicy.GetCacheExtensions?qualifyHint=False&autoUpgrade=True), [GetETag](assetId:///M:System.Web.HttpCachePolicy.GetETag?qualifyHint=False&autoUpgrade=True), [GetETagFromFileDependencies](assetId:///M:System.Web.HttpCachePolicy.GetETagFromFileDependencies?qualifyHint=False&autoUpgrade=True), [GetMaxAge](assetId:///M:System.Web.HttpCachePolicy.GetMaxAge?qualifyHint=False&autoUpgrade=True), [GetMaxAge](assetId:///M:System.Web.HttpCachePolicy.GetMaxAge?qualifyHint=False&autoUpgrade=True), [GetNoStore](assetId:///M:System.Web.HttpCachePolicy.GetNoStore?qualifyHint=False&autoUpgrade=True), [GetNoTransforms](assetId:///M:System.Web.HttpCachePolicy.GetNoTransforms?qualifyHint=False&autoUpgrade=True), [GetOmitVaryStar](assetId:///M:System.Web.HttpCachePolicy.GetOmitVaryStar?qualifyHint=False&autoUpgrade=True), [GetProxyMaxAge](assetId:///M:System.Web.HttpCachePolicy.GetProxyMaxAge?qualifyHint=False&autoUpgrade=True), [GetRevalidation](assetId:///M:System.Web.HttpCachePolicy.GetRevalidation?qualifyHint=False&autoUpgrade=True), [GetUtcLastModified](assetId:///M:System.Web.HttpCachePolicy.GetUtcLastModified?qualifyHint=False&autoUpgrade=True), [GetVaryByCustom](assetId:///M:System.Web.HttpCachePolicy.GetVaryByCustom?qualifyHint=False&autoUpgrade=True), [HasSlidingExpiration](assetId:///M:System.Web.HttpCachePolicy.HasSlidingExpiration?qualifyHint=False&autoUpgrade=True) и [IsValidUntilExpires](assetId:///M:System.Web.HttpCachePolicy.IsValidUntilExpires?qualifyHint=False&autoUpgrade=True).  
  
-   2 новых метода в классе [System.Web.HttpCacheVaryByContentEncodings](assetId:///T:System.Web.HttpCacheVaryByContentEncodings?qualifyHint=True&autoUpgrade=True): [GetContentEncodings](assetId:///M:System.Web.HttpCacheVaryByContentEncodings.GetContentEncodings?qualifyHint=False&autoUpgrade=True) и [SetContentEncodings](assetId:///M:System.Web.HttpCacheVaryByContentEncodings.SetContentEncodings(System.String[])?qualifyHint=False&autoUpgrade=True).  
  
-   2 новых метода в классе [System.Web.HttpCacheVaryByHeaders](assetId:///T:System.Web.HttpCacheVaryByHeaders?qualifyHint=True&autoUpgrade=True): [GetHeaders](assetId:///M:System.Web.HttpCacheVaryByHeaders.GetHeaders?qualifyHint=False&autoUpgrade=True) и [SetHeaders](assetId:///M:System.Web.HttpCacheVaryByHeaders.SetHeaders(System.String[])?qualifyHint=False&autoUpgrade=True).  
  
-   2 новых метода в классе [System.Web.HttpCacheVaryByParams](assetId:///T:System.Web.HttpCacheVaryByParams?qualifyHint=True&autoUpgrade=True): [GetParams](assetId:///M:System.Web.HttpCacheVaryByParams.GetParams?qualifyHint=False&autoUpgrade=True) и [SetParams](assetId:///M:System.Web.HttpCacheVaryByParams.SetParams(System.String[])?qualifyHint=False&autoUpgrade=True).  
  
-   В класс [System.Web.Caching.AggregateCacheDependency](assetId:///T:System.Web.Caching.AggregateCacheDependency?qualifyHint=True&autoUpgrade=True) добавлен метод [GetFileDependencies](assetId:///M:System.Web.Caching.AggregateCacheDependency.GetFileDependencies?qualifyHint=False&autoUpgrade=True).  
  
-   В класс [CacheDependency](assetId:///T:System.Web.Caching.CacheDependency?qualifyHint=False&autoUpgrade=True) добавлен метод [GetFileDependencies](assetId:///M:System.Web.Caching.CacheDependency.GetFileDependencies?qualifyHint=False&autoUpgrade=True).  
  
<a name="Strings"></a>   
### <a name="character-categories"></a>Категории символов  
 Символы в .NET Framework 4.6.2 классифицируются на основе [стандарта Юникод версии 8.0.0](http://www.unicode.org/versions/Unicode8.0.0/). В .NET Framework 4.6 и .NET Framework 4.6.1 символы классифицировались на основе категорий символов Юникода 6.3.  
  
 Поддержка Юникода 8.0 ограничена классификацией символов в классе [CharUnicodeInfo](assetId:///T:System.Globalization.CharUnicodeInfo?qualifyHint=False&autoUpgrade=True) и использующими его типами и методами. К ним относятся класс [StringInfo](assetId:///T:System.Globalization.StringInfo?qualifyHint=False&autoUpgrade=True), перегруженный метод [Char.GetUnicodeCategory](assetId:///M:System.Char.GetUnicodeCategory(System.Char)?qualifyHint=True&autoUpgrade=True) и [классы символов](../Topic/Character%20Classes%20in%20Regular%20Expressions.md), распознаваемые обработчиком регулярных выражений .NET Framework.  Это изменение не влияет на сравнение и сортировку символов и строк. Они по-прежнему зависят от базовой операционной системы или в системах Windows 7 от символьных данных, предоставляемых .NET Framework.  
  
 Сведения об изменениях в категориях символов Юникода 6.0–7.0 см. в статье [The Unicode Standard, Version 7.0.0](http://www.unicode.org/versions/Unicode7.0.0/) на веб-сайте консорциума Юникода. Сведения об изменениях в категориях символов Юникода 7.0–8.0 см. в статье [The Unicode Standard, Version 8.0.0](http://www.unicode.org/versions/Unicode8.0.0/) на веб-сайте Консорциума Юникода.  
  
<a name="Crypto462"></a>   
### <a name="cryptography"></a>Шифрование  
 **Поддержка сертификатов X509, содержащих FIPS 186-3 DSA**  
 В .NET Framework 4.6.2 добавлена поддержка сертификатов X509 с алгоритмом DSA, ключи которых превышают 1024-разрядное ограничение FIPS 186-2.  
  
 В дополнение к поддержке ключей FIPS 186-3 больших размеров, .NET Framework 4.6.2 позволяет вычислять подписи с использованием семейства алгоритмов хэширования SHA-2 (SHA256, SHA384 и SHA512). Поддержка FIPS 186-3 обеспечивается новым классом [System.Security.Cryptography.DSACng](assetId:///T:System.Security.Cryptography.DSACng?qualifyHint=True&autoUpgrade=True).  
  
 Для соответствия последним изменениям в классе [RSA](assetId:///T:System.Security.Cryptography.RSA?qualifyHint=False&autoUpgrade=True) в версии .NET Framework 4.6 и классе [ECDsa](assetId:///T:System.Security.Cryptography.ECDsa?qualifyHint=False&autoUpgrade=True) в версии .NET Framework 4.6.1, абстрактный базовый класс [DSA](assetId:///T:System.Security.Cryptography.DSA?qualifyHint=False&autoUpgrade=True) в .NET Framework 4.6.2 имеет дополнительные методы, позволяющие вызывающим сторонам использовать эту возможность без приведения типов. Для подписания вы можете вызвать данных метод расширения [DSACertificateExtensions.GetDSAPrivateKey](assetId:///M:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?qualifyHint=True&autoUpgrade=True), как показано в следующем примере.  
  
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
  
 Для проверки подписанных данных вы можете вызвать данных метод расширения [DSACertificateExtensions.GetDSAPublicKey](assetId:///M:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?qualifyHint=True&autoUpgrade=True), как показано в следующем примере.  
  
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
  
 **Повышенная четкость входных данных для процедур формирования ключа ECDiffieHellman**  
 В .NET Framework 3.5 добавлена поддержка соглашения о ключах Диффи-Хелмана на эллиптических кривых с тремя разными процедурами формирования ключа. Входные данные для процедур и сами процедуры настраивались с помощью свойств объекта [ECDiffieHellmanCng](assetId:///T:System.Security.Cryptography.ECDiffieHellmanCng?qualifyHint=False&autoUpgrade=True). Однако поскольку не все процедуры правильно считывали каждое входное свойство, часто возникала путаница.  
  
 В .NET Framework 4.6.2 для решения этой проблемы в базовый класс [ECDiffieHellman](assetId:///T:System.Security.Cryptography.ECDiffieHellman?qualifyHint=False&autoUpgrade=True) были добавлены следующие три метода, предназначенные для более четкого представления этих подпрограмм функций формирования ключа и их входных данных.  
  
|Метод ECDiffieHellman|Описание|  
|----------------------------|-----------------|  
|[DeriveKeyFromHash(ECDiffieHellmanPublicKey, HashAlgorithmName, Byte\[\], Byte\[\])](assetId:///M:System.Security.Cryptography.ECDiffieHellman.DeriveKeyFromHash(System.Security.Cryptography.ECDiffieHellmanPublicKey,System.Security.Cryptography.HashAlgorithmName,System.Byte[],System.Byte[])?qualifyHint=False&autoUpgrade=False)|Получает материал ключа с помощью формулы<br /><br /> HASH(secretPrepend &#124;&#124; *x* &#124;&#124; secretAppend)<br /><br /> HASH(secretPrepend OrElse *x* OrElse secretAppend)<br /><br /> здесь *x* является вычисляемым результатом алгоритма Диффи-Хелмана на эллиптических кривых.|  
|[DeriveKeyFromHmac(ECDiffieHellmanPublicKey, HashAlgorithmName, Byte\[\], Byte\[\], Byte\[\])](assetId:///M:System.Security.Cryptography.ECDiffieHellman.DeriveKeyFromHmac(System.Security.Cryptography.ECDiffieHellmanPublicKey,System.Security.Cryptography.HashAlgorithmName,System.Byte[],System.Byte[],System.Byte[])?qualifyHint=False&autoUpgrade=False)|Получает материал ключа с помощью формулы<br /><br /> HMAC(hmacKey, secretPrepend &#124;&#124; *x* &#124;&#124; secretAppend)<br /><br /> HMAC(hmacKey, secretPrepend OrElse *x* OrElse secretAppend)<br /><br /> здесь *x* является вычисляемым результатом алгоритма Диффи-Хелмана на эллиптических кривых.|  
|[DeriveKeyTls(ECDiffieHellmanPublicKey, Byte\[\], Byte\[\])](assetId:///M:System.Security.Cryptography.ECDiffieHellman.DeriveKeyTls(System.Security.Cryptography.ECDiffieHellmanPublicKey,System.Byte[],System.Byte[])?qualifyHint=False&autoUpgrade=False)|Получает материал ключа с помощью алгоритма наследования псевдослучайной функции (PRF) TLS.|  
  
 **Поддержка симметричного шифрования с помощью постоянного ключа**  
 В библиотеку шифрования Windows (CNG) добавлена поддержка хранения постоянных симметричных ключей и использования хранящихся в оборудовании симметричных ключей. Разработчики могут применять эти возможности начиная с версии .NET Framework 4.6.2.  Поскольку понятие имен ключей и поставщиков ключей зависит от реализации, для применения этой функции требуется использовать конструктор конкретных типов реализации, а не предпочтительный метод (например, вызов `Aes.Create`).  
  
 Поддержка симметричного шифрования с помощью постоянных ключей доступна для алгоритмов AES ([AesCng](assetId:///T:System.Security.Cryptography.AesCng?qualifyHint=False&autoUpgrade=True)) и 3DES ([TripleDESCng](assetId:///T:System.Security.Cryptography.TripleDESCng?qualifyHint=False&autoUpgrade=True)). Например:  
  
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
 В .NET Framework 4.6.2 добавлена поддержка класса [SignedXml](assetId:///T:System.Security.Cryptography.Xml.SignedXml?qualifyHint=False&autoUpgrade=True) для методов подписи RSA-SHA256, RSA-SHA384 и RSA-SHA512 PKCS#1 и алгоритмов выборки SHA256, SHA384 и SHA512.  
  
 Все константы URI представлены в [SignedXml](xref:System.Security.Cryptography.Xml.SignedXml?qualifyHint=False&autoUpgrade=True):  
  
|Поле SignedXml|Константа|  
|---------------------|--------------|  
|[XmlDsigSHA256Url](assetId:///F:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA256Url?qualifyHint=False&autoUpgrade=True)|"http://www.w3.org/2001/04/xmlenc#sha256"|  
|[XmlDsigRSASHA256Url](assetId:///F:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA256Url?qualifyHint=False&autoUpgrade=True)|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha256"|  
|[XmlDsigSHA384Url](assetId:///F:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA384Url?qualifyHint=False&autoUpgrade=True)|"http://www.w3.org/2001/04/xmldsig-more#sha384"|  
|[XmlDsigRSASHA384Url](assetId:///F:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA384Url?qualifyHint=False&autoUpgrade=True)|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha384"|  
|[XmlDsigSHA512Url](assetId:///F:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA512Url?qualifyHint=False&autoUpgrade=True)|"http://www.w3.org/2001/04/xmlenc#sha512"|  
|[XmlDsigRSASHA512Url](assetId:///F:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA512Url?qualifyHint=False&autoUpgrade=True)|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha512"|  
  
 Программы, которые зарегистрировали пользовательский обработчик [SignatureDescription](assetId:///T:System.Security.Cryptography.SignatureDescription?qualifyHint=False&autoUpgrade=True) в [CryptoConfig](assetId:///T:System.Security.Cryptography.CryptoConfig?qualifyHint=False&autoUpgrade=True) для поддержки этих алгоритмов, будут работать, как и раньше. Но теперь они поддерживаются платформой по умолчанию, поэтому регистрация в [CryptoConfig](assetId:///T:System.Security.Cryptography.CryptoConfig?qualifyHint=False&autoUpgrade=True) больше не требуется.  
  
<a name="SQLClient"></a>   
### <a name="sqlclient"></a>SqlClient  
 Поставщик данных .NET framework для SQL Server ([System.Data.SqlClient](assetId:///N:System.Data.SqlClient?qualifyHint=True&autoUpgrade=True)) включает следующие новые возможности начиная с версии .NET Framework 4.6.2.  
  
 **Объединение подключений в пул и использование времени ожидания в базах данных SQL Azure**  
 Если включено объединение подключений в пул и наступает время ожидания или возникает другая ошибка входа, происходит кэширование исключения. При последующих попытках подключения для следующих 5 секунд на 1 минуту создается кэшированное исключение.  Дополнительные сведения см. в разделе [Объединение подключений в пул (ADO.NET)](../Topic/SQL%20Server%20Connection%20Pooling%20\(ADO.NET\).md).  
  
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
  
 **Усовершенствования функции Always Encrypted**  
 В SQLClient представлены два усовершенствования для функции Always Encrypted.  
  
-   Для повышения производительности параметризованных запросов к зашифрованным столбцам базы данных выполняется кэширование метаданных шифрования для параметров запроса. Если свойство [SqlConnection.ColumnEncryptionQueryMetadataCacheEnabled](assetId:///P:System.Data.SqlClient.SqlConnection.ColumnEncryptionQueryMetadataCacheEnabled?qualifyHint=True&autoUpgrade=True) имеет значение `true` (это значение по умолчанию), то при неоднократном вызове одного и того же запроса клиент получает от сервера метаданные параметров только один раз.  
  
-   Теперь записи ключей шифрования столбцов в кэше ключа вытесняются по истечении интервала времени, настроенного с помощью свойства [SqlConnection.ColumnEncryptionKeyCacheTtl](assetId:///P:System.Data.SqlClient.SqlConnection.ColumnEncryptionKeyCacheTtl?qualifyHint=True&autoUpgrade=True).  
  
<a name="WCF"></a>   
### <a name="windows-communication-foundation"></a>Windows Communication Foundation  
 В.NET Framework 4.6.2 Windows Communication Foundation получила ряд улучшений в следующих областях.  
  
 **Поддержка безопасности транспорта WCF для сертификатов, сохраненных с помощью CNG**  
 Безопасность транспорта WCF поддерживает сертификаты, сохраненные с использованием библиотеки шифрования Windows (CNG). В .NET Framework 4.6.2 эта поддержка ограничивается использованием сертификатов с открытым ключом, длина экспоненты которого не превышает 32 бита. Если приложение предназначено для .NET Framework 4.6.2, эта функция включена по умолчанию.  
  
 Для приложений, которые предназначены для .NET Framework 4.6.1 и более ранних версий, но работают в .NET Framework 4.6.2, эту функцию можно включить отдельно, добавив указанную ниже строку в раздел [\<runtime>](../Topic/%3Cruntime%3E%20Element.md) файла app.config или web.config.  
  
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
 Клиенты могут использовать параметр конфигурации приложения, чтобы проверить поддержку множественных правил коррекции для одного часового пояса в классе [DataContractJsonSerializer](assetId:///T:System.Runtime.Serialization.Json.DataContractJsonSerializer?qualifyHint=False&autoUpgrade=True). Это функция, включаемая пользователем. Чтобы ее включить, добавьте следующий параметр в файл app.config:  
  
```xml  
  
<runtime>  
     <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseTimeZoneInfo=false" />  
</runtime>  
  
```  
  
 Если эта функция включена, то объект [DataContractJsonSerializer](assetId:///T:System.Runtime.Serialization.Json.DataContractJsonSerializer?qualifyHint=False&autoUpgrade=True) использует для десериализации данных даты и времени тип [TimeZoneInfo](assetId:///T:System.TimeZoneInfo?qualifyHint=False&autoUpgrade=True) вместо типа [TimeZone](assetId:///T:System.TimeZone?qualifyHint=False&autoUpgrade=True). Тип [TimeZoneInfo](assetId:///T:System.TimeZoneInfo?qualifyHint=False&autoUpgrade=True), в отличие от типа [TimeZone](assetId:///T:System.TimeZone?qualifyHint=False&autoUpgrade=True), поддерживает множественные правила коррекции, которые позволяют работать с данными часового пояса за прошлые периоды.  
  
 Дополнительные сведения о структуре [TimeZoneInfo](assetId:///T:System.TimeZoneInfo?qualifyHint=False&autoUpgrade=True) и коррекциях часового пояса см. в статье [Общие сведения о часовых поясах](../Topic/Time%20Zone%20Overview.md).  
  
 **Поддержка сохранения времени в формате UTC при сериализации и десериализации с помощью класса XMLSerializer**  
 Когда класс [XmlSerializer](assetId:///T:System.Xml.Serialization.XmlSerializer?qualifyHint=False&autoUpgrade=True) используется для сериализации значения [DateTime](assetId:///T:System.DateTime?qualifyHint=False&autoUpgrade=True) в формате UTC, он обычно создает строку сериализованного времени, которая сохраняет дату и время, но предполагает, что время является местным.  Например, при создании даты и времени в формате UTC путем вызова следующего кода:  
  
```csharp  
DateTime utc = new DateTime(2016, 11, 07, 3, 0, 0, DateTimeKind.Utc);  
```  
  
```vb  
Dim utc As New Date(2016, 11, 07, 3, 0, 0, DateTimeKind.Utc)  
```  
  
 результатом является сериализованная строка времени "03:00:00.0000000-08:00" для системных восьми часов с отставанием от времени в формате UTC.  Сериализованные значения всегда десериализуются как значения местной даты и времени.  
  
 Можно использовать параметр конфигурации приложения, чтобы определить, сохраняет ли [XmlSerializer](assetId:///T:System.Xml.Serialization.XmlSerializer?qualifyHint=False&autoUpgrade=True) данные о часовом поясе UTC при сериализации и десериализации значений [DateTime](assetId:///T:System.DateTime?qualifyHint=False&autoUpgrade=True).  
  
```xml  
  
<runtime>  
     <AppContextSwitchOverrides   
          value="Switch.System.Runtime.Serialization.DisableSerializeUTCDateTimeToTimeAndDeserializeUTCTimeToUTCDateTime=false" />  
</runtime>  
  
```  
  
 Если эта функция включена, то объект [DataContractJsonSerializer](assetId:///T:System.Runtime.Serialization.Json.DataContractJsonSerializer?qualifyHint=False&autoUpgrade=True) использует для десериализации данных даты и времени тип [TimeZoneInfo](assetId:///T:System.TimeZoneInfo?qualifyHint=False&autoUpgrade=True) вместо типа [TimeZone](assetId:///T:System.TimeZone?qualifyHint=False&autoUpgrade=True). Тип [TimeZoneInfo](assetId:///T:System.TimeZoneInfo?qualifyHint=False&autoUpgrade=True), в отличие от типа [TimeZone](assetId:///T:System.TimeZone?qualifyHint=False&autoUpgrade=True), поддерживает множественные правила коррекции, которые позволяют работать с данными часового пояса за прошлые периоды.  
  
 Дополнительные сведения о структуре [TimeZoneInfo](assetId:///T:System.TimeZoneInfo?qualifyHint=False&autoUpgrade=True) и коррекциях часового пояса см. в статье [Общие сведения о часовых поясах](../Topic/Time%20Zone%20Overview.md).  
  
 **Наилучшее соответствие NetNamedPipeBinding**  
 В WCF представлен новый параметр приложения, который может быть задан в клиентских приложениях для их постоянного подключения к службе, прослушивающей URI, наилучшим образом соответствующий запрошенному. Если этот параметр приложения имеет значение `false` (по умолчанию), клиенты могут использовать [NetNamedPipeBinding](assetId:///T:System.ServiceModel.NetNamedPipeBinding?qualifyHint=False&autoUpgrade=True) для подключения к службе, прослушивающей URI, который является подстрокой запрошенного URI.  
  
 Например, клиент пытается подключиться к службе, прослушивающей `net.pipe://localhost/Service1`, но другая служба на этом компьютере, запущенная с правами администратора, прослушивает `net.pipe://localhost`. Если этому параметру приложения задать значение `false`, клиент будет пытаться подключиться не к той службе. После установки значения `true` для параметра приложения клиент будет всегда подключаться к наиболее подходящей службе.  
  
> [!NOTE]
>  Клиенты, использующие [NetNamedPipeBinding](assetId:///T:System.ServiceModel.NetNamedPipeBinding?qualifyHint=False&autoUpgrade=True), находят службы на основе их базового адреса (если он существует), а не на основе полного адреса конечной точки. Чтобы обеспечить постоянную работу этого параметра, служба должна использовать уникальный базовый адрес.  
  
 Для активации этого изменения добавьте следующий параметр в файл App.config или Web.config клиентского приложения:  
  
```xml  
  
<configuration>  
    <appSettings>  
        <add key="wcf:useBestMatchNamedPipeUri" value="true" />  
    </appSettings>  
</configuration>  
  
```  
  
 **SSL 3.0 не является протоколом по умолчанию**  
 При использовании NetTcp для обеспечения безопасности транспорта и применении типа учетных данных сертификата SSL 3.0 больше не является протоколом по умолчанию для согласования безопасного соединения. В большинстве случаев существующие приложения не должны затрагиваться, поскольку TLS 1.0 входит в список протоколов для NetTcp. Все существующие клиенты должны иметь возможность согласовывать подключение с помощью хотя бы TLS 1.0.      Если требуется Ssl3, воспользуйтесь одним из указанных ниже механизмов конфигурации и добавьте его в список установленных протоколов.  
  
-   Свойство [SslStreamSecurityBindingElement.SslProtocols](assetId:///P:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols?qualifyHint=True&autoUpgrade=True)  
  
-   Свойство [TcpTransportSecurity.SslProtocols](assetId:///P:System.ServiceModel.TcpTransportSecurity.SslProtocols?qualifyHint=True&autoUpgrade=True)  
  
-   Раздел [\<transport>](../Topic/%3Ctransport%3E%20of%20%3CnetTcpBinding%3E.md) раздела [\<netTcpBinding>](../Topic/%3CnetTcpBinding%3E.md)  
  
-   Раздел [\<sslStreamSecurity>](../Topic/%3CsslStreamSecurity%3E.md) раздела [\<customBinding>](../Topic/%3CcustomBinding%3E.md)  
  
<a name="WPF462"></a>   
### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)  
 В.NET Framework 4.6.2 Windows Presentation Foundation получила ряд улучшений в следующих областях.  
  
 **Сортировка групп**  
 Приложение, использующее объект [CollectionView](assetId:///T:System.Windows.Data.CollectionView?qualifyHint=False&autoUpgrade=True) для группирования данных, теперь может явно объявлять правила сортировки групп. Явная сортировка позволяет решить проблему неочевидного упорядочивания, которая возникает, когда приложение динамически добавляет или удаляет группы или когда оно изменяет значения свойств элементов, участвующих в группировании. Она также может повысить производительность процесса создания группы путем перемещения сравнений свойств группирования из сортировки полной коллекции в сортировку групп.  
  
 Для поддержки сортировки групп созданы новые свойства [GroupDescription.SortDescriptions](assetId:///P:System.ComponentModel.GroupDescription.SortDescriptions?qualifyHint=True&autoUpgrade=True) и [GroupDescription.CustomSort](assetId:///P:System.ComponentModel.GroupDescription.CustomSort?qualifyHint=True&autoUpgrade=True), которые описывают правила сортировки коллекции групп, созданных объектом [GroupDescription](assetId:///T:System.ComponentModel.GroupDescription?qualifyHint=False&autoUpgrade=True). Они действуют так же, как одноименные свойства объекта [ListCollectionView](assetId:///T:System.Windows.Data.ListCollectionView?qualifyHint=False&autoUpgrade=True), которые описывают правила сортировки элементов данных.  
  
 Два новых статических свойства класса [PropertyGroupDescription](assetId:///T:System.Windows.Data.PropertyGroupDescription?qualifyHint=False&autoUpgrade=True) ([CompareNameAscending](assetId:///P:System.Windows.Data.PropertyGroupDescription.CompareNameAscending?qualifyHint=False&autoUpgrade=True) и [CompareNameDescending](assetId:///P:System.Windows.Data.PropertyGroupDescription.CompareNameDescending?qualifyHint=False&autoUpgrade=True)) можно использовать для наиболее распространенных случаев.  
  
 Например, следующий XAML группирует данные по возрасту, сортирует возрастные группы в порядке возрастания и группирует элементы в каждой возрастной группе по фамилии.  
  
```xaml  
  
<GroupDescriptions>  
     \<PropertyGroupDescription   
         PropertyName=”Age”   
         CustomSort=   
              ”{x:Static PropertyGroupDescription.CompareNamesAscending}”/>  
     </PropertyGroupDescription>  
</GroupDescriptions>  
  
<SortDescriptions>  
     \<SortDescription PropertyName=”LastName”/>  
</SortDescriptions>  
  
```  
  
 **Поддержка программируемой клавиатуры**  
 Поддержка программируемой клавиатуры позволяет отслеживать фокус в приложениях WPF путем автоматического вызова и отклонения новой программируемой клавиатуры в Windows 10 при получении элементом управления, который может принимать текстовые входные данные, сигнала о сенсорном вводе.  
  
 В предыдущих версиях платформы .NET Framework приложения WPF не использовали отслеживание фокуса без отключения поддержки пера и сенсорного ввода WPF.  В результате приложения WPF должны выбрать между полной поддержкой сенсорного ввода WPF или использованием мыши Windows.  
  
 **DPI для каждого монитора**  
 Для поддержки современных сред с высоким и смешанным разрешением платформа WPF в .NET Framework 4.6.2 включает для приложений WPF поддержку DPI для каждого монитора. Дополнительные сведения о включении в приложении WPF поддержки DPI для каждого монитора см. в [примерах и в руководстве разработчика](https://github.com/Microsoft/WPF-Samples/tree/master/PerMonitorDPI) на сайте GitHub.  
  
 В предыдущих версиях платформы .NET Framework приложения WPF поддерживают DPI на уровне системы. Другими словами, ОС соответствующим образом масштабирует пользовательский интерфейс приложения в зависимости от разрешения экрана монитора, на котором отображается приложение. ,  
  
 Для приложений, работающих под управлением .NET Framework 4.6.2, можно отключить изменения DPI для каждого монитора в приложениях WPF, добавив соответствующую инструкцию в раздел [\<runtime>](../Topic/%3Cruntime%3E%20Element.md) файла конфигурации приложения, как показано ниже.  
  
```xml  
  
<runtime>  
   \<AppContextSwitchOverrides value=”Switch.System.Windows.DoNotScaleForDpiChanges=false”/>  
</runtime>  
  
```  
  
<a name="WF462"></a>   
### <a name="windows-workflow-foundation-wf"></a>Windows Workflow Foundation (WF)  
 В .NET Framework 4.6.2 Windows Workflow Foundation содержит ряд улучшений в следующих областях.  
  
 **Поддержка выражений C# и IntelliSense в повторно размещаемом конструкторе WF**  
 Начиная с .NET Framework 4.5 WF поддерживает выражения C# в конструкторе Visual Studio и рабочих процессах кода. Повторно размещаемый конструктор рабочих процессов является ключевой возможностью WF, позволяющей размещать конструкторы рабочих процессов в приложении вне среды Visual Studio (например, в WPF).  Windows Workflow Foundation поддерживает выражения C# и IntelliSense в повторно размещаемом конструкторе рабочих процессов. Дополнительные сведения см. в [блоге по Windows Workflow Foundation](http://go.microsoft.com/fwlink/?LinkID=809042&clcid=0x409).  
  
 `Availability of IntelliSense when a customer rebuilds a workflow project from Visual Studio`  
 В версиях .NET Framework до версии 4.6.2 в случае перестроения проекта рабочего процесса из Visual Studio происходит нарушение работы IntelliSense конструктора WF. Несмотря на успешное построение проекта, типы рабочих процессов отсутствуют в конструкторе, и в окне **Список ошибок** отображаются предупреждения из IntelliSense о недостающих типах рабочего процесса. В .NET Framework 4.6.2 эта проблема решена и IntelliSense работает.  
  
 **Приложения Workflow версии 1 с функцией отслеживания рабочего процесса теперь работают в режиме FIPS**  
 Теперь на компьютерах с включенным режимом поддержки стандарта FIPS можно успешно запускать приложение Workflow версии 1 с функцией отслеживания рабочих процессов. Чтобы реализовать этот сценарий, необходимо внести следующее изменение в файл app.config:  
  
```xml  
<add key="microsoft:WorkflowRuntime:FIPSRequired" value="true" />  
```  
  
 Если этот сценарий не реализован, запущенное приложение продолжает создавать исключение с сообщением "Данная реализация не является частью протестированных криптографических алгоритмов Windows Platform FIPS".  
  
 **Усовершенствования рабочего процесса при использовании динамического обновления с конструктором рабочих процессов Visual Studio**  
 Теперь конструктор рабочих процессов, конструктор действия FlowChart и другие конструкторы действий успешно загружают и отображают рабочие процессы, которые были сохранены после вызова метода [DynamicUpdateServices.PrepareForUpdate](assetId:///M:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate(System.Activities.Activity)?qualifyHint=True&autoUpgrade=True). В версиях .NET Framework до версии 4.6.2 загрузка XAML-файла в Visual Studio для рабочего процесса, который был сохранен после вызова метода [DynamicUpdateServices.PrepareForUpdate](assetId:///M:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate(System.Activities.Activity)?qualifyHint=True&autoUpgrade=True), может привести к возникновению следующих проблем.  
  
-   Конструктор рабочих процессов не может правильно загрузить XAML-файл (если [ViewStateData.Id](assetId:///P:System.Activities.Presentation.ViewState.ViewStateData.Id?qualifyHint=True&autoUpgrade=True) находится в конце строки).  
  
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
 *API неуправляемой отладки* в .NET Framework 4.6.2 при возникновении исключения [NullReferenceException](assetId:///T:System.NullReferenceException?qualifyHint=False&autoUpgrade=True) теперь выполняет дополнительный анализ, чтобы определить, какая переменная в одной строке исходного кода является `null`.   Для поддержки этого сценария в неуправляемый API отладки были добавлены следующие API.  
  
-   Интерфейсы [ICorDebugCode4](../Topic/ICorDebugCode4%20Interface.md), [ICorDebugVariableHome](../Topic/ICorDebugVariableHome%20Interface.md) и [ICorDebugVariableHomeEnum](../Topic/ICorDebugVariableHomeEnum%20Interface.md), предоставляющие собственные начальные расположения управляемых переменных. Это позволяет отладчикам выполнять анализ потока кода при возникновении исключения [NullReferenceException](assetId:///T:System.NullReferenceException?qualifyHint=False&autoUpgrade=True) и работать в обратном порядке для определения управляемой переменной, соответствующей собственному расположению, которая была `null`.  
  
-   Метод [ICorDebugType2::GetTypeID](../Topic/ICorDebugType2::GetTypeID%20Method.md) обеспечивает сопоставление ICorDebugType с [COR_TYPEID](../Topic/COR_TYPEID%20Structure.md), что позволяет отладчику получить [COR_TYPEID](../Topic/COR_TYPEID%20Structure.md) без экземпляра ICorDebugType. Существующие API в [COR_TYPEID](../Topic/COR_TYPEID%20Structure.md) можно использовать для определения макета класса типа.  
  
<a name="v461"></a>   
## <a name="whats-new-in-the-net-framework-461"></a>Новые возможности .NET Framework 4.6.1  
 Версия .NET Framework 4.6.1 включает новые функции в следующих областях:  
  
-   [Шифрование](#Crypto)  
  
-   [ADO.NET](#ADO.NET461)  
  
-   [Windows Presentation Foundation (WPF)](#WPF461)  
  
-   [Windows Workflow Foundation](#WWF461)  
  
-   [Профилирование](#Profile461)  
  
-   [NGen](#NGEN461)  
  
 Дополнительные сведения о версии .NET Framework 4.6.1 приведены в следующих статьях:  
  
-   [Список изменений в .NET Framework 4.6.1](http://go.microsoft.com/fwlink/?LinkId=622964)  
  
-   [Совместимость приложений в 4.6.1](../Topic/Application%20Compatibility%20in%20the%20.NET%20Framework%204.6.1.md)  
  
-   [Различия интерфейсов API .NET Framework](http://go.microsoft.com/fwlink/?LinkId=622989) (на GitHub)  
  
<a name="Crypto"></a>   
### <a name="cryptography-support-for-x509-certificates-containing-ecdsa"></a>Шифрование: поддержка сертификатов X509, содержащих ECDSA  
 В .NET Framework 4.6 добавлена поддержка RSACng сертификатов X509. В .NET Framework 4.6.1 добавлена поддержка сертификатов X509 с алгоритмом ECDSA (цифровых подписей на основе эллиптических кривых).  
  
 ECDSA обеспечивает более высокую производительность и является более безопасным алгоритмом шифрования, чем RSA, предоставляя лучший выбор, когда производительность и масштабируемость TLS представляет собой проблему. Реализация .NET Framework создает оболочку для вызовов существующих функциональных возможностей Windows.  
  
 В следующем примере кода показано, как легко создать подпись для байтового потока, используя новую поддержку сертификатов X 509 ECDSA, включенную в .NET Framework 4.6.1.  
  
<!-- TODO: review snippet reference  [!CODE [whatsnew.461.crypto#1](../CodeSnippet/VS_Snippets_CLR/whatsnew.461.crypto#1)]  -->  
  
 Это обеспечивает заметное отличие от кода, необходимого для создания подписи в .NET Framework 4.6.  
  
<!-- TODO: review snippet reference  [!CODE [whatsnew.461.crypto#2](../CodeSnippet/VS_Snippets_CLR/whatsnew.461.crypto#2)]  -->  
  
<a name="ADO.NET461"></a>   
### ADO.NET В ADO.NET добавлены следующие возможности.  
  
 Поддержка Always Encrypted (постоянного шифрования) для аппаратно защищенных ключей.  
 Теперь ADO.NET поддерживает хранение главных ключей столбца Always Encrypted непосредственно в аппаратных модулях безопасности (HSM). Благодаря этому клиенты могут использовать асимметричные ключи, хранящиеся в аппаратных модулях безопасности, без необходимости написания специальных поставщиков хранилища главных ключей и их регистрации в приложениях.  
  
 Для доступа к постоянно зашифрованным данным, защищенным с помощью главных ключей столбца, хранящихся в аппаратном модуле безопасности, клиенты должны установить на серверах приложений или клиентских компьютерах предоставленный производителем аппаратного модуля безопасности поставщик служб шифрования или поставщики хранилища ключей CNG.  
  
 Улучшение поведения подключения [MultiSubnetFailover](assetId:///P:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover?qualifyHint=False&autoUpgrade=True) для AlwaysOn.  
 SqlClient теперь автоматически обеспечивает более быстрое подключение к группе доступности (AG) AlwaysOn. Он прозрачно определяет, подключается ли ваше приложение к группе доступности AlwaysOn в другой подсети, и быстро обнаруживает текущий активный сервер и обеспечивает подключение к этому серверу. В предыдущих версиях строка подключения приложения должна была включать `“MultisubnetFailover=true”` для указания, что это приложение подключается к группе доступности AlwaysOn. При подключении приложения к группе доступности AlwaysOn без установки значения `true` для этого ключевого слова подключения время ожидания может быть превышено. В этом выпуске больше *не* требуется, чтобы приложение устанавливало [MultiSubnetFailover](assetId:///P:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover?qualifyHint=False&autoUpgrade=True) в значение `true`. Дополнительные сведения о поддержке SqlClient для групп доступности Always On см. в разделе [Поддержка SqlClient для высокого уровня доступности и аварийного восстановления](../Topic/SqlClient%20Support%20for%20High%20Availability,%20Disaster%20Recovery.md).  
  
<a name="WPF461"></a>   
### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)  
 Windows Presentation Foundation содержит ряд улучшений и изменений.  
  
 Повышение производительности  
 В .NET Framework 4.6.1 была исправлена задержка при срабатывании событий касания. Кроме того, ввод в элементе управления [RichTextBox](assetId:///T:System.Windows.Controls.RichTextBox?qualifyHint=False&autoUpgrade=True) больше не препятствует обрабатывающему потоку при быстром вводе данных.  
  
 Улучшения проверки орфографии  
 В Windows 8.1 и последующих версиях проверка орфографии в WPF была обновлена, чтобы для проверки орфографии в дополнительных языках использовалась поддержка операционной системы.  В версиях Windows, предшествующих Windows 8.1, изменения этой функциональности отсутствуют.  
  
 Как и в предыдущих версиях .NET Framework, язык для блока [RichTextBox](assetId:///T:System.Windows.Controls.RichTextBox?qualifyHint=False&autoUpgrade=True) элемента управления [TextBox](assetId:///T:System.Windows.Controls.TextBox?qualifyHint=False&autoUpgrade=True) определяется путем проверки информации в следующем порядке:  
  
-   `xml:lang`, если имеется;  
  
-   текущий язык ввода;  
  
-   язык и региональные параметры текущего потока.  
  
 Дополнительные сведения о языковой поддержке в WPF см. в [публикации в блоге WPF, посвященной компонентам .NET Framework 4.6.1](http://go.microsoft.com/fwlink/?LinkID=691819).  
  
 Дополнительная поддержка индивидуально настраиваемых словарей  
 В .NET Framework 4.6.1 WPF распознает настраиваемые словари, зарегистрированные глобально. Эта возможность доступна наряду с возможностью их регистрации на уровне элемента управления.  
  
 В предыдущих версиях WPF настраиваемые словари не распознавали исключенные слова и списки автозамены. Эти возможности поддерживаются в Windows 8.1 и Windows 10 благодаря использованию файлов, которые могут быть помещены в каталог `%AppData%\Microsoft\Spelling\<language tag>`.  К этим файлам применяются следующие правила.  
  
-   Файлы должны иметь расширения DIC (для добавленных слов), EXC (для исключенных слов) или ACL (для автозамены).  
  
-   Файлы должны представлять собой открытый текст в кодировке UTF-16 LE, который начинается с метки порядка байтов (BOM).  
  
-   Каждая строка должна состоять из слова (в списках добавленных или исключенных слов) или пары автозамены, в которой слова разделены вертикальной чертой ("&#124;") (в списке автозамены).  
  
-   Эти файлы считаются доступными только для чтения и не изменяются системой.  
  
> [!NOTE]
>  Эти новые форматы файлов не поддерживаются непосредственно API-интерфейсами проверки орфографии WPF, и настраиваемые словари, передаваемые в WPF в приложениях, должны продолжать использовать LEX-файлы.  
  
 Примеры  
 В библиотеке MSDN имеется ряд [примеров WPF](https://msdn.microsoft.com/library/ms771633.aspx). Более 200 наиболее популярных примеров (в зависимости от их использования) будут перенесены в [репозиторий GitHub открытого исходного кода](https://github.com/Microsoft/WPF-Samples). Помогите нам улучшить наши примеры, отправив нам запрос на включение внесенных изменений или открыв [вопрос GitHub](https://github.com/Microsoft/WPF-Samples/issues).  
  
 Расширения DirectX  
 WPF включает [пакет NuGet](http://go.microsoft.com/fwlink/?LinkID=691342), предоставляющий новые реализации [D3DImage](assetId:///T:System.Windows.Interop.D3DImage?qualifyHint=False&autoUpgrade=True), которые упрощают взаимодействие с содержимым DX10 и Dx11. Код для этого пакета открыт и доступен [на GitHub](https://github.com/Microsoft/WPFDXInterop).  
  
<a name="WWF461"></a>   
### <a name="windows-workflow-foundation-transactions"></a>Windows Workflow Foundation: транзакции  
 Метод [Transaction.EnlistPromotableSinglePhase](assetId:///Overload:System.Transactions.Transaction.EnlistPromotableSinglePhase?qualifyHint=True&autoUpgrade=True) для повышения уровня транзакции теперь может использовать диспетчер распределенных транзакций, отличный от MSDTC. Для этого вам нужно передать идентификатор GUID диспетчера транзакции в новый перегружаемый метод [Transaction.EnlistPromotableSinglePhase (IPromotableSinglePhaseNotification, Guid)](assetId:///M:System.Transactions.Transaction.EnlistPromotableSinglePhase(System.Transactions.IPromotableSinglePhaseNotification,System.Guid)?qualifyHint=True&autoUpgrade=False). В случае успешного выполнения операции на возможности транзакции накладываются определенные ограничения. После прикрепления отличного от MSDTC диспетчера транзакций следующие методы вызывают исключение [TransactionPromotionException](assetId:///T:System.Transactions.TransactionPromotionException?qualifyHint=False&autoUpgrade=True), так как эти методы требуют повышения уровня до MSDTC.  
  
-   [Transaction.EnlistDurable](assetId:///Overload:System.Transactions.Transaction.EnlistDurable?qualifyHint=True&autoUpgrade=True)  
  
-   [TransactionInterop.GetDtcTransaction](assetId:///M:System.Transactions.TransactionInterop.GetDtcTransaction(System.Transactions.Transaction)?qualifyHint=True&autoUpgrade=True)  
  
-   [TransactionInterop.GetExportCookie](assetId:///M:System.Transactions.TransactionInterop.GetExportCookie(System.Transactions.Transaction,System.Byte[])?qualifyHint=True&autoUpgrade=True)  
  
-   [TransactionInterop.GetTransmitterPropagationToken](assetId:///M:System.Transactions.TransactionInterop.GetTransmitterPropagationToken(System.Transactions.Transaction)?qualifyHint=True&autoUpgrade=True)  
  
 После прикрепления отличного от MSDTC диспетчера транзакций он должен использоваться для будущих долговременных прикреплений с использованием протоколов, которые он задает. Идентификатор [Guid](assetId:///T:System.Guid?qualifyHint=False&autoUpgrade=True) диспетчера транзакций можно получить с помощью свойства [PromoterType](assetId:///P:System.Transactions.Transaction.PromoterType?qualifyHint=False&autoUpgrade=True). Когда выполняется повышение уровня транзакции, диспетчер транзакций предоставляет массив [Byte](assetId:///T:System.Byte?qualifyHint=False&autoUpgrade=True), представляющий токен повышенного уровня. Этот токен повышенного уровня для транзакции, уровень которой повышается отличным от MSDTC диспетчером транзакций, приложение может получить с помощью метода [GetPromotedToken](assetId:///M:System.Transactions.Transaction.GetPromotedToken?qualifyHint=False&autoUpgrade=True).  
  
 Пользователи новой перегрузки [Transaction.EnlistPromotableSinglePhase(IPromotableSinglePhaseNotification, Guid)](assetId:///M:System.Transactions.Transaction.EnlistPromotableSinglePhase(System.Transactions.IPromotableSinglePhaseNotification,System.Guid)?qualifyHint=True&autoUpgrade=False) должны придерживаться определенной последовательности вызовов, чтоб операция повышения уровня завершилась успешно. Эти правила описаны в документации по данному методу.  
  
<a name="Profile461"></a>   
### <a name="profiling"></a>Профилирование  
 Неуправляемый API профилирования был улучшен следующим образом.  
  
 Улучшенная поддержка доступа к PDB-файлам в интерфейсе [ICorProfilerInfo7](../Topic/ICorProfilerInfo7%20Interface.md)  
 В ASP.Net 5 сборки все чаще компилируются в памяти с помощью Roslyn. Для разработчиков средств профилирования это означает, что PDB-файлы, которые ранее были сериализованы на диске, могут больше не присутствовать. Средства профилирования часто используют PDB-файлы для сопоставления кода с исходными строками для таких задач, как анализ покрытия кода или построковый анализ производительности. Интерфейс [ICorProfilerInfo7](../Topic/ICorProfilerInfo7%20Interface.md) теперь включает два новых метода, [ICorProfilerInfo7::GetInMemorySymbolsLength](../Topic/ICorProfilerInfo7::GetInMemorySymbolsLength%20Method.md) и [ICorProfilerInfo7::ReadInMemorySymbols](../Topic/ICorProfilerInfo7::ReadInMemorySymbols.md), для предоставления этим средствам профилирования доступа к данным PDB-файлов в памяти. С помощью новых API профилировщик может получить содержимое PDB-файлов в памяти в виде массива байтов, а затем обработать его или сериализовать на диск.  
  
 Улучшено инструментирование с использованием интерфейса ICorProfiler.  
 Профилировщики, использующие функциональность ReJit API `ICorProfiler` для динамического инструментирования, теперь могут изменять некоторые метаданные. Ранее такие средства могли инструментировать IL в любое время, но метаданные могли изменяться только во время загрузки модуля. Поскольку IL ссылается на метаданные, это ограничивает типы инструментирования, которое может выполняться. Мы отменили некоторые из этих ограничений, добавив метод [ICorProfilerInfo7::ApplyMetaData](../Topic/ICorProfilerInfo7::ApplyMetaData%20Method.md) для поддержки подмножества правок метаданных после загрузки модуля, в частности путем добавления новых записей `AssemblyRef`, `TypeRef`, `TypeSpec`, `MemberRef`, `MemberSpec` и `UserString`. Это изменение существенно расширяет спектр возможного динамического инструментирования.  
  
<a name="NGEN461"></a>   
### <a name="native-image-generator-ngen-pdbs"></a>PDB-файлы генератора образов в машинном коде (NGEN)  
 Трассировка событий между компьютерами позволяет клиентам профилировать программу на компьютере А и просматривать данные профилирования с сопоставлением исходных строк на компьютере Б. Используя предыдущие версии .NET Framework, пользователь может копировать все модули и образы в машинном коде из профилируемого компьютера на компьютер анализа, содержащий PDB-файл IL, для создания сопоставления "источник-машинный код". Хотя этот процесс может хорошо работать в том случае, если файлы относительно невелики, например для телефонных приложений, на настольных системах эти файлы могут быть очень большими, и на их копирование потребуется значительное время.  
  
 С помощью PDB-файлов Ngen NGen может создать PDB-файл, содержащий сопоставления "IL-машинный код" без зависимости от PDB-файла IL. В нашем сценарии трассировки событий между компьютерами все, что требуется, — это скопировать PDB-файл образа в машинном коде, созданный на компьютере А, на компьютер Б, а затем использовать [API доступа к интерфейсу отладки](https://docs.microsoft.com/en-us/visualstudio/debugger/debug-interface-access/debug-interface-access-sdk-reference) для чтения сопоставления "машинный код-IL" PDB-файла IL и сопоставления "IL-машинный код" PDB-файла образа в машинном коде. Объединение обоих сопоставлений обеспечивает сопоставление "источник-машинный код". Поскольку PDB-файл образа в машинном коде PDB намного меньше, чем все модули и образы в машинном коде, процесс копирования с компьютера А на компьютер Б выполняется гораздо быстрее.  
  
<a name="v46"></a>   
## <a name="whats-new-in-net-2015"></a>Новые возможности .NET 2015  
 .NET 2015 включает .NET Framework 4.6 и .NET Core. Некоторые функции применяются к обеим версиям, а некоторые только к .NET Framework 4.6 или .NET Core.  
  
-   **ASP.NET 5**  
  
     .NET 2015 включает ASP.NET 5 — экономичную платформу .NET для создания современных облачных приложений. Платформа является модульной, поэтому вы можете включить только те функции, которые нужны в приложении. Она может быть размещена в IIS или резидентно в пользовательском процессе, и вы можете запустить приложения с разными версиями .NET Framework на одном сервере. В нее входит новая система конфигурации среды, предназначенная для развертывания облака.  
  
     MVC, веб-API и веб-страницы объединены в одну платформу, которая называется MVC 6. Вы создаете приложения ASP.NET 5 с помощью новых средств в Visual Studio 2015. Существующие приложения будут работать на новой платформе .NET Framework; однако, чтобы создать приложение с MVC 6 или SignalR 3, нужно использовать систему проектов в Visual Studio 2015.  
  
     Дополнительные сведения см. в разделе [ASP.NET 5](http://go.microsoft.com/fwlink/?LinkId=518238).  
  
-   **Обновления ASP.NET**  
  
    -   **API на основе задач для асинхронной очистки ответов**  
  
         ASP.NET теперь предоставляет простой API на основе задач [HttpResponse.FlushAsync](assetId:///M:System.Web.HttpResponse.FlushAsync?qualifyHint=True&autoUpgrade=True) для асинхронной очистки ответов, который позволяет асинхронно сбрасывать ответы, используя поддержку операторов `async/await` языка программирования.  
  
    -   `Model binding supports task-returning methods`  
  
         В версии .NET Framework 4.5 в ASP.NET добавлена функция привязки модели, которая обеспечивает расширяемый, ориентированный на код подход к операциям с данными CRUD на страницах веб-форм и пользовательских элементов управления. Система привязки модели теперь поддерживает возвращающие [задачи](assetId:///T:System.Threading.Tasks.Task?qualifyHint=False&autoUpgrade=True) методы для привязки модели. Эта функция позволяет разработчикам веб-форм сочетать преимущества масштабируемости асинхронного программирования с простотой системы привязки данных при использовании более новых версий моделей ORM, включая Entity Framework.  
  
         Асинхронная привязка модели управляется параметром конфигурации `aspnet:EnableAsyncModelBinding`.  
  
        ```  
  
        <appSettings>  
           <add key=" aspnet:EnableAsyncModelBinding" value="true|false" />  
        </appSettings>  
  
        ```  
  
         Для приложений, предназначенных для .NET Framework 4.6, по умолчанию используется значение `true`. Для приложений, выполняющихся в .NET Framework 4.6, но предназначенных для более ранних версий .NET Framework, по умолчанию используется значение `false`. Включить этот режим можно, задав для параметра конфигурации значение `true`.  
  
    -   **Поддержка HTTP/2 (Windows 10)**  
  
         [HTTP/2](http://www.wikipedia.org/wiki/HTTP/2) — это новая версия протокола HTTP, которая обеспечивает более эффективное подключение (меньшее число круговых путей между клиентом и сервером) и уменьшение задержки при загрузке веб-страницы для пользователей.  HTTP/2 обеспечивает максимальное преимущество для веб-страниц (по сравнению со службами), так как оптимизирует запрос различных артефактов в ходе одной операции. Поддержка HTTP/2 добавлена в ASP.NET в .NET Framework 4.6. Так как сетевые функции существуют на нескольких уровнях, для новых компонентов в Windows, IIS и ASP.NET потребовалось включить HTTP/2. Для использования HTTP/2 с ASP.NET приложение должно выполняться в Windows 10.  
  
         Протокол HTTP/2 также поддерживается и включен по умолчанию для приложений универсальной платформы Windows (UWP) для Windows 10, использующих API [System.Net.Http.HttpClient](assetId:///T:System.Net.Http.HttpClient?qualifyHint=True&autoUpgrade=True).  
  
         Чтобы обеспечить возможность использовать компонент [PUSH_PROMISE](http://http2.github.io/http2-spec/#PUSH_PROMISE) в приложениях ASP.NET, в класс [HttpResponse](assetId:///T:System.Web.HttpResponse?qualifyHint=False&autoUpgrade=True) добавлен новый метод с двумя перегрузками, [PushPromise(String)](assetId:///M:System.Web.HttpResponse.PushPromise(System.String)?qualifyHint=False&autoUpgrade=False) и [PushPromise(String, String, NameValueCollection)](assetId:///M:System.Web.HttpResponse.PushPromise(System.String,System.String,System.Collections.Specialized.NameValueCollection)?qualifyHint=False&autoUpgrade=False).  
  
        > [!NOTE]
        >  Хотя ASP.NET 5 поддерживает HTTP/2, поддержка функции PUSH PROMISE еще не была добавлена.  
  
         Всю работу выполняют браузер и веб-сервер (IIS в Windows). Нет необходимости перекладывать нагрузку на пользователей.  
  
         Большинство [основных браузеров поддерживает HTTP/2](http://www.wikipedia.org/wiki/HTTP/2), поэтому вполне вероятно, что пользователи смогут воспользоваться преимуществами протокола HTTP/2, если его поддерживает ваш сервер.  
  
    -   **Поддержка протокола привязки токенов**  
  
         Корпорация Майкрософт и Google совместно работают над созданием нового подхода к проверке подлинности, называемого протоколом привязки токенов, или [Token Binding Protocol](https://github.com/TokenBinding/Internet-Drafts). Предполагается, что токены проверки подлинности (в кэше браузера) могут быть украдены и использованы злоумышленниками для получения доступа к защищенным в иных обстоятельствах ресурсам (например, к вашему банковскому счету) без помощи пароля или других конфиденциальных сведений. Новый протокол предназначен для устранения этой проблемы.  
  
         Протокол привязки токенов будет реализован в Windows 10 в качестве компонента браузера. Приложения ASP.NET будут участвовать в протоколе для подтверждения действительности токенов проверки подлинности. Реализации клиента и сервера будут обеспечивать комплексную защиту, заданную этим протоколом.  
  
    -   **Алгоритм случайного хэширования строк**  
  
         В .NET Framework 4.5 появился [алгоритм случайного хэширования строк](https://msdn.microsoft.com/library/jj152924.aspx). Однако он не поддерживается ASP.NET, так как некоторые компоненты ASP.NET зависят от стабильного хэш-кода. В .NET Framework 4.6 теперь поддерживаются алгоритмы случайного хэширования строк. Чтобы включить эту функцию, используйте параметр конфигурации `aspnet:UseRandomizedStringHashAlgorithm`.  
  
        ```  
  
        <appSettings>  
           <add key="aspnet:UseRandomizedStringHashAlgorithm" value="true|false" />  
        </appSettings>  
  
        ```  
  
-   **ADO.NET**  
  
     ADO .NET теперь поддерживает функцию «Всегда зашифровано», которая доступна в CTP-версии 2 SQL Server 2016. Благодаря функции «Всегда зашифровано» SQL Server может выполнять операции с зашифрованными данными, и, что важнее всего, ключ шифрования хранится в самом приложении в доверенной среде клиента, а не на сервере. Функция «Всегда зашифровано» защищает данные клиента, поэтому администраторы базы данных не имеют доступа к данным в формате обычного текста. Шифрование и расшифровка данных происходит прозрачно на уровне драйвера, что сводит к минимуму изменения, которые должны быть выполнены для существующих приложений. Дополнительные сведения см. в разделах [Always Encrypted (ядро СУБД)](https://msdn.microsoft.com/library/mt163865\(v=sql.130\).aspx) и [Постоянное шифрование (разработка клиентских приложений)](https://msdn.microsoft.com/library/mt147923\(v=sql.130\).aspx).  
  
-   **64-разрядный компилятор JIT для управляемого кода**  
  
     В .NET Framework 4.6 представлена новая версия 64-разрядного JIT-компилятора (первоначальное кодовое имя RyuJIT). Новый 64-разрядный компилятор имеет значительно большую производительность, чем предыдущий 64-разрядный JIT-компилятор. Новый 64-разрядный компилятор включен для 64-разрядных процессов, выполняющихся на основе .NET Framework 4.6. Приложение будет работать в 64-разрядном процессе, если оно скомпилировано как 64-разрядное или AnyCPU и выполняется в 64-разрядной операционной системе. Хотя приняты все необходимые меры, чтобы обеспечить как можно более прозрачный переход на новый компилятор, возможны изменения в поведении. Мы будем благодарны за любые отзывы о проблемах, возникших при использовании нового JIT-компилятора. Свяжитесь с нами через сайт [Microsoft Connect](http://connect.microsoft.com/) в случае возникновения проблемы, которая может быть связана с новым 64-разрядным JIT-компилятором.  
  
     Новый 64-разрядный JIT-компилятор также включает функции аппаратного ускорения SIMD при работе с типами с поддержкой SIMD в пространстве имен [System.Numerics](assetId:///N:System.Numerics?qualifyHint=False&autoUpgrade=True), что может обеспечить неплохое повышение производительности.  
  
-   **Усовершенствования загрузчика сборок**  
  
     Загрузчик сборок теперь более эффективно использует память благодаря выгрузке сборок IL после загрузки соответствующего образа NGEN. Это изменение снижает использование виртуальной памяти, что особенно полезно для больших 32-разрядных приложений (например, Visual Studio); кроме того, оно обеспечивает экономию физической памяти.  
  
-   **Изменения библиотеки с базовым классом**  
  
     В .NET Framework 4.6 были добавлены многие новые API для поддержки важных сценариев. Внесены следующие изменения и дополнения.  
  
    -   **Реализации IReadOnlyCollection\<T>**  
  
         Дополнительные коллекции реализуют [IReadOnlyCollection\<T>](assetId:///T:System.Collections.Generic.IReadOnlyCollection`1?qualifyHint=False&autoUpgrade=True), например [Queue<T\>](assetId:///T:System.Collections.Generic.Queue`1?qualifyHint=False&autoUpgrade=True) и [Stack\<T>](assetId:///T:System.Collections.Generic.Stack`1?qualifyHint=False&autoUpgrade=True).  
  
    -   **CultureInfo.CurrentCulture и CultureInfo.CurrentUICulture**  
  
         Свойства [CultureInfo.CurrentCulture](assetId:///P:System.Globalization.CultureInfo.CurrentCulture?qualifyHint=True&autoUpgrade=True) и [CultureInfo.CurrentUICulture](assetId:///P:System.Globalization.CultureInfo.CurrentUICulture?qualifyHint=True&autoUpgrade=True) теперь доступны для чтения и записи, а не только для чтения. Если вы назначите этим свойствам новый объект [CultureInfo](assetId:///T:System.Globalization.CultureInfo?qualifyHint=False&autoUpgrade=True), изменяются также язык и региональные параметры, определенные свойством `Thread.CurrentThread.CurrentCulture` для текущего потока и свойствами `Thread.CurrentThread.CurrentUICulture` для текущего потока пользовательского интерфейса.  
  
    -   **Усовершенствования сборки мусора**  
  
         Класс [GC](assetId:///T:System.GC?qualifyHint=False&autoUpgrade=True) теперь включает методы [TryStartNoGCRegion](assetId:///M:System.GC.TryStartNoGCRegion(System.Int64)?qualifyHint=False&autoUpgrade=True) и [EndNoGCRegion](assetId:///M:System.GC.EndNoGCRegion?qualifyHint=False&autoUpgrade=True), которые позволяют запретить сбор мусора во время выполнения критического пути.  
  
         Новая перегрузка метода [GC.Collect(Int32, GCCollectionMode, Boolean, Boolean)](assetId:///M:System.GC.Collect(System.Int32,System.GCCollectionMode,System.Boolean,System.Boolean)?qualifyHint=True&autoUpgrade=False) позволяет контролировать, выполняется ли для кучи мелких объектов и кучи больших объектов очистка и сжатие, или только очистка.  
  
    -   **Типы с поддержкой SIMD**  
  
         Пространство имен [System.Numerics](assetId:///N:System.Numerics?qualifyHint=False&autoUpgrade=True) теперь включает несколько типов с поддержкой SIMD, таких как [Matrix3x2](assetId:///T:System.Numerics.Matrix3x2?qualifyHint=False&autoUpgrade=True), [Matrix4x4](assetId:///T:System.Numerics.Matrix4x4?qualifyHint=False&autoUpgrade=True), [Plane](assetId:///T:System.Numerics.Plane?qualifyHint=False&autoUpgrade=True), [Quaternion](assetId:///T:System.Numerics.Quaternion?qualifyHint=False&autoUpgrade=True), [Vector2](assetId:///T:System.Numerics.Vector2?qualifyHint=False&autoUpgrade=True), [Vector3](assetId:///T:System.Numerics.Vector3?qualifyHint=False&autoUpgrade=True) и [Vector4](assetId:///T:System.Numerics.Vector4?qualifyHint=False&autoUpgrade=True).  
  
         Поскольку новый 64-разрядный JIT-компилятор также включает функции аппаратного ускорения SIMD, особенно значительное повышение производительности обеспечивается при использовании типов с поддержкой SIMD с новым 64-разрядным JIT-компилятором.  
  
    -   **Обновления шифрования**  
  
         API-интерфейс [System.Security.Cryptography](assetId:///N:System.Security.Cryptography?qualifyHint=True&autoUpgrade=True) теперь поддерживает [интерфейсы API шифрования Windows CNG](https://msdn.microsoft.com/library/windows/desktop/aa376214.aspx). Предыдущие версии .NET Framework полностью полагались на [более раннюю версию API шифрования Windows](https://msdn.microsoft.com/library/windows/desktop/aa380255.aspx) в качестве основы для реализации [System.Security.Cryptography](assetId:///N:System.Security.Cryptography?qualifyHint=True&autoUpgrade=True). Мы получали много запросов на реализацию поддержки API CNG, так как он поддерживает [современные алгоритмы шифрования](https://msdn.microsoft.com/library/windows/desktop/bb204775.aspx#suite_b_support), что очень важно для некоторых категорий приложений.  
  
         Платформа .NET Framework 4.6 включает следующие новые усовершенствования для поддержки API-интерфейсов шифрования CNG Windows.  
  
        -   Набор методов расширения для сертификатов X509, `System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)` и `System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)`, которые возвращают реализацию на основе CNG, а не реализацию на основе CAPI (по возможности). (Некоторые смарт-карты и т. д. по-прежнему требуют CAPI, и API-интерфейсы обрабатывают резервный вариант.)  
  
        -   Класс [System.Security.Cryptography.RSACng](assetId:///T:System.Security.Cryptography.RSACng?qualifyHint=True&autoUpgrade=True), который предоставляет реализацию CNG алгоритма RSA.  
  
        -   Улучшения API RSA, позволяющие отказаться от обязательного приведения общих действий. Например, для шифрования данных с помощью объекта [X509Certificate2](assetId:///T:System.Security.Cryptography.X509Certificates.X509Certificate2?qualifyHint=False&autoUpgrade=True) в предыдущих версиях платформы .NET Framework требуется код, аналогичный следующему.  
  
<!-- TODO: review snippet reference              [!CODE [WhatsNew.Casting#1](../CodeSnippet/VS_Snippets_CLR/whatsnew.casting#1)]  -->  
  
             Code that uses the new cryptography APIs in the .NET Framework 4.6 can be rewritten as follows to avoid the cast.  
  
<!-- TODO: review snippet reference              [!CODE [WhatsNew.Casting#2](../CodeSnippet/VS_Snippets_CLR/whatsnew.casting#2)]  -->  
  
    -   **Поддержка преобразования даты и времени в формат времени Unix и обратно**  
  
         Следующие новые методы были добавлены в структуру [DateTimeOffset](assetId:///T:System.DateTimeOffset?qualifyHint=False&autoUpgrade=True) для поддержки преобразования значений даты и времени в формат Unix или из него.  
  
        -   [DateTimeOffset.FromUnixTimeSeconds](assetId:///M:System.DateTimeOffset.FromUnixTimeSeconds(System.Int64)?qualifyHint=True&autoUpgrade=True)  
  
        -   [DateTimeOffset.FromUnixTimeMilliseconds](assetId:///M:System.DateTimeOffset.FromUnixTimeMilliseconds(System.Int64)?qualifyHint=True&autoUpgrade=True)  
  
        -   [DateTimeOffset.ToUnixTimeSeconds](assetId:///M:System.DateTimeOffset.ToUnixTimeSeconds?qualifyHint=True&autoUpgrade=True)  
  
        -   [DateTimeOffset.ToUnixTimeMilliseconds](assetId:///M:System.DateTimeOffset.ToUnixTimeMilliseconds?qualifyHint=True&autoUpgrade=True)  
  
    -   **Параметры совместимости**  
  
         Новый класс [AppContext](assetId:///T:System.AppContext?qualifyHint=False&autoUpgrade=True) добавляет новый компонент совместимости, который позволяет авторам библиотек предоставлять пользователям согласованный механизм отказа от новых функциональных возможностей. Он устанавливает слабо связанный контракт между компонентами для передачи запроса на явный отказ. Эта возможность обычно важна при внесении изменений в существующие функции. В свою очередь, режим неявного согласия для новых функциональных возможностей уже существует.  
  
         С помощью [AppContext](assetId:///T:System.AppContext?qualifyHint=False&autoUpgrade=True) библиотеки определяют и предоставляют параметры совместимости, а использующий их код может устанавливать эти параметры, чтобы изменять поведение библиотек. По умолчанию библиотеки предоставляют новые функции и изменяют их (то есть предоставляют прежние функции) только в том случае, если установлен параметр.  
  
         Приложение (или библиотека) может объявить значение параметра (который всегда имеет тип [Boolean](assetId:///T:System.Boolean?qualifyHint=False&autoUpgrade=True)), определенного зависимой библиотекой. Параметр всегда имеет неявное значение `false`. Установка значения `true` для параметра включает его. Явно задание значения `false` для параметра определяет новое поведение.  
  
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
  
        -   *параметр*.*пространство_имен*  *имя_параметра*  
  
        -   *параметр*.*библиотека*.*имя_параметра*  
  
    -   **Изменения асинхронной модели на основе задач**  
  
         Для приложений, предназначенных для .NET Framework 4.6, объекты [Task](assetId:///T:System.Threading.Tasks.Task?qualifyHint=False&autoUpgrade=True) и [Task\<TResult>](assetId:///T:System.Threading.Tasks.Task`1?qualifyHint=False&autoUpgrade=True) наследуют язык и региональные параметры, а также язык и региональные параметры интерфейса пользователя вызывающего потока. Поведение приложений на предыдущих версиях платформы .NET Framework или без определенной версии .NET Framework не затрагивается. Дополнительные сведения см. в разделе "Язык и региональные параметры в асинхронных операциях на основе задач" статьи, посвященной классу [CultureInfo](assetId:///T:System.Globalization.CultureInfo?qualifyHint=False&autoUpgrade=True).  
  
         Класс [System.Threading.AsyncLocal\<T>](assetId:///T:System.Threading.AsyncLocal`1?qualifyHint=True&autoUpgrade=True) позволяет представлять внешние данные, локальные для определенного асинхронного потока управления, например метода `async`. Его можно использовать для сохранения данных в разных потоках. Кроме того, вы можете определить метод обратного вызова, который получает уведомление при каждом изменении внешних данных из-за явного изменения свойства [AsyncLocal<T\>.Value](assetId:///P:System.Threading.AsyncLocal`1.Value?qualifyHint=True&autoUpgrade=True) или из-за перехода к новому контексту в потоке.  
  
         В асинхронную модель на основе задач добавлены три удобных метода ([Task.CompletedTask](assetId:///P:System.Threading.Tasks.Task.CompletedTask?qualifyHint=True&autoUpgrade=True), [Task.FromCanceled](assetId:///M:System.Threading.Tasks.Task.FromCanceled(System.Threading.CancellationToken)?qualifyHint=True&autoUpgrade=True) и [Task.FromException](assetId:///M:System.Threading.Tasks.Task.FromException(System.Exception)?qualifyHint=True&autoUpgrade=True)), которые возвращают завершенные задачи в определенном состоянии.  
  
         Теперь класс [NamedPipeClientStream](assetId:///T:System.IO.Pipes.NamedPipeClientStream?qualifyHint=False&autoUpgrade=True) поддерживает асинхронное взаимодействие благодаря новому методу [ConnectAsync](assetId:///M:System.IO.Pipes.NamedPipeClientStream.ConnectAsync?qualifyHint=False&autoUpgrade=True). метод.  
  
    -   **EventSource теперь поддерживает запись в журнал событий**  
  
         Теперь класс [EventSource](assetId:///T:System.Diagnostics.Tracing.EventSource?qualifyHint=False&autoUpgrade=True) можно использовать для регистрации административных или рабочих сообщений в журнале событий, вместе с любыми существующими сеансами трассировки событий Windows, созданными на компьютере. Раньше для обеспечения этих функций приходилось использовать пакет Microsoft.Diagnostics.Tracing.EventSource NuGet. Эти функции теперь встроены в .NET Framework 4.6.  
  
         Обновления пакета NuGet и .NET Framework 4.6 включают следующие функции.  
  
        -   **Динамические события**  
  
             Возможность определения событий "на лету" без создания методов событий.  
  
        -   **Разнородные полезные данные**  
  
             Возможность передавать массивы и классы со специальными атрибутами, а также типы-примитивы в качестве полезных данных.  
  
        -   **Отслеживание действий**  
  
             События Start и Stop помечают возникающие между ними события идентификатором, который представляет все текущие активные действия.  
  
         Для поддержки этих функций перегруженный в класс [EventSource](assetId:///T:System.Diagnostics.Tracing.EventSource?qualifyHint=False&autoUpgrade=True) добавлен перегруженный метод [Write](assetId:///M:System.Diagnostics.Tracing.EventSource.Write(System.String)?qualifyHint=False&autoUpgrade=True).  
  
-   **Windows Presentation Foundation (WPF)**  
  
    -   **Усовершенствования HDPI**  
  
         В .NET Framework 4.6 улучшена поддержка HDPI в WPF. В округление макетов внесены изменения для снижения числа вхождений обрезки в элементах управления с границами. По умолчанию эта функция включена только в том случае, если атрибут [TargetFrameworkAttribute](assetId:///T:System.Runtime.Versioning.TargetFrameworkAttribute?qualifyHint=False&autoUpgrade=True) имеет значение .NET 4.6.  Для приложений, которые предназначены для более ранних версий платформы, но выполняются в .NET Framework 4.6, новое поведение можно активировать отдельно, добавив следующую строку в раздел [\<runtime>](../Topic/%3Cruntime%3E%20Element.md) файла app.config:  
  
        ```  
  
        <AppContextSwitchOverrides  
        value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false"  
        />  
  
        ```  
  
         Окна WPF, разнесенные на несколько мониторов с разными параметрами DPI (настройка нескольких параметров разрешения), теперь отображаются полностью, без черных областей. Можно отключить это новое поведение, добавив следующую строку в раздел `<appSettings>` файла app.config.  
  
        ```  
  
        <add key="EnableMultiMonitorDisplayClipping" value="true"/>  
  
        ```  
  
         Поддержка автоматической загрузки правильного курсора в зависимости от параметров DPI добавлена в [System.Windows.Input.Cursor](assetId:///T:System.Windows.Input.Cursor?qualifyHint=True&autoUpgrade=True).  
  
    -   **Улучшено касание**  
  
         В .NET Framework 4.6 решена проблема с касанием, приводившим к непредсказуемому поведению, о которой сообщает клиент на веб-сайте [Connect](https://connect.microsoft.com/VisualStudio/feedback/details/903760/). Пороговое значение двойного касания для приложений Магазина Windows и приложений WPF теперь одинаково в Windows 8.1 и более поздних версий.  
  
    -   **Поддержка прозрачных дочерних окон**  
  
         WPF в .NET Framework 4.6 поддерживает прозрачные дочерние окна в Windows 8.1 и более поздних версий. Это позволяет создавать непрямоугольные и прозрачные дочерние окна в окнах верхнего уровня. Эту функцию можно включить, установив для свойства [HwndSourceParameters.UsesPerPixelTransparency](assetId:///P:System.Windows.Interop.HwndSourceParameters.UsesPerPixelTransparency?qualifyHint=True&autoUpgrade=True) значение `true`.  
  
-   **Windows Communication Foundation (WCF)**  
  
    -   **Поддержка SSL**  
  
         Теперь WCF помимо SSL 3.0 и TLS 1.0 поддерживает SSL-версии TLS 1.1 и TLS 1.2 при использовании NetTcp с безопасностью транспорта и проверкой подлинности клиента. Теперь можно выбрать, какой протокол использовать, или отключить старые менее безопасные протоколы. Это можно сделать, задав свойство [SslProtocols](assetId:///P:System.ServiceModel.TcpTransportSecurity.SslProtocols?qualifyHint=False&autoUpgrade=True) или добавив следующие данные в файл конфигурации.  
  
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
  
    -   **Отправка сообщений с помощью разных подключений HTTP**  
  
         WCF теперь позволяет пользователям отправлять некоторые сообщения с помощью разных базовых HTTP-подключений. Это можно сделать двумя способами.  
  
        -   **С помощью префикса имени группы подключений**  
  
             Пользователи могут указать строку, которую WCF будет использовать как префикс достижения для имени группы подключений. Два сообщения с разными префиксами отправляются с помощью разных базовых HTTP-подключений. Префикс задается путем добавления пары "ключ-значение" в свойство [Message.Properties](assetId:///P:System.ServiceModel.Channels.Message.Properties?qualifyHint=True&autoUpgrade=True) сообщения. Ключ — это "HttpTransportConnectionGroupNamePrefix"; значение — желаемый префикс.  
  
        -   **С помощью разных фабрик каналов**  
  
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
  
-   **Tранзакции**  
  
     Теперь вы можете включить идентификатор распределенной транзакции для транзакций, вызвавших создание исключения, наследуемого от [TransactionException](assetId:///T:System.Transactions.TransactionException?qualifyHint=False&autoUpgrade=True). Это можно сделать, добавив следующий ключ в раздел `appSettings` файла app.config:  
  
    ```  
    <add key="Transactions:IncludeDistributedTransactionIdInExceptionMessage" value="true"/>   
    ```  
  
     Значение по умолчанию — `false`.  
  
-   **Сеть**  
  
    -   **Повторное использование сокета**  
  
         Windows 10 включает новый алгоритм сетевых подключений с высокой масштабируемостью, который повышает эффективность использования ресурсов компьютера путем повторного использования локальных портов для исходящих TCP-подключений. .NET Framework 4.6 поддерживает новый алгоритм, который позволяет приложениям .NET воспользоваться преимуществами нового режима работы. В предыдущих версиях Windows существовало искусственно заданное ограничение числа параллельных подключений (обычно 16 384, размер динамического диапазона портов по умолчанию), которое могло ограничивать масштабируемость службы, вызывая нехватку портов при высокой загрузке.  
  
         В .NET Framework 4.6 добавлены два новых API, которые обеспечивают повторное использование портов и эффективно снимают ограничение на 64 000 одновременных подключения.  
  
        -   Значение перечисления [SocketOptionName.ReuseUnicastPort](assetId:///T:System.Net.Sockets.SocketOptionName?qualifyHint=True&autoUpgrade=True).  
  
        -   Свойство [ServicePointManager.ReusePort](assetId:///P:System.Net.ServicePointManager.ReusePort?qualifyHint=True&autoUpgrade=True).  
  
         По умолчанию свойство [ServicePointManager.ReusePort](assetId:///P:System.Net.ServicePointManager.ReusePort?qualifyHint=True&autoUpgrade=True) имеет значение `false`, если в качестве значения `HWRPortReuseOnSocketBind` для раздела реестра `HKLM\SOFTWARE\Microsoft\.NETFramework\v4.0.30319` не задано 0x1. Чтобы включить повторное использование локальных портов для HTTP-подключений, задайте для свойства [ServicePointManager.ReusePort](assetId:///P:System.Net.ServicePointManager.ReusePort?qualifyHint=True&autoUpgrade=True) значение `true`. В результате все исходящие подключения сокета TCP от [HttpClient](assetId:///T:System.Net.Http.HttpClient?qualifyHint=False&autoUpgrade=True) и [HttpWebRequest](assetId:///T:System.Net.HttpWebRequest?qualifyHint=False&autoUpgrade=True) будут использовать новый параметр [O_REUSE_UNICASTPORT](https://msdn.microsoft.com/library/windows/desktop/ms740532.aspx) сокета Windows 10, который разрешает повторное использование локальных портов.  
  
         Разработчики, создающие приложения, работающие только с сокетами, могут указать параметр [SocketOptionName.ReuseUnicastPort](assetId:///T:System.Net.Sockets.SocketOptionName?qualifyHint=True&autoUpgrade=True) при вызове такого метода, как [Socket.SetSocketOption](assetId:///M:System.Net.Sockets.Socket.SetSocketOption(System.Net.Sockets.SocketOptionLevel,System.Net.Sockets.SocketOptionName,System.Byte[])?qualifyHint=True&autoUpgrade=True), чтобы исходящие сокеты повторно использовали локальные порты для привязки.  
  
    -   **Поддержка международных доменных имен и PunyCode**  
  
         В класс [Uri](assetId:///T:System.Uri?qualifyHint=False&autoUpgrade=True) добавлено новое свойство [IdnHost](assetId:///P:System.Uri.IdnHost?qualifyHint=False&autoUpgrade=True), обеспечивающее более эффективную поддержку международных доменных имен и PunyCode.  
  
-   **Изменение размеров элементов управления Windows Forms.**  
  
     Эта функция в .NET Framework 4.6 дополнена типами [DomainUpDown](assetId:///T:System.Windows.Forms.DomainUpDown?qualifyHint=False&autoUpgrade=True), [NumericUpDown](assetId:///T:System.Windows.Forms.NumericUpDown?qualifyHint=False&autoUpgrade=True), [DataGridViewComboBoxColumn](assetId:///T:System.Windows.Forms.DataGridViewComboBoxColumn?qualifyHint=False&autoUpgrade=True), [DataGridViewColumn](assetId:///T:System.Windows.Forms.DataGridViewColumn?qualifyHint=False&autoUpgrade=True) и [ToolStripSplitButton](assetId:///T:System.Windows.Forms.ToolStripSplitButton?qualifyHint=False&autoUpgrade=True), а также прямоугольником, который определяется параметром [Bounds](assetId:///P:System.Drawing.Design.PaintValueEventArgs.Bounds?qualifyHint=False&autoUpgrade=True) при отображении [UITypeEditor](assetId:///T:System.Drawing.Design.UITypeEditor?qualifyHint=False&autoUpgrade=True).  
  
     Это функция, включаемая пользователем. Чтобы ее включить, задайте для элемента `EnableWindowsFormsHighDpiAutoResizing` в файле конфигурации приложения (app.config) значение `true`:  
  
    ```  
  
    <appSettings>  
       <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />  
    </appSettings>  
  
    ```  
  
-   **Поддержка кодировок кодовых страниц**  
  
     .NET Core в первую очередь поддерживает кодировки Юникод и по умолчанию предоставляет ограниченную поддержку для кодировок кодовых страниц. Вы можете добавить поддержку для кодировок кодовых страниц, доступных в .NET Framework, но не поддерживаемых в .NET Core, зарегистрировав кодировки кодовых страниц в методе [Encoding.RegisterProvider](assetId:///M:System.Text.Encoding.RegisterProvider(System.Text.EncodingProvider)?qualifyHint=True&autoUpgrade=True). Дополнительные сведения см. в документации для класса [System.Text.CodePagesEncodingProvider](xref:System.Text.CodePagesEncodingProvider).  
  
-   **.NET Native**  
  
     Приложения Windows для Windows 10, ориентированные на .NET Core и написанные на языке C# или Visual Basic, могут использовать новую технологию компиляции приложения в машинный код вместо кода IL. Они создают приложения, которым присуща более быстрая загрузка и время выполнения. Дополнительные сведения см. в разделе [Компиляция приложений с помощью .NET Native](../Topic/Compiling%20Apps%20with%20.NET%20Native.md). Общие сведения о .NET Native и рассмотрение отличий такой компиляции от компиляции JIT и NGEN, а также ее влияние на код см. в разделе [.NET Native и компиляция](../Topic/.NET%20Native%20and%20Compilation.md).  
  
     Приложения компилируются в машинный код по умолчанию, если компиляция выполняется с помощью Visual Studio 2015. Дополнительные сведения см. в разделе [Начало работы с .NET Native](../Topic/Getting%20Started%20with%20.NET%20Native.md).  
  
     Для поддержки отладки приложений .NET Native в  интерфейс API отладки неуправляемого кода добавлено несколько новых интерфейсов и перечислений. Дополнительные сведения см. в разделе [Отладка (справочник по неуправляемым API)](../Topic/Debugging%20\(Unmanaged%20API%20Reference\).md).  
  
-   **Пакеты .NET Framework с открытым исходным кодом**  
  
     Пакеты .NET Core, такие как неизменяемые коллекции, [API SIMD](http://go.microsoft.com/fwlink/?LinkID=518639) и сетевые интерфейсы API, например из пространства имен [System.Net.Http](assetId:///N:System.Net.Http?qualifyHint=False&autoUpgrade=True), теперь доступны в виде пакетов с открытым исходным кодом на сайте [GitHub](https://github.com/). Сведения о доступе к этому коду см. в разделе [NetFx на GitHub](http://go.microsoft.com/fwlink/?LinkID=518634). Дополнительные сведения и инструкции, как принять участие в этих пакетах, см. в разделе [Ядро .NET и открытый исходный код](../Topic/.NET%20Core%20and%20Open-Source.md)[домашней странице .NET на GitHub](http://go.microsoft.com/fwlink/?LinkID=518635).  
  
 [К началу](#introduction)  
  
<a name="v452"></a>   
## <a name="whats-new-in-the-net-framework-452"></a>Новые возможности .NET Framework 4.5.2  
  
-   **Новые API для приложений ASP.NET.** Новые методы [HttpResponse.AddOnSendingHeaders](assetId:///M:System.Web.HttpResponse.AddOnSendingHeaders(System.Action{System.Web.HttpContext})?qualifyHint=True&autoUpgrade=True) и [HttpResponseBase.AddOnSendingHeaders](assetId:///M:System.Web.HttpResponseBase.AddOnSendingHeaders(System.Action{System.Web.HttpContextBase})?qualifyHint=True&autoUpgrade=True) позволяют проверять и изменять заголовки и код состояния, когда ответ сбрасывается в клиентское приложение. Мы рекомендуем использовать эти методы вместо событий [PreSendRequestHeaders](assetId:///E:System.Web.HttpApplication.PreSendRequestHeaders?qualifyHint=False&autoUpgrade=True) и [PreSendRequestContent](assetId:///E:System.Web.HttpApplication.PreSendRequestContent?qualifyHint=False&autoUpgrade=True), так как они более эффективны и надежны.  
  
     Метод [HostingEnvironment.QueueBackgroundWorkItem](assetId:///M:System.Web.Hosting.HostingEnvironment.QueueBackgroundWorkItem(System.Action{System.Threading.CancellationToken})?qualifyHint=True&autoUpgrade=True) позволяет назначать небольшие фоновые рабочие элементы. ASP.NET отслеживает эти элементы и блокирует резкое прерывание службами IIS рабочего процесса до выполнения всех фоновых рабочих элементов. Этот метод нельзя вызвать за пределами управляемого домена приложений ASP.NET.  
  
     Новые свойства [HttpResponse.HeadersWritten](assetId:///P:System.Web.HttpResponse.HeadersWritten?qualifyHint=True&autoUpgrade=False) и [HttpResponseBase.HeadersWritten](assetId:///P:System.Web.HttpResponseBase.HeadersWritten?qualifyHint=True&autoUpgrade=False) возвращают логические значения, которые указывают, были ли записаны заголовки ответа. Эти свойства можно использовать, чтобы гарантировать успешность некоторых вызовов API, например [HttpResponse.StatusCode](assetId:///P:System.Web.HttpResponse.StatusCode?qualifyHint=True&autoUpgrade=True) (который создает исключения, если заголовки уже записаны).  
  
-   **Изменение размеров элементов управления Windows Forms.** Эта функция была расширена. Теперь системный параметр DPI можно использовать для изменения размера компонентов следующих дополнительных элементов управления (например, стрелки, раскрывающей поле со списком):  
  
     [ComboBox](assetId:///T:System.Windows.Forms.ComboBox?qualifyHint=False&autoUpgrade=True)   
     [ToolStripComboBox](assetId:///T:System.Windows.Forms.ToolStripComboBox?qualifyHint=False&autoUpgrade=True)   
     [ToolStripMenuItem](assetId:///T:System.Windows.Forms.ToolStripMenuItem?qualifyHint=False&autoUpgrade=True)   
     [Cursor](assetId:///T:System.Windows.Forms.Cursor?qualifyHint=False&autoUpgrade=True)   
     [DataGridView](assetId:///T:System.Windows.Forms.DataGridView?qualifyHint=False&autoUpgrade=True)   
     [DataGridViewComboBoxColumn](assetId:///T:System.Windows.Forms.DataGridViewComboBoxColumn?qualifyHint=False&autoUpgrade=True)  
  
     Это функция, включаемая пользователем. Чтобы ее включить, задайте для элемента `EnableWindowsFormsHighDpiAutoResizing` в файле конфигурации приложения (app.config) значение `true`:  
  
    ```  
    <appSettings>  
       <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />  
    </appSettings>  
    ```  
  
-   **Новая функция рабочего процесса.** Диспетчер ресурсов, который использует метод [EnlistPromotableSinglePhase](assetId:///M:System.Transactions.Transaction.EnlistPromotableSinglePhase(System.Transactions.IPromotableSinglePhaseNotification)?qualifyHint=False&autoUpgrade=True) (и, следовательно, реализует интерфейс [IPromotableSinglePhaseNotification](assetId:///T:System.Transactions.IPromotableSinglePhaseNotification?qualifyHint=False&autoUpgrade=True)), может использовать новый метод [Transaction.PromoteAndEnlistDurable](assetId:///M:System.Transactions.Transaction.PromoteAndEnlistDurable(System.Guid,System.Transactions.IPromotableSinglePhaseNotification,System.Transactions.ISinglePhaseNotification,System.Transactions.EnlistmentOptions)?qualifyHint=True&autoUpgrade=True) для следующих запросов:  
  
    -   повышение транзакции до уровня "координатор распределенных транзакций (Майкрософт)" (MSDTC);  
  
    -   замена [IPromotableSinglePhaseNotification](assetId:///T:System.Transactions.IPromotableSinglePhaseNotification?qualifyHint=False&autoUpgrade=True) на [ISinglePhaseNotification](assetId:///T:System.Transactions.ISinglePhaseNotification?qualifyHint=False&autoUpgrade=True), который является устойчивым зачислением и поддерживает однофазные фиксации.  
  
     Эту операцию можно выполнить в том же домене приложения; для повышения уровня не требуется написание дополнительного неуправляемого кода для взаимодействия с MSDTC. Новый метод можно вызывать только при наличии ожидающего выполнения вызова из [System.Transactions](assetId:///N:System.Transactions?qualifyHint=True&autoUpgrade=True) к методу [IPromotableSinglePhaseNotification](assetId:///T:System.Transactions.IPromotableSinglePhaseNotification?qualifyHint=False&autoUpgrade=True)`Promote`, который реализуется зачислением с возможностью повышения уровня.  
  
-   **Усовершенствования профилирования.** Следующие новые неуправляемые API профилирования обеспечивают более надежное профилирование:  
  
     [Структура COR_PRF_ASSEMBLY_REFERENCE_INFO](../Topic/COR_PRF_ASSEMBLY_REFERENCE_INFO%20Structure.md)   
     [Перечисление COR_PRF_HIGH_MONITOR](../Topic/COR_PRF_HIGH_MONITOR%20Enumeration.md)   
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
  
-   **Повышение уровня транзакции и преобразование ее в устойчивое зачисление**  
  
     В версиях .NET Framework 4.6 и 4.5.2 добавлен новый интерфейс API [Transaction.PromoteAndEnlistDurable](assetId:///M:System.Transactions.Transaction.PromoteAndEnlistDurable(System.Guid,System.Transactions.IPromotableSinglePhaseNotification,System.Transactions.ISinglePhaseNotification,System.Transactions.EnlistmentOptions)?qualifyHint=True&autoUpgrade=True).  
  
    ```  
  
    [System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]  
    public Enlistment PromoteAndEnlistDurable(Guid resourceManagerIdentifier,  
                                              IPromotableSinglePhaseNotification promotableNotification,  
                                              ISinglePhaseNotification enlistmentNotification,  
                                              EnlistmentOptions enlistmentOptions)  
  
    ```  
  
     Этот метод может использоваться в зачислениях, созданных ранее в [Transaction.EnlistPromotableSinglePhase](assetId:///M:System.Transactions.Transaction.EnlistPromotableSinglePhase(System.Transactions.IPromotableSinglePhaseNotification)?qualifyHint=True&autoUpgrade=True) по вызову метода [ITransactionPromoter.Promote](assetId:///M:System.Transactions.ITransactionPromoter.Promote?qualifyHint=True&autoUpgrade=True). Он запрашивает у `System.Transactions` повышение уровня транзакции до транзакции MSDTC и "преобразование" зачисления, допускающего повышение уровня, в зачисление устойчивых ресурсов. После успешного завершения этого метода `System.Transactions` больше не будет ссылаться на интерфейс [IPromotableSinglePhaseNotification](assetId:///T:System.Transactions.IPromotableSinglePhaseNotification?qualifyHint=False&autoUpgrade=True), и все последующие уведомления будут доставляться в предоставленный интерфейс [ISinglePhaseNotification](assetId:///T:System.Transactions.ISinglePhaseNotification?qualifyHint=False&autoUpgrade=True). Рассматриваемое зачисление должно работать как зачисление устойчивых ресурсов, поддерживая ведение журнала транзакций и восстановления. Подробнее см. документацию по [Transaction.EnlistDurable](assetId:///M:System.Transactions.Transaction.EnlistDurable(System.Guid,System.Transactions.IEnlistmentNotification,System.Transactions.EnlistmentOptions)?qualifyHint=True&autoUpgrade=True). Кроме того, зачисления должны поддерживать [ISinglePhaseNotification](assetId:///T:System.Transactions.ISinglePhaseNotification?qualifyHint=False&autoUpgrade=True).  Этот метод может вызываться *только* во время обработки вызова [ITransactionPromoter.Promote](assetId:///M:System.Transactions.ITransactionPromoter.Promote?qualifyHint=True&autoUpgrade=True). В противном случае создается исключение [TransactionException](assetId:///T:System.Transactions.TransactionException?qualifyHint=False&autoUpgrade=True).  
  
 [К началу](#introduction)  
  
<a name="v451"></a>   
## <a name="whats-new-in-the-net-framework-451"></a>Новые возможности .NET Framework 4.5.1  
 **Обновления апреля 2014 г.**:  
  
-   [Обновление 2 для Visual Studio 2013](http://go.microsoft.com/fwlink/p/?LinkId=393658) включает обновления для шаблонов переносимой библиотеки классов для поддержки следующих сценариев:  
  
    -   Возможность использовать API среды выполнения Windows в переносимых библиотеках, предназначенных для Windows 8.1, Windows Phone 8.1 и Windows Phone Silverlight 8.1.  
  
    -   возможность включить XAML-код (типы Windows.UI.XAML) в переносимые библиотеки, предназначенные для Windows 8.1 или Windows Phone 8.1. Поддерживаются следующие шаблоны XAML: "Пустая страница", "Словарь ресурсов", "Шаблонный элемент управления" и "Пользовательский элемент управления".  
  
    -   Можно создать переносной компонент среды выполнения Windows (WINMD-файл) для использования в приложениях магазинов, предназначенных для Windows 8.1 и Windows Phone 8.1.  
  
    -   Можно изменить целевую платформу библиотеки классов Магазина Windows или Магазина Windows Phone, такой как переносимая библиотека классов.  
  
     Дополнительные сведения об этих изменениях см. в разделе [Переносимая библиотека классов](../Topic/Cross-Platform%20Development%20with%20the%20Portable%20Class%20Library.md).  
  
-   Набор содержимого .NET Framework теперь включает документацию для .NET Native. Это технология предварительной компиляции для сборки и развертывания приложений Windows. .NET Native компилирует приложения напрямую в машинный код, а не в промежуточный язык (IL), что повышает производительность. Подробные сведения см. в разделе [Компиляция приложений с помощью .NET Native](../Topic/Compiling%20Apps%20with%20.NET%20Native.md).  
  
-   На странице [.NET Framework Reference Source](http://referencesource.microsoft.com/) предоставляются новые возможности навигации и расширенные функции. Теперь можно искать исходный код .NET Framework в Интернете, [загрузить справочник](http://referencesource.microsoft.com/download.html) для автономной работы и пошагово просматривать источники (включая исправления и обновления) во время отладки. Дополнительные сведения см. в записи блога [Новый облик .NET Reference Source](http://blogs.msdn.com/b/dotnet/archive/2014/02/24/a-new-look-for-net-reference-source.aspx).  
  
 Основные новые функции и улучшения в .NET Framework 4.5.1 включают следующие:  
  
-   Автоматическая переадресация привязки для сборок. Начиная с версии Visual Studio 2013 при компиляции приложения, ориентированного на .NET Framework 4.5.1, в файл конфигурации приложения можно добавить переадресации привязок, если приложение или его компоненты ссылаются на несколько версий одной и той же сборки. Включить эту функцию также можно для проектов, предназначенных для более ранних версий платформы .NET Framework. Дополнительные сведения см. в разделе [Практическое руководство. Включение и отключение автоматического перенаправления привязки](../Topic/How%20to:%20Enable%20and%20Disable%20Automatic%20Binding%20Redirection.md).  
  
-   Возможность сбора диагностической информации, чтобы помочь разработчикам повысить производительность серверных и облачных приложений. Дополнительные сведения см. в документации методов [WriteEventWithRelatedActivityId](assetId:///M:System.Diagnostics.Tracing.EventSource.WriteEventWithRelatedActivityId(System.Int32,System.Guid,System.Object[])?qualifyHint=False&autoUpgrade=True) и [WriteEventWithRelatedActivityIdCore](assetId:///M:System.Diagnostics.Tracing.EventSource.WriteEventWithRelatedActivityIdCore(System.Int32,System.Guid*,System.Int32,System.Diagnostics.Tracing.EventSource.EventData*)?qualifyHint=False&autoUpgrade=True) класса [EventSource](assetId:///T:System.Diagnostics.Tracing.EventSource?qualifyHint=False&autoUpgrade=True).  
  
-   Возможность явно уплотнять кучу больших объектов во время сборки мусора. Дополнительные сведения см. в описании свойства [GCSettings.LargeObjectHeapCompactionMode](assetId:///P:System.Runtime.GCSettings.LargeObjectHeapCompactionMode?qualifyHint=True&autoUpgrade=True).  
  
-   Дополнительные улучшения производительности, например приостановка приложений ASP.NET, усовершенствования многоядерного JIT и более быстрый запуск приложений после обновления платформы .NET Framework. Дополнительные сведения см. в [объявлении о выходе .NET Framework 4.5.1](http://blogs.msdn.com/b/dotnet/archive/2013/06/26/announcing-the-net-framework-4-5-1-preview.aspx) и в публикации в блоге [о приостановке приложения ASP.NET](http://blogs.msdn.com/b/dotnet/archive/2013/10/09/asp-net-app-suspend-responsive-shared-net-web-hosting.aspx).  
  
 Усовершенствования в Windows Forms включают следующие:  
  
-   Изменение размеров элементов управления Windows Forms. Системный параметр DPI можно использовать для изменения размера компонентов элементов управления (например, значков, которые отображаются в сетке свойств) путем явного включения с помощью записи в файле конфигурации приложения (app.config) нужного приложения. Эта функция в настоящее время поддерживается для следующих элементов управления Windows Forms:  
  
     [PropertyGrid](assetId:///T:System.Windows.Forms.PropertyGrid?qualifyHint=False&autoUpgrade=True)   
     [TreeView](assetId:///T:System.Windows.Forms.TreeView?qualifyHint=False&autoUpgrade=True)   
     Поддерживаются некоторые аспекты [DataGridView](assetId:///T:System.Windows.Forms.DataGridView?qualifyHint=False&autoUpgrade=True) (дополнительные поддерживаемые элементы управления перечислены в разделе о [новых возможностях в версии 4.5.2](#v452)).  
  
     Чтобы включить эту функцию, добавьте новый элемент \<appSettings> в файл конфигурации (app.config) и задайте для элемента `EnableWindowsFormsHighDpiAutoResizing` значение `true`:  
  
    ```  
    <appSettings>  
       <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />  
    </appSettings>  
    ```  
  
 В процесс отладки приложений .NET Framework в Visual Studio 2013 внесены следующие улучшения.  
  
-   Возвращаемые значения в отладчике Visual Studio. При отладке управляемого приложения в Visual Studio 2013 в окне "Видимые" отображаются возвращаемые типы и значения для методов. Эти сведения доступны для приложений для настольных систем, приложений для Магазина Windows и приложений Windows Phone. Дополнительные сведения см. в статье [Анализ значений, возвращаемых из вызовов методов](http://msdn.microsoft.com/library/e3245b37-8e2e-4200-ba84-133726e95f1f\(v=vs.120\).aspx) в библиотеке MSDN.  
  
-   "Изменить и продолжить" для 64-разрядных приложений. Visual Studio 2013 поддерживает действие "Изменить и продолжить" для 64-разрядных управляемых приложений для настольных систем, приложений для Магазина Windows и приложений для Windows Phone. Существующие ограничения остаются действующими и для 32-разрядных, и для 64-разрядных приложений (см. последний раздел статьи [Поддерживаемые изменения кода (C#)](http://msdn.microsoft.com/library/ms164927\(v=vs.120\).aspx)).  
  
-   Отладка с поддержкой асинхронности. Чтобы упростить отладку асинхронных приложений в Visual Studio 2013, стеке вызовов скрывает код инфраструктуры, предоставляемый компиляторами для поддержки асинхронного программирования, а также цепочки логических родительских кадров, что упрощает прослеживание логики выполнения программы. В окне "Задачи", которое заменяет собой окно "Параллельные задачи", отображаются задачи, относящиеся к определенной точке останова, а также все другие задачи, которые в данный момент активны или запланированы в приложении. Вы можете прочесть об этой возможности в разделе "Отладка с поддержкой асинхронности" [объявления о выходе .NET Framework 4.5.1](http://blogs.msdn.com/b/dotnet/archive/2013/06/26/announcing-the-net-framework-4-5-1-preview.aspx).  
  
-   Усовершенствованная поддержка исключений для компонентов среды выполнения Windows. В Windows 8.1 все исключения, возникающие в приложениях для Магазина Windows, сохраняют сведения об ошибке, которая вызвала исключение, даже при переходе через границы языков. Вы можете прочесть об этой возможности в разделе "Разработка приложений для Магазина Windows" [объявления о выходе .NET Framework 4.5.1](http://blogs.msdn.com/b/dotnet/archive/2013/06/26/announcing-the-net-framework-4-5-1-preview.aspx).  
  
 Начиная с Visual Studio 2013 вы можете использовать [Управляемое средство профильной оптимизации (Mpgo.exe)](../Topic/Mpgo.exe%20\(Managed%20Profile%20Guided%20Optimization%20Tool\).md) для оптимизации приложений для Магазина Windows 8.x и для настольных систем.  
  
 Список новых возможностей в ASP.NET 4.5.1 см. в разделе [ASP.NET 4.5.1 и Visual Studio 2013](http://go.microsoft.com/fwlink/?LinkID=309094) на сайте ASP.NET.  
  
 [К началу](#introduction)  
  
<a name="core"></a>   
## <a name="whats-new-in-the-net-framework-45"></a>Новые возможности .NET Framework 4.5  
  
### <a name="core-new-features-and-improvements"></a>Основные новые функции и усовершенствования  
  
-   Возможность уменьшения количества перезапусков системы путем обнаружения и закрытия приложений .NET Framework 4 во время развертывания. См. раздел [Уменьшение числа перезагрузок при установке платформы .NET Framework 4.5](../Topic/Reducing%20System%20Restarts%20During%20.NET%20Framework%204.5%20Installations.md).  
  
-   Поддержка массивов, размер которых превышает 2 ГБ, на 64-разрядных платформах. Эту функцию можно включить в файле конфигурации приложения. См. описание [элемента \<gcAllowVeryLargeObjects>](../Topic/%3CgcAllowVeryLargeObjects%3E%20Element.md), в котором также перечислены другие ограничения на размер объекта и размер массива.  
  
-   Улучшенная производительность благодаря фоновой сборке мусора для серверов. Если вы используете серверную сборку мусора в .NET Framework 4.5, фоновая сборка мусора включается автоматически. Сведения см. в разделе "Фоновая сборка мусора сервера" статьи [Основы сборки мусора](../Topic/Fundamentals%20of%20Garbage%20Collection.md).  
  
-   Фоновая компиляция по требованию (JIT), которая доступна по выбору на многоядерных процессорах для повышения производительности приложения. См. статью [Класс ProfileOptimization](assetId:///T:System.Runtime.ProfileOptimization?qualifyHint=False&autoUpgrade=True).  
  
-   Возможность ограничения времени, в течение которого обработчик регулярных выражений будет пытаться разрешить регулярное выражение до истечения срока действия выражения. См. описание свойства [Regex.MatchTimeout](assetId:///P:System.Text.RegularExpressions.Regex.MatchTimeout?qualifyHint=True&autoUpgrade=True).  
  
-   Возможность определить язык и региональные параметры по умолчанию для домена приложения. См. описание класса [CultureInfo](assetId:///T:System.Globalization.CultureInfo?qualifyHint=False&autoUpgrade=True).  
  
-   Консольная поддержка кодировки Юникод (UTF-16). См. описание класса [Console](assetId:///T:System.Console?qualifyHint=False&autoUpgrade=True).  
  
-   Поддержка управления версиями данных сортировки и сравнения строк, зависящих от языка и региональных параметров. См. описание класса [SortVersion](assetId:///T:System.Globalization.SortVersion?qualifyHint=False&autoUpgrade=True).  
  
-   Улучшенная производительность при извлечении ресурсов. См. раздел [Упаковка и развертывание ресурсов](../Topic/Packaging%20and%20Deploying%20Resources%20in%20Desktop%20Apps.md).  
  
-   Усовершенствования в области сжатия ZIP, позволяющие уменьшить размер сжатого файла. См. описание пространства имен [System.IO.Compression](assetId:///N:System.IO.Compression?qualifyHint=True&autoUpgrade=True).  
  
-   Возможность настраивать контекст отражения для переопределения поведения отражения по умолчанию с помощью класса [CustomReflectionContext](assetId:///T:System.Reflection.Context.CustomReflectionContext?qualifyHint=False&autoUpgrade=True).  
  
-   Поддержка версии 2008 стандарта интернационализированных доменных имен в приложениях (Internationalized Domain Names in Applications, IDNA) при использовании класса [System.Globalization.IdnMapping](assetId:///T:System.Globalization.IdnMapping?qualifyHint=True&autoUpgrade=True) в среде Windows 8.  
  
-   Делегирование сравнения строк операционной системе, которая реализует Юникод 6.0, при использовании .NET Framework в среде Windows 8. При работе на других платформах .NET Framework включает собственные данные сравнения строк, которые реализуют Юникод 5.x. См. описание класса [String](assetId:///T:System.String?qualifyHint=False&autoUpgrade=True) и раздел "Примечания" в описании класса [SortVersion](assetId:///T:System.Globalization.SortVersion?qualifyHint=False&autoUpgrade=True).  
  
-   Возможность вычисления хэш-кодов для строк для каждого домена приложения. См. раздел [Элемент \<UseRandomizedStringHashAlgorithm>](../Topic/%3CUseRandomizedStringHashAlgorithm%3E%20Element.md).  
  
-   Поддержка отражения типов разделяется между классами [Type](assetId:///T:System.Type?qualifyHint=False&autoUpgrade=True) и [TypeInfo](assetId:///T:System.Reflection.TypeInfo?qualifyHint=False&autoUpgrade=True). См. раздел [Отражение в .NET Framework для приложений Магазина Windows](../Topic/Reflection%20in%20the%20.NET%20Framework%20for%20Windows%20Store%20Apps.md).  
  
### <a name="managed-extensibility-framework-mef"></a>Managed Extensibility Framework (MEF)  
 В .NET Framework 4.5 для Managed Extensibility Framework (MEF) предоставлены следующие новые возможности.  
  
-   Поддержка универсальных типов.  
  
-   Модель программирования на основе соглашений, позволяющая создавать части на основе соглашений об именах, а не на основе атрибутов.  
  
-   Множественные области действия.  
  
-   Подмножество MEF, которое можно использовать при создании приложений для Магазина Windows 8.x. Это подмножество доступно как [загружаемый пакет](http://go.microsoft.com/fwlink/?LinkId=256238) из коллекции NuGet. Чтобы установить пакет, откройте проект в Visual Studio, выберите **Управление пакетами NuGet** в меню **Проект** и выполните поиск пакета `Microsoft.Composition` в Интернете.  
  
 Дополнительные сведения см. в разделе [Managed Extensibility Framework](../Topic/Managed%20Extensibility%20Framework%20\(MEF\).md).  
  
### <a name="asynchronous-file-operations"></a>Асинхронные операции с файлами  
 В .NET Framework 4.5 добавлены новые асинхронные возможности в языки C# и Visual Basic. Эти возможности представляют собой модель на основе задач для выполнения асинхронных операций. Для использования этой новой модели используйте асинхронные методы в классах ввода-вывода. См. раздел [Асинхронные операции файлового ввода-вывода](../Topic/Asynchronous%20File%20I-O.md).  
  
<a name="tools"></a>   
### <a name="tools"></a>Инструменты  
 В .NET Framework 4.5 генератор файлов ресурсов (Resgen.exe) позволяет преобразовать RESOURCES-файл, внедренный в сборку .NET Framework, в RESW-файл для использования в приложениях Магазина Windows 8.x. Дополнительные сведения см. в разделе [Resgen.exe (генератор файлов ресурсов)](../Topic/Resgen.exe%20\(Resource%20File%20Generator\).md).  
  
 Средство управляемой оптимизации с использованием профиля (Mpgo.exe) позволяет сократить время запуска приложения, улучшить использование памяти (размер рабочего множества) и пропускную способность путем оптимизации сборок машинных образов. Этот инструмент командной строки формирует данные профилирования для сборок машинного образа приложения. См. раздел [Mpgo.exe (инструмент управляемой оптимизации с использованием профиля)](../Topic/Mpgo.exe%20\(Managed%20Profile%20Guided%20Optimization%20Tool\).md). Начиная с Visual Studio 2013 вы можете использовать средство Mpgo.exe для оптимизации приложений для Магазина Windows 8.x и для настольных систем.  
  
<a name="parallel"></a>   
### <a name="parallel-computing"></a>Параллельные вычисления  
 В .NET Framework 4.5 предусмотрено несколько новых возможностей и усовершенствований для параллельных вычислений. К ним относятся повышение производительности, повышение управляемости, улучшенная поддержка асинхронного программирования, новая библиотека потоков данных и улучшенная поддержка параллельной отладки и анализа производительности. См. запись [Новые возможности параллелизма в .NET 4.5](http://go.microsoft.com/fwlink/?LinkId=235061) в блоге, посвященном параллельному программированию в .NET.  
  
<a name="web"></a>   
### <a name="web"></a>Интернет  
 В ASP.NET 4.5 и 4.5.1 добавилась привязка модели для Web Forms, поддержка WebSocket, асинхронные обработчики, усовершенствования для повышения производительности и многие другие возможности. Дополнительные сведения см. в следующих ресурсах:  
  
-   [ASP.NET 4.5 и Visual Studio 2012](../Topic/ASP.NET%20Core%20and%20Visual%20Studio%202015.md) в библиотеке MSDN.  
  
-   [ASP.NET 4.5.1 и Visual Studio 2013](http://go.microsoft.com/fwlink/?LinkID=309094) на сайте ASP.NET.  
  
<a name="networking"></a>   
### <a name="networking"></a>Сеть  
 .NET Framework 4.5 предоставляет новый интерфейс программирования для приложений HTTP. Дополнительные сведения см. в описании новых пространств имен [System.Net.Http](assetId:///N:System.Net.Http?qualifyHint=True&autoUpgrade=True) и [System.Net.Http.Headers](assetId:///N:System.Net.Http.Headers?qualifyHint=True&autoUpgrade=True).  
  
 Также добавлена поддержка нового интерфейса программирования для создания соединения WebSocket и взаимодействия с ним с помощью существующего класса [HttpListener](assetId:///T:System.Net.HttpListener?qualifyHint=False&autoUpgrade=True) и связанных с ним классов. Дополнительные сведения см. в описании нового пространства имен [System.Net.WebSockets](assetId:///N:System.Net.WebSockets?qualifyHint=False&autoUpgrade=True) и класса [HttpListener](assetId:///T:System.Net.HttpListener?qualifyHint=False&autoUpgrade=True).  
  
 Кроме того, в .NET Framework 4.5 улучшено сетевое взаимодействие.  
  
-   RFC-совместимая поддержка URI. Дополнительные сведения см. в описании [Uri](assetId:///T:System.Uri?qualifyHint=False&autoUpgrade=True) и связанных с ним классов.  
  
-   Поддержка синтаксического анализа интернационализированных доменных имен (Internationalized Domain Name, IDN). Дополнительные сведения см. в описании [Uri](assetId:///T:System.Uri?qualifyHint=False&autoUpgrade=True) и связанных с ним классов.  
  
-   Поддержка интернационализации адресов электронной почты (Email Address Internationalization, EAI). Дополнительные сведения см. в описании пространства имен [System.Net.Mail](assetId:///N:System.Net.Mail?qualifyHint=False&autoUpgrade=True).  
  
-   Улучшенная поддержка протокола IPv6. Дополнительные сведения см. в описании пространства имен [System.Net.NetworkInformation](assetId:///N:System.Net.NetworkInformation?qualifyHint=False&autoUpgrade=True).  
  
-   Поддержка сокета с двойным режимом. Дополнительные сведения см. в описании классов [Socket](assetId:///T:System.Net.Sockets.Socket?qualifyHint=False&autoUpgrade=True) и [TcpListener](assetId:///T:System.Net.Sockets.TcpListener?qualifyHint=False&autoUpgrade=True).  
  
<a name="client"></a>   
### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)  
 В .NET Framework 4.5 для Windows Presentation Foundation (WPF) добавлены изменения и усовершенствования в следующих областях.  
  
-   Новый элемент управления [Ribbon](assetId:///T:System.Windows.Controls.Ribbon.Ribbon?qualifyHint=False&autoUpgrade=True), позволяющий реализовать пользовательский интерфейс в виде ленты, на которой размещаются панель быстрого доступа, меню приложения и вкладки.  
  
-   Новый интерфейс [INotifyDataErrorInfo](assetId:///T:System.ComponentModel.INotifyDataErrorInfo?qualifyHint=False&autoUpgrade=True), который поддерживает синхронную и асинхронную проверку данных.  
  
-   Новые функции в классах [VirtualizingPanel](assetId:///T:System.Windows.Controls.VirtualizingPanel?qualifyHint=False&autoUpgrade=True) и [Dispatcher](assetId:///T:System.Windows.Threading.Dispatcher?qualifyHint=False&autoUpgrade=True).  
  
-   Повышение производительности при отображении больших наборов сгруппированных данных, а также за счет доступа к коллекциям в потоках вне пользовательского интерфейса.  
  
-   Привязка данных к статическим свойствам, привязка данных к пользовательским типам, реализующим интерфейс [ICustomTypeProvider](assetId:///T:System.Reflection.ICustomTypeProvider?qualifyHint=False&autoUpgrade=True), а также извлечение сведений о привязке данных из выражения привязки.  
  
-   Изменение расположения данных по мере изменение значений (формирование данных в реальном времени).  
  
-   Возможность проверить, отсоединен ли контекст данных для контейнера элемента.  
  
-   Возможность задать количество времени, которое должно пройти между операциями изменения свойств и обновления источника данных.  
  
-   Улучшенная поддержка реализации шаблонов слабых событий. Кроме того, события теперь могут принимать расширения разметки.  
  
<a name="windows_communication_foundation"></a>   
### <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)  
 В .NET Framework 4.5 добавлены следующие возможности, чтобы упростить создание и обслуживание приложений Windows Communication Foundation (WCF).  
  
-   Упрощение создаваемых файлов конфигурации.  
  
-   Поддержка разработки в соответствии с парадигмой "сначала контракт".  
  
-   Упрощение настройки режима совместимости ASP.NET.  
  
-   Изменения значений свойств транспорта по умолчанию для уменьшения вероятности необходимости их настройки.  
  
-   Обновления класса [XmlDictionaryReaderQuotas](assetId:///T:System.Xml.XmlDictionaryReaderQuotas?qualifyHint=False&autoUpgrade=True) для уменьшения вероятности того, что потребуется вручную настраивать квоты для читателей словаря XML.  
  
-   Проверка файлов конфигурации WCF силами Visual Studio в рамках процесса сборки, позволяющая выявить ошибки в конфигурации до запуска приложения.  
  
-   Новая поддержка асинхронной потоковой передачи.  
  
-   Новое сопоставление протокола HTTPS, облегчающее предоставление конечной точки по HTTPS с помощью служб IIS.  
  
-   Возможность создавать метаданные в одном документе WSDL путем добавления `?singleWSDL` к URL-адресу службы.  
  
-   Поддержка Websockets, обеспечивающая истинно двунаправленный обмен данными через порты 80 и 443 с показателями производительности, схожими с характеристиками TCP-транспорта.  
  
-   Поддержка настройки служб в коде.  
  
-   Всплывающие подсказки в редакторе XML.  
  
-   Поддержка кэширования в [ChannelFactory](assetId:///T:System.ServiceModel.ChannelFactory?qualifyHint=False&autoUpgrade=True).  
  
-   Поддержка сжатия двоичного кодировщика.  
  
-   Поддержка UDP-транспорта, которая позволяет разработчикам писать службы, использующие обмен сообщениями по принципу "отправить и забыть". Клиент отправляет сообщение службе, но не ожидает от нее ответа.  
  
-   Возможность поддерживать несколько режимов аутентификации в одной конечной точке WCF при использовании HTTP-транспорта и безопасности транспорта.  
  
-   Поддержка служб WCF, использующих интернационализированные доменные имена (IDN).  
  
 Дополнительные сведения см. в разделе [Новые возможности в Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkId=228173).  
  
<a name="windows_workflow_foundation"></a>   
### <a name="windows-workflow-foundation-wf"></a>Windows Workflow Foundation (WF)  
 В .NET Framework 4.5 для Windows Workflow Foundation (WF) добавлено несколько новых возможностей, в том числе следующие.  
  
-   Рабочие процессы конечного автомата, которые впервые появились в составе .NET Framework 4.0.1 ([обновление 1 платформы .NET Framework 4](http://go.microsoft.com/fwlink/?LinkID=215092)). В это обновление вошло несколько новых классов и действий, позволивших разработчикам создавать рабочие процессы конечного автомата. В .NET Framework 4.5 эти классы и действия были обновлены и теперь включают в себя следующие возможности.  
  
    -   Возможность установки точек останова на состояниях.  
  
    -   Возможность копирования и вставки переходов в конструкторе рабочих процессов.  
  
    -   Поддержка создания в конструкторе переходов с общим триггером.  
  
    -   Действия для создания рабочих процессов конечного автомата, в том числе [StateMachine](assetId:///T:System.Activities.Statements.StateMachine?qualifyHint=False&autoUpgrade=True), [State](assetId:///T:System.Activities.Statements.State?qualifyHint=False&autoUpgrade=True) и [Transition](assetId:///T:System.Activities.Statements.Transition?qualifyHint=False&autoUpgrade=True).  
  
-   Расширенные возможности конструктора рабочих процессов, например следующие:  
  
    -   Расширенные возможности поиска рабочих процессов в Visual Studio, включая **быстрый поиск** и **поиск в файлах**.  
  
    -   Возможность автоматически создавать действие Sequence, когда к действию-контейнеру добавляется второе действие — дочерний элемент, и включать оба действия в действие Sequence.  
  
    -   Поддержка панорамирования, которая позволяет изменять видимую часть рабочего процесса без использования полос прокрутки.  
  
    -   Новое представление **Структура документа**, в котором компоненты рабочего процесса отображаются в виде древовидной структуры с возможностью выбора компонента в представлении **Структура документа**.  
  
    -   Возможность добавлять примечаний к действиям.  
  
    -   Возможность определять и использовать делегаты действий с помощью конструктора рабочих процессов.  
  
    -   Автоматическое соединение и автоматическая вставка для действий и переходов в рабочих процессах блок-схемы и конечного автомата.  
  
-   Хранение данных о состоянии представления для рабочего процесса в одном элементе в XAML-файле, чтобы данные о состоянии представления можно было легко находить и редактировать.  
  
-   Действие-контейнер NoPersistScope для предотвращения сохранения дочерних действий.  
  
-   Поддержка выражений C#:  
  
    -   Проекты рабочих процессов, в которых используется Visual Basic, будут использовать выражения Visual Basic, а проекты рабочих процессов C# будут использовать выражения C#.  
  
    -   Проекты рабочих процессов C#, созданные в Visual Studio 2010 и содержащие выражения Visual Basic, совместимы с проектами рабочих процессов C#, в которых используются выражения C#.  
  
-   Усовершенствования управления версиями:  
  
    -   Новый класс [WorkflowIdentity](assetId:///T:System.Activities.WorkflowIdentity?qualifyHint=False&autoUpgrade=True), который обеспечивает сопоставление между хранимым экземпляром рабочего процесса и определением этого рабочего процесса.  
  
    -   Параллельное выполнение нескольких версий рабочего процесса в одном и том же узле, в том числе [WorkflowServiceHost](assetId:///T:System.ServiceModel.Activities.WorkflowServiceHost?qualifyHint=False&autoUpgrade=True).  
  
    -   В динамическом обновлении это возможность изменять определение сохраненного экземпляра рабочего процесса.  
  
-   Разработка служб рабочего процесса в соответствии с парадигмой "сначала контракт", что обеспечивает поддержку автоматического создания действий в соответствии с существующим контрактом службы.  
  
 Дополнительные сведения см. в разделе [Новые возможности Windows Workflow Foundation](http://go.microsoft.com/fwlink/?LinkId=228176).  
  
<a name="tailored"></a>   
### <a name="net-for-windows-8x-store-apps"></a>.NET для приложений Магазина Windows 8.x  
 Приложения для Магазина Windows 8.x разрабатываются для конкретных форм-факторов и в полной мере используют возможности операционной системы Windows. Предоставляется подмножество .NET Framework 4.5 или 4.5.1 для разработки приложений для Магазина Windows 8.x с использованием C# или Visual Basic. Это подмножество называется .NET для Магазина Windows 8.x. Оно подробно рассматривается в [обзорной статье](http://go.microsoft.com/fwlink/?LinkId=228491) в Центре разработки для Windows.  
  
<a name="portable"></a>   
### <a name="portable-class-libraries"></a>Переносимые библиотеки классов  
 Проект "Переносимая библиотека классов" для Visual Studio 2012 (и более поздних версий) позволяет писать и собирать управляемые сборки, работающие на нескольких платформах .NET Framework. Используя проект "Переносимая библиотека классов", вы можете создавать приложения для конкретных платформ (например, для Windows Phone или .NET для приложений Магазина Windows 8.x). Доступные типы и члены в проекте автоматически ограничиваются типами и членами, общими для этих платформ. Дополнительные сведения см. в статье [Переносимая библиотека классов](../Topic/Cross-Platform%20Development%20with%20the%20Portable%20Class%20Library.md).  
  
## <a name="see-also"></a>См. также  
 [.NET Framework и внештатные выпуски](~/docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)   
 [Новые возможности Visual Studio 2013](http://msdn.microsoft.com/library/bb386063\(v=vs.120\).aspx)   
 [ASP.NET 4.5.1 и веб-средства для Visual Studio 2013](http://go.microsoft.com/fwlink/?LinkID=309094)   
 [ASP.NET и Visual Studio для веб-разработки](../Topic/ASP.NET%20and%20Visual%20Studio%20for%20Web.md)   
 [Новые возможности в Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkId=228173)   
 [Новые возможности в Windows Workflow Foundation (WF)](http://go.microsoft.com/fwlink/?LinkId=228176)   
 [Новые возможности Visual C++](http://msdn.microsoft.com/library/hh409293\(v=vs.120\).aspx)

