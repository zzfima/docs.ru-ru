---
title: "Как обрабатывать ошибки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: de566e39-9358-44ff-8244-780f6b799966
caps.latest.revision: "5"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a5b0fe57bb6a4604c86e63a154e3af5542672912
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-error-handling"></a>Как обрабатывать ошибки
В этом разделе описаны основные шаги по созданию конфигурации маршрутизации с применением обработки ошибок. В данном примере сообщения перенаправляются в целевую конечную точку. Если сообщение не удается доставить из-за сбоя сети или канала связи (<xref:System.ServiceModel.CommunicationException>), оно повторно отправляется в альтернативную конечную точку.  
  
> [!NOTE]
>  Чтобы смоделировать сбой сети, в данном примере в целевую конечную точку включен неверный адрес. Направление сообщений в эту конечную точку будет завершаться ошибкой, поскольку ни одна служба не прослушивает указанный адрес.  
  
> [!NOTE]
>  Хотя пример, приведенный в данном разделе, специально не затрагивает параметры времени ожидания, при обработке ошибок их тоже нужно учитывать. При возникновении ошибок клиент получает ответ с дополнительной задержкой. Это происходит потому, что служба маршрутизации получает ошибку и пытается отправить сообщение в резервную конечную точку. Если значения времени ожидания, связанные с основной и резервной целевыми конечными точками, велики, клиент может столкнуться с длительной задержкой, вызванной тем, что до успешной отправки сообщение может безрезультатно направляться в разные конечные точки из резервного списка.  
>   
>  Поскольку служба маршрутизации может столкнуться с наибольшей задержкой, равной сумме значений времени ожидания для всех конечных точек, связанных с фильтром, рекомендуется соответствующим образом увеличить значение времени ожидания на клиенте.  
  
### <a name="implement-error-handling"></a>Реализация обработки ошибок  
  
1.  Создайте базовую конфигурацию службы маршрутизации, указав конечную точку службы, предоставленную службой. В следующем примере определяется отдельная конечная точка службы, которая используется для получения сообщений. Также будут определены конечные точки клиента, которые используются для отправки сообщений - deadDestination и realDestination. Конечная точка deadDestination содержит адрес, который не ссылается на работающую службу и используется для моделирования сбоя сети при отправке сообщений в эту конечную точку.  
  
    ```xml  
    <services>  
      <service behaviorConfiguration="routingConfiguration"  
               name="System.ServiceModel.Routing.RoutingService">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost/routingservice/" />  
          </baseAddresses>  
        </host>  
        <!-- Create the Routing Service endpoint -->  
        <endpoint address="router"  
                  binding="basicHttpBinding"  
                  name="RoutingServiceEndpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
      </service>  
    </services>  
  
    <!-- Create the destination endpoints that we want to send to -->  
    <client>  
      <!-- Create a dummy endpoint that we know will be down -->  
      <endpoint name="deadDestination"   
                address="net.tcp://localhost:9090/servicemodelsamples/fakeDestination"  
                binding="netTcpBinding"  
                contract="*" />  
  
      <!-- Now create the real service endpoint -->  
      <endpoint name="realDestination"   
                address="net.tcp://localhost:8080/servicemodelsamples/service"  
                binding="netTcpBinding"   
                contract="*" />  
    </client>  
    ```  
  
2.  Определите фильтры, используемые для маршрутизации сообщений до конечных точек назначения.  В данном примере фильтр MatchAll используется для соответствия всем сообщениям, полученным службой маршрутизации.  
  
    ```xml  
    <filters>  
      <!-- Create a MatchAll filter which will catch all messages -->  
      <filter name="MatchAllFilter1" filterType="MatchAll" />  
    </filters>  
    ```  
  
3.  Задайте список резервных конечных точек, в которые сообщение отправляется в случае сбоя сети или канала связи при отправке сообщения в основную целевую конечную точку. В следующем примере задается резервный список с одной конечной точкой, хотя он может содержать несколько конечных точек.  
  
     Если в резервном списке содержится несколько конечных точек, то при возникновении сбоя сети или канала связи служба маршрутизации попытается отправить сообщение в первую из них. Если при отправке сообщения в эту точку возникает сбой сети или канала связи, служба маршрутизации попытается отправить сообщение в следующую конечную точку в списке. Служба продолжает отправлять сообщение в каждую из резервных конечных точек в списке до успешной отправки сообщения, или до получения от всех точек сообщения об ошибке сети или канала связи, или до получения от конечной точки сообщения об ошибке, не связанной с сетью или каналом связи, после отправки сообщения.  
  
    ```xml  
    <backupLists>          
      <backupList name="backupEndpointList">  
          <add endpointName="realDestination" />  
      </backupList>  
    </backupLists>  
    ```  
  
4.  Задайте таблицу фильтра, сопоставляющую фильтр с конечной точкой deadDestination и списком резервных конечных точек.  Служба маршрутизации сначала попытается отправить сообщение в целевую конечную точку, сопоставленную с фильтром. Поскольку конечная точка deadDestination содержит адрес, не ссылающийся на работающую службу, эта попытка приведет к ошибке сети. Затем служба маршрутизации попытается отправить сообщение в конечную точку из резервного списка.  
  
    ```xml  
    <filterTables>  
            <!-- Set up the Routing Service's Message Filter Table -->  
            <filterTable name="filterTable1">  
                <!-- Add an entity that maps the MatchAllMessageFilter to the dead destination -->  
                <!-- If that endpoint is down, tell the Routing Service to try the endpoints -->  
                <!-- Listed in the backupEndpointList -->  
                <add filterName="MatchAllFilter1" endpointName="deadDestination" backupList="backupEndpointList"/>  
            </filterTable>  
          </filterTables>  
    ```  
  
5.  Для оценки входящих сообщений с помощью фильтра, содержащегося в таблице фильтров, необходимо сопоставить таблицу фильтров с конечными точками службы при помощи поведения маршрутизации.  В следующем примере показано связывание «filterTable1» с конечными точками службы.  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
        <!-- Set up the Routing Behavior -->  
        <behavior name="routingConfiguration">  
          <routing filterTableName="filterTable1" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
## <a name="example"></a>Пример  
 Далее приводится полный листинг файла конфигурации.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright (c) Microsoft Corporation.  All Rights Reserved. -->  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service behaviorConfiguration="routingConfiguration"  
               name="System.ServiceModel.Routing.RoutingService">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost/routingservice/" />  
          </baseAddresses>  
        </host>  
        <!-- Create the Routing Service endpoint -->  
        <endpoint address="router"  
                  binding="basicHttpBinding"  
                  name="RoutingServiceEndpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
      </service>  
    </services>  
    <behaviors>  
      <serviceBehaviors>  
        <!-- Set up the Routing Behavior -->  
        <behavior name="routingConfiguration">  
          <routing filterTableName="filterTable1" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <!-- Create the destination endpoints that we want to send to -->  
    <client>  
      <!-- Create a dummy endpoint that we know will be down -->  
      <endpoint name="deadDestination"   
                address="net.tcp://localhost:9090/servicemodelsamples/fakeDestination"  
                binding="netTcpBinding"  
                contract="*" />  
  
      <!-- Now create the real service endpoint -->  
      <endpoint name="realDestination"   
                address="net.tcp://localhost:8080/servicemodelsamples/service"  
                binding="netTcpBinding"   
                contract="*" />  
    </client>  
    <routing>  
      <filters>  
        <!-- Create a MatchAll filter which will catch all messages -->  
        <filter name="MatchAllFilter1" filterType="MatchAll" />  
      </filters>  
      <filterTables>  
        <!-- Set up the Routing Service's Message Filter Table -->  
        <filterTable name="filterTable1">  
            <!-- Add an entrty that maps the MatchAllMessageFilter to the dead destination -->  
            <!-- If that endpoint is down, tell the Routing Service to try the endpoints -->  
            <!-- Listed in the backupEndpointList -->  
            <add filterName="MatchAllFilter1" endpointName="deadDestination" backupList="backupEndpointList"/>  
        </filterTable>  
      </filterTables>  
      <!-- Create the backup endpoint list -->  
      <backupLists>          
        <backupList name="backupEndpointList">  
            <add endpointName="realDestination" />  
        </backupList>  
      </backupLists>  
      </routing>  
  </system.serviceModel>  
</configuration>  
```
