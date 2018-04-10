---
title: Использование Windows Management Instrumentation для диагностики
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe48738d-e31b-454d-b5ec-24c85c6bf79a
caps.latest.revision: 24
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0862f747cb969a6aa2e63d86e842097260e95b56
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="using-windows-management-instrumentation-for-diagnostics"></a><span data-ttu-id="55fef-102">Использование Windows Management Instrumentation для диагностики</span><span class="sxs-lookup"><span data-stu-id="55fef-102">Using Windows Management Instrumentation for Diagnostics</span></span>
[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="55fef-103"> предоставляет данные проверки службы в среде выполнения с помощью поставщика инструментария управления Windows (WMI) [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="55fef-103"> exposes inspection data of a service at runtime through a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] Windows Management Instrumentation (WMI) provider.</span></span>  
  
## <a name="enabling-wmi"></a><span data-ttu-id="55fef-104">Реализация WMI</span><span class="sxs-lookup"><span data-stu-id="55fef-104">Enabling WMI</span></span>  
 <span data-ttu-id="55fef-105">Инструментарий WMI - это реализованный корпорацией Майкрософт стандарт управления предприятием через Интернет (WBEM).</span><span class="sxs-lookup"><span data-stu-id="55fef-105">WMI is Microsoft's implementation of the Web-Based Enterprise Management (WBEM) standard.</span></span> [!INCLUDE[crabout](../../../../../includes/crabout-md.md)]<span data-ttu-id="55fef-106">см. в пакете WMI SDK [инструментария управления Windows](https://msdn.microsoft.com/library/aa394582.aspx).</span><span class="sxs-lookup"><span data-stu-id="55fef-106"> the WMI SDK, see [Windows Management Instrumentation](https://msdn.microsoft.com/library/aa394582.aspx).</span></span> <span data-ttu-id="55fef-107">WBEM является отраслевым стандартом предоставления приложениями инструментария управления для внешних средств управления.</span><span class="sxs-lookup"><span data-stu-id="55fef-107">WBEM is an industry standard for how applications expose management instrumentation to external management tools.</span></span>  
  
 <span data-ttu-id="55fef-108">Поставщик инструментария WMI - это компонент, предоставляющий инструментарий в среде выполнения с помощью совместимого с WBEM интерфейса.</span><span class="sxs-lookup"><span data-stu-id="55fef-108">A WMI provider is a component that exposes instrumentation at runtime through a WBEM-compatible interface.</span></span> <span data-ttu-id="55fef-109">Он состоит из набора объектов инструментария WMI, имеющих пары атрибут/значение.</span><span class="sxs-lookup"><span data-stu-id="55fef-109">It consists of a set of WMI objects that have attribute/value pairs.</span></span> <span data-ttu-id="55fef-110">Пары могут быть нескольких простых типов.</span><span class="sxs-lookup"><span data-stu-id="55fef-110">Pairs can be of a number of simple types.</span></span> <span data-ttu-id="55fef-111">Средства управления могут подключаться к службам через интерфейс во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="55fef-111">Management tools can connect to the services through the interface at runtime.</span></span> [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]<span data-ttu-id="55fef-112"> предоставляет атрибуты служб, такие как адреса, привязки, поведения и прослушиватели.</span><span class="sxs-lookup"><span data-stu-id="55fef-112"> exposes attributes of services such as addresses, bindings, behaviors, and listeners.</span></span>  
  
 <span data-ttu-id="55fef-113">Встроенный поставщик инструментария WMI может быть активирован в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="55fef-113">The built-in WMI provider can be activated in the configuration file of the application.</span></span> <span data-ttu-id="55fef-114">Это осуществляется посредством `wmiProviderEnabled` атрибут [ \<диагностики >](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md) в [ \<system.serviceModel >](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) статьи, как показано в следующем образце Конфигурация.</span><span class="sxs-lookup"><span data-stu-id="55fef-114">This is done through the `wmiProviderEnabled` attribute of the [\<diagnostics>](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md) in the [\<system.serviceModel>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) section, as shown in the following sample configuration.</span></span>  
  
```xml  
<system.serviceModel>  
    …  
    <diagnostics wmiProviderEnabled="true" />  
    …  
</system.serviceModel>  
```  
  
 <span data-ttu-id="55fef-115">Эта запись конфигурации предоставляет интерфейс инструментария WMI.</span><span class="sxs-lookup"><span data-stu-id="55fef-115">This configuration entry exposes a WMI interface.</span></span> <span data-ttu-id="55fef-116">Теперь приложения управления могут подключаться через этот интерфейс и обращаться к инструментарию управления приложения.</span><span class="sxs-lookup"><span data-stu-id="55fef-116">Management applications can now connect through this interface and access the management instrumentation of the application.</span></span>  
  
## <a name="accessing-wmi-data"></a><span data-ttu-id="55fef-117">Доступ к данным WMI</span><span class="sxs-lookup"><span data-stu-id="55fef-117">Accessing WMI Data</span></span>  
 <span data-ttu-id="55fef-118">Доступ к данным инструментария WMI может осуществляться несколькими различными способами.</span><span class="sxs-lookup"><span data-stu-id="55fef-118">WMI data can be accessed in many different ways.</span></span> <span data-ttu-id="55fef-119">Microsoft предоставляет программные интерфейсы WMI для скриптов, приложений [!INCLUDE[vbprvb](../../../../../includes/vbprvb-md.md)], приложений на языке C++ и [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="55fef-119">Microsoft provides WMI APIs for scripts, [!INCLUDE[vbprvb](../../../../../includes/vbprvb-md.md)] applications, C++ applications, and the [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="55fef-120">Дополнительные сведения см. в разделе [WMI с помощью](http://go.microsoft.com/fwlink/?LinkId=95183).</span><span class="sxs-lookup"><span data-stu-id="55fef-120">For more information, see [Using WMI](http://go.microsoft.com/fwlink/?LinkId=95183).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="55fef-121">При использовании предоставляемых .NET Framework методов для программного доступа к данным WMI следует помнить о том, что при установке подключения эти методы могут вызывать исключения.</span><span class="sxs-lookup"><span data-stu-id="55fef-121">If you use the .NET Framework provided methods to programmatically access WMI data, you should be aware that such methods may throw exceptions when the connection is established.</span></span> <span data-ttu-id="55fef-122">Подключение устанавливается не во время создания экземпляра <xref:System.Management.ManagementObject>, а при получении первого запроса, при котором происходит реальный обмен данными.</span><span class="sxs-lookup"><span data-stu-id="55fef-122">The connection is not established during the construction of the <xref:System.Management.ManagementObject> instance, but on the first request involving actual data exchange.</span></span> <span data-ttu-id="55fef-123">Следовательно, следует использовать блок `try..catch` для перехвата возможных исключений.</span><span class="sxs-lookup"><span data-stu-id="55fef-123">Therefore, you should use a `try..catch` block to catch the possible exceptions.</span></span>  
  
 <span data-ttu-id="55fef-124">Можно изменить уровень ведения журнала сообщений и трассировок, а также параметры журнала сообщений для источника трассировки `System.ServiceModel` в инструментарии WMI.</span><span class="sxs-lookup"><span data-stu-id="55fef-124">You can change the trace and message logging level, as well as message logging options for the `System.ServiceModel` trace source in WMI.</span></span> <span data-ttu-id="55fef-125">Это можно сделать путем обращения к [AppDomainInfo](../../../../../docs/framework/wcf/diagnostics/wmi/appdomaininfo.md) экземпляр, который обеспечивает доступ к следующим логическим свойствам: `LogMessagesAtServiceLevel`, `LogMessagesAtTransportLevel`, `LogMalformedMessages`, и `TraceLevel`.</span><span class="sxs-lookup"><span data-stu-id="55fef-125">This can be done by accessing the [AppDomainInfo](../../../../../docs/framework/wcf/diagnostics/wmi/appdomaininfo.md) instance, which exposes these Boolean properties: `LogMessagesAtServiceLevel`, `LogMessagesAtTransportLevel`, `LogMalformedMessages`, and `TraceLevel`.</span></span> <span data-ttu-id="55fef-126">Поэтому, если в файле конфигурации прослушиватель трассировки настроен на ведение журнала, но эти параметры имеют значение `false`, можно впоследствии изменить их значения на `true`, когда приложение будет выполняться.</span><span class="sxs-lookup"><span data-stu-id="55fef-126">Therefore, if you configure a trace listener for message logging, but set these options to `false` in configuration, you can later change them to `true` when the application is running.</span></span> <span data-ttu-id="55fef-127">В результате ведение журнала будет включено во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="55fef-127">This will effectively enable message logging at runtime.</span></span> <span data-ttu-id="55fef-128">Аналогично, если ведение журнала было включено в файле конфигурации, его можно отключить во время выполнения с помощью инструментария WMI.</span><span class="sxs-lookup"><span data-stu-id="55fef-128">Similarly, if you enable message logging in your configuration file, you can disable it at runtime using WMI.</span></span>  
  
 <span data-ttu-id="55fef-129">Необходимо помнить, что если прослушиватели трассировок журнала сообщений для журнала сообщений или прослушиватели трассировок `System.ServiceModel` для трассировок не заданы в файле конфигурации, ни одно из изменений не будет применено, даже если эти изменения принимаются инструментарием WMI.</span><span class="sxs-lookup"><span data-stu-id="55fef-129">You should be aware that if no message logging trace listeners for message logging, or no `System.ServiceModel` trace listeners for tracing are specified in the configuration file, none of your changes are taken into effect, even though the changes are accepted by WMI.</span></span> <span data-ttu-id="55fef-130">Дополнительные сведения о правильной настройке соответствующих прослушивателей см. в разделе [Настройка ведения журнала сообщений](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) и [Настройка трассировки](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md).</span><span class="sxs-lookup"><span data-stu-id="55fef-130">For more information on properly setting up the respective listeners, see [Configuring Message Logging](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) and [Configuring Tracing](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md).</span></span> <span data-ttu-id="55fef-131">Уровень трассировки всех остальных источников трассировки, заданных конфигурацией, действителен только при запуске приложения и не может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="55fef-131">The trace level of all other trace sources specified by configuration is effective when the application starts, and cannot be changed.</span></span>  
  
 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]<span data-ttu-id="55fef-132"> предоставляет метод `GetOperationCounterInstanceName` скриптов.</span><span class="sxs-lookup"><span data-stu-id="55fef-132"> exposes a `GetOperationCounterInstanceName` method for scripting.</span></span> <span data-ttu-id="55fef-133">Если передать этому методу имя операции, он возвращает имя экземпляра счетчика производительности.</span><span class="sxs-lookup"><span data-stu-id="55fef-133">This method returns a performance counter instance name if you provide it with an operation name.</span></span> <span data-ttu-id="55fef-134">Однако он не проверяет входные данные.</span><span class="sxs-lookup"><span data-stu-id="55fef-134">However, it does not validate your input.</span></span> <span data-ttu-id="55fef-135">Таким образом, если передать ему неправильное имя операции, возвращается неверное имя счетчика.</span><span class="sxs-lookup"><span data-stu-id="55fef-135">Therefore, if you provide an incorrect operation name, an incorrect counter name is returned.</span></span>  
  
 <span data-ttu-id="55fef-136">Свойство `OutgoingChannel` экземпляра `Service` не выполняет подсчет каналов, открытых службой для подключения к другой службе, если клиент [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] для службы назначения не создается в методе `Service`.</span><span class="sxs-lookup"><span data-stu-id="55fef-136">The `OutgoingChannel` property of the `Service` instance does not count channels opened by a service to connect to another service, if the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] client to the destination service is not created within the `Service` method.</span></span>  
  
 <span data-ttu-id="55fef-137">**Внимание** WMI поддерживает только <xref:System.TimeSpan> значение до 3 знаков.</span><span class="sxs-lookup"><span data-stu-id="55fef-137">**Caution** WMI only supports a <xref:System.TimeSpan> value up to 3 decimal points.</span></span> <span data-ttu-id="55fef-138">Например, если одному из свойств служба присваивает значение <xref:System.TimeSpan.MaxValue>, при просмотре через WMI это значение усекается до 3 знаков после десятичного разделителя.</span><span class="sxs-lookup"><span data-stu-id="55fef-138">For example, if your service sets one of its properties to <xref:System.TimeSpan.MaxValue>, its value is truncated after 3 decimal points when viewed through WMI.</span></span>  
  
## <a name="security"></a><span data-ttu-id="55fef-139">Безопасность</span><span class="sxs-lookup"><span data-stu-id="55fef-139">Security</span></span>  
 <span data-ttu-id="55fef-140">Так как поставщик инструментария WMI [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] разрешает обнаружение служб в среде, необходимо проявлять предельную осторожность при предоставлении к нему доступа.</span><span class="sxs-lookup"><span data-stu-id="55fef-140">Because the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] WMI provider allows the discovery of services in an environment, you should exercise extreme caution for granting access to it.</span></span> <span data-ttu-id="55fef-141">При изменении настроек по умолчанию, при которых доступ предоставляется только администратору, третьи лица с более низкой степенью доверия могут получить доступ к конфиденциальным данным в среде.</span><span class="sxs-lookup"><span data-stu-id="55fef-141">If you relax the default administrator-only access, you may allow less-trusted parties access to sensitive data in your environment.</span></span> <span data-ttu-id="55fef-142">В частности, при расширении разрешений для удаленного доступа к WMI могут возникнуть атаки на переполнение.</span><span class="sxs-lookup"><span data-stu-id="55fef-142">Specifically, if you loosen permissions on remote WMI access, flooding attacks can occur.</span></span> <span data-ttu-id="55fef-143">При переполнении процесса избыточными запросами WMI производительность процесса может снизится.</span><span class="sxs-lookup"><span data-stu-id="55fef-143">If a process is flooded by excessive WMI requests, its performance can be degraded.</span></span>  
  
 <span data-ttu-id="55fef-144">Кроме того, при расширении прав доступа к файлу MOF третьи лица с более низкой степенью доверия могут управлять поведением WMI и изменять объекты, находящиеся в схеме WMI.</span><span class="sxs-lookup"><span data-stu-id="55fef-144">In addition, if you relax access permissions for the MOF file, less-trusted parties can manipulate the behavior of WMI and alter the objects that are loaded in the WMI schema.</span></span> <span data-ttu-id="55fef-145">Например, поля могут быть удалены таким образом, что критические данные скрыты от администратора; или поля, которые не заполняются или вызывают исключения, добавляются в файл.</span><span class="sxs-lookup"><span data-stu-id="55fef-145">For example, fields can be removed such that critical data is concealed from the administrator or that fields that do not populate or cause exceptions are added to the file.</span></span>  
  
 <span data-ttu-id="55fef-146">По умолчанию поставщик инструментария управления Windows [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] гарантирует право доступа администратора к инструментам "Выполнить метод", "Запись поставщика" и "Включить учетную запись", а также к инструменту "Включить учетную запись" для службы ASP.NET, локальной службы и сетевой службы.</span><span class="sxs-lookup"><span data-stu-id="55fef-146">By default, the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] WMI provider grants "execute method", "provider write", and "enable account" permission for Administrator, and "enable account" permission for ASP.NET, Local Service and Network Service.</span></span> <span data-ttu-id="55fef-147">В частности, на платформах, отличных от [!INCLUDE[wv](../../../../../includes/wv-md.md)], учетная запись ASP.NET имеет доступ на чтение в пространстве имен ServiceModel инструментария WMI.</span><span class="sxs-lookup"><span data-stu-id="55fef-147">In particular, on non-[!INCLUDE[wv](../../../../../includes/wv-md.md)] platforms, the ASP.NET account has read access to the WMI ServiceModel namespace.</span></span> <span data-ttu-id="55fef-148">Если требуется не предоставлять эти привилегии определенной группе пользователей, нужно либо деактивировать поставщика инструментария WMI (по умолчанию он отключен), либо запретить доступ указанной группы пользователей.</span><span class="sxs-lookup"><span data-stu-id="55fef-148">If you do not want to grant these privileges to a particular user group, you should either deactivate the WMI provider (it is disabled by default), or disable access for the specific user group.</span></span>  
  
 <span data-ttu-id="55fef-149">Возможно, поставщик инструментария WMI не удастся включить через конфигурацию по причине недостаточных привилегий пользователя.</span><span class="sxs-lookup"><span data-stu-id="55fef-149">In addition, when you attempt to enable WMI through configuration, WMI may not be enabled due to insufficient user privilege.</span></span> <span data-ttu-id="55fef-150">Однако при возникновении этого сбоя никакой записи в журнале событий не делается.</span><span class="sxs-lookup"><span data-stu-id="55fef-150">However, no event is written to the event log to record this failure.</span></span>  
  
 <span data-ttu-id="55fef-151">Для изменения уровней привилегий пользователя выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="55fef-151">To modify user privilege levels, use the following steps.</span></span>  
  
1.  <span data-ttu-id="55fef-152">Нажмите кнопку Пуск и затем запустите введите **compmgmt.msc**.</span><span class="sxs-lookup"><span data-stu-id="55fef-152">Click Start and then Run and type **compmgmt.msc**.</span></span>  
  
2.  <span data-ttu-id="55fef-153">Щелкните правой кнопкой мыши **службы и приложения/управляющий элемент WMI** установите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="55fef-153">Right-click **Services and Application/WMI Controls** to select **Properties**.</span></span>  
  
3.  <span data-ttu-id="55fef-154">Выберите **безопасности** вкладку и перейдите к **Root/ServiceModel** пространства имен.</span><span class="sxs-lookup"><span data-stu-id="55fef-154">Select the **Security** Tab, and navigate to the **Root/ServiceModel** namespace.</span></span> <span data-ttu-id="55fef-155">Нажмите кнопку **безопасности** кнопки.</span><span class="sxs-lookup"><span data-stu-id="55fef-155">Click the **Security** button.</span></span>  
  
4.  <span data-ttu-id="55fef-156">Выберите группу или пользователя, для управления доступом и использовать **Разрешить** или **Deny** флажок, чтобы настроить разрешения.</span><span class="sxs-lookup"><span data-stu-id="55fef-156">Select the specific group or user that you want to control access and use the **Allow** or **Deny** checkbox to configure permissions.</span></span>  
  
## <a name="granting-wcf-wmi-registration-permissions-to-additional-users"></a><span data-ttu-id="55fef-157">Предоставление дополнительным пользователям разрешений на регистрацию WCF WMI</span><span class="sxs-lookup"><span data-stu-id="55fef-157">Granting WCF WMI Registration Permissions to Additional Users</span></span>  
 <span data-ttu-id="55fef-158">WCF предоставляет доступ к данным управления для WMI.</span><span class="sxs-lookup"><span data-stu-id="55fef-158">WCF exposes management data to WMI.</span></span> <span data-ttu-id="55fef-159">Это делается посредством размещается внутрипроцессный поставщик WMI, иногда называется «несвязанным поставщиком».</span><span class="sxs-lookup"><span data-stu-id="55fef-159">It does so by hosting an in-process WMI provider, sometimes called a "decoupled provider".</span></span> <span data-ttu-id="55fef-160">Для предоставления доступа к данным управления учетная запись, которая регистрирует этот поставщик, должна иметь необходимые разрешения.</span><span class="sxs-lookup"><span data-stu-id="55fef-160">For the management data to be exposed, the account that registers this provider must have the appropriate permissions.</span></span> <span data-ttu-id="55fef-161">В Windows регистрация несвязанных поставщиков по умолчанию доступна только небольшому числу привилегированных учетных записей.</span><span class="sxs-lookup"><span data-stu-id="55fef-161">In Windows, only a small set of privileged accounts can register decoupled providers by default.</span></span> <span data-ttu-id="55fef-162">Это обстоятельство вызывает затруднения, поскольку пользователям обычно нужно предоставлять доступ к данным WMI из службы WCF, которая работает с учетной записью, не входящей в набор по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="55fef-162">This is a problem because users commonly want to expose WMI data from a WCF service running under an account that is not in the default set.</span></span>  
  
 <span data-ttu-id="55fef-163">Чтобы предоставить такой доступ, администратор должен предоставить дополнительной учетной записи следующие разрешения в указанном порядке:</span><span class="sxs-lookup"><span data-stu-id="55fef-163">To provide this access, an administrator must grant the following permissions to the additional account in the following order:</span></span>  
  
1.  <span data-ttu-id="55fef-164">разрешение на доступ к пространству имен WCF WMI;</span><span class="sxs-lookup"><span data-stu-id="55fef-164">Permission to access to the WCF WMI Namespace.</span></span>  
  
2.  <span data-ttu-id="55fef-165">разрешение на регистрацию несвязанного поставщика WMI для WCF.</span><span class="sxs-lookup"><span data-stu-id="55fef-165">Permission to register the WCF Decoupled WMI Provider.</span></span>  
  
#### <a name="to-grant-wmi-namespace-access-permission"></a><span data-ttu-id="55fef-166">Предоставление разрешения на доступ к пространству имен WMI</span><span class="sxs-lookup"><span data-stu-id="55fef-166">To grant WMI namespace access permission</span></span>  
  
1.  <span data-ttu-id="55fef-167">Выполните следующий скрипт PowerShell.</span><span class="sxs-lookup"><span data-stu-id="55fef-167">Run the following PowerShell script.</span></span>  
  
    ```powershell  
    write-host ""  
    write-host "Granting Access to root/servicemodel WMI namespace to built in users group"  
    write-host ""  
  
    # Create the binary representation of the permissions to grant in SDDL  
    $newPermissions = "O:BAG:BAD:P(A;CI;CCDCLCSWRPWPRCWD;;;BA)(A;CI;CC;;;NS)(A;CI;CC;;;LS)(A;CI;CC;;;BU)"  
    $converter = new-object system.management.ManagementClass Win32_SecurityDescriptorHelper  
    $binarySD = $converter.SDDLToBinarySD($newPermissions)  
    $convertedPermissions = ,$binarySD.BinarySD  
  
    # Get the object used to set the permissions  
    $security = gwmi -namespace root/servicemodel -class __SystemSecurity  
  
    # Get and output the current settings  
    $binarySD = @($null)  
    $result = $security.PsBase.InvokeMethod("GetSD",$binarySD)  
  
    $outsddl = $converter.BinarySDToSDDL($binarySD[0])  
    write-host "Previous ACL: "$outsddl.SDDL  
  
    # Change the Access Control List (ACL) using SDDL  
    $result = $security.PsBase.InvokeMethod("SetSD",$convertedPermissions)   
  
    # Get and output the current settings  
    $binarySD = @($null)  
    $result = $security.PsBase.InvokeMethod("GetSD",$binarySD)  
  
    $outsddl = $converter.BinarySDToSDDL($binarySD[0])  
    write-host "New ACL:      "$outsddl.SDDL  
    write-host ""  
    ```  
  
     <span data-ttu-id="55fef-168">Этот сценарий PowerShell использует языка определения дескрипторов безопасности (SDDL) для предоставления доступа группе встроенных пользователей к пространству имен WMI «root/servicemodel».</span><span class="sxs-lookup"><span data-stu-id="55fef-168">This PowerShell script uses Security Descriptor Definition Language (SDDL) to grant the Built-In Users group access to the "root/servicemodel" WMI namespace.</span></span> <span data-ttu-id="55fef-169">В нем указываются следующие списки управления доступом.</span><span class="sxs-lookup"><span data-stu-id="55fef-169">It specifies the following ACLs:</span></span>  
  
    -   <span data-ttu-id="55fef-170">Встроенная учетная запись администратора (BA) - уже имеет доступ.</span><span class="sxs-lookup"><span data-stu-id="55fef-170">Built-In Administrator (BA) - Already Had Access.</span></span>  
  
    -   <span data-ttu-id="55fef-171">Сетевая служба (NS) - уже имеет доступ.</span><span class="sxs-lookup"><span data-stu-id="55fef-171">Network Service (NS) - Already Had Access.</span></span>  
  
    -   <span data-ttu-id="55fef-172">Локальная система (LS) - уже имеет доступ.</span><span class="sxs-lookup"><span data-stu-id="55fef-172">Local System (LS) - Already Had Access.</span></span>  
  
    -   <span data-ttu-id="55fef-173">Встроенные пользователи - группа, которой предоставляется доступ.</span><span class="sxs-lookup"><span data-stu-id="55fef-173">Built-In Users - The group to grant access to.</span></span>  
  
#### <a name="to-grant-provider-registration-access"></a><span data-ttu-id="55fef-174">Предоставление доступа к регистрации поставщика</span><span class="sxs-lookup"><span data-stu-id="55fef-174">To grant provider registration access</span></span>  
  
1.  <span data-ttu-id="55fef-175">Выполните следующий скрипт PowerShell.</span><span class="sxs-lookup"><span data-stu-id="55fef-175">Run the following PowerShell script.</span></span>  
  
    ```powershell  
    write-host ""  
    write-host "Granting WCF provider registration access to built in users group"  
    write-host ""  
    # Set security on ServiceModel provider  
    $provider = get-WmiObject -namespace "root\servicemodel" __Win32Provider  
  
    write-host "Previous ACL: "$provider.SecurityDescriptor  
    $result = $provider.SecurityDescriptor = "O:BUG:BUD:(A;;0x1;;;BA)(A;;0x1;;;NS)(A;;0x1;;;LS)(A;;0x1;;;BU)"  
  
    # Commit the changes and display it to the console  
    $result = $provider.Put()  
    write-host "New ACL:      "$provider.SecurityDescriptor  
    write-host ""  
    ```  
  
### <a name="granting-access-to-arbitrary-users-or-groups"></a><span data-ttu-id="55fef-176">Предоставление доступа произвольным пользователям или группам</span><span class="sxs-lookup"><span data-stu-id="55fef-176">Granting Access to Arbitrary Users or Groups</span></span>  
 <span data-ttu-id="55fef-177">В примере из этого раздела всем локальным пользователям предоставляются права доступа к регистрации поставщика WMI.</span><span class="sxs-lookup"><span data-stu-id="55fef-177">The example in this section grants WMI Provider registration privileges to all local users.</span></span> <span data-ttu-id="55fef-178">Если нужно предоставить доступ пользователю или группе, которые не являются встроенными, необходимо получить идентификатор безопасности этого пользователя или группы.</span><span class="sxs-lookup"><span data-stu-id="55fef-178">If you want to grant access to a user or group that is not built in, then you must obtain that user or group’s Security Identifier (SID).</span></span> <span data-ttu-id="55fef-179">Нет общего метода для получения идентификатора безопасности любого пользователя.</span><span class="sxs-lookup"><span data-stu-id="55fef-179">There is no simple way to get the SID for an arbitrary user.</span></span> <span data-ttu-id="55fef-180">В качестве одного из решений можно выполнить вход от имени нужного пользователя, а затем выполнить следующую команду в командной оболочке.</span><span class="sxs-lookup"><span data-stu-id="55fef-180">One method is to log on as the desired user and then issue the following shell command.</span></span>  
  
```  
Whoami /user  
```  
  
 <span data-ttu-id="55fef-181">Это позволит получить идентификатор безопасности текущего пользователя, однако такой метод нельзя использовать, чтобы получить идентификатор безопасности любого пользователя.</span><span class="sxs-lookup"><span data-stu-id="55fef-181">This provides the SID of the current user, but this method cannot be used to get the SID on any arbitrary user.</span></span> <span data-ttu-id="55fef-182">Другой способ получения идентификатора безопасности является использование [getsid.exe](http://go.microsoft.com/fwlink/?LinkId=186467) средства из [Windows 2000 Resource Kit Tools для выполнения административных задач](http://go.microsoft.com/fwlink/?LinkId=178660).</span><span class="sxs-lookup"><span data-stu-id="55fef-182">Another method to get the SID is to use the [getsid.exe](http://go.microsoft.com/fwlink/?LinkId=186467) tool from the [Windows 2000 Resource Kit Tools for administrative tasks](http://go.microsoft.com/fwlink/?LinkId=178660).</span></span> <span data-ttu-id="55fef-183">Эта программа сравнивает идентификаторы безопасности двух пользователей (локальных или пользователей домена) и помимо прочего выводит два идентификатора в командную строку.</span><span class="sxs-lookup"><span data-stu-id="55fef-183">This tool compares the SID of two users (local or domain), and as a side effect prints the two SIDs to the command line.</span></span> [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)]<span data-ttu-id="55fef-184">[Известные идентификаторы безопасности](http://go.microsoft.com/fwlink/?LinkId=186468).</span><span class="sxs-lookup"><span data-stu-id="55fef-184"> [Well Known SIDs](http://go.microsoft.com/fwlink/?LinkId=186468).</span></span>  
  
## <a name="accessing-remote-wmi-object-instances"></a><span data-ttu-id="55fef-185">Доступ к экземплярам удаленных объектов WMI</span><span class="sxs-lookup"><span data-stu-id="55fef-185">Accessing Remote WMI Object Instances</span></span>  
 <span data-ttu-id="55fef-186">Если требуется получить доступ к экземплярам инструментария управления Windows [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] с удаленного компьютера, необходимо разрешить конфиденциальность пакета в используемых для доступа средствах.</span><span class="sxs-lookup"><span data-stu-id="55fef-186">If you need to access [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] WMI instances on a remote machine, you must enable packet privacy on the tools that you use for access.</span></span> <span data-ttu-id="55fef-187">В следующем разделе описывается, как это можно сделать с помощью WMI CIM Studio, тестера инструментария управления Windows или .NET SDK 2.0.</span><span class="sxs-lookup"><span data-stu-id="55fef-187">The following section describes how to achieve these using the WMI CIM Studio, Windows Management Instrumentation Tester, as well as .NET SDK 2.0.</span></span>  
  
### <a name="wmi-cim-studio"></a><span data-ttu-id="55fef-188">WMI CIM Studio</span><span class="sxs-lookup"><span data-stu-id="55fef-188">WMI CIM Studio</span></span>  
 <span data-ttu-id="55fef-189">Если вы установили [средства управления WMI](http://go.microsoft.com/fwlink/?LinkId=95185), можно использовать WMI CIM Studio, для доступа к экземплярам WMI.</span><span class="sxs-lookup"><span data-stu-id="55fef-189">If you have installed [WMI Administrative Tools](http://go.microsoft.com/fwlink/?LinkId=95185), you can use the WMI CIM Studio to access WMI instances.</span></span> <span data-ttu-id="55fef-190">Средства расположены в следующей папке:</span><span class="sxs-lookup"><span data-stu-id="55fef-190">The tools are in the following folder</span></span>  
  
 <span data-ttu-id="55fef-191">**%windir%\Program Files\WMI средства\\**</span><span class="sxs-lookup"><span data-stu-id="55fef-191">**%windir%\Program Files\WMI Tools\\**</span></span>  
  
1.  <span data-ttu-id="55fef-192">В **подключиться к пространству имен:** введите **root\ServiceModel** и нажмите кнопку **ОК.**</span><span class="sxs-lookup"><span data-stu-id="55fef-192">In the **Connect to namespace:** window, type **root\ServiceModel** and click **OK.**</span></span>  
  
2.  <span data-ttu-id="55fef-193">В **вход в WMI CIM Studio** окно, нажмите кнопку **параметры >>** кнопку, чтобы развернуть окно.</span><span class="sxs-lookup"><span data-stu-id="55fef-193">In the **WMI CIM Studio Login** window, click the **Options >>** button to expand the window.</span></span> <span data-ttu-id="55fef-194">Выберите **защита пакетов** для **уровень проверки подлинности**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="55fef-194">Select **Packet privacy** for **Authentication level**, and click **OK**.</span></span>  
  
### <a name="windows-management-instrumentation-tester"></a><span data-ttu-id="55fef-195">Тестер инструментария управления Windows</span><span class="sxs-lookup"><span data-stu-id="55fef-195">Windows Management Instrumentation Tester</span></span>  
 <span data-ttu-id="55fef-196">Это средство установлено Windows.</span><span class="sxs-lookup"><span data-stu-id="55fef-196">This tool is installed by Windows.</span></span> <span data-ttu-id="55fef-197">Чтобы запустить его, запустить консоль командной строки с помощью команды **cmd.exe** в **Пуск-Выполнить** диалоговое окно и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="55fef-197">To run it, launch a command console by typing **cmd.exe** in the **Start/Run** dialog box and click **OK**.</span></span> <span data-ttu-id="55fef-198">Введите **wbemtest.exe** в окне команд.</span><span class="sxs-lookup"><span data-stu-id="55fef-198">Then, type **wbemtest.exe** in the command window.</span></span> <span data-ttu-id="55fef-199">Запустится средство Тестер инструментария управления Windows.</span><span class="sxs-lookup"><span data-stu-id="55fef-199">The Windows Management Instrumentation Tester tool is then launched.</span></span>  
  
1.  <span data-ttu-id="55fef-200">Нажмите кнопку **Connect** кнопки в правом верхнем углу окна.</span><span class="sxs-lookup"><span data-stu-id="55fef-200">Click the **Connect** button on the top right corner of the window.</span></span>  
  
2.  <span data-ttu-id="55fef-201">В новом окне введите **root\ServiceModel** для **имен** и выберите **защита пакетов** для **уровень проверки подлинности**.</span><span class="sxs-lookup"><span data-stu-id="55fef-201">In the new window, enter **root\ServiceModel** for the **Namespace** field, and select **Packet privacy** for **Authentication level**.</span></span> <span data-ttu-id="55fef-202">Нажмите кнопку **Подключиться**.</span><span class="sxs-lookup"><span data-stu-id="55fef-202">Click **Connect**.</span></span>  
  
### <a name="using-managed-code"></a><span data-ttu-id="55fef-203">Использование управляемого кода</span><span class="sxs-lookup"><span data-stu-id="55fef-203">Using Managed Code</span></span>  
 <span data-ttu-id="55fef-204">Доступ к удаленным экземплярам WMI также может осуществляться программно с помощью классов, предоставляемых пространством имен <xref:System.Management>.</span><span class="sxs-lookup"><span data-stu-id="55fef-204">You can also access remote WMI instances programmatically by using classes provided by the <xref:System.Management> namespace.</span></span> <span data-ttu-id="55fef-205">В следующем образце кода показано, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="55fef-205">The following code sample demonstrates how to do this.</span></span>  
  
```  
String wcfNamespace = String.Format(@"\\{0}\Root\ServiceModel",      
   this.serviceMachineName);  
  
ConnectionOptions connection = new ConnectionOptions();  
connection.Authentication = AuthenticationLevel.PacketPrivacy;  
ManagementScope scope = new ManagementScope(this.wcfNamespace, connection);  
```
