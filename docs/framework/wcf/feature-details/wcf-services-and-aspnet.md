---
title: Службы WCF и ASP.NET
ms.date: 03/30/2017
ms.assetid: b980496a-f0b0-4319-8e55-a0f0fa32da70
ms.openlocfilehash: 6cfd4f8a5dc2a7835cba409a37b09166e49e8df3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33506167"
---
# <a name="wcf-services-and-aspnet"></a>Службы WCF и ASP.NET
В этом разделе рассматриваются размещения Windows Communication Foundation (WCF) служб side-by-side с ASP.NET и их размещение в режиме совместимости с ASP.NET.  
  
## <a name="hosting-wcf-side-by-side-with-aspnet"></a>Параллельное размещение WCF и ASP.NET  
 Службы WCF, размещенные в Internet Information Services (IIS), можно найти с помощью. Страницы ASPX и веб-службами ASMX внутри одного общего домена приложения. ASP.NET предоставляет общие службы инфраструктуры, таких как управление доменом приложения и динамическая компиляция WCF и среда выполнения ASP.NET HTTP. Конфигурация по умолчанию для WCF side-by-side с ASP.NET.  
  
 ![Службы WCF и ASP .NET: общее состояние](../../../../docs/framework/wcf/feature-details/media/hostingwcfwithaspnet.gif "HostingWCFwithASPNET")  
  
 Среда выполнения ASP.NET HTTP обрабатывает запросы ASP.NET, но не участвует в обработке запросов, предназначенных для служб WCF, несмотря на то, что эти службы размещены в том же домене приложения, что ASP.NET содержимого. Вместо этого модель службы WCF перехватывает сообщения, адресованные службам WCF и направляет их через стек каналов или транспортный WCF.  
  
 Результаты использования параллельной модели представлены ниже.  
  
-   Службы ASP.NET и WCF могут совместно использовать состояние домена приложения. Так как обе эти платформы могут сосуществовать в том же домене приложения, WCF может также совместно использовать состояние домена приложения с ASP.NET (включая статические переменные, события и т. д.).  
  
-   Службы WCF работают согласованно, независимо от среды размещения и транспорта. Среда выполнения HTTP ASP.NET преднамеренно связана со средой размещения IIS/ASP.NET и обменом данных по протоколу HTTP. И наоборот, WCF предназначен для согласованной работы в разных средах размещения (WCF работает согласованно как внутри и вне IIS) и с использованием разных транспортов (служба, размещенная в IIS 7.0 и более поздних версий, работает согласованно во всех предоставляемых конечных точках, даже если Некоторые из этих конечных точек используют протоколы, отличные от HTTP).  
  
-   В пределах домена приложения возможности, реализуемые средой выполнения HTTP применяются к содержимому ASP.NET, но не к WCF. Многие функции платформы приложений ASP.NET, характерные для HTTP не применяются к службам WCF, размещенным в пределах домена приложения с содержимым ASP.NET. В примеры этих возможностей входит следующее.  
  
    -   HttpContext: <xref:System.Web.HttpContext.Current%2A> всегда `null` при доступе из службы WCF. Используйте <!--zz <xref:System.ServiceModel.OperationContext.Current.RequestContext>--> `RequestContext` вместо него.  
  
    -   Авторизация на основе файла: модели безопасности WCF не допускает список управления доступом (ACL), который применяется к файлу .svc службы при определении, авторизован ли запрос на обслуживание.  
  
    -   Авторизация URL-адреса на основе конфигурации: Аналогичным образом, модель безопасности WCF не соответствует правилам авторизации на основе URL-адрес, указанный в System.Web \<авторизации > элемента конфигурации. Эти параметры игнорируются для запросов WCF, если служба находится в пространстве URL-АДРЕСУ, защищены ASP. Правила авторизации URL-адреса в сети.  
  
    -   Расширяемость HttpModule: инфраструктура размещения WCF перехватывает WCF запрашивает при <xref:System.Web.HttpApplication.PostAuthenticateRequest> событие возникает и не возвращает обработку в конвейер ASP.NET HTTP. Модули, закодированные на перехват запросов на более поздних стадиях конвейера, не перехватывают запросы WCF.  
  
    -   Олицетворение ASP.NET: по умолчанию WCF запрашивает всегда выполняется как идентификация процесса IIS, даже если ASP.NET устанавливается для включения олицетворения с помощью System.Web \<identity impersonate = «true» / > параметра конфигурации.  
  
 Эти ограничения применяются только для служб WCF, размещенным в приложении IIS. Поведение содержимого ASP.NET не зависит от наличия WCF.  
  
 Приложения WCF, требующих функциональность, традиционно предоставляемую конвейером HTTP следует рассмотреть возможность использования эквивалентов WCF, размещения и транспорта независимых:  
  
-   <xref:System.ServiceModel.OperationContext> вместо <xref:System.Web.HttpContext>.  
  
-   <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> вместо авторизации на основе файла или URL-адреса ASP.NET.  
  
-   <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector> или пользовательские многоуровневые каналы вместо HTTP-модулей.  
  
-   Олицетворение для каждой операции с помощью WCF вместо олицетворения System.Web.  
  
 Кроме того можно рассмотреть выполнение служб в режиме совместимости с ASP.NET в WCF.  
  
## <a name="hosting-wcf-services-in-aspnet-compatibility-mode"></a>Размещение служб WCF в режиме совместимости ASP.NET  
 Несмотря на то, что модель WCF предназначена для согласованной работы в средах размещения и транспортов, часто применяются сценарии которых приложению не требуется такая степень гибкости. Режим совместимости ASP.NET WCF подходит для сценариев, в которых не требуется возможность размещения за пределами IIS или взаимодействие по протоколам, отличным от HTTP, но в которых используются все функции платформы приложений ASP.NET Web.  
  
 В отличие от side-by-side конфигурации по умолчанию, где инфраструктура размещения WCF перехватывает сообщения WCF и направляет их из конвейера HTTP, службы WCF, работающих в режиме совместимости с ASP.NET принимают полное участие в жизненном цикле запроса ASP.NET HTTP. В режиме совместимости службы WCF используют конвейер HTTP через <xref:System.Web.IHttpHandler> реализацию, аналогично способом запросы, для обработки страниц ASPX и веб-службами ASMX. В результате WCF работает аналогично ASMX в отношении следующих возможностей ASP.NET:  
  
-   <xref:System.Web.HttpContext>: Можно получить доступ к WCF службы, работающие в режиме совместимости с ASP.NET <xref:System.Web.HttpContext.Current%2A> и связанное состояние.  
  
-   Авторизация на основе файла: службы WCF, работающих в режиме совместимости с ASP.NET можно защитить путем присоединения файл системы управления доступом (ACL) к службе SVC-файла.  
  
-   Можно настроить Авторизация URL-адреса: ASP. Правила авторизации URL-адрес NET применяются для запросов WCF при служба WCF выполняется в режиме совместимости с ASP.NET.  
  
-   <xref:System.Web.HttpModuleCollection> расширяемость: WCF, так как службы, работающие в режиме совместимости с ASP.NET принимают полное участие в жизненном цикле запроса ASP.NET HTTP, любой HTTP-модуль, настроенный в конвейере HTTP может работать на запросы WCF до и после вызова службы.  
  
-   Олицетворение ASP.NET: Службы WCF, выполняются с использованием текущей идентификации ASP.NET олицетворение поток, который может отличаться от идентификации процесса IIS, если для приложения включено олицетворение ASP.NET. Если олицетворение ASP.NET и WCF олицетворение включены для конкретной операции службы, реализация службы в конечном счете выполняется с использованием удостоверения, полученный от WCF.  
  
 На уровне приложения с помощью следующей конфигурации (находится в файле Web.config) включен режим совместимости ASP.NET WCF:  
  
```xml  
<system.serviceModel>  
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true" />  
</system.serviceModel>  
```  
  
 Это значение по умолчанию для «`true`», если не указан. Установка этого значения равным «`false`» указывает, что все службы WCF, выполняемые в приложении не запустится в режиме совместимости с ASP.NET.  
  
 Поскольку режим совместимости ASP.NET подразумевает семантику обработки запросов, существенно отличается от значения по умолчанию WCF, реализации отдельных служб имеется возможность управления ли они выполняются внутри приложения, для которых ASP.NET Включен режим совместимости. Службы могут использовать атрибут <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> для указания, поддерживают ли они режим совместимости ASP.NET. По умолчанию атрибут имеет значение <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed>.  
  
 `[AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]`  
  
 `public class CalculatorService : ICalculatorSession`  
  
 `{//Implement calculator service methods.}`  
  
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
>  IIS 7.0 и WAS позволяют службам WCF обмениваться данными по протоколам, отличным от HTTP. Однако службы WCF, работающие в приложениях, поддерживающих режим совместимости с ASP.NET для предоставления конечных точек, отличные от HTTP не разрешены. В такой конфигурации создается исключение активации, когда служба получает первое сообщение.  
  
 Дополнительные сведения о включении режим совместимости с ASP.NET для службы WCF см. в разделе <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode> и [совместимости с ASP.NET](../../../../docs/framework/wcf/samples/aspnet-compatibility.md) образца.  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute>  
 [Функции размещения Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201276)
