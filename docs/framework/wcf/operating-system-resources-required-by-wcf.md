---
title: Ресурсы операционной системы, необходимые WCF
ms.date: 03/30/2017
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
ms.openlocfilehash: 759ab099066e300484860cf3f91d6d084ba1d339
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527085"
---
# <a name="operating-system-resources-required-by-wcf"></a><span data-ttu-id="6fa2a-102">Ресурсы операционной системы, необходимые WCF</span><span class="sxs-lookup"><span data-stu-id="6fa2a-102">Operating System Resources Required by WCF</span></span>
<span data-ttu-id="6fa2a-103">Windows Communication Foundation (WCF) зависит от нескольких ресурсов, которые предоставляются операционной системой для функции.</span><span class="sxs-lookup"><span data-stu-id="6fa2a-103">Windows Communication Foundation (WCF) depends on several resources that are provided by the operating system to function.</span></span> <span data-ttu-id="6fa2a-104">В следующей таблице перечислены эти ресурсы.</span><span class="sxs-lookup"><span data-stu-id="6fa2a-104">The following table lists those resources.</span></span>  
  
|<span data-ttu-id="6fa2a-105">Ресурс</span><span class="sxs-lookup"><span data-stu-id="6fa2a-105">Resource</span></span>|<span data-ttu-id="6fa2a-106">Описание</span><span class="sxs-lookup"><span data-stu-id="6fa2a-106">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="6fa2a-107">Координатор распределенных транзакций (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="6fa2a-107">Microsoft Distributed Transaction Coordinator (MSDTC)</span></span>|<span data-ttu-id="6fa2a-108">Требуется для поддержки транзакций OleTx.</span><span class="sxs-lookup"><span data-stu-id="6fa2a-108">Required to support OleTx transactions.</span></span>|  
|<span data-ttu-id="6fa2a-109">службы IIS</span><span class="sxs-lookup"><span data-stu-id="6fa2a-109">Internet Information Services (IIS)</span></span>|<span data-ttu-id="6fa2a-110">Требуется, если необходимо использовать службы IIS для размещения приложения.</span><span class="sxs-lookup"><span data-stu-id="6fa2a-110">Required if you want to use IIS to host your application.</span></span>|  
|<span data-ttu-id="6fa2a-111">Служба активации Windows (WAS)</span><span class="sxs-lookup"><span data-stu-id="6fa2a-111">Windows Process Activation Service (WAS)</span></span>|<span data-ttu-id="6fa2a-112">Требуется, если необходимо использовать WAS для размещения приложения.</span><span class="sxs-lookup"><span data-stu-id="6fa2a-112">Required if you want to use WAS to host your application.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6fa2a-113">См. также</span><span class="sxs-lookup"><span data-stu-id="6fa2a-113">See also</span></span>
- [<span data-ttu-id="6fa2a-114">Требования к системе</span><span class="sxs-lookup"><span data-stu-id="6fa2a-114">System Requirements</span></span>](../../../docs/framework/wcf/wcf-system-requirements.md)
