---
title: "Практическое руководство. Управление созданием экземпляров служб"
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
ms.assetid: e0b12b34-8004-443a-a46d-83a5c00f2601
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 60a2537f1ddc4563c1514032f7df4894f6ef47af
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-control-service-instancing"></a><span data-ttu-id="bf227-102">Практическое руководство. Управление созданием экземпляров служб</span><span class="sxs-lookup"><span data-stu-id="bf227-102">How to: Control Service Instancing</span></span>
<span data-ttu-id="bf227-103">Установка режима экземпляра службы позволяет определить, когда будет создаваться объект <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> (и связанный с ним определяемый пользователем объект службы).</span><span class="sxs-lookup"><span data-stu-id="bf227-103">Setting the instance mode of a service enables you to specify when a <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> (and its associated user-defined service object) is created.</span></span> <span data-ttu-id="bf227-104">Возможные режимы см. в перечислении <xref:System.ServiceModel.InstanceContextMode>.</span><span class="sxs-lookup"><span data-stu-id="bf227-104">See the <xref:System.ServiceModel.InstanceContextMode> enumeration for the possible modes.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="bf227-105">в разделе поведений, [настройку и расширение среды выполнения с помощью поведений](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="bf227-105"> behaviors, see [Configuring and Extending the Runtime with Behaviors](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).</span></span> <span data-ttu-id="bf227-106">Рабочие примеры см. в разделе [поведения](../../../../docs/framework/wcf/samples/behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="bf227-106">For working examples, see [Behaviors](../../../../docs/framework/wcf/samples/behaviors.md).</span></span>  
  
### <a name="to-control-the-service-instance-lifetime-using-code"></a><span data-ttu-id="bf227-107">Управление временем существования экземпляра службы с помощью кода</span><span class="sxs-lookup"><span data-stu-id="bf227-107">To control the service instance lifetime using code</span></span>  
  
1.  <span data-ttu-id="bf227-108">Примените атрибут <xref:System.ServiceModel.ServiceBehaviorAttribute> к классу службы.</span><span class="sxs-lookup"><span data-stu-id="bf227-108">Apply the <xref:System.ServiceModel.ServiceBehaviorAttribute> to the service class.</span></span>  
  
2.  <span data-ttu-id="bf227-109">Присвойте свойству <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> одно из следующих значений: <xref:System.ServiceModel.InstanceContextMode.PerCall>, <xref:System.ServiceModel.InstanceContextMode.PerSession> или <xref:System.ServiceModel.InstanceContextMode.Single>.</span><span class="sxs-lookup"><span data-stu-id="bf227-109">Set the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property to one of the following values: <xref:System.ServiceModel.InstanceContextMode.PerCall>, <xref:System.ServiceModel.InstanceContextMode.PerSession>, or <xref:System.ServiceModel.InstanceContextMode.Single>.</span></span>  
  
     [!code-csharp[C_ControlServiceInstancing#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#1)]
     [!code-vb[C_ControlServiceInstancing#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="bf227-110">Пример</span><span class="sxs-lookup"><span data-stu-id="bf227-110">Example</span></span>  
 <span data-ttu-id="bf227-111">В следующем примере кода свойству <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> атрибута <xref:System.ServiceModel.ServiceBehaviorAttribute> присваивается значение <xref:System.ServiceModel.InstanceContextMode.PerCall>.</span><span class="sxs-lookup"><span data-stu-id="bf227-111">The following code example sets the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property of the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute to <xref:System.ServiceModel.InstanceContextMode.PerCall>.</span></span>  
  
 [!code-csharp[c_ControlServiceInstancing#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#2)]
 [!code-vb[c_ControlServiceInstancing#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="bf227-112">См. также</span><span class="sxs-lookup"><span data-stu-id="bf227-112">See Also</span></span>  
 <xref:System.ServiceModel.ServiceBehaviorAttribute>  
 <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>  
 <xref:System.ServiceModel.InstanceContextMode>  
 [<span data-ttu-id="bf227-113">Службы: Примеры поведения</span><span class="sxs-lookup"><span data-stu-id="bf227-113">Service: Behaviors Samples</span></span>](http://msdn.microsoft.com/en-us/4e3c6513-a7ff-4b35-8dcf-b5506c6f39a7)
