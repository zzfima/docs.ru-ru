---
title: Примеры устранения неполадок WCF
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], troubleshooting
- Windows Communication Foundation [WCF], troubleshooting
ms.assetid: a9ea7a53-f31a-46eb-806e-898e465a4992
ms.openlocfilehash: f85d37fde19767d7fd1e3002776b4816666cc7e8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183058"
---
# <a name="wcf-troubleshooting-quickstart"></a><span data-ttu-id="f9603-102">Примеры устранения неполадок WCF</span><span class="sxs-lookup"><span data-stu-id="f9603-102">WCF Troubleshooting Quickstart</span></span>
<span data-ttu-id="f9603-103">В этом разделе приведено несколько известных проблем, с которыми столкнулись пользователи при разработке клиентов и служб WCF.</span><span class="sxs-lookup"><span data-stu-id="f9603-103">This topic lists a number of known issues customers have run into while developing WCF clients and services.</span></span> <span data-ttu-id="f9603-104">Если проблема, с которой столкнулись вы, отсутствует в этом списке, рекомендуется настроить трассировку для данной службы.</span><span class="sxs-lookup"><span data-stu-id="f9603-104">If the issue you are running into is not in this list, we recommend you configure tracing for your service.</span></span> <span data-ttu-id="f9603-105">При этом будет создан файл трассировки, который можно просмотреть с помощью средства просмотра файлов трассировки и получить подробные сведения об исключениях, которые могут возникать в службе.</span><span class="sxs-lookup"><span data-stu-id="f9603-105">This will generate a trace file that you can view with the trace file viewer and get detailed information about exceptions that may be occurring within the service.</span></span> <span data-ttu-id="f9603-106">Дополнительные сведения о настройке трассировки см. в разделе [Configuring Tracing](./diagnostics/tracing/configuring-tracing.md).</span><span class="sxs-lookup"><span data-stu-id="f9603-106">For more information on configuring tracing, see: [Configuring Tracing](./diagnostics/tracing/configuring-tracing.md).</span></span> <span data-ttu-id="f9603-107">Дополнительные сведения о средстве просмотра файлов трассировки см. в разделе [Service Trace Viewer Tool (SvcTraceViewer.exe)](service-trace-viewer-tool-svctraceviewer-exe.md).</span><span class="sxs-lookup"><span data-stu-id="f9603-107">For more information on the trace file viewer, see: [Service Trace Viewer Tool (SvcTraceViewer.exe)](service-trace-viewer-tool-svctraceviewer-exe.md).</span></span>  
  
1. [<span data-ttu-id="f9603-108">После установки Windows 7 и IIS при попытке перейти к службе WCF выдается следующее сообщение об ошибке: «Ошибка HTTP 404.3 - не найдено»</span><span class="sxs-lookup"><span data-stu-id="f9603-108">After installing Windows 7 and IIS, when I attempt to browse to a WCF service I get the following error message: HTTP Error 404.3 – Not Found</span></span>](#bkmk_0)  
  
     <span data-ttu-id="f9603-109">Ошибка HTTP 404.3 - не найдено. Запрашиваемая страница не может быть выдана из-за конфигурации расширения.</span><span class="sxs-lookup"><span data-stu-id="f9603-109">HTTP Error 404.3 – Not FoundThe page you are requesting cannot be served because of the extension configuration.</span></span> <span data-ttu-id="f9603-110">Если страница - скрипт, добавьте обработчик.</span><span class="sxs-lookup"><span data-stu-id="f9603-110">If the page is a script, add a handler.</span></span> <span data-ttu-id="f9603-111">Если файл должен загружаться, добавьте MIME-сопоставление.</span><span class="sxs-lookup"><span data-stu-id="f9603-111">If the file should be downloaded, add a MIME map.</span></span> <span data-ttu-id="f9603-112">Подробное описание ошибки InformationModule StaticFileModule.</span><span class="sxs-lookup"><span data-stu-id="f9603-112">Detailed Error InformationModule StaticFileModule.</span></span>  
  
2. [<span data-ttu-id="f9603-113">Иногда я получаю MessageSecurityException на второй запрос, если мой клиент простаивает на некоторое время после первого запроса. Что происходит?</span><span class="sxs-lookup"><span data-stu-id="f9603-113">Sometimes I receive a MessageSecurityException on the second request if my client is idle for a while after the first request. What is happening?</span></span>](#BKMK_q1)  
  
3. [<span data-ttu-id="f9603-114">Мой сервис начинает отказываться от новых клиентов после того, как около 10 клиентов взаимодействуют с ним. Что происходит?</span><span class="sxs-lookup"><span data-stu-id="f9603-114">My service starts to reject new clients after about 10 clients are interacting with it. What is happening?</span></span>](#BKMK_q2)  
  
4. [<span data-ttu-id="f9603-115">Можно ли загружать конфигурацию службы из расположения, отличного от файла конфигурации приложения WCF?</span><span class="sxs-lookup"><span data-stu-id="f9603-115">Can I load my service configuration from somewhere other than the WCF application’s configuration file?</span></span>](#BKMK_q3)  
  
5. [<span data-ttu-id="f9603-116">Мой сервис и клиент отлично работают, но я не могу заставить их работать, когда клиент находится на другом компьютере? Что происходит?</span><span class="sxs-lookup"><span data-stu-id="f9603-116">My service and client work great, but I can’t get them to work when the client is on another computer? What’s happening?</span></span>](#BKMK_q4)  
  
6. [<span data-ttu-id="f9603-117">Когда я бросаю\<исключение FaultException>, где тип является исключением, я всегда получаю общий тип FaultException на клиенте, а не общий тип. Что происходит?</span><span class="sxs-lookup"><span data-stu-id="f9603-117">When I throw a FaultException\<Exception> where the type is an exception, I always receive a general FaultException type on the client and not the generic type. What’s happening?</span></span>](#BKMK_q5)  
  
7. [<span data-ttu-id="f9603-118">Кажется, что односторонние операции и операции по ответу запроса возвращаются примерно с той же скоростью, когда ответ не содержит данных. Что происходит?</span><span class="sxs-lookup"><span data-stu-id="f9603-118">It seems like one-way and request-reply operations return at roughly the same speed when the reply contains no data. What's happening?</span></span>](#BKMK_q6)  
  
8. [<span data-ttu-id="f9603-119">Я использую сертификат X.509 с моим сервисом, и я получаю System.Security.Cryptography.CryptographicException. Что происходит?</span><span class="sxs-lookup"><span data-stu-id="f9603-119">I’m using an X.509 certificate with my service and I get a System.Security.Cryptography.CryptographicException. What’s happening?</span></span>](#BKMK_q77)  
  
9. [<span data-ttu-id="f9603-120">Я изменил первый параметр операции с верхнего регистра на нижний регистр; Теперь мой клиент бросает исключение. Что происходит?</span><span class="sxs-lookup"><span data-stu-id="f9603-120">I changed the first parameter of an operation from uppercase to lowercase; now my client throws an exception. What's happening?</span></span>](#BKMK_q88)  
  
10. [<span data-ttu-id="f9603-121">Я использую один из моих инструментов трассировки, и я получаю EndpointNotFoundException. Что происходит?</span><span class="sxs-lookup"><span data-stu-id="f9603-121">I’m using one of my tracing tools and I get an EndpointNotFoundException. What’s happening?</span></span>](#BKMK_q99)  
  
11. [<span data-ttu-id="f9603-122">При вызове веб-приложения HTTP WCF из приложения службы протокола SOAP WCF возвращается следующая ошибка: «405 Метод запрещен»</span><span class="sxs-lookup"><span data-stu-id="f9603-122">When calling a WCF Web HTTP application from a WCF SOAP application the service returns the following error: 405 Method Not Allowed</span></span>](#BK_MK99)  
  
 [<span data-ttu-id="f9603-123">Какой базовый адрес? Как это связано с адресом конечных точек?</span><span class="sxs-lookup"><span data-stu-id="f9603-123">What is the base address? How does it relate to an endpoint address?</span></span>](#BKMK_q10)  
  
<a name="bkmk_0"></a>
## <a name="after-installing-windows-7-and-iis-when-i-attempt-to-browse-to-a-wcf-service-i-get-the-following-error-message-http-error-4043--not-found"></a><span data-ttu-id="f9603-124">После установки Windows 7 и IIS при попытке перейти к службе WCF выдается следующее сообщение об ошибке: «Ошибка HTTP 404.3 - не найдено»</span><span class="sxs-lookup"><span data-stu-id="f9603-124">After installing Windows 7 and IIS, when I attempt to browse to a WCF service I get the following error message: HTTP Error 404.3 – Not Found</span></span>  
 <span data-ttu-id="f9603-125">Полное сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="f9603-125">The full error message is:</span></span>  
  
 <span data-ttu-id="f9603-126">Ошибка HTTP 404.3 - не найдено. Запрашиваемая страница не может быть выдана из-за конфигурации расширения.</span><span class="sxs-lookup"><span data-stu-id="f9603-126">HTTP Error 404.3 – Not FoundThe page you are requesting cannot be served because of the extension configuration.</span></span> <span data-ttu-id="f9603-127">Если страница - скрипт, добавьте обработчик.</span><span class="sxs-lookup"><span data-stu-id="f9603-127">If the page is a script, add a handler.</span></span> <span data-ttu-id="f9603-128">Если файл должен загружаться, добавьте MIME-сопоставление.</span><span class="sxs-lookup"><span data-stu-id="f9603-128">If the file should be downloaded, add a MIME map.</span></span> <span data-ttu-id="f9603-129">Подробное описание ошибки InformationModule StaticFileModule.</span><span class="sxs-lookup"><span data-stu-id="f9603-129">Detailed Error InformationModule StaticFileModule.</span></span>  
  
 <span data-ttu-id="f9603-130">Это сообщение об ошибке происходит, когда "Windows Communication Foundation HTTP Activation" явно не установлена в панели управления.</span><span class="sxs-lookup"><span data-stu-id="f9603-130">This error message occurs when "Windows Communication Foundation HTTP Activation" is not explicitly set in the Control Panel.</span></span> <span data-ttu-id="f9603-131">Чтобы установить это перейдите на панель управления, нажмите Программы в нижнем левом углу окна.</span><span class="sxs-lookup"><span data-stu-id="f9603-131">To set this go to the Control Panel, click Programs in the lower left-hand corner of the window.</span></span> <span data-ttu-id="f9603-132">Установите переключатель «Включение компонентов Windows».</span><span class="sxs-lookup"><span data-stu-id="f9603-132">Click Turn Windows features on or off.</span></span> <span data-ttu-id="f9603-133">Разверните элемент Microsoft .NET Framework 3.5.1 и выберите «Активация Windows Communication Foundation по HTTP».</span><span class="sxs-lookup"><span data-stu-id="f9603-133">Expand Microsoft .NET Framework 3.5.1 and select Windows Communication Foundation HTTP Activation.</span></span>  
  
<a name="BKMK_q1"></a>
## <a name="sometimes-i-receive-a-messagesecurityexception-on-the-second-request-if-my-client-is-idle-for-a-while-after-the-first-request-what-is-happening"></a><span data-ttu-id="f9603-134">Иногда при втором запросе возникает исключение MessageSecurityException, если клиент бездействует некоторое время после первого запроса.</span><span class="sxs-lookup"><span data-stu-id="f9603-134">Sometimes I receive a MessageSecurityException on the second request if my client is idle for a while after the first request.</span></span> <span data-ttu-id="f9603-135">Что происходит?</span><span class="sxs-lookup"><span data-stu-id="f9603-135">What is happening?</span></span>  
 <span data-ttu-id="f9603-136">Сбой второго запроса может произойти по двум причинам: (1) истекло время ожидания сеанса или (2) перезапущен веб-сервер, на котором размещена служба.</span><span class="sxs-lookup"><span data-stu-id="f9603-136">The second request can fail primarily for two reasons: (1) the session has timed out or (2) the Web server that is hosting the service is recycled.</span></span> <span data-ttu-id="f9603-137">В первом случае сеанс действителен до тех пор, пока служба не выйдет из строя. Если служба не получает запрос от клиента в течение периода времени, указанного в привязке службы (),<xref:System.ServiceModel.Channels.Binding.ReceiveTimeout%2A>служба прекращает сеанс безопасности.</span><span class="sxs-lookup"><span data-stu-id="f9603-137">In the first case, the session is valid until the service times out. When the service does not receive a request from the client within the period of time specified in the service's binding (<xref:System.ServiceModel.Channels.Binding.ReceiveTimeout%2A>), the service terminates the security session.</span></span> <span data-ttu-id="f9603-138">Последующие сообщения клиента приводят к исключению <xref:System.ServiceModel.Security.MessageSecurityException>.</span><span class="sxs-lookup"><span data-stu-id="f9603-138">Subsequent client messages result in the <xref:System.ServiceModel.Security.MessageSecurityException>.</span></span> <span data-ttu-id="f9603-139">Клиент должен повторно установить безопасный сеанс со службой, чтобы отправлять будущие сообщения, или использовать маркер контекста безопасности с отслеживанием состояния.</span><span class="sxs-lookup"><span data-stu-id="f9603-139">The client must re-establish a secure session with the service to send future messages or use a stateful security context token.</span></span> <span data-ttu-id="f9603-140">Токены контекста безопасности с отслеживанием состояния также позволяют защитить сеанс во время перезапуска веб-сервера.</span><span class="sxs-lookup"><span data-stu-id="f9603-140">Stateful security context tokens also allow a secure session to survive a Web server being recycled.</span></span> <span data-ttu-id="f9603-141">Для получения дополнительной информации об использовании маркеров безопасного контекста состояния в безопасном сеансе [см.](./feature-details/how-to-create-a-security-context-token-for-a-secure-session.md)</span><span class="sxs-lookup"><span data-stu-id="f9603-141">For more information about using stateful secure context tokens in a secure session, see [How to: Create a Security Context Token for a Secure Session](./feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).</span></span> <span data-ttu-id="f9603-142">Кроме того, можно отключить безопасные сеансы.</span><span class="sxs-lookup"><span data-stu-id="f9603-142">Alternatively, you can disable secure sessions.</span></span> <span data-ttu-id="f9603-143">При использовании [ \<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) связывания `establishSecurityContext` можно `false` настроить свойство для отсутсвия безопасных сеансов.</span><span class="sxs-lookup"><span data-stu-id="f9603-143">When you use the [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) binding, you can set the `establishSecurityContext` property to `false` to disable secure sessions.</span></span> <span data-ttu-id="f9603-144">Чтобы отключить безопасные сеансы для других привязок, необходимо создать пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="f9603-144">To disable secure sessions for other bindings, you must create a custom binding.</span></span> <span data-ttu-id="f9603-145">Подробные сведения о создании пользовательской привязки см. в разделе [How to: Create a Custom Binding Using the SecurityBindingElement](./feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="f9603-145">For details about creating a custom binding, see [How to: Create a Custom Binding Using the SecurityBindingElement](./feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span> <span data-ttu-id="f9603-146">Перед применением этих параметров необходимо разобраться с требованиями безопасности приложения.</span><span class="sxs-lookup"><span data-stu-id="f9603-146">Before you apply any of these options, you must understand your application's security requirements.</span></span>  
  
<a name="BKMK_q2"></a>
## <a name="my-service-starts-to-reject-new-clients-after-about-10-clients-are-interacting-with-it-what-is-happening"></a><span data-ttu-id="f9603-147">Когда со службой взаимодействует около 10 клиентов, она отклоняет подключение новых клиентов.</span><span class="sxs-lookup"><span data-stu-id="f9603-147">My service starts to reject new clients after about 10 clients are interacting with it.</span></span> <span data-ttu-id="f9603-148">Что происходит?</span><span class="sxs-lookup"><span data-stu-id="f9603-148">What is happening?</span></span>  
 <span data-ttu-id="f9603-149">По умолчанию службы поддерживают не более 10 параллельных сеансов.</span><span class="sxs-lookup"><span data-stu-id="f9603-149">By default, services can have only 10 concurrent sessions.</span></span> <span data-ttu-id="f9603-150">Поэтому при использовании в привязках службы сеансов, служба принимает подключения новых клиентов до достижения этого числа. После этого служба отклоняет подключения новых клиентов, пока не будет закрыт один из текущих сеансов.</span><span class="sxs-lookup"><span data-stu-id="f9603-150">Therefore, if the service bindings use sessions, the service accepts new client connections until it reaches that number, after which it refuses new client connections until one of the current sessions ends.</span></span> <span data-ttu-id="f9603-151">Поддержку большего количества клиентов можно обеспечить несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="f9603-151">You can support more clients in a number of ways.</span></span> <span data-ttu-id="f9603-152">Если для службы не требуются сеансы, не используйте сеансовую привязку.</span><span class="sxs-lookup"><span data-stu-id="f9603-152">If your service does not require sessions, do not use a sessionful binding.</span></span> <span data-ttu-id="f9603-153">(Для получения дополнительной [информации см.](using-sessions.md) Другим вариантом является увеличение лимита сеанса <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentSessions%2A> путем изменения значения свойства на число, соответствующее вашим обстоятельствам.</span><span class="sxs-lookup"><span data-stu-id="f9603-153">(For more information, see [Using Sessions](using-sessions.md).) Another option is to increase the session limit by changing the value of the <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentSessions%2A> property to the number appropriate to your circumstance.</span></span>  
  
<a name="BKMK_q3"></a>
## <a name="can-i-load-my-service-configuration-from-somewhere-other-than-the-wcf-applications-configuration-file"></a><span data-ttu-id="f9603-154">Можно ли загружать конфигурацию службы из расположения, отличного от файла конфигурации приложения WCF?</span><span class="sxs-lookup"><span data-stu-id="f9603-154">Can I load my service configuration from somewhere other than the WCF application’s configuration file?</span></span>  
 <span data-ttu-id="f9603-155">Да, но необходимо создать пользовательский класс <xref:System.ServiceModel.ServiceHost> , переопределяющий метод <xref:System.ServiceModel.ServiceHostBase.ApplyConfiguration%2A> .</span><span class="sxs-lookup"><span data-stu-id="f9603-155">Yes, however, you have to create a custom <xref:System.ServiceModel.ServiceHost> class that overrides the <xref:System.ServiceModel.ServiceHostBase.ApplyConfiguration%2A> method.</span></span> <span data-ttu-id="f9603-156">Внутри этого метода можно вызвать базовый класс, чтобы сначала загрузить конфигурацию (если дополнительно требуется загрузить сведения о стандартной конфигурации), но можно также полностью заменить систему загрузки конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f9603-156">Inside that method, you can call the base to load configuration first (if you want to load the standard configuration information as well) but you can also entirely replace the configuration loading system.</span></span> <span data-ttu-id="f9603-157">Если требуется загрузить конфигурацию из файла конфигурации, который отличается от файла конфигурации приложения, необходимо разобрать файл конфигурации самостоятельно и загрузить конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="f9603-157">If you want to load configuration from a configuration file that is different from the application configuration file, you must parse the configuration file yourself and load the configuration.</span></span>  
  
 <span data-ttu-id="f9603-158">В следующем примере кода показано, как переопределить метод <xref:System.ServiceModel.ServiceHostBase.ApplyConfiguration%2A> и напрямую настроить конечную точку.</span><span class="sxs-lookup"><span data-stu-id="f9603-158">The following code example shows how to override the <xref:System.ServiceModel.ServiceHostBase.ApplyConfiguration%2A> method and directly configure an endpoint.</span></span>  
  
```csharp
public class MyServiceHost : ServiceHost  
{  
    public MyServiceHost(Type serviceType, params Uri[] baseAddresses)
      : base(serviceType, baseAddresses)  
    {
        Console.WriteLine("MyServiceHost Constructor");
    }  
  
    protected override void ApplyConfiguration()  
    {  
        string straddress = GetAddress();  
        Uri address = new Uri(straddress);  
        Binding binding = GetBinding();  
        base.AddServiceEndpoint(typeof(IData), binding, address);  
    }  
  
    string GetAddress()  
    {
        return "http://MyMachine:7777/MyEndpointAddress/";
    }  
  
    Binding GetBinding()  
    {  
        WSHttpBinding binding = new WSHttpBinding();  
        binding.Security.Mode = SecurityMode.None;  
        return binding;  
    }  
}  
```  
  
<a name="BKMK_q4"></a>
## <a name="my-service-and-client-work-great-but-i-cant-get-them-to-work-when-the-client-is-on-another-computer-whats-happening"></a><span data-ttu-id="f9603-159">Служба и клиент работают нормально, но их не удается запустить, если клиент находится на другом компьютере.</span><span class="sxs-lookup"><span data-stu-id="f9603-159">My service and client work great, but I can’t get them to work when the client is on another computer?</span></span> <span data-ttu-id="f9603-160">В чем причина?</span><span class="sxs-lookup"><span data-stu-id="f9603-160">What’s happening?</span></span>  
 <span data-ttu-id="f9603-161">В зависимости от исключения возможны следующие причины.</span><span class="sxs-lookup"><span data-stu-id="f9603-161">Depending upon the exception, there may be several issues:</span></span>  
  
- <span data-ttu-id="f9603-162">Возможно, потребуется использовать для адреса конечной точки клиента имя узла, а не "localhost".</span><span class="sxs-lookup"><span data-stu-id="f9603-162">You might need to change the client endpoint addresses to the host name and not "localhost".</span></span>  
  
- <span data-ttu-id="f9603-163">Возможно, для приложения потребуется открыть порт.</span><span class="sxs-lookup"><span data-stu-id="f9603-163">You might need to open the port to the application.</span></span> <span data-ttu-id="f9603-164">Дополнительные сведения см. в разделе [Firewall Instructions](./samples/firewall-instructions.md) примеров SDK.</span><span class="sxs-lookup"><span data-stu-id="f9603-164">For details, see [Firewall Instructions](./samples/firewall-instructions.md) from the SDK samples.</span></span>  
  
- <span data-ttu-id="f9603-165">Для других возможных проблем смотрите тему примеров [Запуск образцов Windows Communication Foundation Образцы](./samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f9603-165">For other possible issues, see the samples topic [Running the Windows Communication Foundation Samples](./samples/running-the-samples.md).</span></span>  
  
- <span data-ttu-id="f9603-166">Если в клиенте используются учетные данные Windows и создается исключение <xref:System.ServiceModel.Security.SecurityNegotiationException>, настройте Kerberos, как указано ниже.</span><span class="sxs-lookup"><span data-stu-id="f9603-166">If your client is using Windows credentials and the exception is a <xref:System.ServiceModel.Security.SecurityNegotiationException>, configure Kerberos as follows.</span></span>  
  
    1. <span data-ttu-id="f9603-167">Добавьте учетные данные идентификации в элемент конечной точки в файле конфигурации клиента App.config.</span><span class="sxs-lookup"><span data-stu-id="f9603-167">Add the identity credentials to the endpoint element in the client’s App.config file:</span></span>  
  
        ```xml
        <endpoint
          address="http://MyServer:8000/MyService/"
          binding="wsHttpBinding"
          bindingConfiguration="WSHttpBinding_IServiceExample"
          contract="IServiceExample"
          behaviorConfiguration="ClientCredBehavior"
          name="WSHttpBinding_IServiceExample">  
          <identity>  
            <userPrincipalName value="name@corp.contoso.com"/>  
          </identity>  
        </endpoint>  
        ```  
  
    2. <span data-ttu-id="f9603-168">Для этого запустите службу от имени учетной записи System или NetworkService.</span><span class="sxs-lookup"><span data-stu-id="f9603-168">Run the self-hosted service under the System or NetworkService account.</span></span> <span data-ttu-id="f9603-169">Чтобы создать командное окно в учетной записи System, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="f9603-169">You can run this command to create a command window under the System account:</span></span>  
  
        ```console
        at 12:36 /interactive "cmd.exe"  
        ```  
  
    3. <span data-ttu-id="f9603-170">Разместите службу в службах IIS, которые по умолчанию используют учетную запись имени участника службы (SPN).</span><span class="sxs-lookup"><span data-stu-id="f9603-170">Host the service under Internet Information Services (IIS), which, by default, uses the service principal name (SPN) account.</span></span>  
  
    4. <span data-ttu-id="f9603-171">Зарегистрируйте в домене новое имя участника службы (SPN) с помощью программы SetSPN.</span><span class="sxs-lookup"><span data-stu-id="f9603-171">Register a new SPN with the domain using SetSPN.</span></span> <span data-ttu-id="f9603-172">Для этого необходимо быть администратором домена.</span><span class="sxs-lookup"><span data-stu-id="f9603-172">You need to be a domain administrator in order to do this.</span></span>  
  
 <span data-ttu-id="f9603-173">Для получения дополнительной информации о [Security Concepts Used in WCF](./feature-details/security-concepts-used-in-wcf.md) протоколе Kerberos см.</span><span class="sxs-lookup"><span data-stu-id="f9603-173">For more information about the Kerberos protocol, see [Security Concepts Used in WCF](./feature-details/security-concepts-used-in-wcf.md) and:</span></span>  
  
- [<span data-ttu-id="f9603-174">Отладка ошибок проверки подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="f9603-174">Debugging Windows Authentication Errors</span></span>](./feature-details/debugging-windows-authentication-errors.md)  
  
- <span data-ttu-id="f9603-175">[Регистрация имен субъектов-служб Kerberos в файле Http.sys](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms178119(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="f9603-175">[Registering Kerberos Service Principal Names by Using Http.sys](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms178119(v=sql.105))</span></span>  
  
- <span data-ttu-id="f9603-176">[Сведения о Kerberos](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/bb742516(v%3dtechnet.10))</span><span class="sxs-lookup"><span data-stu-id="f9603-176">[Kerberos Explained](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/bb742516(v%3dtechnet.10))</span></span>  
  
<a name="BKMK_q5"></a>
## <a name="when-i-throw-a-faultexceptionexception-where-the-type-is-an-exception-i-always-receive-a-general-faultexception-type-on-the-client-and-not-the-generic-type-whats-happening"></a><span data-ttu-id="f9603-177">Когда я бросаю\<исключение FaultException>, где тип является исключением, я всегда получаю общий тип FaultException на клиенте, а не общий тип.</span><span class="sxs-lookup"><span data-stu-id="f9603-177">When I throw a FaultException\<Exception> where the type is an exception, I always receive a general FaultException type on the client and not the generic type.</span></span> <span data-ttu-id="f9603-178">В чем причина?</span><span class="sxs-lookup"><span data-stu-id="f9603-178">What’s happening?</span></span>  
 <span data-ttu-id="f9603-179">Настоятельно рекомендуется создать свой собственный пользовательский тип данных об ошибке и объявить его в качестве типа сведений в контракте сбоя.</span><span class="sxs-lookup"><span data-stu-id="f9603-179">It is highly recommended that you create your own custom error data type and declare that as the detail type in your fault contract.</span></span> <span data-ttu-id="f9603-180">Это необходимо, так как при использовании типов исключений, предоставляемых системой, могут возникнуть следующие проблемы.</span><span class="sxs-lookup"><span data-stu-id="f9603-180">The reason is that using system-provided exception types:</span></span>  
  
- <span data-ttu-id="f9603-181">Создается зависимость типов, которая не дает возможности воспользоваться одним из главных преимуществ приложений, ориентированных на службы.</span><span class="sxs-lookup"><span data-stu-id="f9603-181">Creates a type dependency that removes one of the biggest strengths of service-oriented applications.</span></span>  
  
- <span data-ttu-id="f9603-182">Не удается воспользоваться стандартной сериализацией исключений.</span><span class="sxs-lookup"><span data-stu-id="f9603-182">Cannot depend upon exceptions serializing in a standard way.</span></span> <span data-ttu-id="f9603-183">Некоторые из них, например <xref:System.Security.SecurityException>, могут вообще не сериализоваться.</span><span class="sxs-lookup"><span data-stu-id="f9603-183">Some—like <xref:System.Security.SecurityException>—may not be serializable at all.</span></span>  
  
- <span data-ttu-id="f9603-184">Внутренние сведения сериализации доступны для клиентов.</span><span class="sxs-lookup"><span data-stu-id="f9603-184">Exposes internal implementation details to clients.</span></span> <span data-ttu-id="f9603-185">Для получения дополнительной информации [см.](specifying-and-handling-faults-in-contracts-and-services.md)</span><span class="sxs-lookup"><span data-stu-id="f9603-185">For more information, see [Specifying and Handling Faults in Contracts and Services](specifying-and-handling-faults-in-contracts-and-services.md).</span></span>  
  
 <span data-ttu-id="f9603-186">Однако при отладке приложения можно сериализовать сведения об исключении и возвратить их клиенту с помощью класса <xref:System.ServiceModel.Description.ServiceDebugBehavior> .</span><span class="sxs-lookup"><span data-stu-id="f9603-186">If you are debugging an application, however, you can serialize exception information and return it to the client by using the <xref:System.ServiceModel.Description.ServiceDebugBehavior> class.</span></span>  
  
<a name="BKMK_q6"></a>
## <a name="it-seems-like-one-way-and-request-reply-operations-return-at-roughly-the-same-speed-when-the-reply-contains-no-data-whats-happening"></a><span data-ttu-id="f9603-187">Создается впечатление, что односторонние операции, а также операции запроса-ответа возвращаются примерно с той же скоростью, что и ответы без данных.</span><span class="sxs-lookup"><span data-stu-id="f9603-187">It seems like one-way and request-reply operations return at roughly the same speed when the reply contains no data.</span></span> <span data-ttu-id="f9603-188">В чем причина?</span><span class="sxs-lookup"><span data-stu-id="f9603-188">What's happening?</span></span>  
 <span data-ttu-id="f9603-189">Если указывается, что операция является односторонней, это лишь означает, что контракт операции принимает входящее сообщение и не возвращает выходное сообщение.</span><span class="sxs-lookup"><span data-stu-id="f9603-189">Specifying that an operation is one way means only that the operation contract accepts an input message and does not return an output message.</span></span> <span data-ttu-id="f9603-190">В WCF все вызовы клиента возвращаются, когда исходящие данные были записаны на провод или выбрасывается исключение.</span><span class="sxs-lookup"><span data-stu-id="f9603-190">In WCF, all client invocations return when the outbound data has been written to the wire or an exception is thrown.</span></span> <span data-ttu-id="f9603-191">Односторонние операции выполняются таким же образом, и они могут создавать исключение, если не удается обнаружить службу, или заблокировать выполнение, если служба не готова к приему данных из сети.</span><span class="sxs-lookup"><span data-stu-id="f9603-191">One-way operations work the same way, and they can throw if the service cannot be located or block if the service is not prepared to accept the data from the network.</span></span> <span data-ttu-id="f9603-192">Как правило, в WCF это приводит к тому, что односторонние вызовы возвращаются клиенту быстрее, чем ответ запроса; но любое условие, замедлит отправку исходящих данных по сети, замедляет односторонние операции, а также операции по ответу запроса.</span><span class="sxs-lookup"><span data-stu-id="f9603-192">Typically in WCF, this results in one-way calls returning to the client more quickly than request-reply; but any condition that slows the sending of the outbound data over the network slows one-way operations as well as request-reply operations.</span></span> <span data-ttu-id="f9603-193">Для получения дополнительной информации [Accessing Services Using a WCF Client](./feature-details/accessing-services-using-a-client.md)см. [One-Way Services](./feature-details/one-way-services.md)</span><span class="sxs-lookup"><span data-stu-id="f9603-193">For more information, see [One-Way Services](./feature-details/one-way-services.md) and [Accessing Services Using a WCF Client](./feature-details/accessing-services-using-a-client.md).</span></span>  
  
<a name="BKMK_q77"></a>
## <a name="im-using-an-x509-certificate-with-my-service-and-i-get-a-systemsecuritycryptographycryptographicexception-whats-happening"></a><span data-ttu-id="f9603-194">В службе используется сертификат X.509, при этом получается исключение System.Security.Cryptography.CryptographicException.</span><span class="sxs-lookup"><span data-stu-id="f9603-194">I’m using an X.509 certificate with my service and I get a System.Security.Cryptography.CryptographicException.</span></span> <span data-ttu-id="f9603-195">В чем причина?</span><span class="sxs-lookup"><span data-stu-id="f9603-195">What’s happening?</span></span>  
 <span data-ttu-id="f9603-196">Обычно это происходит после изменения учетной записи пользователя, в которой выполняется рабочий процесс IIS.</span><span class="sxs-lookup"><span data-stu-id="f9603-196">This commonly occurs after changing the user account under which the IIS worker process runs.</span></span> <span data-ttu-id="f9603-197">Например, в Windows XP, если вы измените учетную запись пользователя по умолчанию, которую Aspnet_wp.exe выполняется с ASPNET на пользовательскую учетную запись пользователя, вы можете увидеть эту ошибку.</span><span class="sxs-lookup"><span data-stu-id="f9603-197">For example, in Windows XP, if you change the default user account that the Aspnet_wp.exe runs under from ASPNET to a custom user account, you may see this error.</span></span> <span data-ttu-id="f9603-198">Если используется закрытый ключ, его процесс должен иметь разрешение для доступа к файлу с этим ключом.</span><span class="sxs-lookup"><span data-stu-id="f9603-198">If using a private key, the process that uses it will need to have permissions to access the file storing that key.</span></span>  
  
 <span data-ttu-id="f9603-199">В этом случае необходимо предоставить учетной записи процесса права доступа для чтения файла с закрытым ключом.</span><span class="sxs-lookup"><span data-stu-id="f9603-199">If this is the case, you must give read access privileges to the process's account for the file containing the private key.</span></span> <span data-ttu-id="f9603-200">Например, если рабочий процесс IIS выполняется в учетной записи Бориса, ему необходимо предоставить права доступа для чтения файла, содержащего закрытый ключ.</span><span class="sxs-lookup"><span data-stu-id="f9603-200">For example, if the IIS worker process is running under the Bob account, then you will need to give Bob read access to the file containing the private key.</span></span>  
  
 <span data-ttu-id="f9603-201">Для получения дополнительной информации о том, как дать правильный доступ к учетной записи пользователя к файлу, который содержит закрытый ключ для конкретного сертификата X.509, [см.](./feature-details/how-to-make-x-509-certificates-accessible-to-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="f9603-201">For more information about how to give the correct user account access to the file that contains the private key for a specific X.509 certificate, see [How to: Make X.509 Certificates Accessible to WCF](./feature-details/how-to-make-x-509-certificates-accessible-to-wcf.md).</span></span>  
  
<a name="BKMK_q88"></a>
## <a name="i-changed-the-first-parameter-of-an-operation-from-uppercase-to-lowercase-now-my-client-throws-an-exception-whats-happening"></a><span data-ttu-id="f9603-202">В имени первого параметра операции прописные буквы были заменены на строчные, и теперь в клиенте выдается исключение.</span><span class="sxs-lookup"><span data-stu-id="f9603-202">I changed the first parameter of an operation from uppercase to lowercase; now my client throws an exception.</span></span> <span data-ttu-id="f9603-203">В чем причина?</span><span class="sxs-lookup"><span data-stu-id="f9603-203">What's happening?</span></span>  
 <span data-ttu-id="f9603-204">Значения имен параметров в подписи операции являются частью договора и чувствительны к случаям.</span><span class="sxs-lookup"><span data-stu-id="f9603-204">The values of the parameter names in the operation signature are part of the contract and are case-sensitive.</span></span> <span data-ttu-id="f9603-205">Используйте атрибут <xref:System.ServiceModel.MessageParameterAttribute?displayProperty=nameWithType> , чтобы различать имя локального параметра и метаданные, описывающие операцию для клиентских приложений.</span><span class="sxs-lookup"><span data-stu-id="f9603-205">Use the <xref:System.ServiceModel.MessageParameterAttribute?displayProperty=nameWithType> attribute when you need to distinguish between the local parameter name and the metadata that describes the operation for client applications.</span></span>  
  
<a name="BKMK_q99"></a>
## <a name="im-using-one-of-my-tracing-tools-and-i-get-an-endpointnotfoundexception-whats-happening"></a><span data-ttu-id="f9603-206">При использовании одного из средств трассировки получено исключение EndpointNotFoundException.</span><span class="sxs-lookup"><span data-stu-id="f9603-206">I’m using one of my tracing tools and I get an EndpointNotFoundException.</span></span> <span data-ttu-id="f9603-207">В чем причина?</span><span class="sxs-lookup"><span data-stu-id="f9603-207">What’s happening?</span></span>  
 <span data-ttu-id="f9603-208">Если вы используете инструмент отслеживания, который не является системным механизмом <xref:System.ServiceModel.EndpointNotFoundException> отслеживания WCF, и вы получаете, <xref:System.ServiceModel.Description.ClientViaBehavior> что указывает на несоответствие фильтра адреса, вам нужно использовать класс, чтобы направить сообщения в утилиту отслеживания и иметь утилиту перенаправить эти сообщения на адрес службы.</span><span class="sxs-lookup"><span data-stu-id="f9603-208">If you are using a tracing tool that is not the system-provided WCF tracing mechanism and you receive an <xref:System.ServiceModel.EndpointNotFoundException> that indicates that there was an address filter mismatch, you need to use the <xref:System.ServiceModel.Description.ClientViaBehavior> class to direct the messages to the tracing utility and have the utility redirect those messages to the service address.</span></span> <span data-ttu-id="f9603-209">Класс <xref:System.ServiceModel.Description.ClientViaBehavior> изменяет заголовок адресации `Via` , чтобы задать следующий сетевой адрес отдельно от конечного получателя, указанного заголовком адресации `To` .</span><span class="sxs-lookup"><span data-stu-id="f9603-209">The <xref:System.ServiceModel.Description.ClientViaBehavior> class alters the `Via` addressing header to specify the next network address separately from the ultimate receiver, indicated by the `To` addressing header.</span></span> <span data-ttu-id="f9603-210">Однако при этом не следует изменять адрес конечной точки, используемый для установки значения `To` .</span><span class="sxs-lookup"><span data-stu-id="f9603-210">When doing this, however, do not change the endpoint address, which is used to establish the `To` value.</span></span>  
  
 <span data-ttu-id="f9603-211">В следующем примере кода показан пример файла конфигурации клиента.</span><span class="sxs-lookup"><span data-stu-id="f9603-211">The following code example shows an example client configuration file.</span></span>  
  
```xml
<endpoint
  address="http://localhost:8000/MyServer/"  
  binding="wsHttpBinding"  
  bindingConfiguration="WSHttpBinding_IMyContract"  
  behaviorConfiguration="MyClient"
  contract="IMyContract"
  name="WSHttpBinding_IMyContract">  
</endpoint>  
<behaviors>  
  <endpointBehaviors>  
    <behavior name="MyClient">  
      <clientVia viaUri="http://localhost:8001/MyServer/"/>  
    </behavior>  
  </endpointBehaviors>  
</behaviors>  
```  
  
<a name="BKMK_q10"></a>
## <a name="what-is-the-base-address-how-does-it-relate-to-an-endpoint-address"></a><span data-ttu-id="f9603-212">Что такое базовый адрес?</span><span class="sxs-lookup"><span data-stu-id="f9603-212">What is the base address?</span></span> <span data-ttu-id="f9603-213">Как он связан с адресом конечной точки?</span><span class="sxs-lookup"><span data-stu-id="f9603-213">How does it relate to an endpoint address?</span></span>  
 <span data-ttu-id="f9603-214">Базовый адрес - это корневой адрес для класса <xref:System.ServiceModel.ServiceHost> .</span><span class="sxs-lookup"><span data-stu-id="f9603-214">A base address is the root address for a <xref:System.ServiceModel.ServiceHost> class.</span></span> <span data-ttu-id="f9603-215">По умолчанию, если в конфигурацию службы добавлен класс <xref:System.ServiceModel.Description.ServiceMetadataBehavior> , язык описания веб-служб (WSDL) для всех конечных точек, публикуемых узлом, извлекается из базового HTTP-адреса, относительного адреса, предоставленного поведением метаданных, а также "?wsdl".</span><span class="sxs-lookup"><span data-stu-id="f9603-215">By default, if you add a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> class into your service configuration, the Web Services Description Language (WSDL) for all endpoints the host publishes are retrieved from the HTTP base address, plus any relative address provided to the metadata behavior, plus "?wsdl".</span></span> <span data-ttu-id="f9603-216">Если вы знакомы с ASP.NET и IIS, базовый адрес эквивалентен виртуальному каталогу.</span><span class="sxs-lookup"><span data-stu-id="f9603-216">If you are familiar with ASP.NET and IIS, the base address is equivalent to the virtual directory.</span></span>  
  
## <a name="sharing-a-port-between-a-service-endpoint-and-a-mex-endpoint-using-the-nettcpbinding"></a><span data-ttu-id="f9603-217">Совместное использование порта конечными точками службы и обмена метаданными при помощи NetTcpBinding</span><span class="sxs-lookup"><span data-stu-id="f9603-217">Sharing a port between a service endpoint and a mex endpoint using the NetTcpBinding</span></span>  
 <span data-ttu-id="f9603-218">Если указать в качестве адреса базы службы net.tcp://MyServer:8080/MyService и добавить следующие конечные точки:</span><span class="sxs-lookup"><span data-stu-id="f9603-218">If you specify the base address for a service as net.tcp://MyServer:8080/MyService and add the following endpoints:</span></span>  
  
```xml  
<services>  
  <service name="Microsoft.Samples.NetTcp.CalculatorService">  
    <endpoint address="calcsvc" binding ="netTcpBinding" contract="Microsoft.Samples.NetTcp.ICalculator"/>  
    <endpoint address="mex" binding="mexTcpBinding" contract="IMetadataExchange" />  
  </service>  
</services>  
```  
  
 <span data-ttu-id="f9603-219">А если модифицировать один из параметров NetTcpBinding, как показано в следующем фрагменте конфигурации:</span><span class="sxs-lookup"><span data-stu-id="f9603-219">And if you modify one of the NetTcpBinding settings as shown in the following configuration snippet:</span></span>  
  
```xml  
<bindings>  
  <netTcpBinding>  
    <binding closeTimeout="00:01:00" openTimeout="00:01:00" receiveTimeout="00:10:00" sendTimeout="00:01:00" transactionFlow="false" transferMode="Buffered" transactionProtocol="OleTransactions" hostNameComparisonMode="StrongWildcard" listenBacklog="10" maxBufferPoolSize="524288" maxBufferSize="65536" maxConnections="11" maxReceivedMessageSize="65536">  
      <readerQuotas maxDepth="32" maxStringContentLength="8192" maxArrayLength="16384" maxBytesPerRead="4096" maxNameTableCharCount="16384"/>  
      <reliableSession ordered="true" inactivityTimeout="00:10:00" enabled="false"/>  
      <security mode="Transport">  
        <transport clientCredentialType="Windows" protectionLevel="EncryptAndSign"/>  
      </security>  
    </binding>  
  </netTcpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="f9603-220">Появится следующее сообщение об ошибке: Необработанное исключение: System.ServiceModel. AddressAlreadyInUseException. Уже есть прослушиватель на конечной точке IP 0.0.0.0:9000. Можно обойти эту ошибку, указав полный URL-адрес с другим портом для конечной точки MEX, как показано в следующем фрагменте конфигурации:</span><span class="sxs-lookup"><span data-stu-id="f9603-220">You will see an error like the following: Unhandled Exception: System.ServiceModel.AddressAlreadyInUseException: There is already a listener on IP endpoint 0.0.0.0:9000 You can work around this error by specifying a fully qualified URL with a different port for the MEX endpoint as shown in the following configuration snippet:</span></span>  
  
```xml
<services>  
  <service name="Microsoft.Samples.NetTcp.CalculatorService">  
    <endpoint address="calcsvc" binding ="netTcpBinding" contract="Microsoft.Samples.NetTcp.ICalculator"/>  
    <endpoint address="net.tcp://localhost:9001/servicemodelsamples/mex" binding="mexTcpBinding" contract="IMetadataExchange" />  
  </service>  
</services>  
```  
  
<a name="BK_MK99"></a>
## <a name="when-calling-a-wcf-web-http-application-from-a-wcf-soap-application-the-service-returns-the-following-error-405-method-not-allowed"></a><span data-ttu-id="f9603-221">При вызове веб-приложения HTTP WCF из приложения службы протокола SOAP WCF возвращается следующая ошибка: «405 Метод запрещен»</span><span class="sxs-lookup"><span data-stu-id="f9603-221">When calling a WCF Web HTTP application from a WCF SOAP application the service returns the following error: 405 Method Not Allowed</span></span>  
 <span data-ttu-id="f9603-222">Вызов приложения WCF Web HTTP (услуга, <xref:System.ServiceModel.WebHttpBinding> использующую и) <xref:System.ServiceModel.Description.WebHttpBehavior>из службы ``Unhandled Exception: System.ServiceModel.FaultException`1[System.ServiceModel.ExceptionDetail]: The remote server returned an unexpected response: (405) Method Not Allowed.`` WCF может генерировать следующее исключение: Это исключение происходит потому, что WCF перезаписывает исходящие <xref:System.ServiceModel.OperationContext> с входящими. <xref:System.ServiceModel.OperationContext></span><span class="sxs-lookup"><span data-stu-id="f9603-222">Calling a WCF Web HTTP application (a service that uses the <xref:System.ServiceModel.WebHttpBinding> and <xref:System.ServiceModel.Description.WebHttpBehavior>) from a WCF service may generate the following exception: ``Unhandled Exception: System.ServiceModel.FaultException`1[System.ServiceModel.ExceptionDetail]: The remote server returned an unexpected response: (405) Method Not Allowed.`` This exception occurs because WCF overwrites the outgoing <xref:System.ServiceModel.OperationContext> with the incoming <xref:System.ServiceModel.OperationContext>.</span></span> <span data-ttu-id="f9603-223">Чтобы решить эту проблему, создайте <xref:System.ServiceModel.OperationContextScope> в рамках операции службы WCF Web HTTP.</span><span class="sxs-lookup"><span data-stu-id="f9603-223">To solve this problem, create an <xref:System.ServiceModel.OperationContextScope> within the WCF Web HTTP service operation.</span></span> <span data-ttu-id="f9603-224">Пример:</span><span class="sxs-lookup"><span data-stu-id="f9603-224">For example:</span></span>  
  
```csharp
public string Echo(string input)  
{  
    using (new OperationContextScope(this.InnerChannel))  
    {  
        return base.Channel.Echo(input);  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="f9603-225">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f9603-225">See also</span></span>

- [<span data-ttu-id="f9603-226">Отладка ошибок проверки подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="f9603-226">Debugging Windows Authentication Errors</span></span>](./feature-details/debugging-windows-authentication-errors.md)
