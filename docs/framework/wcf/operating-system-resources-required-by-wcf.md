---
title: Ресурсы операционной системы, необходимые WCF
ms.date: 03/30/2017
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
ms.openlocfilehash: 4522f1c59c8f74281a0e197338c6206ab29c229b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="operating-system-resources-required-by-wcf"></a><span data-ttu-id="d92da-102">Ресурсы операционной системы, необходимые WCF</span><span class="sxs-lookup"><span data-stu-id="d92da-102">Operating System Resources Required by WCF</span></span>
<span data-ttu-id="d92da-103">Windows Communication Foundation (WCF) зависит от нескольких ресурсов, предоставляемых операционной системой для функции.</span><span class="sxs-lookup"><span data-stu-id="d92da-103">Windows Communication Foundation (WCF) depends on several resources that are provided by the operating system to function.</span></span> <span data-ttu-id="d92da-104">В следующей таблице перечислены эти ресурсы.</span><span class="sxs-lookup"><span data-stu-id="d92da-104">The following table lists those resources.</span></span>  
  
|<span data-ttu-id="d92da-105">Ресурс</span><span class="sxs-lookup"><span data-stu-id="d92da-105">Resource</span></span>|<span data-ttu-id="d92da-106">Описание</span><span class="sxs-lookup"><span data-stu-id="d92da-106">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="d92da-107">Координатор распределенных транзакций (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="d92da-107">Microsoft Distributed Transaction Coordinator (MSDTC)</span></span>|<span data-ttu-id="d92da-108">Требуется для поддержки транзакций OleTx.</span><span class="sxs-lookup"><span data-stu-id="d92da-108">Required to support OleTx transactions.</span></span>|  
|<span data-ttu-id="d92da-109">службы IIS</span><span class="sxs-lookup"><span data-stu-id="d92da-109">Internet Information Services (IIS)</span></span>|<span data-ttu-id="d92da-110">Требуется, если необходимо использовать службы IIS для размещения приложения.</span><span class="sxs-lookup"><span data-stu-id="d92da-110">Required if you want to use IIS to host your application.</span></span>|  
|<span data-ttu-id="d92da-111">Служба активации Windows (WAS)</span><span class="sxs-lookup"><span data-stu-id="d92da-111">Windows Process Activation Service (WAS)</span></span>|<span data-ttu-id="d92da-112">Требуется, если необходимо использовать WAS для размещения приложения.</span><span class="sxs-lookup"><span data-stu-id="d92da-112">Required if you want to use WAS to host your application.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d92da-113">См. также</span><span class="sxs-lookup"><span data-stu-id="d92da-113">See Also</span></span>  
 [<span data-ttu-id="d92da-114">Требования к системе</span><span class="sxs-lookup"><span data-stu-id="d92da-114">System Requirements</span></span>](../../../docs/framework/wcf/wcf-system-requirements.md)
