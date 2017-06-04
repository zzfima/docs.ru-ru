---
title: "Службы WCF и ASP.NET | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b980496a-f0b0-4319-8e55-a0f0fa32da70
caps.latest.revision: 24
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 24
---
# Службы WCF и ASP.NET
В данном разделе описано параллельное размещение служб [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и ASP.NET и их размещение в режиме совместимости ASP.NET.  
  
## Параллельное размещение WCF и ASP.NET  
 Службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], размещенные в службах IIS, могут располагаться на страницах .ASPX и в веб\-службах ASMX внутри одного общего домена приложения.  Платформа ASP.NET предоставляет общие службы инфраструктуры, такие как управление доменом приложения и динамическая компиляция как в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], так и в среде выполнения HTTP ASP.NET.  Конфигурацией по умолчанию для [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] является параллельное размещение с ASP.NET.  
  
 ![Службы WCF и ASP .NET: общее состояние](../../../../docs/framework/wcf/feature-details/media/hostingwcfwithaspnet.gif "HostingWCFwithASPNET")  
  
 Среда выполнения HTTP ASP.NET обрабатывает запросы ASP.NET, но не участвует в обработке запросов, предназначенных для служб [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], несмотря на то что эти службы размещены в том же домене приложения, что и содержимое ASP.NET.  Вместо этого модель службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] перехватывает сообщения, адресованные службам [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], и направляет их через стек каналов или транспортный стек [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 Результаты использования параллельной модели представлены ниже.  
  
-   ASP.NET и службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] могут совместно использовать состояние домена приложения.  Поскольку две платформы могут совместно существовать в одном домене приложения, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] также может использовать состояние домена приложения совместно с платформой ASP.NET \(включая статические переменные, события и т. д.\)  
  
-   Службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] работают согласованно, независимо от среды размещения и транспорта.  Среда выполнения HTTP ASP.NET преднамеренно связана со средой размещения IIS\/ASP.NET и обменом данных по протоколу HTTP.  И наоборот, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создана для согласованной работы в разных средах размещения \([!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] работает согласованно как в пределах, так и за пределами IIS\) и с использованием разных транспортов \(служба, размещенная в IIS 7.0 и более поздних версий, работает согласованно во всех предоставляемых конечных точках, даже если некоторые из этих конечных точек используют протоколы, отличные от HTTP\).  
  
-   В пределах домена приложения функции, реализуемые средой выполнения HTTP, применяются к содержимому ASP.NET, но не к [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  Многие функции платформы приложений ASP.NET, характерные для HTTP, не применяются к службам [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], размещенным в пределах домена приложения с содержимым ASP.NET.  В примеры этих функций входит следующее.  
  
    -   HttpContext. Свойство <xref:System.Web.HttpContext.Current%2A> всегда имеет значение `null`, если доступ осуществляется из службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  Взамен рекомендуется использовать <xref:System.ServiceModel.OperationContext.Current.RequestContext>.  
  
    -   Авторизация на основе файла. Модель безопасности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не допускает применения списка управления доступом \(ACL\) к SVC\-файлу службы при решении того, авторизирован ли запрос службы.  
  
    -   Авторизация URL\-адреса на основе конфигурации. Аналогично, модель безопасности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не придерживается никаких правил авторизации на основе URL\-адреса, указанных в элементе конфигурации \<authorization\> System.Web.  Эти параметры игнорируются для запросов [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], если служба находится в пространстве URL\-адреса, защищенного правилами авторизации URL\-адреса платформы ASP.NET.  
  
    -   Расширяемость HttpModule. Инфраструктура размещения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] перехватывает запросы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], когда возникает событие <xref:System.Web.HttpApplication.PostAuthenticateRequest>, и не возвращает обработку в конвейер HTTP ASP.NET.  Модули, закодированные на перехват запросов на более поздних стадиях конвейера, не перехватывают запросы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
    -   Олицетворение ASP.NET. По умолчанию запросы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] всегда выполняются как идентификация процесса IIS, даже если ASP.NET настроена на включение олицетворения с помощью параметра конфигурации \<identity impersonate\=”true” \/\> System.Web.  
  
 Эти ограничения применяются только к службам [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], размещенным в приложении IIS.  На поведение содержимого ASP.NET не влияет наличие [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 В приложениях [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], требующих функциональность, традиционно предоставляемую конвейером HTTP, следует рассмотреть возможность использования эквивалентов [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], независимых от среды размещения и транспорта.  
  
-   <xref:System.ServiceModel.OperationContext> вместо <xref:System.Web.HttpContext>.  
  
-   <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> вместо авторизации на основе файла или URL\-адреса ASP.NET.  
  
-   <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector> или пользовательские многоуровневые каналы вместо HTTP\-модулей.  
  
-   Олицетворение для каждой операции с использованием [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] вместо олицетворения System.Web.  
  
 Также можно рассмотреть выполнение служб в режиме совместимости ASP.NET [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## Размещение служб WCF в режиме совместимости ASP.NET  
 Несмотря на то что модель [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создана для согласованной работы в разных средах размещения и с использованием разных транспортов, часто применяются сценарии, в которых приложению не требуется такая степень гибкости.  Режим совместимости ASP.NET [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] подходит для сценариев, в которых не требуется возможность размещения за пределами IIS или взаимодействие по протоколам, отличным от HTTP, но в которых используются все функции платформы веб\-приложений ASP.NET.  
  
 В отличие от параллельной конфигурации по умолчанию, в которой инфраструктура размещения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] перехватывает сообщения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и направляет их из конвейера HTTP, службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], выполняемые в режиме совместимости ASP.NET, принимают полное участие в жизненном цикле HTTP\-запроса ASP.NET.  В режиме совместимости службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] используют конвейер HTTP через реализацию <xref:System.Web.IHttpHandler> подобно тому, как выполняется обработка запросов для страниц ASPX и веб\-служб ASMX.  В результате [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] работает аналогично ASMX в отношении следующих функций ASP.NET.  
  
-   Службы <xref:System.Web.HttpContext>: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], выполняемые в режиме совместимости ASP.NET, могут получать доступ к свойству <xref:System.Web.HttpContext.Current%2A> и связанному с ним состоянию.  
  
-   Авторизация на основе файла. Службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], выполняемые в режиме совместимости ASP.NET, можно защитить, прикрепив к файлу .svc службы системный список управления доступом к файлу \(ACL\).  
  
-   Настраиваемая авторизация URL\-адреса. Правила авторизации URL\-адреса ASP.NET применяются к запросам [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], если служба [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] выполняется в режиме совместимости ASP.NET.  
  
-   Расширяемость <xref:System.Web.HttpModuleCollection>. Поскольку службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], выполняемые в режиме совместимости ASP.NET, принимают полное участие в жизненном цикле HTTP\-запроса ASP.NET, любой HTTP\-модуль, настроенный в конвейере HTTP, может выполнять операции с запросами [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] как перед вызовом службы, так и после него.  
  
-   Олицетворение ASP.NET. Службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] выполняются с использованием текущей идентификации олицетворяемого потока ASP.NET, которая может отличаться от идентификации процесса IIS, если для этого приложения включено олицетворение ASP.NET.  Если для определенной операции службы включено и олицетворение ASP.NET, и олицетворение [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], реализация службы в конечном счете выполняется с использованием идентификации, полученной от [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 Режим совместимости ASP.NET [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] включается на уровне приложения с помощью следующей конфигурации \(расположенной в файле Web.config приложения.\)  
  
```  
<system.serviceModel>  
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true" />  
</system.serviceModel>  
```  
  
 По умолчанию задается значение "`true`", если оно не указано.  Если установить значение `false`, все службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], выполняемые в приложении, не будут выполняться в режиме совместимости ASP.NET.  
  
 Поскольку режим совместимости ASP.NET подразумевает семантику обработки запросов, существенно отличающуюся от [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] по умолчанию, в реализации отдельных служб имеется возможность управления тем, выполняются ли они внутри приложения, для которого включен режим совместимости ASP.NET.  Службы могут использовать атрибут <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> для указания, поддерживают ли они режим совместимости ASP.NET.  По умолчанию атрибут имеет значение <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode>.  
  
 `[AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]`  
  
 `public class CalculatorService : ICalculatorSession`  
  
 `{//Implement calculator service methods.}`  
  
 В следующей таблице показано взаимодействие параметра режима совместимости на уровне приложения с заданным уровнем поддержки отдельной службы.  
  
|Параметр режима совместимости на уровне приложения|\[AspNetCompatibilityRequirementsMode\]<br /><br /> Параметр|Полученный результат|  
|--------------------------------------------------------|----------------------------------------------------------|--------------------------|  
|aspNetCompatibilityEnabled \= "`true`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode>|Служба включается успешно.|  
|aspNetCompatibilityEnabled \= "`true`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode>|Служба включается успешно.|  
|aspNetCompatibilityEnabled \= "`true`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode>|При получении службой сообщения возникает ошибка активации.|  
|aspNetCompatibilityEnabled \= "`false`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode>|При получении службой сообщения возникает ошибка активации.|  
|aspNetCompatibilityEnabled \= "`false`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode>|Служба включается успешно.|  
|aspNetCompatibilityEnabled \= "`false`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode>|Служба включается успешно.|  
  
> [!NOTE]
>  IIS 7.0 и WAS позволяют службам [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] взаимодействовать по протоколам, отличным от HTTP.  Однако службам [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], выполняемым в приложениях с включенным режимом совместимости ASP.NET, не разрешено предоставлять конечные точки, работающие по протоколу, отличному от HTTP.  В такой конфигурации создается исключение активации, когда служба получает первое сообщение.  
  
 Дополнительные сведения о включении режима совместимости ASP.NET для служб [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] см. в разделе <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode> и в образце [Совместимость с ASP.NET](../../../../docs/framework/wcf/samples/aspnet-compatibility.md).  
  
## См. также  
 <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute>   
 [Функции размещения фабрики приложений Windows Server](http://go.microsoft.com/fwlink/?LinkId=201276)