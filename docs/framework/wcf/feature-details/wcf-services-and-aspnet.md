---
title: Службы WCF и ASP.NET
ms.date: 03/30/2017
ms.assetid: b980496a-f0b0-4319-8e55-a0f0fa32da70
ms.openlocfilehash: d42787492b00b8e0a5a732d641947fec61b5ff96
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2019
ms.locfileid: "67663681"
---
# <a name="wcf-services-and-aspnet"></a>Службы WCF и ASP.NET

В этом разделе рассматриваются размещения Windows Communication Foundation (WCF) служб side-by-side с помощью ASP.NET и их размещения в режиме совместимости с ASP.NET.

## <a name="hosting-wcf-side-by-side-with-aspnet"></a>Размещение WCF side-by-side с ASP.NET

Службы WCF, размещенные в Internet Information Services (IIS) можно найти с помощью. Страницы ASPX и веб-служб ASMX внутри одного общего домена приложения. ASP.NET предоставляет общие службы инфраструктуры, такие как управление доменом приложения и динамическая компиляция для среды выполнения ASP.NET HTTP и WCF. Конфигурация по умолчанию для WCF — side-by-side с ASP.NET.

![Снимок экрана, показывающий службы WCF и ASP .NET: совместное использование состояния.](./media/wcf-services-and-aspnet/windows-communication-foundation-services-asp-dotnet-configuration.gif)

Среда выполнения ASP.NET HTTP обрабатывает запросы ASP.NET, но не участвует в обработке запросов, предназначенный для служб WCF, несмотря на то, что эти службы размещены в одном домене приложений, так как ASP.NET содержимого. Вместо этого модели службы WCF перехватывает сообщения, адресованные службам WCF и направляет их через стек каналов или транспортный WCF.

Результаты использования параллельной модели представлены ниже.

- ASP.NET и WCF службы могут совместно использовать состояние домена приложения. Поскольку две платформы могут сосуществовать в одном домене приложений, WCF могут также совместно использовать состояние домена приложения с ASP.NET (включая статические переменные, события и т. д.).

- Службы WCF работают согласованно, независимо от среды размещения и транспорта. Среда выполнения HTTP ASP.NET преднамеренно связана со средой размещения IIS/ASP.NET и обменом данных по протоколу HTTP. И наоборот, WCF предназначена для согласованной работы в разных средах размещения (WCF работает согласованно как внутри и вне IIS) и разных транспортов (служба, размещенная в IIS 7.0 и более поздние версии работает согласованно во всех конечных точек, она предоставляет, даже в том случае, если Некоторые из этих конечных точек используют протоколы, отличные от HTTP).

- В AppDomain функции, реализованные средой выполнения HTTP применяются к содержимому ASP.NET, но не к WCF. Множество НТТР-функций платформы приложений ASP.NET не применяются к службам WCF, размещенным внутри домена приложения с содержимым ASP.NET. В примеры этих возможностей входит следующее.

  - HttpContext: <xref:System.Web.HttpContext.Current%2A> всегда `null` при доступе из службы WCF. Взамен рекомендуется использовать <xref:System.ServiceModel.Channels.RequestContext>.

  - Авторизация на основе файлов: Модель безопасности WCF не поддерживает список управления доступом (ACL), который применяется к файлу .svc службы, решая, авторизован ли запрос на обслуживание.

  - Авторизация URL-адрес на основе конфигурации: Аналогично, модель безопасности WCF не придерживается никаких правил авторизации на основе URL-адресов, указанных в System.Web \<авторизации > элемента конфигурации. Эти параметры игнорируются для запросов WCF, если служба находится в пространстве URL-адрес, защищенных с помощью ASP. Правила авторизации URL-адрес NET.

  - Расширяемость HttpModule: Инфраструктура размещения WCF перехватывает WCF запрашивает при <xref:System.Web.HttpApplication.PostAuthenticateRequest> событие возникает и не возвращает обработку в конвейер ASP.NET HTTP. Модули, закодированные на перехват запросов на более поздних стадиях конвейера, не перехватывают запросы WCF.

  - Олицетворение ASP.NET. По умолчанию WCF запрашивает всегда выполняется как идентификация процесса IIS, даже если ASP.NET настроена на включение олицетворения с помощью System.Web \<identity impersonate = «true» / > параметр конфигурации.

Эти ограничения применяются только к службам WCF, размещенным в приложении IIS. Поведение содержимого ASP.NET не зависит от наличия WCF.

Приложения WCF, которым требуется функциональность, традиционно предоставляемую конвейером HTTP следует рассмотреть возможность использования эквивалентов WCF, которые от среды размещения и транспорта независимых:

- <xref:System.ServiceModel.OperationContext> вместо <xref:System.Web.HttpContext>.

- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> вместо авторизации на основе файла или URL-адреса ASP.NET.

- <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector> или пользовательские многоуровневые каналы вместо HTTP-модулей.

- Олицетворение для каждой операции при помощи WCF вместо олицетворения System.Web.

Кроме того можно рассмотреть выполнение служб в режиме совместимости ASP.NET WCF.

## <a name="hosting-wcf-services-in-aspnet-compatibility-mode"></a>Размещение служб WCF в режиме совместимости с ASP.NET

Несмотря на то, что модель WCF позволяет вести себя единообразно во средах размещения и транспортов, часто применяются сценарии, когда приложению требуется такая степень гибкости. Режим совместимости ASP.NET WCF подходит для сценариев, для которых не требуется возможность размещения за пределами IIS или взаимодействие по протоколам, отличным от HTTP, но, использующие все возможности платформы приложений ASP.NET Web.

В отличие от конфигурации по умолчанию side-by-side где размещающая инфраструктура WCF перехватывает сообщения WCF и направляет их из конвейера HTTP, службы WCF, работающие в режиме совместимости ASP.NET полностью участвовать в жизненном цикле запроса ASP.NET HTTP. В режиме совместимости WCF-сервисы используют конвейер HTTP через <xref:System.Web.IHttpHandler> реализации, аналогичную запросы так, для обработки страниц ASPX и веб-служб ASMX. В результате WCF работает аналогично ASMX в отношении следующих возможностей ASP.NET:

- <xref:System.Web.HttpContext>: Службы WCF, работающие в режиме совместимости ASP.NET можно получить доступ к <xref:System.Web.HttpContext.Current%2A> и связанное состояние.

- Авторизация на основе файлов: Службы WCF, работающие в режиме совместимости ASP.NET можно защитить путем присоединения файл системы управления доступом (ACL) к службе SVC-файла.

- Можно настроить URL-адрес авторизации: ASP. Правила авторизации URL-адрес NET являются обязательными для запросов WCF, когда служба WCF выполняется в режиме совместимости ASP.NET.

- <xref:System.Web.HttpModuleCollection> расширяемость: Так как службы WCF, работающие в режиме совместимости ASP.NET полностью участвовать в жизненном цикле запроса ASP.NET HTTP, любой модуль HTTP, настроенный в конвейере HTTP может выполнять операции на запросы WCF, до и после вызова службы.

- Олицетворение ASP.NET. Службы WCF, выполняются с использованием текущего удостоверения ASP.NET олицетворение потока, который может быть отличной от идентификации процесса IIS, если для приложения включено олицетворение ASP.NET. Если олицетворение ASP.NET и олицетворение WCF включены для определенной операции службы, реализация службы в конечном счете выполняется с использованием идентификации, полученной от WCF.

Режим совместимости ASP.NET WCF включается на уровне приложения с помощью следующей конфигурации (находится в файле Web.config приложения):

```xml
<system.serviceModel>
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true" />
</system.serviceModel>
```

По умолчанию задается значение "`true`" Если не указано. Значение "`false`" Указывает, что все службы WCF, выполняемые в приложении не будет выполняться в режиме совместимости с ASP.NET.

Поскольку режим совместимости ASP.NET подразумевает семантику обработки запросов, существенно отличающуюся от WCF по умолчанию, реализации отдельных служб имеется возможность управлять независимо от места выполнения внутри приложения, для которых ASP.NET Включен режим совместимости. Службы могут использовать атрибут <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> для указания, поддерживают ли они режим совместимости ASP.NET. По умолчанию атрибут имеет значение <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed>.

```csharp
[AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
public class CalculatorService : ICalculatorSession
{//Implement calculator service methods.}
```

В следующей таблице показано взаимодействие параметра режима совместимости на уровне приложения с заданным уровнем поддержки отдельной службы.

|Параметр режима совместимости на уровне приложения|[AspNetCompatibilityRequirementsMode]<br /><br /> Параметр|Полученный результат|
|--------------------------------------------------|---------------------------------------------------------|---------------------|
|aspNetCompatibilityEnabled = "`true`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required>|Служба включается успешно.|
|aspNetCompatibilityEnabled = "`true`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed>|Служба включается успешно.|
|aspNetCompatibilityEnabled = "`true`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.NotAllowed>|При получении службой сообщения возникает ошибка активации.|
|aspNetCompatibilityEnabled = "`false`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required>|При получении службой сообщения возникает ошибка активации.|
|aspNetCompatibilityEnabled = "`false`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed>|Служба включается успешно.|
|aspNetCompatibilityEnabled = "`false`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.NotAllowed>|Служба включается успешно.|

> [!NOTE]
> IIS 7.0 и WAS позволяет службам WCF обмениваться данными по протоколам, отличным от HTTP. Тем не менее службы WCF, работающие в приложениях, поддерживающих режим совместимости ASP.NET для предоставления конечных точек не HTTP не разрешены. В такой конфигурации создается исключение активации, когда служба получает первое сообщение.

Дополнительные сведения о включении режима совместимости ASP.NET для служб WCF, см. в разделе <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode> и [совместимости с ASP.NET](../samples/aspnet-compatibility.md) образца.

## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute>
- [Функции размещения Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))
