---
title: "Интерфейс ICorPublish"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublish
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublish
helpviewer_keywords: ICorPublish interface [.NET Framework debugging]
ms.assetid: 87c4fcb2-7703-4a2e-afb6-42973381b960
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7769d26d65a97ea8d1b109e0098eae7e7d51ed10
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorpublish-interface"></a><span data-ttu-id="c7b43-102">Интерфейс ICorPublish</span><span class="sxs-lookup"><span data-stu-id="c7b43-102">ICorPublish Interface</span></span>
<span data-ttu-id="c7b43-103">Служит универсальным интерфейсом для публикации сведений о процессах и сведения о доменах приложений в этих процессов.</span><span class="sxs-lookup"><span data-stu-id="c7b43-103">Serves as the general interface for publishing information about processes and information about the application domains in those processes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c7b43-104">Методы</span><span class="sxs-lookup"><span data-stu-id="c7b43-104">Methods</span></span>  
  
|<span data-ttu-id="c7b43-105">Метод</span><span class="sxs-lookup"><span data-stu-id="c7b43-105">Method</span></span>|<span data-ttu-id="c7b43-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="c7b43-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c7b43-107">Метод EnumProcesses</span><span class="sxs-lookup"><span data-stu-id="c7b43-107">EnumProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md)|<span data-ttu-id="c7b43-108">Возвращает [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) экземпляр, содержащий управляемые процессы, запущенные на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="c7b43-108">Gets an [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instance that contains the managed processes running on this computer.</span></span>|  
|[<span data-ttu-id="c7b43-109">Метод GetProcess</span><span class="sxs-lookup"><span data-stu-id="c7b43-109">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-getprocess-method.md)|<span data-ttu-id="c7b43-110">Возвращает [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) экземпляр, представляющий процесс с указанным идентификатором.</span><span class="sxs-lookup"><span data-stu-id="c7b43-110">Gets an [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c7b43-111">Требования</span><span class="sxs-lookup"><span data-stu-id="c7b43-111">Requirements</span></span>  
 <span data-ttu-id="c7b43-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7b43-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7b43-113">**Заголовок:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="c7b43-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="c7b43-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7b43-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7b43-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7b43-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7b43-116">См. также</span><span class="sxs-lookup"><span data-stu-id="c7b43-116">See Also</span></span>  
 [<span data-ttu-id="c7b43-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="c7b43-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="c7b43-118">Кокласс CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="c7b43-118">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
