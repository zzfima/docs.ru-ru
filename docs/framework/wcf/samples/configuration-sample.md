---
title: Образец конфигурации
ms.date: 03/30/2017
ms.assetid: 75515b4a-8d70-44c8-99e0-7423df41380e
ms.openlocfilehash: 78108dc9b28657f0479e9e39ad134f03cf6c877b
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74714959"
---
# <a name="configuration-sample"></a>Образец конфигурации
Этот образец демонстрирует, как при помощи файла конфигурации можно сделать службу доступной для обнаружения.  
  
> [!NOTE]
> Данный образец реализует возможность обнаружения в конфигурации. Пример, в котором реализовано обнаружение в коде, см. в разделе [Basic](../../../../docs/framework/wcf/samples/basic-sample.md).  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\Configuration`  
  
## <a name="service-configuration"></a>Настройка службы  
 Файл конфигурации в данном образце иллюстрирует две возможности.  
  
- Обеспечение доступности обнаружения службы через стандартную конечную точку <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>.  
  
- Настройка информации, связанной с обнаружением, для конечной точки приложения службы, а также настройка некоторых параметров, связанных с обнаружением, для стандартной конечной точки.  
  
 Чтобы включить функцию обнаружения, в файле конфигурации приложения службы необходимо произвести следующие изменения.  
  
- Необходимо добавить конечную точку обнаружения к элементу `<service>`. Это стандартная конечная точка <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>. Это системная конечная точка, которую среда выполнения связывает со службой обнаружения. Служба обнаружения использует эту конечную точку для прослушивания сообщений.  
  
- Добавим поведение `<serviceDiscovery>` в раздел `<serviceBehaviors>`. Это позволит обнаруживать службу во время выполнения, используя ранее упомянутую конечную точку обнаружения для прослушивания сообщений `Probe` и `Resolve`. После выполнения этих двух добавлений служба доступна для обнаружения на указанной конечной точке обнаружения.  
  
 В следующем фрагменте конфигурации показана служба с указанной конечной точкой приложения и конечной точкой обнаружения.  
  
```xml
<services>  
        <service name="Microsoft.Samples.Discovery.CalculatorService"  
                 behaviorConfiguration="calculatorServiceBehavior">  
          <endpoint address=""  
                    binding="wsHttpBinding"  
                    contract="Microsoft.Samples.Discovery.ICalculatorService"  
                    behaviorConfiguration="endpointBehaviorConfiguration" />  
          <endpoint name="udpDiscovery"   
                    kind="udpDiscoveryEndpoint"   
                endpointConfiguration="adhocDiscoveryEndpointConfiguration"/>        </service>  
      </services>  
```  
  
 Чтобы воспользоваться объявлениями, необходимо добавить конечную точку объявления. Для этого нужно изменить файл конфигурации, как показано в следующем коде.  
  
```xml  
<serviceDiscovery>  
            <announcementEndpoints>  
              <endpoint kind="udpAnnouncementEndpoint"/>  
            </announcementEndpoints>  
          </serviceDiscovery>  
```  
  
 При добавлении конечной точки объявления к службе обнаружения создается клиент объявления по умолчанию для службы. Это гарантирует, что служба отправит объявление о режиме «в сети» или «не в сети» соответственно при открытии и закрытии службы.  
  
 Можно не ограничиваться приведенными простыми шагами и изменить в файле конфигурации дополнительные поведения. Информацией, относящейся к обнаружению, можно управлять с использованием определенных конечных точек. Таким образом пользователь может указать, доступна ли конечная точка для обнаружения, а также пометить ее атрибутом <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior.Scopes%2A> и добавить пользовательские XML-метаданные. Для этого необходимо добавить в конечную точку приложения свойство `behaviorConfiguration`. В этом случае в конечную точку приложения добавляется следующее свойство.  
  
`behaviorConfiguration="endpointBehaviorConfiguration"`  
  
 Теперь с помощью элемента конфигурации поведения можно управлять атрибутами, связанными с обнаружением. В этом случае в конечную точку приложения добавляются две области.  
  
```xml  
<endpointBehaviors>  
          <behavior name="endpointBehaviorConfiguration">  
            <endpointDiscovery>  
              <scopes>  
                <add scope="http://www.example.com/calculator"/>  
                <add scope="ldap:///ou=engineering,o=examplecom,c=us"/>  
              </scopes>  
            </endpointDiscovery>  
  
          </behavior>            
        </endpointBehaviors>  
```  
  
 Дополнительные сведения об областях см. в разделе [Обнаружение Find и FindCriteria](../../../../docs/framework/wcf/feature-details/discovery-find-and-findcriteria.md).  
  
 Можно также управлять определенными сведениями о конечной точке обнаружения. Это выполняется с помощью объекта <xref:System.ServiceModel.Configuration.StandardEndpointsSection>. В данном образце изменяется версия используемого протокола, а также добавляется атрибут `maxResponseDelay`, как показано в следующем примере кода.  
  
```xml  
<standardEndpoints>  
   <udpDiscoveryEndpoint>  
      <standardEndpoint name="adhocDiscoveryEndpointConfiguration" discoveryVersion="WSDiscovery11" maxResponseDelay="00:00:00.600" />    
   </udpDiscoveryEndpoint>  
</standardEndpoints>  
```  
  
 Далее приведен полный листинг файла конфигурации, используемого в этом примере.  
  
```xml  
<configuration>  
    <system.serviceModel>  
  
      <services>  
        <service name="Microsoft.Samples.Discovery.CalculatorService"  
                 behaviorConfiguration="calculatorServiceBehavior">  
          <endpoint address=""  
                    binding="wsHttpBinding"  
                    contract="Microsoft.Samples.Discovery.ICalculatorService"  
                    behaviorConfiguration="endpointBehaviorConfiguration" />  
         <!-- Define the discovery endpoint -->            
<endpoint name="udpDiscovery" kind="udpDiscoveryEndpoint" endpointConfiguration="adhocDiscoveryEndpointConfiguration"/>        </service>  
      </services>  
  
      <behaviors>  
  
        <serviceBehaviors>  
          <behavior name="calculatorServiceBehavior">  
  
            <!-- Add an announcement endpoint -->  
            <serviceDiscovery>  
              <announcementEndpoints>  
                <endpoint kind="udpAnnouncementEndpoint"/>  
              </announcementEndpoints>  
            </serviceDiscovery>  
          </behavior>  
        </serviceBehaviors>  
  
        <endpointBehaviors>  
          <behavior name="endpointBehaviorConfiguration">  
            <!-- Add scopes used to identify the service -->  
            <endpointDiscovery>  
              <scopes>  
                <add scope="http://www.example.com/calculator"/>  
                <add scope="ldap:///ou=engineering,o=examplecom,c=us"/>  
              </scopes>  
            </endpointDiscovery>  
  
          </behavior>            
        </endpointBehaviors>  
  
      </behaviors>  
  
      <standardEndpoints>  
        <udpDiscoveryEndpoint>  
         <!-- Configure the UDP discovery endpoint -->  
          <standardEndpoint name="adhocDiscoveryEndpointConfiguration" discoveryVersion="WSDiscovery11" maxResponseDelay="00:00:00.600" />    
        </udpDiscoveryEndpoint>  
      </standardEndpoints>  
  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="client-configuration"></a>Конфигурация клиента  
 Для включения функции обнаружения в конфигурации приложения для клиента используется конечная точка `standardEndpoint` типа `dynamicEndpoint`, как показано в следующем фрагменте.  
  
```xml  
<client>  
   <!--  Create an endpoint, make kind="dynamicEndpoint" and use the endpointConfiguration to change settings of DynamicEndpoint -->  
   <endpoint name="calculatorEndpoint"  
             binding="wsHttpBinding"  
             contract="ICalculatorService"  
             kind ="dynamicEndpoint"  
             endpointConfiguration="dynamicEndpointConfiguration">  
   </endpoint>  
</client>  
```  
  
 Если клиент использует конечную точку типа `dynamicEndpoint`, обнаружение осуществляется средой выполнения автоматически. При обнаружении используются различные параметры, например те, которые определены в разделе `discoveryClientSettings`, задающем тип используемой конечной точки обнаружения.  
  
```xml  
<endpoint kind="udpDiscoveryEndpoint" endpointConfiguration="adhocDiscoveryEndpointConfiguration" />  
```  
  
 Критерии поиска, используемые для поиска служб:  
  
```xml  
<!-- Add Scopes, ScopeMatchBy, Extensions and termination criteria in FindCriteria -->  
<findCriteria scopeMatchBy="http://schemas.microsoft.com/ws/2008/06/discovery/rfc" duration="00:00:10" maxResults="1">  
   <scopes>  
      <add scope="http://www.microsoft.com/building42/floor1"/>  
   </scopes>  
   <!-- These extensions are sent from the client to the service as part of the probe message -->  
   <extensions>  
      <CustomMetadata>This is custom metadata that is sent to the service along with the client's find request.</CustomMetadata>  
   </extensions>  
</findCriteria>  
```  
  
 Данный образец расширяет эту возможность и изменяет используемый клиентом объект <xref:System.ServiceModel.Discovery.FindCriteria>, а также некоторые свойства стандартной конечной точки `updDiscoveryEndpoint`, применяемой для обнаружения. Измененный объект <xref:System.ServiceModel.Discovery.FindCriteria> использует область и указанный алгоритм `scopeMatchBy`, а также пользовательские критерии завершения. Кроме того, образец также показывает, как клиент может отправлять XML-элементы с помощью сообщений `Probe`. Наконец, вносятся некоторые изменения в конечную точку <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>. В частности, меняется версия используемого протокола и параметры UDP, как показано в приведенном далее файле конфигурации.  
  
```xml  
<udpDiscoveryEndpoint>    
        <!-- Specify the discovery protocol version and UDP transport settings. -->   
        <standardEndpoint name="adhocDiscoveryEndpointConfiguration" discoveryVersion="WSDiscovery11">  
          <transportSettings duplicateMessageHistoryLength="2048"  
                             maxPendingMessageCount="5"  
                             maxReceivedMessageSize="8192"  
                             maxBufferPoolSize="262144"/>  
        </standardEndpoint>        
      </udpDiscoveryEndpoint>  
```  
  
 Далее приведен полный листинг конфигурации клиента для этого образца.  
  
```xml  
<configuration>  
  <system.serviceModel>  
  
    <client>  
      <!--  Create an endpoint, make kind="dynamicEndpoint" and use the endpointConfiguration to change settings of DynamicEndpoint -->  
      <endpoint name="calculatorEndpoint"  
                binding="wsHttpBinding"  
                contract="ICalculatorService"  
                kind ="dynamicEndpoint"  
                endpointConfiguration="dynamicEndpointConfiguration">  
      </endpoint>  
    </client>  
  
    <standardEndpoints>  
  
      <dynamicEndpoint>        
        <standardEndpoint name="dynamicEndpointConfiguration">  
          <discoveryClientSettings>  
            <!-- Controls where the discovery happens. In this case, Probe message is sent over UdpDiscoveryEndpoint. -->  
            <endpoint kind="udpDiscoveryEndpoint" endpointConfiguration="adhocDiscoveryEndpointConfiguration" />  
  
            <!-- Add Scopes, ScopeMatchBy, Extensions and termination criteria in FindCriteria -->  
            <findCriteria scopeMatchBy="http://schemas.microsoft.com/ws/2008/06/discovery/rfc" duration="00:00:10" maxResults="1">  
              <scopes>  
                <add scope="http://www.microsoft.com/building42/floor1"/>  
              </scopes>  
              <!-- These extensions are sent from the client to the service as part of the probe message -->  
              <extensions>  
                <CustomMetadata>This is custom metadata that is sent to the service along with the client's find request.</CustomMetadata>  
              </extensions>  
            </findCriteria>  
          </discoveryClientSettings>  
        </standardEndpoint>     
      </dynamicEndpoint>  
  
      <udpDiscoveryEndpoint>    
        <!-- Specify the discovery protocol version and UDP transport settings. -->   
        <standardEndpoint name="adhocDiscoveryEndpointConfiguration" discoveryVersion="WSDiscovery11">  
          <transportSettings duplicateMessageHistoryLength="2048"  
                             maxPendingMessageCount="5"  
                             maxReceivedMessageSize="8192"  
                             maxBufferPoolSize="262144"/>  
        </standardEndpoint>        
      </udpDiscoveryEndpoint>  
  
    </standardEndpoints>  
  
  </system.serviceModel>  
```  
  
#### <a name="to-use-this-sample"></a>Использование этого образца  
  
1. В этом примере используются конечные точки HTTP и для запуска этого образца необходимо добавить соответствующие списки ACL URL-адресов. Дополнительные сведения см. в разделе [Настройка HTTP и HTTPS](https://go.microsoft.com/fwlink/?LinkId=70353) . Нужные списки управления доступом будут добавлены после выполнения следующей команды с повышенными привилегиями. Если команда не работает, следует указать домен и имя пользователя в следующих аргументах. `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`  
  
2. Постройте решение.  
  
3. Выполните исполняемый файл службы из каталога сборки.  
  
4. Выполните исполняемый файл клиента. Учтите, что клиент может определить расположение службы.  
