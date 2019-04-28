---
title: Практическое руководство. Службы доступа с дуплексным контрактом
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- duplex contracts [WCF]
ms.assetid: 746a9d64-f21c-426c-b85d-972e916ec6c5
ms.openlocfilehash: 366fd9d6aa220bcbec1ee8fb2a04d1b84755800a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61855144"
---
# <a name="how-to-access-services-with-a-duplex-contract"></a><span data-ttu-id="8d678-102">Практическое руководство. Службы доступа с дуплексным контрактом</span><span class="sxs-lookup"><span data-stu-id="8d678-102">How to: Access services with a duplex contract</span></span>

<span data-ttu-id="8d678-103">Одной из функций Windows Communication Foundation (WCF) предоставляет возможность создать службу, использующую дуплексный шаблон обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="8d678-103">One feature of Windows Communication Foundation (WCF) is the ability to create a service that uses a duplex messaging pattern.</span></span> <span data-ttu-id="8d678-104">Такой шаблон позволяет службе взаимодействовать с клиентом с помощью обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="8d678-104">This pattern allows a service to communicate with the client through a callback.</span></span> <span data-ttu-id="8d678-105">В этом разделе показаны шаги для создания клиентского класса, реализующего интерфейс обратного вызова клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="8d678-105">This topic shows the steps to create a WCF client in a client class that implements the callback interface.</span></span>

<span data-ttu-id="8d678-106">Двойная привязка предоставляет службе IP-адрес клиента.</span><span class="sxs-lookup"><span data-stu-id="8d678-106">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="8d678-107">Клиент должен использовать механизм безопасности, чтобы обеспечить подключение только к доверенным службам.</span><span class="sxs-lookup"><span data-stu-id="8d678-107">The client should use security to ensure that it connects only to services it trusts.</span></span>

<span data-ttu-id="8d678-108">Инструкции по созданию базовой службы WCF и клиента, см. в разделе [Приступая к работе](../../../../docs/framework/wcf/getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="8d678-108">For a tutorial on creating a basic WCF service and client, see [Getting Started Tutorial](../../../../docs/framework/wcf/getting-started-tutorial.md).</span></span>

## <a name="to-access-a-duplex-service"></a><span data-ttu-id="8d678-109">Доступ к дуплексной службе</span><span class="sxs-lookup"><span data-stu-id="8d678-109">To access a duplex service</span></span>

1. <span data-ttu-id="8d678-110">Создайте службу, содержащую два интерфейса.</span><span class="sxs-lookup"><span data-stu-id="8d678-110">Create a service that contains two interfaces.</span></span> <span data-ttu-id="8d678-111">Первый интерфейс предназначен для службы, второй - для обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="8d678-111">The first interface is for the service, the second is for the callback.</span></span> <span data-ttu-id="8d678-112">Дополнительные сведения о создании дуплексной службы см. в разделе [как: Создание дуплексного контракта](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="8d678-112">For more information about creating a duplex service, see [How to: Create a Duplex Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>

2. <span data-ttu-id="8d678-113">Запустите службу.</span><span class="sxs-lookup"><span data-stu-id="8d678-113">Run the service.</span></span>

3. <span data-ttu-id="8d678-114">Используйте [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для создания контрактов (интерфейсы) для клиента.</span><span class="sxs-lookup"><span data-stu-id="8d678-114">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate contracts (interfaces) for the client.</span></span> <span data-ttu-id="8d678-115">Сведения о том, как это сделать, см. в разделе [как: Создание клиента](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="8d678-115">For information about how to do this, see  [How to: Create a Client](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span>

4. <span data-ttu-id="8d678-116">Реализуйте в классе клиента интерфейс обратного вызова, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="8d678-116">Implement the callback interface in the client class, as shown in the following example.</span></span>

    ```csharp
    public class CallbackHandler : ICalculatorDuplexCallback
    {
        public void Result(double result)
        {
            Console.WriteLine("Result ({0})", result);
        }
        public void Equation(string equation)
        {
            Console.WriteLine("Equation({0})", equation);
        }
    }
    ```

    ```vb
    Public Class CallbackHandler
    Implements ICalculatorDuplexCallback
       Public Sub Result (ByVal result As Double)
          Console.WriteLine("Result ({0})", result)
       End Sub
        Public Sub Equation(ByVal equation As String)
            Console.WriteLine("Equation({0})", equation)
        End Sub
    End Class
    ```

5. <span data-ttu-id="8d678-117">Создайте экземпляр класса <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="8d678-117">Create an instance of the <xref:System.ServiceModel.InstanceContext> class.</span></span> <span data-ttu-id="8d678-118">Конструктору требуется экземпляр класса клиента.</span><span class="sxs-lookup"><span data-stu-id="8d678-118">The constructor requires an instance of the client class.</span></span>

    ```csharp
    InstanceContext site = new InstanceContext(new CallbackHandler());
    ```

    ```vb
    Dim site As InstanceContext = New InstanceContext(new CallbackHandler())
    ```

6. <span data-ttu-id="8d678-119">Создайте экземпляр клиента WCF с помощью конструктора, который требует <xref:System.ServiceModel.InstanceContext> объекта.</span><span class="sxs-lookup"><span data-stu-id="8d678-119">Create an instance of the WCF client using the constructor that requires an <xref:System.ServiceModel.InstanceContext> object.</span></span> <span data-ttu-id="8d678-120">Вторым параметром конструктора является имя конечной точки, определенное в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8d678-120">The second parameter of the constructor is the name of an endpoint found in the configuration file.</span></span>

    ```csharp
    CalculatorDuplexClient wcfClient = new CalculatorDuplexClient(site, "default");
    ```

    ```vb
    Dim wcfClient As New CalculatorDuplexClient(site, "default")
    ```

7. <span data-ttu-id="8d678-121">Вызовите методы класса клиента WCF, при необходимости.</span><span class="sxs-lookup"><span data-stu-id="8d678-121">Call the methods of the WCF client as required.</span></span>

## <a name="example"></a><span data-ttu-id="8d678-122">Пример</span><span class="sxs-lookup"><span data-stu-id="8d678-122">Example</span></span>

<span data-ttu-id="8d678-123">В следующем примере кода показано, как создать класс клиента, обращающийся к дуплексному контракту.</span><span class="sxs-lookup"><span data-stu-id="8d678-123">The following code example demonstrates how to create a client class that accesses a duplex contract.</span></span>

[!code-csharp[S_DuplexClients#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_duplexclients/cs/client.cs#1)]
[!code-vb[S_DuplexClients#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_duplexclients/vb/client.vb#1)]

## <a name="see-also"></a><span data-ttu-id="8d678-124">См. также</span><span class="sxs-lookup"><span data-stu-id="8d678-124">See also</span></span>

- [<span data-ttu-id="8d678-125">Руководство по началу работы</span><span class="sxs-lookup"><span data-stu-id="8d678-125">Getting Started Tutorial</span></span>](../../../../docs/framework/wcf/getting-started-tutorial.md)
- [<span data-ttu-id="8d678-126">Практическое руководство. Создание дуплексного контракта</span><span class="sxs-lookup"><span data-stu-id="8d678-126">How to: Create a Duplex Contract</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)
- [<span data-ttu-id="8d678-127">Служебная программа для метаданных ServiceModel (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="8d678-127">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="8d678-128">Практическое руководство. Создание клиента</span><span class="sxs-lookup"><span data-stu-id="8d678-128">How to: Create a Client</span></span>](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md)
- [<span data-ttu-id="8d678-129">Практическое руководство. Использование ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="8d678-129">How to: Use the ChannelFactory</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-channelfactory.md)
