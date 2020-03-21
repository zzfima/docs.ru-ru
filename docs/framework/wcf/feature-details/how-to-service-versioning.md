---
title: Как управлять версиями службы
ms.date: 03/30/2017
ms.assetid: 4287b6b3-b207-41cf-aebe-3b1d4363b098
ms.openlocfilehash: 3cd52e1f52a93e408ebed846894cc5686652cc91
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184847"
---
# <a name="how-to-service-versioning"></a><span data-ttu-id="b6d92-102">Как управлять версиями службы</span><span class="sxs-lookup"><span data-stu-id="b6d92-102">How To: Service Versioning</span></span>
<span data-ttu-id="b6d92-103">В этом разделе описаны основные шаги, которые необходимо выполнить для создания конфигурации маршрутизации сообщений к разным версиям одной и той же службы.</span><span class="sxs-lookup"><span data-stu-id="b6d92-103">This topic outlines the basic steps required to create a routing configuration that routes messages to different versions of the same service.</span></span> <span data-ttu-id="b6d92-104">В этом примере сообщения направляются в две разные версии службы калькулятора: `roundingCalc` (v1) и `regularCalc` (v2).</span><span class="sxs-lookup"><span data-stu-id="b6d92-104">In this example, messages are routed to two different versions of a calculator service, `roundingCalc` (v1) and `regularCalc` (v2).</span></span> <span data-ttu-id="b6d92-105">Обе реализации поддерживают одинаковые операции, однако старая версия службы `roundingCalc`, прежде чем вернуть результаты вычислений, округляет их до ближайшего целого числа.</span><span class="sxs-lookup"><span data-stu-id="b6d92-105">Both implementations support the same operations; however the older service, `roundingCalc`, rounds all calculations to the nearest integer value before returning.</span></span> <span data-ttu-id="b6d92-106">Клиентское приложение должно указать необходимость использования более новой версии службы `regularCalc`.</span><span class="sxs-lookup"><span data-stu-id="b6d92-106">A client application must be able to indicate whether to use the newer `regularCalc` service.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="b6d92-107">Для передачи сообщения указанной версии службы служба маршрутизации определяет место назначения сообщения на основе его содержимого.</span><span class="sxs-lookup"><span data-stu-id="b6d92-107">In order to route a message to a specific service version, the Routing Service must be able to determine the message destination based on the message content.</span></span> <span data-ttu-id="b6d92-108">В показанном ниже методе клиент указывает версию в заголовке сообщения.</span><span class="sxs-lookup"><span data-stu-id="b6d92-108">In the method demonstrated below, the client will specify the version by inserting information into a message header.</span></span> <span data-ttu-id="b6d92-109">Существуют методы управления версиями служб, которые не требуют передачи дополнительных данных клиентом.</span><span class="sxs-lookup"><span data-stu-id="b6d92-109">There are methods of service versioning that do not require clients to pass additional data.</span></span> <span data-ttu-id="b6d92-110">Например, сообщение может быть отправлено самой последней или наиболее совместимой версии службы либо маршрутизатор может использовать часть стандартного конверта SOAP.</span><span class="sxs-lookup"><span data-stu-id="b6d92-110">For example, a message could be routed to the most recent or most compatible version of a service or the router could use a part of the standard SOAP envelope.</span></span>  
  
 <span data-ttu-id="b6d92-111">Операции, предоставляемые обеими службами:</span><span class="sxs-lookup"><span data-stu-id="b6d92-111">The operations exposed by both services are:</span></span>  
  
- <span data-ttu-id="b6d92-112">Добавить</span><span class="sxs-lookup"><span data-stu-id="b6d92-112">Add</span></span>  
  
- <span data-ttu-id="b6d92-113">Вычитание</span><span class="sxs-lookup"><span data-stu-id="b6d92-113">Subtract</span></span>  
  
- <span data-ttu-id="b6d92-114">Умножение</span><span class="sxs-lookup"><span data-stu-id="b6d92-114">Multiply</span></span>  
  
- <span data-ttu-id="b6d92-115">Деление</span><span class="sxs-lookup"><span data-stu-id="b6d92-115">Divide</span></span>  
  
 <span data-ttu-id="b6d92-116">Поскольку обе реализации служб обрабатывают одни и те же операции и, в сущности, отличаются только возвращаемыми данных, базовые данные, содержащиеся в сообщениях, отправленных клиентскими приложениями, не являются достаточно уникальными, чтобы можно было определить способ маршрутизации запроса.</span><span class="sxs-lookup"><span data-stu-id="b6d92-116">Because both service implementations handle the same operations, and are essentially identical other than the data that they return, the base data contained in messages sent from client applications is not unique enough to allow you to determine how to route the request.</span></span> <span data-ttu-id="b6d92-117">Например, нельзя использовать фильтры действий, поскольку действия по умолчанию одинаковы для обеих служб.</span><span class="sxs-lookup"><span data-stu-id="b6d92-117">For example, Action filters cannot be used because the default actions for both services are the same.</span></span>  
  
 <span data-ttu-id="b6d92-118">Эту ситуацию можно разрешить несколькими способами, например сделав конкретную конечную точку доступной маршрутизатору для каждой версии службы или добавив в сообщение пользовательский элемент заголовка, указывающий версию службы.</span><span class="sxs-lookup"><span data-stu-id="b6d92-118">This can be resolved in several ways, such as exposing a specific endpoint on the router for each version of the service or adding a custom header element to the message to indicate service version.</span></span>  <span data-ttu-id="b6d92-119">Все эти подходы позволяют выполнять уникальную маршрутизацию входящих сообщений для указанной версии службы, но для разграничения запросов для разных версий служб рекомендуется использование уникального содержимого сообщения.</span><span class="sxs-lookup"><span data-stu-id="b6d92-119">Each of these approaches allows you to uniquely route incoming messages to a specific version of the service, but utilizing unique message content is the preferred method of differentiating between requests for different service versions.</span></span>  
  
 <span data-ttu-id="b6d92-120">В данном примере клиентское приложение добавляет пользовательский заголовок CalcVer в сообщение запроса.</span><span class="sxs-lookup"><span data-stu-id="b6d92-120">In this example, the client application adds the ‘CalcVer’ custom header to the request message.</span></span> <span data-ttu-id="b6d92-121">Этот заголовок содержит значение, указывающее версию службы, которой должно быть передано сообщение.</span><span class="sxs-lookup"><span data-stu-id="b6d92-121">This header will contain a value that indicates the version of the service that the message should be routed to.</span></span> <span data-ttu-id="b6d92-122">Значение «1» указывает на то, что сообщение должно быть обработано службой roundingCalc, а значение «2» - службой regularCalc.</span><span class="sxs-lookup"><span data-stu-id="b6d92-122">A value of ‘1’ indicates that the message must be processed by the roundingCalc service, while a value of ‘2’ indicates the regularCalc service.</span></span> <span data-ttu-id="b6d92-123">Это позволяет клиентскому приложению непосредственно управлять версиями службы, которые будут обрабатывать сообщение.</span><span class="sxs-lookup"><span data-stu-id="b6d92-123">This allows the client application to directly control which version of the service will process the message.</span></span>  <span data-ttu-id="b6d92-124">Поскольку пользовательский заголовок является значением, содержащимся в сообщении, можно использовать одну конечную точку для получения сообщений, предназначенных для обеих версий службы.</span><span class="sxs-lookup"><span data-stu-id="b6d92-124">Since the custom header is a value contained within the message, you can use one endpoint to receive messages destined for both versions of the service.</span></span> <span data-ttu-id="b6d92-125">Для добавления пользовательского заголовка сообщения включить в клиентское приложение следующий код:</span><span class="sxs-lookup"><span data-stu-id="b6d92-125">The following code can be used in the client application to add this custom header to the message:</span></span>  
  
```csharp  
messageHeadersElement.Add(MessageHeader.CreateHeader("CalcVer", "http://my.custom.namespace/", "2"));  
```  
  
### <a name="implement-service-versioning"></a><span data-ttu-id="b6d92-126">Реализация управления версиями</span><span class="sxs-lookup"><span data-stu-id="b6d92-126">Implement Service Versioning</span></span>  
  
1. <span data-ttu-id="b6d92-127">Создайте базовую конфигурацию службы маршрутизации, указав конечную точку службы, предоставленную службой.</span><span class="sxs-lookup"><span data-stu-id="b6d92-127">Create the basic Routing Service configuration by specifying the service endpoint exposed by the service.</span></span> <span data-ttu-id="b6d92-128">В следующем примере определяется отдельная конечная точка службы, которая будет использоваться для получения сообщений.</span><span class="sxs-lookup"><span data-stu-id="b6d92-128">The following example defines a single service endpoint, which will be used to receive messages.</span></span> <span data-ttu-id="b6d92-129">Также определяются конечные точки клиента, которые используются для передачи сообщений службам `roundingCalc` (v1) и `regularCalc` (v2).</span><span class="sxs-lookup"><span data-stu-id="b6d92-129">It also defines the client endpoints which will be used to send messages to the `roundingCalc` (v1) and the `regularCalc` (v2) services.</span></span>  
  
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
    <!--set up the destination endpoints-->  
          <endpoint name="regularCalcEndpoint"  
                    address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                    binding="netTcpBinding"  
                    contract="*" />  
  
          <endpoint name="roundingCalcEndpoint"  
                    address="http://localhost:8080/servicemodelsamples/service/"  
                    binding="wsHttpBinding"  
                    contract="*" />  
        </client>  
    ```  
  
2. <span data-ttu-id="b6d92-130">Определите фильтры, используемые для маршрутизации сообщений до конечных точек назначения.</span><span class="sxs-lookup"><span data-stu-id="b6d92-130">Define the filters used to route messages to the destination endpoints.</span></span>  <span data-ttu-id="b6d92-131">В этом примере фильтр XPath используется для определения значения пользовательского заголовка "CalcVer", чтобы определить, к какой версии следует направить сообщение.</span><span class="sxs-lookup"><span data-stu-id="b6d92-131">For this example, the XPath filter is used to detect the value of the "CalcVer" custom header to determine which version the message should be routed to.</span></span> <span data-ttu-id="b6d92-132">Фильтр XPath также используется для обнаружения сообщений, которые не содержат заголовок "CalcVer".</span><span class="sxs-lookup"><span data-stu-id="b6d92-132">An XPath filter is also used to detect messages that do not contain the "CalcVer" header.</span></span> <span data-ttu-id="b6d92-133">В следующем примере определяются необходимые фильтры и таблица пространства имен.</span><span class="sxs-lookup"><span data-stu-id="b6d92-133">The following example defines the required filters and namespace table.</span></span>  
  
    ```xml  
    <!-- use the namespace table element to define a prefix for our custom namespace-->  
    <namespaceTable>  
      <add prefix="custom" namespace="http://my.custom.namespace/"/>  
    </namespaceTable>  
    <filters>  
      <!--define the different message filters-->  
      <!--define an xpath message filter to look for the  
          custom header containing a value of 2-->  
      <filter name="XPathFilterRegular" filterType="XPath"  
              filterData="sm:header()/custom:CalcVer = '2'"/>  
      <!--define an xpath message filter to look for the  
          custom header containing a value of 1-->  
      <filter name="XPathFilterRounding" filterType="XPath"  
              filterData="sm:header()/custom:CalcVer = '1'"/>  
       <!--define an xpath message filter to look for  
           messages that do not contain the custom header-->  
       <filter name="XPathFilterNoHeader" filterType="XPath"  
               filterData="count(sm:header()/custom:CalcVer)=0"/>  
    </filters  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="b6d92-134">Префикс пространства имен s12 определяется по умолчанию в таблице `http://www.w3.org/2003/05/soap-envelope`пространства имен и представляет пространство имен.</span><span class="sxs-lookup"><span data-stu-id="b6d92-134">The s12 namespace prefix is defined by default in the namespace table, and represents the namespace `http://www.w3.org/2003/05/soap-envelope`.</span></span>
  
3. <span data-ttu-id="b6d92-135">Определите таблицу фильтров, которая связывает каждый фильтр с клиентской конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="b6d92-135">Define the filter table, which associates each filter with a client endpoint.</span></span> <span data-ttu-id="b6d92-136">Если сообщение содержит заголовок "CalcVer" со значением 1, оно будет отправлено в обычную службу Calc.</span><span class="sxs-lookup"><span data-stu-id="b6d92-136">If the message contains the "CalcVer" header with a value of 1, it will be sent to the regularCalc service.</span></span> <span data-ttu-id="b6d92-137">Если сообщение содержит заголовок CalcVer со значением «2», то оно будет передано службе roundingCalc.</span><span class="sxs-lookup"><span data-stu-id="b6d92-137">If the header contains a value of 2, it will be sent to the roundingCalc service.</span></span> <span data-ttu-id="b6d92-138">Если заголовок отсутствует, то сообщение будет передано regularCalc.</span><span class="sxs-lookup"><span data-stu-id="b6d92-138">If no header is present, the message will be routed to the regularCalc.</span></span>  
  
     <span data-ttu-id="b6d92-139">Далее будет определена таблица фильтров, а также добавлены определенные ранее фильтры.</span><span class="sxs-lookup"><span data-stu-id="b6d92-139">The following defines the filter table and adds the filters defined earlier.</span></span>  
  
    ```xml  
    <filterTables>  
      <filterTable name="filterTable1">  
          <!--add the filters to the message filter table-->  
          <!--look for the custom header = 1, and if we find it,  
              send the message to the rounding calc endpoint-->  
          <add filterName="XPathFilterRounding" endpointName="roundingCalcEndpoint"/>  
          <!--look for the custom header = 2, and if we find it,  
              send the message to the rounding calc endpoint-->  
          <add filterName="XPathFilterRegular" endpointName="regularCalcEndpoint"/>  
          <!--look for the absence of the custom header, and if  
              it is not present, assume the v1 endpoint-->  
          <add filterName="XPathFilterNoHeader" endpointName="roundingCalcEndpoint"/>  
      </filterTable>  
    </filterTables>  
    ```  
  
4. <span data-ttu-id="b6d92-140">Для оценки входящих сообщений с помощью фильтров, содержащихся в таблице фильтров, следует связать таблицу фильтров с конечными точками службы при помощи поведения маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="b6d92-140">To evaluate incoming messages against the filters contained in the filter table, you must associate the filter table with the service endpoints by using the routing behavior.</span></span> <span data-ttu-id="b6d92-141">Следующий пример демонстрирует связь `filterTable1` с конечными точками службы:</span><span class="sxs-lookup"><span data-stu-id="b6d92-141">The following example demonstrates associating `filterTable1` with the service endpoints:</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="b6d92-142">Пример</span><span class="sxs-lookup"><span data-stu-id="b6d92-142">Example</span></span>  
 <span data-ttu-id="b6d92-143">Далее приведен полный листинг файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b6d92-143">The following is a complete listing of the configuration file.</span></span>  
  
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
<!--set up the destination endpoints-->  
      <endpoint name="regularCalcEndpoint"  
                address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                binding="netTcpBinding"  
                contract="*" />  
  
      <endpoint name="roundingCalcEndpoint"  
                address="http://localhost:8080/servicemodelsamples/service/"  
                binding="wsHttpBinding"  
                contract="*" />  
    </client>  
    <routing>  
      <!-- use the namespace table element to define a prefix for our custom namespace-->  
      <namespaceTable>  
        <add prefix="custom" namespace="http://my.custom.namespace/"/>  
      </namespaceTable>  
      <filters>  
        <!--define the different message filters-->  
        <!--define an xpath message filter to look for the  
            custom header containing a value of 2-->  
        <filter name="XPathFilterRegular" filterType="XPath"  
                filterData="sm:header()/custom:CalcVer = '2'"/>  
        <!--define an xpath message filter to look for the  
            custom header containing a value of 1-->  
        <filter name="XPathFilterRounding" filterType="XPath"  
                filterData="sm:header()/custom:CalcVer = '1'"/>  
        <!--define an xpath message filter to look for  
            messages that do not contain the custom header-->  
        <filter name="XPathFilterNoHeader" filterType="XPath"  
                filterData="count(sm:header()/custom:CalcVer)=0"/>  
      </filters>  
      <filterTables>  
        <filterTable name="filterTable1">  
            <!--add the filters to the message filter table-->  
            <!--look for the custom header = 1, and if we find it,  
                send the message to the rounding calc endpoint-->  
            <add filterName="XPathFilterRounding" endpointName="roundingCalcEndpoint"/>  
            <!--look for the custom header = 2, and if we find it,  
                send the message to the rounding calc endpoint-->  
            <add filterName="XPathFilterRegular" endpointName="regularCalcEndpoint"/>  
            <!--look for the absence of the custom header, and if  
                it is not present, assume the v1 endpoint-->  
            <add filterName="XPathFilterNoHeader" endpointName="roundingCalcEndpoint"/>  
        </filterTable>  
      </filterTables>  
    </routing>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="b6d92-144">Пример</span><span class="sxs-lookup"><span data-stu-id="b6d92-144">Example</span></span>  
 <span data-ttu-id="b6d92-145">Ниже приведен полный листинг клиентского приложения.</span><span class="sxs-lookup"><span data-stu-id="b6d92-145">The following is a complete listing of the client application.</span></span>  
  
```csharp  
using System;  
using System.ServiceModel;  
using System.ServiceModel.Channels;  
  
namespace Microsoft.Samples.AdvancedFilters  
{  
    //The service contract is defined in generatedClient.cs, generated from the service by the svcutil tool.  
  
    //Client implementation code.  
    class Client  
    {  
        static void Main()  
        {  
            //Print out the welcome text  
            Console.WriteLine("This sample routes the Calculator Sample through the new WCF RoutingService");  
            Console.WriteLine("Wait for all the services to indicate that they've started, then press");  
            Console.WriteLine("<ENTER> to start the client.");  
  
            while (Console.ReadLine() != "quit")  
            {  
                //Offer the Address configuration for the client  
                Console.WriteLine("");  
                Console.WriteLine("Welcome to the Calculator Client!");  
  
                EndpointAddress epa;  
                //set the default address as the general router endpoint  
                epa = new EndpointAddress("http://localhost/routingservice/router/calculator");  
  
                //set up the CalculatorClient with the EndpointAddress, the WSHttpBinding, and the ICalculator contract  
                //We use the WSHttpBinding so that the outgoing has a message envelope, which we'll manipulate in a minute  
                CalculatorClient client = new CalculatorClient(new WSHttpBinding(), epa);  
                //client.Endpoint.Contract = ContractDescription.GetContract(typeof(ICalculator));  
  
                //Ask the customer if they want to add a custom header to the outgoing message.  
                //The Router will look for this header, and if so ignore the endpoint the message was  
                //received on, and instead direct the message to the RoundingCalcService.  
                Console.WriteLine("");  
                Console.WriteLine("Which calculator service should be used?");  
                Console.WriteLine("Enter 1 for the rounding calculator, 2 for the regular calculator.");  
                Console.WriteLine("[1] or [2]?");  
  
                string header = Console.ReadLine();  
  
                //get the current operationContextScope from the client's inner channel  
                using (OperationContextScope ocs = new OperationContextScope((client.InnerChannel)))  
                {  
                    //get the outgoing message headers element (collection) from the context  
                    MessageHeaders messageHeadersElement = OperationContext.Current.OutgoingMessageHeaders;  
  
                    //if they wanted to create the header, go ahead and add it to the outgoing message  
                    if (header != null && (header=="1" || header=="2"))  
                    {  
                        //create a new header "RoundingCalculator", no specific namespace, and set the value to
                        //the value of header.  
                        //the Routing Service will look for this header in order to determine if the message  
                        //should be routed to the RoundingCalculator  
                        messageHeadersElement.Add(MessageHeader.CreateHeader("CalcVer", "http://my.custom.namespace/", header));  
                    }  
                    else //incorrect choice, no header added  
                    {  
                        Console.WriteLine("Incorrect value entered, not adding a header");  
                    }  
  
                        //call the client operations  
                        CallClient(client);  
                }  
  
                //close the client to clean it up  
                client.Close();  
                Console.WriteLine();  
                Console.WriteLine("Press <ENTER> to run the client again or type 'quit' to quit.");  
            }  
        }  
  
        private static void CallClient(CalculatorClient client)  
        {  
            Console.WriteLine("");  
            Console.WriteLine("Sending!");  
            // Call the Add service operation.  
            double value1 = 100.00D;  
            double value2 = 15.99D;  
            double result = client.Add(value1, value2);  
            Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
            // Call the Subtract service operation.  
            value1 = 145.00D;  
            value2 = 76.54D;  
            result = client.Subtract(value1, value2);  
            Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);  
  
            // Call the Multiply service operation.  
            value1 = 9.00D;  
            value2 = 81.25D;  
            result = client.Multiply(value1, value2);  
            Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);  
  
            // Call the Divide service operation.  
            value1 = 22.00D;  
            value2 = 7.00D;  
            result = client.Divide(value1, value2);  
            Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="b6d92-146">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b6d92-146">See also</span></span>

- [<span data-ttu-id="b6d92-147">Службы маршрутизации</span><span class="sxs-lookup"><span data-stu-id="b6d92-147">Routing Services</span></span>](../../../../docs/framework/wcf/samples/routing-services.md)
