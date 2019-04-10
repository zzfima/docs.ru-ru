---
title: Практическое руководство. Проверка и изменение сообщений в службе
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9c5b1cc7-84f3-45f8-9226-d59c278e8c42
ms.openlocfilehash: 87f9cf5040ffb757799c51d598d0755847c5bfd9
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59340650"
---
# <a name="how-to-inspect-and-modify-messages-on-the-service"></a><span data-ttu-id="bb7db-102">Практическое руководство. Проверка и изменение сообщений в службе</span><span class="sxs-lookup"><span data-stu-id="bb7db-102">How to: Inspect and Modify Messages on the Service</span></span>
<span data-ttu-id="bb7db-103">Может проверять или изменять входящие или исходящие сообщения по всему клиента Windows Communication Foundation (WCF) путем реализации <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType> и его вставки в среду выполнения службы.</span><span class="sxs-lookup"><span data-stu-id="bb7db-103">You can inspect or modify the incoming or outgoing messages across a Windows Communication Foundation (WCF) client by implementing a <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType> and inserting it into the service runtime.</span></span> <span data-ttu-id="bb7db-104">Дополнительные сведения см. в разделе [расширение диспетчеров](../../../../docs/framework/wcf/extending/extending-dispatchers.md).</span><span class="sxs-lookup"><span data-stu-id="bb7db-104">For more information, see [Extending Dispatchers](../../../../docs/framework/wcf/extending/extending-dispatchers.md).</span></span> <span data-ttu-id="bb7db-105">Эквивалентную функцию в службе выполняет интерфейс <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bb7db-105">The equivalent feature on the service is the <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>.</span></span>  
  
### <a name="to-inspect-or-modify-messages"></a><span data-ttu-id="bb7db-106">Проверка или изменение сообщений</span><span class="sxs-lookup"><span data-stu-id="bb7db-106">To inspect or modify messages</span></span>  
  
1. <span data-ttu-id="bb7db-107">Реализовать интерфейс <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bb7db-107">Implement the <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType> interface.</span></span>  
  
2. <span data-ttu-id="bb7db-108">Реализуйте интерфейс <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> или <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> в зависимости от области, в которую нужно легко вставить инспектор сообщений служб.</span><span class="sxs-lookup"><span data-stu-id="bb7db-108">Implement a <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>, or <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> interface depending upon the scope at which you want to easily insert your service message inspector.</span></span>  
  
3. <span data-ttu-id="bb7db-109">Вставьте поведение до вызова метода <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> в класс <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bb7db-109">Insert your behavior prior to calling the <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> method on the <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType>.</span></span> <span data-ttu-id="bb7db-110">Дополнительные сведения см. в разделе [настройку и расширение среды выполнения с помощью поведений](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="bb7db-110">For details, see [Configuring and Extending the Runtime with Behaviors](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb7db-111">Пример</span><span class="sxs-lookup"><span data-stu-id="bb7db-111">Example</span></span>  
 <span data-ttu-id="bb7db-112">В следующих примерах кода показаны, по порядку:</span><span class="sxs-lookup"><span data-stu-id="bb7db-112">The following code examples show, in order:</span></span>  
  
-   <span data-ttu-id="bb7db-113">реализация инспектора службы;</span><span class="sxs-lookup"><span data-stu-id="bb7db-113">A service inspector implementation.</span></span>  
  
-   <span data-ttu-id="bb7db-114">поведение службы, вставляющее инспектор;</span><span class="sxs-lookup"><span data-stu-id="bb7db-114">A service behavior that inserts the inspector.</span></span>  
  
-   <span data-ttu-id="bb7db-115">файл конфигурации, загружающий и запускающий поведение в приложении службы.</span><span class="sxs-lookup"><span data-stu-id="bb7db-115">A configuration file that loads and runs the behavior in a service application.</span></span>  
  
 [!code-csharp[Interceptors#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/interceptors.cs#7)]
 [!code-vb[Interceptors#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/interceptors.vb#7)]  
  
 [!code-csharp[Interceptors#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/insertingbehaviors.cs#8)]
 [!code-vb[Interceptors#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/insertingbehaviors.vb#8)]  
  
 [!code-xml[Interceptors#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/hostapplication.exe.config#9)]  
  
## <a name="see-also"></a><span data-ttu-id="bb7db-116">См. также</span><span class="sxs-lookup"><span data-stu-id="bb7db-116">See also</span></span>

- <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>
- [<span data-ttu-id="bb7db-117">Настройка и расширение среды выполнения с помощью поведений</span><span class="sxs-lookup"><span data-stu-id="bb7db-117">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
