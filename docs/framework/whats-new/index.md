---
title: "Новые возможности .NET Framework"
ms.custom: 
ms.date: 05/02/2017
ms.prod: .net-framework
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
ms.translationtype: HT
ms.sourcegitcommit: 3155295489e1188640dae5aa5bf9fdceb7480ed6
ms.openlocfilehash: f922abca6898e91748158ee16f89ca7f57a81bf7
ms.contentlocale: ru-ru
ms.lasthandoff: 08/05/2017

---

# <a name="whats-new-in-the-net-framework"></a>Новые возможности .NET Framework
<a name="introduction"></a>В этой статье кратко излагаются ключевые новые возможности и усовершенствования в следующих версиях .NET Framework:  
 
[.NET Framework 4.7](#v47)   
[.NET Framework 4.6.2](#v462)   
[.NET Framework 4.6.1](#v461)   
[.NET 2015 и .NET Framework 4.6](#v46)   
[.NET Framework 4.5.2](#v452)   
[.NET Framework 4.5.1](#v451)   
[.NET Framework 4.5](#core)   

Данная статья не содержит исчерпывающей информации обо всех новых возможностях и может быть изменена. Общие сведения о .NET Framework см. в разделе [Начало работы с .NET Framework](../../../docs/framework/get-started/index.md). Поддерживаемые платформы см. в разделе [Требования к системе](~/docs/framework/get-started/system-requirements.md). Ссылки для загрузки и инструкции по установке см. в разделе [Руководство по установке](../../../docs/framework/install/guide-for-developers.md).

> [!NOTE]
> Команда .NET Framework также выпускает компоненты в виде внештатных выпусков совместно с NuGet для расширения поддержки и введения новых возможностей (таких как неизменяемые коллекции и векторные типы с поддержкой SIMD). Дополнительные сведения см. в разделах [Дополнительные библиотеки классов и интерфейсы API](../additional-apis/index.md) и [.NET Framework и внештатные выпуски](~/docs/framework/get-started/the-net-framework-and-out-of-band-releases.md). См. [полный список пакетов NuGet](https://blogs.msdn.microsoft.com/dotnet/p/nugetpackages/) для .NET Framework или подпишитесь на [наш веб-канал](https://nuget.org/api/v2/curated-feeds/dotnetframework/Packages/).

<a name="v47"></a> 
## <a name="introducing-the-net-framework-47"></a>Знакомство с платформой .NET Framework 4.7

Версия .NET Framework 4.7 является следующим шагом развития версий .NET Framework 4.6, 4.6.1 и 4.6.2. Она включает много исправлений и несколько новых возможностей, сохраняя при этом высокую стабильность работы.

### <a name="downloading-and-installing-the-net-framework-47"></a>Скачивание и установка .NET Framework 4.7
 
.NET Framework 4.7 можно скачать здесь:

- [Веб-установщик .NET Framework 4.7](http://go.microsoft.com/fwlink/?LinkId=825299).

- [Автономный установщик .NET Framework 4.7](http://go.microsoft.com/fwlink/?LinkId=825303).

.NET Framework 4.7 можно установить на платформах Windows 10, Windows 8.1 и Windows 7, а также на соответствующих серверных платформах начиная с Windows Server 2008 R2 с пакетом обновления 1 (SP1). .NET Framework 4.7 можно установить с помощью веб-установщика или автономного установщика. Для большинства пользователей рекомендуется использовать веб-установщик.

Вы можете назначить .NET Framework 4.7 в качестве целевой платформы в Visual Studio 2012 (или более поздних версиях), установив [.NET Framework 4.7 Developer Pack](http://go.microsoft.com/fwlink/?LinkId=825319).

### <a name="whats-new-in-the-net-framework-47"></a>Новые возможности .NET Framework 4.7

.NET Framework 4.7 включает новые функции в следующих областях:

- [Ядро](#Core47)
- [Сеть](#net47)
- [ASP.NET](#ASP-NET47)
- [Windows Communication Foundation (WCF)](#wcf47)
- [Windows Forms](#wf47)
- [Windows Presentation Foundation (WPF)](#WPF47)

Список новых API-интерфейсов, добавленных в .NET Framework 4.7, см. в статье [об изменениях API-интерфейсов в .NET Framework 4.7](https://github.com/Microsoft/dotnet/blob/master/releases/net47/dotnet47-api-changes.md) на сайте GitHub. Список улучшенных функций и исправленных ошибок в .NET Framework 4.7 см. в статье [об изменениях в .NET Framework 4.7](http://github.com/Microsoft/dotnet/blob/master/releases/net47/dotnet47-changes.md) на сайте GitHub.  Дополнительные сведения см. в записи блога .NET, посвященной [объявлению о выпуске .NET Framework 4.7](https://blogs.msdn.microsoft.com/dotnet/2017/04/05/announcing-the-net-framework-4-7/).

<a name="Core47" />
#### <a name="core"></a>Ядро

.NET Framework 4.7 улучшает сериализацию, используя <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>:

**Дополнительные функциональные возможности на основе эллиптической криптографии (ECC)***

В .NET Framework 4.7 были добавлены методы `ImportParameters(ECParameters)` в классы <xref:System.Security.Cryptography.ECDsa> и <xref:System.Security.Cryptography.ECDiffieHellman>, которые позволяют объекту представлять уже установленный ключ. Также добавлен метод `ExportParameters(Boolean)` для экспорта ключа с явными параметрами кривой.

В .NET Framework 4.7 также добавлена поддержка дополнительных кривых (включая пакет кривых Brainpool) и стандартные определения для упрощения создания при помощи новых фабричных методов <xref:System.Security.Cryptography.ECDsa.Create%2A> и <xref:System.Security.Cryptography.ECDiffieHellman.Create%2A>.

На GitHub вы найдете [пример криптографических улучшений в .NET Framework 4.7](https://gist.github.com/richlander/5a182899895a87a296c21ada97f7a54e).

**Улучшенная поддержка управляющих символов для DataContractJsonSerializer**

В .NET Framework 4.7 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> сериализует управляющие символы в соответствии со стандартом ECMAScript 6. Это поведение включено по умолчанию для приложений, предназначенных для .NET Framework 4.7, и предлагается в качестве дополнительной функции для приложений, которые выполняются в среде .NET Framework 4.7, но предназначены для предыдущих версий платформы .NET Framework. Дополнительные сведения см. в статье [Изменения целевой платформы в .NET Framework 4.7](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md).

<a name="net47" />
#### <a name="networking"></a>Сеть

В .NET Framework 4.7 добавлена следующая сетевая возможность.

**Поддержка операционной системы по умолчанию для протоколов TLS***

Стек TLS, который используется в <xref:System.Net.Security.SslStream?displayProperty=fullName> и других компонентах, расположенных в стеке над ним (например, HTTP, FTP и SMTP), позволяет разработчикам использовать протоколы TLS по умолчанию, поддерживаемые операционной системой. Разработчики теперь не обязаны жестко указывать версию TLS.

<a name="ASP-NET47" />
#### <a name="aspnet"></a>ASP.NET

ASP.NET в .NET Framework 4.7 включает следующие новые функции:

**Расширяемость кэша объектов**

Начиная с .NET Framework 4.7 в ASP.NET добавляется новый набор интерфейсов API, которые позволяют разработчикам заменить стандартные механизмы кэширования объектов в памяти и мониторинга за использованием памяти в ASP.NET. Разработчики могут переопределить любой из следующих трех компонентов, если их не устраивает стандартная реализация ASP.NET.

- **Хранилище кэша объектов**. В новом разделе конфигурации поставщиков кэша разработчик может подключить новую реализацию кэша объектов для приложения ASP.NET с помощью нового интерфейса **ICacheStoreProvider**.
 
- **Мониторинг памяти**. Стандартный монитор памяти ASP.NET уведомляет приложения о том, что они приближаются к настроенному для процесса лимиту байтов исключительного пользования, а также о нехватке общей доступной физической памяти на компьютере. Уведомление срабатывает незадолго до достижения ограничения. Для некоторых приложений эти уведомления поступают слишком поздно и не позволяют предпринять никаких разумных действий. Разработчики могут использовать собственные мониторы памяти, чтобы заменить значение по умолчанию с помощью свойства <xref:System.Web.Hosting.ApplicationMonitors.MemoryMonitor%2A?displayProperty=fullName>.

- **Реакции на достижение лимита памяти**. По умолчанию ASP.NET пытается обрезать кэш объектов, периодически вызывая функцию <xref:System.GC.Collect%2A?displayProperty=fullName> при приближении к лимиту байтов исключительного пользования для процесса. Для некоторых приложений частота вызовов <xref:System.GC.Collect%2A?displayProperty=fullName> или размер кэша после обрезки не позволяют обеспечить эффективность работы. Теперь разработчик может изменить или дополнить поведение по умолчанию, назначив собственную реализацию **IObserver** в качестве монитора памяти для приложения.

<a name="wcf47" />
#### <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)

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
- Повышение надежности операций сериализации при вызове метода <xref:System.Runtime.Serialization.FormatterServices.GetSerializableMembers%28System.Type%29?displayProperty=fullName>.
- Повышение надежности при удалении обслуживающего потока путем вызова метода **ChannelSynchronizer.RemoveWaiter**.

<a name="wf47" />
#### <a name="windows-forms"></a>Windows Forms

В .NET Framework 4.7 для Windows Forms улучшена поддержка мониторов высоким разрешением.

**Поддержка высокого разрешения**

Начиная с приложений, ориентированных на .NET Framework 4.7, в .NET Framework поддерживается высокое разрешение и динамическое разрешение для приложений Windows Forms. Поддержка высокого разрешения улучшает расположение и внешний вид форм и элементов управления на мониторах с высокой плотностью точек на дюйм. Функция динамического разрешения изменяет расположение и внешний вид формы и элементов управления, когда пользователь изменяет разрешение монитора или масштаб отображения при запущенном приложении.

Поддержку высокого разрешения нужно активировать дополнительно, определив раздел [\<System.Windows.Forms.ConfigurationSection>](../configure-apps/file-schema/winforms/index.md) в файле конфигурации приложения. Дополнительные сведения об активации поддержки высокого разрешения и динамического разрешения для приложений Windows Forms вы можете найти в статье [Поддержка высокого DPI в Windows Forms](../winforms/high-dpi-support-in-windows-forms.md).

<a name="WPF47"></a> 
#### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

В .NET Framework 4.7 добавлены следующие улучшения для WPF.

**Поддержка стека для управления касанием или пером, основанного на сообщениях Windows WM_POINTER**

Теперь вы можете использовать стек управления касанием или пером на основе сообщений [WM_POINTER](https://msdn.microsoft.com/library/windows/desktop/hh454903.aspx) вместо платформы служб рукописного ввода Windows (WISP). Эту функцию нужно отдельно активировать в .NET Framework. Дополнительные сведения см. в статье [Изменения целевой платформы в .NET Framework 4.7](../migration-guide/retargeting-changes-in-the-net-framework-4-7.md).

**Новая реализация интерфейсов API WPF для печати**

API-интерфейсы WPF для печати в классе <xref:System.Printing.PrintQueue?displayProperty=fullName> вызывают [API пакета печати документа](https://msdn.microsoft.com/library/windows/desktop/hh448418(v=vs.85).aspx) Windows вместо устаревших [API печати XPS](https://msdn.microsoft.com/library/windows/desktop/ff686814(v=vs.85).aspx). Влияние этого изменения на совместимость приложений можно изучить в статье [Изменения целевой платформы в .NET Framework 4.7](../migration-guide/retargeting-changes-in-the-net-framework-4-7.md). 

<a name="v462"></a> 
## <a name="whats-new-in-the-net-framework-462"></a>Новые возможности .NET Framework 4.6.2

В [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] появились новые возможности в следующих областях.

- [ASP.NET](#ASPNET462)

- [Категории символов](#Strings)

- [Шифрование](#Crypto462)

- [SqlClient](#SQLClient)

- [Windows Communication Foundation](#WCF)

- [Windows Presentation Foundation (WPF)](#WPF462)

- [Windows Workflow Foundation (WF)](#WF462)

- [ClickOnce](#ClickOnce)

- [Преобразование приложений Windows Forms и WPF в приложения UWP](#UWPConvert)

- [Усовершенствования отладки](#Debug462)

Список новых интерфейсов API, добавленных в .NET Framework 4.6.2, см. в статье [об изменениях API в .NET Framework 4.6.2](https://github.com/Microsoft/dotnet/blob/master/releases/net462/dotnet462-api-changes.md) на сайте GitHub. Список улучшенных функций и исправленных ошибок в .NET Framework 4.6.2 см. в статье [об изменениях в .NET Framework 4.6.2](http://go.microsoft.com/fwlink/?LinkId=708778) на сайте GitHub.  Дополнительные сведения см. в разделе [Объявление о выпуске .NET Framework 4.6.2](https://blogs.msdn.microsoft.com/dotnet/2016/08/02/announcing-net-framework-4-6-2/) в блоге .NET.

<a name="ASPNET462"></a> 
### <a name="aspnet"></a>ASP.NET
 В [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] в ASP.NET представлены следующие улучшения.

 **Улучшенная поддержка локализованных сообщений об ошибках в элементах управления по проверке заметок к данным**. Эти элементы позволяют вам выполнять проверки путем добавления атрибутов к свойству класса. Элемент <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=fullName> атрибута определяет текст сообщения об ошибке, если проверка не пройдена. Начиная с [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], в ASP.NET упрощена локализация сообщений об ошибках. Локализация сообщений об ошибках происходит в указанных далее случаях.

1.  В атрибуте проверки указан <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=fullName>.

2.  Файл ресурсов хранится в папке App_LocalResources.

3.  Имя локализованного файла ресурсов имеет форму `DataAnnotation.Localization.{`*имя*`}.resx`, где *имя* — это имя языка и региональных параметров в формате *languageCode*`-`*country/regionCode* или *languageCode*.

4.  Имя ключа ресурса является строкой, назначенной атрибуту <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=fullName>, а его значением является локализованное сообщение об ошибке.

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

| Имя                                 | Значение                                     |
| ------------------------------------ | ----------------------------------------- |
| The rating must be between 1 and 10. | La note doit être comprise entre 1 et 10. |

 Затем этот файл можно

 Кроме того, локализация заметок к данным является расширяемой. Разработчики могут подключить собственный поставщик локализатора строк путем реализации интерфейса <xref:System.Web.Globalization.IStringLocalizerProvider> для хранения строки локализации в месте, отличном от файла ресурсов.

 **Поддержка асинхронных операций с поставщиками хранилища состояния сеансов**. Теперь ASP.NET позволяет использовать методы, возвращающие задачи, с поставщиками хранилища состояния сеанса, благодаря чему приложениям ASP.NET доступны предоставляемые асинхронностью возможности масштабируемости. Для поддержки асинхронных операций с поставщиками хранилищ состояния сеансов ASP.NET предлагает новый интерфейс <xref:System.Web.SessionState.ISessionStateModule?displayProperty=fullName>, который наследует от <xref:System.Web.IHttpModule> и позволяет разработчикам реализовывать их собственные модули состояния сеансов и асинхронные поставщики хранилищ сеансов. Интерфейс определяется следующим образом:

```csharp
public interface ISessionStateModule : IHttpModule {
    void ReleaseSessionState(HttpContext context);
    Task ReleaseSessionStateAsync(HttpContext context);
}
```

 Кроме того, класс <xref:System.Web.SessionState.SessionStateUtility> включает два новых метода (<xref:System.Web.SessionState.SessionStateUtility.IsSessionStateReadOnly%2A> и <xref:System.Web.SessionState.SessionStateUtility.IsSessionStateRequired%2A>), которые можно использоваться для поддержки асинхронных операций.

 **Поддержка асинхронных операций для поставщиков кэша вывода**. Начиная с версии [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], методы, которые возвращают задачи, могут использоваться с поставщиками кэша вывода, благодаря чему становятся доступны предоставляемые асинхронностью возможности масштабируемости.  Поставщики, реализующие эти методы, сокращают вероятность блокировок потоков на веб-сервере и улучшают масштабируемость службы ASP.NET.

 Для поддержки поставщиков кэша асинхронного вывода были добавлены следующие API:

- Класс <xref:System.Web.Caching.OutputCacheProviderAsync?displayProperty=fullName>, который наследует от <xref:System.Web.Caching.OutputCacheProvider?displayProperty=fullName> и позволяет разработчикам реализовать поставщик кэша асинхронного вывода.

- Класс <xref:System.Web.Caching.OutputCacheUtility>, который предоставляет вспомогательные методы для настройки кэша вывода.

- 18 новых методов в классе <xref:System.Web.HttpCachePolicy?displayProperty=fullName>. К ним относятся <xref:System.Web.HttpCachePolicy.GetCacheability%2A>, <xref:System.Web.HttpCachePolicy.GetCacheExtensions%2A>, <xref:System.Web.HttpCachePolicy.GetETag%2A>, <xref:System.Web.HttpCachePolicy.GetETagFromFileDependencies%2A>, <xref:System.Web.HttpCachePolicy.GetMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetNoStore%2A>, <xref:System.Web.HttpCachePolicy.GetNoTransforms%2A>, <xref:System.Web.HttpCachePolicy.GetOmitVaryStar%2A>, <xref:System.Web.HttpCachePolicy.GetProxyMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetRevalidation%2A>, <xref:System.Web.HttpCachePolicy.GetUtcLastModified%2A>, <xref:System.Web.HttpCachePolicy.GetVaryByCustom%2A>, <xref:System.Web.HttpCachePolicy.HasSlidingExpiration%2A> и <xref:System.Web.HttpCachePolicy.IsValidUntilExpires%2A>.

- 2 новых метода в классе <xref:System.Web.HttpCacheVaryByContentEncodings?displayProperty=fullName>: <xref:System.Web.HttpCacheVaryByContentEncodings.GetContentEncodings%2A> и <xref:System.Web.HttpCacheVaryByContentEncodings.SetContentEncodings%2A>.

- 2 новых метода в классе <xref:System.Web.HttpCacheVaryByHeaders?displayProperty=fullName>: <xref:System.Web.HttpCacheVaryByHeaders.GetHeaders%2A> и <xref:System.Web.HttpCacheVaryByHeaders.SetHeaders%2A>.

- 2 новых метода в классе <xref:System.Web.HttpCacheVaryByParams?displayProperty=fullName>: <xref:System.Web.HttpCacheVaryByParams.GetParams%2A> и <xref:System.Web.HttpCacheVaryByParams.SetParams%2A>.

- В классе <xref:System.Web.Caching.AggregateCacheDependency?displayProperty=fullName> метод <xref:System.Web.Caching.AggregateCacheDependency.GetFileDependencies%2A>.

- В классе <xref:System.Web.Caching.CacheDependency> метод <xref:System.Web.Caching.CacheDependency.GetFileDependencies%2A>.

<a name="Strings"></a> 
### <a name="character-categories"></a>Категории символов
 Символы в [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] классифицируются на основе [стандарта Юникод версии 8.0.0](http://www.unicode.org/versions/Unicode8.0.0/). В [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] и [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] символы классифицировались на основе категорий символов Юникода 6.3.

 Поддержка Юникода 8.0 ограничена классификацией символов по классу <xref:System.Globalization.CharUnicodeInfo> и связанными типами и методами. К ним относятся класс <xref:System.Globalization.StringInfo>, перегруженный метод <xref:System.Char.GetUnicodeCategory%2A?displayProperty=fullName> и [классы символов](../../../docs/standard/base-types/character-classes-in-regular-expressions.md), распознаваемые обработчиком регулярных выражений .NET Framework.  Это изменение не влияет на сравнение и сортировку символов и строк. Они по-прежнему зависят от базовой операционной системы или в системах Windows 7 от символьных данных, предоставляемых .NET Framework.

 Сведения об изменениях в категориях символов Юникода 6.0–7.0 см. в статье [The Unicode Standard, Version 7.0.0](http://www.unicode.org/versions/Unicode7.0.0/) на веб-сайте консорциума Юникода. Сведения об изменениях в категориях символов Юникода 7.0–8.0 см. в статье [The Unicode Standard, Version 8.0.0](http://www.unicode.org/versions/Unicode8.0.0/) на веб-сайте Консорциума Юникода.

<a name="Crypto462"></a> 
### <a name="cryptography"></a>Шифрование
 **Поддержка сертификатов X509, содержащих алгоритм цифровых подписей (DSA) FIPS 186-3**. В [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] добавлена поддержка сертификатов X509 с алгоритмом DSA, ключи которых превышают ограничение FIPS 186-2 в 1024 разряда.

 В дополнение к поддержке больших размеров ключей FIPS 186-3 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] позволяет использовать вычисление подписей с семейством алгоритмов хэширования SHA-2 (SHA256, SHA384 и SHA512). Поддержка FIPS 186 3 осуществляется с помощью нового класса <xref:System.Security.Cryptography.DSACng?displayProperty=fullName>.

 Для соответствия последним изменениям в классе <xref:System.Security.Cryptography.RSA> на платформе в .NET Framework 4.6 и классе <xref:System.Security.Cryptography.ECDsa> на платформе .NET Framework 4.6.1 абстрактный базовый класс <xref:System.Security.Cryptography.DSA> в [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] имеет дополнительные методы, позволяющие вызывающим сторонам использовать эту возможность без приведения. Можно вызвать метод расширения <xref:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPrivateKey%2A?displayProperty=fullName> для подписывания данных, как показано в следующем примере.

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

 Можно также вызвать метод расширения <xref:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPublicKey%2A?displayProperty=fullName> для проверки подписанных данных, как показано в следующем примере.

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

 **Улучшенная читаемость входных данных для подпрограмм формирования ключа ECDiffieHellman**. В .NET Framework 3.5 была добавлена поддержка трех разных подпрограмм формирования ключа с протоколом Диффи — Хеллмана на эллиптических кривых. Входные данные для процедур и сами процедуры настраивались с помощью свойств объекта <xref:System.Security.Cryptography.ECDiffieHellmanCng>. Однако поскольку не все процедуры правильно считывали каждое входное свойство, часто возникала путаница.

 Для решения этой проблемы в [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] в базовый класс <xref:System.Security.Cryptography.ECDiffieHellman> были добавлены следующие три метода, предназначенные для более четкого представления этих процедур формирования ключа и их входных данных.

|Метод ECDiffieHellman|Описание|
|----------------------------|-----------------|
|<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyFromHash%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Security.Cryptography.HashAlgorithmName%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|Получает материал ключа с помощью формулы<br /><br /> HASH(secretPrepend &#124;&#124; *x* &#124;&#124; secretAppend)<br /><br /> HASH(secretPrepend OrElse *x* OrElse secretAppend)<br /><br /> здесь *x* является вычисляемым результатом алгоритма Диффи-Хелмана на эллиптических кривых.|
|<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyFromHmac%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Security.Cryptography.HashAlgorithmName%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|Получает материал ключа с помощью формулы<br /><br /> HMAC(hmacKey, secretPrepend &#124;&#124; *x* &#124;&#124; secretAppend)<br /><br /> HMAC(hmacKey, secretPrepend OrElse *x* OrElse secretAppend)<br /><br /> здесь *x* является вычисляемым результатом алгоритма Диффи-Хелмана на эллиптических кривых.|
|<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyTls%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|Получает материал ключа с помощью алгоритма наследования псевдослучайной функции (PRF) TLS.|

 **Поддержка симметричного шифрования с постоянным ключом**. В библиотеку шифрования Windows (CNG) была добавлена поддержка хранения постоянных симметричных ключей и использования симметричных ключей, хранящихся в оборудовании. [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] открывает разработчикам доступ к этой функциональности.  Поскольку понятие имен ключей и поставщиков ключей зависит от реализации, для применения этой функции требуется использовать конструктор конкретных типов реализации, а не предпочтительный метод (например, вызов `Aes.Create`).

 Поддержка симметричного шифрования с помощью постоянных ключей доступна для алгоритмов AES (<xref:System.Security.Cryptography.AesCng>) и 3DES (<xref:System.Security.Cryptography.TripleDESCng>). Пример:

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

 **Поддержка SignedXml для хэширования SHA-2**. В [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] добавлена поддержка класса <xref:System.Security.Cryptography.Xml.SignedXml> для методов подписи PKCS#1 RSA-SHA256, RSA-SHA384 и RSA-SHA512 и алгоритмов выборки SHA256, SHA384 и SHA512.

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

<a name="SQLClient"></a> 
### <a name="sqlclient"></a>SqlClient
 Поставщик данных .NET framework для SQL Server (<xref:System.Data.SqlClient?displayProperty=fullName>) предлагает следующие новые возможности в [!INCLUDE[net_v462](../../../includes/net-v462-md.md)].

 **Объединение подключений в пул и работа с временем ожидания в базах данных SQL Azure**. Если включено объединение подключений в пул и при входе возникает простой или другая ошибка, происходит кэширование исключения, и это исключение будет выдаваться для любых последующих попыток подключения в период от 5 секунд до 1 минуты.  Дополнительные сведения см. в разделе [Объединение подключений в пул (ADO.NET)](../../../docs/framework/data/adonet/sql-server-connection-pooling.md).

 Это поведение является нежелательным при подключении к базам данных SQL Azure, поскольку попытки соединения могут завершиться временными ошибками, которые обычно быстро исправляются. В целях максимальной оптимизации процедуры повторных попыток подключения поведение периода блокировки пула подключений удаляется при сбое соединений с базами данных SQL Azure.

 За счет добавленного нового ключевого слова `PoolBlockingPeriod` вы можете выбирать период времени блокировки, лучше всего подходящий для вашего приложения. К этим значениям относятся следующие.

 `Auto` — период блокировки пула для приложения, которое подключается к базе данных SQL Azure, становится неактивным, а для приложения, которое подключается к другому экземпляру SQL Server, наоборот, активируется. Это значение по умолчанию. Если имя конечной точки сервера заканчивается любой из приведенных ниже строк, она считается базой данных SQL Azure.

- .database.windows.net

- .database.chinacloudapi.cn

- .database.usgovcloudapi.net

- .database.cloudapi.de

 `AlwaysBlock` Период блокировки пула подключений всегда включен.

 `NeverBlock` Период блокировки пула подключений всегда отключен.

 **Усовершенствования функции Always Encrypted.** В SQLClient представлены два усовершенствования для функции Always Encrypted.

- Для повышения производительности параметризованных запросов к зашифрованным столбцам базы данных выполняется кэширование метаданных шифрования для параметров запроса. Если свойству <xref:System.Data.SqlClient.SqlConnection.ColumnEncryptionQueryMetadataCacheEnabled%2A?displayProperty=fullName> задано значение `true` (это значение по умолчанию) и один и тот же запрос вызывается несколько раз, клиент получает метаданные параметров с сервера только один раз.

- Теперь записи ключей шифрования столбцов в кэше ключа вытесняются по истечении интервала времени, настроенного с помощью свойства <xref:System.Data.SqlClient.SqlConnection.ColumnEncryptionKeyCacheTtl%2A?displayProperty=fullName>.

<a name="WCF"></a> 
### <a name="windows-communication-foundation"></a>Windows Communication Foundation
 В [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] Windows Communication Foundation содержит ряд улучшений в следующих областях.

 **Поддержка защиты транспорта WCF для сертификатов, хранимых с помощью CNG**. Защита транспорта WCF поддерживает сертификаты, хранимые с использованием библиотеки шифрования Windows (CNG). В [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] эта поддержка ограничивается использованием сертификатов с открытым ключом, длина экспоненты которого не превышает 32 бита. Если приложение предназначено для [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], эта функция включена по умолчанию.

 Для приложений, которые предназначены для [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] и более ранних версий, но работают в [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], эту функцию можно включить путем добавления следующей строки в раздел [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла app.config или web.config.

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

 **Улучшенная поддержка множества правил перехода на летнее время с помощью класса DataContractJsonSerializer**. Клиенты могут использовать специальный параметр конфигурации приложения, чтобы определить, поддерживает ли класс <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> множество правил перевода времени для одного часового пояса. Это функция, включаемая пользователем. Чтобы ее включить, добавьте следующий параметр в файл app.config:

```xml
<runtime>
     <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseTimeZoneInfo=false" />
</runtime>
```

Если эта возможность включена, объект <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> использует тип <xref:System.TimeZoneInfo> вместо типа <xref:System.TimeZone> для десериализации данных даты и времени. <xref:System.TimeZoneInfo> поддерживает несколько правил коррекции, что позволяет работать с историческими данными часового пояса, а <xref:System.TimeZone> — не поддерживает.

Дополнительные сведения о структуре <xref:System.TimeZoneInfo> и коррекциях часового пояса см. в статье [Общие сведения о часовых поясах](../../../docs/standard/datetime/time-zone-overview.md).

**Поддержка сохранения времени в формате UTC при сериализации и десериализации с помощью класса XMLSerializer.** Обычно, когда класс <xref:System.Xml.Serialization.XmlSerializer> используется для сериализации значения <xref:System.DateTime> в формате UTC, он создает строку сериализованного времени, которая сохраняет дату и время, но предполагает, что время является местным.  Например, при создании даты и времени в формате UTC путем вызова следующего кода:

```csharp
DateTime utc = new DateTime(2016, 11, 07, 3, 0, 0, DateTimeKind.Utc);
```

```vb
Dim utc As New Date(2016, 11, 07, 3, 0, 0, DateTimeKind.Utc)
```

Результатом является сериализованная строка времени "03:00:00.0000000-08:00" для системных восьми часов с отставанием от времени в формате UTC.  Сериализованные значения всегда десериализуются как значения местной даты и времени.

 Параметр конфигурации приложения можно использовать, чтобы определить, сохраняет ли <xref:System.Xml.Serialization.XmlSerializer> данные о часовом поясе UTC при сериализации и десериализации значений <xref:System.DateTime>.

```xml 
<runtime>
     <AppContextSwitchOverrides 
          value="Switch.System.Runtime.Serialization.DisableSerializeUTCDateTimeToTimeAndDeserializeUTCTimeToUTCDateTime=false" />
</runtime>
```

Если эта возможность включена, объект <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> использует тип <xref:System.TimeZoneInfo> вместо типа <xref:System.TimeZone> для десериализации данных даты и времени. <xref:System.TimeZoneInfo> поддерживает несколько правил коррекции, что позволяет работать с историческими данными часового пояса, а <xref:System.TimeZone> — не поддерживает.

Дополнительные сведения о структуре <xref:System.TimeZoneInfo> и коррекциях часового пояса см. в статье [Общие сведения о часовых поясах](../../../docs/standard/datetime/time-zone-overview.md).

 **Более точный подбор соответствия с помощью NetNamedPipeBinding**. В WCF представлен новый параметр для клиентских приложений, позволяющий им всегда подключаться к ожидающей передачи данных службе с тем URI, который точнее всего соответствует их запросу. Если этот параметр приложения имеет значение `false` (по умолчанию), клиенты могут использовать <xref:System.ServiceModel.NetNamedPipeBinding> для подключения к службе, прослушивающей URI, который является подстрокой запрошенного URI.

 Например, клиент пытается подключиться к службе, прослушивающей `net.pipe://localhost/Service1`, но другая служба на этом компьютере, запущенная с правами администратора, прослушивает `net.pipe://localhost`. Если этому параметру приложения задать значение `false`, клиент будет пытаться подключиться не к той службе. После установки значения `true` для параметра приложения клиент будет всегда подключаться к наиболее подходящей службе.

> [!NOTE]
>  Клиенты, использующие <xref:System.ServiceModel.NetNamedPipeBinding>, находят службы на основе их базового адреса (если он существует), а не на основе полного адреса конечной точки. Чтобы обеспечить постоянную работу этого параметра, служба должна использовать уникальный базовый адрес.

 Для активации этого изменения добавьте следующий параметр в файл App.config или Web.config клиентского приложения:

```xml
<configuration>
    <appSettings>
        <add key="wcf:useBestMatchNamedPipeUri" value="true" />
    </appSettings>
</configuration>
```

 **SSL 3.0 больше не является протоколом по умолчанию**. При использовании NetTcp с защитой транспорта и сертификатом типа "учетные данные" протокол SSL 3.0 больше не применяется по умолчанию для согласования безопасного соединения. В большинстве случаев существующие приложения не должны затрагиваться, поскольку TLS 1.0 входит в список протоколов для NetTcp. Все существующие клиенты должны иметь возможность согласовывать подключение с помощью хотя бы TLS 1.0.      Если требуется Ssl3, воспользуйтесь одним из указанных ниже механизмов конфигурации и добавьте его в список установленных протоколов.

- Свойство <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols%2A?displayProperty=fullName>.

- Свойство <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=fullName>.

- Раздел [\<transport>](../../../docs/framework/configure-apps/file-schema/wcf/transport-of-nettcpbinding.md) раздела [\<netTcpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)

- Раздел [\<sslStreamSecurity>](../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) раздела [\<customBinding>](../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)

<a name="WPF462"></a> 
### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)
 В [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] Windows Presentation Foundation содержит ряд улучшений в следующих областях.

 **Сортировка групп**. Приложение, использующее объект <xref:System.Windows.Data.CollectionView> для группировки данных, теперь может явно объявлять порядок сортировки групп. Явная сортировка позволяет решить проблему неочевидного упорядочивания, которая возникает, когда приложение динамически добавляет или удаляет группы или когда оно изменяет значения свойств элементов, участвующих в группировании. Она также может повысить производительность процесса создания группы путем перемещения сравнений свойств группирования из сортировки полной коллекции в сортировку групп.

 Для поддержки сортировки групп новые свойства <xref:System.ComponentModel.GroupDescription.SortDescriptions%2A?displayProperty=fullName> и <xref:System.ComponentModel.GroupDescription.CustomSort%2A?displayProperty=fullName> описывают способ сортировки коллекции групп, созданной объектом <xref:System.ComponentModel.GroupDescription>. Эта процедура аналогична способу, которым свойства <xref:System.Windows.Data.ListCollectionView> с аналогичными именами описывают принцип сортировки элементов данных.

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

 **Поддержка экранной клавиатуры**. Теперь приложения WPF могут отслеживать фокус: когда элемент управления, способный принимать текстовый ввод, получает сенсорные входные данные, возможен автоматический вызов и закрытие новой экранной клавиатуры в Windows 10.

 В предыдущих версиях платформы .NET Framework приложения WPF не использовали отслеживание фокуса без отключения поддержки пера и сенсорного ввода WPF.  В результате приложения WPF должны выбрать между полной поддержкой сенсорного ввода WPF или использованием мыши Windows.

 **Поддержка разных DPI для разных мониторов**. В связи со все более частым использованием приложений WPF в средах с высоким DPI или с множеством разных DPI в [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] поддерживается контроль DPI для каждого отдельного монитора. Дополнительные сведения о включении в приложении WPF поддержки DPI для каждого монитора см. в [примерах и в руководстве разработчика](https://github.com/Microsoft/WPF-Samples/tree/master/PerMonitorDPI) на сайте GitHub.

 В предыдущих версиях платформы .NET Framework приложения WPF поддерживают DPI на уровне системы. Другими словами, ОС соответствующим образом масштабирует пользовательский интерфейс приложения в зависимости от разрешения экрана монитора, на котором отображается приложение. ,

 Для приложений, работающих под управлением [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], можно отключить изменения DPI для каждого монитора в приложениях WPF путем добавления инструкции конфигурации в раздел [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения, как показано ниже.

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.Windows.DoNotScaleForDpiChanges=false"/>
</runtime>
```

<a name="WF462"></a> 
### <a name="windows-workflow-foundation-wf"></a>Windows Workflow Foundation (WF)
 В [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] Windows Workflow Foundation содержит ряд улучшений в следующих областях.

 **Поддержка выражений C# и IntelliSense в конструкторе рабочих процессов WF, размещенном внутри приложений**. Начиная с версии [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], WF поддерживает выражения C# в конструкторе Visual Studio и в процессах работы с кодом. Повторно размещаемый конструктор рабочих процессов является ключевой возможностью WF, позволяющей размещать конструкторы рабочих процессов в приложении вне среды Visual Studio (например, в WPF).  Windows Workflow Foundation поддерживает выражения C# и IntelliSense в повторно размещаемом конструкторе рабочих процессов. Дополнительные сведения см. в [блоге по Windows Workflow Foundation](http://go.microsoft.com/fwlink/?LinkID=809042&clcid=0x409).

 `Availability of IntelliSense when a customer rebuilds a workflow project from Visual Studio`. В версиях до [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] при перестройке проекта Workflow из Visual Studio происходит нарушение работы IntelliSense в конструкторе WF. Несмотря на успешное построение проекта, типы рабочих процессов отсутствуют в конструкторе, и в окне **Список ошибок** отображаются предупреждения из IntelliSense о недостающих типах рабочего процесса. В [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] эта проблема решена и IntelliSense работает.

 **Приложения Workflow версии 1 с отслеживанием теперь работают в режиме FIPS**. Теперь на компьютерах с режимом поддержки FIPS можно без ошибок запускать приложения Workflow версии 1 с включенной функцией отслеживания. Чтобы реализовать этот сценарий, необходимо внести следующее изменение в файл app.config:

```xml
<add key="microsoft:WorkflowRuntime:FIPSRequired" value="true" />
```

 Если этот сценарий не реализован, запущенное приложение продолжает создавать исключение с сообщением "Данная реализация не является частью протестированных криптографических алгоритмов Windows Platform FIPS".

 **Исправлена работа Workflow при использовании динамического обновления с конструктором Workflow в Visual Studio**. Теперь конструктор Workflow, конструктор действий FlowChart и другие конструкторы действий Workflow без ошибок загружают и отображают рабочие процессы, сохраненные после вызова метода <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=fullName>. В версиях .NET Framework, предшествующих [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], загрузка XAML-файла в Visual Studio для рабочего процесса, который был сохранен после вызова метода <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=fullName>, может привести к возникновению следующих проблем.

- Конструктор рабочих процессов не может правильно загрузить XAML-файл (если <xref:System.Activities.Presentation.ViewState.ViewStateData.Id%2A?displayProperty=fullName> находится в конце строки).

- Конструктор действия FlowChart или другие конструкторы действий рабочих процессов могут отображать все объекты в их расположениях по умолчанию в отличие от значений вложенных свойств.

<a name="ClickOnce"></a> 
### <a name="clickonce"></a>ClickOnce
 Технология ClickOnce была обновлена для поддержки протоколов TLS 1.1 и TLS 1.2 наряду с уже поддерживаемой версией 1.0. ClickOnce автоматически определяет необходимый протокол. Для включения поддержки протоколов TLS 1.1 и 1.2 в приложении ClickOnce не требуется выполнять дополнительные действия.

<a name="UWPConvert"></a> 
### <a name="converting-windows-forms-and-wpf-apps-to--uwp-apps"></a>Преобразование приложений Windows Forms и приложений WPF в приложения UWP
 Теперь Windows предоставляет возможности переноса существующих классических приложений Windows, включая приложения WPF и Windows Forms, на универсальную платформу Windows (UWP). Эта технология играет роль моста, позволяя постепенно переносить существующую базу кода на платформу UWP, переводя, тем самым, приложения на все устройства Windows 10.

 Преобразованное классическое приложение получает удостоверение, аналогичное удостоверению приложения платформы UWP, которое делает доступными интерфейсы API UWP для включения функций, таких как динамические плитки и уведомления. Приложение продолжает работать как раньше и функционирует как приложение полного доверия. После преобразования приложения к существующему процессу полного доверия можно добавить процесс контейнера приложения для подключения адаптивного пользовательского интерфейса. При перемещении всех функциональных возможностей в процесс контейнера приложения можно удалить процесс полного доверия и сделать новое приложение UWP доступным для всех устройств Windows 10.

<a name="Debug462"></a> 
### <a name="debugging-improvements"></a>Усовершенствования отладки
 *API неуправляемой отладки* был усовершенствован в [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] для выполнения дополнительного анализа при возникновении <xref:System.NullReferenceException>, чтобы определить, какая переменная в одной строке исходного кода является `null`.   Для поддержки этого сценария в неуправляемый API отладки были добавлены следующие API.

- Интерфейсы [ICorDebugCode4](../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md), [ICorDebugVariableHome](../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) и [ICorDebugVariableHomeEnum](../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md), предоставляющие собственные начальные расположения управляемых переменных. Это позволяет отладчикам выполнять анализ потока кода при возникновении <xref:System.NullReferenceException> и работать в обратном порядке для определения управляемой переменной, соответствующей собственному расположению, которым был `null`.

- Метод [ICorDebugType2::GetTypeID](../../../docs/framework/unmanaged-api/debugging/icordebugtype2-gettypeid-method.md) обеспечивает сопоставление ICorDebugType с [COR_TYPEID](../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), что позволяет отладчику получить [COR_TYPEID](../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) без экземпляра ICorDebugType. Существующие API в [COR_TYPEID](../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) можно использовать для определения макета класса типа.

<a name="v461"></a> 
## <a name="whats-new-in-the-net-framework-461"></a>Новые возможности .NET Framework 4.6.1
 В [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] появились новые возможности в следующих областях.

- [Шифрование](#Crypto)

- [ADO.NET](#ADO.NET461)

- [Windows Presentation Foundation (WPF)](#WPF461)

- [Windows Workflow Foundation](#WWF461)

- [Профилирование](#Profile461)

- [NGen](#NGEN461)

 Дополнительные сведения о [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] см. в следующих разделах.

- [Список изменений в .NET Framework 4.6.1](http://go.microsoft.com/fwlink/?LinkId=622964)

- [Совместимость приложений в 4.6.1](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)

- [Различия интерфейсов API .NET Framework](http://go.microsoft.com/fwlink/?LinkId=622989) (на GitHub)

<a name="Crypto"></a> 
### <a name="cryptography-support-for-x509-certificates-containing-ecdsa"></a>Шифрование: поддержка сертификатов X509, содержащих ECDSA
 В .NET Framework 4.6 добавлена поддержка RSACng сертификатов X509. В [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] добавляется поддержка ECDSA (алгоритма цифровых подписей на основе эллиптических кривых) сертификатов X509.

 ECDSA обеспечивает более высокую производительность и является более безопасным алгоритмом шифрования, чем RSA, предоставляя лучший выбор, когда производительность и масштабируемость TLS представляет собой проблему. Реализация .NET Framework создает оболочку для вызовов существующих функциональных возможностей Windows.

 В следующем примере кода показано, как легко можно создать подпись для байтового потока, используя новую поддержку сертификатов X 509 ECDSA, включенную в [!INCLUDE[net_v461](../../../includes/net-v461-md.md)].

 [!code-csharp[whatsnew.461.crypto#1](../../../samples/snippets/csharp/VS_Snippets_CLR/whatsnew.461.crypto/cs/Code46.cs#1)] [!code-vb[whatsnew.461.crypto#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.461.crypto/vb/Code461.vb#1)]

 Это обеспечивает заметное отличие от кода, необходимого для создания подписи в .NET Framework 4.6.

 [!code-csharp[whatsnew.461.crypto#2](../../../samples/snippets/csharp/VS_Snippets_CLR/whatsnew.461.crypto/cs/Code46.cs#2)] [!code-vb[whatsnew.461.crypto#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.461.crypto/vb/Code46.vb#2)]

<a name="ADO.NET461"></a> 
### <a name="adonet"></a>ADO.NET
 В ADO.NET добавлены следующие возможности.

 Поддержка Always Encrypted (постоянного шифрования) для аппаратно защищенных ключей. Теперь ADO.NET поддерживает хранение главных ключей столбца Always Encrypted непосредственно в аппаратных модулях безопасности (HSM). Благодаря этому клиенты могут использовать асимметричные ключи, хранящиеся в аппаратных модулях безопасности, без необходимости написания специальных поставщиков хранилища главных ключей и их регистрации в приложениях.

 Для доступа к постоянно зашифрованным данным, защищенным с помощью главных ключей столбца, хранящихся в аппаратном модуле безопасности, клиенты должны установить на серверах приложений или клиентских компьютерах предоставленный производителем аппаратного модуля безопасности поставщик служб шифрования или поставщики хранилища ключей CNG.

 Улучшенное поведение подключения <xref:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover%2A>, благодаря которому AlwaysOn SqlClient теперь автоматически обеспечивает более быстрое подключение к группе доступности (AG) AlwaysOn. Он прозрачно определяет, подключается ли ваше приложение к группе доступности AlwaysOn в другой подсети, и быстро обнаруживает текущий активный сервер и обеспечивает подключение к этому серверу. В предыдущих версиях строка подключения приложения должна была включать `"MultisubnetFailover=true"` для указания, что это приложение подключается к группе доступности AlwaysOn. При подключении приложения к группе доступности AlwaysOn без установки значения `true` для этого ключевого слова подключения время ожидания может быть превышено. В этом выпуске больше *не* требуется, чтобы приложение устанавливало <xref:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover%2A> в значение `true`. Дополнительные сведения о поддержке SqlClient для групп доступности Always On см. в разделе [Поддержка SqlClient для высокого уровня доступности и аварийного восстановления](../../../docs/framework/data/adonet/sql/sqlclient-support-for-high-availability-disaster-recovery.md).

<a name="WPF461"></a> 
### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)
 Windows Presentation Foundation содержит ряд улучшений и изменений.

 Улучшенная производительность. В [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] была исправлена задержка при срабатывании событий касания. Кроме того, ввод в элементе управления <xref:System.Windows.Controls.RichTextBox> больше не препятствует обрабатывающему потоку при быстром вводе данных.

 Улучшения проверки орфографии. В Windows 8.1 и последующих версиях проверка орфографии в WPF была обновлена, чтобы для проверки орфографии в дополнительных языках использовалась поддержка операционной системы.  В версиях Windows, предшествующих Windows 8.1, изменения этой функциональности отсутствуют.

 Как и в предыдущих версиях .NET Framework, язык для блока <xref:System.Windows.Controls.RichTextBox> элемента управления <xref:System.Windows.Controls.TextBox> определяется путем поиска информации в следующем порядке:

- `xml:lang`, если имеется;

- текущий язык ввода;

- язык и региональные параметры текущего потока.

 Дополнительные сведения о языковой поддержке в WPF см. в [публикации в блоге WPF, посвященной компонентам .NET Framework 4.6.1](http://go.microsoft.com/fwlink/?LinkID=691819).

 Дополнительная поддержка индивидуально настраиваемых словарей. В [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] WPF распознает настраиваемые словари, зарегистрированные глобально. Эта возможность доступна наряду с возможностью их регистрации на уровне элемента управления.

 В предыдущих версиях WPF настраиваемые словари не распознавали исключенные слова и списки автозамены. Эти возможности поддерживаются в Windows 8.1 и Windows 10 благодаря использованию файлов, которые могут быть помещены в каталог `%AppData%\Microsoft\Spelling\<language tag>`.  К этим файлам применяются следующие правила.

- Файлы должны иметь расширения DIC (для добавленных слов), EXC (для исключенных слов) или ACL (для автозамены).

- Файлы должны представлять собой открытый текст в кодировке UTF-16 LE, который начинается с метки порядка байтов (BOM).

- Каждая строка должна состоять из слова (в списках добавленных или исключенных слов) или пары автозамены, в которой слова разделены вертикальной чертой ("&#124;") (в списке автозамены).

- Эти файлы считаются доступными только для чтения и не изменяются системой.

> [!NOTE]
>  Эти новые форматы файлов не поддерживаются непосредственно API-интерфейсами проверки орфографии WPF, и настраиваемые словари, передаваемые в WPF в приложениях, должны продолжать использовать LEX-файлы.

 Примеры. В библиотеке MSDN имеется ряд [примеров WPF](https://msdn.microsoft.com/library/ms771633.aspx). Более 200 наиболее популярных примеров (в зависимости от их использования) будут перенесены в [репозиторий GitHub открытого исходного кода](https://github.com/Microsoft/WPF-Samples). Помогите нам улучшить наши примеры, отправив нам запрос на включение внесенных изменений или открыв [вопрос GitHub](https://github.com/Microsoft/WPF-Samples/issues).

 Расширение DirectX WPF включает [пакет NuGet](http://go.microsoft.com/fwlink/?LinkID=691342), предоставляющий новые реализации <xref:System.Windows.Interop.D3DImage>, которые упрощают взаимодействие с содержимым DX10 и Dx11. Код для этого пакета открыт и доступен [на GitHub](https://github.com/Microsoft/WPFDXInterop).

<a name="WWF461"></a> 
### <a name="windows-workflow-foundation-transactions"></a>Windows Workflow Foundation: транзакции
 Метод <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A?displayProperty=fullName> теперь может использовать для повышения уровня транзакции диспетчер распределенных транзакций, отличный от MSDTC. Это делается путем указания идентификатора GUID диспетчера транзакций в новую перегрузку <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%28System.Transactions.IPromotableSinglePhaseNotification%2CSystem.Guid%29?displayProperty=fullName>. В случае успешного выполнения операции на возможности транзакции накладываются определенные ограничения. После прикрепления отличного от MSDTC диспетчера транзакций следующие методы вызывают исключение <xref:System.Transactions.TransactionPromotionException>, так как эти методы требуют повышения до MSDTC.

- <xref:System.Transactions.Transaction.EnlistDurable%2A?displayProperty=fullName>

- <xref:System.Transactions.TransactionInterop.GetDtcTransaction%2A?displayProperty=fullName>

- <xref:System.Transactions.TransactionInterop.GetExportCookie%2A?displayProperty=fullName>

- <xref:System.Transactions.TransactionInterop.GetTransmitterPropagationToken%2A?displayProperty=fullName>

 После прикрепления отличного от MSDTC диспетчера транзакций он должен использоваться для будущих долговременных прикреплений с использованием протоколов, которые он задает. Идентификатор <xref:System.Guid> диспетчера транзакций можно получить с помощью свойства <xref:System.Transactions.Transaction.PromoterType%2A>. Когда выполняется повышение уровня транзакции, диспетчер транзакций предоставляет массив <xref:System.Byte>, представляющий токен повышенного уровня. Приложение может получить этот токен повышенного уровня для транзакции, уровень которой повышается отличным от MSDTC диспетчером транзакций, с помощью метода <xref:System.Transactions.Transaction.GetPromotedToken%2A>.

 Пользователи новой перегрузки <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%28System.Transactions.IPromotableSinglePhaseNotification%2CSystem.Guid%29?displayProperty=fullName> должны придерживаться определенной последовательности вызовов для успешного завершения операции повышения уровня. Эти правила описаны в документации по данному методу.

<a name="Profile461"></a> 
### <a name="profiling"></a>Профилирование
 Неуправляемый API профилирования был улучшен следующим образом.

 Улучшенная поддержка доступа к PDB-файлам в интерфейсе [ICorProfilerInfo7](../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md). В ASP.Net 5 сборки все чаще компилируются в памяти с помощью Roslyn. Для разработчиков средств профилирования это означает, что PDB-файлы, которые ранее были сериализованы на диске, могут больше не присутствовать. Средства профилирования часто используют PDB-файлы для сопоставления кода с исходными строками для таких задач, как анализ покрытия кода или построковый анализ производительности. Интерфейс [ICorProfilerInfo7](../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md) теперь включает два новых метода, [ICorProfilerInfo7::GetInMemorySymbolsLength](../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md) и [ICorProfilerInfo7::ReadInMemorySymbols](../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md), для предоставления этим средствам профилирования доступа к данным PDB-файлов в памяти. С помощью новых API профилировщик может получить содержимое PDB-файлов в памяти в виде массива байтов, а затем обработать его или сериализовать на диск.

 Улучшено инструментирование с использованием интерфейса ICorProfiler. Профилировщики, использующие функциональность ReJit API `ICorProfiler` для динамического инструментирования, теперь могут изменять некоторые метаданные. Ранее такие средства могли инструментировать IL в любое время, но метаданные могли изменяться только во время загрузки модуля. Поскольку IL ссылается на метаданные, это ограничивает типы инструментирования, которое может выполняться. Мы отменили некоторые из этих ограничений, добавив метод [ICorProfilerInfo7::ApplyMetaData](../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md) для поддержки подмножества правок метаданных после загрузки модуля, в частности путем добавления новых записей `AssemblyRef`, `TypeRef`, `TypeSpec`, `MemberRef`, `MemberSpec` и `UserString`. Это изменение существенно расширяет спектр возможного динамического инструментирования.

<a name="NGEN461"></a> 
### <a name="native-image-generator-ngen-pdbs"></a>PDB-файлы генератора образов в машинном коде (NGEN)
 Трассировка событий между компьютерами позволяет клиентам профилировать программу на компьютере А и просматривать данные профилирования с сопоставлением исходных строк на компьютере Б. Используя предыдущие версии .NET Framework, пользователь может копировать все модули и образы в машинном коде из профилируемого компьютера на компьютер анализа, содержащий PDB-файл IL, для создания сопоставления "источник-машинный код". Хотя этот процесс может хорошо работать в том случае, если файлы относительно невелики, например для телефонных приложений, на настольных системах эти файлы могут быть очень большими, и на их копирование потребуется значительное время.

 С помощью PDB-файлов Ngen NGen может создать PDB-файл, содержащий сопоставления "IL-машинный код" без зависимости от PDB-файла IL. В нашем сценарии трассировки событий между компьютерами все, что требуется, — это скопировать PDB-файл образа в машинном коде, созданный на компьютере А, на компьютер Б, а затем использовать [API доступа к интерфейсу отладки](https://msdn.microsoft.com/library/ee8x173s.aspx) для чтения сопоставления "машинный код-IL" PDB-файла IL и сопоставления "IL-машинный код" PDB-файла образа в машинном коде. Объединение обоих сопоставлений обеспечивает сопоставление "источник-машинный код". Поскольку PDB-файл образа в машинном коде PDB намного меньше, чем все модули и образы в машинном коде, процесс копирования с компьютера А на компьютер Б выполняется гораздо быстрее.

<a name="v46"></a> 
## <a name="whats-new-in-net-2015"></a>Новые возможности .NET 2015
 В .NET 2015 представлены [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] и .NET Core. Некоторые функции применяются к обеим версиям, а другие — только к [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] или только к [!INCLUDE[net_core](../../../includes/net-core-md.md)].

- **ASP.NET 5**

     .NET 2015 включает ASP.NET 5 — экономичную реализацию .NET для создания современных облачных приложений. Платформа ASP.NET 5 является модульной, поэтому вы можете включить только те функции, которые нужны в приложении. Она может быть размещена в IIS или резидентно в пользовательском процессе, и вы можете запустить приложения с разными версиями .NET Framework на одном сервере. В нее входит новая система конфигурации среды, предназначенная для развертывания облака.

     MVC, веб-API и веб-страницы объединены в одну платформу, которая называется MVC 6. Вы создаете приложения ASP.NET 5 с помощью новых средств в Visual Studio 2015. Существующие приложения будут работать на новой платформе .NET Framework; однако, чтобы создать приложение с MVC 6 или SignalR 3, нужно использовать систему проектов в Visual Studio 2015.

     Дополнительные сведения см. в разделе [ASP.NET 5](http://go.microsoft.com/fwlink/?LinkId=518238).

- **Обновления ASP.NET**

    - **API на основе задач для асинхронной очистки ответов**

         ASP.NET теперь предоставляет простой API на основе задач для асинхронной очистки ответов, <xref:System.Web.HttpResponse.FlushAsync%2A?displayProperty=fullName>, который позволяет асинхронно сбрасывать ответы, используя поддержку операторов `async/await` языка программирования.

    - `Model binding supports task-returning methods`

         В [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] в ASP.NET добавлена функция привязки модели, которая обеспечивает расширяемый, ориентированный на код подход к операциям с данными CRUD на страницах веб-форм и пользовательских элементов управления. Система привязки модели теперь поддерживает возвращающие <xref:System.Threading.Tasks.Task> методы привязки модели. Эта функция позволяет разработчикам веб-форм сочетать преимущества масштабируемости асинхронного программирования с простотой системы привязки данных при использовании более новых версий моделей ORM, включая Entity Framework.

         Асинхронная привязка модели управляется параметром конфигурации `aspnet:EnableAsyncModelBinding`.

        ```xml
        <appSettings>
           <add key=" aspnet:EnableAsyncModelBinding" value="true|false" />
        </appSettings>
        ```

         Для приложений, предназначенных для [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], по умолчанию установлено значение `true`. Для приложений, выполняющихся в [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], предназначенных для более ранних версий .NET Framework, значение по умолчанию — `false`. Включить этот режим можно, задав для параметра конфигурации значение `true`.

    - **Поддержка HTTP/2 (Windows 10)**

         [HTTP/2](http://www.wikipedia.org/wiki/HTTP/2) — это новая версия протокола HTTP, которая обеспечивает более эффективное подключение (меньшее число круговых путей между клиентом и сервером) и уменьшение задержки при загрузке веб-страницы для пользователей.  HTTP/2 обеспечивает максимальное преимущество для веб-страниц (по сравнению со службами), так как оптимизирует запрос различных артефактов в ходе одной операции. Поддержка HTTP/2 добавлена в ASP.NET в .NET Framework 4.6. Так как сетевые функции существуют на нескольких уровнях, для новых компонентов в Windows, IIS и ASP.NET потребовалось включить HTTP/2. Для использования HTTP/2 с ASP.NET приложение должно выполняться в Windows 10.

         Протокол HTTP/2 также поддерживается и включен по умолчанию для приложений универсальной платформы Windows (UWP) для Windows 10, использующих API <xref:System.Net.Http.HttpClient?displayProperty=fullName>.

         Чтобы обеспечить способ использования компонента [PUSH_PROMISE](http://http2.github.io/http2-spec/#PUSH_PROMISE) в приложениях ASP.NET, в класс <xref:System.Web.HttpResponse> добавлен новый метод с двумя перегрузками, <xref:System.Web.HttpResponse.PushPromise%28System.String%29> и <xref:System.Web.HttpResponse.PushPromise%28System.String%2CSystem.String%2CSystem.Collections.Specialized.NameValueCollection%29>.

        > [!NOTE]
        >  Хотя ASP.NET 5 поддерживает HTTP/2, поддержка функции PUSH PROMISE еще не была добавлена.

         Всю работу выполняют браузер и веб-сервер (IIS в Windows). Нет необходимости перекладывать нагрузку на пользователей.

         Большинство [основных браузеров поддерживает HTTP/2](http://www.wikipedia.org/wiki/HTTP/2), поэтому вполне вероятно, что пользователи смогут воспользоваться преимуществами протокола HTTP/2, если его поддерживает ваш сервер.

    - **Поддержка протокола привязки токенов**

         Корпорация Майкрософт и Google совместно работают над созданием нового подхода к проверке подлинности, называемого протоколом привязки токенов, или [Token Binding Protocol](https://github.com/TokenBinding/Internet-Drafts). Предполагается, что токены проверки подлинности (в кэше браузера) могут быть украдены и использованы злоумышленниками для получения доступа к защищенным в иных обстоятельствах ресурсам (например, к вашему банковскому счету) без помощи пароля или других конфиденциальных сведений. Новый протокол предназначен для устранения этой проблемы.

         Протокол привязки токенов будет реализован в Windows 10 в качестве компонента браузера. Приложения ASP.NET будут участвовать в протоколе для подтверждения действительности токенов проверки подлинности. Реализации клиента и сервера будут обеспечивать комплексную защиту, заданную этим протоколом.

    - **Алгоритм случайного хэширования строк**

         В .NET Framework 4.5 появился [алгоритм случайного хэширования строк](../configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md). Однако он не поддерживается ASP.NET, так как некоторые компоненты ASP.NET зависят от стабильного хэш-кода. В [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] алгоритмы случайного хэширования строк теперь поддерживаются. Чтобы включить эту функцию, используйте параметр конфигурации `aspnet:UseRandomizedStringHashAlgorithm`.

        ```xml
        <appSettings>
           <add key="aspnet:UseRandomizedStringHashAlgorithm" value="true|false" />
        </appSettings>
        ```

- **ADO.NET**

     ADO .NET теперь поддерживает функцию «Всегда зашифровано», которая доступна в CTP-версии 2 SQL Server 2016. Благодаря функции «Всегда зашифровано» SQL Server может выполнять операции с зашифрованными данными, и, что важнее всего, ключ шифрования хранится в самом приложении в доверенной среде клиента, а не на сервере. Функция «Всегда зашифровано» защищает данные клиента, поэтому администраторы базы данных не имеют доступа к данным в формате обычного текста. Шифрование и расшифровка данных происходит прозрачно на уровне драйвера, что сводит к минимуму изменения, которые должны быть выполнены для существующих приложений. Дополнительные сведения см. в разделах [Always Encrypted (ядро СУБД)](/sql/relational-databases/security/encryption/always-encrypted-database-engine) и [Постоянное шифрование (разработка клиентских приложений)](/sql/relational-databases/security/encryption/always-encrypted-client-development).

- **64-разрядный компилятор JIT для управляемого кода**

     В .NET Framework 4.6 представлена новая версия 64-разрядного JIT-компилятора (первоначальное кодовое имя RyuJIT). Новый 64-разрядный компилятор имеет значительно большую производительность, чем предыдущий 64-разрядный JIT-компилятор. Новый 64-разрядный компилятор включен для 64-разрядных процессов, выполняющихся на основе .NET Framework 4.6. Приложение будет работать в 64-разрядном процессе, если оно скомпилировано как 64-разрядное или AnyCPU и выполняется в 64-разрядной операционной системе. Хотя приняты все необходимые меры, чтобы обеспечить как можно более прозрачный переход на новый компилятор, возможны изменения в поведении. Мы будем благодарны за любые отзывы о проблемах, возникших при использовании нового JIT-компилятора. Свяжитесь с нами через сайт [Microsoft Connect](http://connect.microsoft.com/) в случае возникновения проблемы, которая может быть связана с новым 64-разрядным JIT-компилятором.

     Новый 64-разрядный JIT-компилятор также включает функции аппаратного ускорения SIMD при работе с типами с поддержкой SIMD в пространстве имен <xref:System.Numerics>, что может обеспечить неплохое повышение производительности.

- **Усовершенствования загрузчика сборок**

     Загрузчик сборок теперь более эффективно использует память благодаря выгрузке сборок IL после загрузки соответствующего образа NGEN. Это изменение снижает использование виртуальной памяти, что особенно полезно для больших 32-разрядных приложений (например, Visual Studio); кроме того, оно обеспечивает экономию физической памяти.

- **Изменения библиотеки с базовым классом**

     В [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] были добавлены многие новые API, расширив число важных сценариев. Внесены следующие изменения и дополнения.

    - **Реализации IReadOnlyCollection\<T>**

         Дополнительные коллекции реализуют <xref:System.Collections.Generic.IReadOnlyCollection%601>, например <xref:System.Collections.Generic.Queue%601> и <xref:System.Collections.Generic.Stack%601>.

    - **CultureInfo.CurrentCulture и CultureInfo.CurrentUICulture**

         Свойства <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> и <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> теперь доступны для чтения и записи, а не только для чтения. При назначении нового объекта <xref:System.Globalization.CultureInfo> этим свойствам язык и региональные параметры текущего потока, определенные свойством `Thread.CurrentThread.CurrentCulture`, и язык и региональные параметры текущего потока пользовательского интерфейса, определенные свойствами `Thread.CurrentThread.CurrentUICulture`, также изменяются.

    - **Усовершенствования сборки мусора**

         Класс <xref:System.GC> теперь включает методы <xref:System.GC.TryStartNoGCRegion%2A> и <xref:System.GC.EndNoGCRegion%2A>, которые позволяют запретить сбор мусора во время выполнения критического пути.

         Новая перегрузка метода <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%2CSystem.Boolean%29?displayProperty=fullName> позволяет контролировать, выполняется ли очистка и сжатие кучи мелких объектов и кучи больших объектов или только очистка.

    - **Типы с поддержкой SIMD**

         Пространство имен <xref:System.Numerics> теперь включает различные типы с поддержкой SIMD, например <xref:System.Numerics.Matrix3x2>, <xref:System.Numerics.Matrix4x4>, <xref:System.Numerics.Plane>, <xref:System.Numerics.Quaternion>, <xref:System.Numerics.Vector2>, <xref:System.Numerics.Vector3> и <xref:System.Numerics.Vector4>.

         Поскольку новый 64-разрядный JIT-компилятор также включает функции аппаратного ускорения SIMD, особенно значительное повышение производительности обеспечивается при использовании типов с поддержкой SIMD с новым 64-разрядным JIT-компилятором.

    - **Обновления шифрования**

         API <xref:System.Security.Cryptography?displayProperty=fullName> обновляется для поддержки [API шифрования CNG Windows](https://msdn.microsoft.com/library/windows/desktop/aa376214.aspx). Предыдущие версии .NET Framework полностью зависели от [более ранних версий API шифрования Windows](https://msdn.microsoft.com/library/windows/desktop/aa380255.aspx) для реализации <xref:System.Security.Cryptography?displayProperty=fullName>. Мы получали много запросов на реализацию поддержки API CNG, так как он поддерживает [современные алгоритмы шифрования](https://msdn.microsoft.com/library/windows/desktop/bb204775.aspx#suite_b_support), что очень важно для некоторых категорий приложений.

         Платформа .NET Framework 4.6 включает следующие новые усовершенствования для поддержки API-интерфейсов шифрования CNG Windows.

        - Набор методов расширения для сертификатов X509, `System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)` и `System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)`, которые возвращают реализацию на основе CNG, а не реализацию на основе CAPI (по возможности). (Некоторые смарт-карты и т. д. по-прежнему требуют CAPI, и API-интерфейсы обрабатывают резервный вариант.)

        - Класс <xref:System.Security.Cryptography.RSACng?displayProperty=fullName>, который обеспечивает реализацию CNG алгоритма RSA.

        - Улучшения API RSA, позволяющие отказаться от обязательного приведения общих действий. Например, для шифрования данных с помощью объекта <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> в предыдущих версиях платформы .NET Framework требуется код, аналогичный следующему.

             [!code-csharp[WhatsNew.Casting#1](../../../samples/snippets/csharp/VS_Snippets_CLR/whatsnew.casting/cs/program.cs#1)]    [!code-vb[WhatsNew.Casting#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.casting/vb/module1.vb#1)]

             Код, использующий новые API-интерфейсы шифрования в .NET Framework 4.6, можно переписать следующим образом, чтобы избежать приведения.

             [!code-csharp[WhatsNew.Casting#2](../../../samples/snippets/csharp/VS_Snippets_CLR/whatsnew.casting/cs/program.cs#2)]    [!code-vb[WhatsNew.Casting#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.casting/vb/module1.vb#2)]

    - **Поддержка преобразования даты и времени в формат времени Unix и обратно**

         Следующие новые методы были добавлены в структуру <xref:System.DateTimeOffset> для поддержки преобразования значений даты и времени в формат Unix или из него.

        - <xref:System.DateTimeOffset.FromUnixTimeSeconds%2A?displayProperty=fullName>

        - <xref:System.DateTimeOffset.FromUnixTimeMilliseconds%2A?displayProperty=fullName>

        - <xref:System.DateTimeOffset.ToUnixTimeSeconds%2A?displayProperty=fullName>

        - <xref:System.DateTimeOffset.ToUnixTimeMilliseconds%2A?displayProperty=fullName>

    - **Параметры совместимости**

         Новый класс <xref:System.AppContext> добавляет новый компонент совместимости, который позволяет авторам библиотек предоставлять согласованный механизм явного отказа для новых функциональных возможностей. Он устанавливает слабо связанный контракт между компонентами для передачи запроса на явный отказ. Эта возможность обычно важна при внесении изменений в существующие функции. В свою очередь, режим неявного согласия для новых функциональных возможностей уже существует.

         В <xref:System.AppContext> библиотеки определяют и предоставляют параметры совместимости, а код, который от них зависит, может устанавливать эти параметры для влияния на поведение библиотек. По умолчанию библиотеки предоставляют новые функции и изменяют их (то есть предоставляют прежние функции) только в том случае, если установлен параметр.

         Приложение (или библиотека) может объявить значение параметра (который всегда имеет значение <xref:System.Boolean>), определяемое зависимой библиотекой. Параметр всегда имеет неявное значение `false`. Установка значения `true` для параметра включает его. Явно задание значения `false` для параметра определяет новое поведение.

        ```csharp
        AppContext.SetSwitch("Switch.AmazingLib.ThrowOnException", true);
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
           else {
              // new code
           }
        }
        ```

         Рекомендуется использовать согласованный формат параметров, так как они представляют собой формальный контракт, предоставляемый библиотекой. Ниже приведены два очевидных формата:

        - *параметр*.*пространство_имен*  *имя_параметра*

        - *параметр*.*библиотека*.*имя_параметра*

    - **Изменения асинхронной модели на основе задач**

         Для приложений, предназначенных для [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], объекты <xref:System.Threading.Tasks.Task> и <xref:System.Threading.Tasks.Task%601> наследуют язык и региональные параметры, а также язык и региональные параметры интерфейса пользователя вызывающего потока. Поведение приложений на предыдущих версиях платформы .NET Framework или без определенной версии .NET Framework не затрагивается. Дополнительные сведения см. в подразделе "Язык и региональные параметры в асинхронных операциях на основе задач" раздела, посвященного классу <xref:System.Globalization.CultureInfo>.

         Класс <xref:System.Threading.AsyncLocal%601?displayProperty=fullName> позволяет представлять внешние данные, локальные для данного асинхронного потока управления, такие как метод `async`. Его можно использовать для сохранения данных в разных потоках. Кроме того, можно определить метод обратного вызова, который получает уведомление при каждом изменении внешних данных из-за явного изменения свойства <xref:System.Threading.AsyncLocal%601.Value%2A?displayProperty=fullName> или из-за перехода контекста в потоке.

         Три удобных метода, <xref:System.Threading.Tasks.Task.CompletedTask%2A?displayProperty=fullName>, <xref:System.Threading.Tasks.Task.FromCanceled%2A?displayProperty=fullName> и <xref:System.Threading.Tasks.Task.FromException%2A?displayProperty=fullName>, добавлены в асинхронную модель на основе задач (TAP) для возврата завершенных задач в определенном состоянии.

         Теперь класс <xref:System.IO.Pipes.NamedPipeClientStream> поддерживает асинхронное взаимодействие с новым методом <xref:System.IO.Pipes.NamedPipeClientStream.ConnectAsync%2A>. метод.

    - **EventSource теперь поддерживает запись в журнал событий**

         Теперь класс <xref:System.Diagnostics.Tracing.EventSource> можно использовать для регистрации в журнале событий административных сообщений или рабочих сообщений в дополнение ко всем существующим сеансам трассировки событий Windows, созданным на компьютере. Раньше для обеспечения этих функций приходилось использовать пакет Microsoft.Diagnostics.Tracing.EventSource NuGet. Эти функции теперь встроены в .NET Framework 4.6.

         Обновления пакета NuGet и .NET Framework 4.6 включают следующие функции.

        - **Динамические события**

             Возможность определения событий "на лету" без создания методов событий.

        - **Разнородные полезные данные**

             Возможность передавать массивы и классы со специальными атрибутами, а также типы-примитивы в качестве полезных данных.

        - **Отслеживание действий**

             События Start и Stop помечают возникающие между ними события идентификатором, который представляет все текущие активные действия.

         Для поддержки этих функций перегруженный метод <xref:System.Diagnostics.Tracing.EventSource.Write%2A> был добавлен в класс <xref:System.Diagnostics.Tracing.EventSource>.

- **Windows Presentation Foundation (WPF)**

    - **Усовершенствования HDPI**

         Более эффективная поддержка HDPI в WPF в [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]. В округление макетов внесены изменения для снижения числа вхождений обрезки в элементах управления с границами. По умолчанию эта функция включена, только если для атрибута <xref:System.Runtime.Versioning.TargetFrameworkAttribute> задано значение .NET 4.6.  Для приложений, которые предназначены для более ранних версий платформы, но выполняются в [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], можно выбрать новое поведение, добавив следующую строку в раздел [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла app.config:

        ```xml
        <AppContextSwitchOverrides
        value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false"
        />
        ```

         Окна WPF, разнесенные на несколько мониторов с разными параметрами DPI (настройка нескольких параметров разрешения), теперь отображаются полностью, без черных областей. Можно отключить это новое поведение, добавив следующую строку в раздел `<appSettings>` файла app.config.

        ```xml
        <add key="EnableMultiMonitorDisplayClipping" value="true"/>
        ```

         Поддержка автоматической загрузки правого курсора в зависимости от параметров DPI добавлена в <xref:System.Windows.Input.Cursor?displayProperty=fullName>.

    - **Улучшено касание**

         Проблема с касанием, приводившим к непредсказуемому поведению, о которой сообщает клиент на веб-сайте [Connect](https://connect.microsoft.com/VisualStudio/feedback/details/903760/), была разрешена в [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]. Пороговое значение двойного касания для приложений Магазина Windows и приложений WPF теперь одинаково в Windows 8.1 и более поздних версий.

    - **Поддержка прозрачных дочерних окон**

         WPF в [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] поддерживает прозрачные дочерние окна в Windows 8.1 и более поздних версий. Это позволяет создавать непрямоугольные и прозрачные дочерние окна в окнах верхнего уровня. Чтобы включить эту функцию, необходимо задать для свойства <xref:System.Windows.Interop.HwndSourceParameters.UsesPerPixelTransparency%2A?displayProperty=fullName> значение `true`.

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

             Пользователи могут указать строку, которую WCF будет использовать как префикс достижения для имени группы подключений. Два сообщения с разными префиксами отправляются с помощью разных базовых HTTP-подключений. Префикс задается путем добавления пары "ключ-значение" в свойство <xref:System.ServiceModel.Channels.Message.Properties%2A?displayProperty=fullName> сообщения. Ключ — это "HttpTransportConnectionGroupNamePrefix"; значение — желаемый префикс.

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

    ```
    Operation 'Request3|{http://tempuri.org/}IService' on service instance with identifier '2b0667b6-09c8-4093-9d02-f6c67d534292' cannot be performed at this time. Please ensure that the operations are performed in the correct order and that the binding in use provides ordered delivery guarantees. 
    ```

     Это же сообщение отображается при получении сообщения о внеочередной операции в отсутствии закладок без протокола.

     Если элемент `FilterResumeTimeoutInSeconds` имеет ненулевое значение, существуют закладки без протокола и истекает интервал времени ожидания, то происходит сбой операции с сообщением об истечении времени ожидания.

- **Tранзакции**

     Теперь можно включить идентификатор распределенной транзакции для транзакций, вызвавших создание исключения, производного от <xref:System.Transactions.TransactionException>. Это можно сделать, добавив следующий ключ в раздел `appSettings` файла app.config:

    ```xml
    <add key="Transactions:IncludeDistributedTransactionIdInExceptionMessage" value="true"/> 
    ```

     Значение по умолчанию — `false`.

- **Сеть**

    - **Повторное использование сокета**

         Windows 10 включает новый алгоритм сетевых подключений с высокой масштабируемостью, который повышает эффективность использования ресурсов компьютера путем повторного использования локальных портов для исходящих TCP-подключений. .NET Framework 4.6 поддерживает новый алгоритм, который позволяет приложениям .NET воспользоваться преимуществами нового режима работы. В предыдущих версиях Windows существовало искусственно заданное ограничение числа параллельных подключений (обычно 16 384, размер динамического диапазона портов по умолчанию), которое могло ограничивать масштабируемость службы, вызывая нехватку портов при высокой загрузке.

         В [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] добавлены два новых API, которые обеспечивают повторное использование портов и эффективно снимают ограничение параллельных подключений в 64 000.

        - Значение перечисления <xref:System.Net.Sockets.SocketOptionName?displayProperty=fullName>.

        - Свойство <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=fullName>.

         По умолчанию свойство <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=fullName> имеет значение `false`, если в качестве значения `HWRPortReuseOnSocketBind` раздела реестра `HKLM\SOFTWARE\Microsoft\.NETFramework\v4.0.30319` не задано 0x1. Чтобы включить повторное использование локальных портов для HTTP-подключений, задайте для свойства <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=fullName> значение `true`. В результате все исходящие подключения сокета TCP от <xref:System.Net.Http.HttpClient> и <xref:System.Net.HttpWebRequest> будут использовать новый параметр сокета Windows 10, [SO_REUSE_UNICASTPORT](https://msdn.microsoft.com/library/windows/desktop/ms740532.aspx), который обеспечивает повторное использование локальных портов.

         Разработчики, создающие приложения, работающие только с сокетами, могут указать параметр <xref:System.Net.Sockets.SocketOptionName?displayProperty=fullName> при вызове такого метода, как <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=fullName>, чтобы исходящие сокеты повторно использовали локальные порты во время привязки.

    - **Поддержка международных доменных имен и PunyCode**

         В класс <xref:System.Uri> добавлено новое свойство <xref:System.Uri.IdnHost%2A>, обеспечивающее более эффективную поддержку международных доменных имен и PunyCode.

- **Изменение размеров элементов управления Windows Forms.**

     Эта функция была расширена в [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] и включает типы <xref:System.Windows.Forms.DomainUpDown>, <xref:System.Windows.Forms.NumericUpDown>, <xref:System.Windows.Forms.DataGridViewComboBoxColumn>, <xref:System.Windows.Forms.DataGridViewColumn> и <xref:System.Windows.Forms.ToolStripSplitButton>, а также прямоугольник, указанный свойством <xref:System.Drawing.Design.PaintValueEventArgs.Bounds%2A>, используемым при рисовании <xref:System.Drawing.Design.UITypeEditor>.

     Это функция, включаемая пользователем. Чтобы ее включить, задайте для элемента `EnableWindowsFormsHighDpiAutoResizing` в файле конфигурации приложения (app.config) значение `true`:

    ```xml
    <appSettings>
       <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />
    </appSettings>
    ```

- **Поддержка кодировок кодовых страниц**

     [!INCLUDE[net_core](../../../includes/net-core-md.md)] в первую очередь поддерживает кодировки Юникод и по умолчанию предоставляет ограниченную поддержку для кодировок кодовых страниц. Вы можете добавить поддержку для кодировок кодовых страниц, доступных в .NET Framework, но не поддерживаемых в [!INCLUDE[net_core](../../../includes/net-core-md.md)], путем регистрации кодировок кодовых страниц в методе <xref:System.Text.Encoding.RegisterProvider%2A?displayProperty=fullName>. Для получения дополнительной информации см. <xref:System.Text.CodePagesEncodingProvider?displayProperty=fullName>.

- **.NET Native**

     Приложения Windows для Windows 10, ориентированные на [!INCLUDE[net_core](../../../includes/net-core-md.md)] и написанные на языке C# или Visual Basic, могут воспользоваться преимуществами новой технологии, компилирующей приложения в машинный код, а не в IL-код. Они создают приложения, которым присуща более быстрая загрузка и время выполнения. Дополнительные сведения см. в разделе [Компиляция приложений с помощью .NET Native](../../../docs/framework/net-native/index.md). Общие сведения о .NET Native и рассмотрение отличий такой компиляции от компиляции JIT и NGEN, а также ее влияние на код см. в разделе [.NET Native и компиляция](../../../docs/framework/net-native/net-native-and-compilation.md).

     Приложения компилируются в машинный код по умолчанию, если компиляция выполняется с помощью Visual Studio 2015. Дополнительные сведения см. в разделе [Начало работы с .NET Native](../../../docs/framework/net-native/getting-started-with-net-native.md).

     Для поддержки отладки приложений .NET Native в  интерфейс API отладки неуправляемого кода добавлено несколько новых интерфейсов и перечислений. Дополнительные сведения см. в разделе [Отладка (справочник по неуправляемым API)](../../../docs/framework/unmanaged-api/debugging/index.md).

- **Пакеты .NET Framework с открытым исходным кодом**

     Пакеты [!INCLUDE[net_core](../../../includes/net-core-md.md)], такие как неизменяемые коллекции, [API SIMD](http://go.microsoft.com/fwlink/?LinkID=518639) и API-интерфейсы сетевых подключений, например из пространства имен <xref:System.Net.Http>, теперь доступны в виде пакетов с открытым исходным кодом на сайте [GitHub](https://github.com/). Сведения о доступе к этому коду см. в разделе [NetFx на GitHub](http://go.microsoft.com/fwlink/?LinkID=518634). Дополнительные сведения и инструкции, как принять участие в этих пакетах, см. в разделе [Ядро .NET и открытый исходный код](../../../docs/framework/get-started/net-core-and-open-source.md)[домашней странице .NET на GitHub](http://go.microsoft.com/fwlink/?LinkID=518635).

 [К началу](#introduction)

<a name="v452"></a> 
## <a name="whats-new-in-the-net-framework-452"></a>Новые возможности .NET Framework 4.5.2

- **Новые API для приложений ASP.NET.** Новые методы <xref:System.Web.HttpResponse.AddOnSendingHeaders%2A?displayProperty=fullName> и <xref:System.Web.HttpResponseBase.AddOnSendingHeaders%2A?displayProperty=fullName> позволяют проверять и изменять коды состояния и заголовки ответов при передаче ответа в клиентское приложение. Эти методы можно использовать вместо событий <xref:System.Web.HttpApplication.PreSendRequestHeaders> и <xref:System.Web.HttpApplication.PreSendRequestContent>; они более эффективны и надежны.

     Метод <xref:System.Web.Hosting.HostingEnvironment.QueueBackgroundWorkItem%2A?displayProperty=fullName> позволяет планировать небольшие фоновые рабочие элементы. ASP.NET отслеживает эти элементы и блокирует резкое прерывание службами IIS рабочего процесса до выполнения всех фоновых рабочих элементов. Этот метод нельзя вызвать за пределами управляемого домена приложений ASP.NET.

     Новые свойства <xref:System.Web.HttpResponse.HeadersWritten?displayProperty=fullName> и <xref:System.Web.HttpResponseBase.HeadersWritten?displayProperty=fullName> возвращают логические значения, которые указывают, были ли записаны заголовки ответов. Эти свойства можно использовать, чтобы гарантировать, что вызовы API, например <xref:System.Web.HttpResponse.StatusCode%2A?displayProperty=fullName> (создает исключения, если заголовки записаны), будут выполняться успешно.

- **Изменение размеров элементов управления Windows Forms.** Эта функция была расширена. Теперь системный параметр DPI можно использовать для изменения размера компонентов следующих дополнительных элементов управления (например, стрелки, раскрывающей поле со списком):

     <xref:System.Windows.Forms.ComboBox>    <xref:System.Windows.Forms.ToolStripComboBox>    <xref:System.Windows.Forms.ToolStripMenuItem>    <xref:System.Windows.Forms.Cursor>    <xref:System.Windows.Forms.DataGridView>    <xref:System.Windows.Forms.DataGridViewComboBoxColumn>

     Это функция, включаемая пользователем. Чтобы ее включить, задайте для элемента `EnableWindowsFormsHighDpiAutoResizing` в файле конфигурации приложения (app.config) значение `true`:

    ```xml
    <appSettings>
       <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />
    </appSettings>
    ```

- **Новая функция рабочего процесса.** Диспетчер ресурсов, использующий метод <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A> (и, следовательно, реализующий интерфейс <xref:System.Transactions.IPromotableSinglePhaseNotification>), может использовать новый метод <xref:System.Transactions.Transaction.PromoteAndEnlistDurable%2A?displayProperty=fullName> для запроса следующих операций:

    - повышение транзакции до уровня "координатор распределенных транзакций (Майкрософт)" (MSDTC);

    - замена <xref:System.Transactions.IPromotableSinglePhaseNotification> перечислением<xref:System.Transactions.ISinglePhaseNotification>, которое является устойчивым перечислением, поддерживающим одноэтапные фиксации.

     Эту операцию можно выполнить в том же домене приложения; для повышения уровня не требуется написание дополнительного неуправляемого кода для взаимодействия с MSDTC. Новый метод можно вызвать только при наличии ожидающего выполнения вызова из <xref:System.Transactions?displayProperty=fullName> к методу <xref:System.Transactions.IPromotableSinglePhaseNotification>`Promote`, который реализуется перечислением, поддерживающим повышение уровня.

- **Усовершенствования профилирования.** Следующие новые неуправляемые API профилирования обеспечивают более надежное профилирование:

     [Структура COR_PRF_ASSEMBLY_REFERENCE_INFO](../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md) [Перечисление COR_PRF_HIGH_MONITOR](../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) [Метод GetAssemblyReferences](../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) [Метод GetEventMask2](../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) [Метод SetEventMask2](../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) [Метод AddAssemblyReference](../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)

     Предыдущие реализации `ICorProfiler` поддерживали отложенную загрузку зависимых сборок. Новые API профилирования требуют немедленной доступности для загрузки вставляемых профилировщиком зависимых сборок вместо их загрузки после полной инициализации приложения. Это изменение не влияет на пользователей существующих API `ICorProfiler`.

- **Усовершенствования отладки.** Следующие новые интерфейсы API отладки неуправляемого кода обеспечивают более эффективную интеграцию с профилировщиком. Теперь можно получить доступ к метаданным, вставленным профилировщиком, а также к локальным переменным и коду, созданным запросами компилировщика ReJIT во время отладки дампа.

     [Метод SetWriteableMetadataUpdateMode](../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md) [Метод EnumerateLocalVariablesEx](../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md) [Метод GetLocalVariableEx](../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md) [Метод GetCodeEx](../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md) [Метод GetActiveReJitRequestILCode](../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md) [Метод GetInstrumentedILMap](../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md)

- **Изменения трассировки событий.** Платформа .NET Framework 4.5.2 поддерживает внепроцессную трассировку действий, основанную на трассировке событий Windows (ETW), для более крупных контактных зон. Это позволяет поставщикам решений автоматического управления питанием (АРМ) предлагать облегченные средства, точно отслеживающие стоимость отдельных запросов и действий в разных потоках.  Эти события вызываются только при включении их контроллерами ETW. Таким образом, изменения не влияют на ранее написанный код ETW или код, который выполняется при отключенной трассировке ETW.

- **Повышение уровня транзакции и преобразование ее в устойчивое зачисление**

     <xref:System.Transactions.Transaction.PromoteAndEnlistDurable%2A?displayProperty=fullName> — это новый API, добавленный в .NET Framework 4.5.2 и 4.6.

    ```csharp
    [System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]
    public Enlistment PromoteAndEnlistDurable(Guid resourceManagerIdentifier,
                                              IPromotableSinglePhaseNotification promotableNotification,
                                              ISinglePhaseNotification enlistmentNotification,
                                              EnlistmentOptions enlistmentOptions)
    ```

     Метод может использоваться зачислением, ранее созданным <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A?displayProperty=fullName> в ответ на метод <xref:System.Transactions.ITransactionPromoter.Promote%2A?displayProperty=fullName>. Он запрашивает у `System.Transactions` повышение уровня транзакции до транзакции MSDTC и "преобразование" зачисления, допускающего повышение уровня, в зачисление устойчивых ресурсов. После успешного завершения этого метода `System.Transactions` больше не будет ссылаться на интерфейс <xref:System.Transactions.IPromotableSinglePhaseNotification>, и все будущие уведомления будут поступать в предоставленном интерфейсе <xref:System.Transactions.ISinglePhaseNotification>. Рассматриваемое зачисление должно работать как зачисление устойчивых ресурсов, поддерживая ведение журнала транзакций и восстановления. Подробные сведения см. в разделе <xref:System.Transactions.Transaction.EnlistDurable%2A?displayProperty=fullName>. Кроме того, зачисление должно поддерживать <xref:System.Transactions.ISinglePhaseNotification>.  Этот метод может вызываться *только* во время обработки вызова <xref:System.Transactions.ITransactionPromoter.Promote%2A?displayProperty=fullName>. Если это не так, создается исключение <xref:System.Transactions.TransactionException>.

 [К началу](#introduction)

<a name="v451"></a> 
## <a name="whats-new-in-the-net-framework-451"></a>Новые возможности .NET Framework 4.5.1
 **Обновления апреля 2014 г.**:

- [Обновление 2 для Visual Studio 2013](http://go.microsoft.com/fwlink/p/?LinkId=393658) включает обновления для шаблонов переносимой библиотеки классов для поддержки следующих сценариев:

    - Возможность использовать API среды выполнения Windows в переносимых библиотеках, предназначенных для Windows 8.1, Windows Phone 8.1 и Windows Phone Silverlight 8.1.

    - возможность включить XAML-код (типы Windows.UI.XAML) в переносимые библиотеки, предназначенные для Windows 8.1 или Windows Phone 8.1. Поддерживаются следующие шаблоны XAML: "Пустая страница", "Словарь ресурсов", "Шаблонный элемент управления" и "Пользовательский элемент управления".

    - Можно создать переносной компонент среды выполнения Windows (WINMD-файл) для использования в приложениях магазинов, предназначенных для Windows 8.1 и Windows Phone 8.1.

    - Можно изменить целевую платформу библиотеки классов Магазина Windows или Магазина Windows Phone, такой как переносимая библиотека классов.

     Дополнительные сведения об этих изменениях см. в разделе [Переносимая библиотека классов](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md).

- Набор содержимого .NET Framework теперь включает документацию для [!INCLUDE[net_native](../../../includes/net-native-md.md)], технологии предварительной компиляции для сборки и развертывания приложений Windows. [!INCLUDE[net_native](../../../includes/net-native-md.md)] компилирует приложения напрямую в машинный код, а не в промежуточный язык (IL), что повышает производительность. Подробные сведения см. в разделе [Компиляция приложений с помощью .NET Native](../../../docs/framework/net-native/index.md).

- На странице [.NET Framework Reference Source](http://referencesource.microsoft.com/) предоставляются новые возможности навигации и расширенные функции. Теперь можно искать исходный код .NET Framework в Интернете, [загрузить справочник](http://referencesource.microsoft.com/download.html) для автономной работы и пошагово просматривать источники (включая исправления и обновления) во время отладки. Дополнительные сведения см. в записи блога [Новый облик .NET Reference Source](https://blogs.msdn.microsoft.com/dotnet/2014/02/24/a-new-look-for-net-reference-source/).

 Основные новые функции и улучшения в .NET Framework 4.5.1 включают следующие:

- Автоматическая переадресация привязки для сборок. Начиная с [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)], при компиляции приложения, ориентированного на [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], в файл конфигурации приложения можно добавить переадресации привязок, если приложение или его компоненты ссылаются на несколько версий одной и той же сборки. Включить эту функцию также можно для проектов, предназначенных для более ранних версий платформы .NET Framework. Дополнительные сведения см. в разделе [Практическое руководство. Включение и отключение автоматического перенаправления привязки](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md).

- Возможность сбора диагностической информации, чтобы помочь разработчикам повысить производительность серверных и облачных приложений. Дополнительные сведения см. в описании методов <xref:System.Diagnostics.Tracing.EventSource.WriteEventWithRelatedActivityId%2A> и <xref:System.Diagnostics.Tracing.EventSource.WriteEventWithRelatedActivityIdCore%2A> класса <xref:System.Diagnostics.Tracing.EventSource>.

- Возможность явно уплотнять кучу больших объектов во время сборки мусора. Дополнительные сведения см. в описании свойства <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=fullName>.

- Дополнительные улучшения производительности, например приостановка приложений ASP.NET, усовершенствования многоядерного JIT и более быстрый запуск приложений после обновления платформы .NET Framework. Дополнительные сведения см. в [объявлении о выходе .NET Framework 4.5.1](https://blogs.msdn.microsoft.com/dotnet/2013/06/26/announcing-the-net-framework-4-5-1-preview/) и в публикации в блоге [о приостановке приложения ASP.NET](https://blogs.msdn.microsoft.com/dotnet/2013/10/09/asp-net-app-suspend-responsive-shared-net-web-hosting/).

 Усовершенствования в Windows Forms включают следующие:

- Изменение размеров элементов управления Windows Forms. Системный параметр DPI можно использовать для изменения размера компонентов элементов управления (например, значков, которые отображаются в сетке свойств) путем явного включения с помощью записи в файле конфигурации приложения (app.config) нужного приложения. Эта функция в настоящее время поддерживается для следующих элементов управления Windows Forms:

     <xref:System.Windows.Forms.PropertyGrid>  <xref:System.Windows.Forms.TreeView>  Поддерживаются некоторые аспекты <xref:System.Windows.Forms.DataGridView> (дополнительные поддерживаемые элементы управления см. в статье о [новых возможностях в версии 4.5.2](#v452)).

     Чтобы включить эту функцию, добавьте новый элемент \<appSettings> в файл конфигурации (app.config) и задайте для элемента `EnableWindowsFormsHighDpiAutoResizing` значение `true`:

    ```xml
    <appSettings>
       <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />
    </appSettings>
    ```

 В число улучшений в области отладки приложений .NET Framework в [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] входят следующие:

- Возвращаемые значения в отладчике Visual Studio. При отладке управляемого приложения в [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] в окне "Видимые" отображаются возвращаемые типы и значения для методов. Эти сведения доступны для приложений для настольных систем, приложений для Магазина Windows и приложений Windows Phone. Дополнительные сведения см. в статье [Анализ значений, возвращаемых из вызовов методов](http://msdn.microsoft.com/library/e3245b37-8e2e-4200-ba84-133726e95f1f\(v=vs.120\).aspx) в библиотеке MSDN.

- "Изменить и продолжить" для 64-разрядных приложений. [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] поддерживает команду "Изменить и продолжить" для 64-разрядных управляемых приложений для настольных систем, приложений Магазина Windows и приложений Windows Phone. Существующие ограничения остаются действующими и для 32-разрядных, и для 64-разрядных приложений (см. последний раздел статьи [Поддерживаемые изменения кода (C#)](/visualstudio/debugger/supported-code-changes-csharp)).

- Отладка с поддержкой асинхронности. Чтобы упростить отладку асинхронных приложений в [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)], в стеке вызовов скрывается код инфраструктуры, предоставляемый компиляторами для поддержки асинхронного программирования, а также цепочки логических родительских кадров, что упрощает прослеживание логики выполнения программы. В окне "Задачи", которое заменяет собой окно "Параллельные задачи", отображаются задачи, относящиеся к определенной точке останова, а также все другие задачи, которые в данный момент активны или запланированы в приложении. Вы можете прочесть об этой возможности в разделе "Отладка с поддержкой асинхронности" [объявления о выходе .NET Framework 4.5.1](https://blogs.msdn.microsoft.com/dotnet/2013/06/26/announcing-the-net-framework-4-5-1-preview/).

- Усовершенствованная поддержка исключений для компонентов среды выполнения Windows. В [!INCLUDE[win81](../../../includes/win81-md.md)] исключения, возникающие в приложениях для Магазина Windows, сохраняют сведения об ошибке, которая вызвала исключение, даже при переходе через границу языка. Вы можете прочесть об этой возможности в разделе "Разработка приложений для Магазина Windows" [объявления о выходе .NET Framework 4.5.1](https://blogs.msdn.microsoft.com/dotnet/2013/06/26/announcing-the-net-framework-4-5-1-preview/). 

 Начиная с [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)], вы можете использовать [Управляемое средство профильной оптимизации (Mpgo.exe)](../../../docs/framework/tools/mpgo-exe-managed-profile-guided-optimization-tool.md) для оптимизации приложений [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], а также приложений для настольных систем.

 Список новых возможностей в ASP.NET 4.5.1 см. в разделе [ASP.NET 4.5.1 и Visual Studio 2013](http://go.microsoft.com/fwlink/?LinkID=309094) на сайте ASP.NET.

 [К началу](#introduction)

<a name="core"></a> 
## <a name="whats-new-in-the-net-framework-45"></a>Новые возможности .NET Framework 4.5

### <a name="core-new-features-and-improvements"></a>Основные новые функции и усовершенствования

- Возможность уменьшения количества перезапусков системы путем обнаружения и закрытия приложений .NET Framework 4 во время развертывания. См. раздел [Уменьшение числа перезагрузок при установке платформы .NET Framework 4.5](../../../docs/framework/deployment/reducing-system-restarts.md).

- Поддержка массивов, размер которых превышает 2 ГБ, на 64-разрядных платформах. Эту функцию можно включить в файле конфигурации приложения. См. описание [элемента \<gcAllowVeryLargeObjects>](../../../docs/framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md), в котором также перечислены другие ограничения на размер объекта и размер массива.

- Улучшенная производительность благодаря фоновой сборке мусора для серверов. При использовании серверной сборки мусора в [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] фоновая сборка мусора включается автоматически. Сведения см. в разделе "Фоновая сборка мусора сервера" статьи [Основы сборки мусора](../../../docs/standard/garbage-collection/fundamentals.md).

- Фоновая компиляция по требованию (JIT), которая доступна по выбору на многоядерных процессорах для повышения производительности приложения. См. раздел <xref:System.Runtime.ProfileOptimization>.

- Возможность ограничения времени, в течение которого обработчик регулярных выражений будет пытаться разрешить регулярное выражение до истечения срока действия выражения. См. свойство <xref:System.Text.RegularExpressions.Regex.MatchTimeout%2A?displayProperty=fullName>.

- Возможность определить язык и региональные параметры по умолчанию для домена приложения. См. класс <xref:System.Globalization.CultureInfo>.

- Консольная поддержка кодировки Юникод (UTF-16). См. класс <xref:System.Console>.

- Поддержка управления версиями данных сортировки и сравнения строк, зависящих от языка и региональных параметров. См. класс <xref:System.Globalization.SortVersion>.

- Улучшенная производительность при извлечении ресурсов. См. раздел [Упаковка и развертывание ресурсов](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md).

- Усовершенствования в области сжатия ZIP, позволяющие уменьшить размер сжатого файла. См. пространство имен <xref:System.IO.Compression?displayProperty=fullName>.

- Возможность настраивать контекст отражения для переопределения поведения отражения по умолчанию с помощью класса <xref:System.Reflection.Context.CustomReflectionContext>.

- Поддержка версии 2008 стандарта интернационализированных доменных имен в приложениях (Internationalized Domain Names in Applications, IDNA) при использовании класса <xref:System.Globalization.IdnMapping?displayProperty=fullName> в [!INCLUDE[win8](../../../includes/win8-md.md)].

- Делегирование сравнения строк операционной системе, которая реализует Юникод 6.0, при использовании .NET Framework в [!INCLUDE[win8](../../../includes/win8-md.md)]. При работе на других платформах .NET Framework включает собственные данные сравнения строк, которые реализуют Юникод 5.x. См. класс <xref:System.String> и раздел "Примечания" в описании класса <xref:System.Globalization.SortVersion>.

- Возможность вычисления хэш-кодов для строк для каждого домена приложения. См. раздел [Элемент \<UseRandomizedStringHashAlgorithm>](../../../docs/framework/configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md).

- Поддержка отражения типов, разделенная между классами <xref:System.Type> и <xref:System.Reflection.TypeInfo>. См. раздел [Отражение в .NET Framework для приложений Магазина Windows](../../../docs/framework/reflection-and-codedom/reflection-for-windows-store-apps.md).

### <a name="managed-extensibility-framework-mef"></a>Managed Extensibility Framework (MEF)
 В [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] в Managed Extensibility Framework (MEF) предусмотрены следующие новые возможности:

- Поддержка универсальных типов.

- Модель программирования на основе соглашений, позволяющая создавать части на основе соглашений об именах, а не на основе атрибутов.

- Множественные области действия.

- Подмножество MEF, которое можно использовать при создании приложений [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]. Это подмножество доступно как [загружаемый пакет](http://go.microsoft.com/fwlink/?LinkId=256238) из коллекции NuGet. Чтобы установить пакет, откройте проект в Visual Studio, выберите **Управление пакетами NuGet** в меню **Проект** и выполните поиск пакета `Microsoft.Composition` в Интернете.

 Дополнительные сведения см. в разделе [Managed Extensibility Framework](../../../docs/framework/mef/index.md).

### <a name="asynchronous-file-operations"></a>Асинхронные операции с файлами
 В [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] в языки C# и Visual Basic были добавлены новые асинхронные возможности. Эти возможности представляют собой модель на основе задач для выполнения асинхронных операций. Для использования этой новой модели используйте асинхронные методы в классах ввода-вывода. См. раздел [Асинхронные операции файлового ввода-вывода](../../../docs/standard/io/asynchronous-file-i-o.md).

<a name="tools"></a> 
### <a name="tools"></a>Инструменты
 В [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] генератор файлов ресурсов (Resgen.exe) позволяет создать RESW-файл для использования в приложениях [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] из RESOURCES-файла, внедренного в сборку .NET Framework. Дополнительные сведения см. в разделе [Resgen.exe (генератор файлов ресурсов)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md).

 Средство управляемой оптимизации с использованием профиля (Mpgo.exe) позволяет сократить время запуска приложения, улучшить использование памяти (размер рабочего множества) и пропускную способность путем оптимизации сборок машинных образов. Этот инструмент командной строки формирует данные профилирования для сборок машинного образа приложения. См. раздел [Mpgo.exe (инструмент управляемой оптимизации с использованием профиля)](../../../docs/framework/tools/mpgo-exe-managed-profile-guided-optimization-tool.md). Начиная с [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)], можно использовать средство Mpgo.exe для оптимизации приложений [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], а также приложений для настольных систем.

<a name="parallel"></a> 
### <a name="parallel-computing"></a>Параллельные вычисления
 В [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] предусмотрено несколько новых возможностей и усовершенствований для параллельных вычислений. К ним относятся повышение производительности, повышение управляемости, улучшенная поддержка асинхронного программирования, новая библиотека потоков данных и улучшенная поддержка параллельной отладки и анализа производительности. См. запись [Новые возможности параллелизма в .NET 4.5](http://go.microsoft.com/fwlink/?LinkId=235061) в блоге, посвященном параллельному программированию в .NET.

<a name="web"></a> 
### <a name="web"></a>Интернет
 В ASP.NET 4.5 и 4.5.1 добавилась привязка модели для Web Forms, поддержка WebSocket, асинхронные обработчики, усовершенствования для повышения производительности и многие другие возможности. Дополнительные сведения см. в следующих ресурсах:

- [ASP.NET 4.5 и Visual Studio 2012](http://msdn.microsoft.com/library/ac9bb7f6-f094-4af7-bad0-acf49a5dbc55) в библиотеке MSDN.

- [ASP.NET 4.5.1 и Visual Studio 2013](http://go.microsoft.com/fwlink/?LinkID=309094) на сайте ASP.NET.

<a name="networking"></a> 
### <a name="networking"></a>Сеть
 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] предоставляет новый интерфейс программирования для приложений HTTP. Дополнительные сведения см. в описании новых пространств имен <xref:System.Net.Http?displayProperty=fullName> и <xref:System.Net.Http.Headers?displayProperty=fullName>.

 Также предусмотрена поддержка нового интерфейса программирования для приема и взаимодействия с соединением WebSocket с помощью существующего класса <xref:System.Net.HttpListener> и связанных с ним классов. Дополнительные сведения см. в описании нового пространства имен <xref:System.Net.WebSockets> и класса <xref:System.Net.HttpListener>.

 Кроме того, в [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] предусмотрены следующие усовершенствования в плане сетевого взаимодействия:

- RFC-совместимая поддержка URI. Дополнительные сведения см. в описании <xref:System.Uri> и соответствующих классов.

- Поддержка синтаксического анализа интернационализированных доменных имен (Internationalized Domain Name, IDN). Дополнительные сведения см. в описании <xref:System.Uri> и соответствующих классов.

- Поддержка интернационализации адресов электронной почты (Email Address Internationalization, EAI). Дополнительные сведения см. в описании пространства имен <xref:System.Net.Mail>.

- Улучшенная поддержка протокола IPv6. Дополнительные сведения см. в описании пространства имен <xref:System.Net.NetworkInformation>.

- Поддержка сокета с двойным режимом. Дополнительные сведения см. в описаниях классов <xref:System.Net.Sockets.Socket> и <xref:System.Net.Sockets.TcpListener>.

<a name="client"></a> 
### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)
 В [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] Windows Presentation Foundation (WPF) содержит изменения и усовершенствования в следующих областях:

- Новый элемент управления <xref:System.Windows.Controls.Ribbon.Ribbon>, позволяющий реализовать пользовательский интерфейс в виде ленты, на которой размещаются панель быстрого доступа, меню приложения и вкладки.

- Новый интерфейс <xref:System.ComponentModel.INotifyDataErrorInfo>, который поддерживает синхронную и асинхронную проверку данных.

- Новые возможности для классов <xref:System.Windows.Controls.VirtualizingPanel> и <xref:System.Windows.Threading.Dispatcher>.

- Повышение производительности при отображении больших наборов сгруппированных данных, а также за счет доступа к коллекциям в потоках вне пользовательского интерфейса.

- Привязка данных к статическим свойствам, привязка данных к пользовательским типам, реализующим интерфейс <xref:System.Reflection.ICustomTypeProvider>, а также извлечение сведений о привязке данных из выражения привязки.

- Изменение расположения данных по мере изменение значений (формирование данных в реальном времени).

- Возможность проверить, отсоединен ли контекст данных для контейнера элемента.

- Возможность задать количество времени, которое должно пройти между операциями изменения свойств и обновления источника данных.

- Улучшенная поддержка реализации шаблонов слабых событий. Кроме того, события теперь могут принимать расширения разметки.

<a name="windows_communication_foundation"></a> 
### <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)
 В [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] были добавлены следующие возможности, чтобы упростить создание и обслуживание приложений Windows Communication Foundation (WCF):

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

 Дополнительные сведения см. в разделе [Новые возможности в Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkId=228173).

<a name="windows_workflow_foundation"></a> 
### <a name="windows-workflow-foundation-wf"></a>Windows Workflow Foundation (WF)
 В Windows Workflow Foundation (WF) в [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] было добавлено несколько новых возможностей, в том числе следующие:

- Рабочие процессы конечного автомата, которые впервые появились в составе .NET Framework 4.0.1 ([обновление 1 платформы .NET Framework 4](http://go.microsoft.com/fwlink/?LinkID=215092)). В это обновление вошло несколько новых классов и действий, позволивших разработчикам создавать рабочие процессы конечного автомата. В [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] эти классы и действия были обновлены и теперь включают в себя следующие возможности:

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

 Дополнительные сведения см. в разделе [Новые возможности Windows Workflow Foundation](http://go.microsoft.com/fwlink/?LinkId=228176).

<a name="tailored"></a> 
### [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]
 Приложения [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] разрабатываются для конкретных форм-факторов и в полной мере используют возможности операционной системы Windows. Подмножество [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] или 4.5.1 доступно для разработки приложений [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] для Windows с использованием C# или Visual Basic. Это подмножество называется [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] и рассматривается в [обзорной статье](http://go.microsoft.com/fwlink/?LinkId=228491) в Центре разработки для Windows.

<a name="portable"></a> 
### <a name="portable-class-libraries"></a>Переносимые библиотеки классов
 Проект "Переносимая библиотека классов" в [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)] (и более поздних версиях) позволяет писать и собирать управляемые сборки, работающие на нескольких платформах .NET Framework. Используя проект "Переносимая библиотека классов", можно выбирать платформы для ориентирования (например, Windows Phone и [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]). Доступные типы и члены в проекте автоматически ограничиваются типами и членами, общими для этих платформ. Дополнительные сведения см. в статье [Переносимая библиотека классов](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md).

## <a name="see-also"></a>См. также
 [.NET Framework и внештатные выпуски](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)   
 [Новые возможности Visual Studio 2017](/visualstudio/ide/whats-new-in-visual-studio)   
 [ASP.NET](/aspnet)   
 [Новые возможности Visual C++](/cpp/what-s-new-for-visual-cpp-in-visual-studio) 

