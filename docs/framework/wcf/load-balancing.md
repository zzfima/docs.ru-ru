---
title: Балансировка нагрузки
ms.date: 03/30/2017
helpviewer_keywords:
- load balancing [WCF]
ms.assetid: 148e0168-c08d-4886-8769-776d0953b80f
ms.openlocfilehash: a444df2b05803ec54c5bd9030ce12209cfe9bd07
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183983"
---
# <a name="load-balancing"></a>Балансировка нагрузки
Одним из способов увеличения емкости приложений Windows Communication Foundation (WCF) является их масштабирование путем их развертывания в ферме серверов, сбалансированных с нагрузкой. Приложения WCF могут быть сбалансированы с помощью стандартных методов балансировки нагрузки, включая балансирумы нагрузки программного обеспечения, такие как балансировка нагрузки Windows Network, а также аппаратные приборы балансировки нагрузки.  
  
 В следующих разделах обсуждаются соображения для балансировки нагрузки wCF приложений, построенных с использованием различных системных привязок.  
  
## <a name="load-balancing-with-the-basic-http-binding"></a>Балансировка нагрузки с базовой привязкой HTTP  
 С точки зрения балансировки нагрузки приложения <xref:System.ServiceModel.BasicHttpBinding> WCF, которые общаются с использованием них, ничем не отличаются от других распространенных типов сетевого трафика HTTP (статическое HTML-контент, ASP.NET страниц ы или ASMX Web Services). Каналы WCF, которые используют эту связующую связь, по своей сути являются апосильными и прекращают свои соединения при закрытии канала. Поэтому привязка <xref:System.ServiceModel.BasicHttpBinding> хорошо работает с имеющимися методами балансировки нагрузки HTTP.  
  
 По умолчанию <xref:System.ServiceModel.BasicHttpBinding> отправляет заголовок HTTP подключения в сообщениях со значением `Keep-Alive`, которое позволяет клиентам устанавливать устойчивые подключения к службам, которые поддерживают их. Такая конфигурация увеличивает пропускную способность, потому что ранее установленные подключения можно повторно использовать для отправки новых сообщений одному и тому же серверу. Однако повторное использований подключений может привести к тому, что клиенты будут слишком сильно связаны с конкретным сервером фермы балансировки нагрузки, что приведет к снижению эффективности балансировки нагрузки за счет равномерного распределения запросов между серверами фермы. Если такое поведение является нежелательным, можно на сервере отключить заголовок `Keep-Alive`, присвоив свойству <xref:System.ServiceModel.Channels.HttpTransportBindingElement.KeepAliveEnabled%2A> значение <xref:System.ServiceModel.Channels.CustomBinding> или пользовательскую привязку <xref:System.ServiceModel.Channels.Binding>. В следующем примере показано, как добиться этого с помощью конфигурации.  
  
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
  
 Используя упрощенную конфигурацию, введенную в .NET Framework 4, такое же поведение может быть выполнено с помощью следующей упрощенной конфигурации.  
  
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
  
 Дополнительные сведения о конечных точках по умолчанию, привязках и режимах работы см. в разделах [Упрощенная конфигурация](simplified-configuration.md) и [Упрощенная конфигурация служб WCF](./samples/simplified-configuration-for-wcf-services.md).  
  
## <a name="load-balancing-with-the-wshttp-binding-and-the-wsdualhttp-binding"></a>Балансировка нагрузки с привязкой WSHttp и привязкой WSDualHttp  
 Для привязок <xref:System.ServiceModel.WSHttpBinding> и <xref:System.ServiceModel.WSDualHttpBinding> можно обеспечить балансировку нагрузки, используя для этого методы балансировки нагрузки HTTP, реализуемые путем внесения некоторых изменений в конфигурацию привязки по умолчанию.  
  
- Отключите установление контекста безопасности. Для этого присвойте свойству <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> привязки <xref:System.ServiceModel.WSHttpBinding> значение `false`. Кроме того, при необходимости сеансов безопасности можно использовать сеансы безопасности состояния, описанные в теме [«Безопасные сессии».](./feature-details/secure-sessions.md) Сеансы безопасности с отслеживанием состояния позволяют службе не учитывать состояние, потому что все сведения о состоянии сеанса безопасности передаются с каждым запросом в рамках маркера безопасности защиты. Обратите внимание, что для включения сеансов безопасности с отслеживанием состояния необходимо использовать привязку <xref:System.ServiceModel.Channels.CustomBinding> или определенную пользователем привязку <xref:System.ServiceModel.Channels.Binding>, поскольку необходимые параметры конфигурации не доступны в привязках <xref:System.ServiceModel.WSHttpBinding> и <xref:System.ServiceModel.WSDualHttpBinding>, которые предоставляются системой.  
  
- Не используйте надежные сеансы. Эта возможность отключена по умолчанию.  
  
## <a name="load-balancing-the-nettcp-binding"></a>Балансировка нагрузки привязки Net.TCP  
 Балансировку нагрузки привязки <xref:System.ServiceModel.NetTcpBinding> можно осуществлять с помощью методов балансировки нагрузки уровня протокола IP. Однако для уменьшения времени задержки подключений привязка <xref:System.ServiceModel.NetTcpBinding> по умолчанию объединяет TCP-подключения. Такая оптимизация противоречит базовому механизму балансировки нагрузки. Основным параметром конфигурации, используемым для оптимизации <xref:System.ServiceModel.NetTcpBinding>, является время ожидания аренды, которое входит в настройки пула подключений. В результате объединения клиентских подключений в пул эти подключения оказываются связанными с конкретными серверами фермы. По мере увеличения времени существования таких подключений (этот показатель зависит от значения времени ожидания аренды) распределение нагрузки между различными серверами фермы становится несбалансированным. В результате среднее время одного вызова увеличивается. Поэтому при использовании привязки <xref:System.ServiceModel.NetTcpBinding> с балансировкой нагрузки следует рассмотреть возможность уменьшения используемого привязкой времени ожидания аренды по умолчанию. Для начала использования балансировки нагрузки можно установить время ожидания аренды равным 30 секундам, хотя оптимальное значение будет зависеть от конкретного приложения. Более подробную информацию о тайм-ауте и других транспортных квотах читайте в ["Транспортных квотах".](./feature-details/transport-quotas.md)  
  
 Для достижения максимальной производительности при балансировке нагрузки рекомендуется использовать <xref:System.ServiceModel.NetTcpSecurity> (<xref:System.ServiceModel.SecurityMode.Transport> или <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>).  
  
## <a name="see-also"></a>См. также раздел

- [Рекомендации по размещению в службах IIS](./feature-details/internet-information-services-hosting-best-practices.md)
