---
title: Как Секционирование данных служб
ms.date: 03/30/2017
ms.assetid: 1ccff72e-d76b-4e36-93a2-e51f7b32dc83
ms.openlocfilehash: 49aefd88d73732a139a79f8c53d5beca44d4d4ba
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947870"
---
# <a name="how-to-service-data-partitioning"></a>Как Секционирование данных служб
В этом разделе описаны основные шаги, которые необходимо выполнить для секционирования сообщений по нескольким экземплярам одной и той же целевой службы. Секционирование данных служб обычно используется в том случае, если необходимо масштабирование службы для повышения качества обслуживания или определенным образом обрабатывать запросы от различных клиентов. Например, сообщения от высокого значения или «золотых» клиентов могут обрабатываться с более высоким приоритетом, чем сообщения от стандартного клиента.  
  
 В этом примере сообщения передаются двум экземплярам службы regularCalc. Оба экземпляра службы идентичны, но служба, представленная конечной точкой calculator1, обрабатывает сообщения, которые получены от особо важных клиентов, а конечная точка calculator2 - от остальных.  
  
 Сообщение, отправляемое от клиента, не содержит уникальных данных, которые могут быть использованы для определения экземпляра службы, которому необходимо направить сообщение. Чтобы каждый клиент мог обращаться к определенным службам, будут реализованы две конечные точки целевой службы, которые будут получать сообщения.  
  
> [!NOTE]
> Хотя в этом примере секционирование данных производится по конечным точкам, оно также может выполняться по данным, содержащимся в самом сообщении (заголовку или тексту).  
  
### <a name="implement-service-data-partitioning"></a>Реализация секционирования данных служб  
  
1. Создайте базовую конфигурацию службы маршрутизации, указав конечные точки службы, предоставленные службой. В следующем примере определяются две конечные точки службы, которые будут использоваться для получения сообщений. Кроме того, будут определены клиентские конечные точки для отправки сообщений экземплярам служб regularCalc.  
  
    ```xml  
    <services>  
      <service behaviorConfiguration="routingConfiguration"  
               name="System.ServiceModel.Routing.RoutingService">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost/routingservice/router" />  
          </baseAddresses>  
        </host>  
        <!--Set up the inbound endpoints for the Routing Service-->  
        <!--create the endpoints for the calculator service-->  
        <endpoint address="calculator1"  
                  binding="wsHttpBinding"  
                  name="calculator1Endpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
        <endpoint address="calculator2"  
                  binding="wsHttpBinding"  
                  name="calculator2Endpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
       </service>  
    </services>  
    <client>  
    <!--set up the destination endpoints-->  
        <endpoint name="CalcEndpoint1"  
                  address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                  binding="netTcpBinding"  
                  contract="*" />  
  
        <endpoint name="CalcEndpoint2"  
                  address="net.tcp://localhost:8080/servicemodelsamples/service/"  
                  binding="netTcpBinding"  
                  contract="*" />  
     </client>  
    ```  
  
2. Определите фильтры, используемые для маршрутизации сообщений до конечных точек назначения.  В этом примере фильтр EndpointName служит для определения конечной точки службы, которая получает сообщение. В следующем примере определяется секция и фильтры маршрутизации.  
  
    ```xml  
    <filters>  
      <!--define the different message filters-->  
      <!--define endpoint name filters looking for messages that show up on the virtual endpoints-->  
      <filter name="HighPriority" filterType="EndpointName"  
              filterData="calculator1Endpoint"/>  
      <filter name="NormalPriority" filterType="EndpointName"  
              filterData="calculator2Endpoint"/>  
    </filters>  
    ```  
  
3. Определите таблицу фильтров, которая связывает каждый фильтр с клиентской конечной точкой. В этом примере маршрутизация сообщения будет определяться по конечной точке, через которую оно было получено. Поскольку сообщение может соответствовать только одному из двух возможных фильтров, в использовании приоритетов фильтров для управление порядком выполнения оценки фильтров не требуется.  
  
     Далее будет определена таблица фильтров, а также добавлены определенные ранее фильтры.  
  
    ```xml  
    <filterTables>  
       <filterTable name="filterTable1">  
         <!--add the filters to the message filter table-->  
         <add filterName="HighPriority" endpointName="CalcEndpoint1"/>  
         <add filterName="NormalPriority" endpointName="CalcEndpoint2"/>  
       </filterTable>  
    </filterTables>  
    ```  
  
4. Для обработки входящих сообщений фильтрами, содержащимися в таблице, необходимо связать таблицу фильтров с конечными точками службы при помощи поведения маршрутизации. В следующем примере демонстрируется связывание "filterTable1" с конечными точками службы:  
  
    ```xml  
    <behaviors>  
      <!--default routing service behavior definition-->  
      <serviceBehaviors>  
        <behavior name="routingConfiguration">  
          <routing filterTableName="filterTable1" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
## <a name="example"></a>Пример  
 Далее приведен полный листинг файла конфигурации.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright (c) Microsoft Corporation. All rights reserved -->  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service behaviorConfiguration="routingConfiguration"  
               name="System.ServiceModel.Routing.RoutingService">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost/routingservice/router" />  
          </baseAddresses>  
        </host>  
        <!--Set up the inbound endpoints for the Routing Service-->  
        <!--create the endpoints for the calculator service-->  
        <endpoint address="calculator1"  
                  binding="wsHttpBinding"  
                  name="calculator1Endpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
        <endpoint address="calculator2"  
                  binding="wsHttpBinding"  
                  name="calculator2Endpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
  
      </service>  
    </services>  
    <behaviors>  
      <!--default routing service behavior definition-->  
      <serviceBehaviors>  
        <behavior name="routingConfiguration">  
          <routing filterTableName="filterTable1" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
    <client>  
<!--set up the destination endpoints-->  
      <endpoint name="CalcEndpoint1"  
                address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                binding="netTcpBinding"  
                contract="*" />  
  
      <endpoint name="CalcEndpoint2"  
                address="net.tcp://localhost:8080/servicemodelsamples/service/"  
                binding="netTcpBinding"  
                contract="*" />  
    </client>  
    <routing>  
      <!-- use the namespace table element to define a prefix for our custom namespace-->  
  
      <filters>  
        <!--define the different message filters-->  
        <!--define endpoint name filters looking for messages that show up on the virtual endpoints-->  
        <filter name="HighPriority" filterType="EndpointName"  
                filterData="calculator1Endpoint"/>  
        <filter name="NormalPriority" filterType="EndpointName"  
                filterData="calculator2Endpoint"/>  
      </filters>  
  
      <filterTables>  
        <filterTable name="filterTable1">  
          <!--add the filters to the message filter table-->  
          <add filterName="HighPriority" endpointName="CalcEndpoint1"/>  
          <add filterName="NormalPriority" endpointName="CalcEndpoint2"/>  
        </filterTable>  
      </filterTables>  
  
    </routing>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- [Службы маршрутизации](../../../../docs/framework/wcf/samples/routing-services.md)
