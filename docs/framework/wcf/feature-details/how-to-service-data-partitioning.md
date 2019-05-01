---
title: 'Как выполнить: Секционирование данных служб'
ms.date: 03/30/2017
ms.assetid: 1ccff72e-d76b-4e36-93a2-e51f7b32dc83
ms.openlocfilehash: 17cb80bf253491eb563d6fd45b5997e452f542e1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62047533"
---
# <a name="how-to-service-data-partitioning"></a><span data-ttu-id="97300-102">Как выполнить: Секционирование данных служб</span><span class="sxs-lookup"><span data-stu-id="97300-102">How To: Service Data Partitioning</span></span>
<span data-ttu-id="97300-103">В этом разделе описаны основные шаги, которые необходимо выполнить для секционирования сообщений по нескольким экземплярам одной и той же целевой службы.</span><span class="sxs-lookup"><span data-stu-id="97300-103">This topic outlines the basic steps required to partition messages across multiple instances of the same destination service.</span></span> <span data-ttu-id="97300-104">Секционирование данных служб обычно используется в том случае, если необходимо масштабирование службы для повышения качества обслуживания или определенным образом обрабатывать запросы от различных клиентов.</span><span class="sxs-lookup"><span data-stu-id="97300-104">Service data partitioning is typically used when you need to scale a service in order to provide better quality of service, or when you need to handle requests from different customers in a specific way.</span></span> <span data-ttu-id="97300-105">Например сообщения из высокое значение "или" клиенты «Золотая» может потребоваться обработать на более высокий приоритет, чем сообщения от стандартных клиентов.</span><span class="sxs-lookup"><span data-stu-id="97300-105">For example, messages from high value or "Gold" customers may need to be processed at a higher priority than messages from a standard customer.</span></span>  
  
 <span data-ttu-id="97300-106">В этом примере сообщения передаются двум экземплярам службы regularCalc.</span><span class="sxs-lookup"><span data-stu-id="97300-106">In this example, messages are routed to one of two instances of the regularCalc service.</span></span> <span data-ttu-id="97300-107">Оба экземпляра службы идентичны, но служба, представленная конечной точкой calculator1, обрабатывает сообщения, которые получены от особо важных клиентов, а конечная точка calculator2 - от остальных.</span><span class="sxs-lookup"><span data-stu-id="97300-107">Both instances of the service are identical; however the service represented by the calculator1 endpoint processes messages received from high value customers, the calculator 2 endpoint processes messages from other customers</span></span>  
  
 <span data-ttu-id="97300-108">Сообщение, отправляемое от клиента, не содержит уникальных данных, которые могут быть использованы для определения экземпляра службы, которому необходимо направить сообщение.</span><span class="sxs-lookup"><span data-stu-id="97300-108">The message sent from the client does not have any unique data that can be used to identify which service instance the message should be routed to.</span></span> <span data-ttu-id="97300-109">Чтобы каждый клиент мог обращаться к определенным службам, будут реализованы две конечные точки целевой службы, которые будут получать сообщения.</span><span class="sxs-lookup"><span data-stu-id="97300-109">To allow each client to route data to a specific destination service we will implement two service endpoints that will be used to receive messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="97300-110">Хотя в этом примере секционирование данных производится по конечным точкам, оно также может выполняться по данным, содержащимся в самом сообщении (заголовку или тексту).</span><span class="sxs-lookup"><span data-stu-id="97300-110">While this example uses specific endpoints to partition data, this could also be accomplished using information contained within the message itself such as header or body data.</span></span>  
  
### <a name="implement-service-data-partitioning"></a><span data-ttu-id="97300-111">Реализация секционирования данных служб</span><span class="sxs-lookup"><span data-stu-id="97300-111">Implement Service Data Partitioning</span></span>  
  
1. <span data-ttu-id="97300-112">Создайте базовую конфигурацию службы маршрутизации, указав конечные точки службы, предоставленные службой.</span><span class="sxs-lookup"><span data-stu-id="97300-112">Create the basic Routing Service configuration by specifying the service endpoints exposed by the service.</span></span> <span data-ttu-id="97300-113">В следующем примере определяются две конечные точки службы, которые будут использоваться для получения сообщений.</span><span class="sxs-lookup"><span data-stu-id="97300-113">The following example defines two endpoints, which will be used to receive messages.</span></span> <span data-ttu-id="97300-114">Кроме того, будут определены клиентские конечные точки для отправки сообщений экземплярам служб regularCalc.</span><span class="sxs-lookup"><span data-stu-id="97300-114">It also defines the client endpoints, which are used to send messages to the regularCalc service instances.</span></span>  
  
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
  
2. <span data-ttu-id="97300-115">Определите фильтры, используемые для маршрутизации сообщений до конечных точек назначения.</span><span class="sxs-lookup"><span data-stu-id="97300-115">Define the filters used to route messages to the destination endpoints.</span></span>  <span data-ttu-id="97300-116">В этом примере фильтр EndpointName служит для определения конечной точки службы, которая получает сообщение.</span><span class="sxs-lookup"><span data-stu-id="97300-116">For this example, the EndpointName filter is used to determine which service endpoint received the message.</span></span> <span data-ttu-id="97300-117">В следующем примере определяется секция и фильтры маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="97300-117">The following example defines the necessary routing section and filters.</span></span>  
  
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
  
3. <span data-ttu-id="97300-118">Определите таблицу фильтров, которая связывает каждый фильтр с клиентской конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="97300-118">Define the filter table, which associates each filter with a client endpoint.</span></span> <span data-ttu-id="97300-119">В этом примере маршрутизация сообщения будет определяться по конечной точке, через которую оно было получено.</span><span class="sxs-lookup"><span data-stu-id="97300-119">In this example, the message will be routed based on the specific endpoint it was received over.</span></span> <span data-ttu-id="97300-120">Поскольку сообщение может соответствовать только одному из двух возможных фильтров, в использовании приоритетов фильтров для управление порядком выполнения оценки фильтров не требуется.</span><span class="sxs-lookup"><span data-stu-id="97300-120">Since the message can only match one of the two possible filters, there is no need for using filter priority to control to the order in which filters are evaluated.</span></span>  
  
     <span data-ttu-id="97300-121">Далее будет определена таблица фильтров, а также добавлены определенные ранее фильтры.</span><span class="sxs-lookup"><span data-stu-id="97300-121">The following defines the filter table and adds the filters defined earlier.</span></span>  
  
    ```xml  
    <filterTables>  
       <filterTable name="filterTable1">  
         <!--add the filters to the message filter table-->  
         <add filterName="HighPriority" endpointName="CalcEndpoint1"/>  
         <add filterName="NormalPriority" endpointName="CalcEndpoint2"/>  
       </filterTable>  
    </filterTables>  
    ```  
  
4. <span data-ttu-id="97300-122">Для обработки входящих сообщений фильтрами, содержащимися в таблице, необходимо связать таблицу фильтров с конечными точками службы при помощи поведения маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="97300-122">To evaluate incoming messages against the filters contained in the table, you must associate the filter table with the service endpoints by using the routing behavior.</span></span> <span data-ttu-id="97300-123">В следующем примере показано связывание «filterTable1» с конечными точками служб:</span><span class="sxs-lookup"><span data-stu-id="97300-123">The following example demonstrates associating "filterTable1" with the service endpoints:</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="97300-124">Пример</span><span class="sxs-lookup"><span data-stu-id="97300-124">Example</span></span>  
 <span data-ttu-id="97300-125">Далее приведен полный листинг файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="97300-125">The following is a complete listing of the configuration file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="97300-126">См. также</span><span class="sxs-lookup"><span data-stu-id="97300-126">See also</span></span>

- [<span data-ttu-id="97300-127">Службы маршрутизации</span><span class="sxs-lookup"><span data-stu-id="97300-127">Routing Services</span></span>](../../../../docs/framework/wcf/samples/routing-services.md)
