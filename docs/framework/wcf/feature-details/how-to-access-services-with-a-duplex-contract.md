---
title: "Практическое руководство. Доступ к службам с дуплексным контрактом"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: duplex contracts [WCF]
ms.assetid: 746a9d64-f21c-426c-b85d-972e916ec6c5
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 425d17fa34b61985ad3600f992e028e156f6adb9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-access-services-with-a-duplex-contract"></a><span data-ttu-id="af8f5-102">Практическое руководство. Доступ к службам с дуплексным контрактом</span><span class="sxs-lookup"><span data-stu-id="af8f5-102">How to: Access Services with a Duplex Contract</span></span>
<span data-ttu-id="af8f5-103">Одной из особенностей [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] является возможность создать службу, использующую дуплексный шаблон обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="af8f5-103">One feature of [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] is the ability to create a service that uses a duplex messaging pattern.</span></span> <span data-ttu-id="af8f5-104">Такой шаблон позволяет службе взаимодействовать с клиентом с помощью обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="af8f5-104">This pattern allows a service to communicate with the client through a callback.</span></span> <span data-ttu-id="af8f5-105">В этом разделе приведены основные этапы создания клиента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в классе клиента, который реализует интерфейс обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="af8f5-105">This topic shows the steps to create a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client in a client class that implements the callback interface.</span></span>  
  
 <span data-ttu-id="af8f5-106">Двойная привязка предоставляет службе IP-адрес клиента.</span><span class="sxs-lookup"><span data-stu-id="af8f5-106">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="af8f5-107">Клиент должен использовать механизм безопасности, чтобы обеспечить подключение только к доверенным службам.</span><span class="sxs-lookup"><span data-stu-id="af8f5-107">The client should use security to ensure that it connects only to services it trusts.</span></span>  
  
 <span data-ttu-id="af8f5-108">Учебник по созданию базового [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] службы и клиента см. в разделе [учебник по началу работы](../../../../docs/framework/wcf/getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="af8f5-108">For a tutorial on creating a basic [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service and client, see [Getting Started Tutorial](../../../../docs/framework/wcf/getting-started-tutorial.md).</span></span>  
  
### <a name="to-access-a-duplex-service"></a><span data-ttu-id="af8f5-109">Доступ к дуплексной службе</span><span class="sxs-lookup"><span data-stu-id="af8f5-109">To access a duplex service</span></span>  
  
1.  <span data-ttu-id="af8f5-110">Создайте службу, содержащую два интерфейса.</span><span class="sxs-lookup"><span data-stu-id="af8f5-110">Create a service that contains two interfaces.</span></span> <span data-ttu-id="af8f5-111">Первый интерфейс предназначен для службы, второй - для обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="af8f5-111">The first interface is for the service, the second is for the callback.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="af8f5-112">Создание дуплексной службы. в разделе [как: создание дуплексного контракта](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="af8f5-112"> creating a duplex service, see [How to: Create a Duplex Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
2.  <span data-ttu-id="af8f5-113">Запустите службу.</span><span class="sxs-lookup"><span data-stu-id="af8f5-113">Run the service.</span></span>  
  
3.  <span data-ttu-id="af8f5-114">Используйте [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для создания контрактов (интерфейсы) для клиента.</span><span class="sxs-lookup"><span data-stu-id="af8f5-114">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate contracts (interfaces) for the client.</span></span> <span data-ttu-id="af8f5-115">Сведения о том, как это сделать в разделе [как: создание клиента](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="af8f5-115">For information about how to do this, see  [How to: Create a Client](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span>  
  
4.  <span data-ttu-id="af8f5-116">Реализуйте в классе клиента интерфейс обратного вызова, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="af8f5-116">Implement the callback interface in the client class, as shown in the following example.</span></span>  
  
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
            Console.Writeline("Equation({0})", equation)  
        End Sub  
    End Class  
    ```  
  
5.  <span data-ttu-id="af8f5-117">Создайте экземпляр класса <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="af8f5-117">Create an instance of the <xref:System.ServiceModel.InstanceContext> class.</span></span> <span data-ttu-id="af8f5-118">Конструктору требуется экземпляр класса клиента.</span><span class="sxs-lookup"><span data-stu-id="af8f5-118">The constructor requires an instance of the client class.</span></span>  
  
    ```csharp  
    InstanceContext site = new InstanceContext(new CallbackHandler());  
    ```  
  
    ```vb  
    Dim site As InstanceContext = New InstanceContext(new CallbackHandler())  
    ```  
  
6.  <span data-ttu-id="af8f5-119">Создайте экземпляр клиента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], используя конструктор, которому требуется объект <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="af8f5-119">Create an instance of the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client using the constructor that requires an <xref:System.ServiceModel.InstanceContext> object.</span></span> <span data-ttu-id="af8f5-120">Вторым параметром конструктора является имя конечной точки, определенное в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="af8f5-120">The second parameter of the constructor is the name of an endpoint found in the configuration file.</span></span>  
  
    ```csharp  
    CalculatorDuplexClient wcfClient =   
    new CalculatorDuplexClient(site, "default")  
    ```  
  
    ```vb  
    Dim wcfClient As New CalculatorDuplexClient(site, "default")  
    ```  
  
7.  <span data-ttu-id="af8f5-121">Вызовите требуемые методы клиента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af8f5-121">Call the methods of the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client as required.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af8f5-122">Пример</span><span class="sxs-lookup"><span data-stu-id="af8f5-122">Example</span></span>  
 <span data-ttu-id="af8f5-123">В следующем примере кода показано, как создать класс клиента, обращающийся к дуплексному контракту.</span><span class="sxs-lookup"><span data-stu-id="af8f5-123">The following code example demonstrates how to create a client class that accesses a duplex contract.</span></span>  
  
 [!code-csharp[S_DuplexClients#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_duplexclients/cs/client.cs#1)]
 [!code-vb[S_DuplexClients#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_duplexclients/vb/client.vb#1)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="af8f5-124">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="af8f5-124">.NET Framework Security</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af8f5-125">См. также</span><span class="sxs-lookup"><span data-stu-id="af8f5-125">See Also</span></span>  
 [<span data-ttu-id="af8f5-126">Руководство по началу работы</span><span class="sxs-lookup"><span data-stu-id="af8f5-126">Getting Started Tutorial</span></span>](../../../../docs/framework/wcf/getting-started-tutorial.md)  
 [<span data-ttu-id="af8f5-127">Практическое руководство. Создание дуплексного контракта</span><span class="sxs-lookup"><span data-stu-id="af8f5-127">How to: Create a Duplex Contract</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)  
 [<span data-ttu-id="af8f5-128">Служебная программа для метаданных ServiceModel (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="af8f5-128">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [<span data-ttu-id="af8f5-129">Практическое руководство. Создание клиента</span><span class="sxs-lookup"><span data-stu-id="af8f5-129">How to: Create a Client</span></span>](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [<span data-ttu-id="af8f5-130">Практическое руководство. Использование ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="af8f5-130">How to: Use the ChannelFactory</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-channelfactory.md)
