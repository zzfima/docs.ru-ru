---
title: Ресурсы операционной системы, необходимые WCF
ms.date: 03/30/2017
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
ms.openlocfilehash: ac9bd5ed7c2092720c6521d0f78185c3fbf9f94b
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72318944"
---
# <a name="operating-system-resources-required-by-wcf"></a><span data-ttu-id="a5d79-102">Ресурсы операционной системы, необходимые WCF</span><span class="sxs-lookup"><span data-stu-id="a5d79-102">Operating System Resources Required by WCF</span></span>
<span data-ttu-id="a5d79-103">Windows Communication Foundation (WCF) зависит от нескольких ресурсов, предоставляемых операционной системой для работы.</span><span class="sxs-lookup"><span data-stu-id="a5d79-103">Windows Communication Foundation (WCF) depends on several resources that are provided by the operating system to function.</span></span> <span data-ttu-id="a5d79-104">В следующей таблице перечислены эти ресурсы.</span><span class="sxs-lookup"><span data-stu-id="a5d79-104">The following table lists those resources.</span></span>  
  
|<span data-ttu-id="a5d79-105">Ресурс</span><span class="sxs-lookup"><span data-stu-id="a5d79-105">Resource</span></span>|<span data-ttu-id="a5d79-106">Описание</span><span class="sxs-lookup"><span data-stu-id="a5d79-106">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="a5d79-107">Координатор распределенных транзакций (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="a5d79-107">Microsoft Distributed Transaction Coordinator (MSDTC)</span></span>|<span data-ttu-id="a5d79-108">Требуется для поддержки транзакций OleTx.</span><span class="sxs-lookup"><span data-stu-id="a5d79-108">Required to support OleTx transactions.</span></span>|  
|<span data-ttu-id="a5d79-109">службы IIS</span><span class="sxs-lookup"><span data-stu-id="a5d79-109">Internet Information Services (IIS)</span></span>|<span data-ttu-id="a5d79-110">Требуется, если необходимо использовать службы IIS для размещения приложения.</span><span class="sxs-lookup"><span data-stu-id="a5d79-110">Required if you want to use IIS to host your application.</span></span>|  
|<span data-ttu-id="a5d79-111">Служба активации Windows (WAS)</span><span class="sxs-lookup"><span data-stu-id="a5d79-111">Windows Process Activation Service (WAS)</span></span>|<span data-ttu-id="a5d79-112">Требуется, если необходимо использовать WAS для размещения приложения.</span><span class="sxs-lookup"><span data-stu-id="a5d79-112">Required if you want to use WAS to host your application.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a5d79-113">См. также</span><span class="sxs-lookup"><span data-stu-id="a5d79-113">See also</span></span>

- [<span data-ttu-id="a5d79-114">Требования к системе</span><span class="sxs-lookup"><span data-stu-id="a5d79-114">System Requirements</span></span>](wcf-system-requirements.md)
