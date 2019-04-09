---
title: Практическое руководство. Создание конечной точки службы в коде
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3fbb22fa-2930-48b8-b437-def1de87c6a0
ms.openlocfilehash: 0b51018a5940e01b38b00addb762fa6504495a4c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59139871"
---
# <a name="how-to-create-a-service-endpoint-in-code"></a><span data-ttu-id="298ef-102">Практическое руководство. Создание конечной точки службы в коде</span><span class="sxs-lookup"><span data-stu-id="298ef-102">How to: Create a Service Endpoint in Code</span></span>
<span data-ttu-id="298ef-103">В этом примере контракт `ICalculator` определен для службы калькулятора, служба реализуется в классе `CalculatorService`, а затем ее конечная точка задается в коде с указанием того, что служба должна использовать класс <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="298ef-103">In this example, an `ICalculator` contract is defined for a calculator service, the service is implemented in the `CalculatorService` class, and then its endpoint is defined in code, where it is specified that the service must use the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span>  
  
 <span data-ttu-id="298ef-104">В большинстве случаев рекомендуется указывать привязку и адрес декларативно в конфигурации, а не принудительно в коде.</span><span class="sxs-lookup"><span data-stu-id="298ef-104">It is usually the best practice to specify the binding and address information declaratively in configuration rather than imperatively in code.</span></span> <span data-ttu-id="298ef-105">Как правило, определять конечные точки в коде непрактично, поскольку привязки и адреса для развернутой службы чаще всего отличаются от привязок и адресов, используемых в процессе разработки службы.</span><span class="sxs-lookup"><span data-stu-id="298ef-105">Defining endpoints in code is usually not practical because the bindings and addresses for a deployed service are typically different from those used while the service is being developed.</span></span> <span data-ttu-id="298ef-106">В общем случае, если не указывать привязку и адрес в коде, их можно изменять без повторной компиляции или повторного развертывания приложения.</span><span class="sxs-lookup"><span data-stu-id="298ef-106">More generally, keeping the binding and addressing information out of the code allows them to change without having to recompile or redeploy the application.</span></span>  
  
#### <a name="to-create-a-service-endpoint-in-code"></a><span data-ttu-id="298ef-107">Создание конечной точки службы в коде</span><span class="sxs-lookup"><span data-stu-id="298ef-107">To create a service endpoint in code</span></span>  
  
1.  <span data-ttu-id="298ef-108">Создайте интерфейс, определяющий контракт службы.</span><span class="sxs-lookup"><span data-stu-id="298ef-108">Create the interface that defines the service contract.</span></span>  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#1)]
     [!code-vb[c_HowTo_CodeServiceBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#1)]  
  
2.  <span data-ttu-id="298ef-109">Реализуйте контракт службы, определенный на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="298ef-109">Implement the service contract defined in step 1.</span></span>  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#2)]
     [!code-vb[c_HowTo_CodeServiceBinding#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#2)]  
  
3.  <span data-ttu-id="298ef-110">В ведущем приложении создайте базовый адрес для службы и привязку, которая используется со службой.</span><span class="sxs-lookup"><span data-stu-id="298ef-110">In the hosting application, create the base address for the service and the binding to be used with the service.</span></span>  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#3)]
     [!code-vb[c_HowTo_CodeServiceBinding#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#3)]  
  
4.  <span data-ttu-id="298ef-111">Создайте основное приложение и вызовите <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%29> или одну из других перегрузок, чтобы добавить конечную точку службы для основного приложения.</span><span class="sxs-lookup"><span data-stu-id="298ef-111">Create the host and call <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%29> or one of the other overloads to add the service endpoint for the host.</span></span>  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#6)]
     [!code-vb[c_HowTo_CodeServiceBinding#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#6)]  
  
     <span data-ttu-id="298ef-112">Чтобы указать привязку в коде, но использовать конечные точки по умолчанию, предоставляемые средой выполнения, передайте базовый адрес в конструктор при создании <xref:System.ServiceModel.ServiceHost> и не вызывайте метод <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>.</span><span class="sxs-lookup"><span data-stu-id="298ef-112">To specify the binding in code, but to use the default endpoints provided by the runtime, pass the bass address into constructor when creating the <xref:System.ServiceModel.ServiceHost>, and do not call <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>.</span></span>  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#7)]
     [!code-vb[c_HowTo_CodeServiceBinding#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#7)]  
  
     <span data-ttu-id="298ef-113">Дополнительные сведения о конечных точках по умолчанию, см. в разделе [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) и [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="298ef-113">For more information about default endpoints, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="298ef-114">См. также</span><span class="sxs-lookup"><span data-stu-id="298ef-114">See also</span></span>

- [<span data-ttu-id="298ef-115">Практическое руководство. Задание привязки службы в коде</span><span class="sxs-lookup"><span data-stu-id="298ef-115">How to: Specify a Service Binding in Code</span></span>](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-code.md)
