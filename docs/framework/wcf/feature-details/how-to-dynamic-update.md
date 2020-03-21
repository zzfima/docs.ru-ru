---
title: Как проводить динамическое обновление
ms.date: 03/30/2017
ms.assetid: 9b8f6e0d-edab-4a7e-86e3-8c66bebc64bb
ms.openlocfilehash: aaeb4d9d42c289cf34a6aee9212fc2d74b8f8c01
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184969"
---
# <a name="how-to-dynamic-update"></a>Как проводить динамическое обновление
В этом разделе описаны основные действия по созданию и динамическому обновлению конфигурации маршрутизации. В данном примере первоначальная конфигурация маршрутизации получена из файла конфигурации, согласно этой конфигурации все сообщения направляются службе калькулятора regularCalc. Однако впоследствии она будет программно обновлена, чтобы изменить конечную точку назначения на службу roundingCalc.  
  
> [!NOTE]
> Во многих системах используется полностью динамическая конфигурация, конфигурация по умолчанию при этом не используется. В некоторых случаях, как в этом разделе, желательно, чтобы при запуске службы конфигурация находилась в состоянии по умолчанию.  
  
> [!NOTE]
> Динамическое обновление выполняется только в памяти, сам файл конфигурации при этом не изменяется.  
  
 Обе службы, regularCalc и roundingCalc, поддерживают одинаковые операции сложения, вычитания, умножения и деления, однако служба roundingCalc, прежде чем возвратить результаты вычислений, округляет их до ближайшего целого числа. С помощью файла конфигурации выполняется настройка службы для перенаправления всех сообщений службе regularCalc. После запуска службы маршрутизации она перенастраивается с помощью метода <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> для перенаправления сообщений службе roundingCalc.  
  
### <a name="implement-initial-configuration"></a>Реализация первоначальной конфигурации  
  
1. Создайте базовую конфигурацию службы маршрутизации, указав конечные точки службы, предоставленные службой. В следующем примере определяется отдельная конечная точка службы, которая будет использоваться для получения сообщений. Также будет определена конечная точка клиента, которая будет использоваться для отправки сообщений службе regularCalc.  
  
    ```xml  
    <services>  
      <service behaviorConfiguration="routingConfiguration"  
               name="System.ServiceModel.Routing.RoutingService">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost/routingservice/router" />  
          </baseAddresses>  
        </host>  
        <!--Set up the inbound endpoint for the Routing Service-->  
        <endpoint address="calculator"  
                  binding="wsHttpBinding"  
                  name="routerEndpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
      </service>  
    </services>  
    <client>  
    <!--set up the destination endpoint-->  
      <endpoint name="regularCalcEndpoint"  
                address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                binding="netTcpBinding"  
                contract="*" />  
    </client>  
    ```  
  
2. Определите фильтр, используемый для перенаправления сообщений в конечные точки назначения. В этом примере фильтр MatchAll используется для перенаправления всех сообщений в заданную ранее конечную точку regularCalcEndpoint. Ниже приведен пример этого фильтра и таблицы фильтра.  
  
    ```xml  
    <filters>  
      <!--define the message filter-->  
      <filter name="MatchAllFilter" filterType="MatchAll"/>  
    </filters>  
    <filterTables>  
      <filterTable name="filterTable1">  
          <!--add the filter to the message filter table-->  
          <add filterName="MatchAllFilter" endpointName="regularCalcEndpoint"/>  
      </filterTable>  
    </filterTables>  
    ```  
  
3. Для оценки входящих сообщений с помощью фильтров, содержащихся в таблице фильтров, следует связать таблицу фильтров с конечными точками службы при помощи поведения маршрутизации. Следующий пример демонстрирует связь "filterTable1" с конечной точкой службы.  
  
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
  
## <a name="implement-dynamic-configuration"></a>Реализация динамической конфигурации  
 Динамическая настройка службы маршрутизации может выполняться только в коде путем создания нового экземпляра <xref:System.ServiceModel.Routing.RoutingConfiguration> и замены текущей конфигурации с помощью метода <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A>.  В этом примере служба маршрутизации является резидентной в консольном приложении. После запуска приложения изменить конфигурацию маршрутизации можно, введя в окне консоли «regular» или «rounding», чтобы настроить конечную току назначения, в которую будут направляться сообщения. При значении «regular» это regularCalc, в противном случае при значении «rounding» это roundingCalc.  
  
1. Для поддержки службы маршрутизации необходимо добавить следующие операторы using.  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.ServiceModel;  
    using System.ServiceModel.Channels;  
    using System.ServiceModel.Description;  
    using System.ServiceModel.Dispatcher;  
    using System.ServiceModel.Routing;  
    ```  
  
2. Чтобы сделать службу маршрутизации резидентной в консольном приложении, используется следующий код. Служба маршрутизации при этом инициализируется с конфигурацией, описанной в предыдущем шаге, которая содержится в файле конфигурации приложения. Цикл while содержит код, используемый для изменения конфигурации маршрутизации.  
  
    ```csharp  
    // Host the service within this EXE console application.  
    public static void Main()  
    {  
        // Create a ServiceHost for the CalculatorService type.  
        using (ServiceHost serviceHost =  
            new ServiceHost(typeof(RoutingService)))  
        {  
            // Open the ServiceHost to create listeners
            // and start listening for messages.  
            Console.WriteLine("The Routing Service configured, opening....");  
            serviceHost.Open();  
            Console.WriteLine("The Routing Service is now running.");  
             Console.WriteLine("Type 'quit' to terminate router.");  
             Console.WriteLine("<ENTER> to change routing configuration.");  
             while (Console.ReadLine() != "quit")  
             {  
            ....  
            }  
        }  
    }  
    ```  
  
3. Чтобы динамически обновить конфигурацию маршрутизации, необходимо создать новую конфигурацию маршрутизации. В ней должны быть указаны все конечные точки, фильтры и таблицы фильтров, которые требуются для новой конфигурации маршрутизации, поскольку она полностью заменит существующую конфигурацию маршрутизации. Чтобы использовать новую конфигурацию маршрутизации, необходимо вызвать метод <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> и передать новую конфигурацию.  
  
     Добавьте следующий код в определенный ранее цикл while, чтобы разрешить перенастройку службы с использованием пользовательского ввода.  
  
    ```csharp  
    Console.WriteLine("Enter 'regular' or 'rounding' to set the destination endpoint:");  
    string destEndpoint = Console.ReadLine();  
    // Create a new RoutingConfiguration  
    RoutingConfiguration rc = new RoutingConfiguration();  
    // Determine the endpoint to configure for  
    switch (destEndpoint)  
    {  
        case "regular":  
            // Define the destination endpoint  
            ServiceEndpoint regularCalc = new ServiceEndpoint(  
               ContractDescription.GetContract(typeof(IRequestReplyRouter)),  
               new NetTcpBinding(),  
               new EndpointAddress("net.tcp://localhost:9090/servicemodelsamples/service/"));  
            // Create a MatchAll filter and add to the filter table  
            rc.FilterTable.Add(new MatchAllMessageFilter(), new List<ServiceEndpoint> { regularCalc });  
            // Use ApplyConfiguration to update the Routing Service  
            serviceHost.Extensions.Find<RoutingExtension>().ApplyConfiguration(rc);  
            Console.WriteLine("Applied new routing configuration.");  
            break;  
        case "rounding":  
            // Define the destination endpoint  
            ServiceEndpoint roundingCalc = new ServiceEndpoint(  
               ContractDescription.GetContract(typeof(IRequestReplyRouter)),  
               new NetTcpBinding(),  
               new EndpointAddress("net.tcp://localhost:8080/servicemodelsamples/service/"));  
            // Create a MatchAll filter and add to the filter table  
            rc.FilterTable.Add(new MatchAllMessageFilter(), new List<ServiceEndpoint> { roundingCalc });  
            // Use ApplyConfiguration to update the Routing Service  
            serviceHost.Extensions.Find<RoutingExtension>().ApplyConfiguration(rc);  
            Console.WriteLine("Applied new routing configuration.");  
            break;  
        default:  
            Console.WriteLine("Incorrect value entered, no change.");  
            break;  
    }  
    ```  
  
    > [!NOTE]
    > Поскольку метод для предоставления новой конфигурации маршрутизации содержится в расширении службы RoutingExtension, новые объекты RoutingConfiguration могут быть предоставлены в любом месте модели расширяемости WCF, которая имеет или может получить ссылку на ServiceHost или ServiceExtensions (например, в другом ServiceExtension).
  
## <a name="example"></a>Пример  

Ниже приводится полный список консольного приложения, используемого в этом примере:
  
```csharp
//-----------------------------------------------------------------  
//  Copyright (c) Microsoft Corporation.  All Rights Reserved.  
//-----------------------------------------------------------------  
  
using System;  
using System.Collections.Generic;  
using System.ServiceModel;  
using System.ServiceModel.Channels;  
using System.ServiceModel.Description;  
using System.ServiceModel.Dispatcher;  
using System.ServiceModel.Routing;  
  
namespace Microsoft.Samples.AdvancedFilters  
{  
    public class Router  
    {  
        // Host the service within this EXE console application.  
        public static void Main()  
        {
            // Create a ServiceHost for the CalculatorService type.  
            using (ServiceHost serviceHost =  
                new ServiceHost(typeof(RoutingService)))  
            {  
                // Open the ServiceHost to create listeners
                // and start listening for messages.  
                Console.WriteLine("The Routing Service configured, opening....");  
                serviceHost.Open();  
                Console.WriteLine("The Routing Service is now running.");  
                Console.WriteLine("Type 'quit' to terminate router.");  
                Console.WriteLine("<ENTER> to change routing configuration.");  
                while (Console.ReadLine() != "quit")  
                {  
                    Console.WriteLine("Enter 'regular' or 'rounding' to set the destination endpoint:");  
                    string destEndpoint = Console.ReadLine();  
                    // Create a new RoutingConfiguration  
                    RoutingConfiguration rc = new RoutingConfiguration();  
                    // Determine the endpoint to configure for  
                    switch (destEndpoint)  
                    {  
                        case "regular":  
                            // Define the destination endpoint  
                            ServiceEndpoint regularCalc = new ServiceEndpoint(  
                            ContractDescription.GetContract(typeof(IRequestReplyRouter)),  
                            new NetTcpBinding(),  
                            new EndpointAddress("net.tcp://localhost:9090/servicemodelsamples/service/"));  
                            // Create a MatchAll filter and add to the filter table  
                            rc.FilterTable.Add(new MatchAllMessageFilter(), new List<ServiceEndpoint> { regularCalc });  
                            // Use ApplyConfiguration to update the Routing Service  
                            serviceHost.Extensions.Find<RoutingExtension>().ApplyConfiguration(rc);  
                            Console.WriteLine("Applied new routing configuration.");  
                            break;  
                        case "rounding":  
                            // Define the destination endpoint  
                            ServiceEndpoint roundingCalc = new ServiceEndpoint(  
                                ContractDescription.GetContract(typeof(IRequestReplyRouter)),  
                                new NetTcpBinding(),  
                                new EndpointAddress("net.tcp://localhost:8080/servicemodelsamples/service/"));  
                            // Create a MatchAll filter and add to the filter table  
                            rc.FilterTable.Add(new MatchAllMessageFilter(), new List<ServiceEndpoint> { roundingCalc });  
                            // Use ApplyConfiguration to update the Routing Service  
                            serviceHost.Extensions.Find<RoutingExtension>().ApplyConfiguration(rc);  
                            Console.WriteLine("Applied new routing configuration.");  
                            break;  
                        default:  
                            Console.WriteLine("Incorrect value entered, no change.");  
                            break;  
                    }  
                }  
            }  
        }  
    }  
}  
```  
  
## <a name="example"></a>Пример  

Ниже приводится полный список файла конфигурации, используемого в этом примере:
  
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
        <!--Set up the inbound endpoint for the Routing Service-->  
        <endpoint address="calculator"  
                  binding="wsHttpBinding"  
                  name="routerEndpoint"  
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
<!--set up the destination endpoint-->  
      <endpoint name="regularCalcEndpoint"  
                address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                binding="netTcpBinding"  
                contract="*" />  
    </client>  
    <routing>  
  
      <filters>  
        <!--define the message filter-->  
        <filter name="MatchAllFilter" filterType="MatchAll"/>  
      </filters>  
      <filterTables>  
        <filterTable name="filterTable1">  
            <!--add the filter to the message filter table-->  
            <add filterName="MatchAllFilter" endpointName="regularCalcEndpoint"/>  
        </filterTable>  
      </filterTables>  
    </routing>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также раздел

- [Службы маршрутизации](../samples/routing-services.md)
