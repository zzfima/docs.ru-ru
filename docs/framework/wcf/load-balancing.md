---
title: Балансировка нагрузки
ms.date: 03/30/2017
helpviewer_keywords:
- load balancing [WCF]
ms.assetid: 148e0168-c08d-4886-8769-776d0953b80f
ms.openlocfilehash: a43546b9cbb95cd16c1d94372e786acd103ea0bb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61921957"
---
# <a name="load-balancing"></a><span data-ttu-id="211e9-102">Балансировка нагрузки</span><span class="sxs-lookup"><span data-stu-id="211e9-102">Load Balancing</span></span>
<span data-ttu-id="211e9-103">Один из способов повышения производительности приложений Windows Communication Foundation (WCF) является автоматическое масштабирование, развернув их на ферме серверов с балансировкой нагрузки.</span><span class="sxs-lookup"><span data-stu-id="211e9-103">One way to increase the capacity of Windows Communication Foundation (WCF) applications is to scale them out by deploying them into a load-balanced server farm.</span></span> <span data-ttu-id="211e9-104">Приложения WCF может быть сбалансирована с помощью стандартных методов балансировки нагрузки, включая программные подсистемы балансировки нагрузки, такие как Windows балансировки сетевой нагрузки, а также нагрузки на основе оборудования устройства для балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="211e9-104">WCF applications can be load balanced using standard load balancing techniques, including software load balancers such as Windows Network Load Balancing as well as hardware-based load balancing appliances.</span></span>  
  
 <span data-ttu-id="211e9-105">В следующих разделах рассматриваются рекомендации для приложений WCF, созданные с помощью различных привязок, предоставляемых системой балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="211e9-105">The following sections discuss considerations for load balancing WCF applications built using various system-provided bindings.</span></span>  
  
## <a name="load-balancing-with-the-basic-http-binding"></a><span data-ttu-id="211e9-106">Балансировка нагрузки с базовой привязкой HTTP</span><span class="sxs-lookup"><span data-stu-id="211e9-106">Load Balancing with the Basic HTTP Binding</span></span>  
 <span data-ttu-id="211e9-107">С точки зрения балансировки нагрузки, приложения WCF, которые взаимодействуют с использованием <xref:System.ServiceModel.BasicHttpBinding> ничем не отличаются от других стандартных типов HTTP сетевого трафика (статических HTML-содержимое, страницы ASP.NET или веб-служб ASMX).</span><span class="sxs-lookup"><span data-stu-id="211e9-107">From the perspective of load balancing, WCF applications that communicate using the <xref:System.ServiceModel.BasicHttpBinding> are no different than other common types of HTTP network traffic (static HTML content, ASP.NET pages, or ASMX Web Services).</span></span> <span data-ttu-id="211e9-108">Каналы WCF, использующие эту привязку не учитывают состояние и завершают подключения, когда закрывается канал.</span><span class="sxs-lookup"><span data-stu-id="211e9-108">WCF channels that use this binding are inherently stateless, and terminate their connections when the channel closes.</span></span> <span data-ttu-id="211e9-109">Поэтому привязка <xref:System.ServiceModel.BasicHttpBinding> хорошо работает с имеющимися методами балансировки нагрузки HTTP.</span><span class="sxs-lookup"><span data-stu-id="211e9-109">As such, the <xref:System.ServiceModel.BasicHttpBinding> works well with existing HTTP load balancing techniques.</span></span>  
  
 <span data-ttu-id="211e9-110">По умолчанию <xref:System.ServiceModel.BasicHttpBinding> отправляет заголовок HTTP подключения в сообщениях со значением `Keep-Alive`, которое позволяет клиентам устанавливать устойчивые подключения к службам, которые поддерживают их.</span><span class="sxs-lookup"><span data-stu-id="211e9-110">By default, the <xref:System.ServiceModel.BasicHttpBinding> sends a connection HTTP header in messages with a `Keep-Alive` value, which enables clients to establish persistent connections to the services that support them.</span></span> <span data-ttu-id="211e9-111">Такая конфигурация увеличивает пропускную способность, потому что ранее установленные подключения можно повторно использовать для отправки новых сообщений одному и тому же серверу.</span><span class="sxs-lookup"><span data-stu-id="211e9-111">This configuration offers enhanced throughput because previously established connections can be reused to send subsequent messages to the same server.</span></span> <span data-ttu-id="211e9-112">Однако повторное использований подключений может привести к тому, что клиенты будут слишком сильно связаны с конкретным сервером фермы балансировки нагрузки, что приведет к снижению эффективности балансировки нагрузки за счет равномерного распределения запросов между серверами фермы.</span><span class="sxs-lookup"><span data-stu-id="211e9-112">However, connection reuse may cause clients to become strongly associated to a specific server within the load-balanced farm, which reduces the effectiveness of round-robin load balancing.</span></span> <span data-ttu-id="211e9-113">Если такое поведение является нежелательным, можно на сервере отключить заголовок `Keep-Alive`, присвоив свойству <xref:System.ServiceModel.Channels.HttpTransportBindingElement.KeepAliveEnabled%2A> значение <xref:System.ServiceModel.Channels.CustomBinding> или пользовательскую привязку <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="211e9-113">If this behavior is undesirable, HTTP `Keep-Alive` can be disabled on the server using the <xref:System.ServiceModel.Channels.HttpTransportBindingElement.KeepAliveEnabled%2A> property with a <xref:System.ServiceModel.Channels.CustomBinding> or user-defined <xref:System.ServiceModel.Channels.Binding>.</span></span> <span data-ttu-id="211e9-114">В следующем примере показано, как добиться этого с помощью конфигурации.</span><span class="sxs-lookup"><span data-stu-id="211e9-114">The following example shows how to do this using configuration.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  
 <system.serviceModel>  
  <services>  
   <service   
     name="Microsoft.ServiceModel.Samples.CalculatorService"  
     behaviorConfiguration="CalculatorServiceBehavior">  
     <host>  
      <baseAddresses>  
       <add baseAddress="http://localhost:8000/servicemodelsamples/service"/>  
      </baseAddresses>  
     </host>  
    <!-- configure http endpoint, use base address provided by host  
         And the customBinding -->  
     <endpoint address=""  
           binding="customBinding"  
           bindingConfiguration="HttpBinding"   
           contract="Microsoft.ServiceModel.Samples.ICalculator" />  
   </service>  
  </services>  
  
  <bindings>  
    <customBinding>  
  
    <!-- Configure a CustomBinding that disables keepAliveEnabled-->  
      <binding name="HttpBinding" keepAliveEnabled="False"/>  
  
    </customBinding>  
  </bindings>  
 </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="211e9-115">При использовании упрощенной конфигурации, реализованной в [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)], можно обеспечить такой же режим работы за счет использования следующей упрощенной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="211e9-115">Using the simplified configuration introduced in [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)], the same behavior can be accomplished using the following simplified configuration.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
 <system.serviceModel>  
    <protocolMapping>  
      <add scheme="http" binding="customBinding" />  
    </protocolMapping>  
    <bindings>  
      <customBinding>  
  
      <!-- Configure a CustomBinding that disables keepAliveEnabled-->  
        <binding keepAliveEnabled="False"/>  
  
      </customBinding>  
    </bindings>  
 </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="211e9-116">Дополнительные сведения о конечных точках по умолчанию, привязках и режимах работы см. в разделах [Упрощенная конфигурация](../../../docs/framework/wcf/simplified-configuration.md) и [Упрощенная конфигурация служб WCF](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="211e9-116">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="load-balancing-with-the-wshttp-binding-and-the-wsdualhttp-binding"></a><span data-ttu-id="211e9-117">Балансировка нагрузки с привязкой WSHttp и привязкой WSDualHttp</span><span class="sxs-lookup"><span data-stu-id="211e9-117">Load Balancing with the WSHttp Binding and the WSDualHttp Binding</span></span>  
 <span data-ttu-id="211e9-118">Для привязок <xref:System.ServiceModel.WSHttpBinding> и <xref:System.ServiceModel.WSDualHttpBinding> можно обеспечить балансировку нагрузки, используя для этого методы балансировки нагрузки HTTP, реализуемые путем внесения некоторых изменений в конфигурацию привязки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="211e9-118">Both the <xref:System.ServiceModel.WSHttpBinding> and the <xref:System.ServiceModel.WSDualHttpBinding> can be load balanced using HTTP load balancing techniques provided several modifications are made to the default binding configuration.</span></span>  
  
- <span data-ttu-id="211e9-119">Отключите установление контекста безопасности. Для этого присвойте свойству <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> привязки <xref:System.ServiceModel.WSHttpBinding> значение `false`.</span><span class="sxs-lookup"><span data-stu-id="211e9-119">Turn off Security Context Establishment: this can be accomplished by the setting the <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> property on the <xref:System.ServiceModel.WSHttpBinding> to `false`.</span></span> <span data-ttu-id="211e9-120">Кроме того, семинары, посвященные безопасности, если они необходимы имеется возможность использовать сеансы безопасности с отслеживанием состояния, как описано в разделе [безопасные сеансы](../../../docs/framework/wcf/feature-details/secure-sessions.md) раздела.</span><span class="sxs-lookup"><span data-stu-id="211e9-120">Alternatively, if security sessions are required, it is possible to use stateful security sessions as described in the [Secure Sessions](../../../docs/framework/wcf/feature-details/secure-sessions.md) topic.</span></span> <span data-ttu-id="211e9-121">Сеансы безопасности с отслеживанием состояния позволяют службе не учитывать состояние, потому что все сведения о состоянии сеанса безопасности передаются с каждым запросом в рамках маркера безопасности защиты.</span><span class="sxs-lookup"><span data-stu-id="211e9-121">Stateful security sessions enable the service to remain stateless as all of the state for the security session is transmitted with each request as a part of the protection security token.</span></span> <span data-ttu-id="211e9-122">Обратите внимание, что для включения сеансов безопасности с отслеживанием состояния необходимо использовать привязку <xref:System.ServiceModel.Channels.CustomBinding> или определенную пользователем привязку <xref:System.ServiceModel.Channels.Binding>, поскольку необходимые параметры конфигурации не доступны в привязках <xref:System.ServiceModel.WSHttpBinding> и <xref:System.ServiceModel.WSDualHttpBinding>, которые предоставляются системой.</span><span class="sxs-lookup"><span data-stu-id="211e9-122">Note that to enable a stateful security session, it is necessary to use a <xref:System.ServiceModel.Channels.CustomBinding> or user-defined <xref:System.ServiceModel.Channels.Binding> as the necessary configuration settings are not exposed on <xref:System.ServiceModel.WSHttpBinding> and <xref:System.ServiceModel.WSDualHttpBinding> that are provided by the system.</span></span>  
  
- <span data-ttu-id="211e9-123">Не используйте надежные сеансы.</span><span class="sxs-lookup"><span data-stu-id="211e9-123">Do not use reliable sessions.</span></span> <span data-ttu-id="211e9-124">Эта возможность отключена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="211e9-124">This feature is off by default.</span></span>  
  
## <a name="load-balancing-the-nettcp-binding"></a><span data-ttu-id="211e9-125">Балансировка нагрузки привязки Net.TCP</span><span class="sxs-lookup"><span data-stu-id="211e9-125">Load Balancing the Net.TCP Binding</span></span>  
 <span data-ttu-id="211e9-126">Балансировку нагрузки привязки <xref:System.ServiceModel.NetTcpBinding> можно осуществлять с помощью методов балансировки нагрузки уровня протокола IP.</span><span class="sxs-lookup"><span data-stu-id="211e9-126">The <xref:System.ServiceModel.NetTcpBinding> can be load balanced using IP-layer load balancing techniques.</span></span> <span data-ttu-id="211e9-127">Однако для уменьшения времени задержки подключений привязка <xref:System.ServiceModel.NetTcpBinding> по умолчанию объединяет TCP-подключения.</span><span class="sxs-lookup"><span data-stu-id="211e9-127">However, the <xref:System.ServiceModel.NetTcpBinding> pools TCP connections by default to reduce connection latency.</span></span> <span data-ttu-id="211e9-128">Такая оптимизация противоречит базовому механизму балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="211e9-128">This is an optimization that interferes with the basic mechanism of load balancing.</span></span> <span data-ttu-id="211e9-129">Основным параметром конфигурации, используемым для оптимизации <xref:System.ServiceModel.NetTcpBinding>, является время ожидания аренды, которое входит в настройки пула подключений.</span><span class="sxs-lookup"><span data-stu-id="211e9-129">The primary configuration value for optimizing the <xref:System.ServiceModel.NetTcpBinding> is the lease timeout, which is part of the Connection Pool Settings.</span></span> <span data-ttu-id="211e9-130">В результате объединения клиентских подключений в пул эти подключения оказываются связанными с конкретными серверами фермы.</span><span class="sxs-lookup"><span data-stu-id="211e9-130">Connection pooling causes client connections to become associated to specific servers within the farm.</span></span> <span data-ttu-id="211e9-131">По мере увеличения времени существования таких подключений (этот показатель зависит от значения времени ожидания аренды) распределение нагрузки между различными серверами фермы становится несбалансированным.</span><span class="sxs-lookup"><span data-stu-id="211e9-131">As the lifetime of those connections increase (a factor controlled by the lease timeout setting), the load distribution across various servers in the farm becomes unbalanced.</span></span> <span data-ttu-id="211e9-132">В результате среднее время одного вызова увеличивается.</span><span class="sxs-lookup"><span data-stu-id="211e9-132">As a result the average call time increases.</span></span> <span data-ttu-id="211e9-133">Поэтому при использовании привязки <xref:System.ServiceModel.NetTcpBinding> с балансировкой нагрузки следует рассмотреть возможность уменьшения используемого привязкой времени ожидания аренды по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="211e9-133">So when using the <xref:System.ServiceModel.NetTcpBinding> in load-balanced scenarios, consider reducing the default lease timeout used by the binding.</span></span> <span data-ttu-id="211e9-134">Для начала использования балансировки нагрузки можно установить время ожидания аренды равным 30 секундам, хотя оптимальное значение будет зависеть от конкретного приложения.</span><span class="sxs-lookup"><span data-stu-id="211e9-134">A 30-second lease timeout is a reasonable starting point for load-balanced scenarios, although the optimal value is application-dependent.</span></span> <span data-ttu-id="211e9-135">Дополнительные сведения о времени ожидания аренды канала и других квотах транспорта см. в разделе [квоты транспорта](../../../docs/framework/wcf/feature-details/transport-quotas.md).</span><span class="sxs-lookup"><span data-stu-id="211e9-135">For more information about the channel lease timeout and other transport quotas, see [Transport Quotas](../../../docs/framework/wcf/feature-details/transport-quotas.md).</span></span>  
  
 <span data-ttu-id="211e9-136">Для достижения максимальной производительности при балансировке нагрузки рекомендуется использовать <xref:System.ServiceModel.NetTcpSecurity> (<xref:System.ServiceModel.SecurityMode.Transport> или <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>).</span><span class="sxs-lookup"><span data-stu-id="211e9-136">For best performance in load-balanced scenarios, consider using <xref:System.ServiceModel.NetTcpSecurity> (either <xref:System.ServiceModel.SecurityMode.Transport> or <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="211e9-137">См. также</span><span class="sxs-lookup"><span data-stu-id="211e9-137">See also</span></span>

- [<span data-ttu-id="211e9-138">Рекомендации по размещению в службах IIS</span><span class="sxs-lookup"><span data-stu-id="211e9-138">Internet Information Services Hosting Best Practices</span></span>](../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)
