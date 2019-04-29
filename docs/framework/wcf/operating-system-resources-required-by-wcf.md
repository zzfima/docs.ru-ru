---
title: Ресурсы операционной системы, необходимые WCF
ms.date: 03/30/2017
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
ms.openlocfilehash: 828d656370efd7638fa4cf367b84ee7b316b89bb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61955224"
---
# <a name="operating-system-resources-required-by-wcf"></a><span data-ttu-id="2fe71-102">Ресурсы операционной системы, необходимые WCF</span><span class="sxs-lookup"><span data-stu-id="2fe71-102">Operating System Resources Required by WCF</span></span>
<span data-ttu-id="2fe71-103">Windows Communication Foundation (WCF) зависит от нескольких ресурсов, которые предоставляются операционной системой для функции.</span><span class="sxs-lookup"><span data-stu-id="2fe71-103">Windows Communication Foundation (WCF) depends on several resources that are provided by the operating system to function.</span></span> <span data-ttu-id="2fe71-104">В следующей таблице перечислены эти ресурсы.</span><span class="sxs-lookup"><span data-stu-id="2fe71-104">The following table lists those resources.</span></span>  
  
|<span data-ttu-id="2fe71-105">Ресурс</span><span class="sxs-lookup"><span data-stu-id="2fe71-105">Resource</span></span>|<span data-ttu-id="2fe71-106">Описание</span><span class="sxs-lookup"><span data-stu-id="2fe71-106">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="2fe71-107">Координатор распределенных транзакций (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="2fe71-107">Microsoft Distributed Transaction Coordinator (MSDTC)</span></span>|<span data-ttu-id="2fe71-108">Требуется для поддержки транзакций OleTx.</span><span class="sxs-lookup"><span data-stu-id="2fe71-108">Required to support OleTx transactions.</span></span>|  
|<span data-ttu-id="2fe71-109">службы IIS</span><span class="sxs-lookup"><span data-stu-id="2fe71-109">Internet Information Services (IIS)</span></span>|<span data-ttu-id="2fe71-110">Требуется, если необходимо использовать службы IIS для размещения приложения.</span><span class="sxs-lookup"><span data-stu-id="2fe71-110">Required if you want to use IIS to host your application.</span></span>|  
|<span data-ttu-id="2fe71-111">Служба активации Windows (WAS)</span><span class="sxs-lookup"><span data-stu-id="2fe71-111">Windows Process Activation Service (WAS)</span></span>|<span data-ttu-id="2fe71-112">Требуется, если необходимо использовать WAS для размещения приложения.</span><span class="sxs-lookup"><span data-stu-id="2fe71-112">Required if you want to use WAS to host your application.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2fe71-113">См. также</span><span class="sxs-lookup"><span data-stu-id="2fe71-113">See also</span></span>

- [<span data-ttu-id="2fe71-114">Требования к системе</span><span class="sxs-lookup"><span data-stu-id="2fe71-114">System Requirements</span></span>](../../../docs/framework/wcf/wcf-system-requirements.md)
