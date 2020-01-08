---
title: Службы WCF и ASP.NET
ms.date: 03/30/2017
ms.assetid: b980496a-f0b0-4319-8e55-a0f0fa32da70
ms.openlocfilehash: 0a64e277d3465b77a2553d6b9c3901f09a6e1a52
ms.sourcegitcommit: 8c99457955fc31785b36b3330c4ab6ce7984a7ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/29/2019
ms.locfileid: "75544735"
---
# <a name="wcf-services-and-aspnet"></a>Службы WCF и ASP.NET

В этом разделе обсуждаются службы размещения Windows Communication Foundation (WCF) параллельно с ASP.NET и их размещение в режиме совместимости ASP.NET.

## <a name="hosting-wcf-side-by-side-with-aspnet"></a>Размещение WCF параллельно с ASP.NET

Службы WCF, размещенные в службы IIS (IIS), можно найти с помощью. Страницы ASPX и веб-службы ASMX внутри одного общего домена приложения. ASP.NET предоставляет общие службы инфраструктуры, такие как управление AppDomain и динамическая компиляция как для WCF, так и для среды выполнения HTTP ASP.NET. Конфигурация по умолчанию для WCF параллельна с ASP.NET.

![Снимок экрана, показывающий службы WCF и ASP .NET: состояние общего доступа.](./media/wcf-services-and-aspnet/windows-communication-foundation-services-asp-dotnet-configuration.gif)

Среда выполнения HTTP ASP.NET обрабатывает запросы ASP.NET, но не участвует в обработке запросов, предназначенных для служб WCF, несмотря на то, что эти службы размещаются в том же домене AppDomain, что и содержимое ASP.NET. Вместо этого модель службы WCF перехватывает сообщения, адресованные службам WCF, и направляет их через стек транспорта или канала WCF.

Результаты использования параллельной модели представлены ниже.

- Службы ASP.NET и WCF могут совместно использовать состояние AppDomain. Поскольку две платформы могут сосуществовать в одном домене AppDomain, WCF также может совместно использовать состояние AppDomain с ASP.NET (включая статические переменные, события и т. д.).

- Службы WCF работают единообразно, независимо от среды размещения и транспорта. Среда выполнения HTTP ASP.NET преднамеренно связана со средой размещения IIS/ASP.NET и обменом данных по протоколу HTTP. И наоборот, платформа WCF разработана для согласованного поведения в средах размещения (WCF работает как внутри, так и вне служб IIS) и между транспортом (служба, размещенная в IIS 7,0 и более поздних версий, имеет согласованное поведение для всех предоставляемых конечных точек, даже если Некоторые из этих конечных точек используют протоколы, отличные от HTTP.

- В AppDomain функции, реализуемые средой выполнения HTTP, применяются к содержимому ASP.NET, но не к WCF. Многие функции, характерные для HTTP платформы приложений ASP.NET, не применяются к службам WCF, размещенным в домене AppDomain, содержащем содержимое ASP.NET. В примеры этих возможностей входит следующее.

  - HttpContext: <xref:System.Web.HttpContext.Current%2A> всегда `null` при доступе из службы WCF. Взамен рекомендуется использовать <xref:System.ServiceModel.Channels.RequestContext> .

  - Авторизация на основе файлов. модель безопасности WCF не допускает применения списка управления доступом (ACL) к SVC-файлу службы при принятии решения о том, авторизован ли запрос на обслуживание.

  - Авторизация URL-адреса на основе конфигурации. Аналогично, модель безопасности WCF не соответствует правилам авторизации на основе URL-адресов, указанным в элементе конфигурации \<авторизации > System. Web. Эти параметры игнорируются для запросов WCF, если служба находится в пространстве URL-адресов, защищенном ASP. Правила авторизации URL-адресов NET.

  - Расширяемость HttpModule. Инфраструктура хостинга WCF перехватывает запросы WCF при возникновении события <xref:System.Web.HttpApplication.PostAuthenticateRequest> и не возвращает обработку в конвейер HTTP ASP.NET. Модули, закодированные для перехвата запросов на последующих стадиях конвейера, не перехватывают запросы WCF.

  - Олицетворение ASP.NET. по умолчанию запросы WCF всегда выполняются как удостоверение процесса IIS, даже если для ASP.NET задано разрешение олицетворения с помощью параметра конфигурации System. Web \<Identity IMPERSONATE = "true"/>.

Эти ограничения относятся только к службам WCF, размещенным в приложении IIS. Поведение содержимого ASP.NET не влияет на присутствие WCF.

Приложения WCF, которым требуются функциональные возможности, обычно предоставляемые конвейером HTTP, должны использовать эквиваленты WCF, которые являются независимыми узлами и транспортом:

- <xref:System.ServiceModel.OperationContext> вместо <xref:System.Web.HttpContext>.

- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> вместо авторизации на основе файла или URL-адреса ASP.NET.

- <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector> или пользовательские многоуровневые каналы вместо HTTP-модулей.

- Олицетворение для каждой операции с использованием WCF вместо олицетворения System. Web.

Кроме того, можно рассмотреть возможность запуска служб в режиме совместимости ASP.NET WCF.

## <a name="hosting-wcf-services-in-aspnet-compatibility-mode"></a>Размещение служб WCF в режиме совместимости ASP.NET

Несмотря на то что модель WCF разработана для обеспечения единообразного поведения в средах размещения и транспортах, часто бывают ситуации, когда приложению не требуется такая степень гибкости. Режим совместимости ASP.NET WCF подходит для сценариев, которые не нуждаются в возможности размещения вне служб IIS или для взаимодействия по протоколам, отличным от HTTP, но которые используют все функции платформы веб-приложений ASP.NET.

В отличие от параллельной конфигурации по умолчанию, где инфраструктура размещения WCF перехватывает сообщения WCF и направляет их из конвейера HTTP, службы WCF, работающие в режиме совместимости ASP.NET, полностью участвуют в жизненном цикле HTTP-запроса ASP.NET. В режиме совместимости службы WCF используют конвейер HTTP через реализацию <xref:System.Web.IHttpHandler>, аналогично способу обработки запросов к страницам ASPX и веб-службам ASMX. В результате WCF ведет себя так же, как ASMX, по отношению к следующим ASP.NET функциям:

- <xref:System.Web.HttpContext>: службы WCF, работающие в режиме совместимости ASP.NET, имеют доступ к <xref:System.Web.HttpContext.Current%2A> и связанному с ним состоянию.

- Авторизация на основе файлов. службы WCF, работающие в режиме совместимости ASP.NET, могут быть защищены путем присоединения списков управления доступом (ACL) файловой системы к SVC-файлу службы.

- Настраиваемая авторизация URL-адреса: ASP. Правила авторизации URL-адресов сети применяются для запросов WCF, когда служба WCF работает в режиме совместимости ASP.NET.

- Расширяемость <xref:System.Web.HttpModuleCollection>. Поскольку службы WCF, работающие в режиме совместимости ASP.NET, полностью участвуют в жизненном цикле HTTP-запроса ASP.NET, любой HTTP-модуль, настроенный в конвейере HTTP, может работать с запросами WCF как до, так и после вызова службы.

- Олицетворение ASP.NET. службы WCF выполняются с использованием текущего удостоверения олицетворяемого потока ASP.NET, который может отличаться от удостоверения процесса IIS, если для приложения включено олицетворение ASP.NET. Если ASP.NET олицетворение и олицетворение WCF включены для конкретной операции службы, реализация службы в конечном итоге выполняется с использованием удостоверения, полученного от WCF.

Режим совместимости ASP.NET WCF включается на уровне приложения с помощью следующей конфигурации (расположенной в файле Web. config приложения):

```xml
<system.serviceModel>
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true" />
</system.serviceModel>
```

Значение по умолчанию — `false`, если не указано. Значение `false` указывает, что все службы WCF, запущенные в приложении, не будут работать в режиме совместимости ASP.NET.

Так как режим совместимости ASP.NET подразумевает семантику обработки запросов, которая фундаментально отличается от среды WCF по умолчанию, реализации отдельных служб могут контролировать, выполняется ли они внутри приложения, для которого ASP.NET Включен режим совместимости. Службы могут использовать атрибут <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> для указания, поддерживают ли они режим совместимости ASP.NET. По умолчанию атрибут имеет значение <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed>.

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
> Службы IIS 7,0 и WAS позволяют службам WCF взаимодействовать по протоколам, отличным от HTTP. Однако службы WCF, работающие в приложениях с включенным режимом совместимости ASP.NET, не могут предоставлять конечные точки, отличные от HTTP. В такой конфигурации создается исключение активации, когда служба получает первое сообщение.

Дополнительные сведения о включении режима совместимости ASP.NET для служб WCF см. в разделе <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode> и пример [совместимости с ASP.NET](../samples/aspnet-compatibility.md) .

## <a name="see-also"></a>См. также:

- <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute>
- [Функции размещения Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))
