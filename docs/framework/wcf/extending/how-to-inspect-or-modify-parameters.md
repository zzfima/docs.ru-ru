---
title: "Практическое руководство. Проверка или изменение параметров"
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
ms.assetid: ab6c0ac7-aac4-45ba-93d6-a0e9afd1756f
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5f1a0ef31ba074082e4c3aa8a26e6a59502a7566
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-inspect-or-modify-parameters"></a><span data-ttu-id="eb813-102">Практическое руководство. Проверка или изменение параметров</span><span class="sxs-lookup"><span data-stu-id="eb813-102">How to: Inspect or Modify Parameters</span></span>
<span data-ttu-id="eb813-103">Проверять или изменять входящие или исходящие сообщения для отдельной операции в клиентском объекте [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] или службе [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] можно посредством реализации интерфейса <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType> и его вставки в среду выполнения клиента или службы.</span><span class="sxs-lookup"><span data-stu-id="eb813-103">You can inspect or modify the incoming or outgoing messages for a single operation on a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client object or a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service by implementing the <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType> interface and inserting it into the client or service runtime.</span></span> <span data-ttu-id="eb813-104">Как правило, для добавления инспекторов параметров для отдельной операции используется поведение операции; другие поведения могут использоваться для обеспечения быстрого доступа к среде выполнения в более широкой области действия.</span><span class="sxs-lookup"><span data-stu-id="eb813-104">Typically an operation behavior is used to add parameter inspectors for a single operation; other behaviors can be used to provide easy access to the runtime at a greater scope.</span></span> <span data-ttu-id="eb813-105">Дополнительные сведения см. в разделе [расширение клиентов](../../../../docs/framework/wcf/extending/extending-clients.md) и [расширение диспетчеров](../../../../docs/framework/wcf/extending/extending-dispatchers.md).</span><span class="sxs-lookup"><span data-stu-id="eb813-105">For more information, see [Extending Clients](../../../../docs/framework/wcf/extending/extending-clients.md) and [Extending Dispatchers](../../../../docs/framework/wcf/extending/extending-dispatchers.md).</span></span>  
  
### <a name="inspecting-or-modifying-parameters"></a><span data-ttu-id="eb813-106">Проверка или изменение параметров</span><span class="sxs-lookup"><span data-stu-id="eb813-106">Inspecting or Modifying Parameters</span></span>  
  
1.  <span data-ttu-id="eb813-107">Реализовать интерфейс <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="eb813-107">Implement the <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType> interface.</span></span>  
  
2.  <span data-ttu-id="eb813-108">Реализуйте поведение <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType> или <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> (в зависимости от того, какая требуется область действия), чтобы добавить инспектор параметров в свойство <xref:System.ServiceModel.Dispatcher.ClientOperation.ParameterInspectors%2A?displayProperty=nameWithType> или <xref:System.ServiceModel.Dispatcher.DispatchOperation.ParameterInspectors%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="eb813-108">Implement a <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType> or <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> (depending upon the required scope) to add your parameter inspector to either the <xref:System.ServiceModel.Dispatcher.ClientOperation.ParameterInspectors%2A?displayProperty=nameWithType> or <xref:System.ServiceModel.Dispatcher.DispatchOperation.ParameterInspectors%2A?displayProperty=nameWithType> properties.</span></span>  
  
3.  <span data-ttu-id="eb813-109">Вставьте поведение до вызова метода <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType> или <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> в производство каналов <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="eb813-109">Insert your behavior prior to calling <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType> or the <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> method on the <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="eb813-110">Дополнительные сведения см. в разделе [настройку и расширение среды выполнения с помощью поведений](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="eb813-110">For details, see [Configuring and Extending the Runtime with Behaviors](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb813-111">Пример</span><span class="sxs-lookup"><span data-stu-id="eb813-111">Example</span></span>  
 <span data-ttu-id="eb813-112">В следующих примерах кода показаны, по порядку:</span><span class="sxs-lookup"><span data-stu-id="eb813-112">The following code examples show, in order:</span></span>  
  
-   <span data-ttu-id="eb813-113">реализация инспектора параметров;</span><span class="sxs-lookup"><span data-stu-id="eb813-113">A parameter inspector implementation.</span></span>  
  
-   <span data-ttu-id="eb813-114">реализация поведения, вставляющего инспектор параметров с помощью <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> и <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>;</span><span class="sxs-lookup"><span data-stu-id="eb813-114">The behavior implementation that inserts the parameter inspector using a <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>, and an <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="eb813-115">файл конфигурации, который загружает и запускает поведение конечной точки в клиентском приложении для вставки инспектора параметров в клиент.</span><span class="sxs-lookup"><span data-stu-id="eb813-115">A configuration file that loads and runs the endpoint behavior in a client application to insert the parameter inspector on the client.</span></span>  
  
 [!code-csharp[Interceptors#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/interceptors.cs#4)]
 [!code-vb[Interceptors#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/interceptors.vb#4)]  
  
 [!code-csharp[Interceptors#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/insertingbehaviors.cs#5)]
 [!code-vb[Interceptors#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/insertingbehaviors.vb#5)]  
  
 [!code-xml[Interceptors#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/client.exe.config#3)]  
  
## <a name="see-also"></a><span data-ttu-id="eb813-116">См. также</span><span class="sxs-lookup"><span data-stu-id="eb813-116">See Also</span></span>  
 [<span data-ttu-id="eb813-117">Настройка и расширение среды выполнения с помощью поведений</span><span class="sxs-lookup"><span data-stu-id="eb813-117">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
