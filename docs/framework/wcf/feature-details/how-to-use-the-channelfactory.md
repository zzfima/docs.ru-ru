---
title: "Практическое руководство. Использование ChannelFactory"
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
ms.assetid: d48f01b5-582b-4c8b-b547-8adddae7e371
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cd9c7c69ba65fe676e9ea0eba250fc3200e90c51
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-use-the-channelfactory"></a><span data-ttu-id="13939-102">Практическое руководство. Использование ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="13939-102">How to: Use the ChannelFactory</span></span>
<span data-ttu-id="13939-103">Универсальный класс <xref:System.ServiceModel.ChannelFactory%601> используется в сложных сценариях, требующих создания фабрики каналов, которая может использоваться для создания нескольких каналов.</span><span class="sxs-lookup"><span data-stu-id="13939-103">The generic <xref:System.ServiceModel.ChannelFactory%601> class is used in advanced scenarios that require the creation of a channel factory that can be used to create more than one channel.</span></span>  
  
### <a name="to-create-and-use-the-channelfactory-class"></a><span data-ttu-id="13939-104">Создание и использование класса ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="13939-104">To create and use the ChannelFactory class</span></span>  
  
1.  <span data-ttu-id="13939-105">Создайте и запустите службу [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="13939-105">Build and run an [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="13939-106">[Проектирование и реализация служб](../../../../docs/framework/wcf/designing-and-implementing-services.md), [Настройка служб](../../../../docs/framework/wcf/configuring-services.md), и [услуг](../../../../docs/framework/wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="13939-106"> [Designing and Implementing Services](../../../../docs/framework/wcf/designing-and-implementing-services.md), [Configuring Services](../../../../docs/framework/wcf/configuring-services.md), and [Hosting Services](../../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
2.  <span data-ttu-id="13939-107">Используйте [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для создания контракта для клиента (интерфейс).</span><span class="sxs-lookup"><span data-stu-id="13939-107">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the contract (interface) for the client.</span></span>  
  
3.  <span data-ttu-id="13939-108">В коде клиента для создания нескольких прослушивателей конечной точки используйте класс <xref:System.ServiceModel.ChannelFactory%601>.</span><span class="sxs-lookup"><span data-stu-id="13939-108">In the client code, use the <xref:System.ServiceModel.ChannelFactory%601> class to create multiple endpoint listeners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13939-109">Пример</span><span class="sxs-lookup"><span data-stu-id="13939-109">Example</span></span>  
 [!code-csharp[c_HowToUseChannelFactory#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtousechannelfactory/cs/source.cs#1)]
 [!code-vb[c_HowToUseChannelFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtousechannelfactory/vb/source.vb#1)]
