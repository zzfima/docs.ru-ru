---
title: Практическое руководство. Использование клиента Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- WCF clients [WCF], using
ms.assetid: 190349fc-0573-49c7-bb85-8e316df7f31f
ms.openlocfilehash: 79431588e27b02a40d5898929f1bdf644c8a79cd
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33803810"
---
# <a name="how-to-use-a-windows-communication-foundation-client"></a><span data-ttu-id="a9439-102">Практическое руководство. Использование клиента Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="a9439-102">How to: Use a Windows Communication Foundation Client</span></span>
<span data-ttu-id="a9439-103">Это последний из шести шагов, необходимых для создания базового приложения Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="a9439-103">This is the last of six tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="a9439-104">Общие сведения обо всех шести задач см. в разделе [учебник по началу работы](../../../docs/framework/wcf/getting-started-tutorial.md) раздела.</span><span class="sxs-lookup"><span data-stu-id="a9439-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>  
  
 <span data-ttu-id="a9439-105">После создания и настройки прокси службы Windows Communication Foundation (WCF) можно создать экземпляр клиента и клиентское приложение можно скомпилировать и использовать для взаимодействия со службой WCF.</span><span class="sxs-lookup"><span data-stu-id="a9439-105">Once a Windows Communication Foundation (WCF) proxy has been created and configured, a client instance can be created and the client application can be compiled and used to communicate with the WCF service.</span></span> <span data-ttu-id="a9439-106">В этом разделе описаны процедуры создания и использования клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="a9439-106">This topic describes procedures for instantiating and using a WCF client.</span></span> <span data-ttu-id="a9439-107">Эта процедура выполняет три операции.</span><span class="sxs-lookup"><span data-stu-id="a9439-107">This procedure does three things:</span></span>  
  
1.  <span data-ttu-id="a9439-108">Создает экземпляр класса клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="a9439-108">Instantiates a WCF client.</span></span>  
  
2.  <span data-ttu-id="a9439-109">Вызывает операции службы из созданной учетной записи-посредника.</span><span class="sxs-lookup"><span data-stu-id="a9439-109">Calls the service operations from the generated proxy.</span></span>  
  
3.  <span data-ttu-id="a9439-110">Закрывает клиент после завершения вызова операции.</span><span class="sxs-lookup"><span data-stu-id="a9439-110">Closes the client once the operation call is completed.</span></span>  
  
### <a name="to-use-a-windows-communication-foundation-client"></a><span data-ttu-id="a9439-111">Использование клиента Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="a9439-111">To use a Windows Communication Foundation client</span></span>  
  
1.  <span data-ttu-id="a9439-112">Откройте файл Program.cs или Program.vb из проекта GettingStartedClient и замените существующий код в файлах следующим:</span><span class="sxs-lookup"><span data-stu-id="a9439-112">Open the Program.cs or Program.vb file from the GettingStartedClient project and replace the existing code with the following code:</span></span>  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using GettingStartedClient.ServiceReference1;  
  
    namespace GettingStartedClient  
    {  
        class Program  
        {  
            static void Main(string[] args)  
            {  
                //Step 1: Create an instance of the WCF proxy.  
                CalculatorClient client = new CalculatorClient();  
  
                // Step 2: Call the service operations.  
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
  
                //Step 3: Closing the client gracefully closes the connection and cleans up resources.  
                client.Close();  
            }  
        }  
    }  
    ```  
  
    ```  
    Imports System  
    Imports System.Collections.Generic  
    Imports System.Text  
    Imports System.ServiceModel  
    Imports GettingStartedClientVB2.ServiceReference1  
  
    Module Module1  
  
        Sub Main()  
            ' Step 1: Create an instance of the WCF proxy  
            Dim Client As New CalculatorClient()  
  
            'Step 2: Call the service operations.  
            'Call the Add service operation.  
            Dim value1 As Double = 100D  
            Dim value2 As Double = 15.99D  
            Dim result As Double = Client.Add(value1, value2)  
            Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)  
  
            'Call the Subtract service operation.  
            value1 = 145D  
            value2 = 76.54D  
            result = Client.Subtract(value1, value2)  
            Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result)  
  
            'Call the Multiply service operation.  
            value1 = 9D  
            value2 = 81.25D  
            result = Client.Multiply(value1, value2)  
            Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result)  
  
            'Call the Divide service operation.  
            value1 = 22D  
            value2 = 7D  
            result = Client.Divide(value1, value2)  
            Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result)  
  
            ' Step 3: Closing the client gracefully closes the connection and cleans up resources.  
            Client.Close()  
  
            Console.WriteLine()  
            Console.WriteLine("Press <ENTER> to terminate client.")  
            Console.ReadLine()  
  
        End Sub  
  
    End Module  
    ```  
  
     <span data-ttu-id="a9439-113">Обратите внимание на инструкции using и imports для импорта GettingStartedClient.ServiceReference1.</span><span class="sxs-lookup"><span data-stu-id="a9439-113">Notice the using or imports statement that imports the GettingStartedClient.ServiceReference1.</span></span> <span data-ttu-id="a9439-114">Эта инструкция импортирует код, созданный функцией «Добавить ссылки на службу» средства Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a9439-114">This imports the code generated by Add Service Reference in Visual Studio.</span></span> <span data-ttu-id="a9439-115">Код создает WCF-прокси и затем вызывает каждую операцию службы, предоставленную службой калькулятора, закрывает прокси и завершает работу.</span><span class="sxs-lookup"><span data-stu-id="a9439-115">The code instantiates the WCF proxy and then calls each of the service operations exposed by the calculator service, closes the proxy and terminates.</span></span>  
  
 <span data-ttu-id="a9439-116">Вы завершили работу с учебником.</span><span class="sxs-lookup"><span data-stu-id="a9439-116">You have now completed the tutorial.</span></span> <span data-ttu-id="a9439-117">Был определен и реализован контракт службы, создан WCF-прокси, настроено клиентское приложение WCF, и использованы прокси для вызова операций службы.</span><span class="sxs-lookup"><span data-stu-id="a9439-117">You defined a service contract, implemented the service contract, generated a WCF proxy, configured a WCF client application, and then used the proxy to call service operations.</span></span> <span data-ttu-id="a9439-118">Чтобы проверить приложение, сначала запустите GettingStartedHost для запуска службы, а затем сам клиент GettingStartedClient.</span><span class="sxs-lookup"><span data-stu-id="a9439-118">To test out the application first run GettingStartedHost to start the service and then run GettingStartedClient.</span></span> <span data-ttu-id="a9439-119">Вывод из GettingStartedHost должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a9439-119">The output from GettingStartedHost should look like this:</span></span>  
  
```Output  
The service is ready.Press <ENTER> to terminate service.Received Add(100,15.99)Return: 115.99Received Subtract(145,76.54)Return: 68.46Received Multiply(9,81.25)Return: 731.25Received Divide(22,7)Return: 3.14285714285714  
```  
  
 <span data-ttu-id="a9439-120">Вывод GettingStartedClient должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a9439-120">The output from GettingStartedClient should look like this:</span></span>  
  
```Output  
Add(100,15.99) = 115.99Subtract(145,76.54) = 68.46Multiply(9,81.25) = 731.25Divide(22,7) = 3.14285714285714Press <ENTER> to terminate client.  
```  
  
## <a name="see-also"></a><span data-ttu-id="a9439-121">См. также</span><span class="sxs-lookup"><span data-stu-id="a9439-121">See Also</span></span>  
 [<span data-ttu-id="a9439-122">Создание клиентов</span><span class="sxs-lookup"><span data-stu-id="a9439-122">Building Clients</span></span>](../../../docs/framework/wcf/building-clients.md)  
 [<span data-ttu-id="a9439-123">Практическое руководство. Создание клиента</span><span class="sxs-lookup"><span data-stu-id="a9439-123">How to: Create a Client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [<span data-ttu-id="a9439-124">Руководство по началу работы</span><span class="sxs-lookup"><span data-stu-id="a9439-124">Getting Started Tutorial</span></span>](../../../docs/framework/wcf/getting-started-tutorial.md)  
 [<span data-ttu-id="a9439-125">Базовое программирование для WCF</span><span class="sxs-lookup"><span data-stu-id="a9439-125">Basic WCF Programming</span></span>](../../../docs/framework/wcf/basic-wcf-programming.md)  
 [<span data-ttu-id="a9439-126">Практическое руководство. Создание дуплексного контракта</span><span class="sxs-lookup"><span data-stu-id="a9439-126">How to: Create a Duplex Contract</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)  
 [<span data-ttu-id="a9439-127">Практическое руководство. Доступ к службам с дуплексным контрактом</span><span class="sxs-lookup"><span data-stu-id="a9439-127">How to: Access Services with a Duplex Contract</span></span>](../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)  
 [<span data-ttu-id="a9439-128">Начало работы</span><span class="sxs-lookup"><span data-stu-id="a9439-128">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [<span data-ttu-id="a9439-129">Резидентное размещение</span><span class="sxs-lookup"><span data-stu-id="a9439-129">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)
