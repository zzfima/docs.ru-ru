---
title: "Ресурсы операционной системы, необходимые WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fde00011a7fffde4c4c75f9605758971b42627f4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="operating-system-resources-required-by-wcf"></a><span data-ttu-id="b26db-102">Ресурсы операционной системы, необходимые WCF</span><span class="sxs-lookup"><span data-stu-id="b26db-102">Operating System Resources Required by WCF</span></span>
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)]<span data-ttu-id="b26db-103"> зависит о нескольких ресурсов, работа которых обеспечивается операционной системой.</span><span class="sxs-lookup"><span data-stu-id="b26db-103"> depends on several resources that are provided by the operating system to function.</span></span> <span data-ttu-id="b26db-104">В следующей таблице перечислены эти ресурсы.</span><span class="sxs-lookup"><span data-stu-id="b26db-104">The following table lists those resources.</span></span>  
  
|<span data-ttu-id="b26db-105">Ресурс</span><span class="sxs-lookup"><span data-stu-id="b26db-105">Resource</span></span>|<span data-ttu-id="b26db-106">Описание</span><span class="sxs-lookup"><span data-stu-id="b26db-106">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="b26db-107">Координатор распределенных транзакций (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="b26db-107">Microsoft Distributed Transaction Coordinator (MSDTC)</span></span>|<span data-ttu-id="b26db-108">Требуется для поддержки транзакций OleTx.</span><span class="sxs-lookup"><span data-stu-id="b26db-108">Required to support OleTx transactions.</span></span>|  
|<span data-ttu-id="b26db-109">службы IIS</span><span class="sxs-lookup"><span data-stu-id="b26db-109">Internet Information Services (IIS)</span></span>|<span data-ttu-id="b26db-110">Требуется, если необходимо использовать службы IIS для размещения приложения.</span><span class="sxs-lookup"><span data-stu-id="b26db-110">Required if you want to use IIS to host your application.</span></span>|  
|<span data-ttu-id="b26db-111">Служба активации Windows (WAS)</span><span class="sxs-lookup"><span data-stu-id="b26db-111">Windows Process Activation Service (WAS)</span></span>|<span data-ttu-id="b26db-112">Требуется, если необходимо использовать WAS для размещения приложения.</span><span class="sxs-lookup"><span data-stu-id="b26db-112">Required if you want to use WAS to host your application.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b26db-113">См. также</span><span class="sxs-lookup"><span data-stu-id="b26db-113">See Also</span></span>  
 [<span data-ttu-id="b26db-114">Требования к системе</span><span class="sxs-lookup"><span data-stu-id="b26db-114">System Requirements</span></span>](../../../docs/framework/wcf/wcf-system-requirements.md)
