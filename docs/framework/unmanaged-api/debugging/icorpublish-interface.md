---
title: Интерфейс ICorPublish
ms.date: 03/30/2017
api_name:
- ICorPublish
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish
helpviewer_keywords:
- ICorPublish interface [.NET Framework debugging]
ms.assetid: 87c4fcb2-7703-4a2e-afb6-42973381b960
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7581d68f5c2b575403ddc84d06147f012e7ab39e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59076345"
---
# <a name="icorpublish-interface"></a><span data-ttu-id="5befb-102">Интерфейс ICorPublish</span><span class="sxs-lookup"><span data-stu-id="5befb-102">ICorPublish Interface</span></span>
<span data-ttu-id="5befb-103">Служит универсальным интерфейсом для публикации сведений о процессах и сведения о доменах приложений в этих процессах.</span><span class="sxs-lookup"><span data-stu-id="5befb-103">Serves as the general interface for publishing information about processes and information about the application domains in those processes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5befb-104">Методы</span><span class="sxs-lookup"><span data-stu-id="5befb-104">Methods</span></span>  
  
|<span data-ttu-id="5befb-105">Метод</span><span class="sxs-lookup"><span data-stu-id="5befb-105">Method</span></span>|<span data-ttu-id="5befb-106">Описание</span><span class="sxs-lookup"><span data-stu-id="5befb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5befb-107">Метод EnumProcesses</span><span class="sxs-lookup"><span data-stu-id="5befb-107">EnumProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md)|<span data-ttu-id="5befb-108">Получает [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) экземпляру, содержащему управляемых процессов, запущенных на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="5befb-108">Gets an [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instance that contains the managed processes running on this computer.</span></span>|  
|[<span data-ttu-id="5befb-109">Метод GetProcess</span><span class="sxs-lookup"><span data-stu-id="5befb-109">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-getprocess-method.md)|<span data-ttu-id="5befb-110">Получает [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) экземпляр, представляющий процесс с указанным идентификатором.</span><span class="sxs-lookup"><span data-stu-id="5befb-110">Gets an [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5befb-111">Требования</span><span class="sxs-lookup"><span data-stu-id="5befb-111">Requirements</span></span>  
 <span data-ttu-id="5befb-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5befb-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5befb-113">**Заголовок.** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="5befb-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="5befb-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5befb-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="5befb-115">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="5befb-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5befb-116">См. также</span><span class="sxs-lookup"><span data-stu-id="5befb-116">See also</span></span>

- [<span data-ttu-id="5befb-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="5befb-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="5befb-118">Кокласс CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="5befb-118">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
