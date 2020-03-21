---
title: Как использовать фильтры
ms.date: 03/30/2017
ms.assetid: f2c7255f-c376-460e-aa20-14071f1666e5
ms.openlocfilehash: f99c2af623dacac3ebe46422815a7f42e2a4df2c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184817"
---
# <a name="how-to-use-filters"></a>Как использовать фильтры
В этом разделе описаны основные шаги по созданию конфигурации маршрутизации с несколькими фильтрами. В этом примере сообщения направляются в две реализации службы калькулятора: regularCalc и roundingCalc. Обе реализации поддерживают одинаковые операции, однако одна служба, прежде чем вернуть результаты вычислений, округляет их до ближайшего целого числа. Клиентское приложение должно иметь возможность указывать, нужно ли использовать версию службы, выполняющую округление. Если предпочитаемая служба не указана, сообщения равномерно распределяются между двумя службами. Операции, предоставляемые обеими службами:  
  
- Добавить  
  
- Вычитание  
  
- Умножение  
  
- Деление  
  
 Поскольку в обеих службах применяются одни и те же операции, нельзя использовать фильтр действий, так как указанное в сообщении действие не будет уникальным. Вместо этого придется проделать дополнительную работу, чтобы гарантированно направлять сообщения в соответствующую конечную точку.  
  
### <a name="determine-unique-data"></a>Определение уникальных данных  
  
1. Поскольку обе реализации служб обрабатывают одни и те же операции и, в сущности, отличаются только возвращаемыми данных, базовые данные, содержащиеся в сообщениях, отправленных клиентскими приложениями, не являются достаточно уникальными, чтобы можно было определить способ маршрутизации запроса. Но если клиентское приложение добавляет в сообщение уникальное значение заголовка, можно использовать это значение для маршрутизации сообщения.  
  
     Например, если клиентскому приложению нужно, чтобы сообщение обрабатывалось калькулятором с округлением, в него необходимо добавить пользовательский заголовок с помощью следующего кода:  
  
    ```csharp  
    messageHeadersElement.Add(MessageHeader.CreateHeader("RoundingCalculator",
                                   "http://my.custom.namespace/", "rounding"));  
    ```  
  
     Теперь можно применить фильтр XPath, чтобы выявлять сообщения с этим заголовком и направлять их в службу roundCalc.  
  
2. Кроме того, в службе маршрутизации имеются две виртуальные конечные точки службы, которые могут использоваться с фильтрами EndpointName, EndpointAddress или PrefixEndpointAddress для уникальной маршрутизации входящих сообщений в определенную реализацию калькулятора, в зависимости от того, к какой конечной точке клиентское приложение направляет запрос.  
  
### <a name="define-endpoints"></a>Определение конечных точек  
  
1. При определении конечных точек, используемых службой маршрутизации, необходимо сначала определить форму канала, используемого клиентами и службами. В этом сценарии обе целевые службы используют шаблон «запрос-ответ», поэтому применяется <xref:System.ServiceModel.Routing.IRequestReplyRouter>. В следующем примере определяются конечные точки службы, предоставляемые службой маршрутизации.  
  
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
            <!--first create the general router endpoint-->  
            <endpoint address="general"  
                      binding="wsHttpBinding"  
                      name="routerEndpoint"  
                      contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
            <!--create a virtual endpoint for the regular calculator service-->  
            <endpoint address="regular/calculator"  
                      binding="wsHttpBinding"  
                      name="calculatorEndpoint"  
                      contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
            <!--now create a virtual endpoint for the rounding calculator-->  
            <endpoint address="rounding/calculator"  
                      binding="wsHttpBinding"  
                      name="roundingEndpoint"  
                      contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
  
          </service>  
    </services>  
    ```  
  
     В этой конфигурации службы маршрутизации предоставляют три отдельные конечные точки. В зависимости от выборов, сделанных в процессе работы, клиентское приложение отправляет сообщения по одному из этих адресов. Сообщения, поступающие в одну из конечных точек «виртуального» сервиса («округление/калькулятор» или «обычный/калькулятор»), направляются в соответствующую реализацию калькулятора. Если клиентское приложение не направляет запрос в определенную конечную точку, сообщение отправляется в общую конечную точку. Независимо от того, какая конечная точка выбрана, клиентское приложение может также включить пользовательский заголовок, указывающий, что сообщение должно быть перенаправлено в реализацию калькулятора с округлением.  
  
2. В следующем примере определяются клиентские (целевые) конечные точки, в которые направляет сообщения служба маршрутизации.  
  
    ```xml  
    <client>  
          <endpoint name="regularCalcEndpoint"  
                    address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                    binding="netTcpBinding"  
                    contract="*" />  
  
          <endpoint name="roundingCalcEndpoint"  
                    address="net.tcp://localhost:8080/servicemodelsamples/service/"  
                    binding="netTcpBinding"  
                    contract="*" />  
    </client>  
    ```  
  
     Эти конечные точки используются в таблице фильтров для указания целевой конечной точки, в которую отправляется сообщение, если оно соответствует критериям определенного фильтра.  
  
### <a name="define-filters"></a>Определение фильтров  
  
1. Чтобы направить сообщения на основе пользовательского заголовка "RoundingCalculator", который клиентское приложение добавляет в сообщение, определите фильтр, который использует запрос XPath для проверки наличия этого заголовка. Поскольку этот заголовок определяется с помощью пользовательского пространства имен, также добавьте запись в пространстве имен, которая определяет пользовательскую префикс пространства имен "обычай", который используется в запросе XPath. В следующем примере определяются необходимый раздел маршрутизации, таблица пространства имен и фильтр XPath.  
  
    ```xml  
    <routing>  
          <!-- use the namespace table element to define a prefix for our custom namespace-->  
          <namespaceTable>  
            <add prefix="custom" namespace="http://my.custom.namespace/"/>  
          </namespaceTable>  
          <filters>  
            <!--define the different message filters-->  
            <!--define an xpath message filter to look for the custom header coming from the client-->  
            <filter name="XPathFilter" filterType="XPath"
                    filterData="/s12:Envelope/s12:Header/custom:RoundingCalculator = 'rounding'"/>  
          </filters>  
    </routing>  
    ```  
  
     Этот **MessageFilter** ищет заголовок РаундингКалькор в сообщении, содержащем значение "округления". Этот заголовок задается клиентом и указывает, что сообщение должно быть направлено в службу roundingCalc.  
  
    > [!NOTE]
    > Префикс пространства имен s12 определяется по умолчанию в таблице `http://www.w3.org/2003/05/soap-envelope`пространства имен и представляет пространство имен.
  
2. Также необходимо определить фильтры для поиска сообщений, полученных в двух виртуальных конечных точках. Первая виртуальная конечная точка — конечная точка «обычный/калькулятор». Клиент может направлять запросы в эту конечную точку, чтобы указать, что сообщение должно быть направлено в службу regularCalc. В следующей конфигурации определен фильтр, использующий <xref:System.ServiceModel.Dispatcher.EndpointNameMessageFilter> для определения, было ли сообщение получено через конечную точку с именем, указанным в параметре filterData.  
  
    ```xml  
    <!--define an endpoint name filter looking for messages that show up on the virtual regular calculator endpoint-->  
    <filter name="EndpointNameFilter" filterType="EndpointName" filterData="calculatorEndpoint"/>  
    ```  
  
     Если сообщение получено в конечном пункте службы под названием "calculatorEndpoint", этот фильтр оценивается как. `true`  
  
3. Затем определите фильтр для поиска сообщений, отправленных на адрес roundingEndpoint. Клиент может направлять запросы в эту конечную точку, чтобы указать, что сообщение должно быть направлено в службу roundingCalc. Следующая конфигурация определяет фильтр, <xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter> который использует для определения, если сообщение поступило в конечную точку "округление/калькулятор".  
  
    ```xml  
    <!--define a filter looking for messages that show up with the address prefix.  The corresponds to the rounding calc virtual endpoint-->  
    <filter name="PrefixAddressFilter" filterType="PrefixEndpointAddress"  
            filterData="http://localhost/routingservice/router/rounding/"/>  
    ```  
  
     Если сообщение получено по адресу, `http://localhost/routingservice/router/rounding/` который начинается с этого фильтра оценивается как **истинное.** Поскольку базовый адрес, `http://localhost/routingservice/router` используемый этой конфигурацией, и адрес, указанный для округленияEndpoint, является "округлением/калькулятором", полный адрес, используемый для связи с этой конечной точкой, совпадает `http://localhost/routingservice/router/rounding/calculator`с этим фильтром.  
  
    > [!NOTE]
    > Фильтр PrefixEndpointAddress не вычисляет имя узла при проведении сопоставления, поскольку одному узлу может соответствовать несколько имен узлов, все из которых могут быть допустимыми ссылками на узел из клиентского приложения. Например, все следующие ссылки относятся к одному и тому же узлу:  
    >
    > - localhost  
    > - 127.0.0.1  
    > - `www.contoso.com`  
    > - ContosoWeb01  
  
4. Конечный фильтр должен поддерживать маршрутизацию сообщений, прибывающих в общую конечную точку без пользовательского заголовка. В этом сценарии сообщения должны отправляться либо в службу regularCalc, либо roundingCalc. Для поддержки "круглого робина" в направлении этих сообщений используйте пользовательский фильтр, который позволяет одному экземпляру фильтра совпадать с каждым обработанным сообщением.  В следующем примере определено два экземпляра фильтра RoundRobinMessageFilter, сгруппированных вместе, что означает, что они должны чередоваться.  
  
    ```xml  
    <!-- Set up the custom message filters.  In this example,   
         we'll use the example round robin message filter,   
         which alternates between the references-->  
    <filter name="RoundRobinFilter1" filterType="Custom"  
                    customType="CustomFilterAssembly.RoundRobinMessageFilter, CustomFilterAssembly"  
                    filterData="group1"/>  
    <filter name="RoundRobinFilter2" filterType="Custom"  
                    customType="CustomFilterAssembly.RoundRobinMessageFilter, CustomFilterAssembly"  
                    filterData="group1"/>  
    ```  
  
     Во время выполнения в этом типе фильтра чередуются все определенные экземпляры типа, настроенные в виде одной группы в одной коллекции. Это приводит к тому, что сообщения, `RoundRobinFilter1` `RoundRobinFilter2`обработанные этим пользовательским фильтром, чередуются между возвратом `true` и .  
  
### <a name="define-filter-tables"></a>Определение таблиц фильтров  
  
1. Чтобы связать фильтры с определенными клиентскими конечными точками, нужно поместить их в таблицу фильтров. В этом примере сценария также используются параметры приоритета фильтров, позволяющие указать очередность обработки фильтров. Если приоритет фильтров не задан, все фильтры вычисляются одновременно.  
  
    > [!NOTE]
    > Хотя заданный приоритет фильтров позволяет управлять очередностью обработки фильтров, он может неблагоприятно сказаться на производительности службы маршрутизации. Если возможно, логику фильтрации следует строить так, чтобы задавать приоритет фильтров не требовалось.  
  
     Ниже определяется таблица фильтров и добавляет "XPathFilter", определенный ранее в таблицу с приоритетом 2. В этой записи также указывается, что если сообщение `XPathFilter` совпадает `roundingCalcEndpoint`с сообщением, сообщение будет направлено в .  
  
    ```xml  
    <routing>  
    ...      <filters>  
    ...      </filters>  
          <filterTables>  
            <table name="filterTable1">  
              <entries>  
                <!--add the filters to the message filter table-->  
                <!--first look for the custom header, and if we find it,  
                    send the message to the rounding calc endpoint-->  
                <add filterName="XPathFilter" endpointName="roundingCalcEndpoint" priority="2"/>  
              </entries>  
            </table>  
          <filterTables>  
    </routing>  
    ```  
  
     Если приоритет фильтров задан, фильтр с наивысшим приоритетом выполняется первым. Если удовлетворены критерии одного или нескольких фильтров с одним уровнем приоритета, фильтры с более низкими уровнями приоритета обрабатываться не будут. В этом сценарии 2 это самый высокий указанный приоритет, на этом уровне имеется единственная запись фильтра.  
  
2. Записи фильтров были определены, чтобы путем проверки имени конечной точки или префикса адреса выяснить, получено ли сообщение в определенной конечной точке. В следующих записях обе записи фильтров добавляются в таблицу фильтров и связываются с целевыми конечными точками, в которые будут направляться сообщения. Для этих фильтров задан приоритет 1, чтобы указать, что они должны выполняться, только если сообщение не соответствует предыдущему фильтру XPath.  
  
    ```xml  
    <!--if the header wasn't there, send the message based on which virtual endpoint it arrived at-->  
    <!--we determine this through the endpoint name, or through the address prefix-->  
    <add filterName="EndpointNameFilter" endpointName="regularCalcEndpoint" priority="1"/>  
    <add filterName="PrefixAddressFilter" endpointName="roundingCalcEndpoint" priority="1"/>  
    ```  
  
     Поскольку для этих фильтров задан приоритет 1, они будут вычисляться, только если сообщение не соответствует фильтру с уровнем приоритета 2. Также, поскольку оба фильтра имеют одинаковый приоритет, они будут вычисляться одновременно. Поскольку эти два фильтра являются взаимоисключающими, сообщение может соответствовать только одному из них.  
  
3. Если сообщение не соответствует ни одному из предыдущих фильтров, это значит, что оно было получено через конечную точку общей службы и не содержит заголовка, указывающего, куда сообщение должно быть направлено. Эти сообщения должны обрабатываться пользовательским фильтром, который распределяет нагрузку между двумя службами калькуляторов. В следующем примере показано, как добавлять записи фильтров в таблицу фильтров. Каждый фильтр связывается с одной из двух целевых конечных точек.  
  
    ```xml  
    <!--if none of the other filters have matched,   
        this message showed up on the default router endpoint,   
        with no custom header-->  
    <!--round robin these requests between the two services-->  
    <add filterName="RoundRobinFilter1" endpointName="regularCalcEndpoint" priority="0"/>  
    <add filterName="RoundRobinFilter2" endpointName="roundingCalcEndpoint" priority="0"/>  
    ```  
  
     Поскольку для этих записей задан приоритет 0, они будут вычисляться, только если сообщение не соответствует ни одному фильтру с более высоким уровнем приоритета. Также, поскольку оба фильтра имеют одинаковый приоритет, они будут вычисляться одновременно.  
  
     Как упоминалось ранее, пользовательский фильтр, используемый этими определениями фильтров, возвращает значение `true` для каждого второго полученного сообщения. Поскольку только два фильтра с одинаковыми параметрами группы определены с использованием этого фильтра, служба маршрутизации поочередно отправляет сообщения в конечные точки regularCalcEndpoint и RoundingCalcEndpoint.  
  
4. Для оценки сообщений с помощью фильтров таблица фильтров должна быть связана с конечными точками службы, которые будут получать сообщения.  В приведенном ниже примере показано, как связать таблицу маршрутизации с конечными точками службы с помощью поведения маршрутизации.  
  
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
        <!--first create the general router endpoint-->  
        <endpoint address="general"  
                  binding="wsHttpBinding"  
                  name="routerEndpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
        <!--create a virtual endpoint for the regular calculator service-->  
        <endpoint address="regular/calculator"  
                  binding="wsHttpBinding"  
                  name="calculatorEndpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
        <!--now create a virtual endpoint for the rounding calculator-->  
        <endpoint address="rounding/calculator"  
                  binding="wsHttpBinding"  
                  name="roundingEndpoint"  
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
      <endpoint name="regularCalcEndpoint"  
                address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                binding="netTcpBinding"  
                contract="*" />  
  
      <endpoint name="roundingCalcEndpoint"  
                address="net.tcp://localhost:8080/servicemodelsamples/service/"  
                binding="netTcpBinding"  
                contract="*" />  
    </client>  
    <routing>  
      <!-- use the namespace table element to define a prefix for our custom namespace-->  
      <namespaceTable>  
        <add prefix="custom" namespace="http://my.custom.namespace/"/>  
      </namespaceTable>  
      <filters>  
        <!--define the different message filters-->  
        <!--define an xpath message filter to look for the custom header coming from the client-->  
        <filter name="XPathFilter" filterType="XPath" filterData="/s12:Envelope/s12:Header/custom:RoundingCalculator = 'rounding'"/>  
  
        <!--define an endpoint name filter looking for messages that show up on the virtual regular calculator endpoint-->  
        <filter name="EndpointNameFilter" filterType="EndpointName" filterData="calculatorEndpoint"/>  
  
        <!--define a filter looking for messages that show up with the address prefix.  The corresponds to the rounding calc virtual endpoint-->  
        <filter name="PrefixAddressFilter" filterType="PrefixEndpointAddress" filterData="http://localhost/routingservice/router/rounding/"/>  
  
        <!--Set up the custom message filters.  In this example, we'll use the example round robin message filter, which alternates between the references-->  
        <filter name="RoundRobinFilter1" filterType="Custom" customType="CustomFilterAssembly.RoundRobinMessageFilter, CustomFilterAssembly" filterData="group1"/>  
        <filter name="RoundRobinFilter2" filterType="Custom" customType="CustomFilterAssembly.RoundRobinMessageFilter, CustomFilterAssembly" filterData="group1"/>  
      </filters>  
      <filterTables>  
        <table name="filterTable1">  
          <entries>  
            <!--add the filters to the message filter table-->  
            <!--first look for the custom header, and if we find it, send the message to the rounding calc endpoint-->  
            <add filterName="XPathFilter" endpointName="roundingCalcEndpoint" priority="2"/>  
  
            <!--if the header wasn't there, send the message based on which virtual endpoint it arrived at-->  
            <!--we determine this through the endpoint name, or through the address prefix-->  
            <add filterName="EndpointNameFilter" endpointName="regularCalcEndpoint" priority="1"/>  
            <add filterName="PrefixAddressFilter" endpointName="roundingCalcEndpoint" priority="1"/>  
  
            <!--if none of the other filters have matched, this message showed up on the default router endpoint, with no custom header-->  
            <!--round robin these requests between the two services-->  
            <add filterName="RoundRobinFilter1" endpointName="regularCalcEndpoint" priority="0"/>  
            <add filterName="RoundRobinFilter2" endpointName="roundingCalcEndpoint" priority="0"/>  
          </entries>  
        </table>  
      </filterTables>  
    </routing>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также раздел

- [Службы маршрутизации](../../../../docs/framework/wcf/samples/routing-services.md)
