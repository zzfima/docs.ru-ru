---
title: Ресурсы операционной системы, необходимые WCF
ms.date: 03/30/2017
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
ms.openlocfilehash: 828d656370efd7638fa4cf367b84ee7b316b89bb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59100955"
---
# <a name="operating-system-resources-required-by-wcf"></a><span data-ttu-id="fff00-102">Ресурсы операционной системы, необходимые WCF</span><span class="sxs-lookup"><span data-stu-id="fff00-102">Operating System Resources Required by WCF</span></span>
<span data-ttu-id="fff00-103">Windows Communication Foundation (WCF) зависит от нескольких ресурсов, которые предоставляются операционной системой для функции.</span><span class="sxs-lookup"><span data-stu-id="fff00-103">Windows Communication Foundation (WCF) depends on several resources that are provided by the operating system to function.</span></span> <span data-ttu-id="fff00-104">В следующей таблице перечислены эти ресурсы.</span><span class="sxs-lookup"><span data-stu-id="fff00-104">The following table lists those resources.</span></span>  
  
|<span data-ttu-id="fff00-105">Ресурс</span><span class="sxs-lookup"><span data-stu-id="fff00-105">Resource</span></span>|<span data-ttu-id="fff00-106">Описание</span><span class="sxs-lookup"><span data-stu-id="fff00-106">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="fff00-107">Координатор распределенных транзакций (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="fff00-107">Microsoft Distributed Transaction Coordinator (MSDTC)</span></span>|<span data-ttu-id="fff00-108">Требуется для поддержки транзакций OleTx.</span><span class="sxs-lookup"><span data-stu-id="fff00-108">Required to support OleTx transactions.</span></span>|  
|<span data-ttu-id="fff00-109">службы IIS</span><span class="sxs-lookup"><span data-stu-id="fff00-109">Internet Information Services (IIS)</span></span>|<span data-ttu-id="fff00-110">Требуется, если необходимо использовать службы IIS для размещения приложения.</span><span class="sxs-lookup"><span data-stu-id="fff00-110">Required if you want to use IIS to host your application.</span></span>|  
|<span data-ttu-id="fff00-111">Служба активации Windows (WAS)</span><span class="sxs-lookup"><span data-stu-id="fff00-111">Windows Process Activation Service (WAS)</span></span>|<span data-ttu-id="fff00-112">Требуется, если необходимо использовать WAS для размещения приложения.</span><span class="sxs-lookup"><span data-stu-id="fff00-112">Required if you want to use WAS to host your application.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fff00-113">См. также</span><span class="sxs-lookup"><span data-stu-id="fff00-113">See also</span></span>

- [<span data-ttu-id="fff00-114">Требования к системе</span><span class="sxs-lookup"><span data-stu-id="fff00-114">System Requirements</span></span>](../../../docs/framework/wcf/wcf-system-requirements.md)
