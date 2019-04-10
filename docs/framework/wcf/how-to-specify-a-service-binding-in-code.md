---
title: Практическое руководство. Задание привязки службы в коде
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 67ab5dd8-79c1-4e62-aa75-828ea918a53a
ms.openlocfilehash: 9f3320b031141246a394191a1924509204707dc1
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59303457"
---
# <a name="how-to-specify-a-service-binding-in-code"></a><span data-ttu-id="5cc2c-102">Практическое руководство. Задание привязки службы в коде</span><span class="sxs-lookup"><span data-stu-id="5cc2c-102">How to: Specify a Service Binding in Code</span></span>
<span data-ttu-id="5cc2c-103">В этом примере контракт `ICalculator` определен для службы калькулятора, служба реализуется в классе `CalculatorService`, а затем ее конечная точка задается в коде с указанием того, что служба должна использовать класс <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="5cc2c-103">In this example, an `ICalculator` contract is defined for a calculator service, the service is implemented in the `CalculatorService` class, and then its endpoint is defined in code, where it is specified that the service must use the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span>  
  
 <span data-ttu-id="5cc2c-104">В большинстве случаев рекомендуется указывать привязку и адрес декларативно в конфигурации, а не принудительно в коде.</span><span class="sxs-lookup"><span data-stu-id="5cc2c-104">It is usually the best practice to specify the binding and address information declaratively in configuration rather than imperatively in code.</span></span> <span data-ttu-id="5cc2c-105">Как правило, определять конечные точки в коде непрактично, поскольку привязки и адреса для развернутой службы чаще всего отличаются от привязок и адресов, используемых в процессе разработки службы.</span><span class="sxs-lookup"><span data-stu-id="5cc2c-105">Defining endpoints in code is usually not practical because the bindings and addresses for a deployed service are typically different from those used while the service is being developed.</span></span> <span data-ttu-id="5cc2c-106">В общем случае, если не указывать привязку и адрес в коде, их можно изменять без повторной компиляции или повторного развертывания приложения.</span><span class="sxs-lookup"><span data-stu-id="5cc2c-106">More generally, keeping the binding and addressing information out of the code allows them to change without having to recompile or redeploy the application.</span></span>  
  
 <span data-ttu-id="5cc2c-107">Описание способов настройки этой службы с помощью элементов конфигурации вместо кода, см. в разделе [как: Указание привязки службы в конфигурации](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="5cc2c-107">For a description of how to configure this service using configuration elements instead of code, see [How to: Specify a Service Binding in Configuration](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span></span>  
  
### <a name="to-specify-in-code-to-use-the-basichttpbinding-for-the-service"></a><span data-ttu-id="5cc2c-108">Указание в коде использования привязки BasicHttpBinding для этой службы</span><span class="sxs-lookup"><span data-stu-id="5cc2c-108">To specify in code to use the BasicHttpBinding for the service</span></span>  
  
1. <span data-ttu-id="5cc2c-109">Определите контракт службы для данного типа службы.</span><span class="sxs-lookup"><span data-stu-id="5cc2c-109">Define a service contract for the type of service.</span></span>  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#1)]
     [!code-vb[C_HowTo_CodeServiceBinding#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#1)]  
  
2. <span data-ttu-id="5cc2c-110">Реализуйте контракт службы в классе службы.</span><span class="sxs-lookup"><span data-stu-id="5cc2c-110">Implement the service contract in a service class.</span></span>  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#2)]
     [!code-vb[C_HowTo_CodeServiceBinding#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#2)]  
  
3. <span data-ttu-id="5cc2c-111">В ведущем приложении создайте базовый адрес для службы и привязку, которая используется со службой.</span><span class="sxs-lookup"><span data-stu-id="5cc2c-111">In the hosting application, create the base address for the service and the binding to use with the service.</span></span>  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#3)]
     [!code-vb[C_HowTo_CodeServiceBinding#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#3)]  
  
4. <span data-ttu-id="5cc2c-112">Создайте ведущее приложение для службы, добавьте конечную точку, затем откройте ведущее приложение.</span><span class="sxs-lookup"><span data-stu-id="5cc2c-112">Create the host for the service, add the endpoint, and then open the host.</span></span>  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#4)]
     [!code-vb[C_HowTo_CodeServiceBinding#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#4)]  
  
### <a name="to-modify-the-default-values-of-the-binding-properties"></a><span data-ttu-id="5cc2c-113">Изменение значений по умолчанию для свойств привязки</span><span class="sxs-lookup"><span data-stu-id="5cc2c-113">To modify the default values of the binding properties</span></span>  
  
1. <span data-ttu-id="5cc2c-114">Чтобы изменить одно из значений свойства по умолчанию для класса <xref:System.ServiceModel.BasicHttpBinding>, перед созданием основного приложения задайте в привязке новое значение свойства.</span><span class="sxs-lookup"><span data-stu-id="5cc2c-114">To modify one of the default property values of the <xref:System.ServiceModel.BasicHttpBinding> class, set the property value on the binding to the new value before creating the host.</span></span> <span data-ttu-id="5cc2c-115">Например, чтобы изменить значения по умолчанию для времени ожидания при открытии и закрытии с 1 минуты на 2 минуты, используйте следующее.</span><span class="sxs-lookup"><span data-stu-id="5cc2c-115">For example, to change the default open and close timeout values of 1 minute to 2 minutes, use the following.</span></span>  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#5)]
     [!code-vb[C_HowTo_CodeServiceBinding#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="5cc2c-116">См. также</span><span class="sxs-lookup"><span data-stu-id="5cc2c-116">See also</span></span>

- [<span data-ttu-id="5cc2c-117">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="5cc2c-117">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="5cc2c-118">Задание адреса конечной точки</span><span class="sxs-lookup"><span data-stu-id="5cc2c-118">Specifying an Endpoint Address</span></span>](../../../docs/framework/wcf/specifying-an-endpoint-address.md)
